<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<!-- =============================================== -->
<!-- MAPA CONSTELACIÓN - VERSIÓN ELEGANTE CORREGIDA -->
<!-- =============================================== -->

<style>
    /* ESTÉTICA GLOBAL - FONDO ESPACIAL LIMPIO */
    :root {
        /* Paleta cósmica refinada */
        --space-black: #050509;
        --core-gradient: linear-gradient(135deg, #1C64F2 0%, #FFDD00 100%);
        --magenta-intuition: #B51EFF;
        --violet-injustice: #8A3FFC;
        --amber-hostility: #FF9F1C;
        --pollen-yellow: #FFDD00;
        --eco-green: #00C49A;
        --toxicity-red: #E11D48;
        --data-blue: #1C64F2;
        --fog-white: #F2F2F2;
        --emergent-blue: #00D4FF;
        
        /* Tamaños de órbitas - AUMENTADOS 35% */
        --orbit-intuitions: 220px;    /* +37.5% */
        --orbit-questions: 380px;     /* +35.7% */
        --orbit-themes: 560px;        /* +33.3% */
        --orbit-actions: 760px;       /* +31.0% */
        --orbit-futures: 1000px;      /* +31.6% */
    }
    
    @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&display=swap');
    
    /* CONTENEDOR PRINCIPAL - FONDO ELEGANTE */
    .galaxy-constellation {
        position: relative;
        width: 100%;
        height: 140vh;
        min-height: 1200px;
        background: var(--space-black);
        overflow: hidden;
        border-radius: 20px;
        margin: 4rem 0;
        font-family: 'Space Grotesk', 'Inter', -apple-system, sans-serif;
        font-weight: 600;
    }
    
    /* TEXTURA DE ESTRELLAS SUBTIL */
    .star-field {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-image: 
            radial-gradient(1px 1px at 10% 15%, rgba(255, 255, 255, 0.05) 1px, transparent 0),
            radial-gradient(1px 1px at 20% 45%, rgba(255, 221, 0, 0.03) 1px, transparent 0),
            radial-gradient(1px 1px at 30% 75%, rgba(138, 63, 252, 0.04) 1px, transparent 0),
            radial-gradient(1px 1px at 40% 25%, rgba(28, 100, 242, 0.05) 1px, transparent 0),
            radial-gradient(2px 2px at 50% 55%, rgba(255, 255, 255, 0.03) 1px, transparent 0),
            radial-gradient(1px 1px at 60% 85%, rgba(255, 46, 136, 0.04) 1px, transparent 0),
            radial-gradient(1px 1px at 70% 35%, rgba(0, 212, 255, 0.03) 1px, transparent 0),
            radial-gradient(1px 1px at 80% 65%, rgba(0, 196, 154, 0.05) 1px, transparent 0);
        background-size: 500px 500px;
        animation: star-twinkle 25s infinite alternate;
        z-index: 1;
        opacity: 0.6;
    }
    
    @keyframes star-twinkle {
        0%, 100% { opacity: 0.4; }
        50% { opacity: 0.8; }
    }
    
    /* ÓRBITAS - MUY TENUES */
    .galaxy-orbit {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 50%;
        border: 0.5px solid;
        opacity: 0.03;
        z-index: 2;
    }
    
    .orbit-1 { width: var(--orbit-intuitions); height: var(--orbit-intuitions); border-color: var(--magenta-intuition); }
    .orbit-2 { width: var(--orbit-questions); height: var(--orbit-questions); border-color: var(--fog-white); }
    .orbit-3 { width: var(--orbit-themes); height: var(--orbit-themes); border-color: var(--data-blue); }
    .orbit-4 { width: var(--orbit-actions); height: var(--orbit-actions); border-color: var(--amber-hostility); }
    .orbit-5 { width: var(--orbit-futures); height: var(--orbit-futures); border-color: var(--emergent-blue); }
    
    /* ===== SISTEMA DE NODOS - TAMAÑOS AUMENTADOS 40% ===== */
    
    /* CLASE BASE PARA TODOS LOS NODOS */
    .cosmic-node {
        position: absolute;
        cursor: pointer;
        z-index: 10;
        transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        font-weight: 600;
        animation: cosmic-float 10s ease-in-out infinite;
        animation-delay: calc(var(--node-index) * 0.1s);
        filter: drop-shadow(0 0 20px rgba(0, 0, 0, 0.3));
    }
    
    @keyframes cosmic-float {
        0%, 100% { transform: translate(-50%, -50%) scale(1); }
        50% { transform: translate(-50%, -50%) scale(1.02); }
    }
    
    /* CONTENEDOR DE CONTENIDO - PADDING AMPLIO */
    .node-content {
        position: relative;
        z-index: 3;
        padding: 24px; /* 24px padding interno */
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
        text-shadow: 0 1px 2px rgba(0, 0, 0, 0.5);
        color: var(--fog-white);
        font-size: 0.95rem;
        line-height: 1.3;
        letter-spacing: 0.01em;
    }
    
    /* LÍMITE DE CARACTERES POR LÍNEA */
    .node-content div {
        max-width: 90%;
        word-wrap: break-word;
        hyphens: auto;
    }
    
    /* ===== TIPOS DE NODOS - TAMAÑOS AUMENTADOS ===== */
    
    /* 🌞 NÚCLEO - CÍRCULO GRANDE (+45%) */
    .node-type-core {
        width: 220px; /* +45% */
        height: 220px;
        border-radius: 50%;
        background: radial-gradient(
            circle at center,
            #1C64F2 0%,
            #1C64F2 40%,
            rgba(28, 100, 242, 0.2) 70%,
            transparent 100%
        );
        box-shadow: 
            inset 0 0 40px rgba(255, 255, 255, 0.3),
            0 0 80px rgba(28, 100, 242, 0.4);
        animation: core-pulse 8s ease-in-out infinite;
    }
    
    @keyframes core-pulse {
        0%, 100% { 
            box-shadow: 
                inset 0 0 40px rgba(255, 255, 255, 0.3),
                0 0 80px rgba(28, 100, 242, 0.4);
        }
        50% { 
            box-shadow: 
                inset 0 0 50px rgba(255, 255, 255, 0.4),
                0 0 100px rgba(28, 100, 242, 0.5);
        }
    }
    
    /* 💎 INTUICIONES - ROMBOS (+40%) */
    .node-type-intuition {
        width: 140px; /* +40% */
        height: 140px;
        background: radial-gradient(
            circle at center,
            var(--magenta-intuition) 0%,
            var(--magenta-intuition) 40%,
            rgba(181, 30, 255, 0.2) 70%,
            transparent 100%
        );
        clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
        box-shadow: 
            inset 0 0 20px rgba(255, 255, 255, 0.2),
            0 0 40px rgba(181, 30, 255, 0.3);
    }
    
    /* 🧠 PREGUNTAS - HEXÁGONOS (+44%) */
    .node-type-question {
        width: 130px; /* +44% */
        height: 130px;
        background: radial-gradient(
            circle at center,
            rgba(242, 242, 242, 0.95) 0%,
            rgba(242, 242, 242, 0.95) 40%,
            rgba(242, 242, 242, 0.2) 70%,
            transparent 100%
        );
        clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
        color: var(--space-black);
        box-shadow: 
            inset 0 0 20px rgba(255, 255, 255, 0.3),
            0 0 35px rgba(242, 242, 242, 0.3);
    }
    
    /* 🟣 CAMPOS TEÓRICOS - CÍRCULOS GRANDES (+42%) */
    .node-type-theme {
        width: 170px; /* +42% */
        height: 170px;
        border-radius: 50%;
        box-shadow: 
            inset 0 0 30px rgba(255, 255, 255, 0.25),
            0 0 50px currentColor;
        background: radial-gradient(
            circle at center,
            currentColor 0%,
            currentColor 40%,
            rgba(255, 255, 255, 0.1) 70%,
            transparent 100%
        );
    }
    
    /* ◉ ACCIONES - CÍRCULO DOBLE BORDE (+36%) */
    .node-type-action {
        width: 150px; /* +36% */
        height: 150px;
        border-radius: 50%;
        background: transparent;
        border: 3px solid;
        box-shadow: 
            inset 0 0 30px rgba(255, 255, 255, 0.2),
            0 0 50px currentColor;
        position: relative;
    }
    
    .node-type-action::before {
        content: '';
        position: absolute;
        top: 15%;
        left: 15%;
        right: 15%;
        bottom: 15%;
        border-radius: 50%;
        border: 2px solid;
        opacity: 0.4;
    }
    
    /* ⭐ FUTUROS - ESTRELLAS (+50%) */
    .node-type-future {
        width: 150px; /* +50% */
        height: 150px;
        background: radial-gradient(
            circle at center,
            var(--emergent-blue) 0%,
            var(--emergent-blue) 40%,
            rgba(0, 212, 255, 0.2) 70%,
            transparent 100%
        );
        clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        box-shadow: 
            inset 0 0 25px rgba(255, 255, 255, 0.25),
            0 0 40px rgba(0, 212, 255, 0.3);
        animation: star-sparkle 6s ease-in-out infinite;
    }
    
    @keyframes star-sparkle {
        0%, 100% { opacity: 0.95; transform: translate(-50%, -50%) scale(1) rotate(0deg); }
        50% { opacity: 1; transform: translate(-50%, -50%) scale(1.05) rotate(3deg); }
    }
    
    /* ✦ MICRO-NODOS (+33%) */
    .node-type-micro {
        width: 26px; /* +30% */
        height: 26px;
        border-radius: 50%;
        background: radial-gradient(
            circle at center,
            var(--fog-white) 0%,
            var(--fog-white) 50%,
            transparent 80%
        );
        font-size: 0;
        box-shadow: 0 0 12px currentColor;
        animation: micro-pulse 3s ease-in-out infinite;
        animation-delay: calc(var(--micro-index) * 0.2s);
    }
    
    @keyframes micro-pulse {
        0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0.5; }
        50% { transform: translate(-50%, -50%) scale(1.2); opacity: 0.8; }
    }
    
    /* ===== COLORES ESPECÍFICOS CON DEGRADADOS LIMPIOS ===== */
    
    /* Temas teóricos */
    .theme-urban { color: var(--violet-injustice); }
    .theme-urban .node-content { color: var(--fog-white); }
    
    .theme-hostile { color: var(--amber-hostility); }
    .theme-hostile .node-content { color: var(--space-black); }
    
    .theme-species { color: var(--pollen-yellow); }
    .theme-species .node-content { color: var(--space-black); }
    
    .theme-research { color: var(--eco-green); }
    .theme-research .node-content { color: var(--fog-white); }
    
    .theme-sensory { color: var(--toxicity-red); }
    .theme-sensory .node-content { color: var(--fog-white); }
    
    /* Acciones */
    .action-amber { color: var(--amber-hostility); }
    .action-green { color: var(--eco-green); }
    .action-red { color: var(--toxicity-red); }
    .action-blue { color: var(--data-blue); }
    
    /* Micro-nodos coloreados */
    .micro-care { color: var(--eco-green); }
    .micro-friction { color: var(--amber-hostility); }
    .micro-presence { color: var(--violet-injustice); }
    .micro-erasure { color: var(--toxicity-red); }
    .micro-vulnerability { color: var(--magenta-intuition); }
    .micro-coexistence { color: var(--pollen-yellow); }
    
    /* ===== EFECTOS HOVER REFINADOS ===== */
    
    .cosmic-node:hover {
        z-index: 100 !important;
        transform: translate(-50%, -50%) scale(1.1) !important;
        filter: brightness(1.2) drop-shadow(0 0 30px rgba(255, 255, 255, 0.2));
    }
    
    .node-type-core:hover {
        box-shadow: 
            inset 0 0 60px rgba(255, 255, 255, 0.4),
            0 0 120px rgba(28, 100, 242, 0.6);
    }
    
    .node-type-future:hover {
        animation: star-sparkle-hover 1.5s ease-in-out infinite;
    }
    
    @keyframes star-sparkle-hover {
        0%, 100% { opacity: 1; transform: translate(-50%, -50%) scale(1.1) rotate(0deg); }
        50% { opacity: 1; transform: translate(-50%, -50%) scale(1.15) rotate(5deg); }
    }
    
    /* ===== CONEXIONES - CURVAS BÉZIER SUAVES ===== */
    
    .cosmic-connection {
        position: absolute;
        z-index: 4;
        transition: all 0.3s ease;
        pointer-events: none;
    }
    
    /* Línea fuerte - Solo 3-5 de estas */
    .connection-strong {
        height: 2.5px;
        background: linear-gradient(90deg, 
            var(--violet-injustice) 0%,
            var(--emergent-blue) 100%);
        opacity: 0.4;
        filter: drop-shadow(0 0 8px rgba(138, 63, 252, 0.3));
    }
    
    /* Línea normal - Grosor reducido, opacidad 35% */
    .connection-normal {
        height: 1px;
        background: linear-gradient(90deg, 
            currentColor 0%,
            rgba(255, 255, 255, 0.3) 100%);
        opacity: 0.35;
        border-radius: 1px;
    }
    
    /* Línea débil - Punteada sutil */
    .connection-weak {
        height: 0.5px;
        border: none;
        background-image: repeating-linear-gradient(
            90deg,
            transparent,
            transparent 4px,
            rgba(242, 242, 242, 0.2) 4px,
            rgba(242, 242, 242, 0.2) 8px
        );
        opacity: 0.2;
    }
    
    /* ===== TOOLTIP ELEGANTE ===== */
    
    .cosmic-tooltip {
        position: fixed;
        background: rgba(5, 5, 9, 0.92);
        border: 1px solid rgba(242, 242, 242, 0.12);
        border-radius: 12px;
        padding: 1.5rem;
        max-width: 320px;
        z-index: 1000;
        pointer-events: none;
        opacity: 0;
        transform: translateY(15px) scale(0.98);
        transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
        box-shadow: 
            0 12px 48px rgba(0, 0, 0, 0.5),
            0 0 0 1px rgba(28, 100, 242, 0.1);
        backdrop-filter: blur(12px);
        color: var(--fog-white);
        font-size: 0.95rem;
        line-height: 1.5;
        font-weight: 400;
    }
    
    .cosmic-tooltip.active {
        opacity: 1;
        transform: translateY(0) scale(1);
    }
    
    .tooltip-title {
        color: var(--data-blue);
        font-weight: 700;
        margin-bottom: 0.75rem;
        font-size: 1.1rem;
        letter-spacing: 0.02em;
    }
    
    .tooltip-content {
        opacity: 0.9;
        font-weight: 300;
        font-size: 0.9rem;
    }
    
    /* ===== LEYENDA DISCRETA ===== */
    
    .galaxy-legend {
        position: absolute;
        bottom: 2rem;
        right: 2rem;
        background: rgba(5, 5, 9, 0.75); /* Opacidad reducida */
        border: 1px solid rgba(242, 242, 242, 0.08);
        border-radius: 16px;
        padding: 1.25rem;
        z-index: 50;
        backdrop-filter: blur(15px); /* Efecto frosted glass */
        max-width: 240px;
        box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        transition: all 0.3s ease;
        opacity: 0.9;
    }
    
    .legend-title {
        color: rgba(242, 242, 242, 0.8); /* Color más neutro */
        font-size: 0.85rem;
        font-weight: 600;
        margin-bottom: 1rem;
        text-transform: uppercase;
        letter-spacing: 1px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        opacity: 0.9;
    }
    
    .legend-toggle {
        background: none;
        border: none;
        color: rgba(242, 242, 242, 0.6);
        opacity: 0.7;
        cursor: pointer;
        font-size: 1.1rem;
        line-height: 1;
        padding: 0.25rem;
        border-radius: 4px;
        transition: all 0.2s ease;
    }
    
    .legend-toggle:hover {
        background: rgba(242, 242, 242, 0.1);
        opacity: 1;
    }
    
    .legend-content {
        transition: all 0.3s ease;
    }
    
    .legend-item {
        display: flex;
        align-items: center;
        margin-bottom: 0.7rem;
        font-size: 0.8rem;
        opacity: 0.85;
        color: rgba(242, 242, 242, 0.9);
    }
    
    .legend-shape {
        width: 20px;
        height: 20px;
        margin-right: 0.75rem;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 4px;
        flex-shrink: 0;
    }
    
    /* ===== RESPONSIVE OPTIMIZADO ===== */
    
    @media (max-width: 1400px) {
        :root {
            --orbit-intuitions: 200px;
            --orbit-questions: 340px;
            --orbit-themes: 500px;
            --orbit-actions: 680px;
            --orbit-futures: 900px;
        }
        
        .node-type-core { width: 200px; height: 200px; }
        .node-type-intuition { width: 125px; height: 125px; }
        .node-type-question { width: 115px; height: 115px; }
        .node-type-theme { width: 150px; height: 150px; }
        .node-type-action { width: 135px; height: 135px; }
        .node-type-future { width: 135px; height: 135px; }
        
        .node-content {
            padding: 20px;
            font-size: 0.9rem;
        }
    }
    
    @media (max-width: 1024px) {
        .galaxy-constellation {
            height: 120vh;
            min-height: 1000px;
        }
        
        :root {
            --orbit-intuitions: 180px;
            --orbit-questions: 300px;
            --orbit-themes: 440px;
            --orbit-actions: 600px;
            --orbit-futures: 800px;
        }
        
        .node-type-core { width: 180px; height: 180px; font-size: 0.9rem; }
        .node-type-intuition { width: 110px; height: 110px; }
        .node-type-question { width: 100px; height: 100px; font-size: 0.8rem; }
        .node-type-theme { width: 130px; height: 130px; font-size: 0.85rem; }
        .node-type-action { width: 120px; height: 120px; }
        .node-type-future { width: 120px; height: 120px; }
        
        .node-content {
            padding: 18px;
            font-size: 0.85rem;
        }
        
        .galaxy-legend {
            max-width: 200px;
            padding: 1rem;
            right: 1rem;
            bottom: 1rem;
        }
    }
    
    @media (max-width: 768px) {
        .galaxy-constellation {
            height: 100vh;
            min-height: 800px;
        }
        
        :root {
            --orbit-intuitions: 150px;
            --orbit-questions: 250px;
            --orbit-themes: 370px;
            --orbit-actions: 500px;
            --orbit-futures: 650px;
        }
        
        .node-type-core { width: 160px; height: 160px; font-size: 0.85rem; }
        .node-type-intuition { width: 95px; height: 95px; font-size: 0.75rem; }
        .node-type-question { width: 85px; height: 85px; font-size: 0.75rem; }
        .node-type-theme { width: 110px; height: 110px; font-size: 0.8rem; }
        .node-type-action { width: 100px; height: 100px; font-size: 0.75rem; }
        .node-type-future { width: 100px; height: 100px; font-size: 0.75rem; }
        
        .node-content {
            padding: 15px;
            font-size: 0.8rem;
        }
        
        .galaxy-legend {
            display: none; /* Ocultar en móviles para más espacio */
        }
    }
    
    @media (max-width: 480px) {
        .galaxy-constellation {
            height: 90vh;
            min-height: 700px;
        }
        
        :root {
            --orbit-intuitions: 130px;
            --orbit-questions: 220px;
            --orbit-themes: 320px;
            --orbit-actions: 430px;
            --orbit-futures: 550px;
        }
        
        .node-type-core { width: 140px; height: 140px; font-size: 0.8rem; }
        .node-type-intuition { width: 85px; height: 85px; font-size: 0.7rem; }
        .node-type-question { width: 75px; height: 75px; font-size: 0.7rem; }
        .node-type-theme { width: 95px; height: 95px; font-size: 0.75rem; }
        .node-type-action { width: 85px; height: 85px; font-size: 0.7rem; }
        .node-type-future { width: 85px; height: 85px; font-size: 0.7rem; }
        
        .node-content {
            padding: 12px;
            font-size: 0.75rem;
        }
    }
