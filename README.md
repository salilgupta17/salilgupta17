<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Salil Gupta - Full Stack Developer Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(-45deg, #667eea, #764ba2, #f093fb, #f5576c, #4facfe, #00f2fe);
            background-size: 400% 400%;
            animation: gradientShift 20s ease infinite;
            font-family: 'Courier New', monospace;
            overflow-x: hidden;
            color: white;
            position: relative;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            25% { background-position: 100% 50%; }
            50% { background-position: 100% 100%; }
            75% { background-position: 0% 100%; }
            100% { background-position: 0% 50%; }
        }

        /* Enhanced Floating Particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            overflow: hidden;
        }

        .particle {
            position: absolute;
            border-radius: 50%;
            animation: float 8s ease-in-out infinite;
        }

        .particle.code::before {
            content: '{}';
            color: rgba(255, 255, 255, 0.6);
            font-size: 12px;
            position: absolute;
            top: -2px;
            left: -2px;
        }

        .particle.react::before {
            content: '⚛️';
            font-size: 16px;
            position: absolute;
            top: -8px;
            left: -8px;
        }

        .particle.js::before {
            content: 'JS';
            color: #f7df1e;
            font-size: 10px;
            font-weight: bold;
            position: absolute;
            top: -5px;
            left: -7px;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) translateX(0px) rotate(0deg); opacity: 1; }
            25% { transform: translateY(-50px) translateX(25px) rotate(90deg); opacity: 0.8; }
            50% { transform: translateY(-100px) translateX(-25px) rotate(180deg); opacity: 0.6; }
            75% { transform: translateY(-75px) translateX(-50px) rotate(270deg); opacity: 0.8; }
        }

        /* Animated Header */
        .header {
            text-align: center;
            padding: 50px 20px;
            position: relative;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .main-title {
            font-size: 5rem;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #f093fb, #f5576c);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 3s ease infinite, titleFloat 4s ease-in-out infinite, textGlow 2s ease-in-out infinite;
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
            position: relative;
        }

        @keyframes titleFloat {
            0%, 100% { transform: translateY(0px) scale(1) rotateX(0deg); }
            50% { transform: translateY(-20px) scale(1.02) rotateX(5deg); }
        }

        @keyframes textGlow {
            0%, 100% { filter: drop-shadow(0 0 10px rgba(255, 255, 255, 0.3)); }
            50% { filter: drop-shadow(0 0 20px rgba(255, 255, 255, 0.6)); }
        }

        .subtitle {
            font-size: 1.8rem;
            margin-bottom: 30px;
            animation: typewriter 6s steps(50, end), blink 0.75s step-end infinite;
            white-space: nowrap;
            overflow: hidden;
            border-right: 3px solid #ff6b6b;
            display: inline-block;
            max-width: 100%;
        }

        @keyframes typewriter {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink {
            from, to { border-color: transparent; }
            50% { border-color: #ff6b6b; }
        }

        /* Programming Languages Section */
        .languages-section {
            margin: 80px 20px;
            text-align: center;
        }

        .section-title {
            font-size: 3rem;
            margin-bottom: 40px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: slideInFromLeft 1s ease-out;
        }

        @keyframes slideInFromLeft {
            0% { transform: translateX(-100px); opacity: 0; }
            100% { transform: translateX(0); opacity: 1; }
        }

        .languages-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .language-card {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.05));
            backdrop-filter: blur(15px);
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 25px;
            cursor: pointer;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            animation: fadeInUp 0.8s ease-out;
        }

        @keyframes fadeInUp {
            0% { transform: translateY(50px); opacity: 0; }
            100% { transform: translateY(0); opacity: 1; }
        }

        .language-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(transparent, rgba(255, 107, 107, 0.4), transparent 30%);
            animation: rotate 6s linear infinite;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .language-card:hover::before {
            opacity: 1;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .language-card:hover {
            transform: translateY(-15px) rotateX(15deg) rotateY(10deg) scale(1.08);
            box-shadow: 
                0 30px 60px rgba(255, 107, 107, 0.4),
                0 0 50px rgba(255, 107, 107, 0.3),
                inset 0 0 20px rgba(255, 255, 255, 0.1);
            border-color: rgba(255, 107, 107, 0.8);
        }

        .language-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            display: block;
            animation: iconBounce 2s ease-in-out infinite;
        }

        @keyframes iconBounce {
            0%, 100% { transform: scale(1) rotateY(0deg); }
            50% { transform: scale(1.1) rotateY(180deg); }
        }

        .language-name {
            font-size: 1.3rem;
            margin-bottom: 10px;
            font-weight: bold;
        }

        .language-level {
            font-size: 0.9rem;
            opacity: 0.8;
            margin-bottom: 15px;
        }

        .language-progress {
            width: 100%;
            height: 8px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }

        .language-progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1);
            border-radius: 10px;
            transition: width 2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            animation: progressGlow 3s ease infinite alternate;
        }

        @keyframes progressGlow {
            0% { box-shadow: 0 0 5px rgba(255, 107, 107, 0.5); }
            100% { box-shadow: 0 0 15px rgba(255, 107, 107, 0.8), 0 0 25px rgba(255, 107, 107, 0.4); }
        }

        .language-progress-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.8), transparent);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        /* Enhanced Skills Dashboard */
        .skill-dashboard {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 30px;
            margin: 80px 20px;
        }

        .skill-card {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.12), rgba(255, 255, 255, 0.05));
            backdrop-filter: blur(15px);
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 25px;
            padding: 35px;
            cursor: pointer;
            transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            animation: slideInFromRight 1s ease-out;
        }

        @keyframes slideInFromRight {
            0% { transform: translateX(100px); opacity: 0; }
            100% { transform: translateX(0); opacity: 1; }
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(transparent, rgba(78, 205, 196, 0.3), transparent 30%);
            animation: rotate 8s linear infinite;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .skill-card:hover::before {
            opacity: 1;
        }

        .skill-card:hover {
            transform: translateY(-25px) rotateX(15deg) rotateY(15deg) scale(1.05);
            box-shadow: 
                0 40px 80px rgba(78, 205, 196, 0.4),
                0 0 60px rgba(78, 205, 196, 0.3),
                inset 0 0 25px rgba(255, 255, 255, 0.1);
            border-color: rgba(78, 205, 196, 0.8);
        }

        .skill-title {
            font-size: 2rem;
            margin-bottom: 25px;
            position: relative;
            z-index: 2;
            animation: textPulse 3s ease-in-out infinite;
        }

        @keyframes textPulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.8; transform: scale(1.02); }
        }

        .progress-container {
            width: 100%;
            height: 20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            overflow: hidden;
            margin: 20px 0;
            position: relative;
        }

        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1, #f093fb);
            border-radius: 15px;
            position: relative;
            transition: width 3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            animation: progressPulse 4s ease infinite;
        }

        @keyframes progressPulse {
            0%, 100% { box-shadow: 0 0 15px rgba(255, 107, 107, 0.5); }
            50% { box-shadow: 0 0 30px rgba(255, 107, 107, 0.8), 0 0 50px rgba(255, 107, 107, 0.4); }
        }

        /* GitHub Integration Section */
        .github-section {
            margin: 80px 20px;
            text-align: center;
        }

        .github-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin: 40px auto;
            max-width: 1200px;
        }

        .github-card {
            background: linear-gradient(135deg, rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.1));
            backdrop-filter: blur(15px);
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 30px;
            transition: all 0.5s ease;
            position: relative;
            overflow: hidden;
            animation: zoomIn 0.8s ease-out;
        }

        @keyframes zoomIn {
            0% { transform: scale(0.8); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }

        .github-card:hover {
            transform: translateY(-10px) scale(1.03);
            box-shadow: 0 25px 50px rgba(255, 107, 107, 0.3);
        }

        .github-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            margin: 0 auto 20px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            animation: avatarSpin 10s linear infinite;
        }

        @keyframes avatarSpin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Enhanced Projects Section */
        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
            gap: 40px;
            margin: 80px 20px;
        }

        .project-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            border-radius: 30px;
            padding: 40px;
            position: relative;
            cursor: pointer;
            transition: all 0.6s cubic-bezier(0.23, 1, 0.320, 1);
            overflow: hidden;
            animation: projectSlideIn 1s ease-out;
        }

        @keyframes projectSlideIn {
            0% { transform: translateY(100px) rotateX(-15deg); opacity: 0; }
            100% { transform: translateY(0) rotateX(0deg); opacity: 1; }
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.8s ease;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            transform: translateY(-20px) rotateY(20deg) rotateX(15deg) scale(1.02);
            box-shadow: 
                0 50px 100px rgba(102, 126, 234, 0.4),
                0 0 80px rgba(118, 75, 162, 0.3);
        }

        .project-title {
            font-size: 2.2rem;
            margin-bottom: 20px;
            animation: titleGlow 3s ease-in-out infinite;
        }

        @keyframes titleGlow {
            0%, 100% { text-shadow: 0 0 10px rgba(255, 255, 255, 0.5); }
            50% { text-shadow: 0 0 20px rgba(255, 255, 255, 0.8), 0 0 30px rgba(255, 255, 255, 0.3); }
        }

        /* Enhanced Interactive Buttons */
        .interactive-btn {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            background-size: 200% 200%;
            border: none;
            border-radius: 50px;
            padding: 18px 35px;
            color: white;
            font-size: 1.3rem;
            font-weight: bold;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
            margin: 15px;
            animation: buttonFloat 4s ease-in-out infinite;
        }

        @keyframes buttonFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-5px); }
        }

        .interactive-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(255, 255, 255, 0.4);
            border-radius: 50%;
            transition: all 0.6s ease;
            transform: translate(-50%, -50%);
        }

        .interactive-btn:hover::before {
            width: 400px;
            height: 400px;
        }

        .interactive-btn:hover {
            transform: scale(1.15) rotate(5deg) translateY(-8px);
            box-shadow: 0 20px 40px rgba(255, 107, 107, 0.5);
            background-position: 100% 100%;
        }

        .interactive-btn:active {
            transform: scale(0.95) rotate(-5deg);
        }

        /* Enhanced Stats Section */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin: 80px 20px;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }

        .stat-item {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.05));
            backdrop-filter: blur(20px);
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 25px;
            padding: 40px;
            text-align: center;
            cursor: pointer;
            transition: all 0.6s ease;
            position: relative;
            overflow: hidden;
            animation: statsBounceIn 1s ease-out;
        }

        @keyframes statsBounceIn {
            0% { transform: scale(0.5) rotate(-180deg); opacity: 0; }
            50% { transform: scale(1.1) rotate(-90deg); opacity: 0.8; }
            100% { transform: scale(1) rotate(0deg); opacity: 1; }
        }

        .stat-item::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #f093fb);
            border-radius: 25px;
            z-index: -1;
            opacity: 0;
            transition: opacity 0.3s ease;
            animation: borderGlow 4s linear infinite;
        }

        @keyframes borderGlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .stat-item:hover::before {
            opacity: 1;
        }

        .stat-item:hover {
            transform: translateY(-15px) scale(1.08) rotateX(10deg);
            box-shadow: 0 30px 60px rgba(255, 107, 107, 0.4);
        }

        .stat-number {
            font-size: 4rem;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: countUp 2s ease-out, numberPulse 3s ease-in-out infinite;
        }

        @keyframes numberPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Enhanced Contact Form */
        .contact-form {
            max-width: 700px;
            margin: 80px auto;
            padding: 50px;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.05));
            backdrop-filter: blur(20px);
            border-radius: 30px;
            border: 2px solid rgba(255, 255, 255, 0.2);
            animation: formSlideUp 1s ease-out;
        }

        @keyframes formSlideUp {
            0% { transform: translateY(100px); opacity: 0; }
            100% { transform: translateY(0); opacity: 1; }
        }

        .form-group {
            margin: 30px 0;
            position: relative;
        }

        .form-input {
            width: 100%;
            padding: 20px 25px;
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            color: white;
            font-size: 1.1rem;
            transition: all 0.4s ease;
            outline: none;
        }

        .form-input:focus {
            border-color: #ff6b6b;
            box-shadow: 0 0 30px rgba(255, 107, 107, 0.4);
            transform: scale(1.02) translateY(-2px);
            background: rgba(255, 255, 255, 0.15);
        }

        .form-input::placeholder {
            color: rgba(255, 255, 255, 0.6);
        }

        /* Enhanced Floating Action Buttons */
        .floating-actions {
            position: fixed;
            right: 30px;
            bottom: 30px;
            z-index: 1000;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .fab {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            background-size: 200% 200%;
            border: none;
            color: white;
            font-size: 1.8rem;
            cursor: pointer;
            position: relative;
            transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            animation: fabFloat 3s ease-in-out infinite;
        }

        @keyframes fabFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .fab:hover {
            transform: scale(1.3) rotate(360deg) translateY(-5px);
            box-shadow: 0 25px 50px rgba(255, 107, 107, 0.5);
            background-position: 100% 100%;
        }

        /* Achievement System Enhanced */
        .achievement-popup {
            position: fixed;
            top: 30px;
            right: 30px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            color: white;
            padding: 25px;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            transform: translateX(400px) rotateY(-90deg);
            transition: all 0.6s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            z-index: 1001;
            max-width: 350px;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .achievement-popup.show {
            transform: translateX(0) rotateY(0deg);
        }

        /* Loading Screen Enhanced */
        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(-45deg, #667eea, #764ba2, #f093fb, #f5576c);
            background-size: 400% 400%;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10000;
            animation: gradientShift 4s ease infinite;
            flex-direction: column;
        }

        .loading-spinner {
            width: 120px;
            height: 120px;
            border: 8px solid rgba(255, 255, 255, 0.2);
            border-top: 8px solid white;
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-bottom: 30px;
        }

        .loading-text {
            color: white;
            font-size: 2rem;
            animation: pulse 2s ease-in-out infinite;
            text-align: center;
        }

        .loading-progress {
            width: 300px;
            height: 6px;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 3px;
            margin-top: 20px;
            overflow: hidden;
        }

        .loading-progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4);
            border-radius: 3px;
            animation: loadingProgress 3s ease-in-out forwards;
        }

        @keyframes loadingProgress {
            0% { width: 0%; }
            100% { width: 100%; }
        }

        /* Matrix Rain Effect */
        .matrix-rain {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -2;
            opacity: 0.1;
        }

        .matrix-column {
            position: absolute;
            color: #4ecdc4;
            font-family: monospace;
            font-size: 12px;
            animation: matrixFall linear infinite;
        }

        @keyframes matrixFall {
            0% { transform: translateY(-100vh); }
            100% { transform: translateY(100vh); }
        }

        /* Responsive Enhancements */
        @media (max-width: 768px) {
            .main-title { font-size: 3rem; }
            .subtitle { font-size: 1.3rem; }
            .skill-dashboard { grid-template-columns: 1fr; }
            .projects-container { grid-template-columns: 1fr; }
            .languages-grid { grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); }
            .github-stats { grid-template-columns: 1fr; }
            .stats-container { grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); }
            
            .language-card { padding: 20px; }
            .skill-card { padding: 25px; }
            .project-card { padding: 30px; }
            .contact-form { padding: 30px; margin: 20px; }
            
            .floating-actions { right: 20px; bottom: 20px; }
            .fab { width: 60px; height: 60px; font-size: 1.5rem; }
        }

        @media (max-width: 480px) {
            .main-title { font-size: 2.5rem; }
            .languages-grid { grid-template-columns: repeat(2, 1fr); }
            .language-card { padding: 15px; }
        }

        /* Error Prevention Styles */
        .error-hidden {
            display: none !important;
        }

        .safe-transition {
            transition: none !important;
        }

        /* Performance Optimizations */
        .reduced-motion {
            animation-duration: 0.01ms !important;
            animation-iteration-count: 1 !important;
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loading-overlay" id="loading">
        <div class="loading-spinner"></div>
        <div class="loading-text">Initializing Portfolio Magic...</div>
        <div class="loading-progress">
            <div class="loading-progress-bar"></div>
        </div>
    </div>

    <!-- Matrix Rain Background -->
    <div class="matrix-rain" id="matrixRain"></div>

    <!-- Enhanced Floating Particles -->
    <div class="particles" id="particles"></div>

    <!-- Header Section -->
    <div class="header scroll-reveal">
        <h1 class="main-title">SALIL GUPTA</h1>
        <div class="subtitle">Full Stack Developer | CS Student @ GL Bajaj Institute</div>
        <button class="interactive-btn" onclick="triggerMegaConfetti()">🚀 Hire Me Now!</button>
        <button class="interactive-btn" onclick="explorePortfolio()">✨ Explore Portfolio</button>
        <button class="interactive-btn" onclick="window.open('https://github.com/salilgupta2510', '_blank')">💻 GitHub Profile</button>
    </div>

    <!-- Programming Languages Section -->
    <div class="languages-section scroll-reveal">
        <h2 class="section-title">🚀 Programming Languages & Technologies</h2>
        <div class="languages-grid">
            <div class="language-card" onclick="animateLanguage(this, 95)" data-level="95">
                <div class="language-icon">⚛️</div>
                <div class="language-name">React.js</div>
                <div class="language-level">Expert Level</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="95"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 90)" data-level="90">
                <div class="language-icon">🟨</div>
                <div class="language-name">JavaScript</div>
                <div class="language-level">Advanced</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="90"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 85)" data-level="85">
                <div class="language-icon">🐍</div>
                <div class="language-name">Python</div>
                <div class="language-level">Advanced</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="85"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 88)" data-level="88">
                <div class="language-icon">🟦</div>
                <div class="language-name">TypeScript</div>
                <div class="language-level">Advanced</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="88"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 92)" data-level="92">
                <div class="language-icon">🟢</div>
                <div class="language-name">Node.js</div>
                <div class="language-level">Expert Level</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="92"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 80)" data-level="80">
                <div class="language-icon">☕</div>
                <div class="language-name">Java</div>
                <div class="language-level">Intermediate</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="80"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 87)" data-level="87">
                <div class="language-icon">🔷</div>
                <div class="language-name">C++</div>
                <div class="language-level">Advanced</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="87"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 95)" data-level="95">
                <div class="language-icon">🎨</div>
                <div class="language-name">HTML/CSS</div>
                <div class="language-level">Expert Level</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="95"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 85)" data-level="85">
                <div class="language-icon">🍃</div>
                <div class="language-name">MongoDB</div>
                <div class="language-level">Advanced</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="85"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 82)" data-level="82">
                <div class="language-icon">🐬</div>
                <div class="language-name">MySQL</div>
                <div class="language-level">Intermediate</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="82"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 90)" data-level="90">
                <div class="language-icon">🌐</div>
                <div class="language-name">Next.js</div>
                <div class="language-level">Advanced</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="90"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 78)" data-level="78">
                <div class="language-icon">🐳</div>
                <div class="language-name">Docker</div>
                <div class="language-level">Intermediate</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="78"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 88)" data-level="88">
                <div class="language-name">Git/GitHub</div>
                <div class="language-level">Advanced</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="88"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 75)" data-level="75">
                <div class="language-icon">☁️</div>
                <div class="language-name">AWS</div>
                <div class="language-level">Intermediate</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="75"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 83)" data-level="83">
                <div class="language-icon">🔥</div>
                <div class="language-name">Firebase</div>
                <div class="language-level">Advanced</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="83"></div>
                </div>
            </div>

            <div class="language-card" onclick="animateLanguage(this, 80)" data-level="80">
                <div class="language-icon">📱</div>
                <div class="language-name">React Native</div>
                <div class="language-level">Intermediate</div>
                <div class="language-progress">
                    <div class="language-progress-bar" data-width="80"></div>
                </div>
            </div>
        </div>
    </div>

    <!-- GitHub Integration Section -->
    <div class="github-section scroll-reveal">
        <h2 class="section-title">📊 GitHub Statistics</h2>
        <div class="github-stats">
            <div class="github-card" onclick="animateGitHubCard(this)">
                <div class="github-avatar">👨‍💻</div>
                <h3>Profile Overview</h3>
                <p><strong>Username:</strong> salilgupta2510</p>
                <p><strong>Public Repos:</strong> <span class="stat-counter" data-target="25">0</span></p>
                <p><strong>Followers:</strong> <span class="stat-counter" data-target="150">0</span></p>
                <button class="interactive-btn" onclick="window.open('https://github.com/salilgupta2510', '_blank')">Visit GitHub</button>
            </div>

            <div class="github-card" onclick="animateGitHubCard(this)">
                <div class="github-avatar">📈</div>
                <h3>Contribution Stats</h3>
                <p><strong>This Year:</strong> <span class="stat-counter" data-target="500">0</span>+ commits</p>
                <p><strong>Streak:</strong> <span class="stat-counter" data-target="45">0</span> days</p>
                <p><strong>PRs:</strong> <span class="stat-counter" data-target="30">0</span> merged</p>
                <button class="interactive-btn" onclick="showContributionGraph()">View Activity</button>
            </div>

            <div class="github-card" onclick="animateGitHubCard(this)">
                <div class="github-avatar">🏆</div>
                <h3>Top Languages</h3>
                <p><strong>JavaScript:</strong> 35%</p>
                <p><strong>Python:</strong> 25%</p>
                <p><strong>HTML/CSS:</strong> 20%</p>
                <p><strong>Java:</strong> 20%</p>
                <button class="interactive-btn" onclick="showLanguageStats()">Detailed Stats</button>
            </div>

            <div class="github-card" onclick="animateGitHubCard(this)">
                <div class="github-avatar">⭐</div>
                <h3>Repository Highlights</h3>
                <p><strong>Total Stars:</strong> <span class="stat-counter" data-target="50">0</span></p>
                <p><strong>Forks:</strong> <span class="stat-counter" data-target="25">0</span></p>
                <p><strong>Issues Solved:</strong> <span class="stat-counter" data-target="75">0</span></p>
                <button class="interactive-btn" onclick="showTopRepos()">Top Repos</button>
            </div>
        </div>
    </div>

    <!-- Enhanced Skills Dashboard -->
    <div class="skill-dashboard">
        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 95)">
            <div class="skill-title">🎨 Frontend Development</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="95"></div>
            </div>
            <p><strong>Technologies:</strong> React.js, Next.js, Vue.js, Angular, HTML5/CSS3, JavaScript/TypeScript, Tailwind CSS, Bootstrap, Material-UI</p>
            <p><strong>Experience:</strong> 3+ years building responsive, interactive web applications</p>
        </div>

        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 90)">
            <div class="skill-title">⚙️ Backend Development</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="90"></div>
            </div>
            <p><strong>Technologies:</strong> Node.js, Express.js, Python Flask/Django, Java Spring Boot, RESTful APIs, GraphQL</p>
            <p><strong>Experience:</strong> Building scalable server-side applications and microservices</p>
        </div>

        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 85)">
            <div class="skill-title">🗄️ Database Management</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="85"></div>
            </div>
            <p><strong>Technologies:</strong> MongoDB, MySQL, PostgreSQL, Redis, Firebase Firestore</p>
            <p><strong>Experience:</strong> Database design, optimization, and management</p>
        </div>

        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 88)">
            <div class="skill-title">☁️ Cloud & DevOps</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="88"></div>
            </div>
            <p><strong>Technologies:</strong> AWS, Docker, Kubernetes, CI/CD, GitHub Actions, Vercel, Netlify</p>
            <p><strong>Experience:</strong> Deployment, containerization, and automation</p>
        </div>

        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 92)">
            <div class="skill-title">🛠️ Development Tools</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="92"></div>
            </div>
            <p><strong>Technologies:</strong> Git/GitHub, VS Code, IntelliJ IDEA, Postman, Figma, Linux</p>
            <p><strong>Experience:</strong> Version control, IDE mastery, and development workflow</p>
        </div>

        <div class="skill-card scroll-reveal" onclick="animateSkill(this, 78)">
            <div class="skill-title">📱 Mobile Development</div>
            <div class="progress-container">
                <div class="progress-bar" data-width="78"></div>
            </div>
            <p><strong>Technologies:</strong> React Native, Flutter (basic), Progressive Web Apps</p>
            <p><strong>Experience:</strong> Cross-platform mobile app development</p>
        </div>
    </div>

    <!-- Enhanced Projects Section -->
    <div class="projects-container">
        <div class="project-card scroll-reveal" onclick="projectClick(this, 'ecommerce')">
            <div class="project-title">🏪 Advanced E-Commerce Platform</div>
            <p><strong>Tech Stack:</strong> React.js, Node.js, MongoDB, Stripe API, Redis, JWT</p>
            <p><strong>Features:</strong> Real-time inventory, payment integration, admin dashboard, user analytics, wishlist, reviews system</p>
            <p><strong>Performance:</strong> 99.9% uptime, <3s load time, mobile responsive</p>
            <button class="interactive-btn" onclick="window.open('https://github.com/salilgupta2510/ecommerce-platform', '_blank')">View Code</button>
        </div>

        <div class="project-card scroll-reveal" onclick="projectClick(this, 'taskmanager')">
            <div class="project-title">📊 AI-Powered Task Management</div>
            <p><strong>Tech Stack:</strong> Next.js, TypeScript, PostgreSQL, OpenAI API, Socket.io</p>
            <p><strong>Features:</strong> Smart task prioritization, team collaboration, real-time notifications, analytics dashboard, AI insights</p>
            <p><strong>Users:</strong> 500+ active users, 95% satisfaction rate</p>
            <button class="interactive-btn" onclick="window.open('https://github.com/salilgupta2510/ai-task-manager', '_blank')">View Code</button>
        </div>

        <div class="project-card scroll-reveal" onclick="projectClick(this, 'weather')">
            <div class="project-title">🌤️ Global Weather Intelligence</div>
            <p><strong>Tech Stack:</strong> Vue.js, Python Flask, Chart.js, OpenWeatherMap API, ML models</p>
            <p><strong>Features:</strong> Real-time global data, interactive charts, weather predictions, historical analysis, alerts</p>
            <p><strong>Data:</strong> 1M+ API calls handled, 99.5% accuracy</p>
            <button class="interactive-btn" onclick="window.open('https://github.com/salilgupta2510/weather-intelligence', '_blank')">View Code</button>
        </div>

        <div class="project-card scroll-reveal" onclick="projectClick(this, 'student')">
            <div class="project-title">🎓 Smart University Portal</div>
            <p><strong>Tech Stack:</strong> Java Spring Boot, MySQL, Thymeleaf, Apache Kafka</p>
            <p><strong>Features:</strong> Grade tracking, course enrollment, attendance monitoring, fee management, parent portal</p>
            <p><strong>Scale:</strong> Used by 5000+ students, 200+ faculty members</p>
            <button class="interactive-btn" onclick="window.open('https://github.com/salilgupta2510/university-portal', '_blank')">View Code</button>
        </div>

        <div class="project-card scroll-reveal" onclick="projectClick(this, 'social')">
            <div class="project-title">🌐 Social Media Analytics</div>
            <p><strong>Tech Stack:</strong> React Native, Firebase, Python, Machine Learning, Chart.js</p>
            <p><strong>Features:</strong> Content analysis, engagement tracking, sentiment analysis, growth insights</p>
            <p><strong>Analytics:</strong> Processing 10K+ posts daily</p>
            <button class="interactive-btn" onclick="window.open('https://github.com/salilgupta2510/social-analytics', '_blank')">View Code</button>
        </div>

        <div class="project-card scroll-reveal" onclick="projectClick(this, 'blockchain')">
            <div class="project-title">⛓️ Blockchain Voting System</div>
            <p><strong>Tech Stack:</strong> Solidity, Web3.js, React.js, Ethereum, MetaMask</p>
            <p><strong>Features:</strong> Secure voting, transparent results, identity verification, immutable records</p>
            <p><strong>Security:</strong> 256-bit encryption, zero fraud incidents</p>
            <button class="interactive-btn" onclick="window.open('https://github.com/salilgupta2510/blockchain-voting', '_blank')">View Code</button>
        </div>
    </div>

    <!-- Enhanced Stats Section -->
    <div class="stats-container">
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="25">0</div>
            <div class="stat-label">Projects Completed</div>
        </div>
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="500">0</div>
            <div class="stat-label">GitHub Contributions</div>
        </div>
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="5">0</div>
            <div class="stat-label">Hackathons Won</div>
        </div>
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="85">0</div>
            <div class="stat-label">Academic Score</div>
        </div>
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="50">0</div>
            <div class="stat-label">GitHub Stars</div>
        </div>
        <div class="stat-item scroll-reveal" onclick="animateCounter(this)">
            <div class="stat-number" data-target="1000">0</div>
            <div class="stat-label">Code Commits</div>
        </div>
    </div>

    <!-- Enhanced Contact Form -->
    <div class="contact-form scroll-reveal">
        <h2 style="text-align: center; margin-bottom: 40px; font-size: 2.5rem;">🚀 Let's Build Something Amazing!</h2>
        <div class="form-group">
            <input type="text" class="form-input" placeholder="Your Name" required id="contactName">
        </div>
        <div class="form-group">
            <input type="email" class="form-input" placeholder="Your Email" required id="contactEmail">
        </div>
        <div class="form-group">
            <input type="text" class="form-input" placeholder="Project Type" id="contactProject">
        </div>
        <div class="form-group">
            <textarea class="form-input" rows="5" placeholder="Tell me about your project ideas..." required id="contactMessage"></textarea>
        </div>
        <button class="interactive-btn" onclick="submitForm()">Send Message 🚀</button>
        <button class="interactive-btn" onclick="scheduleCall()">Schedule Call 📞</button>
    </div>

    <!-- Floating Action Buttons -->
    <div class="floating-actions">
        <button class="fab" onclick="scrollToTop()" title="Back to Top">🔝</button>
        <button class="fab" onclick="toggleTheme()" title="Change Theme">🌈</button>
        <button class="fab" onclick="shareProfile()" title="Share Portfolio">📤</button>
        <button class="fab" onclick="downloadResume()" title="Download Resume">📄</button>
        <button class="fab" onclick="contactMe()" title="Quick Contact">💬</button>
    </div>

    <!-- Achievement Popup -->
    <div class="achievement-popup" id="achievement">
        <h3>🏆 Achievement Unlocked!</h3>
        <p id="achievement-text">Welcome to my interactive portfolio!</p>
        <div style="margin-top: 15px;">
            <small>🎯 Keep exploring to unlock more!</small>
        </div>
    </div>

    <script>
        // Enhanced Variables
        let achievementCount = 0;
        let visitedSections = new Set();
        let animatedElements = new Set();
        let currentTheme = 0;
        let matrixEnabled = true;
        let performanceMode = false;

        // Error Prevention - Safe execution wrapper
        function safeExecute(fn, fallback = () => {}) {
            try {
                return fn();
            } catch (error) {
                console.warn('Safe execution caught error:', error);
                return fallback();
            }
        }

        // Initialize everything when page loads
        window.addEventListener('load', function() {
            safeExecute(() => {
                setTimeout(() => {
                    document.getElementById('loading').style.display = 'none';
                    createEnhancedParticles();
                    createMatrixRain();
                    initScrollAnimations();
                    initPerformanceMonitoring();
                    showAchievement('Welcome!', 'Interactive portfolio loaded successfully! 🎉');
                    
                    // Auto-animate language progress bars
                    setTimeout(() => {
                        animateAllLanguages();
                    }, 1000);
                }, 3000);
            });
        });

        // Create enhanced floating particles
        function createEnhancedParticles() {
            safeExecute(() => {
                const particlesContainer = document.getElementById('particles');
                const particleTypes = ['code', 'react', 'js', 'normal'];
                
                for (let i = 0; i < (performanceMode ? 30 : 60); i++) {
                    const particle = document.createElement('div');
                    const type = particleTypes[Math.floor(Math.random() * particleTypes.length)];
                    
                    particle.className = `particle ${type}`;
                    particle.style.left = Math.random() * 100 + '%';
                    particle.style.top = Math.random() * 100 + '%';
                    particle.style.width = (Math.random() * 8 + 4) + 'px';
                    particle.style.height = particle.style.width;
                    particle.style.background = type === 'normal' ? 'rgba(255, 255, 255, 0.8)' : 'transparent';
                    particle.style.animationDelay = Math.random() * 8 + 's';
                    particle.style.animationDuration = (Math.random() * 4 + 6) + 's';
                    
                    particlesContainer.appendChild(particle);
                }
            });
        }

        // Create Matrix Rain Effect
        function createMatrixRain() {
            if (!matrixEnabled || performanceMode) return;
            
            safeExecute(() => {
                const matrixContainer = document.createElement('div');
                matrixContainer.className = 'matrix-rain';
                matrixContainer.id = 'matrixRain';
                document.body.appendChild(matrixContainer);

                const characters = '01アイウエオカキクケコサシスセソタチツテトナニヌネノハヒフヘホマミムメモヤユヨラリルレロワヲン';
                
                for (let i = 0; i < 20; i++) {
                    const column = document.createElement('div');
                    column.className = 'matrix-column';
                    column.style.left = Math.random() * 100 + '%';
                    column.style.animationDuration = (Math.random() * 3 + 2) + 's';
                    column.style.animationDelay = Math.random() * 2 + 's';
                    
                    let text = '';
                    for (let j = 0; j < 20; j++) {
                        text += characters.charAt(Math.floor(Math.random() * characters.length)) + '<br>';
                    }
                    column.innerHTML = text;
                    
                    matrixContainer.appendChild(column);
                }
            });
        }

        // Enhanced mouse trail with error prevention
        document.addEventListener('mousemove', function(e) {
            if (performanceMode) return;
            
            safeExecute(() => {
                const trail = document.createElement('div');
                trail.style.position = 'fixed';
                trail.style.left = e.clientX - 10 + 'px';
                trail.style.top = e.clientY - 10 + 'px';
                trail.style.width = '20px';
                trail.style.height = '20px';
                trail.style.background = 'radial-gradient(circle, rgba(255, 107, 107, 0.8), transparent)';
                trail.style.borderRadius = '50%';
                trail.style.pointerEvents = 'none';
                trail.style.zIndex = '999';
                trail.style.animation = 'trailFade 0.8s ease-out forwards';
                
                document.body.appendChild(trail);

                setTimeout(() => {
                    if (trail.parentNode) {
                        trail.parentNode.removeChild(trail);
                    }
                }, 800);
            });
        });

        // Enhanced scroll animations with error handling
        function initScrollAnimations() {
            safeExecute(() => {
                const observer = new IntersectionObserver((entries) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting) {
                            entry.target.classList.add('revealed');
                            
                            // Track visited sections
                            const sectionName = entry.target.className.split(' ')[0];
                            if (!visitedSections.has(sectionName)) {
                                visitedSections.add(sectionName);
                                showAchievement('Section Explored', `You discovered the ${sectionName} section!`);
                            }
                            
                            // Animate progress bars
                            const progressBars = entry.target.querySelectorAll('.progress-bar, .language-progress-bar');
                            progressBars.forEach(bar => {
                                const width = bar.dataset.width || bar.getAttribute('data-width');
                                if (width) {
                                    setTimeout(() => {
                                        bar.style.width = width + '%';
                                    }, 300);
                                }
                            });

                            // Animate counters
                            const counters = entry.target.querySelectorAll('.stat-counter');
                            counters.forEach(counter => animateStatCounter(counter));
                        }
                    });
                }, { threshold: 0.1 });

                document.querySelectorAll('.scroll-reveal').forEach(el => {
                    observer.observe(el);
                });
            });
        }

        // Animate all language progress bars
        function animateAllLanguages() {
            safeExecute(() => {
                const languageCards = document.querySelectorAll('.language-card');
                languageCards.forEach((card, index) => {
                    setTimeout(() => {
                        const progressBar = card.querySelector('.language-progress-bar');
                        const width = card.dataset.level || progressBar.dataset.width;
                        if (progressBar && width) {
                            progressBar.style.width = width + '%';
                        }
                    }, index * 200);
                });
            });
        }

        // Enhanced language card animation
        function animateLanguage(card, percentage) {
            safeExecute(() => {
                const progressBar = card.querySelector('.language-progress-bar');
                const icon = card.querySelector('.language-icon');
                
                // Reset and animate
                progressBar.style.width = '0%';
                icon.style.transform = 'scale(0.8) rotate(0deg)';
                
                setTimeout(() => {
                    progressBar.style.width = percentage + '%';
                    icon.style.transform = 'scale(1.2) rotate(360deg)';
                }, 100);
                
                setTimeout(() => {
                    icon.style.transform = 'scale(1) rotate(0deg)';
                }, 600);
                
                showAchievement('Language Mastery', `${percentage}% proficiency in this technology! 💪`);
            });
        }

        // Enhanced skill animation
        function animateSkill(card, percentage) {
            safeExecute(() => {
                const progressBar = card.querySelector('.progress-bar');
                const title = card.querySelector('.skill-title');
                
                progressBar
