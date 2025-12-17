<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&display=swap">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&display=swap">
<link rel="stylesheet" href="../stylesheets/mapa-galaxia.css">

<style>
/* ==== OCULTAR TODO LO DE MKDOCS ==== */
.md-header, .md-tabs, .md-sidebar, .md-nav__title, 
h1:first-of-type, .md-typeset h1,
.md-footer, .md-search, .md-logo {
    display: none !important;
    visibility: hidden !important;
    height: 0 !important;
    margin: 0 !important;
    padding: 0 !important;
    font-size: 0 !important;
    line-height: 0 !important;
}

body {
    margin-top: 0 !important;
    padding-top: 0 !important;
    overflow: hidden !important;
    background: #000 !important;
}

/* ===== MENÚ DESORDENADO ===== */
.menu-container {
    display: flex !important;
    justify-content: center !important;
    align-items: center !important;
    width: 100% !important;
    margin: 0 !important;
    padding: 1rem 0 !important;
    background: linear-gradient(90deg, #0a0a0a, #1a1a2e) !important;
    border-bottom: 2px solid #ff5e7d !important;
    position: relative !important;
    z-index: 1000;
    transform: rotate(-0.5deg);
}

.custom-header-menu {
    display: flex;
    align-items: center;
    gap: 4rem;
    margin: 0;
    padding: 0;
    transform: skewX(-5deg);
}

.custom-header-menu a {
    color: #00c6ff;
    text-decoration: none;
    font-weight: 700;
    font-size: 1.1rem;
    padding: 0.5rem 1rem;
    border: 2px solid transparent;
    transition: all 0.4s ease;
    font-family: 'Space Mono', monospace;
    text-transform: uppercase;
    letter-spacing: 2px;
    position: relative;
    overflow: hidden;
}

.custom-header-menu a:hover {
    color: #ff5e7d;
    border-color: #ff5e7d;
    transform: translateY(-3px) skewX(5deg);
    box-shadow: 0 5px 20px rgba(255, 94, 125, 0.4);
}

.custom-header-menu a:before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
    transition: 0.5s;
}

.custom-header-menu a:hover:before {
    left: 100%;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --pigeon-blood: #ff4757;
    --microbe-glow: #00d2d3;
    --pollution-smog: #a4b0be;
    --concrete-gray: #57606f;
    --breath-blue: #70a1ff;
    --gut-green: #2ed573;
    --invisible-white: rgba(255, 255, 255, 0.1);
    --warning-yellow: #ffa502;
    --death-black: #000000;
}

body {
    font-family: 'Montserrat', sans-serif;
    background: radial-gradient(ellipse at center, #0a0e17 0%, #000000 100%);
    color: #fff;
    margin: 0;
    padding: 0;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    position: relative;
    overflow: hidden;
}

/* ==== CONTENEDOR PRINCIPAL - DESORDENADO ==== */
.main-container {
    flex: 1;
    position: relative;
    overflow: hidden;
    width: 100%;
    height: calc(100vh - 80px);
    background: 
        radial-gradient(circle at 20% 30%, rgba(255, 71, 87, 0.05) 0%, transparent 50%),
        radial-gradient(circle at 80% 70%, rgba(0, 210, 211, 0.05) 0%, transparent 50%),
        radial-gradient(circle at 40% 90%, rgba(112, 161, 255, 0.03) 0%, transparent 50%);
}

/* FONDO CÓSMICO DESORDENADO */
#stars {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    pointer-events: none;
}

.star {
    position: absolute;
    background: white;
    border-radius: 50%;
    opacity: 0;
    animation: twinkle var(--duration) infinite var(--delay);
}

@keyframes twinkle {
    0%, 100% { opacity: 0.05; transform: scale(1); }
    50% { opacity: var(--opacity); transform: scale(1.2); }
}

/* ESTRELLAS QUE PARPADEAN DIFERENTE */
.star.type1 { animation-timing-function: ease-in-out; }
.star.type2 { animation-timing-function: cubic-bezier(0.4, 0, 0.6, 1); }
.star.type3 { animation-timing-function: steps(4, end); }

/* Viewport DESORDENADO */
.viewport {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    cursor: grab;
    background: transparent;
}

.viewport.grabbing {
    cursor: grabbing;
}

/* GALAXIA ORGÁNICA, NO PERFECTA */
#galaxy {
    position: absolute;
    width: 5000px;
    height: 5000px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0.3) rotate(5deg);
    transform-origin: center center;
    transition: transform 0.2s cubic-bezier(0.4, 0, 0.2, 1);
    will-change: transform;
}

/* CANVAS CON TEXTOURE */
#galaxy-canvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    filter: contrast(1.2) brightness(0.9);
}

/* NODO CENTRAL - NO PERFECTO */
.central-node {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) rotate(-10deg);
    width: 450px;
    height: 450px;
    border-radius: 35% 65% 70% 30% / 30% 40% 60% 70%;
    background: 
        radial-gradient(circle at 30% 30%, var(--pigeon-blood) 0%, transparent 70%),
        radial-gradient(circle at 70% 70%, var(--microbe-glow) 0%, transparent 70%),
        radial-gradient(circle at 50% 50%, rgba(0, 0, 0, 0.8) 0%, transparent 100%);
    box-shadow: 
        inset 0 0 100px rgba(255, 71, 87, 0.3),
        inset 0 0 100px rgba(0, 210, 211, 0.3),
        0 0 200px rgba(255, 71, 87, 0.5),
        0 0 300px rgba(0, 210, 211, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    z-index: 10;
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    border: 3px solid rgba(255, 255, 255, 0.1);
    animation: float 8s ease-in-out infinite;
}