</style>

<!-- =============================================== -->
<!-- HTML DEL MAPA GALÁCTICO ELEGANTE -->
<!-- =============================================== -->

<div class="galaxy-constellation" id="galaxyMap">
    <!-- Fondo estrellado sutil -->
    <div class="star-field"></div>
    
    <!-- Órbitas muy tenues -->
    <div class="galaxy-orbit orbit-1"></div>
    <div class="galaxy-orbit orbit-2"></div>
    <div class="galaxy-orbit orbit-3"></div>
    <div class="galaxy-orbit orbit-4"></div>
    <div class="galaxy-orbit orbit-5"></div>
    
    <!-- Contenedor de nodos -->
    <div id="cosmicNodes"></div>
    
    <!-- Contenedor de conexiones -->
    <div id="cosmicConnections"></div>
    
    <!-- Contenedor de micro-nodos -->
    <div id="microNodes"></div>
    
    <!-- Tooltip elegante -->
    <div class="cosmic-tooltip" id="cosmicTooltip">
        <div class="tooltip-title" id="tooltipTitle"></div>
        <div class="tooltip-content" id="tooltipContent"></div>
    </div>
    
    <!-- Leyenda discreta -->
    <div class="galaxy-legend" id="galaxyLegend">
        <div class="legend-title">
            <span>MAP LEGEND</span>
            <button class="legend-toggle" id="legendToggle">−</button>
        </div>
        <div class="legend-content" id="legendContent">
            <div class="legend-item">
                <div class="legend-shape node-type-core" style="transform: scale(0.5);"></div>
                <span>Core Concept</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-intuition" style="transform: scale(0.6);"></div>
                <span>Intuitions</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-question" style="transform: scale(0.6);"></div>
                <span>Motor Questions</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-theme theme-urban" style="transform: scale(0.6);"></div>
                <span>Thematic Fields</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-action action-amber" style="transform: scale(0.6);"></div>
                <span>Actions as Knowledge</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-future" style="transform: scale(0.6);"></div>
                <span>Emergent Futures</span>
            </div>
        </div>
    </div>
