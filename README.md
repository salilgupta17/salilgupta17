# 🚀 Salil Gupta - Computer Science Student

<div align="center">
  
  ![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=30&color=%2336BCF7&center=true&vCenter=true&width=700&lines=Computer+Science+Student;Software+Engineering+Enthusiast;Full+Stack+Developer;Problem+Solver+%26+Innovator;Building+Tomorrow's+Technology)
  
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,24,25,30&height=150&section=header&text=SALIL%20GUPTA&fontSize=45&fontColor=fff&animation=fadeIn&fontAlignY=38"/>
  
</div>

## 👨‍💻 Professional Overview

> *"Passionate about transforming complex problems into elegant software solutions through innovative thinking and continuous learning."*

🎓 **Education**: B.Tech Computer Science & Engineering - GL Bajaj Institute of Technology & Management  
💼 **Focus**: Full Stack Development & Software Engineering  
🌱 **Currently Learning**: Advanced algorithms, system design, cloud technologies  
🎯 **Career Goal**: Building scalable software solutions that impact millions of users  
⚡ **Philosophy**: Clean code, efficient algorithms, user-centric design  

---

## 🎮 Interactive Skill Dashboard

<div align="center">

### 💻 Click to Explore My Tech Arsenal! 💻

<div class="skill-dashboard">
  <div class="skill-category" onclick="toggleSkillDetails('frontend')">
    <h3>🎨 Frontend Development</h3>
    <div class="progress-bar">
      <div class="progress-fill frontend-fill" style="width: 85%"></div>
    </div>
    <div class="skill-details" id="frontend-details">
      <p><strong>React.js, Next.js, Vue.js, HTML5/CSS3, JavaScript/TypeScript</strong></p>
      <p>Building responsive, interactive user interfaces with modern frameworks</p>
    </div>
  </div>
  
  <div class="skill-category" onclick="toggleSkillDetails('backend')">
    <h3>⚙️ Backend Development</h3>
    <div class="progress-bar">
      <div class="progress-fill backend-fill" style="width: 80%"></div>
    </div>
    <div class="skill-details" id="backend-details">
      <p><strong>Node.js, Express.js, Python, Java, RESTful APIs</strong></p>
      <p>Creating robust server-side applications and efficient APIs</p>
    </div>
  </div>
  
  <div class="skill-category" onclick="toggleSkillDetails('database')">
    <h3>🗄️ Database Management</h3>
    <div class="progress-bar">
      <div class="progress-fill database-fill" style="width: 75%"></div>
    </div>
    <div class="skill-details" id="database-details">
      <p><strong>MongoDB, MySQL, PostgreSQL, Database Design</strong></p>
      <p>Designing efficient data structures and optimizing queries</p>
    </div>
  </div>
  
  <div class="skill-category" onclick="toggleSkillDetails('tools')">
    <h3>🛠️ Development Tools</h3>
    <div class="progress-bar">
      <div class="progress-fill tools-fill" style="width: 90%"></div>
    </div>
    <div class="skill-details" id="tools-details">
      <p><strong>Git, GitHub, VS Code, Docker, Linux, AWS</strong></p>
      <p>Proficient with modern development workflows and deployment</p>
    </div>
  </div>
</div>

</div>

<style>
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes progressFill {
  from { width: 0%; }
  to { width: var(--target-width); }
}

@keyframes glow {
  0% { box-shadow: 0 0 5px rgba(54, 188, 247, 0.3); }
  50% { box-shadow: 0 0 20px rgba(54, 188, 247, 0.6); }
  100% { box-shadow: 0 0 5px rgba(54, 188, 247, 0.3); }
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
  40% { transform: translateY(-5px); }
  60% { transform: translateY(-3px); }
}

.skill-dashboard {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  margin: 30px 0;
  padding: 20px;
}

.skill-category {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 15px;
  padding: 25px;
  cursor: pointer;
  transition: all 0.4s ease;
  border: 2px solid transparent;
  animation: fadeIn 0.6s ease;
}

.skill-category:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: 0 15px 30px rgba(102, 126, 234, 0.4);
  border: 2px solid #36BCF7;
  animation: bounce 0.6s ease, glow 2s infinite;
}

.skill-category h3 {
  color: white;
  margin: 0 0 15px 0;
  font-size: 1.3em;
}

.progress-bar {
  width: 100%;
  height: 8px;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 10px;
  overflow: hidden;
  margin: 15px 0;
}

.progress-fill {
  height: 100%;
  border-radius: 10px;
  transition: all 1s ease;
  position: relative;
}