@keyframes float {
    0%, 100% { transform: translate(-50%, -50%) rotate(-10deg) translateY(0) scale(1); }
    50% { transform: translate(-50%, -50%) rotate(-8deg) translateY(-20px) scale(1.02); }
}

.central-node:hover {
    transform: translate(-50%, -50%) rotate(0deg) scale(1.1);
    border-radius: 50% 30% 40% 60% / 60% 30% 70% 40%;
    box-shadow: 
        inset 0 0 150px rgba(255, 71, 87, 0.4),
        inset 0 0 150px rgba(0, 210, 211, 0.4),
        0 0 300px rgba(255, 71, 87, 0.7),
        0 0 500px rgba(0, 210, 211, 0.5);
    animation: none;
}

.central-node-content {
    text-align: center;
    padding: 50px;
    width: 100%;
    transform: rotate(10deg);
}

.central-node-title {
    font-weight: 900;
    font-size: 2.8rem;
    text-transform: uppercase;
    letter-spacing: 5px;
    margin-bottom: 15px;
    color: #ffffff;
    text-shadow: 
        0 0 10px rgba(255, 71, 87, 0.8),
        0 0 20px rgba(0, 210, 211, 0.8),
        0 0 40px rgba(255, 71, 87, 0.6);
    line-height: 1.1;
    font-family: 'Space Mono', monospace;
}

.central-node-subtitle {
    font-weight: 300;
    font-size: 1rem;
    color: rgba(255, 255, 255, 0.7);
    letter-spacing: 8px;
    text-transform: uppercase;
    font-style: italic;
}

/* NODOS ORGÁNICOS - FORMAS IMPERFECTAS */
.node {
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    z-index: 5;
    overflow: hidden;
    padding: 20px;
    text-align: center;
    border: 2px solid rgba(255, 255, 255, 0.1);
    filter: drop-shadow(0 0 10px currentColor);
    animation: nodeFloat var(--float-duration) ease-in-out infinite var(--float-delay);
}

@keyframes nodeFloat {
    0%, 100% { transform: translate(-50%, -50%) rotate(var(--rotation)) translateY(0); }
    50% { transform: translate(-50%, -50%) rotate(calc(var(--rotation) + 5deg)) translateY(-15px); }
}

.node-icon {
    font-size: 2.5rem;
    margin-bottom: 15px;
    opacity: 0.9;
    filter: drop-shadow(0 0 8px currentColor);
}

.node-title {
    font-weight: 700;
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    color: #ffffff;
    text-shadow: 0 1px 3px rgba(0, 0, 0, 0.8);
    line-height: 1.3;
    width: 100%;
    word-wrap: break-word;
    font-family: 'Space Mono', monospace;
}

.node-subtitle {
    font-size: 0.7rem;
    color: rgba(255, 255, 255, 0.6);
    margin-top: 8px;
    font-weight: 300;
    font-style: italic;
}

/* FORMAS ORGÁNICAS PARA NODOS */
.node.shape1 { border-radius: 40% 60% 60% 40% / 60% 40% 60% 40%; }
.node.shape2 { border-radius: 30% 70% 50% 50% / 30% 50% 70% 70%; }
.node.shape3 { border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%; }
.node.shape4 { border-radius: 50% 50% 30% 70% / 50% 30% 70% 50%; }
.node.shape5 { border-radius: 70% 30% 50% 50% / 30% 70% 50% 70%; }
.node.shape6 { border-radius: 40% 60% 70% 30% / 40% 50% 60% 70%; }

/* COLORES Y EFECTOS DE NODOS */
.pigeon-node {
    background: radial-gradient(circle at 30% 30%, 
        rgba(255, 71, 87, 0.9) 0%,
        rgba(255, 71, 87, 0.6) 40%,
        transparent 80%);
    box-shadow: 
        inset 0 0 30px rgba(255, 71, 87, 0.3),
        0 0 50px rgba(255, 71, 87, 0.6);
    border-color: rgba(255, 71, 87, 0.3);
}

.microbe-node {
    background: radial-gradient(circle at 70% 30%, 
        rgba(0, 210, 211, 0.9) 0%,
        rgba(0, 210, 211, 0.6) 40%,
        transparent 80%);
    box-shadow: 
        inset 0 0 30px rgba(0, 210, 211, 0.3),
        0 0 50px rgba(0, 210, 211, 0.6);
    border-color: rgba(0, 210, 211, 0.3);
}

.pollution-node {
    background: radial-gradient(circle at 50% 50%, 
        rgba(164, 176, 190, 0.8) 0%,
        rgba(87, 96, 111, 0.6) 50%,
        transparent 80%);
    box-shadow: 
        inset 0 0 30px rgba(164, 176, 190, 0.2),
        0 0 50px rgba(164, 176, 190, 0.4);
    border-color: rgba(164, 176, 190, 0.2);
}

.breath-node {
    background: radial-gradient(circle at 20% 80%, 
        rgba(112, 161, 255, 0.9) 0%,
        rgba(112, 161, 255, 0.6) 40%,
        transparent 80%);
    box-shadow: 
        inset 0 0 30px rgba(112, 161, 255, 0.3),
        0 0 50px rgba(112, 161, 255, 0.6);
    border-color: rgba(112, 161, 255, 0.3);
}

.gut-node {
    background: radial-gradient(circle at 80% 20%, 
        rgba(46, 213, 115, 0.9) 0%,
        rgba(46, 213, 115, 0.6) 40%,
        transparent 80%);
    box-shadow: 
        inset 0 0 30px rgba(46, 213, 115, 0.3),
        0 0 50px rgba(46, 213, 115, 0.6);
    border-color: rgba(46, 213, 115, 0.3);
}