</div>

<!-- =============================================== -->
<!-- JAVASCRIPT OPTIMIZADO PARA CONEXIONES CURVAS -->
<!-- =============================================== -->

<script>
// ===== CONFIGURACIÓN DE NODOS - TEXTO OPTIMIZADO =====

const galaxyData = {
    // 🌞 NÚCLEO
    core: {
        id: "core",
        type: "core",
        title: "THE INVISIBLE CITY",
        subtitle: "Beauty hides violence",
        content: "Urban aesthetics conceal systemic violence against human and non-human life.",
        tooltip: "The central intuition: what we call beautiful in cities often systematically excludes certain lives and species.",
        x: 50,
        y: 50,
        connections: ["intuition1", "theme1", "theme2", "question3"]
    },
    
    // 💎 INTUICIONES - TEXTO BREVE
    intuitions: [
        {
            id: "intuition1",
            type: "intuition",
            title: "Beauty excludes",
            content: "Aesthetic standards as tools of power",
            tooltip: "Clean spaces, curated nature, orderly facades that make some lives 'dirt' and others 'proper'.",
            angle: 0,
            orbit: 1
        },
        {
            id: "intuition2",
            type: "intuition",
            title: "Violence hidden",
            content: "Aesthetics mask structural harm",
            tooltip: "The violence of absence: what is systematically removed or made invisible in the name of beauty.",
            angle: 90,
            orbit: 1
        },
        {
            id: "intuition3",
            type: "intuition",
            title: "Nature expelled",
            content: "Non-curated life removed",
            tooltip: "Plants as decoration, animals as pests, ecosystems as 'mess' to be cleaned from urban spaces.",
            angle: 180,
            orbit: 1
        },
        {
            id: "intuition4",
            type: "intuition",
            title: "Order as control",
            content: "Disguised as care, enacted as power",
            tooltip: "Safety measures that exclude, cleanliness that erases, maintenance that displaces vulnerable lives.",
            angle: 270,
            orbit: 1
        }
    ],
    
    // 🧠 PREGUNTAS - TEXTO CONCISO
    questions: [
        {
            id: "question1",
            type: "question",
            title: "Who can rest?",
            content: "Politics of pause in public space",
            tooltip: "Questioning benches designed against sleeping, surfaces that deny comfort, temporal restrictions on presence.",
            angle: 0,
            orbit: 2
        },
        {
            id: "question2",
            type: "question",
            title: "Whose lives matter?",
            content: "Hierarchy of urban citizenship",
            tooltip: "From homeless humans to pigeons: which lives are welcomed, tolerated, or actively eliminated in cities?",
            angle: 60,
            orbit: 2
        },
        {
            id: "question3",
            type: "question",
            title: "Beauty justifies?",
            content: "Aesthetic rationale for exclusion",
            tooltip: "How visual pleasure becomes an alibi for systemic violence in urban 'improvement' projects.",
            angle: 120,
            orbit: 2
        },
        {
            id: "question4",
            type: "question",
            title: "Design empathy?",
            content: "Cross-species understanding",
            tooltip: "Can interfaces, installations, or experiences help humans feel what other species feel in cities?",
            angle: 180,
            orbit: 2
        },
        {
            id: "question5",
            type: "question",
            title: "Normalized violence?",
            content: "Invisible systemic harm",
            tooltip: "The violence of spikes on ledges, smooth benches, pesticide spraying, constant noise pollution.",
            angle: 240,
            orbit: 2
        },
        {
            id: "question6",
            type: "question",
            title: "Species design?",
            content: "Non-human urban planning",
            tooltip: "What would a pigeon's ideal plaza look like? A bee's transportation system? A tree's housing development?",
            angle: 300,
            orbit: 2
        }
    ],
    
    // 🟣 CAMPOS TEÓRICOS
    themes: [
        {
            id: "theme1",
            type: "theme",
            title: "Urban Aesthetics",
            colorClass: "theme-urban",
            content: "Politics of beauty",
            tooltip: "How aesthetic standards in urban design serve to normalize exclusion and control. Beauty as ideology.",
            angle: 0,
            orbit: 3,
            connections: ["intuition1", "question3", "action1"]
        },
        {
            id: "theme2",
            type: "theme",
            title: "Hostile Design",
            colorClass: "theme-hostile",
            content: "Architecture expels",
            tooltip: "Anti-homeless benches, pigeon spikes, seating deterrents. Violence normalized through design.",
            angle: 60,
            orbit: 3,
            connections: ["intuition4", "question1", "action1"]
        },
        {
            id: "theme3",
            type: "theme",
            title: "Multispecies Justice",
            colorClass: "theme-species",
            content: "Beyond human rights",
            tooltip: "Questioning anthropocentric cities. Rights to shelter, food, movement for all species.",
            angle: 120,
            orbit: 3,
            connections: ["intuition3", "question2", "action2"]
        },
        {
            id: "theme4",
            type: "theme",
            title: "Embodied Research",
            colorClass: "theme-research",
            content: "Body as method",
            tooltip: "Walking, sitting, wearing, performing. First-person ethnography to reveal hidden urban violence.",
            angle: 180,
            orbit: 3,
            connections: ["question4", "action1", "action3"]
        },
        {
            id: "theme5",
            type: "theme",
            title: "Sensory Translation",
            colorClass: "theme-sensory",
            content: "Cross-species perception",
            tooltip: "Interfaces for perceiving pollution, noise, vibration as other species might experience them.",
            angle: 240,
            orbit: 3,
            connections: ["question4", "question6", "future1"]
        },
        {
            id: "theme6",
            type: "theme",
            title: "Environmental Empathy",
            colorClass: "theme-urban",
            content: "Feeling-with ecosystems",
            tooltip: "Developing emotional connections to non-human urban residents and their living conditions.",
            angle: 300,
            orbit: 3,
            connections: ["question4", "future3"]
        }
    ],
    
    // ◉ ACCIONES
    actions: [
        {
            id: "action1",
            type: "action",
            title: "Sitting hostile",
            colorClass: "action-amber",
            content: "Body as sensor",
            tooltip: "Using the body to experience and reveal the normalized violence of exclusionary urban furniture.",
            angle: 45,
            orbit: 4,
            connections: ["theme2", "theme4"]
        },
        {
            id: "action2",
            type: "action",
            title: "Returning Life",
            colorClass: "action-green",
            content: "Rewilding acts",
            tooltip: "Soil deposits, seed bombs, moss graffiti. Reintroducing non-curated life into controlled spaces.",
            angle: 135,
            orbit: 4,
            connections: ["theme3", "future4"]
        },
        {
            id: "action3",
            type: "action",
            title: "Wearing Hostility",
            colorClass: "action-red",
            content: "Material translation",
            tooltip: "Turning anti-pigeon spikes into clothing. Making architectural violence visible on the body.",
            angle: 225,
            orbit: 4,
            connections: ["theme2", "theme4"]
        },
        {
            id: "action4",
            type: "action",
            title: "Sensory experiments",
            colorClass: "action-blue",
            content: "Perception interfaces",
            tooltip: "Prototyping devices that translate urban conditions across sensory modalities and species.",
            angle: 315,
            orbit: 4,
            connections: ["theme5", "future1"]
        }
    ],
    
    // ⭐ FUTUROS
    futures: [
        {
            id: "future1",
            type: "future",
            title: "Multispecies perception",
            content: "Cross-sensing tools",
            tooltip: "Wearables and installations that help humans perceive pollution, vibration, signals as other species do.",
            angle: 45,
            orbit: 5,
            connections: ["theme5", "action4"]
        },
        {
            id: "future2",
            type: "future",
            title: "Embodied translation",
            content: "Full-body ecology",
            tooltip: "Haptic suits, olfactory displays that make environmental conditions tangibly felt by humans.",
            angle: 135,
            orbit: 5,
            connections: ["theme5", "action4"]
        },
        {
            id: "future3",
            type: "future",
            title: "Empathy-driven design",
            content: "Compassionate planning",
            tooltip: "Design processes centering multispecies wellbeing, sensory justice, and ecological empathy.",
            angle: 225,
            orbit: 5,
            connections: ["theme6", "future4"]
        },
        {
            id: "future4",
            type: "future",
            title: "Urban coexistence",
            content: "Multispecies community",
            tooltip: "Reimagining cities where all residents are recognized as citizens with rights and needs.",
            angle: 315,
            orbit: 5,
            connections: ["theme6", "action2"]
        }
    ],
    
    // ✦ MICRO-NODOS
    microNodes: [
        {id: "micro1", word: "care", colorClass: "micro-care", x: 30, y: 25},
        {id: "micro2", word: "friction", colorClass: "micro-friction", x: 70, y: 20},
        {id: "micro3", word: "presence", colorClass: "micro-presence", x: 85, y: 45},
        {id: "micro4", word: "erasure", colorClass: "micro-erasure", x: 75, y: 75},
        {id: "micro5", word: "vulnerability", colorClass: "micro-vulnerability", x: 45, y: 85},
        {id: "micro6", word: "coexistence", colorClass: "micro-coexistence", x: 20, y: 70}
    ]
};

