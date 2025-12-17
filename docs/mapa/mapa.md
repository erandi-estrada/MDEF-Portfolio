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
    background: #fefaf0 !important;
}

/* ===== MENÚ CON PERSONALIDAD ===== */
.menu-container {
    display: flex !important;
    justify-content: center !important;
    align-items: center !important;
    width: 100% !important;
    margin: 0 !important;
    padding: 1.2rem 0 !important;
    background: linear-gradient(90deg, #f5f0e6 0%, #f0ebe0 100%) !important;
    border-bottom: 3px solid #d4af37 !important;
    position: relative !important;
    z-index: 1000;
    box-shadow: 0 2px 15px rgba(0, 0, 0, 0.05);
}

.custom-header-menu {
    display: flex;
    align-items: center;
    gap: 3.5rem;
    margin: 0;
    padding: 0;
}

.custom-header-menu a {
    color: #2d3748;
    text-decoration: none;
    font-weight: 700;
    font-size: 1.1rem;
    padding: 0.6rem 1.2rem;
    border: 2px solid transparent;
    transition: all 0.4s ease;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    position: relative;
    background: rgba(255, 255, 255, 0.3);
    border-radius: 8px;
}

.custom-header-menu a:hover {
    color: #c0392b;
    border-color: #c0392b;
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(192, 57, 43, 0.15);
    background: rgba(255, 255, 255, 0.5);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --pigeon-color: #3498db;
    --microbe-color: #9b59b6;
    --pollution-color: #7f8c8d;
    --stress-color: #e67e22;
    --breath-color: #16a085;
    --injustice-color: #c0392b;
    --concrete-color: #95a5a6;
    --life-color: #27ae60;
    --bg-light: #fefaf0;
    --bg-lighter: #fffaf5;
    --text-dark: #2c3e50;
    --text-muted: #7f8c8d;
}

body {
    font-family: 'Montserrat', sans-serif;
    background-color: var(--bg-light);
    color: var(--text-dark);
    margin: 0;
    padding: 0;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    position: relative;
}

/* ==== CONTENEDOR PRINCIPAL CON FONDO CLARO ==== */
.main-container {
    flex: 1;
    position: relative;
    overflow: hidden;
    width: 100%;
    height: calc(100vh - 80px);
    background: var(--bg-light);
    background-image: 
        radial-gradient(circle at 20% 30%, rgba(52, 152, 219, 0.03) 0%, transparent 50%),
        radial-gradient(circle at 80% 70%, rgba(155, 89, 182, 0.03) 0%, transparent 50%),
        linear-gradient(45deg, rgba(254, 250, 240, 0.8) 0%, rgba(255, 250, 245, 0.9) 100%);
}

/* PARTÍCULAS FLOTANTES SUTILES */
#particles {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 0;
    pointer-events: none;
}

.particle {
    position: absolute;
    border-radius: 50%;
    opacity: 0.1;
    animation: float 25s infinite linear;
    background: rgba(52, 152, 219, 0.1);
}

@keyframes float {
    0% { transform: translateY(0) translateX(0); }
    25% { transform: translateY(-15px) translateX(8px); }
    50% { transform: translateY(-30px) translateX(0); }
    75% { transform: translateY(-15px) translateX(-8px); }
    100% { transform: translateY(0) translateX(0); }
}

/* Viewport */
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

/* ESPACIO DEL MAPA - ORGÁNICO */
#map-space {
    position: absolute;
    width: 4000px;
    height: 4000px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0.35);
    transform-origin: center center;
    transition: transform 0.15s cubic-bezier(0.4, 0, 0.2, 1);
    will-change: transform;
    background: transparent;
}

/* CANVAS PARA CONEXIONES */
#connections-canvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    opacity: 0.4;
}

/* NODO CENTRAL - FORMA ORGÁNICA SOBRE FONDO CLARO */
.central-node {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 400px;
    height: 400px;
    border-radius: 45% 55% 60% 40% / 50% 45% 55% 50%;
    background: 
        radial-gradient(circle at 30% 30%, rgba(52, 152, 219, 0.9) 0%, transparent 70%),
        radial-gradient(circle at 70% 70%, rgba(155, 89, 182, 0.9) 0%, transparent 70%),
        radial-gradient(circle at 50% 50%, rgba(255, 255, 255, 0.95) 30%, transparent 100%);
    box-shadow: 
        inset 0 0 80px rgba(52, 152, 219, 0.3),
        inset 0 0 80px rgba(155, 89, 182, 0.3),
        0 0 100px rgba(52, 152, 219, 0.4),
        0 0 100px rgba(155, 89, 182, 0.3),
        0 10px 40px rgba(0, 0, 0, 0.1);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    z-index: 10;
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    border: 3px solid rgba(52, 152, 219, 0.2);
    animation: central-pulse 8s ease-in-out infinite;
}

@keyframes central-pulse {
    0%, 100% { 
        transform: translate(-50%, -50%) scale(1);
        border-radius: 45% 55% 60% 40% / 50% 45% 55% 50%;
    }
    33% { 
        transform: translate(-50%, -50%) scale(1.03);
        border-radius: 50% 50% 55% 45% / 45% 55% 45% 55%;
    }
    66% { 
        transform: translate(-50%, -50%) scale(0.98);
        border-radius: 40% 60% 55% 45% / 55% 45% 55% 45%;
    }
}

