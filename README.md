<!-- START: Animated GitHub Profile Section -->
<style>
  /* Keyframe animation for fade-in and zoom */
  @keyframes fadeInZoomIn {
    0% {
      opacity: 0;
      transform: scale(0.5);
    }
    100% {
      opacity: 1;
      transform: scale(1);
    }
  }

  /* Hover grow effect */
  .hover-grow:hover {
    transform: scale(1.1);
    transition: transform 0.3s ease;
  }

  /* Skill bar container styling */
  .skill-bar {
    width: 100%;
    max-width: 320px;
    background: #eee;
    border-radius: 12px;
    overflow: hidden;
    margin: 15px auto;
  }

  /* Skill bar fill with animation */
  .skill-bar-fill {
    height: 22px;
    width: 0;
    background: linear-gradient(90deg, #4caf50, #81c784);
    border-radius: 12px;
    animation: fillBar 2s forwards;
  }

  /* Skill level percentages via CSS variables */
  .skill-html {
    --skill-level: 90%;
  }
  .skill-css {
    --skill-level: 85%;
  }
  .skill-js {
    --skill-level: 75%;
  }
  .skill-react {
    --skill-level: 70%;
  }
  .skill-node {
    --skill-level: 60%;
  }

  @keyframes fillBar {
    to {
      width: var(--skill-level);
    }
  }

  /* Spinner animation */
  .spinner {
    border: 5px solid #f3f3f3;
    border-top: 5px solid #4caf50;
    border-radius: 50%;
    width: 48px;
    height: 48px;
    animation: spin 1s linear infinite;
    margin: 30px auto;
  }

  @keyframes spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }

  /* Hover card styling */
  .card {
    width: 320px;
    background: #fafafa;
    border: 1px solid #ccc;
    border-radius: 15px;
    padding: 18px 20px;
    margin: 25px auto;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
  }
  .card:hover {
    transform: translateY(-8px);
    box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
  }

  /* Center container */
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
  <h1 class="hover-grow" style="animation: fadeInZoomIn 1s ease forwards;">Hi, I'm Salil Gupta 👋</h1>
  <p>Computer Science Engineer at GL Bajaj Institute of Technology & Management</p>

  <!-- Animated SVG Circle -->
  <svg
    width="120"
    height="120"
    viewBox="0 0 100 100"
    style="margin: 20px auto; display: block;"
  >
    <circle cx="50" cy="50" r="40" stroke="#4caf50" stroke-width="4" fill="#a5d6a7">
      <animate
        attributeName="r"
        values="10;40;10"
        dur="3s"
        repeatCount="indefinite"
      />
    </circle>
  </svg>

  <h2 style="margin-top: 35px;">Skills & Expertise</h2>

  <!-- Skill bars -->
  <div class="skill-bar skill-html">
    <div class="skill-bar-fill"></div>
  </div>
  <div class="skill-bar skill-css">
    <div class="skill-bar-fill"></div>
  </div>
  <div class="skill-bar skill-js">
    <div class="skill-bar-fill"></div>
  </div>
  <div class="skill-bar skill-react">
    <div class="skill-bar-fill"></div>
  </div>
  <div class="skill-bar skill-node">
    <div class="skill-bar-fill"></div>
  </div>

  <!-- Spinner loader -->
  <div class="spinner"></div>

  <!-- Hover card for featured project -->
  <div class="card hover-grow">
    <strong>Featured Project</strong>
    <p>
      Interactive Portfolio Website with animations, clean design, and responsive
      UI.
    </p>
    <a
      href="https://github.com/yourusername/yourproject"
      target="_blank"
      rel="noopener noreferrer"
      >View on GitHub</a
    >
  </div>
</div>

<!-- END: Animated GitHub Profile Section -->