// ===== FUNCIONES DE CONSTRUCCIÓN OPTIMIZADAS =====

function createGalaxy() {
    const nodesContainer = document.getElementById('cosmicNodes');
    const connectionsContainer = document.getElementById('cosmicConnections');
    const microContainer = document.getElementById('microNodes');
    
    // Crear nodo central
    createNode(galaxyData.core, nodesContainer, 0);
    
    // Crear todos los nodos
    const allNodes = [
        ...galaxyData.intuitions,
        ...galaxyData.questions,
        ...galaxyData.themes,
        ...galaxyData.actions,
        ...galaxyData.futures
    ];
    
    allNodes.forEach((node, index) => {
        createNode(node, nodesContainer, index + 1);
    });
    
    // Crear micro-nodos
    galaxyData.microNodes.forEach((micro, index) => {
        createMicroNode(micro, microContainer, index);
    });
    
    // Crear conexiones curvas
    setTimeout(() => {
        createAllConnections(connectionsContainer);
    }, 100);
}

function createNode(nodeData, container, index) {
    const node = document.createElement('div');
    node.className = `cosmic-node node-type-${nodeData.type}`;
    node.dataset.id = nodeData.id;
    node.dataset.type = nodeData.type;
    node.style.setProperty('--node-index', index);
    
    // Calcular posición con separación adecuada
    let x, y;
    if (nodeData.type === 'core') {
        x = 50;
        y = 50;
    } else {
        const orbit = getOrbitRadius(nodeData.orbit);
        const angle = (nodeData.angle * Math.PI) / 180;
        x = 50 + (orbit * Math.cos(angle));
        y = 50 + (orbit * Math.sin(angle));
    }
    
    node.style.left = `${x}%`;
    node.style.top = `${y}%`;
    
    // Añadir clase de color
    if (nodeData.colorClass) {
        node.classList.add(nodeData.colorClass);
    }
    
    // Contenido con texto optimizado
    const content = document.createElement('div');
    content.className = 'node-content';
    
    const title = document.createElement('div');
    title.textContent = nodeData.title;
    title.style.fontWeight = '700';
    title.style.marginBottom = '0.3rem';
    title.style.fontSize = nodeData.type === 'core' ? '1.1rem' : '0.95rem';
    
    const subtitle = document.createElement('div');
    subtitle.textContent = nodeData.content;
    subtitle.style.fontSize = '0.85rem';
    subtitle.style.opacity = '0.9';
    subtitle.style.fontWeight = '500';
    
    content.appendChild(title);
    content.appendChild(subtitle);
    node.appendChild(content);
    
    container.appendChild(node);
    
    // Event listeners
    setupNodeInteractions(node, nodeData);
}