.frontend-fill { background: linear-gradient(90deg, #36BCF7, #667eea); }
.backend-fill { background: linear-gradient(90deg, #764ba2, #667eea); }
.database-fill { background: linear-gradient(90deg, #f093fb, #f5576c); }
.tools-fill { background: linear-gradient(90deg, #4facfe, #00f2fe); }

.skill-details {
  color: white;
  margin-top: 15px;
  opacity: 0;
  max-height: 0;
  overflow: hidden;
  transition: all 0.4s ease;
}

.skill-details.active {
  opacity: 1;
  max-height: 100px;
}

.skill-details p {
  margin: 8px 0;
  font-size: 0.9em;
}

.achievement-card {
  background: linear-gradient(45deg, #1a1a2e, #16213e);
  border: 2px solid #36BCF7;
  border-radius: 15px;
  padding: 20px;
  margin: 15px;
  transition: all 0.5s ease;
  cursor: pointer;
}

.achievement-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 40px rgba(54, 188, 247, 0.3);
  border-color: #667eea;
}

.project-showcase {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 25px;
  margin: 30px 0;
}

.project-card {
  background: linear-gradient(135deg, #2c3e50, #3498db);
  border-radius: 20px;
  padding: 25px;
  color: white;
  transition: all 0.4s ease;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.project-card::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
  transform: rotate(45deg);
  transition: all 0.6s ease;
  opacity: 0;
}

.project-card:hover::before {
  opacity: 1;
  transform: rotate(45deg) translate(50%, 50%);
}

.project-card:hover {
  transform: translateY(-10px) rotateX(5deg);
  box-shadow: 0 25px 50px rgba(52, 152, 219, 0.3);
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  margin: 30px 0;
}

.stat-card {
  background: linear-gradient(135deg, #667eea, #764ba2);
  border-radius: 15px;
  padding: 20px;
  text-align: center;
  color: white;
  transition: all 0.3s ease;
  cursor: pointer;
}

.stat-card:hover {
  transform: scale(1.05) rotateY(5deg);
  box-shadow: 0 15px 30px rgba(102, 126, 234, 0.4);
}

.stat-number {
  font-size: 2.5em;
  font-weight: bold;
  margin: 10px 0;
}

.stat-label {
  font-size: 1.1em;
  opacity: 0.9;
}
</style>

<script>
function toggleSkillDetails(skillId) {
  const details = document.getElementById(skillId + '-details');
  details.classList.toggle('active');
  
  // Add some visual feedback
  const category = details.parentElement;
  if (details.classList.contains('active')) {
    category.style.background = 'linear-gradient(135deg, #36BCF7, #667eea)';
  } else {
    category.style.background = 'linear-gradient(135deg, #667eea, #764ba2)';
  }
}

// Add progress bar animation on page load
window.addEventListener('load', () => {
  const progressBars = document.querySelectorAll('.progress-fill');
  progressBars.forEach((bar, index) => {
    setTimeout(() => {
      bar.style.animation = 'progressFill 2s ease forwards';
    }, index * 200);
  });
});

// Add click counter for engagement
let clickCount = 0;
function trackEngagement() {
  clickCount++;
  if (clickCount === 5) {
    showAchievement('Curious Explorer', 'You\'ve explored 5 sections!');
  }
}

function showAchievement(title, description) {
  const achievement = document.createElement('div');
  achievement.style.cssText = `
    position: fixed;
    top: 20px;
    right: 20px;
    background: linear-gradient(45deg, #36BCF7, #667eea);
    color: white;
    padding: 15px 20px;
    border-radius: 10px;
    box-shadow: 0 10px 25px rgba(54, 188, 247, 0.3);
    z-index: 1000;
    animation: fadeIn 0.5s ease;
  `;
  achievement.innerHTML = `<strong>🏆 ${title}</strong><br/>${description}`;
  document.body.appendChild(achievement);
  
  setTimeout(() => achievement.remove(), 3000);
}

// Add event listeners to track clicks
document.addEventListener('click', trackEngagement);
</script>

## 🚀 Featured Projects Portfolio

<div class="project-showcase">

<div class="project-card">
  <h3>🏪 E-Commerce Platform</h3>
  <p><strong>Tech Stack:</strong> React, Node.js, MongoDB, Stripe API</p>
  <p><strong>Features:</strong> Complete shopping cart, payment integration, admin dashboard, inventory management</p>
  <p><strong>Impact:</strong> Full-featured online store with secure transactions</p>
  <div style="margin-top: 15px;">
    <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React"/>
    <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white" alt="Node.js"/>
    <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" alt="MongoDB"/>
  </div>
</div>

<div class="project-card">
  <h3>📊 Task Management System</h3>
  <p><strong>Tech Stack:</strong> Next.js, TypeScript, PostgreSQL, Tailwind CSS</p>
  <p><strong>Features:</strong> Project tracking, team collaboration, real-time updates, analytics dashboard</p>
  <p><strong>Impact:</strong> Increased team productivity by 40% in testing</p>
  <div style="margin-top: 15px;">
    <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white" alt="Next.js"/>
    <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"/>
    <img src="https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  </div>
</div>

<div class="project-card">
  <h3>🌤️ Weather Analytics Dashboard</h3>
  <p><strong>Tech Stack:</strong> Vue.js, Python Flask, Chart.js, Weather APIs</p>
  <p><strong>Features:</strong> Real-time weather data, historical trends, interactive charts, location-based forecasts</p>
  <p><strong>Impact:</strong> Comprehensive weather analysis tool</p>
  <div style="margin-top: 15px;">
    <img src="https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vue.js&logoColor=white" alt="Vue.js"/>
    <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
    <img src="https://img.shields.io/badge/Chart.js-FF6384?style=flat-square&logo=chart.js&logoColor=white" alt="Chart.js"/>
  </div>
</div>

<div class="project-card">
  <h3>🎓 Student Portal System</h3>
  <p><strong>Tech Stack:</strong> Java Spring Boot, MySQL, Thymeleaf, Bootstrap</p>
  <p><strong>Features:</strong> Student information management, grade tracking, course enrollment, attendance monitoring</p>
  <p><strong>Impact:</strong> Academic project for GL Bajaj institute</p>
  <div style="margin-top: 15px;">
    <img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=java&logoColor=white" alt="Java"/>
    <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=spring&logoColor=white" alt="Spring Boot"/>
    <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="MySQL"/>
  </div>
</div>

</div>

## 📈 Academic & Professional Achievements

<div class="stats-grid">

<div class="achievement-card stat-card">
  <div class="stat-number">15+</div>
  <div class="stat-label">Projects Completed</div>
</div>

<div class="achievement-card stat-card">
  <div class="stat-number">8.5</div>
  <div class="stat-label">CGPA Maintained</div>
</div>

<div class="achievement-card stat-card">
  <div class="stat-number">500+</div>
  <div class="stat-label">GitHub Contributions</div>
</div>

<div class="achievement-card stat-card">
  <div class="stat-number">3</div>
  <div class="stat-label">Hackathons Won</div>
</div>

</div>

### 🎓 Academic Excellence
- 📚 **Relevant Coursework**: Data Structures, Algorithms, DBMS, Software Engineering, Computer Networks
- 🏆 **Achievements**: Dean's List, Academic Excellence Award, Top 10% of class
- 💡 **Research Interests**: Machine Learning, Web Technologies, System Design
- 👥 **Leadership**: Technical Lead in Computer Science Society

## 📊 GitHub Analytics Dashboard

<div align="center">
  
<div class="achievement-card">
  <img height="200em" src="https://github-readme-stats.vercel.app/api?username=salilgupta17&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true"/>
</div>

<div class="achievement-card">
  <img height="200em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=salilgupta17&layout=compact&langs_count=8&theme=tokyonight"/>
</div>
  
<div class="achievement-card">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=salilgupta17&theme=tokyonight" alt="GitHub Streak"/>
</div>
  
<div class="achievement-card">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=salilgupta17&theme=tokyo-night&bg_color=1a1b27&color=70a5fd&line=bf91f3&point=1a1b27&area=true&hide_border=true"/>
</div>

</div>

## 🌐 Professional Connect

<div align="center">

### 📧 Let's Build Something Amazing Together

**📧 Email**: [salilgupta17@gmail.com](mailto:salilgupta17@gmail.com)  
**💼 LinkedIn**: [Connect for opportunities](YOUR_LINKEDIN_PROFILE)  
**🌐 Portfolio**: [View my complete work](YOUR_PORTFOLIO_WEBSITE)  

### 🔗 Professional Networks

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](YOUR_LINKEDIN)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/salilgupta17)
[![Portfolio](https://img.shields.io/badge/Portfolio-255E63?style=for-the-badge&logo=About.me&logoColor=white)](YOUR_PORTFOLIO)
[![Email](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:salilgupta17@gmail.com)

</div>

## 🚀 Current Learning Path

### 🎯 2024 Goals & Focus Areas
- **Advanced Frontend**: Mastering React ecosystem, performance optimization
- **Backend Scalability**: Microservices architecture, cloud deployment
- **Data Science**: Python for data analysis, machine learning fundamentals  
- **DevOps**: Docker containerization, CI/CD pipelines, AWS services
- **Open Source**: Contributing to meaningful projects, building community

### 💡 What Drives Me
- 🔥 **Passion for Problem Solving**: Love tackling complex technical challenges
- 🚀 **Innovation Mindset**: Always exploring new technologies and methodologies
- 👥 **Team Collaboration**: Believe in the power of collective intelligence
- 📚 **Continuous Learning**: Staying updated with industry trends and best practices
- 🌟 **Quality Focus**: Writing clean, maintainable, and efficient code

---

<div align="center">
  
  <img src="https://github-profile-trophy.vercel.app/?username=salilgupta17&theme=tokyonight&column=3&margin-w=15&margin-h=15"/>
  
  ### 💫 *"Innovation distinguishes between a leader and a follower"* 💫
  
  **⭐ Interested in collaboration? Let's connect and create! ⭐**
  
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,24,25,30&height=120&section=footer&animation=fadeIn"/>
  
  ![Profile Views](https://komarev.com/ghpvc/?username=salilgupta17&color=36BCF7&style=for-the-badge)
  
  *🚀 Ready to contribute to impactful projects and innovative solutions! 🚀*
  
</div>

<!-- 
📝 CUSTOMIZATION CHECKLIST:
✅ Replace YOUR_LINKEDIN with actual LinkedIn profile
✅ Replace YOUR_PORTFOLIO with portfolio website  
✅ Update email if different from salilgupta17@gmail.com
✅ Add actual CGPA and achievements
✅ Customize project details with real repositories
✅ Update learning goals based on interests
✅ Add specific coursework and grades if desired
-->