.central-node:hover {
    transform: translate(-50%, -50%) scale(1.1);
    box-shadow: 
        inset 0 0 120px rgba(52, 152, 219, 0.4),
        inset 0 0 120px rgba(155, 89, 182, 0.4),
        0 0 150px rgba(52, 152, 219, 0.6),
        0 0 150px rgba(155, 89, 182, 0.4),
        0 15px 50px rgba(0, 0, 0, 0.15);
    animation: none;
    border-color: rgba(52, 152, 219, 0.4);
}

.central-node-content {
    text-align: center;
    padding: 50px;
    width: 100%;
}

.central-node-title {
    font-weight: 900;
    font-size: 2.5rem;
    text-transform: uppercase;
    letter-spacing: 3px;
    margin-bottom: 15px;
    color: #2c3e50;
    text-shadow: 
        0 2px 4px rgba(0, 0, 0, 0.1),
        0 0 20px rgba(52, 152, 219, 0.3);
    line-height: 1.1;
}

.central-node-subtitle {
    font-weight: 300;
    font-size: 1.1rem;
    color: rgba(44, 62, 80, 0.8);
    letter-spacing: 2px;
    text-transform: uppercase;
    font-style: italic;
}

/* NODOS - FORMAS VARIADAS SOBRE FONDO CLARO */
.node {
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    z-index: 5;
    overflow: hidden;
    padding: 20px;
    text-align: center;
    border: 2px solid rgba(255, 255, 255, 0.8);
    filter: drop-shadow(0 5px 15px rgba(0, 0, 0, 0.1));
    animation: node-float var(--float-time) ease-in-out infinite;
    background: rgba(255, 255, 255, 0.9);
    backdrop-filter: blur(5px);
}

@keyframes node-float {
    0%, 100% { transform: translate(-50%, -50%) rotate(var(--rotation)) translateY(0); }
    50% { transform: translate(-50%, -50%) rotate(calc(var(--rotation) + 3deg)) translateY(-10px); }
}

/* FORMAS ORGÁNICAS */
.node.shape-a { border-radius: 40% 60% 55% 45% / 45% 40% 60% 55%; }
.node.shape-b { border-radius: 60% 40% 45% 55% / 55% 60% 40% 45%; }
.node.shape-c { border-radius: 50% 50% 40% 60% / 60% 40% 50% 50%; }
.node.shape-d { border-radius: 35% 65% 50% 50% / 50% 35% 65% 50%; }
.node.shape-e { border-radius: 55% 45% 60% 40% / 40% 60% 45% 55%; }

.node-icon {
    font-size: 2.2rem;
    margin-bottom: 12px;
    opacity: 0.9;
    filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.2));
}

.node-title {
    font-weight: 800;
    font-size: 1rem;
    text-transform: uppercase;
    letter-spacing: 1.2px;
    color: #2c3e50;
    line-height: 1.3;
    width: 100%;
    word-wrap: break-word;
}

.node-subtitle {
    font-size: 0.75rem;
    color: rgba(44, 62, 80, 0.7);
    margin-top: 6px;
    font-weight: 400;
    font-style: italic;
}

/* COLORES DE NODOS - CON FONDO BLANCO SEMITRANSPARENTE */
.pigeon-node {
    background: 
        radial-gradient(circle at 30% 30%, 
            rgba(52, 152, 219, 0.9) 0%,
            rgba(52, 152, 219, 0.6) 40%,
            rgba(255, 255, 255, 0.9) 80%);
    box-shadow: 
        inset 0 0 40px rgba(52, 152, 219, 0.2),
        0 0 60px rgba(52, 152, 219, 0.3),
        0 8px 25px rgba(0, 0, 0, 0.1);
    border-color: rgba(52, 152, 219, 0.4);
}

.microbe-node {
    background: 
        radial-gradient(circle at 70% 30%, 
            rgba(155, 89, 182, 0.9) 0%,
            rgba(155, 89, 182, 0.6) 40%,
            rgba(255, 255, 255, 0.9) 80%);
    box-shadow: 
        inset 0 0 40px rgba(155, 89, 182, 0.2),
        0 0 60px rgba(155, 89, 182, 0.3),
        0 8px 25px rgba(0, 0, 0, 0.1);
    border-color: rgba(155, 89, 182, 0.4);
}

.pollution-node {
    background: 
        radial-gradient(circle at 50% 50%, 
            rgba(127, 140, 141, 0.8) 0%,
            rgba(149, 165, 166, 0.5) 40%,
            rgba(255, 255, 255, 0.9) 80%);
    box-shadow: 
        inset 0 0 40px rgba(149, 165, 166, 0.15),
        0 0 60px rgba(149, 165, 166, 0.2),
        0 8px 25px rgba(0, 0, 0, 0.1);
    border-color: rgba(149, 165, 166, 0.3);
}

.stress-node {
    background: 
        radial-gradient(circle at 20% 80%, 
            rgba(230, 126, 34, 0.9) 0%,
            rgba(230, 126, 34, 0.6) 40%,
            rgba(255, 255, 255, 0.9) 80%);
    box-shadow: 
        inset 0 0 40px rgba(230, 126, 34, 0.2),
        0 0 60px rgba(230, 126, 34, 0.3),
        0 8px 25px rgba(0, 0, 0, 0.1);
    border-color: rgba(230, 126, 34, 0.3);
}