function getOrbitRadius(orbitNumber) {
    const orbits = {
        1: 22,   // 220px / 1000px * 100%
        2: 38,   // 380px / 1000px * 100%
        3: 56,   // 560px / 1000px * 100%
        4: 76,   // 760px / 1000px * 100%
        5: 100   // 1000px / 1000px * 100%
    };
    return orbits[orbitNumber] || 0;
}

// ===== CONEXIONES CURVAS BÉZIER =====

function createAllConnections(container) {
    // Solo 4-5 líneas fuertes
    createBezierConnection("core", "intuition1", "strong", container);
    createBezierConnection("theme1", "action1", "strong", container);
    createBezierConnection("theme3", "action2", "strong", container);
    createBezierConnection("theme5", "future1", "strong", container);
    
    // Conexiones normales (reducidas)
    createBezierConnection("core", "theme1", "normal", container);
    createBezierConnection("core", "theme2", "normal", container);
    createBezierConnection("intuition1", "question3", "normal", container);
    createBezierConnection("theme2", "question1", "normal", container);
    createBezierConnection("theme4", "action3", "normal", container);
    createBezierConnection("theme6", "future3", "normal", container);
    
    // Conexiones débiles (mínimas)
    createBezierConnection("micro1", "theme3", "weak", container);
    createBezierConnection("micro4", "theme2", "weak", container);
}

