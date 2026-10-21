<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shahid Azam - Data Scientist</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Rajdhani:wght@300;400;500;600;700&display=swap');

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #0a0e17;
    color: #e0e0e0;
    font-family: 'Rajdhani', sans-serif;
    overflow-x: hidden;
    min-height: 100vh;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
  }

  /* ===== HEADER SECTION ===== */
  .header-section {
    background: linear-gradient(135deg, #0d1117 0%, #0a1628 50%, #0d1117 100%);
    border: 2px solid #00ff88;
    border-radius: 12px;
    padding: 40px;
    position: relative;
    overflow: hidden;
    margin-bottom: 20px;
    box-shadow: 0 0 30px rgba(0, 255, 136, 0.15), inset 0 0 30px rgba(0, 255, 136, 0.05);
  }

  .header-section::before {
    content: '';
    position: absolute;
    top: -2px; left: -2px; right: -2px; bottom: -2px;
    background: linear-gradient(45deg, #00ff88, transparent, #00ff88, transparent);
    background-size: 400% 400%;
    animation: borderGlow 4s ease infinite;
    z-index: -1;
    border-radius: 14px;
  }

  @keyframes borderGlow {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
  }

  .header-content {
    display: flex;
    align-items: center;
    gap: 40px;
  }

  .header-text { flex: 1; }

  .header-text h1 {
    font-family: 'Orbitron', sans-serif;
    font-size: 3.5rem;
    font-weight: 900;
    color: #ffffff;
    text-shadow: 0 0 20px rgba(0, 255, 136, 0.5), 0 0 40px rgba(0, 255, 136, 0.3);
    letter-spacing: 4px;
    margin-bottom: 10px;
  }

  .header-text .title {
    font-family: 'Share Tech Mono', monospace;
    font-size: 1.5rem;
    color: #00ff88;
    letter-spacing: 6px;
    margin-bottom: 20px;
    position: relative;
    display: inline-block;
  }

  .header-text .title::after {
    content: '|';
    animation: blink 1s step-end infinite;
    color: #00ff88;
  }

  @keyframes blink {
    50% { opacity: 0; }
  }

  .skills-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 15px;
  }

  .skill-tag {
    background: rgba(0, 255, 136, 0.08);
    border: 1px solid rgba(0, 255, 136, 0.4);
    color: #00ff88;
    padding: 6px 16px;
    border-radius: 20px;
    font-size: 0.85rem;
    font-family: 'Share Tech Mono', monospace;
    transition: all 0.3s ease;
    cursor: default;
  }

  .skill-tag:hover {
    background: rgba(0, 255, 136, 0.2);
    box-shadow: 0 0 15px rgba(0, 255, 136, 0.3);
    transform: translateY(-2px);
  }

  .header-image {
    width: 280px;
    height: 280px;
    border-radius: 50%;
    border: 3px solid #00ff88;
    overflow: hidden;
    position: relative;
    box-shadow: 0 0 30px rgba(0, 255, 136, 0.3);
    flex-shrink: 0;
  }

  .header-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .header-image::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    border: 2px solid #00ff88;
    border-radius: 50%;
    animation: pulse-ring 2s ease-out infinite;
  }

  @keyframes pulse-ring {
    0% { transform: scale(1); opacity: 1; }
    100% { transform: scale(1.15); opacity: 0; }
  }

  /* ===== AI SECTION ===== */
  .ai-section {
    background: linear-gradient(180deg, #0d1117 0%, #0a1628 100%);
    border: 2px solid #00ff88;
    border-radius: 12px;
    padding: 40px;
    position: relative;
    overflow: hidden;
    box-shadow: 0 0 30px rgba(0, 255, 136, 0.15), inset 0 0 30px rgba(0, 255, 136, 0.05);
  }

  .ai-section::before {
    content: '';
    position: absolute;
    top: -2px; left: -2px; right: -2px; bottom: -2px;
    background: linear-gradient(45deg, #00ff88, transparent, #00ff88, transparent);
    background-size: 400% 400%;
    animation: borderGlow 4s ease infinite;
    z-index: -1;
    border-radius: 14px;
  }

  .ai-title {
    font-family: 'Orbitron', sans-serif;
    font-size: 2.8rem;
    font-weight: 900;
    text-align: center;
    color: #ffffff;
    text-shadow: 0 0 20px rgba(0, 255, 136, 0.5);
    letter-spacing: 8px;
    margin-bottom: 10px;
  }

  .ai-subtitle {
    font-family: 'Share Tech Mono', monospace;
    text-align: center;
    color: #00ff88;
    font-size: 0.9rem;
    letter-spacing: 3px;
    margin-bottom: 40px;
    opacity: 0.8;
  }

  /* ===== MAIN LAYOUT ===== */
  .main-layout {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
    gap: 20px;
    align-items: start;
  }

  /* ===== INFO BOXES ===== */
  .info-box {
    background: rgba(0, 255, 136, 0.03);
    border: 1px solid rgba(0, 255, 136, 0.3);
    border-radius: 8px;
    padding: 20px;
    margin-bottom: 15px;
    position: relative;
    transition: all 0.3s ease;
  }

  .info-box:hover {
    border-color: #00ff88;
    box-shadow: 0 0 20px rgba(0, 255, 136, 0.2);
    transform: translateX(5px);
  }

  .info-box .layer-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.7rem;
    color: #00ff88;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 5px;
    opacity: 0.7;
  }

  .info-box h3 {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.1rem;
    color: #ffffff;
    margin-bottom: 10px;
    letter-spacing: 2px;
  }

  .info-box ul {
    list-style: none;
    padding: 0;
  }

  .info-box ul li {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.8rem;
    color: #a0a0a0;
    padding: 3px 0;
    position: relative;
    padding-left: 15px;
  }

  .info-box ul li::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: #00ff88;
  }

  .box-icon {
    position: absolute;
    right: 15px;
    top: 50%;
    transform: translateY(-50%);
    font-size: 2rem;
    opacity: 0.3;
  }

  /* ===== NEURAL NETWORK CANVAS ===== */
  .neural-network-container {
    position: relative;
    width: 100%;
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  #neuralCanvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
  }

  .nn-label {
    position: absolute;
    top: 10px;
    left: 50%;
    transform: translateX(-50%);
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.75rem;
    color: #00ff88;
    letter-spacing: 3px;
    background: rgba(0, 255, 136, 0.1);
    border: 1px solid rgba(0, 255, 136, 0.3);
    padding: 5px 20px;
    border-radius: 20px;
    z-index: 2;
  }

  .nn-axis-labels {
    position: absolute;
    bottom: 10px;
    left: 0;
    right: 0;
    display: flex;
    justify-content: space-between;
    padding: 0 20px;
    z-index: 2;
  }

  .nn-axis-labels span {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.65rem;
    color: #00ff88;
    letter-spacing: 2px;
    opacity: 0.6;
  }

  /* ===== FOOTER ===== */
  .footer-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 30px;
    padding-top: 15px;
    border-top: 1px solid rgba(0, 255, 136, 0.2);
  }

  .footer-bar .training-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.75rem;
    color: #00ff88;
    letter-spacing: 2px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .footer-bar .training-label::before {
    content: '';
    width: 8px;
    height: 8px;
    background: #00ff88;
    border-radius: 50%;
    animation: pulse-dot 1.5s ease infinite;
  }

  @keyframes pulse-dot {
    0%, 100% { opacity: 1; box-shadow: 0 0 5px #00ff88; }
    50% { opacity: 0.5; box-shadow: 0 0 15px #00ff88; }
  }

  .footer-bar .metrics {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.75rem;
    color: #00ff88;
    letter-spacing: 2px;
  }

  .progress-bar {
    width: 200px;
    height: 4px;
    background: rgba(0, 255, 136, 0.1);
    border-radius: 2px;
    overflow: hidden;
    margin: 0 20px;
  }

  .progress-bar-fill {
    height: 100%;
    background: linear-gradient(90deg, #00ff88, #00cc6a);
    border-radius: 2px;
    animation: progressAnim 3s ease-in-out infinite;
    box-shadow: 0 0 10px #00ff88;
  }

  @keyframes progressAnim {
    0% { width: 20%; }
    50% { width: 85%; }
    100% { width: 20%; }
  }

  /* ===== PARTICLES BACKGROUND ===== */
  .particles-bg {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none;
    z-index: -1;
    overflow: hidden;
  }

  .particle {
    position: absolute;
    width: 2px;
    height: 2px;
    background: #00ff88;
    border-radius: 50%;
    opacity: 0.3;
    animation: float-particle linear infinite;
  }

  @keyframes float-particle {
    0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
    10% { opacity: 0.3; }
    90% { opacity: 0.3; }
    100% { transform: translateY(-100px) rotate(720deg); opacity: 0; }
  }

  /* ===== RESPONSIVE ===== */
  @media (max-width: 900px) {
    .header-content { flex-direction: column; text-align: center; }
    .header-text h1 { font-size: 2.2rem; }
    .skills-tags { justify-content: center; }
    .main-layout { grid-template-columns: 1fr; }
    .ai-title { font-size: 1.8rem; letter-spacing: 4px; }
    .header-image { width: 200px; height: 200px; }
    .neural-network-container { height: 350px; }
  }

  /* ===== SCANLINE EFFECT ===== */
  .scanline {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none;
    z-index: 9999;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0, 255, 136, 0.015) 2px,
      rgba(0, 255, 136, 0.015) 4px
    );
  }
</style>
</head>
<body>

<div class="scanline"></div>

<!-- Background Particles -->
<div class="particles-bg" id="particlesBg"></div>

<div class="container">

  <!-- HEADER -->
  <div class="header-section">
    <div class="header-content">
      <div class="header-text">
        <h1>SHAHID AZAM</h1>
        <div class="title">DATA SCIENTIST</div>
        <div class="skills-tags">
          <span class="skill-tag">Data Visualization</span>
          <span class="skill-tag">IoT</span>
          <span class="skill-tag">Artificial Intelligence</span>
          <span class="skill-tag">Data Science</span>
          <span class="skill-tag">Big Data Mining</span>
          <span class="skill-tag">Machine Learning</span>
          <span class="skill-tag">Deep Learning</span>
          <span class="skill-tag">Neural Networks</span>
        </div>
      </div>
      <div class="header-image">
        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=400&h=400&fit=crop&crop=face" alt="Shahid Azam">
      </div>
    </div>
  </div>

  <!-- AI SECTION -->
  <div class="ai-section">
    <h2 class="ai-title">ARTIFICIAL INTELLIGENCE</h2>
    <p class="ai-subtitle">MACHINE LEARNING / DEEP LEARNING / NLP / DATA VISUALIZATION / BIG DATA / IOT</p>

    <div class="main-layout">

      <!-- LEFT COLUMN -->
      <div class="left-column">
        <div class="info-box" data-connect="iot">
          <div class="layer-label">DATA LAYER</div>
          <h3>IoT & EDGE</h3>
          <ul>
            <li>Sensor data streams</li>
            <li>Edge inference</li>
            <li>Real-time telemetry</li>
          </ul>
          <div class="box-icon">📡</div>
        </div>

        <div class="info-box" data-connect="bigdata">
          <div class="layer-label">DATA LAYER</div>
          <h3>BIG DATA MINING</h3>
          <ul>
            <li>Spark and Hadoop</li>
            <li>Pattern discovery</li>
            <li>Feature extraction</li>
          </ul>
          <div class="box-icon">📊</div>
        </div>

        <div class="info-box" data-connect="viz">
          <div class="layer-label">DATA LAYER</div>
          <h3>VISUALIZATION</h3>
          <ul>
            <li>Interactive dashboards</li>
            <li>Plotly and Matplotlib</li>
            <li>Data storytelling</li>
          </ul>
          <div class="box-icon">📈</div>
        </div>
      </div>

      <!-- CENTER - NEURAL NETWORK -->
      <div class="neural-network-container">
        <div class="nn-label">NEURAL NETWORK</div>
        <canvas id="neuralCanvas"></canvas>
        <div class="nn-axis-labels">
          <span>INPUT</span>
          <span>HIDDEN LAYERS</span>
          <span>OUTPUT</span>
        </div>
      </div>

      <!-- RIGHT COLUMN -->
      <div class="right-column">
        <div class="info-box" data-connect="ml">
          <div class="layer-label">INTELLIGENCE LAYER</div>
          <h3>MACHINE LEARNING</h3>
          <ul>
            <li>Supervised learning</li>
            <li>Model evaluation</li>
            <li>Feature engineering</li>
          </ul>
          <div class="box-icon"></div>
        </div>

        <div class="info-box" data-connect="dl">
          <div class="layer-label">INTELLIGENCE LAYER</div>
          <h3>DEEP LEARNING</h3>
          <ul>
            <li>CNNs and RNNs</li>
            <li>Transformers</li>
            <li>PyTorch, TensorFlow</li>
          </ul>
          <div class="box-icon">🧠</div>
        </div>

        <div class="info-box" data-connect="nlp">
          <div class="layer-label">INTELLIGENCE LAYER</div>
          <h3>NATURAL LANGUAGE</h3>
          <ul>
            <li>Text classification</li>
            <li>Embeddings and RAG</li>
            <li>Large language models</li>
          </ul>
          <div class="box-icon">💬</div>
        </div>
      </div>

    </div>

    <!-- FOOTER BAR -->
    <div class="footer-bar">
      <div class="training-label">MODEL TRAINING</div>
      <div class="progress-bar">
        <div class="progress-bar-fill"></div>
      </div>
      <div class="metrics">LOSS DOWN / ACCURACY UP</div>
    </div>
  </div>

</div>

<script>
// ===== PARTICLES BACKGROUND =====
(function() {
  const bg = document.getElementById('particlesBg');
  for (let i = 0; i < 30; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    p.style.left = Math.random() * 100 + '%';
    p.style.animationDuration = (8 + Math.random() * 15) + 's';
    p.style.animationDelay = Math.random() * 10 + 's';
    p.style.width = p.style.height = (1 + Math.random() * 3) + 'px';
    bg.appendChild(p);
  }
})();

// ===== NEURAL NETWORK ANIMATION =====
(function() {
  const canvas = document.getElementById('neuralCanvas');
  const ctx = canvas.getContext('2d');
  let W, H;
  let time = 0;

  function resize() {
    const rect = canvas.parentElement.getBoundingClientRect();
    W = canvas.width = rect.width;
    H = canvas.height = rect.height;
  }
  resize();
  window.addEventListener('resize', resize);

  // Neural network layers
  const layers = [4, 7, 9, 7, 4];
  const nodes = [];
  const connections = [];
  const particles = [];

  // Create nodes
  function createNodes() {
    nodes.length = 0;
    const layerSpacing = W / (layers.length + 1);
    for (let l = 0; l < layers.length; l++) {
      const x = layerSpacing * (l + 1);
      const nodeSpacing = H / (layers[l] + 1);
      for (let n = 0; n < layers[l]; n++) {
        const y = nodeSpacing * (n + 1);
        nodes.push({
          x: x,
          y: y,
          layer: l,
          index: n,
          baseRadius: 4 + Math.random() * 3,
          pulsePhase: Math.random() * Math.PI * 2,
          glowIntensity: 0.3 + Math.random() * 0.7
        });
      }
    }
  }

  // Create connections
  function createConnections() {
    connections.length = 0;
    for (let l = 0; l < layers.length - 1; l++) {
      const currentLayerNodes = nodes.filter(n => n.layer === l);
      const nextLayerNodes = nodes.filter(n => n.layer === l + 1);
      for (const cn of currentLayerNodes) {
        for (const nn of nextLayerNodes) {
          if (Math.random() > 0.3) {
            connections.push({
              from: cn,
              to: nn,
              weight: 0.2 + Math.random() * 0.8,
              particleSpeed: 0.005 + Math.random() * 0.015,
              particleOffset: Math.random()
            });
          }
        }
      }
    }
  }

  // Create traveling particles
  function createParticles() {
    particles.length = 0;
    for (const conn of connections) {
      if (Math.random() > 0.5) {
        particles.push({
          connection: conn,
          progress: Math.random(),
          speed: conn.particleSpeed,
          size: 1.5 + Math.random() * 2,
          brightness: 0.5 + Math.random() * 0.5
        });
      }
    }
  }

  createNodes();
  createConnections();
  createParticles();

  window.addEventListener('resize', () => {
    resize();
    createNodes();
    createConnections();
    createParticles();
  });

  function draw() {
    ctx.clearRect(0, 0, W, H);
    time += 0.016;

    // Draw connections
    for (const conn of connections) {
      const alpha = 0.05 + conn.weight * 0.15;
      ctx.beginPath();
      ctx.moveTo(conn.from.x, conn.from.y);

      // Curved connection
      const midX = (conn.from.x + conn.to.x) / 2;
      const midY = (conn.from.y + conn.to.y) / 2;
      const curveOffset = Math.sin(time * 2 + conn.from.pulsePhase) * 10;
      ctx.quadraticCurveTo(midX + curveOffset, midY, conn.to.x, conn.to.y);

      ctx.strokeStyle = `rgba(0, 255, 136, ${alpha})`;
      ctx.lineWidth = 0.5 + conn.weight * 1;
      ctx.stroke();
    }

    // Draw traveling particles along connections
    for (const p of particles) {
      p.progress += p.speed;
      if (p.progress > 1) {
        p.progress = 0;
        p.connection = connections[Math.floor(Math.random() * connections.length)];
      }

      const conn = p.connection;
      const t = p.progress;
      const midX = (conn.from.x + conn.to.x) / 2;
      const midY = (conn.from.y + conn.to.y) / 2;
      const curveOffset = Math.sin(time * 2 + conn.from.pulsePhase) * 10;

      // Quadratic bezier point
      const px = (1-t)*(1-t)*conn.from.x + 2*(1-t)*t*(midX + curveOffset) + t*t*conn.to.x;
      const py = (1-t)*(1-t)*conn.from.y + 2*(1-t)*t*midY + t*t*conn.to.y;

      // Glow
      const gradient = ctx.createRadialGradient(px, py, 0, px, py, p.size * 4);
      gradient.addColorStop(0, `rgba(0, 255, 136, ${p.brightness * 0.8})`);
      gradient.addColorStop(0.5, `rgba(0, 255, 136, ${p.brightness * 0.3})`);
      gradient.addColorStop(1, 'rgba(0, 255, 136, 0)');
      ctx.beginPath();
      ctx.arc(px, py, p.size * 4, 0, Math.PI * 2);
      ctx.fillStyle = gradient;
      ctx.fill();

      // Core
      ctx.beginPath();
      ctx.arc(px, py, p.size, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(255, 255, 255, ${p.brightness})`;
      ctx.fill();
    }

    // Draw nodes
    for (const node of nodes) {
      const pulse = Math.sin(time * 3 + node.pulsePhase) * 0.3 + 0.7;
      const radius = node.baseRadius * (0.8 + pulse * 0.4);

      // Outer glow
      const glowRadius = radius * 4;
      const gradient = ctx.createRadialGradient(node.x, node.y, 0, node.x, node.y, glowRadius);
      gradient.addColorStop(0, `rgba(0, 255, 136, ${0.3 * node.glowIntensity * pulse})`);
      gradient.addColorStop(0.5, `rgba(0, 255, 136, ${0.1 * node.glowIntensity * pulse})`);
      gradient.addColorStop(1, 'rgba(0, 255, 136, 0)');
      ctx.beginPath();
      ctx.arc(node.x, node.y, glowRadius, 0, Math.PI * 2);
      ctx.fillStyle = gradient;
      ctx.fill();

      // Node ring
      ctx.beginPath();
      ctx.arc(node.x, node.y, radius + 2, 0, Math.PI * 2);
      ctx.strokeStyle = `rgba(0, 255, 136, ${0.4 * pulse})`;
      ctx.lineWidth = 1;
      ctx.stroke();

      // Node core
      ctx.beginPath();
      ctx.arc(node.x, node.y, radius, 0, Math.PI * 2);
      const coreGrad = ctx.createRadialGradient(node.x, node.y, 0, node.x, node.y, radius);
      coreGrad.addColorStop(0, `rgba(255, 255, 255, ${0.9 * pulse})`);
      coreGrad.addColorStop(0.7, `rgba(0, 255, 136, ${0.6 * pulse})`);
      coreGrad.addColorStop(1, `rgba(0, 200, 100, ${0.3 * pulse})`);
      ctx.fillStyle = coreGrad;
      ctx.fill();
    }

    // Draw subtle grid
    ctx.strokeStyle = 'rgba(0, 255, 136, 0.03)';
    ctx.lineWidth = 0.5;
    const gridSize = 40;
    for (let x = 0; x < W; x += gridSize) {
      ctx.beginPath();
      ctx.moveTo(x, 0);
      ctx.lineTo(x, H);
      ctx.stroke();
    }
    for (let y = 0; y < H; y += gridSize) {
      ctx.beginPath();
      ctx.moveTo(0, y);
      ctx.lineTo(W, y);
      ctx.stroke();
    }

    requestAnimationFrame(draw);
  }

  draw();
})();
</script>

</body>
</html>