.warning-node {
    background: radial-gradient(circle at 50% 20%, 
        rgba(255, 165, 2, 0.9) 0%,
        rgba(255, 165, 2, 0.6) 40%,
        transparent 80%);
    box-shadow: 
        inset 0 0 30px rgba(255, 165, 2, 0.3),
        0 0 50px rgba(255, 165, 2, 0.6);
    border-color: rgba(255, 165, 2, 0.3);
}

.invisible-node {
    background: radial-gradient(circle at 20% 50%, 
        rgba(255, 255, 255, 0.3) 0%,
        rgba(255, 255, 255, 0.1) 40%,
        transparent 80%);
    box-shadow: 
        inset 0 0 30px rgba(255, 255, 255, 0.1),
        0 0 40px rgba(255, 255, 255, 0.2);
    border-color: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(5px);
}

/* EFECTO HOVER DESORDENADO */
.node:hover {
    transform: scale(1.4) translate(-50%, -50%) rotate(calc(var(--rotation) + 20deg)) !important;
    z-index: 20;
    box-shadow: 
        0 0 100px currentColor,
        inset 0 0 50px rgba(255, 255, 255, 0.2);
    border-color: rgba(255, 255, 255, 0.4);
    animation: none !important;
    filter: drop-shadow(0 0 20px currentColor) brightness(1.3);
}

/* PANEL DE CONTENIDO DESORDENADO */
.content-panel {
    position: fixed;
    top: 100px;
    right: 20px;
    width: 450px;
    max-height: 80vh;
    overflow-y: auto;
    background: rgba(0, 0, 0, 0.85);
    backdrop-filter: blur(20px) saturate(180%);
    border-radius: 15px 0 15px 15px;
    padding: 30px;
    box-shadow: 
        0 20px 60px rgba(0, 0, 0, 0.8),
        inset 0 1px 0 rgba(255, 255, 255, 0.1),
        0 0 0 1px rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.15);
    z-index: 1000;
    display: none;
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    transform-origin: top right;
    transform: translateX(20px) rotate(1deg);
    opacity: 0;
}

.content-panel.active {
    display: block;
    animation: panelIn 0.6s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}

@keyframes panelIn {
    from { 
        opacity: 0;
        transform: translateX(50px) rotate(5deg) scale(0.9);
    }
    to { 
        opacity: 1;
        transform: translateX(0) rotate(0deg) scale(1);
    }
}

.panel-category {
    display: inline-block;
    font-size: 0.75rem;
    padding: 8px 20px;
    border-radius: 20px;
    margin-bottom: 25px;
    font-weight: 800;
    color: #000;
    text-transform: uppercase;
    letter-spacing: 2px;
    transform: skewX(-10deg);
    font-family: 'Space Mono', monospace;
}

.panel-title {
    font-size: 1.8rem;
    font-weight: 900;
    margin-bottom: 20px;
    color: #fff;
    line-height: 1.2;
    text-transform: uppercase;
    letter-spacing: 3px;
    font-family: 'Space Mono', monospace;
}

.panel-text {
    font-size: 1rem;
    line-height: 1.7;
    color: rgba(255, 255, 255, 0.8);
    margin-bottom: 25px;
    font-weight: 300;
}

.panel-list {
    margin: 20px 0;
    padding-left: 0;
}

.panel-list-item {
    font-size: 0.95rem;
    color: rgba(255, 255, 255, 0.7);
    margin-bottom: 12px;
    line-height: 1.6;
    position: relative;
    padding-left: 25px;
    transform: translateX(10px);
}

.panel-list-item:before {
    content: '→';
    color: currentColor;
    position: absolute;
    left: 0;
    opacity: 0.5;
}

.panel-poem {
    background: rgba(255, 255, 255, 0.05);
    border-left: 3px solid;
    padding: 20px;
    margin: 25px 0;
    border-radius: 0 8px 8px 0;
    font-style: italic;
    font-weight: 300;
    line-height: 1.8;
    color: rgba(255, 255, 255, 0.6);
}

.panel-poem-title {
    font-size: 0.9rem;
    font-weight: 700;
    margin-bottom: 10px;
    text-transform: uppercase;
    letter-spacing: 2px;
    color: rgba(255, 255, 255, 0.8);
    font-family: 'Space Mono', monospace;
}

.panel-close {
    position: absolute;
    top: 15px;
    right: 15px;
    background: rgba(255, 255, 255, 0.1);
    border: none;
    color: rgba(255, 255, 255, 0.6);
    font-size: 1.8rem;
    cursor: pointer;
    transition: all 0.3s;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1001;
    transform: rotate(45deg);
}

.panel-close:hover {
    background: rgba(255, 255, 255, 0.2);
    color: #fff;
    transform: rotate(135deg);
}

/* LEYENDA ORGÁNICA */
.legend {
    position: fixed;
    bottom: 20px;
    left: 20px;
    background: rgba(0, 0, 0, 0.7);
    backdrop-filter: blur(10px);
    padding: 20px;
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.1);
    z-index: 1000;
    max-width: 280px;
    transform: rotate(-1deg);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

.legend-title {
    font-size: 0.9rem;
    font-weight: 700;
    margin-bottom: 15px;
    color: #fff;
    text-transform: uppercase;
    letter-spacing: 3px;
    font-family: 'Space Mono', monospace;
    transform: skewX(-5deg);
}

