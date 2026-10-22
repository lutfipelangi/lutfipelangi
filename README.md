<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Neural Network</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #050a06;
            color: #00ff41;
            font-family: 'Share Tech Mono', monospace;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow: hidden;
        }

        .dashboard {
            width: 1000px;
            height: 600px;
            border: 2px solid #00ff41;
            border-radius: 10px;
            padding: 20px;
            display: flex;
            flex-direction: column;
            position: relative;
            box-shadow: 0 0 20px rgba(0, 255, 65, 0.2);
        }

        header {
            text-align: center;
            margin-bottom: 20px;
        }

        header h1 {
            font-size: 32px;
            letter-spacing: 5px;
            text-shadow: 0 0 10px #00ff41;
        }

        header p {
            font-size: 12px;
            color: #00aa2a;
            letter-spacing: 2px;
        }

        .main-content {
            display: flex;
            flex: 1;
            gap: 20px;
        }

        .panel {
            width: 250px;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .card {
            border: 1px solid rgba(0, 255, 65, 0.3);
            border-radius: 5px;
            padding: 10px;
            background: rgba(0, 255, 65, 0.05);
            box-shadow: inset 0 0 10px rgba(0, 255, 65, 0.1);
        }

        .card h2 {
            font-size: 12px;
            color: #00aa2a;
            margin-bottom: 5px;
        }

        .card h3 {
            font-size: 16px;
            margin-bottom: 10px;
            text-shadow: 0 0 5px #00ff41;
        }

        .card ul {
            list-style: none;
            font-size: 11px;
            color: #a0ffa0;
        }

        .card ul li::before {
            content: "> ";
            color: #00ff41;
        }

        .center-panel {
            flex: 1;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            border: 1px solid rgba(0, 255, 65, 0.1);
            border-radius: 5px;
            background: radial-gradient(circle, rgba(0, 255, 65, 0.05) 0%, transparent 70%);
        }

        canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        .canvas-label {
            position: absolute;
            bottom: 10px;
            font-size: 10px;
            color: #00aa2a;
            display: flex;
            justify-content: space-between;
            width: 80%;
        }
    </style>
</head>
<body>

    <div class="dashboard">
        <header>
            <h1>ARTIFICIAL INTELLIGENCE</h1>
            <p>MACHINE LEARNING / DEEP LEARNING / NLP / DATA VISUALIZATION / BIG DATA / IOT</p>
        </header>

        <div class="main-content">
            <!-- Kolom Kiri -->
            <div class="panel">
                <div class="card">
                    <h2>DATA LAYER</h2>
                    <h3>IoT & EDGE</h3>
                    <ul>
                        <li>Sensor data streams</li>
                        <li>Edge inference</li>
                        <li>Real-time telemetry</li>
                    </ul>
                </div>
                <div class="card">
                    <h2>DATA LAYER</h2>
                    <h3>BIG DATA MINING</h3>
                    <ul>
                        <li>Spark and Hadoop</li>
                        <li>Pattern discovery</li>
                        <li>Feature extraction</li>
                    </ul>
                </div>
                <div class="card">
                    <h2>DATA LAYER</h2>
                    <h3>VISUALIZATION</h3>
                    <ul>
                        <li>Interactive dashboards</li>
                        <li>Plotly and Matplotlib</li>
                        <li>Data storytelling</li>
                    </ul>
                </div>
            </div>

            <!-- Kolom Tengah (Animasi) -->
            <div class="center-panel">
                <canvas id="neuralCanvas"></canvas>
                <div class="canvas-label">
                    <span>INPUT</span>
                    <span>HIDDEN LAYERS</span>
                    <span>OUTPUT</span>
                </div>
            </div>

            <!-- Kolom Kanan -->
            <div class="panel">
                <div class="card">
                    <h2>INTELLIGENCE LAYER</h2>
                    <h3>MACHINE LEARNING</h3>
                    <ul>
                        <li>Supervised learning</li>
                        <li>Model evaluation</li>
                        <li>Feature engineering</li>
                    </ul>
                </div>
                <div class="card">
                    <h2>INTELLIGENCE LAYER</h2>
                    <h3>DEEP LEARNING</h3>
                    <ul>
                        <li>CNNs and RNNs</li>
                        <li>Transformers</li>
                        <li>PyTorch, TensorFlow</li>
                    </ul>
                </div>
                <div class="card">
                    <h2>INTELLIGENCE LAYER</h2>
                    <h3>NATURAL LANGUAGE</h3>
                    <ul>
                        <li>Text classification</li>
                        <li>Embeddings and RAG</li>
                        <li>Large language models</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('neuralCanvas');
        const ctx = canvas.getContext('2d');

        // Atur ukuran canvas
        function resizeCanvas() {
            canvas.width = canvas.parentElement.clientWidth;
            canvas.height = canvas.parentElement.clientHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        // Data Node (Titik-titik)
        const layers = [4, 6, 6, 4]; // Jumlah node per layer (Input, Hidden, Hidden, Output)
        let nodes = [];
        let connections = [];
        let particles = [];

        function initNetwork() {
            nodes = [];
            connections = [];
            particles = [];

            const width = canvas.width;
            const height = canvas.height;
            const layerSpacing = width / (layers.length + 1);
            const nodeRadius = 4;

            // Buat Nodes
            for (let i = 0; i < layers.length; i++) {
                const numNodes = layers[i];
                const x = layerSpacing * (i + 1);
                const ySpacing = height / (numNodes + 1);

                for (let j = 0; j < numNodes; j++) {
                    const y = ySpacing * (j + 1);
                    nodes.push({ x, y, r: nodeRadius, layer: i });
                }
            }

            // Buat Connections (Garis antar layer)
            for (let i = 0; i < nodes.length; i++) {
                for (let j = 0; j < nodes.length; j++) {
                    if (nodes[j].layer === nodes[i].layer + 1) {
                        connections.push({ from: nodes[i], to: nodes[j] });
                        
                        // Tambahkan partikel acak untuk setiap koneksi
                        if (Math.random() > 0.5) {
                            particles.push({
                                from: nodes[i],
                                to: nodes[j],
                                progress: Math.random(),
                                speed: 0.01 + Math.random() * 0.02
                            });
                        }
                    }
                }
            }
        }

        // Animasi
        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Gambar Garis (Connections)
            ctx.strokeStyle = 'rgba(0, 255, 65, 0.15)';
            ctx.lineWidth = 1;
            connections.forEach(conn => {
                ctx.beginPath();
                ctx.moveTo(conn.from.x, conn.from.y);
                ctx.lineTo(conn.to.x, conn.to.y);
                ctx.stroke();
            });

            // Gambar Partikel Bergerak (Data yang mengalir)
            particles.forEach(p => {
                p.progress += p.speed;
                if (p.progress > 1) {
                    p.progress = 0; // Reset jika sudah sampai ujung
                }

                // Interpolasi posisi
                const currentX = p.from.x + (p.to.x - p.from.x) * p.progress;
                const currentY = p.from.y + (p.to.y - p.from.y) * p.progress;

                ctx.beginPath();
                ctx.arc(currentX, currentY, 2, 0, Math.PI * 2);
                ctx.fillStyle = '#00ff41';
                ctx.shadowBlur = 10;
                ctx.shadowColor = '#00ff41';
                ctx.fill();
                ctx.shadowBlur = 0; // Reset shadow
            });

            // Gambar Nodes (Titik)
            nodes.forEach(node => {
                ctx.beginPath();
                ctx.arc(node.x, node.y, node.r, 0, Math.PI * 2);
                ctx.fillStyle = '#00ff41';
                ctx.fill();
                
                // Efek cincin luar
                ctx.beginPath();
                ctx.arc(node.x, node.y, node.r + 2, 0, Math.PI * 2);
                ctx.strokeStyle = 'rgba(0, 255, 65, 0.5)';
                ctx.stroke();
            });

            requestAnimationFrame(animate);
        }

        // Jalankan
        resizeCanvas();
        initNetwork();
        animate();

        // Re-init jika ukuran layar berubah
        window.addEventListener('resize', () => {
            resizeCanvas();
            initNetwork();
        });
    </script>
</body>
</html>
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:001a0b,50:00ff88,100:001a0b&height=180&section=header&text=MASPEL&fontSize=64&fontColor=ffffff&fontAlignY=38&desc=CREATIVE%20DIGITAL%20%7C%20BUSINESS%20%7C%20OWNER&descAlignY=62&descSize=16" width="100%" alt="MASPEL neon header"/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=00FF88&center=true&vCenter=true&width=650&lines=Welcome+to+MASPEL's+GitHub;Building+Ideas+into+Digital+Projects;AI+%7C+Automation+%7C+Creative+Tech;Learn.+Build.+Improve." alt="Animated typing text"/>

</div>

---

<div align="center">

<img src="https://img.shields.io/badge/IDENTITY-MASPEL-00ff88?style=for-the-badge&labelColor=07130d" alt="MASPEL"/>
<img src="https://img.shields.io/badge/MODE-ALWAYS%20LEARNING-00ff88?style=for-the-badge&labelColor=07130d" alt="Always learning"/>

</div>

## 🟢 ABOUT MASPEL

> Exploring technology, creating useful things, and turning ideas into reality.

- 🤖 AI tools and experiments
- ⚙️ Automation and practical workflows
- 💻 Open-source technology
- 🎨 Digital creativity and learning

## ⚡ TECHNOLOGY

<div align="center">

<img src="https://skillicons.dev/icons?i=python,git,github,linux,bash,html,css,js&theme=dark" alt="Technology icons"/>

</div>

## 🧬 DIGITAL ACTIVITY



## ◈ CURRENT MISSIONS

- `01` — Explore AI and local agents
- `02` — Build useful automations
- `03` — Learn by making real projects
- `04` — Improve a little every day

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:001a0b,50:00ff88,100:001a0b&height=100&section=footer" width="100%" alt="Neon footer"/>

<sub>SMALL STEPS · REAL PROGRESS · KEEP BUILDING</sub>

</div>


<div align="center">

# <img src="https://readme-typing-svg.herokuapp.com?font=Orbitron&size=40&duration=3000&color=00FF88&center=true&vCenter=true&width=600&lines=MASPEL" alt="MASPEL" />

### <img src="https://readme-typing-svg.herokuapp.com?font=Share+Tech+Mono&size=20&duration=2000&color=00FF88&center=true&vCenter=true&width=400&lines=DATA+SCIENTIST" alt="Data Scientist" />

<br>

<!-- SKILLS BADGES -->
<table align="center">
<tr>
<td>

![Data Visualization](https://img.shields.io/badge/Data_Visualization-00FF88?style=for-the-badge&logo=apache-echarts&logoColor=white&labelColor=0d1117)
![IoT](https://img.shields.io/badge/IoT-00FF88?style=for-the-badge&logo=arduino&logoColor=white&labelColor=0d1117)
![AI](https://img.shields.io/badge/Artificial_Intelligence-00FF88?style=for-the-badge&logo=openai&logoColor=white&labelColor=0d1117)
![Data Science](https://img.shields.io/badge/Data_Science-00FF88?style=for-the-badge&logo=python&logoColor=white&labelColor=0d1117)

</td>
</tr>
<tr>
<td>

![Big Data](https://img.shields.io/badge/Big_Data_Mining-00FF88?style=for-the-badge&logo=apache-spark&logoColor=white&labelColor=0d1117)
![Machine Learning](https://img.shields.io/badge/Machine_Learning-00FF88?style=for-the-badge&logo=scikit-learn&logoColor=white&labelColor=0d1117)
![Deep Learning](https://img.shields.io/badge/Deep_Learning-00FF88?style=for-the-badge&logo=pytorch&logoColor=white&labelColor=0d1117)
![Neural Networks](https://img.shields.io/badge/Neural_Networks-00FF88?style=for-the-badge&logo=keras&logoColor=white&labelColor=0d1117)

</td>
</tr>
</table>

<br>

<!-- ANIMATED NEURAL NETWORK SVG -->
<svg width="700" height="400" viewBox="0 0 700 400" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <radialGradient id="nodeGlow" cx="50%" cy="50%" r="50%">
      <stop offset="0%" style="stop-color:#ffffff;stop-opacity:0.9"/>
      <stop offset="50%" style="stop-color:#00FF88;stop-opacity:0.6"/>
      <stop offset="100%" style="stop-color:#00FF88;stop-opacity:0"/>
    </radialGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
    <linearGradient id="lineGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#00FF88;stop-opacity:0.1"/>
      <stop offset="50%" style="stop-color:#00FF88;stop-opacity:0.6"/>
      <stop offset="100%" style="stop-color:#00FF88;stop-opacity:0.1"/>
    </linearGradient>
  </defs>

  <!-- Background -->
  <rect width="700" height="400" fill="#0a0e17" rx="12"/>

  <!-- Grid lines -->
  <g stroke="#00FF88" stroke-opacity="0.05" stroke-width="0.5">
    <line x1="0" y1="50" x2="700" y2="50"/>
    <line x1="0" y1="100" x2="700" y2="100"/>
    <line x1="0" y1="150" x2="700" y2="150"/>
    <line x1="0" y1="200" x2="700" y2="200"/>
    <line x1="0" y1="250" x2="700" y2="250"/>
    <line x1="0" y1="300" x2="700" y2="300"/>
    <line x1="0" y1="350" x2="700" y2="350"/>
    <line x1="100" y1="0" x2="100" y2="400"/>
    <line x1="200" y1="0" x2="200" y2="400"/>
    <line x1="300" y1="0" x2="300" y2="400"/>
    <line x1="400" y1="0" x2="400" y2="400"/>
    <line x1="500" y1="0" x2="500" y2="400"/>
    <line x1="600" y1="0" x2="600" y2="400"/>
  </g>

  <!-- Title -->
  <text x="350" y="35" text-anchor="middle" font-family="monospace" font-size="14" fill="#00FF88" letter-spacing="4" opacity="0.8"></text>

  <!-- CONNECTIONS with animated dashes -->
  <g stroke="#00FF88" stroke-width="1" fill="none" opacity="0.3">
    <!-- Layer 1 to Layer 2 -->
    <line x1="120" y1="120" x2="260" y2="80" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="2s" repeatCount="indefinite"/>
    </line>
    <line x1="120" y1="120" x2="260" y2="160" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="2.5s" repeatCount="indefinite"/>
    </line>
    <line x1="120" y1="120" x2="260" y2="240" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="1.8s" repeatCount="indefinite"/>
    </line>
    <line x1="120" y1="200" x2="260" y2="80" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="2.2s" repeatCount="indefinite"/>
    </line>
    <line x1="120" y1="200" x2="260" y2="160" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="1.9s" repeatCount="indefinite"/>
    </line>
    <line x1="120" y1="200" x2="260" y2="240" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="2.3s" repeatCount="indefinite"/>
    </line>
    <line x1="120" y1="200" x2="260" y2="320" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="2.1s" repeatCount="indefinite"/>
    </line>
    <line x1="120" y1="280" x2="260" y2="160" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="2.4s" repeatCount="indefinite"/>
    </line>
    <line x1="120" y1="280" x2="260" y2="240" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="1.7s" repeatCount="indefinite"/>
    </line>
    <line x1="120" y1="280" x2="260" y2="320" stroke-dasharray="4,4">
      <animate attributeName="stroke-dashoffset" from="0" to="-16" dur="2.6s" repeatCount="indefinite"/>
    </line>

   
  </g>

  <!-- TRAVELING PARTICLES (animated circles along paths) -->
  <circle r="3" fill="#ffffff" filter="url(#glow)">
    <animateMotion dur="3s" repeatCount="indefinite" path="M120,120 L260,160 L400,220 L540,200 L620,250"/>
  </circle>
  <circle r="2.5" fill="#00FF88" filter="url(#glow)">
    <animateMotion dur="4s" repeatCount="indefinite" path="M120,200 L260,80 L400,140 L540,100 L620,150"/>
  </circle>
  <circle r="2" fill="#ffffff" filter="url(#glow)">
    <animateMotion dur="3.5s" repeatCount="indefinite" path="M120,280 L260,240 L400,300 L540,300 L620,250"/>
  </circle>
  <circle r="3" fill="#00FF88" filter="url(#glow)">
    <animateMotion dur="4.5s" repeatCount="indefinite" path="M120,120 L260,240 L400,60 L540,100 L620,150"/>
  </circle>
  <circle r="2" fill="#ffffff" filter="url(#glow)">
    <animateMotion dur="3.2s" repeatCount="indefinite" path="M120,200 L260,320 L400,360 L540,300 L620,250"/>
  </circle>

  <!-- NODES - Layer 1 (Input) -->
  <g>
    <circle cx="120" cy="120" r="12" fill="url(#nodeGlow)" filter="url(#glow)">
      <animate attributeName="r" values="10;14;10" dur="2s" repeatCount="indefinite"/>
    </circle>
    <circle cx="120" cy="120" r="6" fill="#00FF88" opacity="0.8">
      <animate attributeName="opacity" values="0.5;1;0.5" dur="2s" repeatCount="indefinite"/>
    </circle>

   
  </g>

  <!-- NODES - Layer 2 -->
  <g>
    <circle cx="260" cy="80" r="10" fill="url(#nodeGlow)" filter="url(#glow)">
      <animate attributeName="r" values="8;12;8" dur="2.1s" repeatCount="indefinite"/>
    </circle>
    <circle cx="260" cy="80" r="5" fill="#00FF88" opacity="0.8">
      <animate attributeName="opacity" values="0.5;1;0.5" dur="2.1s" repeatCount="indefinite"/>
    </circle>

  
  </g>

  <!-- NODES - Layer 3 (Hidden) -->
  <g>
    <circle cx="400" cy="60" r="9" fill="url(#nodeGlow)" filter="url(#glow)">
      <animate attributeName="r" values="7;11;7" dur="2s" repeatCount="indefinite"/>
    </circle>
    <circle cx="400" cy="60" r="4.5" fill="#00FF88" opacity="0.8">
      <animate attributeName="opacity" values="0.5;1;0.5" dur="2s" repeatCount="indefinite"/>
    </circle>

    
  </g>

  <!-- NODES - Layer 4 -->
  <g>
    <circle cx="540" cy="100" r="10" fill="url(#nodeGlow)" filter="url(#glow)">
      <animate attributeName="r" values="8;12;8" dur="2.2s" repeatCount="indefinite"/>
    </circle>
    <circle cx="540" cy="100" r="5" fill="#00FF88" opacity="0.8">
      <animate attributeName="opacity" values="0.5;1;0.5" dur="2.2s" repeatCount="indefinite"/>
    </circle>

    
  </g>

  <!-- NODES - Layer 5 (Output) -->
  <g>
    <circle cx="620" cy="150" r="12" fill="url(#nodeGlow)" filter="url(#glow)">
      <animate attributeName="r" values="10;14;10" dur="2s" repeatCount="indefinite"/>
    </circle>
    <circle cx="620" cy="150" r="6" fill="#00FF88" opacity="0.8">
      <animate attributeName="opacity" values="0.5;1;0.5" dur="2s" repeatCount="indefinite"/>
    </circle>

   
  </g>

  <!-- Axis Labels -->
  <text x="120" y="390" text-anchor="middle" font-family="monospace" font-size="10" fill="#00FF88" opacity="0.6"></text>
  <text x="350" y="390" text-anchor="middle" font-family="monospace" font-size="10" fill="#00FF88" opacity="0.6"></text>
  <text x="620" y="390" text-anchor="middle" font-family="monospace" font-size="10" fill="#00FF88" opacity="0.6"></text>
</svg>

<br>

<!-- AI SECTION TITLE -->
# 🧠 ARTIFICIAL INTELLIGENCE

### `MACHINE LEARNING / DEEP LEARNING / NLP / DATA VISUALIZATION / BIG DATA / IOT`

<br>

<!-- INFO BOXES TABLE -->
<table align="center" width="100%">
<tr>
<td width="50%" valign="top">

### 📡 DATA LAYER — IoT & EDGE
- Sensor data streams
- Edge inference
- Real-time telemetry

### 📊 DATA LAYER — Big Data Mining
- Spark and Hadoop
- Pattern discovery
- Feature extraction

### 📈 DATA LAYER — Visualization
- Interactive dashboards
- Plotly and Matplotlib
- Data storytelling

</td>
<td width="50%" valign="top">

### 🤖 INTELLIGENCE LAYER — Machine Learning
- Supervised learning
- Model evaluation
- Feature engineering

###  INTELLIGENCE LAYER — Deep Learning
- CNNs and RNNs
- Transformers
- PyTorch, TensorFlow

### 💬 INTELLIGENCE LAYER — Natural Language
- Text classification
- Embeddings and RAG
- Large language models

</td>
</tr>
</table>

<br>

<!-- PROGRESS BAR -->
<table align="center">
<tr>
<td>

**🟢 MODEL TRAINING**

</td>
<td>

![Training Progress](https://geps.dev/progress/75?bgColor=0d1117&color=00FF88&titleColor=00FF88)

</td>
<td>

**LOSS DOWN / ACCURACY UP **

</td>
</tr>
</table>

<br>

<!-- GITHUB STATS -->
<table align="center">
<tr>
<td>
  <img src="https://github-readme-stats.vercel.app/api?username=lutfipelangi&show_icons=true&theme=transparent&title_color=00FF88&text_color=e0e0e0&icon_color=00FF88&bg_color=0d1117&border_color=00FF88&hide_border=false" width="400" alt="GitHub Stats"/>
</td>
<td>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=lutfipelangi&layout=compact&theme=transparent&title_color=00FF88&text_color=e0e0e0&bg_color=0d1117&border_color=00FF88&hide_border=false" width="300" alt="Top Languages"/>
</td>
</tr>
</table>

<br>




<br>

<!-- FOOTER -->
---
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:00FF88,100:0a1628&height=80&section=footer&text=MASPEL&fontSize=30&fontColor=ffffff&animation=twinkling" width="100%"/>
</p>

</div>

<div align="center">

<!-- Efek Mengetik (Typing Effect) Warna Hijau -->
<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=26&pause=1000&color=00FF00&background=000000&center=true&vCenter=true&width=600&lines=Welcome+to+my+terminal...;root@github:~%23+whoami;I+use+Linux+btw...;sudo+apt+install+knowledge;Access+Granted." alt="Typing SVG" />
</a>

<br><br>

<!-- Kotak Terminal Palsu -->
<div align="left" style="background-color: #000000; border: 1px solid #00FF00; border-radius: 5px; padding: 15px; font-family: 'Courier New', Courier, monospace; color: #00FF00; box-shadow: 0px 0px 10px #00FF00;">



       .---.        OS: Linux (Custom Kernel)
      /     \       Shell: bash 5.2.21
     | () () |      Terminal: Alacritty
      \  ^  /       DE: i3wm / XFCE
       |||||        CPU: AMD Ryzen Threadripper 9960X 
       |||||        RAM: 64GB DDR5
                  Uptime: 1337 days