.breath-node {
    background: 
        radial-gradient(circle at 80% 20%, 
            rgba(22, 160, 133, 0.9) 0%,
            rgba(22, 160, 133, 0.6) 40%,
            rgba(255, 255, 255, 0.9) 80%);
    box-shadow: 
        inset 0 0 40px rgba(22, 160, 133, 0.2),
        0 0 60px rgba(22, 160, 133, 0.3),
        0 8px 25px rgba(0, 0, 0, 0.1);
    border-color: rgba(22, 160, 133, 0.3);
}

.injustice-node {
    background: 
        radial-gradient(circle at 50% 20%, 
            rgba(192, 57, 43, 0.9) 0%,
            rgba(192, 57, 43, 0.6) 40%,
            rgba(255, 255, 255, 0.9) 80%);
    box-shadow: 
        inset 0 0 40px rgba(192, 57, 43, 0.2),
        0 0 60px rgba(192, 57, 43, 0.3),
        0 8px 25px rgba(0, 0, 0, 0.1);
    border-color: rgba(192, 57, 43, 0.3);
}

.life-node {
    background: 
        radial-gradient(circle at 20% 50%, 
            rgba(39, 174, 96, 0.9) 0%,
            rgba(39, 174, 96, 0.6) 40%,
            rgba(255, 255, 255, 0.9) 80%);
    box-shadow: 
        inset 0 0 40px rgba(39, 174, 96, 0.2),
        0 0 60px rgba(39, 174, 96, 0.3),
        0 8px 25px rgba(0, 0, 0, 0.1);
    border-color: rgba(39, 174, 96, 0.3);
}

/* EFECTO HOVER */
.node:hover {
    transform: scale(1.25) translate(-50%, -50%) rotate(calc(var(--rotation) + 15deg)) !important;
    z-index: 20;
    box-shadow: 
        0 0 80px currentColor,
        inset 0 0 50px rgba(255, 255, 255, 0.3),
        0 15px 40px rgba(0, 0, 0, 0.2);
    border-color: rgba(255, 255, 255, 0.6);
    animation: none !important;
    filter: drop-shadow(0 0 25px currentColor) brightness(1.1);
    background: rgba(255, 255, 255, 0.95);
}

