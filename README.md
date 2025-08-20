<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Salil's Retro Arcade</title>
  <style>
    :root { --bg:#0b0f1a; --panel:#12172a; --accent:#58a6ff; --good:#22c55e; --bad:#ef4444; --text:#e5e7eb; }
    html, body { height: 100%; margin: 0; background: radial-gradient(1200px 600px at 50% -10%, #1e293b 0%, #0b0f1a 55%, #05070e 100%); font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace; color: var(--text); }
    .wrap { max-width: 1100px; margin: 24px auto; padding: 16px; }
    .card { background: linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,.01)); border: 1px solid rgba(255,255,255,.08); border-radius: 16px; box-shadow: 0 10px 30px rgba(0,0,0,.35); }
    .header { display: grid; grid-template-columns: 1fr auto; gap: 12px; align-items: center; padding: 16px 18px; }
    .title { font-size: clamp(18px, 3vw, 28px); letter-spacing: 1px; }
    .links a { text-decoration: none; color: var(--bg); background: var(--accent); padding: 8px 12px; border-radius: 999px; font-weight: 700; margin-left: 8px; box-shadow: inset 0 -2px 0 rgba(0,0,0,.25); }
    .links a.secondary { background: transparent; color: var(--text); border: 1px solid rgba(255,255,255,.2); }

    .hud { display:grid; grid-template-columns: repeat(4, 1fr); gap: 10px; padding: 10px 14px; border-top: 1px solid rgba(255,255,255,.08); border-bottom: 1px solid rgba(255,255,255,.08); background: rgba(0,0,0,.25); }
    .hud .pill { background: rgba(255,255,255,.06); border: 1px solid rgba(255,255,255,.12); border-radius: 999px; padding: 8px 12px; text-align:center; }

    .game { position: relative; padding: 14px; }
    canvas { display:block; width:100%; height:auto; border-radius: 12px; background: linear-gradient(180deg, #0b1224, #060910); image-rendering: pixelated; }

    .footer { display:flex; justify-content: space-between; align-items:center; padding: 12px 16px; font-size: 13px; opacity:.9 }
    .kbd { display:inline-block; padding:2px 6px; border-radius:6px; border:1px solid rgba(255,255,255,.25); background: rgba(255,255,255,.06); }

    /* secret */
    .secret { display:none; padding: 14px 18px; border-top: 1px dashed rgba(255,255,255,.2); }
    .secret.show { display:block; animation: pop .35s ease; }
    @keyframes pop { from { transform: scale(.96); opacity: 0 } to { transform: scale(1); opacity: 1 } }

    @media (max-width:720px){ .hud{grid-template-columns: repeat(2,1fr);} .links{display:flex;flex-wrap:wrap;gap:8px} .links a{margin:0} }
  </style>
</head>
<body>
  <div class="wrap card">
    <div class="header">
      <div class="title">🕹️ Salil Gupta — Retro Arcade Portfolio</div>
      <div class="links">
        <a href="https://github.com/salilgupta17" target="_blank" rel="noopener">⭐ GitHub</a>
        <a class="secondary" href="https://linkedin.com/in/salilgupta17" target="_blank" rel="noopener">🔗 LinkedIn</a>
      </div>
    </div>

    <div class="hud" id="hud">
      <div class="pill">Score: <span id="score">0</span></div>
      <div class="pill">Level: <span id="level">1</span></div>
      <div class="pill">Lives: <span id="lives">3</span></div>
      <div class="pill">Best: <span id="best">0</span></div>
    </div>

    <div class="game">
      <canvas id="game" width="900" height="520" aria-label="Retro arcade canvas"></canvas>
    </div>

    <div class="footer">
      <div>
        Controls: <span class="kbd">←</span> <span class="kbd">→</span> to move • <span class="kbd">Space</span> to dash
      </div>
      <div>Find the secret by entering the Konami code: ↑ ↑ ↓ ↓ ← → ← → B A</div>
    </div>

    <div id="secret" class="secret">🎉 Secret Unlocked! You found the easter egg. Check out my <a href="https://github.com/salilgupta17?tab=repositories" target="_blank" rel="noopener">top repos</a>.</div>
  </div>

  <script>
    // === GAME SETUP (one-file, no libs) ===
    const C = document.getElementById('game');
    const ctx = C.getContext('2d');
    const W = C.width, H = C.height;

    // world params
    const state = {
      running: true,
      score: 0,
      level: 1,
      lives: 3,
      best: Number(localStorage.getItem('bestScoreArcade')||0),
      t: 0
    };

    // player
    const player = { x: W/2, y: H-60, w: 26, h: 26, vx: 0, speed: 5.0, dash: 0 };

    // entities
    const coins = []; // good pickups
    const foes = [];  // bad obstacles

    // input
    const keys = new Set();
    addEventListener('keydown', e => { keys.add(e.key); if(["ArrowLeft","ArrowRight"," ","Spacebar"].includes(e.key)) e.preventDefault(); });
    addEventListener('keyup',   e => keys.delete(e.key));

    // helpers
    const rnd = (a,b)=>Math.random()*(b-a)+a;
    const clamp = (v,a,b)=>Math.max(a,Math.min(b,v));
    function rects(a,b){ return (a.x < b.x+b.w && a.x+a.w > b.x && a.y < b.y+b.h && a.y+a.h > b.y); }

    function spawnCoin(){ coins.push({ x: rnd(20,W-40), y: -20, w: 14, h: 14, vy: rnd(1.0, 2.4) + state.level*0.1 }); }
    function spawnFoe(){ foes.push({ x: rnd(20,W-40), y: -26, w: 24, h: 24, vy: rnd(1.2, 2.8) + state.level*0.12 }); }

    // draw helpers
    function drawPixelRect(x,y,w,h, col1, col2){
      // border
      ctx.fillStyle = col2; ctx.fillRect(x-1,y-1,w+2,h+2);
      ctx.fillStyle = col1; ctx.fillRect(x,y,w,h);
    }

    function glowText(txt,x,y){
      ctx.save(); ctx.shadowColor = '#58a6ff'; ctx.shadowBlur=14; ctx.fillStyle = '#cbe7ff'; ctx.font = '700 16px monospace'; ctx.fillText(txt,x,y); ctx.restore();
    }

    // main loop
    function loop(){
      if(!state.running){ requestAnimationFrame(loop); return; }
      state.t++;

      // spawn pacing
      if(state.t % Math.max(20, 60 - state.level*3) === 0) spawnCoin();
      if(state.t % Math.max(30, 90 - state.level*4) === 0) spawnFoe();

      // physics
      player.vx = (keys.has('ArrowLeft')?-1:0) + (keys.has('ArrowRight')?1:0);
      let spd = player.speed + state.level*0.05;
      if(keys.has(' ')||keys.has('Spacebar')){ if(player.dash<=0){ player.dash=14; } }
      if(player.dash>0){ spd *= 2.2; player.dash--; }
      player.x = clamp(player.x + player.vx * spd, 10, W-10-player.w);

      coins.forEach(c=> c.y += c.vy);
      foes.forEach(f=> f.y += f.vy);

      // collisions
      for(let i=coins.length-1;i>=0;i--){ const c=coins[i]; if(rects(player,c)){ coins.splice(i,1); state.score+=10; if(state.score % 100 === 0){ state.level++; } }
        else if(c.y>H+20){ coins.splice(i,1); }
      }
      for(let i=foes.length-1;i>=0;i--){ const f=foes[i]; if(rects(player,f)){ foes.splice(i,1); hit(); }
        else if(f.y>H+26){ foes.splice(i,1); }
      }

      // render
      ctx.clearRect(0,0,W,H);

      // starfield bg
      for(let i=0;i<60;i++){ const x=(i*73 + state.t*0.6)%W; const y=(i*41 + state.t*0.4)%H; ctx.fillStyle = 'rgba(255,255,255,.06)'; ctx.fillRect(x,y,2,2); }

      // player
      drawPixelRect(player.x, player.y, player.w, player.h, '#22c55e', '#134e4a');

      // coins
      coins.forEach(c=>{ drawPixelRect(c.x, c.y, c.w, c.h, '#fbbf24', '#7c2d12'); });
      // foes
      foes.forEach(f=>{ drawPixelRect(f.x, f.y, f.w, f.h, '#ef4444', '#7f1d1d'); });

      glowText('Score: '+state.score, 16, 28);
      glowText('Level: '+state.level, 140, 28);
      glowText('Lives: '+state.lives, 260, 28);
      requestAnimationFrame(loop);
    }

    function hit(){
      state.lives--; shake(10);
      if(state.lives<=0){
        state.best = Math.max(state.best, state.score); localStorage.setItem('bestScoreArcade', state.best);
        gameOver();
      }
      updateHUD();
    }

    function updateHUD(){
      document.getElementById('score').textContent = state.score;
      document.getElementById('level').textContent = state.level;
      document.getElementById('lives').textContent = state.lives;
      document.getElementById('best').textContent = state.best;
    }

    function gameOver(){
      state.running=false;
      ctx.save(); ctx.fillStyle='rgba(0,0,0,.6)'; ctx.fillRect(0,0,W,H);
      ctx.fillStyle='#e5e7eb'; ctx.font='700 40px monospace'; ctx.textAlign='center';
      ctx.fillText('GAME OVER', W/2, H/2-20);
      ctx.font='16px monospace';
      ctx.fillText('Press R to restart', W/2, H/2+20);
      ctx.restore();
    }

    function restart(){
      state.running=true; state.score=0; state.level=1; state.lives=3; coins.length=0; foes.length=0; player.x=W/2; player.dash=0; updateHUD();
    }

    addEventListener('keydown', e=>{ if(e.key==='r' || e.key==='R'){ restart(); } });

    // tiny screen shake
    function shake(n){ let i=0; const base = C.style.transform; const id=setInterval(()=>{ i++; C.style.transform=`translate(${(Math.random()*2-1)*4}px, ${(Math.random()*2-1)*3}px)`; if(i>n){ clearInterval(id); C.style.transform=base; } }, 20); }

    updateHUD();
    loop();

    // === KONAMI CODE (unlocks secret bar) ===
    (function(){ const seq=["ArrowUp","ArrowUp","ArrowDown","ArrowDown","ArrowLeft","ArrowRight","ArrowLeft","ArrowRight","b","a"]; let i=0; window.addEventListener('keydown', e=>{ i = (e.key===seq[i]) ? i+1 : (e.key===seq[0]?1:0); if(i===seq.length){ document.getElementById('secret').classList.add('show'); i=0; } },{passive:true});})();
  </script>
</body>
</html>