function createBezierConnection(sourceId, targetId, strength, container) {
    const source = document.querySelector(`[data-id="${sourceId}"]`);
    const target = document.querySelector(`[data-id="${targetId}"]`);
    
    if (!source || !target) return;
    
    // Crear elemento SVG para curva Bézier
    const svgNS = "http://www.w3.org/2000/svg";
    const svg = document.createElementNS(svgNS, "svg");
    svg.classList.add("cosmic-connection");
    svg.style.position = "absolute";
    svg.style.top = "0";
    svg.style.left = "0";
    svg.style.width = "100%";
    svg.style.height = "100%";
    svg.style.pointerEvents = "none";
    svg.style.zIndex = "4";
    svg.style.overflow = "visible";
    
    // Coordenadas de los nodos
    const sourceRect = source.getBoundingClientRect();
    const targetRect = target.getBoundingClientRect();
    const containerRect = document.getElementById('galaxyMap').getBoundingClientRect();
    
    const x1 = sourceRect.left + sourceRect.width/2 - containerRect.left;
    const y1 = sourceRect.top + sourceRect.height/2 - containerRect.top;
    const x2 = targetRect.left + targetRect.width/2 - containerRect.left;
    const y2 = targetRect.top + targetRect.height/2 - containerRect.top;
    
    // Puntos de control para curva Bézier
    const dx = x2 - x1;
    const dy = y2 - y1;
    const distance = Math.sqrt(dx * dx + dy * dy);
    
    // Curvatura proporcional a la distancia
    const curvature = distance * 0.15;
    
    const cx1 = x1 + dx * 0.3 + curvature;
    const cy1 = y1 + dy * 0.3 - curvature;
    const cx2 = x1 + dx * 0.7 - curvature;
    const cy2 = y1 + dy * 0.7 + curvature;
    
    // Crear path Bézier
    const path = document.createElementNS(svgNS, "path");
    const d = `M ${x1} ${y1} C ${cx1} ${cy1}, ${cx2} ${cy2}, ${x2} ${y2}`;
    path.setAttribute("d", d);
    path.setAttribute("fill", "none");
    
    // Estilos según fuerza
    switch(strength) {
        case "strong":
            path.setAttribute("stroke", "url(#gradient-strong)");
            path.setAttribute("stroke-width", "2.5");
            path.setAttribute("opacity", "0.4");
            break;
        case "normal":
            path.setAttribute("stroke", "rgba(242, 242, 242, 0.35)");
            path.setAttribute("stroke-width", "1");
            path.setAttribute("opacity", "0.35");
            break;
        case "weak":
            path.setAttribute("stroke", "rgba(242, 242, 242, 0.2)");
            path.setAttribute("stroke-width", "0.5");
            path.setAttribute("stroke-dasharray", "4,4");
            path.setAttribute("opacity", "0.2");
            break;
    }
    
    // Definir gradiente para líneas fuertes
    if (strength === "strong") {
        const defs = document.createElementNS(svgNS, "defs");
        const gradient = document.createElementNS(svgNS, "linearGradient");
        gradient.setAttribute("id", "gradient-strong");
        gradient.setAttribute("x1", "0%");
        gradient.setAttribute("y1", "0%");
        gradient.setAttribute("x2", "100%");
        gradient.setAttribute("y2", "0%");
        
        const stop1 = document.createElementNS(svgNS, "stop");
        stop1.setAttribute("offset", "0%");
        stop1.setAttribute("stop-color", "#8A3FFC");
        stop1.setAttribute("stop-opacity", "0.8");
        
        const stop2 = document.createElementNS(svgNS, "stop");
        stop2.setAttribute("offset", "100%");
        stop2.setAttribute("stop-color", "#00D4FF");
        stop2.setAttribute("stop-opacity", "0.8");
        
        gradient.appendChild(stop1);
        gradient.appendChild(stop2);
        defs.appendChild(gradient);
        svg.appendChild(defs);
    }
    
    svg.appendChild(path);
    container.appendChild(svg);
    
    return svg;
}