.legend-items {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.legend-item {
    display: flex;
    align-items: center;
    gap: 12px;
    transform: translateX(5px);
}

.legend-color {
    width: 14px;
    height: 14px;
    border-radius: 50%;
    flex-shrink: 0;
    box-shadow: 0 0 10px currentColor;
}

.legend-label {
    font-size: 0.8rem;
    color: rgba(255, 255, 255, 0.7);
    line-height: 1.3;
    font-weight: 300;
}

/* INSTRUCCIONES POÉTICAS */
.instructions {
    position: fixed;
    bottom: 20px;
    right: 20px;
    text-align: right;
    font-size: 0.8rem;
    color: rgba(255, 255, 255, 0.3);
    z-index: 1000;
    background: rgba(0, 0, 0, 0.3);
    padding: 15px;
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.05);
    max-width: 250px;
    backdrop-filter: blur(5px);
    line-height: 1.6;
    font-style: italic;
    transform: rotate(1deg);
}

/* RESPONSIVE DESORDENADO */
@media (max-width: 1200px) {
    #galaxy {
        width: 4000px;
        height: 4000px;
    }
    
    .central-node {
        width: 380px;
        height: 380px;
    }
    
    .node {
        width: 160px;
        height: 160px;
    }
    
    .content-panel {
        width: 400px;
    }
}

@media (max-width: 900px) {
    #galaxy {
        width: 3500px;
        height: 3500px;
        transform: translate(-50%, -50%) scale(0.25) rotate(3deg);
    }
    
    .central-node {
        width: 320px;
        height: 320px;
    }
    
    .node {
        width: 140px;
        height: 140px;
    }
    
    .content-panel {
        width: calc(100% - 40px);
        max-width: 400px;
        top: 90px;
    }
    
    .legend {
        display: none;
    }
}

@media (max-width: 600px) {
    .main-container {
        height: calc(100vh - 60px);
    }
    
    .menu-container {
        padding: 10px;
        transform: rotate(0);
    }
    
    .custom-header-menu {
        gap: 15px;
        transform: skewX(0);
    }
    
    .custom-header-menu a {
        font-size: 0.8rem;
        padding: 0.3rem 0.6rem;
    }
    
    .content-panel {
        left: 10px;
        right: 10px;
        max-width: none;
        top: 80px;
        padding: 20px;
        transform: none;
    }
    
    .central-node {
        width: 250px;
        height: 250px;
    }
    
    .node {
        width: 120px;
        height: 120px;
    }
    
    .central-node-title {
        font-size: 1.8rem;
        letter-spacing: 3px;
    }
    
    .node-title {
        font-size: 0.8rem;
    }
    
    .instructions {
        display: none;
    }
}
</style>

<!-- MENÚ DESALIÑADO -->
<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">PROJECTS</a>
        <a href="../../about/me">ABOUT</a>
    </div>
</div>

<!-- CONTENEDOR PRINCIPAL -->
<div class="main-container">
    <div id="stars"></div>
    
    <!-- Viewport -->
    <div class="viewport" id="viewport">
        <div id="galaxy">
            <canvas id="galaxy-canvas"></canvas>
            
            <!-- Nodo central orgánico -->
            <div class="central-node" id="centralNode">
                <div class="central-node-content">
                    <div class="central-node-title">INFRASTRUCTURE OF URBAN NON-HUMAN LIFE</div>
                    <div class="central-node-subtitle">Pigeons & Urban Microorganisms</div>
                </div>
            </div>
            
            <!-- Nodos serán generados aleatoriamente -->
        </div>
    </div>
</div>

<!-- Panel de contenido poético -->
<div class="content-panel" id="contentPanel">
    <button class="panel-close" id="closePanel">+</button>
    <div class="panel-category" id="panelCategory">VISIBLE/INVISIBLE</div>
    <h2 class="panel-title" id="panelTitle">THE BLOOD & THE GLOW</h2>
    <p class="panel-text" id="panelText">Pigeons bleed red where concrete bites. Microbes glow blue where toxins pool. One we see but refuse. One we need but ignore. The city breathes through both.</p>
    
    <div class="panel-poem" id="panelPoem">
        <div class="panel-poem-title" id="poemTitle">from the gut of the city</div>
        <p id="poemText">pigeon shit on polished marble / microbes dancing in smog / the invisible infrastructure / of everything we call progress</p>
    </div>
    
    <div class="panel-list" id="panelList">
        <!-- List items serán poblados por JavaScript -->
    </div>
</div>

<!-- Leyenda poética -->
<div class="legend">
    <div class="legend-title">THE SPECTRUM</div>
    <div class="legend-items">
        <div class="legend-item">
            <div class="legend-color" style="background-color: #ff4757;"></div>
            <div class="legend-label">Pigeon Blood / Visible Exclusion</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #00d2d3;"></div>
            <div class="legend-label">Microbe Glow / Invisible Foundation</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #a4b0be;"></div>
            <div class="legend-label">Pollution Smog / Shared Suffering</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #70a1ff;"></div>
            <div class="legend-label">Urban Breath / What's Taken</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #2ed573;"></div>
            <div class="legend-label">Gut Ecology / Internal Revolutions</div>
        </div>
    </div>
</div>

<!-- Instrucciones poéticas -->
<div class="instructions">
    click what bleeds / click what glows<br>
    zoom into the wound / drag through the fog<br>
    double-click to remember where center is<br>
    (there is no center)
</div>

