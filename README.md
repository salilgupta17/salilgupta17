# 🎮 Welcome to My Arcade — Salil Gupta

> *Insert coins to start…*

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Press+Start+2P&size=18&duration=2500&pause=600&center=true&vCenter=true&multiline=true&repeat=true&width=800&height=100&lines=Hi%2C+I'm+Salil+Gupta!;Full-stack+%E2%9A%A1+Game-flavored+Developer;React+%7C+Node.js+%7C+C%2B%2B+%7C+MongoDB" alt="typing intro"/>
</p>

<p align="center">
  <a href="https://github.com/salilgupta17?tab=repositories"><img alt="Stars" src="https://custom-icon-badges.demolab.com/github/stars/salilgupta17?logo=star&logoColor=fff"></a>
  <a href="https://visitorbadge.io/status?path=salilgupta17"><img alt="Visitors" src="https://visitorbadge.io/api/visitors?path=salilgupta17&label=VISITORS&countColor=%23263759"></a>
  <a href="https://linkedin.com/in/salilgupta17"><img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-Press%20Start%20%E2%86%92-1e90ff"></a>
  <!-- Optional: add email -->
  <!-- <a href="mailto:YOUR_EMAIL"><img alt="Email" src="https://img.shields.io/badge/Contact-Email-ff69b4"></a> -->
</p>

---

## 🕹️ Mini-Game: Konami Code Easter Egg
*(visit my portfolio and try ↑ ↑ ↓ ↓ ← → ← → B A)*  

```html
<script>
(function(){
  const konami = ["ArrowUp","ArrowUp","ArrowDown","ArrowDown","ArrowLeft","ArrowRight","ArrowLeft","ArrowRight","b","a"];
  let idx=0;
  window.addEventListener('keydown',e=>{
    idx = (e.key===konami[idx])? idx+1 : (e.key===konami[0]?1:0);
    if(idx===konami.length){
      alert('🧩 Secret Unlocked!');
      document.body.classList.add('show-secret');
      idx=0;
    }
  });
})();
</script>