// ===== INTERACCIÓN REFINADA =====

const tooltip = document.getElementById('cosmicTooltip');
const tooltipTitle = document.getElementById('tooltipTitle');
const tooltipContent = document.getElementById('tooltipContent');

function setupNodeInteractions(node, nodeData) {
    node.addEventListener('mouseenter', (e) => {
        handleNodeHover(e, nodeData);
    });
    
    node.addEventListener('mouseleave', handleNodeLeave);
    node.addEventListener('click', () => handleNodeClick(nodeData));
}

function handleNodeHover(event, nodeData) {
    // Mostrar tooltip
    tooltipTitle.textContent = nodeData.title;
    tooltipContent.textContent = nodeData.tooltip || nodeData.content;
    
    tooltip.style.left = `${event.clientX + 20}px`;
    tooltip.style.top = `${event.clientY + 20}px`;
    tooltip.classList.add('active');
    
    // Resaltar conexiones relacionadas
    document.querySelectorAll('.cosmic-connection path').forEach(path => {
        path.style.opacity = '0.15';
        path.style.transition = 'opacity 0.3s ease';
    });
    
    // Buscar y resaltar conexiones de este nodo
    const nodeId = nodeData.id;
    document.querySelectorAll('.cosmic-connection').forEach(conn => {
        const path = conn.querySelector('path');
        if (path && (conn.dataset.source === nodeId || conn.dataset.target === nodeId)) {
            path.style.opacity = '0.7';
            path.style.filter = 'drop-shadow(0 0 4px rgba(255, 255, 255, 0.3))';
        }
    });
}