<script>
    // DATOS POÉTICOS DESORDENADOS
    const nodesData = {
        central: {
            id: "central",
            title: "THE BLOOD & THE GLOW",
            text: "Pigeons bleed red where spikes meet feathers. Microbes glow blue in chemical rivers. One is visible violence, one is invisible foundation. The city breathes through both while pretending not to.",
            category: "VISIBLE/INVISIBLE",
            poem: {
                title: "from the gut of the city",
                text: "pigeon shit on polished marble / microbes dancing in smog / the invisible infrastructure / of everything we call progress"
            },
            points: [
                "One we see but refuse to acknowledge",
                "One we need but work to destroy",
                "Both breathing what we exhale",
                "Both dying what we design"
            ]
        },
        
        // NODOS DE PALOMAS - DESORDENADOS
        pigeons: [
            {
                id: "pigeon-blood",
                title: "BLOOD ON CONCRETE",
                subtitle: "visible violence",
                text: "Red droplets where anti-roosting spikes meet soft underbellies. The city's aesthetic preference written in hemoglobin. Every spike says 'your body is the problem'.",
                category: "VISIBLE EXCLUSION",
                poem: "feathers against steel / the architecture of no / red on gray on gray",
                points: [
                    "Spikes as punctuation in urban grammar",
                    "Blood as evidence of design intention",
                    "The body as unwanted text",
                    "Aesthetic cleansing as violence"
                ],
                x: -800,
                y: -300,
                rotation: -15
            },
            {
                id: "pigeon-breath",
                title: "BREATHING SMOG",
                subtitle: "shared atmosphere",
                text: "Lungs filled with what we exhale: PM2.5, NO₂, the ghost of gasoline. They breathe our progress and cough our pollution. Their respiration our confession.",
                category: "SHARED AIR",
                poem: "inhale the city's exhaust / exhale what's left of sky / we breathe through each other",
                points: [
                    "Shared atmosphere, unequal suffering",
                    "Lungs as pollution collectors",
                    "Every breath a chemical archive",
                    "Their asthma our industrial diary"
                ],
                x: -1200,
                y: 200,
                rotation: 25
            },
            {
                id: "pigeon-gut",
                title: "GUT OF THE CITY",
                subtitle: "internal ecology",
                text: "Stomachs full of our refuse: microplastics, half-eaten burgers, chemical rain. Their gut microbiome maps our consumption patterns. Internal landscapes of external waste.",
                category: "INTERNAL ECOLOGY",
                poem: "plastic in the crop / fast food wrapping as nesting / the city eats itself",
                points: [
                    "Gut as urban archive",
                    "Microbiome as pollution map",
                    "Digestion as material translation",
                    "Internalizing external violence"
                ],
                x: -500,
                y: 800,
                rotation: -30
            }
        ],
        
        // NODOS DE MICROBIOS - DESORDENADOS
        microbes: [
            {
                id: "microbe-glow",
                title: "GLOW IN DARK",
                subtitle: "invisible foundation",
                text: "Bioluminescent reactions to chemical stress. Blue glow where toxins pool. Microbes screaming in light what we ignore in data. The city's unconscious glowing.",
                category: "INVISIBLE INFRASTRUCTURE",
                poem: "blue pulse in drainage / the city's fever dreams / light without witness",
                points: [
                    "Glow as stress signal",
                    "Light without human witness",
                    "Chemical conversations in dark",
                    "Infrastructure that illuminates"
                ],
                x: 900,
                y: -400,
                rotation: 10
            },
            {
                id: "microbe-scream",
                title: "SILENT SCREAM",
                subtitle: "chemical panic",
                text: "Metabolic screams at pH extremes. Enzymatic breakdowns in heavy metal baths. Microbial communities shifting in chemical terror we call 'progress'.",
                category: "CHEMICAL PANIC",
                poem: "enzymes dissolving / in acid rain baptism / silent chemical screams",
                points: [
                    "Metabolism as protest",
                    "Enzymatic breakdown as trauma",
                    "Community collapse as evidence",
                    "Chemical stress as daily liturgy"
                ],
                x: 1300,
                y: 100,
                rotation: -20
            },
            {
                id: "microbe-network",
                title: "INVISIBLE NETWORK",
                subtitle: "urban mycelium",
                text: "Bacterial highways in pavement cracks. Fungal networks under sidewalks. Microbial cities beneath human cities. Infrastructure we build on without seeing.",
                category: "SUBSURFACE INFRASTRUCTURE",
                poem: "roots in concrete / mycelium in pipe dreams / the city beneath",
                points: [
                    "Subsurface communication networks",
                    "Infrastructure of decay and renewal",
                    "Cities built on microbial cities",
                    "The ground as living tissue"
                ],
                x: 700,
                y: 900,
                rotation: 15
            }
        ],
        
        // NODOS DE CONTAMINACIÓN - CAÓTICOS
        pollution: [
            {
                id: "smog-dreams",
                title: "SMOG DREAMS",
                subtitle: "shared delirium",
                text: "PM2.5 particles as shared hallucinations. Heavy metals as collective nervous breakdown. The air thick with what we've forgotten we're breathing.",
                category: "SHARED DELIRIUM",
                poem: "particulate dreams / heavy metal lullabies / we sleep in what we make",
                points: [
                    "Air as chemical soup",
                    "Breathing as involuntary participation",
                    "Pollution as shared subconscious",
                    "Atmosphere as archive of industry"
                ],
                x: -1500,
                y: -800,
                rotation: 40
            },
            {
                id: "chemical-whisper",
                title: "CHEMICAL WHISPER",
                subtitle: "slow violence",
                text: "VOCs whispering through cell membranes. Pesticides in rainfall communion. The slow accumulation of 'not immediately lethal' as permanent damage.",
                category: "SLOW VIOLENCE",
                poem: "rain as poison gift / soil as chemical sponge / slow accumulation of no",
                points: [
                    "Violence measured in decades",
                    "Damage that doesn't bleed",
                    "Toxicity as background radiation",
                    "The emergency that feels normal"
                ],
                x: 1800,
                y: -700,
                rotation: -35
            }
        ],
        
        // NODOS CONCEPTUALES - POÉTICOS
        concepts: [
            {
                id: "invisible-visible",
                title: "INVISIBLE/VISIBLE",
                subtitle: "the dichotomy",
                text: "Pigeons: too visible, therefore excluded. Microbes: invisible, therefore ignored. The city manages life through these twin mechanisms of perception and denial.",
                category: "PERCEPTION POLITICS",
                poem: "see too much: spikes / see nothing: sterilization / the politics of sight",
                points: [
                    "Visibility as liability",
                    "Invisibility as erasure",
                    "The gaze as weapon",
                    "What we choose to see/destroy"
                ],
                x: 0,
                y: -1200,
                rotation: 5
            },
            {
                id: "breath-shared",
                title: "SHARED BREATH",
                subtitle: "atmospheric commons",
                text: "One atmosphere, unequal access. One air, different concentrations of poison. The fiction of separation in shared respiration.",
                category: "ATMOSPHERIC COMMONS",
                poem: "one air / many concentrations of harm / breathing as unequal communion",
                points: [
                    "The myth of separate spaces",
                    "Air as connecting tissue",
                    "Breath as evidence of connection",
                    "Shared atmosphere, unequal risk"
                ],
                x: 100,
                y: 1300,
                rotation: -10
            },
            {
                id: "gut-city",
                title: "GUT AS CITY",
                subtitle: "internal urbanism",
                text: "The pigeon's gut microbiome as mirror of urban consumption. Microbial cities inside animal cities inside human cities. Nested infrastructures of digestion and waste.",
                category: "NESTED INFRASTRUCTURES",
                poem: "city in gut in city / digestion as urban planning / shit as material flow",
                points: [
                    "Internal ecosystems reflecting external",
                    "Digestion as urban metabolism",
                    "Waste as transformed material",
                    "The body as urban scale model"
                ],
                x: -1400,
                y: 1100,
                rotation: 25
            }
        ]
    };

    // Variables globales
    let canvas, ctx;
    let scale = 0.3;
    let offsetX = 0, offsetY = 0;
    let isDragging = false;
    let lastX = 0, lastY = 0;
    let galaxy = document.getElementById('galaxy');
    let viewport = document.getElementById('viewport');

    // Crear estrellas caóticas
    function initStars() {
        const starsContainer = document.getElementById('stars');
        starsContainer.innerHTML = '';
        
        for (let i = 0; i < 600; i++) {
            const star = document.createElement('div');
            star.classList.add('star', `type${Math.floor(Math.random() * 3) + 1}`);
            
            const size = Math.random() * 4 + 0.5;
            star.style.width = `${size}px`;
            star.style.height = `${size}px`;
            star.style.left = `${Math.random() * 100}%`;
            star.style.top = `${Math.random() * 100}%`;
            
            // Propiedades CSS personalizadas
            star.style.setProperty('--duration', `${Math.random() * 7 + 3}s`);
            star.style.setProperty('--delay', `${Math.random() * 5}s`);
            star.style.setProperty('--opacity', `${Math.random() * 0.6 + 0.2}`);
            
            starsContainer.appendChild(star);
        }
    }

    // Crear nodos en posiciones orgánicas
    function createOrganicNodes() {
        // Combinar todos los nodos
        const allNodes = [
            ...nodesData.pigeons,
            ...nodesData.microbes,
            ...nodesData.pollution,
            ...nodesData.concepts
        ];
        
        allNodes.forEach((nodeData, index) => {
            const node = document.createElement('div');
            
            // Clase y forma aleatoria
            const shapeClass = `shape${Math.floor(Math.random() * 6) + 1}`;
            node.classList.add('node', shapeClass);
            
            // Clase de color según tipo
            if (nodeData.category.includes('PIGEON') || nodeData.id.includes('pigeon')) {
                node.classList.add('pigeon-node');
            } else if (nodeData.category.includes('MICROBE') || nodeData.id.includes('microbe')) {
                node.classList.add('microbe-node');
            } else if (nodeData.category.includes('POLLUTION') || nodeData.category.includes('SMOG')) {
                node.classList.add('pollution-node');
            } else if (nodeData.category.includes('BREATH')) {
                node.classList.add('breath-node');
            } else if (nodeData.category.includes('GUT')) {
                node.classList.add('gut-node');
            } else if (nodeData.category.includes('WARNING')) {
                node.classList.add('warning-node');
            } else {
                node.classList.add('invisible-node');
            }
            
            node.id = nodeData.id;
            node.dataset.title = nodeData.title;
            node.dataset.text = nodeData.text;
            node.dataset.category = nodeData.category;
            node.dataset.poem = nodeData.poem;
            node.dataset.points = JSON.stringify(nodeData.points);
            
            // Posición personalizada o aleatoria
            const x = nodeData.x || (Math.random() - 0.5) * 3000;
            const y = nodeData.y || (Math.random() - 0.5) * 3000;
            const rotation = nodeData.rotation || Math.random() * 360;
            
            node.style.left = `calc(50% + ${x}px)`;
            node.style.top = `calc(50% + ${y}px)`;
            node.style.setProperty('--rotation', `${rotation}deg`);
            node.style.setProperty('--float-duration', `${Math.random() * 5 + 3}s`);
            node.style.setProperty('--float-delay', `${Math.random() * 2}s`);
            
            // Tamaño aleatorio
            const size = 150 + Math.random() * 100;
            node.style.width = `${size}px`;
            node.style.height = `${size}px`;
            
            // Icono
            const iconElement = document.createElement('div');
            iconElement.classList.add('node-icon');
            if (nodeData.category.includes('PIGEON')) {
                iconElement.textContent = '🕊️';
            } else if (nodeData.category.includes('MICROBE')) {
                iconElement.textContent = '🦠';
            } else if (nodeData.category.includes('POLLUTION')) {
                iconElement.textContent = '☁️';
            } else if (nodeData.category.includes('BREATH')) {
                iconElement.textContent = '🌬️';
            } else if (nodeData.category.includes('GUT')) {
                iconElement.textContent = '🌀';
            } else {
                iconElement.textContent = ['✨', '⚡', '💫', '🌌'][Math.floor(Math.random() * 4)];
            }
            
            // Título
            const titleElement = document.createElement('div');
            titleElement.classList.add('node-title');
            titleElement.textContent = nodeData.title;
            
            // Subtítulo
            const subtitleElement = document.createElement('div');
            subtitleElement.classList.add('node-subtitle');
            subtitleElement.textContent = nodeData.subtitle || '';
            
            node.appendChild(iconElement);
            node.appendChild(titleElement);
            if (nodeData.subtitle) {
                node.appendChild(subtitleElement);
            }
            
            // Evento click
            node.addEventListener('click', (e) => {
                e.stopPropagation();
                showNodeContent(nodeData);
            });
            
            galaxy.appendChild(node);
        });
        
        // Nodo central
        document.getElementById('centralNode').addEventListener('click', (e) => {
            e.stopPropagation();
            showNodeContent(nodesData.central);
        });
    }

    // Mostrar contenido poético
    function showNodeContent(nodeData) {
        const panel = document.getElementById('contentPanel');
        const panelTitle = document.getElementById('panelTitle');
        const panelText = document.getElementById('panelText');
        const panelCategory = document.getElementById('panelCategory');
        const poemTitle = document.getElementById('poemTitle');
        const poemText = document.getElementById('poemText');
        const panelList = document.getElementById('panelList');
        
        // Actualizar contenido
        panelTitle.textContent = nodeData.title;
        panelText.textContent = nodeData.text;
        panelCategory.textContent = nodeData.category;
        
        // Color según categoría
        let color = '#ff4757';
        if (nodeData.category.includes('MICROBE') || nodeData.id.includes('microbe')) {
            color = '#00d2d3';
        } else if (nodeData.category.includes('POLLUTION') || nodeData.category.includes('SMOG')) {
            color = '#a4b0be';
        } else if (nodeData.category.includes('BREATH')) {
            color = '#70a1ff';
        } else if (nodeData.category.includes('GUT')) {
            color = '#2ed573';
        }
        
        panelCategory.style.background = color;
        
        // Poema
        if (nodeData.poem) {
            document.getElementById('panelPoem').style.display = 'block';
            document.getElementById('panelPoem').style.borderLeftColor = color;
            poemTitle.textContent = typeof nodeData.poem === 'object' ? nodeData.poem.title : 'fragment';
            poemText.textContent = typeof nodeData.poem === 'object' ? nodeData.poem.text : nodeData.poem;
        } else {
            document.getElementById('panelPoem').style.display = 'none';
        }
        
        // Lista de puntos
        panelList.innerHTML = '';
        if (nodeData.points && nodeData.points.length > 0) {
            nodeData.points.forEach(point => {
                const listItem = document.createElement('div');
                listItem.classList.add('panel-list-item');
                listItem.textContent = point;
                listItem.style.color = color;
                panelList.appendChild(listItem);
            });
        }
        
        // Mostrar panel
        panel.classList.add('active');
    }

    // Cerrar panel
    document.getElementById('closePanel').addEventListener('click', () => {
        document.getElementById('contentPanel').classList.remove('active');
    });

    // Inicializar canvas
    function initCanvas() {
        canvas = document.getElementById('galaxy-canvas');
        ctx = canvas.getContext('2d');
        
        function resizeCanvas() {
            canvas.width = galaxy.offsetWidth;
            canvas.height = galaxy.offsetHeight;
            drawOrganicConnections();
        }
        
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();
    }

    // Conexiones orgánicas, no perfectas
    function drawOrganicConnections() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        
        const centerX = canvas.width / 2;
        const centerY = canvas.height / 2;
        
        // Dibujar desde el centro
        const allNodes = document.querySelectorAll('.node:not(.central-node)');
        
        allNodes.forEach(node => {
            const rect = node.getBoundingClientRect();
            const galaxyRect = galaxy.getBoundingClientRect();
            
            const nodeX = (rect.left + rect.width/2 - galaxyRect.left) / scale;
            const nodeY = (rect.top + rect.height/2 - galaxyRect.top) / scale;
            
            // Color según tipo de nodo
            let color = 'rgba(255, 71, 87, 0.1)';
            if (node.classList.contains('microbe-node')) {
                color = 'rgba(0, 210, 211, 0.1)';
            } else if (node.classList.contains('pollution-node')) {
                color = 'rgba(164, 176, 190, 0.08)';
            } else if (node.classList.contains('breath-node')) {
                color = 'rgba(112, 161, 255, 0.1)';
            }
            
            // Línea con variación
            drawWobblyLine(centerX, centerY, nodeX, nodeY, color, 1.2);
        });
        
        // Conexiones entre nodos relacionados
        drawNodeConnections();
    }
    
    function drawWobblyLine(x1, y1, x2, y2, color, width) {
        const segments = 20;
        const variance = 30;
        
        ctx.beginPath();
        ctx.moveTo(x1, y1);
        
        for (let i = 1; i <= segments; i++) {
            const t = i / segments;
            const x = x1 + (x2 - x1) * t + (Math.random() - 0.5) * variance;
            const y = y1 + (y2 - y1) * t + (Math.random() - 0.5) * variance;
            
            ctx.lineTo(x, y);
        }
        
        ctx.lineTo(x2, y2);
        ctx.strokeStyle = color;
        ctx.lineWidth = width;
        ctx.lineCap = 'round';
        ctx.stroke();
    }
    
    function drawNodeConnections() {
        // Conexiones específicas
        const connections = [
            ['pigeon-blood', 'smog-dreams'],
            ['microbe-glow', 'chemical-whisper'],
            ['pigeon-gut', 'gut-city'],
            ['pigeon-breath', 'breath-shared']
        ];
        
        connections.forEach(([fromId, toId]) => {
            const fromNode = document.getElementById(fromId);
            const toNode = document.getElementById(toId);
            
            if (fromNode && toNode) {
                const galaxyRect = galaxy.getBoundingClientRect();
                
                const fromRect = fromNode.getBoundingClientRect();
                const fromX = (fromRect.left + fromRect.width/2 - galaxyRect.left) / scale;
                const fromY = (fromRect.top + fromRect.height/2 - galaxyRect.top) / scale;
                
                const toRect = toNode.getBoundingClientRect();
                const toX = (toRect.left + toRect.width/2 - galaxyRect.left) / scale;
                const toY = (toRect.top + toRect.height/2 - galaxyRect.top) / scale;
                
                // Color según nodo de origen
                let color = 'rgba(255, 255, 255, 0.05)';
                if (fromNode.classList.contains('pigeon-node')) {
                    color = 'rgba(255, 71, 87, 0.15)';
                } else if (fromNode.classList.contains('microbe-node')) {
                    color = 'rgba(0, 210, 211, 0.15)';
                }
                
                drawCurvedConnection(fromX, fromY, toX, toY, color, 1);
            }
        });
    }
    
    function drawCurvedConnection(x1, y1, x2, y2, color, width) {
        const centerX = canvas.width / 2;
        const centerY = canvas.height / 2;
        
        const cp1x = (x1 + centerX) / 2 + (Math.random() - 0.5) * 100;
        const cp1y = (y1 + centerY) / 2 + (Math.random() - 0.5) * 100;
        
        ctx.beginPath();
        ctx.moveTo(x1, y1);
        ctx.quadraticCurveTo(cp1x, cp1y, x2, y2);
        ctx.strokeStyle = color;
        ctx.lineWidth = width;
        ctx.lineCap = 'round';
        ctx.stroke();
    }

    // Actualizar transformación
    function updateTransform() {
        galaxy.style.transform = `translate(calc(-50% + ${offsetX}px), calc(-50% + ${offsetY}px)) scale(${scale}) rotate(${5 * (offsetX / 10000)}deg)`;
        drawOrganicConnections();
    }

    // Zoom orgánico
    function handleWheel(e) {
        e.preventDefault();
        
        const zoomFactor = 0.08;
        const oldScale = scale;
        
        if (e.deltaY < 0) {
            scale = Math.min(scale + zoomFactor, 0.8);
        } else {
            scale = Math.max(scale - zoomFactor, 0.2);
        }
        
        const rect = viewport.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        
        offsetX -= (x - rect.width/2) * (scale - oldScale) / oldScale;
        offsetY -= (y - rect.height/2) * (scale - oldScale) / oldScale;
        
        updateTransform();
    }

    // Arrastre
    function handleMouseDown(e) {
        if (!e.target.closest('.content-panel')) {
            isDragging = true;
            lastX = e.clientX;
            lastY = e.clientY;
            viewport.classList.add('grabbing');
        }
    }

    function handleMouseMove(e) {
        if (!isDragging) return;
        
        offsetX += (e.clientX - lastX);
        offsetY += (e.clientY - lastY);
        lastX = e.clientX;
        lastY = e.clientY;
        
        updateTransform();
    }

    function handleMouseUp() {
        isDragging = false;
        viewport.classList.remove('grabbing');
    }

    // Reset
    function resetView() {
        scale = 0.3;
        offsetX = 0;
        offsetY = 0;
        updateTransform();
    }

    // Inicializar
    document.addEventListener('DOMContentLoaded', () => {
        initStars();
        createOrganicNodes();
        initCanvas();
        updateTransform();
        
        // Mostrar contenido central con retraso
        setTimeout(() => {
            showNodeContent(nodesData.central);
        }, 1000);
        
        // Event listeners
        viewport.addEventListener('wheel', handleWheel);
        viewport.addEventListener('mousedown', handleMouseDown);
        document.addEventListener('mousemove', handleMouseMove);
        document.addEventListener('mouseup', handleMouseUp);
        viewport.addEventListener('dblclick', resetView);
        
        // Cerrar panel al hacer clic fuera
        document.addEventListener('click', (e) => {
            const panel = document.getElementById('contentPanel');
            const isNode = e.target.closest('.node') || e.target.closest('.central-node');
            const isCloseBtn = e.target.closest('.panel-close');
            const isPanel = e.target.closest('.content-panel');
            
            if (!isNode && !isCloseBtn && !isPanel && panel.classList.contains('active')) {
                panel.classList.remove('active');
            }
        });
    });
</script>