<!-- START: Animated GitHub Profile Section -->
<style>
  /* Keyframe animation for fade-in and zoom */
  @keyframes fadeInZoomIn {
    0% {opacity: 0; transform: scale(0.5);}
    100% {opacity: 1; transform: scale(1);}
  }

  /* Container for fade-in zoom effect */
  .animate-fade-zoom {
    animation: fadeInZoomIn 1s ease forwards;
    display: inline-block;
  }

  /* Hover grow effect */
  .hover-grow:hover {
    transform: scale(1.1);
    transition: transform 0.3s ease;
  }

  /* Skill bars container style */
  .skill-bar {
    width: 100%;
    max-width: 300px;
    background: #eee;
    border-radius: 10px;
    overflow: hidden;
    margin: 12px 0;
  }

  /* Skill bars fill animation */
  .skill-bar-fill {
    height: 20px;
    width: 0;
    background: linear-gradient(90deg, #4caf50, #81c784);
    animation: fillBar 2s forwards;
    border-radius: 10px;
  }

  /* Custom property to control bar width */
  .skill-html { --skill-level: 90%; }
  .skill-css { --skill-level: 85%; }
  .skill-js { --skill-level: 75%; }

  @keyframes fillBar {
    to { width: var(--skill-level); }
  }

  /* Spinner animation for progress indicator */
  .spinner {
    border: 4px solid #f3f3f3;
    border-top: 4px solid #4caf50;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    animation: spin 1s linear infinite;
    margin: 20px auto;
  }

  @keyframes spin {
    0% { transform: rotate(0); }
    100% { transform: rotate(360deg); }
  }

  /* Hover card style */
  .card {
    width: 280px;
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 15px;
    transition: transform 0.3s, box-shadow 0.3s;
    cursor: pointer;
    margin: 15px auto;
    background: #fafafa;
  }

  .card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.15);
  }

  /* Centered text and layout */
  .center {
    text-align: center;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
    color: #333;
    max-width: 360px;
    margin: auto;
  }
</style>

<div class="center">
  <h2 class="animate-fade-zoom hover-grow">Hi, I'm Salil Gupta 👋</h2>
  <p>Computer Science Engineer @ GL Bajaj Institute of Technology & Management</p>

  <!-- Animated SVG Circle -->
  <svg width="100" height="100" viewBox="0 0 100 100" class="animate-fade-zoom">
    <circle cx="50" cy="50" r="40" stroke="#4caf50" stroke-width="4" fill="#a5d6a7">
      <animate attributeName="r" values="10;40;10" dur="3s" repeatCount="indefinite" />
    </circle>
  </svg>

  <h3>Skills</h3>

  <div class="skill-bar skill-html">
    <div class="skill-bar-fill"></div>
  </div>
  <div class="skill-bar skill-css">
    <div class="skill-bar-fill"></div>
  </div>
  <div class="skill-bar skill-js">
    <div class="skill-bar-fill"></div>
  </div>

  <!-- Spinner for loading/process effect -->
  <div class="spinner"></div>

  <!-- Hover Card -->
  <div class="card hover-grow">
    <strong>Featured Project</strong>
    <p>Interactive Portfolio Website with animations and clean UI design.</p>
    <a href="https://github.com/yourusername/yourproject" target="_blank">View on GitHub</a>
  </div>
</div>
<!-- END: Animated GitHub Profile Section -->