function handleNodeLeave() {
    tooltip.classList.remove('active');
    
    // Restaurar conexiones
    document.querySelectorAll('.cosmic-connection path').forEach(path => {
        path.style.opacity = '';
        path.style.filter = '';
    });
}

function handleNodeClick(nodeData) {
    // Aquí podrías integrar con tu sistema de modales
    console.log(`Nodo clickeado: ${nodeData.title}`, nodeData);
    
    // Mostrar información en consola o integrar con tu UI
    const info = `
        ${nodeData.title}
        ${nodeData.type.toUpperCase()}
        
        ${nodeData.tooltip || nodeData.content}
    `;
    
    // Opción: mostrar un alert más elegante o integrar con tu sistema
    if (window.innerWidth > 768) {
        alert(info);
    }
}

// ===== LEYENDA INTERACTIVA =====

const legendToggle = document.getElementById('legendToggle');
const legendContent = document.getElementById('legendContent');
let legendVisible = true;

legendToggle.addEventListener('click', () => {
    legendVisible = !legendVisible;
    
    if (legendVisible) {
        legendContent.style.display = 'block';
        legendToggle.textContent = '−';
    } else {
        legendContent.style.display = 'none';
        legendToggle.textContent = '+';
    }
});

// ===== MICRO-NODOS =====

function createMicroNode(microData, container, index) {
    const micro = document.createElement('div');
    micro.className = `cosmic-node node-type-micro ${microData.colorClass}`;
    micro.dataset.id = microData.id;
    micro.dataset.word = microData.word;
    micro.style.setProperty('--micro-index', index);
    micro.style.left = `${microData.x}%`;
    micro.style.top = `${microData.y}%`;
    
    micro.addEventListener('mouseenter', (e) => {
        showTooltip(microData.word, 
            `Conceptual thread: ${microData.word} as a lens for reading urban relations and violence.`, 
            e);
    });
    
    micro.addEventListener('mouseleave', hideTooltip);
    
    container.appendChild(micro);
}

function showTooltip(title, content, event) {
    tooltipTitle.textContent = title;
    tooltipContent.textContent = content;
    
    tooltip.style.left = `${event.clientX + 15}px`;
    tooltip.style.top = `${event.clientY + 15}px`;
    tooltip.classList.add('active');
}

function hideTooltip() {
    tooltip.classList.remove('active');
}

// ===== INICIALIZACIÓN =====

document.addEventListener('DOMContentLoaded', () => {
    createGalaxy();
    
    // Ajustar al redimensionar
    let resizeTimeout;
    window.addEventListener('resize', () => {
        clearTimeout(resizeTimeout);
        resizeTimeout = setTimeout(() => {
            document.getElementById('cosmicConnections').innerHTML = '';
            createAllConnections(document.getElementById('cosmicConnections'));
        }, 250);
    });
    
    // Mover tooltip con el mouse
    document.addEventListener('mousemove', (e) => {
        if (tooltip.classList.contains('active')) {
            tooltip.style.left = `${e.clientX + 20}px`;
            tooltip.style.top = `${e.clientY + 20}px`;
        }
    });
});
</script>