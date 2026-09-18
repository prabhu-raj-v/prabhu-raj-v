<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Prabhu Raj V | Resume</title>
  <!-- Google Fonts & FontAwesome -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&family=Rajdhani:wght@500;600;700&family=Share+Tech+Mono&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"/>

  <style>
    :root {
      --neon-cyan: #00f0ff;
      --neon-pink: #ff0055;
      --neon-yellow: #fcee0a;
      --neon-purple: #b026ff;
      --bg-dark: #05050c;
      --panel-bg: rgba(10, 14, 26, 0.82);
      --card-border: rgba(0, 240, 255, 0.35);
      --text-main: #e2f1f8;
      --text-muted: #8fa3b7;
      --glow-cyan: 0 0 12px rgba(0, 240, 255, 0.5), 0 0 24px rgba(0, 240, 255, 0.2);
      --glow-pink: 0 0 12px rgba(ff, 0, 85, 0.6);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: var(--bg-dark);
      color: var(--text-main);
      font-family: 'Rajdhani', sans-serif;
      overflow-x: hidden;
      min-height: 100vh;
      position: relative;
    }

    /* Cyberpunk CRT Scanline Effect */
    body::before {
      content: " ";
      display: block;
      position: fixed;
      top: 0; left: 0; bottom: 0; right: 0;
      background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.35) 50%),
                  linear-gradient(90deg, rgba(255, 0, 0, 0.03), rgba(0, 255, 0, 0.01), rgba(0, 0, 255, 0.03));
      z-index: 99;
      background-size: 100% 3px, 3px 100%;
      pointer-events: none;
      opacity: 0.65;
    }

    /* 3D Cyberpunk Canvas */
    #bg-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      z-index: -1;
    }

    /* Container */
    .container {
      max-width: 1050px;
      margin: 0 auto;
      padding: 40px 20px 130px 20px;
      position: relative;
      z-index: 10;
    }

    /* Header Section */
    header {
      background: var(--panel-bg);
      backdrop-filter: blur(10px);
      padding: 45px 35px;
      border: 1px solid var(--neon-cyan);
      box-shadow: var(--glow-cyan), inset 0 0 15px rgba(0, 240, 255, 0.1);
      margin-bottom: 30px;
      text-align: center;
      position: relative;
      clip-path: polygon(0 0, calc(100% - 30px) 0, 100% 30px, 100% 100%, 30px 100%, 0 calc(100% - 30px));
      animation: glitchEntry 0.9s cubic-bezier(0.2, 1, 0.3, 1);
    }

    /* Cyber Corner accents */
    header::after {
      /* content: 'SYSTEM_STATUS // ONLINE'; */
      font-family: 'Share Tech Mono', monospace;
      position: absolute;
      top: 6px;
      right: 40px;
      font-size: 0.7rem;
      color: var(--neon-yellow);
      letter-spacing: 2px;
      text-shadow: 0 0 8px var(--neon-yellow);
    }

    header h1 {
      font-family: 'Orbitron', sans-serif;
      font-size: 2.8rem;
      font-weight: 900;
      color: #fff;
      letter-spacing: 3px;
      text-transform: uppercase;
      text-shadow: 0 0 10px var(--neon-cyan), 0 0 20px var(--neon-cyan);
      margin-bottom: 6px;
      position: relative;
      display: inline-block;
    }

    header h2 {
      font-family: 'Share Tech Mono', monospace;
      font-size: 1.25rem;
      color: var(--neon-pink);
      text-shadow: 0 0 8px var(--neon-pink);
      letter-spacing: 2px;
      margin-bottom: 24px;
      text-transform: uppercase;
    }

    .contact-info {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      font-family: 'Share Tech Mono', monospace;
      font-size: 0.95rem;
    }

    .contact-info a, .contact-info span {
      color: var(--text-muted);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 8px;
      background: rgba(0, 0, 0, 0.6);
      padding: 6px 14px;
      border: 1px solid rgba(0, 240, 255, 0.25);
      border-radius: 2px;
      transition: all 0.3s ease;
    }

    .contact-info a:hover {
      color: #fff;
      border-color: var(--neon-cyan);
      box-shadow: 0 0 10px rgba(0, 240, 255, 0.6);
      transform: translateY(-2px);
    }

    .contact-info i {
      color: var(--neon-cyan);
    }

    /* Layout Sections */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 26px;
      margin-bottom: 26px;
    }

    .card {
      background: var(--panel-bg);
      backdrop-filter: blur(12px);
      border: 1px solid var(--card-border);
      padding: 30px;
      position: relative;
      clip-path: polygon(0 0, calc(100% - 18px) 0, 100% 18px, 100% 100%, 18px 100%, 0 calc(100% - 18px));
      transition: all 0.35s ease;
      box-shadow: inset 0 0 15px rgba(0, 240, 255, 0.05);
    }

    .card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 4px;
      height: 100%;
      background: var(--neon-cyan);
      box-shadow: 0 0 8px var(--neon-cyan);
    }

    .card:hover {
      border-color: var(--neon-pink);
      box-shadow: 0 0 20px rgba(255, 0, 85, 0.35), inset 0 0 15px rgba(255, 0, 85, 0.1);
      transform: translateY(-4px) scale(1.01);
    }

    .card:hover::before {
      background: var(--neon-pink);
      box-shadow: 0 0 10px var(--neon-pink);
    }

    .card h3 {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.25rem;
      font-weight: 700;
      margin-bottom: 20px;
      color: #fff;
      display: flex;
      align-items: center;
      gap: 12px;
      border-bottom: 1px dashed rgba(0, 240, 255, 0.3);
      padding-bottom: 12px;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .card h3 i {
      color: var(--neon-cyan);
      text-shadow: 0 0 8px var(--neon-cyan);
    }

    .card p, .card ul {
      color: var(--text-muted);
      font-size: 1.05rem;
      line-height: 1.7;
    }

    /* Skills Badges */
    .skills-group {
      margin-bottom: 20px;
    }

    .skills-group:last-child {
      margin-bottom: 0;
    }

    .skills-group h4 {
      font-family: 'Share Tech Mono', monospace;
      color: var(--neon-yellow);
      margin-bottom: 10px;
      font-size: 0.95rem;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .tag {
      background: rgba(0, 0, 0, 0.7);
      color: var(--neon-cyan);
      border: 1px solid rgba(0, 240, 255, 0.4);
      padding: 5px 12px;
      font-family: 'Share Tech Mono', monospace;
      font-size: 0.88rem;
      font-weight: 600;
      letter-spacing: 0.5px;
      clip-path: polygon(0 0, calc(100% - 6px) 0, 100% 6px, 100% 100%, 6px 100%, 0 calc(100% - 6px));
      transition: all 0.25s ease;
    }

    .tag:hover {
      background: var(--neon-cyan);
      color: #000;
      border-color: var(--neon-cyan);
      box-shadow: 0 0 12px var(--neon-cyan);
      transform: scale(1.06);
    }

    /* Timeline Items */
    .timeline-item {
      margin-bottom: 24px;
      position: relative;
      padding-left: 24px;
      border-left: 2px solid rgba(0, 240, 255, 0.3);
    }

    .timeline-item::before {
      content: '';
      position: absolute;
      left: -6px;
      top: 6px;
      width: 10px;
      height: 10px;
      background: var(--neon-pink);
      box-shadow: 0 0 8px var(--neon-pink);
      transform: rotate(45deg);
    }

    .timeline-item:last-child {
      margin-bottom: 0;
    }

    .timeline-title {
      font-family: 'Orbitron', sans-serif;
      font-weight: 700;
      color: #fff;
      font-size: 1.1rem;
      margin-bottom: 4px;
      letter-spacing: 0.5px;
    }

    .timeline-subtitle {
      font-size: 1rem;
      color: var(--neon-cyan);
      font-weight: 600;
      margin-bottom: 4px;
    }

    .timeline-date {
      font-family: 'Share Tech Mono', monospace;
      font-size: 0.85rem;
      color: var(--neon-yellow);
      margin-bottom: 12px;
      display: inline-block;
      background: rgba(252, 238, 10, 0.08);
      border: 1px solid rgba(252, 238, 10, 0.3);
      padding: 2px 8px;
    }

    .timeline-item ul {
      list-style-type: none;
      padding-left: 0;
    }

    .timeline-item ul li {
      position: relative;
      padding-left: 18px;
      margin-bottom: 8px;
    }

    .timeline-item ul li::before {
      content: '>';
      font-family: 'Share Tech Mono', monospace;
      position: absolute;
      left: 0;
      color: var(--neon-pink);
      font-weight: bold;
    }

    /* Sticky Bottom Download Button */
    .download-bar {
      position: fixed;
      bottom: 30px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 1000;
    }

    .download-btn {
      display: flex;
      align-items: center;
      gap: 12px;
      background: #000;
      color: var(--neon-cyan);
      padding: 14px 32px;
      font-family: 'Orbitron', sans-serif;
      font-weight: 700;
      font-size: 0.95rem;
      letter-spacing: 1.5px;
      text-decoration: none;
      text-transform: uppercase;
      border: 2px solid var(--neon-cyan);
      box-shadow: var(--glow-cyan);
      clip-path: polygon(15px 0, 100% 0, 100% calc(100% - 15px), calc(100% - 15px) 100%, 0 100%, 0 15px);
      transition: all 0.3s ease;
    }

    .download-btn:hover {
      background: var(--neon-cyan);
      color: #000;
      box-shadow: 0 0 25px var(--neon-cyan), 0 0 45px rgba(0, 240, 255, 0.5);
      transform: translateY(-3px) scale(1.02);
    }

    @keyframes glitchEntry {
      0% { opacity: 0; transform: translateY(-15px); filter: hue-rotate(90deg); }
      50% { opacity: 0.7; transform: translateY(5px); }
      100% { opacity: 1; transform: translateY(0); filter: hue-rotate(0deg); }
    }

    @media (max-width: 768px) {
      header { padding: 32px 18px; }
      header h1 { font-size: 1.9rem; }
      .grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

  <!-- Subtle 3D Canvas Background -->
  <canvas id="bg-canvas"></canvas>

  <div class="container">
    
    <!-- Header / Intro -->
    <header>
      <h1>PRABHU RAJ V</h1>
      <h2>Computer Science Engineer</h2>
      <div class="contact-info">
        <span><i class="fa-solid fa-location-dot"></i> Vadalur, Cuddalore 607303</span>
        <a href="mailto:v.prabhuraj.in@gmail.com"><i class="fa-solid fa-envelope"></i> v.prabhuraj.in@gmail.com</a>
        <a href="tel:6381358794"><i class="fa-solid fa-phone"></i> 6381358794</a>
        <a href="https://linkedin.com/in/prabhu-raj-v" target="_blank"><i class="fa-brands fa-linkedin"></i> linkedin.com/in/prabhu-raj-v</a>
      </div>
    </header>

    <!-- Objective Card -->
    <div class="card" style="margin-bottom: 24px;">
      <h3><i class="fa-solid fa-bullseye"></i> Career Objective</h3>
      <p>Passionate web developer with a strong focus on leveraging technology to drive business outcomes. Proven ability to communicate effectively and collaborate with cross-functional teams on engineering projects. Skilled in translating complex technical concepts into actionable insights for stakeholders.</p>
    </div>

    <!-- Main Grid -->
    <div class="grid">
      
      <!-- Experience & Projects -->
      <div class="card">
        <h3><i class="fa-solid fa-briefcase"></i> Experience & Projects</h3>
        
        <div class="timeline-item">
          <div class="timeline-title">Web Developer - Internship</div>
          <div class="timeline-subtitle">Exposys Data Labs</div>
          <div class="timeline-date">2023</div>
          <ul>
            <li><strong>Portfolio:</strong> Built professional websites showcasing individual or organizational work, skills, and achievements.</li>
            <li><strong>E-commerce Product Page:</strong> Designed responsive layouts and developed features for product display.</li>
            <li><strong>Mass Mail Dispatcher:</strong> Developed web-based applications facilitating the distribution of large email volumes to target audiences.</li>
          </ul>
        </div>

        <div class="timeline-item">
          <div class="timeline-title">Driver Drowsiness Detection & Traffic Sign Recognition using AI</div>
          <div class="timeline-subtitle">Academic Project</div>
          <p style="margin-top: 8px;">Designed an AI-based system detecting driver fatigue and recognizing traffic signs in real-time to enhance road safety. Implemented live alerts using computer vision and deployed the solution on Raspberry Pi for embedded use.</p>
        </div>
      </div>

      <!-- Skills -->
      <div class="card">
        <h3><i class="fa-solid fa-code"></i> Technical & Soft Skills</h3>
        
        <div class="skills-group">
          <h4>Programming Languages</h4>
          <div class="tags">
            <span class="tag">Java</span>
            <span class="tag">JavaScript</span>
            <span class="tag">Python</span>
          </div>
        </div>

        <div class="skills-group">
          <h4>Frontend & Backend</h4>
          <div class="tags">
            <span class="tag">HTML</span>
            <span class="tag">CSS</span>
            <span class="tag">React.js</span>
            <span class="tag">Node.js</span>
          </div>
        </div>

        <div class="skills-group">
          <h4>Databases</h4>
          <div class="tags">
            <span class="tag">SQL</span>
          </div>
        </div>

        <div class="skills-group">
          <h4>Soft Skills</h4>
          <div class="tags">
            <span class="tag">Verbal & Written Communication</span>
            <span class="tag">Time Management</span>
            <span class="tag">Problem Solving</span>
          </div>
        </div>

        <div class="skills-group">
          <h4>Languages Known</h4>
          <div class="tags">
            <span class="tag">English</span>
            <span class="tag">Tamil</span>
          </div>
        </div>
      </div>

    </div>

    <!-- Education & Certifications Grid -->
    <div class="grid">
      
      <!-- Education -->
      <div class="card">
        <h3><i class="fa-solid fa-graduation-cap"></i> Education</h3>
        
        <div class="timeline-item">
          <div class="timeline-title">B.Tech - Computer Science Engineering</div>
          <div class="timeline-subtitle">Achariya College of Engineering Technology, Pondicherry</div>
          <div class="timeline-date">2021 - 2025</div>
          <p>CGPA: 7.19</p>
        </div>

        <div class="timeline-item">
          <div class="timeline-title">Higher Secondary Certificate</div>
          <div class="timeline-subtitle">Jawahar Matriculation Higher Secondary School, Neyveli</div>
          <div class="timeline-date">2020 - 2021</div>
          <p>Percentage: 70.9%</p>
        </div>

        <div class="timeline-item">
          <div class="timeline-title">Secondary School Leaving Certificate</div>
          <div class="timeline-subtitle">Jawahar Matriculation Higher Secondary School, Neyveli</div>
          <div class="timeline-date">2018 - 2019</div>
          <p>Percentage: 60.6%</p>
        </div>
      </div>

      <!-- Certifications -->
      <div class="card">
        <h3><i class="fa-solid fa-certificate"></i> Certifications</h3>
        
        <div class="timeline-item">
          <div class="timeline-title">NPTEL</div>
          <ul>
            <li>Introduction to Operating System</li>
            <li>Programming in Java</li>
          </ul>
        </div>

        <div class="timeline-item">
          <div class="timeline-title">EDUSKILL</div>
          <ul>
            <li>AI and Machine Learning</li>
          </ul>
        </div>
      </div>

    </div>

  </div>

  <!-- Download Resume Button -->
  <div class="download-bar">
    <a href="https://drive.google.com/file/d/1xooyKSx0UHTmgcdGH3tqDYZnG8zRuGVv/view" target="_blank" class="download-btn">
      <i class="fa-solid fa-download"></i> Download Resume
    </a>
  </div>

  <!-- Three.js Library -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

  <script>
    // --- Cyberpunk 3D Holographic Perspective Grid ---
    const canvas = document.getElementById('bg-canvas');
    const scene = new THREE.Scene();
    scene.fog = new THREE.FogExp2(0x05050c, 0.0022);

    const camera = new THREE.PerspectiveCamera(65, window.innerWidth / window.innerHeight, 1, 1000);
    camera.position.set(0, 45, 180);
    camera.rotation.x = -0.2;

    const renderer = new THREE.WebGLRenderer({ canvas: canvas, antialias: true, alpha: true });
    renderer.setSize(window.innerWidth, window.innerHeight);
    renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

    // Cyberpunk Terrain Grid
    const gridWidth = 400;
    const gridDepth = 400;
    const segments = 45;

    const gridGeo = new THREE.PlaneGeometry(gridWidth, gridDepth, segments, segments);
    gridGeo.rotateX(-Math.PI / 2);

    const pos = gridGeo.attributes.position;
    const origY = new Float32Array(pos.count);
    for (let i = 0; i < pos.count; i++) {
      origY[i] = 0;
    }

    // Grid Material with Cyan Neon Lines
    const gridMat = new THREE.MeshBasicMaterial({
      color: 0x00f0ff,
      wireframe: true,
      transparent: true,
      opacity: 0.22
    });

    const gridMesh = new THREE.Mesh(gridGeo, gridMat);
    scene.add(gridMesh);

    // Dynamic Floating Neon Cyber Particles
    const starCount = 350;
    const starGeo = new THREE.BufferGeometry();
    const starCoords = new Float32Array(starCount * 3);

    for (let i = 0; i < starCount * 3; i += 3) {
      starCoords[i] = (Math.random() - 0.5) * 600;
      starCoords[i + 1] = Math.random() * 200 - 20;
      starCoords[i + 2] = (Math.random() - 0.5) * 600;
    }

    starGeo.setAttribute('position', new THREE.BufferAttribute(starCoords, 3));
    const starMat = new THREE.PointsMaterial({
      color: 0xff0055,
      size: 2.2,
      transparent: true,
      opacity: 0.7
    });

    const stars = new THREE.Points(starGeo, starMat);
    scene.add(stars);

    // Mouse Tracking Parallax
    let mouseX = 0;
    let mouseY = 0;
    const windowHalfX = window.innerWidth / 2;
    const windowHalfY = window.innerHeight / 2;

    document.addEventListener('mousemove', (event) => {
      mouseX = (event.clientX - windowHalfX) * 0.05;
      mouseY = (event.clientY - windowHalfY) * 0.05;
    });

    const clock = new THREE.Clock();

    function animate() {
      requestAnimationFrame(animate);
      const time = clock.getElapsedTime();

      // Ripple dynamic cyber grid
      const positions = gridMesh.geometry.attributes.position;
      for (let i = 0; i < positions.count; i++) {
        const x = positions.getX(i);
        const z = positions.getZ(i);
        const yVal = Math.sin((x * 0.04) + time * 1.5) * 4 + Math.cos((z * 0.04) + time * 1.2) * 4;
        positions.setY(i, yVal);
      }
      positions.needsUpdate = true;

      // Particle Drift
      stars.rotation.y = time * 0.03;
      stars.rotation.x = Math.sin(time * 0.02) * 0.1;

      // Mouse Parallax Follow
      camera.position.x += (mouseX - camera.position.x) * 0.03;
      camera.position.y += (-mouseY + 45 - camera.position.y) * 0.03;
      camera.lookAt(0, 0, 0);

      renderer.render(scene, camera);
    }

    animate();

    window.addEventListener('resize', () => {
      camera.aspect = window.innerWidth / window.innerHeight;
      camera.updateProjectionMatrix();
      renderer.setSize(window.innerWidth, window.innerHeight);
    });
  </script>
</body>
</html>