/* PANEL DE CONTENIDO - SOBRE FONDO CLARO */
.content-panel {
    position: fixed;
    top: 100px;
    right: 20px;
    width: 480px;
    max-height: 80vh;
    overflow-y: auto;
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(20px);
    border-radius: 12px;
    padding: 35px;
    box-shadow: 
        0 25px 50px rgba(0, 0, 0, 0.15),
        inset 0 1px 0 rgba(255, 255, 255, 0.8);
    border: 1px solid rgba(0, 0, 0, 0.08);
    z-index: 1000;
    display: none;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.content-panel.active {
    display: block;
    animation: panelSlide 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

@keyframes panelSlide {
    from { 
        opacity: 0;
        transform: translateX(30px) scale(0.95);
    }
    to { 
        opacity: 1;
        transform: translateX(0) scale(1);
    }
}

.panel-category {
    display: inline-block;
    font-size: 0.8rem;
    padding: 8px 22px;
    border-radius: 20px;
    margin-bottom: 25px;
    font-weight: 800;
    color: #ffffff;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    background: var(--node-color);
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.panel-title {
    font-size: 1.9rem;
    font-weight: 800;
    margin-bottom: 20px;
    color: #2c3e50;
    line-height: 1.2;
    text-transform: uppercase;
    letter-spacing: 1.5px;
}

.panel-text {
    font-size: 1.05rem;
    line-height: 1.7;
    color: var(--text-muted);
    margin-bottom: 25px;
    font-weight: 400;
}

.panel-concept {
    background: rgba(52, 152, 219, 0.05);
    border-left: 4px solid var(--node-color);
    padding: 20px;
    margin: 25px 0;
    border-radius: 0 8px 8px 0;
}

.panel-concept-title {
    font-size: 0.9rem;
    font-weight: 700;
    margin-bottom: 12px;
    text-transform: uppercase;
    letter-spacing: 1.2px;
    color: var(--text-dark);
}

.panel-list {
    margin: 20px 0;
    padding-left: 20px;
}

.panel-list-item {
    font-size: 0.95rem;
    color: var(--text-muted);
    margin-bottom: 10px;
    line-height: 1.6;
    position: relative;
    padding-left: 25px;
}

.panel-list-item:before {
    content: '→';
    color: var(--node-color);
    position: absolute;
    left: 0;
    font-weight: bold;
}

.panel-close {
    position: absolute;
    top: 20px;
    right: 20px;
    background: rgba(44, 62, 80, 0.1);
    border: none;
    color: var(--text-muted);
    font-size: 1.8rem;
    cursor: pointer;
    transition: all 0.3s;
    width: 42px;
    height: 42px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1001;
}

.panel-close:hover {
    background: rgba(44, 62, 80, 0.2);
    color: var(--text-dark);
    transform: rotate(90deg);
}

/* LEYENDA SOBRE FONDO CLARO */
.legend {
    position: fixed;
    bottom: 20px;
    left: 20px;
    background: rgba(255, 255, 255, 0.9);
    backdrop-filter: blur(10px);
    padding: 20px;
    border-radius: 10px;
    border: 1px solid rgba(0, 0, 0, 0.08);
    z-index: 1000;
    max-width: 280px;
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
}

.legend-title {
    font-size: 0.9rem;
    font-weight: 800;
    margin-bottom: 15px;
    color: #2c3e50;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    padding-bottom: 10px;
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
}

.legend-color {
    width: 14px;
    height: 14px;
    border-radius: 50%;
    flex-shrink: 0;
    box-shadow: 0 0 10px currentColor;
}

.legend-label {
    font-size: 0.82rem;
    color: rgba(44, 62, 80, 0.8);
    line-height: 1.3;
}

/* INSTRUCCIONES */
.instructions {
    position: fixed;
    bottom: 20px;
    right: 20px;
    text-align: right;
    font-size: 0.85rem;
    color: rgba(44, 62, 80, 0.6);
    z-index: 1000;
    background: rgba(255, 255, 255, 0.8);
    padding: 12px 18px;
    border-radius: 10px;
    border: 1px solid rgba(0, 0, 0, 0.08);
    max-width: 260px;
    backdrop-filter: blur(5px);
    line-height: 1.5;
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
}

/* RESPONSIVE */
@media (max-width: 1200px) {
    #map-space {
        width: 3500px;
        height: 3500px;
    }
    
    .central-node {
        width: 350px;
        height: 350px;
    }
    
    .node {
        width: 170px;
        height: 170px;
    }
    
    .content-panel {
        width: 420px;
    }
}

@media (max-width: 900px) {
    #map-space {
        width: 3000px;
        height: 3000px;
        transform: translate(-50%, -50%) scale(0.3);
    }
    
    .central-node {
        width: 300px;
        height: 300px;
    }
    
    .node {
        width: 150px;
        height: 150px;
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
        height: calc(100vh - 70px);
    }
    
    .menu-container {
        padding: 1rem 0;
    }
    
    .custom-header-menu {
        gap: 1.5rem;
    }
    
    .custom-header-menu a {
        font-size: 0.9rem;
        padding: 0.5rem 0.8rem;
    }
    
    .content-panel {
        left: 10px;
        right: 10px;
        max-width: none;
        top: 85px;
        padding: 25px;
    }
    
    .central-node {
        width: 250px;
        height: 250px;
    }
    
    .node {
        width: 130px;
        height: 130px;
    }
    
    .central-node-title {
        font-size: 1.8rem;
    }
    
    .node-title {
        font-size: 0.9rem;
    }
}
</style>

<!-- MENÚ -->
<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">PROJECTS</a>
        <a href="../../about/me">ABOUT</a>
    </div>
</div>

<!-- CONTENEDOR PRINCIPAL -->
<div class="main-container">
    <div id="particles"></div>
    
    <!-- Viewport -->
    <div class="viewport" id="viewport">
        <div id="map-space">
            <canvas id="connections-canvas"></canvas>
            
            <!-- Nodo central orgánico -->
            <div class="central-node" id="centralNode">
                <div class="central-node-content">
                    <div class="central-node-title">INFRASTRUCTURE OF URBAN NON-HUMAN LIFE</div>
                    <div class="central-node-subtitle">Pigeons & Urban Microorganisms</div>
                </div>
            </div>
            
            <!-- Nodos serán generados -->
        </div>
    </div>
</div>

<!-- Panel de contenido -->
<div class="content-panel" id="contentPanel">
    <button class="panel-close" id="closePanel">×</button>
    <div class="panel-category" id="panelCategory">VISIBLE/INVISIBLE</div>
    <h2 class="panel-title" id="panelTitle">THE URBAN DICHOTOMY</h2>
    <p class="panel-text" id="panelText">How cities manage life through perception: what's visible gets excluded, what's invisible gets ignored. Pigeons represent the violence of visibility, microorganisms represent the erasure of invisibility.</p>
    
    <div class="panel-concept" id="panelConcept">
        <div class="panel-concept-title" id="conceptTitle">CORE IDEA</div>
        <p id="conceptText">Both species experience urban violence, but through different mechanisms: one through spikes and noise, the other through chemicals and sterilization. Together, they map the full spectrum of urban exclusion.</p>
    </div>
    
    <div class="panel-list" id="panelList">
        <!-- List items serán poblados -->
    </div>
</div>

<!-- Leyenda -->
<div class="legend">
    <div class="legend-title">MAP KEY</div>
    <div class="legend-items">
        <div class="legend-item">
            <div class="legend-color" style="background-color: #3498db;"></div>
            <div class="legend-label">Pigeons / Visible Exclusion</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #9b59b6;"></div>
            <div class="legend-label">Microorganisms / Invisible Foundation</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #7f8c8d;"></div>
            <div class="legend-label">Pollution / Shared Burden</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #e67e22;"></div>
            <div class="legend-label">Stress / Biological Response</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #16a085;"></div>
            <div class="legend-label">Breath / Atmospheric Commons</div>
        </div>
    </div>
</div>

<!-- Instrucciones -->
<div class="instructions">
    Click nodes to explore connections<br>
    Scroll to zoom in/out<br>
    Drag to navigate the map<br>
    Double-click to reset view
</div>

<script>
    // DATOS ORGÁNICOS
    const nodesData = {
        central: {
            id: "central",
            title: "THE URBAN DICHOTOMY",
            text: "Cities manage non-human life through twin mechanisms: visible exclusion (spikes, noise, removal) and invisible erasure (chemicals, sterilization, ignorance). Pigeons experience the violence of being seen, microorganisms suffer the violence of being unseen.",
            category: "VISIBLE/INVISIBLE",
            concept: {
                title: "PERCEPTION AS VIOLENCE",
                text: "What we choose to see determines how we exclude. What we choose to ignore determines what we destroy. Urban design is an exercise in selective perception."
            },
            points: [
                "Visibility leads to direct violence",
                "Invisibility leads to systemic neglect",
                "Both are forms of urban management",
                "Both reveal human priorities"
            ]
        },
        
        // NODOS DE PALOMAS
        pigeons: [
            {
                id: "pigeon-body",
                title: "THE BODY IN SPACE",
                subtitle: "visible presence",
                text: "Pigeon bodies occupy space in ways deemed unacceptable. Their resting, nesting, feeding—all become transgressions. The urban response: spikes, nets, repellents. Architecture that says 'your body is the problem'.",
                category: "VISIBLE EXCLUSION",
                concept: "The politics of resting",
                points: [
                    "Resting as political act",
                    "Body as unwanted architecture",
                    "Design against presence",
                    "The violence of 'no place'"
                ],
                x: -1000,
                y: -200,
                size: 180
            },
            {
                id: "pigeon-lungs",
                title: "SHARED ATMOSPHERE",
                subtitle: "breathing together",
                text: "Pigeons breathe what we exhale: PM2.5, NO₂, ozone. Their respiratory systems become archives of urban pollution. Each breath a record of industrial progress and environmental cost.",
                category: "ATMOSPHERIC COMMONS",
                concept: "Breath as connection",
                points: [
                    "One air, unequal effects",
                    "Lungs as pollution sensors",
                    "Respiration as shared fate",
                    "The fiction of separation"
                ],
                x: -1400,
                y: 300,
                size: 200
            },
            {
                id: "pigeon-gut",
                title: "INTERNAL CITY",
                subtitle: "gut as urban archive",
                text: "Pigeon digestive systems contain microplastics, chemical residues, human food waste. Their gut microbiome maps our consumption patterns and waste management failures.",
                category: "INTERNAL ECOLOGIES",
                concept: "Digestion as translation",
                points: [
                    "Gut as material archive",
                    "Microbiome as urban map",
                    "Consumption made visible",
                    "Waste internalized"
                ],
                x: -800,
                y: 1000,
                size: 190
            }
        ],
        
        // NODOS DE MICROORGANISMOS
        microbes: [
            {
                id: "microbe-invisible",
                title: "INVISIBLE INFRASTRUCTURE",
                subtitle: "unseen foundation",
                text: "Microorganisms perform essential urban functions: nutrient cycling, soil regeneration, pollution breakdown. Their work is invisible, their existence ignored until something goes wrong.",
                category: "INVISIBLE LABOR",
                concept: "Work without witness",
                points: [
                    "Essential but unseen",
                    "Labor without recognition",
                    "Foundation of urban ecosystems",
                    "Ignored until collapse"
                ],
                x: 1100,
                y: -300,
                size: 195
            },
            {
                id: "microbe-chemical",
                title: "CHEMICAL CONVERSATIONS",
                subtitle: "silent communication",
                text: "Microbes communicate through chemical signals disrupted by pollution. Heavy metals, VOCs, pH changes—all distort their language, their communities, their survival.",
                category: "CHEMICAL STRESS",
                concept: "Pollution as noise",
                points: [
                    "Chemical language disrupted",
                    "Signals drowned in toxins",
                    "Community collapse",
                    "Silent chemical violence"
                ],
                x: 1500,
                y: 150,
                size: 185
            },
            {
                id: "microbe-network",
                title: "SUBSURFACE NETWORKS",
                subtitle: "cities beneath",
                text: "Bacterial highways in pavement cracks, fungal networks under sidewalks, microbial communities in building materials. An entire urban ecosystem operating beneath human perception.",
                category: "SUBSURFACE SYSTEMS",
                concept: "The city below",
                points: [
                    "Infrastructure on infrastructure",
                    "Networks beneath networks",
                    "Ecosystems within ecosystems",
                    "Life in the cracks"
                ],
                x: 900,
                y: 1100,
                size: 205
            }
        ],
        
        // NODOS DE PRESIÓN/CONTAMINACIÓN
        pressures: [
            {
                id: "air-toxicity",
                title: "ATMOSPHERIC LOAD",
                subtitle: "shared burden",
                text: "Particulate matter affects pigeons' respiratory systems while traveling on microbes. Heavy metals accumulate in tissues while altering microbial metabolism. One pollution, multiple damages.",
                category: "SHARED STRESSOR",
                concept: "Pollution's many faces",
                points: [
                    "Same source, different effects",
                    "Cross-species contamination",
                    "Atmospheric violence",
                    "Shared but unequal suffering"
                ],
                x: -1600,
                y: -700,
                size: 175
            },
            {
                id: "noise-pressure",
                title: "ACOUSTIC STRESS",
                subtitle: "sound as violence",
                text: "Chronic noise disrupts pigeon communication, increases stress hormones, alters behavior. While microbes don't 'hear', the noise ecosystem affects their habitats and predators.",
                category: "SENSORY POLLUTION",
                concept: "The violence of sound",
                points: [
                    "Communication disrupted",
                    "Stress made audible",
                    "Sensory overload",
                    "The sound of exclusion"
                ],
                x: 1800,
                y: -600,
                size: 180
            },
            {
                id: "thermal-stress",
                title: "HEAT ISLAND EFFECT",
                subtitle: "temperature as weapon",
                text: "Urban heat islands increase temperatures, reducing microbial diversity while stressing pigeon thermoregulation. Concrete absorbs heat, radiates violence.",
                category: "THERMAL STRESS",
                concept: "Heat as design failure",
                points: [
                    "Temperature as exclusion",
                    "Concrete as heat battery",
                    "Thermal stress across scales",
                    "Design that overheats life"
                ],
                x: 0,
                y: -1300,
                size: 190
            }
        ],
        
        // NODOS CONCEPTUALES
        concepts: [
            {
                id: "visible-invisible",
                title: "VISIBLE/INVISIBLE",
                subtitle: "the perception spectrum",
                text: "Pigeons are too visible, therefore excluded. Microbes are invisible, therefore ignored. The city manages life through these complementary mechanisms of perception politics.",
                category: "PERCEPTION POLITICS",
                concept: "Seeing and not-seeing",
                points: [
                    "Visibility as liability",
                    "Invisibility as erasure",
                    "The politics of attention",
                    "How perception determines value"
                ],
                x: 200,
                y: 1400,
                size: 210
            },
            {
                id: "scale-connection",
                title: "SCALE CONNECTIONS",
                subtitle: "micro to macro",
                text: "Microbial shifts affect air quality affects pigeon health affects urban ecosystems. Changes at microscopic scales cascade through visible systems. Everything is connected through material flows.",
                category: "SYSTEMIC CONNECTIONS",
                concept: "Everything is connected",
                points: [
                    "Micro changes macro effects",
                    "Cascading consequences",
                    "Material flows connect all",
                    "No scale is isolated"
                ],
                x: -1300,
                y: 1200,
                size: 185
            },
            {
                id: "design-intervention",
                title: "WHERE TO INTERVENE",
                subtitle: "design opportunities",
                text: "Potential points for intervention: creating multispecies habitats, designing pollution translation tools, developing sensory interfaces, rethinking hostile architecture, acknowledging invisible labor.",
                category: "DESIGN POTENTIAL",
                concept: "From mapping to making",
                points: [
                    "Multispecies co-design",
                    "Making invisible visible",
                    "Translating pollution",
                    "Designing with, not against"
                ],
                x: 1400,
                y: 800,
                size: 200
            }
        ]
    };

    // Variables globales
    let canvas, ctx;
    let scale = 0.35;
    let offsetX = 0, offsetY = 0;
    let isDragging = false;
    let lastX = 0, lastY = 0;
    let mapSpace = document.getElementById('map-space');
    let viewport = document.getElementById('viewport');

    // Crear partículas sutiles
    function initParticles() {
        const particlesContainer = document.getElementById('particles');
        particlesContainer.innerHTML = '';
        
        for (let i = 0; i < 60; i++) {
            const particle = document.createElement('div');
            particle.classList.add('particle');
            
            // Colores sutiles
            const colors = [
                'rgba(52, 152, 219, 0.08)',   // azul paloma
                'rgba(155, 89, 182, 0.08)',   // púrpura microbe
                'rgba(127, 140, 141, 0.06)',  // gris contaminación
                'rgba(230, 126, 34, 0.06)',   // naranja estrés
                'rgba(22, 160, 133, 0.06)'    // verde/turquesa
            ];
            
            const size = Math.random() * 5 + 1;
            particle.style.width = `${size}px`;
            particle.style.height = `${size}px`;
            particle.style.left = `${Math.random() * 100}%`;
            particle.style.top = `${Math.random() * 100}%`;
            particle.style.background = colors[Math.floor(Math.random() * colors.length)];
            particle.style.animationDuration = `${Math.random() * 25 + 20}s`;
            particle.style.animationDelay = `${Math.random() * 5}s`;
            
            particlesContainer.appendChild(particle);
        }
    }

    // Crear nodos orgánicos
    function createOrganicNodes() {
        const allNodes = [
            ...nodesData.pigeons,
            ...nodesData.microbes,
            ...nodesData.pressures,
            ...nodesData.concepts
        ];
        
        const shapeClasses = ['shape-a', 'shape-b', 'shape-c', 'shape-d', 'shape-e'];
        
        allNodes.forEach((nodeData, index) => {
            const node = document.createElement('div');
            
            // Forma aleatoria
            const shapeClass = shapeClasses[Math.floor(Math.random() * shapeClasses.length)];
            node.classList.add('node', shapeClass);
            
            // Clase de color
            if (nodeData.category.includes('PIGEON') || nodeData.id.includes('pigeon')) {
                node.classList.add('pigeon-node');
            } else if (nodeData.category.includes('MICROBE') || nodeData.id.includes('microbe')) {
                node.classList.add('microbe-node');
            } else if (nodeData.category.includes('POLLUTION') || nodeData.category.includes('STRESS')) {
                if (nodeData.title.includes('AIR') || nodeData.title.includes('ATMOSPHERIC')) {
                    node.classList.add('pollution-node');
                } else if (nodeData.title.includes('NOISE') || nodeData.title.includes('THERMAL')) {
                    node.classList.add('stress-node');
                } else {
                    node.classList.add('pollution-node');
                }
            } else if (nodeData.category.includes('BREATH') || nodeData.category.includes('ATMOSPHERIC')) {
                node.classList.add('breath-node');
            } else if (nodeData.category.includes('INJUSTICE') || nodeData.category.includes('POLITICS')) {
                node.classList.add('injustice-node');
            } else if (nodeData.category.includes('DESIGN')) {
                node.classList.add('life-node');
            } else {
                node.classList.add('pigeon-node');
            }
            
            node.id = nodeData.id;
            node.dataset.title = nodeData.title;
            node.dataset.text = nodeData.text;
            node.dataset.category = nodeData.category;
            node.dataset.concept = nodeData.concept;
            node.dataset.points = JSON.stringify(nodeData.points);
            
            // Posición y propiedades
            const x = nodeData.x || (Math.random() - 0.5) * 2500;
            const y = nodeData.y || (Math.random() - 0.5) * 2500;
            const rotation = (Math.random() - 0.5) * 30;
            
            node.style.left = `calc(50% + ${x}px)`;
            node.style.top = `calc(50% + ${y}px)`;
            node.style.setProperty('--rotation', `${rotation}deg`);
            node.style.setProperty('--float-time', `${Math.random() * 4 + 5}s`);
            
            // Tamaño
            const size = nodeData.size || (160 + Math.random() * 60);
            node.style.width = `${size}px`;
            node.style.height = `${size}px`;
            
            // Icono
            const iconElement = document.createElement('div');
            iconElement.classList.add('node-icon');
            
            // Iconos según categoría
            if (nodeData.category.includes('PIGEON')) {
                iconElement.textContent = ['🕊️', '🏙️', '👁️'][Math.floor(Math.random() * 3)];
            } else if (nodeData.category.includes('MICROBE')) {
                iconElement.textContent = ['🦠', '🔬', '🌀'][Math.floor(Math.random() * 3)];
            } else if (nodeData.category.includes('POLLUTION')) {
                iconElement.textContent = ['☁️', '⚗️', '⚠️'][Math.floor(Math.random() * 3)];
            } else if (nodeData.category.includes('STRESS')) {
                iconElement.textContent = ['💥', '🔥', '📈'][Math.floor(Math.random() * 3)];
            } else {
                iconElement.textContent = ['💡', '🔗', '⚡'][Math.floor(Math.random() * 3)];
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
            
            mapSpace.appendChild(node);
        });
        
        // Nodo central
        document.getElementById('centralNode').addEventListener('click', (e) => {
            e.stopPropagation();
            showNodeContent(nodesData.central);
        });
    }

    // Mostrar contenido
    function showNodeContent(nodeData) {
        const panel = document.getElementById('contentPanel');
        const panelTitle = document.getElementById('panelTitle');
        const panelText = document.getElementById('panelText');
        const panelCategory = document.getElementById('panelCategory');
        const conceptTitle = document.getElementById('conceptTitle');
        const conceptText = document.getElementById('conceptText');
        const panelList = document.getElementById('panelList');
        
        // Actualizar contenido
        panelTitle.textContent = nodeData.title;
        panelText.textContent = nodeData.text;
        panelCategory.textContent = nodeData.category;
        
        // Color según categoría
        let color = '#3498db'; // default pigeon blue
        if (nodeData.category.includes('MICROBE')) {
            color = '#9b59b6';
        } else if (nodeData.category.includes('POLLUTION') || nodeData.category.includes('STRESS')) {
            color = '#7f8c8d';
        } else if (nodeData.category.includes('ATMOSPHERIC') || nodeData.category.includes('BREATH')) {
            color = '#16a085';
        } else if (nodeData.category.includes('INJUSTICE') || nodeData.category.includes('POLITICS')) {
            color = '#c0392b';
        } else if (nodeData.category.includes('DESIGN')) {
            color = '#27ae60';
        }
        
        // Aplicar color
        panel.style.setProperty('--node-color', color);
        document.getElementById('panelCategory').style.background = color;
        document.getElementById('panelConcept').style.borderLeftColor = color;
        
        // Actualizar concepto
        if (nodeData.concept) {
            document.getElementById('panelConcept').style.display = 'block';
            conceptTitle.textContent = typeof nodeData.concept === 'object' ? nodeData.concept.title : 'KEY IDEA';
            conceptText.textContent = typeof nodeData.concept === 'object' ? nodeData.concept.text : nodeData.concept;
        } else {
            document.getElementById('panelConcept').style.display = 'none';
        }
        
        // Lista de puntos
        panelList.innerHTML = '';
        if (nodeData.points && nodeData.points.length > 0) {
            nodeData.points.forEach(point => {
                const listItem = document.createElement('div');
                listItem.classList.add('panel-list-item');
                listItem.textContent = point;
                listItem.style.setProperty('--node-color', color);
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
        canvas = document.getElementById('connections-canvas');
        ctx = canvas.getContext('2d');
        
        function resizeCanvas() {
            canvas.width = mapSpace.offsetWidth;
            canvas.height = mapSpace.offsetHeight;
            drawOrganicConnections();
        }
        
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();
    }

    // Conexiones orgánicas sutiles
    function drawOrganicConnections() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        
        const centerX = canvas.width / 2;
        const centerY = canvas.height / 2;
        
        // Conexiones desde el centro
        const allNodes = document.querySelectorAll('.node:not(.central-node)');
        
        allNodes.forEach(node => {
            const rect = node.getBoundingClientRect();
            const spaceRect = mapSpace.getBoundingClientRect();
            
            const nodeX = (rect.left + rect.width/2 - spaceRect.left) / scale;
            const nodeY = (rect.top + rect.height/2 - spaceRect.top) / scale;
            
            // Color según tipo de nodo
            let color = 'rgba(52, 152, 219, 0.1)';
            let width = 1.3;
            
            if (node.classList.contains('microbe-node')) {
                color = 'rgba(155, 89, 182, 0.1)';
                width = 1.2;
            } else if (node.classList.contains('pollution-node')) {
                color = 'rgba(127, 140, 141, 0.08)';
                width = 1.0;
            } else if (node.classList.contains('stress-node')) {
                color = 'rgba(230, 126, 34, 0.08)';
                width = 1.1;
            } else if (node.classList.contains('breath-node')) {
                color = 'rgba(22, 160, 133, 0.08)';
                width = 1.2;
            }
            
            // Dibujar línea al centro
            drawConnectionToCenter(centerX, centerY, nodeX, nodeY, color, width);
        });
        
        // Conexiones específicas
        drawSpecificConnections();
    }
    
    function drawConnectionToCenter(x1, y1, x2, y2, color, width) {
        ctx.beginPath();
        ctx.moveTo(x1, y1);
        
        // Línea con ligera curva
        const cpX = (x1 + x2) / 2 + (Math.random() - 0.5) * 80;
        const cpY = (y1 + y2) / 2 + (Math.random() - 0.5) * 80;
        
        ctx.quadraticCurveTo(cpX, cpY, x2, y2);
        ctx.strokeStyle = color;
        ctx.lineWidth = width;
        ctx.lineCap = 'round';
        ctx.stroke();
    }
    
    function drawSpecificConnections() {
        // Conexiones importantes
        const connections = [
            { from: 'pigeon-body', to: 'visible-invisible', color: 'rgba(52, 152, 219, 0.15)', width: 1.6 },
            { from: 'microbe-invisible', to: 'visible-invisible', color: 'rgba(155, 89, 182, 0.15)', width: 1.6 },
            { from: 'air-toxicity', to: 'pigeon-lungs', color: 'rgba(127, 140, 141, 0.12)', width: 1.4 },
            { from: 'air-toxicity', to: 'microbe-chemical', color: 'rgba(127, 140, 141, 0.12)', width: 1.4 },
            { from: 'pigeon-gut', to: 'scale-connection', color: 'rgba(52, 152, 219, 0.14)', width: 1.5 },
            { from: 'microbe-network', to: 'scale-connection', color: 'rgba(155, 89, 182, 0.14)', width: 1.5 }
        ];
        
        connections.forEach(conn => {
            const fromNode = document.getElementById(conn.from);
            const toNode = document.getElementById(conn.to);
            
            if (fromNode && toNode) {
                const spaceRect = mapSpace.getBoundingClientRect();
                
                const fromRect = fromNode.getBoundingClientRect();
                const fromX = (fromRect.left + fromRect.width/2 - spaceRect.left) / scale;
                const fromY = (fromRect.top + fromRect.height/2 - spaceRect.top) / scale;
                
                const toRect = toNode.getBoundingClientRect();
                const toX = (toRect.left + toRect.width/2 - spaceRect.left) / scale;
                const toY = (toRect.top + toRect.height/2 - spaceRect.top) / scale;
                
                // Línea curva
                ctx.beginPath();
                ctx.moveTo(fromX, fromY);
                
                const cp1x = (fromX + toX) / 2 + (Math.random() - 0.5) * 150;
                const cp1y = (fromY + toY) / 2 + (Math.random() - 0.5) * 150;
                
                ctx.quadraticCurveTo(cp1x, cp1y, toX, toY);
                ctx.strokeStyle = conn.color;
                ctx.lineWidth = conn.width;
                ctx.lineCap = 'round';
                ctx.stroke();
            }
        });
    }

    // Actualizar transformación
    function updateTransform() {
        mapSpace.style.transform = `translate(calc(-50% + ${offsetX}px), calc(-50% + ${offsetY}px)) scale(${scale})`;
        drawOrganicConnections();
    }

    // Zoom
    function handleWheel(e) {
        e.preventDefault();
        
        const zoomFactor = 0.07;
        const oldScale = scale;
        
        if (e.deltaY < 0) {
            scale = Math.min(scale + zoomFactor, 0.8);
        } else {
            scale = Math.max(scale - zoomFactor, 0.25);
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
        scale = 0.35;
        offsetX = 0;
        offsetY = 0;
        updateTransform();
    }

    // Inicializar
    document.addEventListener('DOMContentLoaded', () => {
        initParticles();
        createOrganicNodes();
        initCanvas();
        updateTransform();
        
        // Mostrar contenido central
        setTimeout(() => {
            showNodeContent(nodesData.central);
        }, 800);
        
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