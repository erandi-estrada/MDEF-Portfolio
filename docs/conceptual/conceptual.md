<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<!-- =============================================== -->
<!-- CONSTELACIÓN EXPANDIDA - VERSIÓN PLANETARIA -->
<!-- =============================================== -->

<style>
    /* Variables de color y espacio - AUMENTADAS */
    :root {
        /* Colores base */
        --black-phosphor: #050509;
        --data-blue: #1C64F2;
        --species-violet: #8A3FFC;
        --hostility-amber: #FF9F1C;
        --bee-yellow: #FFDD00;
        --ecosystem-green: #00C49A;
        --toxicity-red: #E11D48;
        --fog-white: #F2F2F2;
        --magenta-intuition: #FF2E88;
        --emergent-blue: #00D4FF;
        
        /* Tamaños de órbitas - AUMENTADOS */
        --orbit-1: 180px;  /* Intuiciones - antes 120px */
        --orbit-2: 300px;  /* Preguntas - antes 200px */
        --orbit-3: 450px;  /* Campos teóricos - antes 320px */
        --orbit-4: 620px;  /* Acciones - antes 460px */
        --orbit-5: 800px;  /* Futuros - antes 600px */
    }
    
    /* Contenedor principal - MÁS ALTO */
    .expanded-constellation {
        position: relative;
        width: 100%;
        height: 120vh; /* Aumentado de 100vh */
        min-height: 1100px; /* Aumentado de 900px */
        background: var(--black-phosphor);
        overflow: hidden;
        border-radius: 16px;
        margin: 4rem 0;
        font-family: 'Space Grotesk', 'Inter', sans-serif;
    }
    
    /* Fondo estrellado complejo */
    .deep-starfield {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: 
            radial-gradient(2px 2px at 10% 15%, rgba(255, 255, 255, 0.15) 1px, transparent 0),
            radial-gradient(2px 2px at 20% 45%, rgba(255, 221, 0, 0.2) 1px, transparent 0),
            radial-gradient(3px 3px at 30% 75%, rgba(138, 63, 252, 0.15) 1px, transparent 0),
            radial-gradient(4px 4px at 40% 25%, rgba(28, 100, 242, 0.2) 1px, transparent 0),
            radial-gradient(2px 2px at 50% 55%, rgba(255, 242, 242, 0.1) 1px, transparent 0),
            radial-gradient(3px 3px at 60% 85%, rgba(255, 46, 136, 0.15) 1px, transparent 0),
            radial-gradient(4px 4px at 70% 35%, rgba(0, 212, 255, 0.15) 1px, transparent 0),
            radial-gradient(2px 2px at 80% 65%, rgba(0, 196, 154, 0.2) 1px, transparent 0),
            radial-gradient(3px 3px at 90% 15%, rgba(255, 159, 28, 0.15) 1px, transparent 0);
        background-size: 300px 300px;
        animation: star-twinkle 15s infinite alternate;
        z-index: 1;
    }
    
    @keyframes star-twinkle {
        0%, 100% { opacity: 0.3; }
        25% { opacity: 0.6; }
        50% { opacity: 0.4; }
        75% { opacity: 0.8; }
    }
    
    /* Órbitas con gradientes sutiles */
    .expanded-orbit {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 50%;
        border: 1px solid;
        z-index: 2;
        opacity: 0.15;
        animation: orbit-rotate 120s linear infinite;
    }
    
    .orbit-intuitions { 
        width: var(--orbit-1); 
        height: var(--orbit-1);
        border-color: var(--magenta-intuition);
        animation-duration: 80s;
    }
    
    .orbit-questions { 
        width: var(--orbit-2); 
        height: var(--orbit-2);
        border-color: var(--fog-white);
        animation-duration: 100s;
    }
    
    .orbit-themes { 
        width: var(--orbit-3); 
        height: var(--orbit-3);
        border-color: var(--data-blue);
        animation-duration: 120s;
        opacity: 0.2;
    }
    
    .orbit-actions { 
        width: var(--orbit-4); 
        height: var(--orbit-4);
        border-color: var(--hostility-amber);
        animation-duration: 140s;
    }
    
    .orbit-futures { 
        width: var(--orbit-5); 
        height: var(--orbit-5);
        border-color: var(--emergent-blue);
        animation-duration: 160s;
        opacity: 0.25;
    }
    
    @keyframes orbit-rotate {
        from { transform: translate(-50%, -50%) rotate(0deg); }
        to { transform: translate(-50%, -50%) rotate(360deg); }
    }
    
    /* ===== NUEVO DISEÑO DE NODOS - ESTILO PLANETA ===== */
    
    /* Contenedor base para todos los nodos */
    .planet-node {
        position: absolute;
        cursor: pointer;
        z-index: 5;
        transition: all 0.4s ease;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        font-weight: 600;
    }
    
    /* Efecto de planeta - Sólido en centro, degradado hacia bordes */
    .planet-node::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        border-radius: inherit;
        background: radial-gradient(
            circle at 30% 30%,
            rgba(255, 255, 255, 0.9) 0%,
            rgba(255, 255, 255, 0.4) 20%,
            rgba(255, 255, 255, 0.1) 50%,
            transparent 70%
        );
        opacity: 0.3;
        z-index: 1;
    }
    
    /* Contenido del nodo */
    .planet-content {
        position: relative;
        z-index: 2;
        padding: 1rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
    }
    
    /* Nodo central - El corazón (MÁS GRANDE) */
    .node-core {
        width: 220px; /* Aumentado de 180px */
        height: 220px;
        border-radius: 50%;
        background: radial-gradient(
            circle at 30% 30%,
            #1C64F2 0%,
            #0A4BCF 20%,
            #003399 50%,
            #001F5C 100%
        );
        box-shadow: 
            0 0 100px rgba(28, 100, 242, 0.6),
            inset 0 0 60px rgba(255, 255, 255, 0.4),
            0 0 30px rgba(255, 221, 0, 0.3);
        animation: core-pulse 6s ease-in-out infinite;
        color: var(--fog-white);
        font-size: 1.1rem;
    }
    
    @keyframes core-pulse {
        0%, 100% { 
            transform: translate(-50%, -50%) scale(1);
            box-shadow: 
                0 0 100px rgba(28, 100, 242, 0.6),
                inset 0 0 60px rgba(255, 255, 255, 0.4);
        }
        50% { 
            transform: translate(-50%, -50%) scale(1.05);
            box-shadow: 
                0 0 140px rgba(28, 100, 242, 0.8),
                inset 0 0 80px rgba(255, 255, 255, 0.6);
        }
    }
    
    /* Rombo - Intuiciones (MÁS GRANDE) */
    .node-diamond {
        width: 110px; /* Aumentado de 80px */
        height: 110px;
        background: radial-gradient(
            circle at 30% 30%,
            #FF2E88 0%,
            #D91A6F 30%,
            #B30054 60%,
            #8A0040 100%
        );
        clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
        animation: diamond-float 8s ease-in-out infinite;
        color: var(--fog-white);
        font-size: 0.9rem;
        box-shadow: 
            0 0 40px rgba(255, 46, 136, 0.5),
            inset 0 0 30px rgba(255, 255, 255, 0.2);
    }
    
    @keyframes diamond-float {
        0%, 100% { transform: translate(-50%, -50%) rotate(45deg) scale(1); }
        50% { transform: translate(-50%, -50%) rotate(45deg) scale(1.05); }
    }
    
    /* Hexágono - Preguntas (MÁS GRANDE) */
    .node-hexagon {
        width: 100px; /* Aumentado de 70px */
        height: 100px;
        background: radial-gradient(
            circle at 30% 30%,
            #F2F2F2 0%,
            #D9D9D9 30%,
            #BFBFBF 60%,
            #8C8C8C 100%
        );
        clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
        color: var(--black-phosphor);
        font-size: 0.85rem;
        animation: hexagon-rotate 20s linear infinite;
        box-shadow: 
            0 0 30px rgba(242, 242, 242, 0.4),
            inset 0 0 20px rgba(255, 255, 255, 0.3);
    }
    
    @keyframes hexagon-rotate {
        from { transform: translate(-50%, -50%) rotate(0deg); }
        to { transform: translate(-50%, -50%) rotate(360deg); }
    }
    
    /* Círculo - Campos teóricos (MÁS GRANDE) */
    .node-circle {
        width: 140px; /* Aumentado de 100px */
        height: 140px;
        border-radius: 50%;
        color: var(--black-phosphor);
        font-size: 1rem;
        animation: circle-breathe 10s ease-in-out infinite;
        box-shadow: 
            0 0 50px rgba(0, 0, 0, 0.3),
            inset 0 0 40px rgba(255, 255, 255, 0.2);
    }
    
    /* Colores específicos para círculos con efecto planeta */
    .circle-urban {
        background: radial-gradient(
            circle at 30% 30%,
            #8A3FFC 0%,
            #7029D9 25%,
            #5614B6 50%,
            #3D008C 100%
        );
        color: var(--fog-white);
    }
    
    .circle-hostile {
        background: radial-gradient(
            circle at 30% 30%,
            #FF9F1C 0%,
            #E68900 25%,
            #CC7300 50%,
            #B35C00 100%
        );
    }
    
    .circle-species {
        background: radial-gradient(
            circle at 30% 30%,
            #FFDD00 0%,
            #E6C600 25%,
            #CCB000 50%,
            #B39900 100%
        );
    }
    
    .circle-research {
        background: radial-gradient(
            circle at 30% 30%,
            #00C49A 0%,
            #00AA85 25%,
            #009170 50%,
            #00775C 100%
        );
        color: var(--fog-white);
    }
    
    .circle-sensory {
        background: radial-gradient(
            circle at 30% 30%,
            #E11D48 0%,
            #C90A34 25%,
            #B00021 50%,
            #96000F 100%
        );
        color: var(--fog-white);
    }
    
    .circle-environment {
        background: radial-gradient(
            circle at 30% 30%,
            #1C64F2 0%,
            #0A4BCF 25%,
            #003399 50%,
            #001F5C 100%
        );
        color: var(--fog-white);
    }
    
    @keyframes circle-breathe {
        0%, 100% { transform: translate(-50%, -50%) scale(1); }
        50% { transform: translate(-50%, -50%) scale(1.08); }
    }
    
    /* Anillo doble - Acciones (MÁS GRANDE) */
    .node-ring {
        width: 130px; /* Aumentado de 90px */
        height: 130px;
        border-radius: 50%;
        background: transparent;
        border: 4px solid;
        box-shadow: 
            inset 0 0 40px rgba(255, 255, 255, 0.3),
            0 0 50px currentColor;
        animation: ring-pulse 4s ease-in-out infinite;
        color: var(--fog-white);
        font-size: 0.9rem;
        position: relative;
        overflow: hidden;
    }
    
    .node-ring::after {
        content: '';
        position: absolute;
        top: 10%;
        left: 10%;
        right: 10%;
        bottom: 10%;
        border-radius: 50%;
        background: radial-gradient(
            circle at 30% 30%,
            rgba(255, 255, 255, 0.2) 0%,
            rgba(255, 255, 255, 0.1) 30%,
            rgba(255, 255, 255, 0.05) 60%,
            transparent 80%
        );
        z-index: 1;
    }
    
    /* Colores específicos para anillos */
    .ring-amber { border-color: var(--hostility-amber); }
    .ring-green { border-color: var(--ecosystem-green); }
    .ring-red { border-color: var(--toxicity-red); }
    .ring-blue { border-color: var(--data-blue); }
    
    @keyframes ring-pulse {
        0%, 100% { 
            box-shadow: 
                inset 0 0 40px rgba(255, 255, 255, 0.3),
                0 0 50px currentColor;
        }
        50% { 
            box-shadow: 
                inset 0 0 60px rgba(255, 255, 255, 0.4),
                0 0 70px currentColor;
        }
    }
    
    /* Estrella - Futuros emergentes (MÁS GRANDE) */
    .node-star {
        width: 120px; /* Aumentado de 80px */
        height: 120px;
        background: radial-gradient(
            circle at 30% 30%,
            #00D4FF 0%,
            #00B8E6 20%,
            #009CCC 40%,
            #007FB3 60%,
            #006399 80%,
            #004680 100%
        );
        clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        animation: star-sparkle 3s ease-in-out infinite;
        color: var(--fog-white);
        font-size: 0.9rem;
        box-shadow: 
            0 0 60px rgba(0, 212, 255, 0.5),
            inset 0 0 30px rgba(255, 255, 255, 0.3);
    }
    
    @keyframes star-sparkle {
        0%, 100% { 
            opacity: 0.9; 
            transform: translate(-50%, -50%) scale(1) rotate(0deg);
        }
        50% { 
            opacity: 1; 
            transform: translate(-50%, -50%) scale(1.1) rotate(10deg);
        }
    }
    
    /* Micro-luces - Conexiones laterales */
    .node-micro {
        width: 15px; /* Aumentado de 12px */
        height: 15px;
        border-radius: 50%;
        position: absolute;
        background: var(--fog-white);
        opacity: 0.5;
        z-index: 3;
        animation: micro-twinkle 2s ease-in-out infinite;
        animation-delay: calc(var(--i) * 0.1s);
        box-shadow: 0 0 10px currentColor;
    }
    
    @keyframes micro-twinkle {
        0%, 100% { opacity: 0.3; transform: scale(1); }
        50% { opacity: 0.8; transform: scale(1.4); }
    }
    
    /* ===== CONEXIONES MEJORADAS ===== */
    
    .connection-line {
        position: absolute;
        height: 2px;
        background: linear-gradient(90deg, transparent, var(--fog-white), transparent);
        transform-origin: 0 0;
        z-index: 2;
        opacity: 0.2;
        transition: all 0.3s ease;
    }
    
    .connection-strong {
        height: 3px;
        background: linear-gradient(90deg, var(--data-blue), var(--ecosystem-green));
        opacity: 0.35;
        box-shadow: 0 0 10px rgba(28, 100, 242, 0.3);
    }
    
    .connection-curved {
        height: 2px;
        background: linear-gradient(90deg, var(--species-violet), var(--magenta-intuition));
        border-radius: 50%;
        opacity: 0.25;
        box-shadow: 0 0 8px rgba(138, 63, 252, 0.3);
    }
    
    /* Efecto hover para nodos */
    .planet-node:hover {
        z-index: 100 !important;
        transform: translate(-50%, -50%) scale(1.15) !important;
        filter: brightness(1.2);
    }
    
    .planet-node:hover .planet-content {
        text-shadow: 0 0 10px rgba(255, 255, 255, 0.7);
    }
    
    /* ===== RESPONSIVE - OPTIMIZADO ===== */
    
    @media (max-width: 1400px) {
        :root {
            --orbit-1: 160px;
            --orbit-2: 280px;
            --orbit-3: 420px;
            --orbit-4: 580px;
            --orbit-5: 750px;
        }
        
        .node-core { width: 200px; height: 200px; font-size: 1rem; }
        .node-diamond { width: 100px; height: 100px; font-size: 0.85rem; }
        .node-hexagon { width: 90px; height: 90px; font-size: 0.8rem; }
        .node-circle { width: 130px; height: 130px; font-size: 0.95rem; }
        .node-ring { width: 120px; height: 120px; font-size: 0.85rem; }
        .node-star { width: 110px; height: 110px; font-size: 0.85rem; }
    }
    
    @media (max-width: 1024px) {
        .expanded-constellation {
            height: 100vh;
            min-height: 900px;
        }
        
        :root {
            --orbit-1: 140px;
            --orbit-2: 240px;
            --orbit-3: 360px;
            --orbit-4: 500px;
            --orbit-5: 650px;
        }
        
        .node-core { width: 180px; height: 180px; font-size: 0.95rem; }
        .node-diamond { width: 90px; height: 90px; font-size: 0.8rem; }
        .node-hexagon { width: 80px; height: 80px; font-size: 0.75rem; }
        .node-circle { width: 115px; height: 115px; font-size: 0.85rem; }
        .node-ring { width: 105px; height: 105px; font-size: 0.8rem; border-width: 3px; }
        .node-star { width: 95px; height: 95px; font-size: 0.8rem; }
    }
    
    @media (max-width: 768px) {
        .expanded-constellation {
            height: 800px;
            min-height: 800px;
        }
        
        :root {
            --orbit-1: 120px;
            --orbit-2: 200px;
            --orbit-3: 300px;
            --orbit-4: 420px;
            --orbit-5: 550px;
        }
        
        .node-core { width: 160px; height: 160px; font-size: 0.9rem; }
        .node-diamond { width: 80px; height: 80px; font-size: 0.75rem; }
        .node-hexagon { width: 70px; height: 70px; font-size: 0.7rem; }
        .node-circle { width: 100px; height: 100px; font-size: 0.8rem; }
        .node-ring { width: 90px; height: 90px; font-size: 0.75rem; }
        .node-star { width: 85px; height: 85px; font-size: 0.75rem; }
    }
    
    @media (max-width: 480px) {
        .expanded-constellation {
            height: 700px;
            min-height: 700px;
        }
        
        :root {
            --orbit-1: 100px;
            --orbit-2: 170px;
            --orbit-3: 260px;
            --orbit-4: 360px;
            --orbit-5: 470px;
        }
        
        .node-core { width: 140px; height: 140px; font-size: 0.85rem; }
        .node-diamond { width: 70px; height: 70px; font-size: 0.7rem; }
        .node-hexagon { width: 60px; height: 60px; font-size: 0.65rem; }
        .node-circle { width: 85px; height: 85px; font-size: 0.75rem; }
        .node-ring { width: 75px; height: 75px; font-size: 0.7rem; }
        .node-star { width: 70px; height: 70px; font-size: 0.7rem; }
    }
</style>

<!-- =============================================== -->
<!-- HTML DE LA CONSTELACIÓN PLANETARIA -->
<!-- =============================================== -->

<div class="expanded-constellation" id="expandedConstellation">
    <!-- Fondo estrellado -->
    <div class="deep-starfield"></div>
    
    <!-- Órbitas -->
    <div class="expanded-orbit orbit-intuitions"></div>
    <div class="expanded-orbit orbit-questions"></div>
    <div class="expanded-orbit orbit-themes"></div>
    <div class="expanded-orbit orbit-actions"></div>
    <div class="expanded-orbit orbit-futures"></div>
    
    <!-- ===== NÚCLEO ===== -->
    <div class="planet-node node-core" style="top: 50%; left: 50%;" data-modal="core">
        <div class="planet-content">
            <div style="font-size: 1.3rem; font-weight: 800; margin-bottom: 0.3rem;">THE INVISIBLE CITY</div>
            <div style="font-size: 0.85rem; opacity: 0.9; line-height: 1.2;">Violence hidden under aesthetics</div>
        </div>
    </div>
    
    <!-- ===== ANILLO 1: INTUICIONES ===== -->
    <div class="planet-node node-diamond" style="top: calc(50% - var(--orbit-1) * 0.7); left: 50%;" data-modal="intuition1">
        <div class="planet-content" style="transform: rotate(-45deg);">
            Beauty that excludes
        </div>
    </div>
    
    <div class="planet-node node-diamond" style="top: 50%; left: calc(50% + var(--orbit-1) * 0.7);" data-modal="intuition2">
        <div class="planet-content" style="transform: rotate(-45deg);">
            Violence as absence
        </div>
    </div>
    
    <div class="planet-node node-diamond" style="top: calc(50% + var(--orbit-1) * 0.7); left: 50%;" data-modal="intuition3">
        <div class="planet-content" style="transform: rotate(-45deg);">
            Nature expelled
        </div>
    </div>
    
    <div class="planet-node node-diamond" style="top: 50%; left: calc(50% - var(--orbit-1) * 0.7);" data-modal="intuition4">
        <div class="planet-content" style="transform: rotate(-45deg);">
            Order as ideology
        </div>
    </div>
    
    <!-- ===== ANILLO 2: PREGUNTAS ===== -->
    <div class="planet-node node-hexagon" style="top: calc(50% - var(--orbit-2) * 0.9); left: 50%;" data-modal="question1">
        <div class="planet-content">
            What bodies can rest?
        </div>
    </div>
    
    <div class="planet-node node-hexagon" style="top: calc(50% - var(--orbit-2) * 0.45); left: calc(50% + var(--orbit-2) * 0.78);" data-modal="question2">
        <div class="planet-content">
            Whose lives are allowed?
        </div>
    </div>
    
    <div class="planet-node node-hexagon" style="top: calc(50% + var(--orbit-2) * 0.45); left: calc(50% + var(--orbit-2) * 0.78);" data-modal="question3">
        <div class="planet-content">
            How does beauty justify exclusion?
        </div>
    </div>
    
    <div class="planet-node node-hexagon" style="top: calc(50% + var(--orbit-2) * 0.9); left: 50%;" data-modal="question4">
        <div class="planet-content">
            Can design generate empathy?
        </div>
    </div>
    
    <div class="planet-node node-hexagon" style="top: calc(50% + var(--orbit-2) * 0.45); left: calc(50% - var(--orbit-2) * 0.78);" data-modal="question5">
        <div class="planet-content">
            What violence is invisible?
        </div>
    </div>
    
    <div class="planet-node node-hexagon" style="top: calc(50% - var(--orbit-2) * 0.45); left: calc(50% - var(--orbit-2) * 0.78);" data-modal="question6">
        <div class="planet-content">
            How would species design cities?
        </div>
    </div>
    
    <!-- ===== ANILLO 3: CAMPOS TEÓRICOS ===== -->
    <div class="planet-node node-circle circle-urban" style="top: calc(50% - var(--orbit-3)); left: 50%;" data-modal="theme1">
        <div class="planet-content">
            Urban Aesthetics
        </div>
    </div>
    
    <div class="planet-node node-circle circle-hostile" style="top: calc(50% - var(--orbit-3) * 0.5); left: calc(50% + var(--orbit-3) * 0.87);" data-modal="theme2">
        <div class="planet-content">
            Hostile Design
        </div>
    </div>
    
    <div class="planet-node node-circle circle-species" style="top: calc(50% + var(--orbit-3) * 0.5); left: calc(50% + var(--orbit-3) * 0.87);" data-modal="theme3">
        <div class="planet-content">
            Multispecies Justice
        </div>
    </div>
    
    <div class="planet-node node-circle circle-research" style="top: calc(50% + var(--orbit-3)); left: 50%;" data-modal="theme4">
        <div class="planet-content">
            Embodied Research
        </div>
    </div>
    
    <div class="planet-node node-circle circle-sensory" style="top: calc(50% + var(--orbit-3) * 0.5); left: calc(50% - var(--orbit-3) * 0.87);" data-modal="theme5">
        <div class="planet-content">
            Sensory Translation
        </div>
    </div>
    
    <div class="planet-node node-circle circle-environment" style="top: calc(50% - var(--orbit-3) * 0.5); left: calc(50% - var(--orbit-3) * 0.87);" data-modal="theme6">
        <div class="planet-content">
            Environmental Empathy
        </div>
    </div>
    
    <!-- ===== ANILLO 4: ACCIONES ===== -->
    <div class="planet-node node-ring ring-amber" style="top: calc(50% - var(--orbit-4) * 0.87); left: calc(50% + var(--orbit-4) * 0.5);" data-modal="action1">
        <div class="planet-content">
            Sitting on hostile architecture
        </div>
    </div>
    
    <div class="planet-node node-ring ring-green" style="top: calc(50% + var(--orbit-4) * 0.87); left: calc(50% + var(--orbit-4) * 0.5);" data-modal="action2">
        <div class="planet-content">
            Returning Life
        </div>
    </div>
    
    <div class="planet-node node-ring ring-red" style="top: calc(50% + var(--orbit-4) * 0.87); left: calc(50% - var(--orbit-4) * 0.5);" data-modal="action3">
        <div class="planet-content">
            Wearing Hostility
        </div>
    </div>
    
    <div class="planet-node node-ring ring-blue" style="top: calc(50% - var(--orbit-4) * 0.87); left: calc(50% - var(--orbit-4) * 0.5);" data-modal="action4">
        <div class="planet-content">
            Sensory experiments
        </div>
    </div>
    
    <!-- ===== ANILLO 5: FUTUROS EMERGENTES ===== -->
    <div class="planet-node node-star" style="top: calc(50% - var(--orbit-5) * 0.7); left: calc(50% + var(--orbit-5) * 0.7);" data-modal="future1">
        <div class="planet-content">
            Multispecies perception
        </div>
    </div>
    
    <div class="planet-node node-star" style="top: calc(50% + var(--orbit-5) * 0.7); left: calc(50% + var(--orbit-5) * 0.7);" data-modal="future2">
        <div class="planet-content">
            Sensory translation interfaces
        </div>
    </div>
    
    <div class="planet-node node-star" style="top: calc(50% + var(--orbit-5) * 0.7); left: calc(50% - var(--orbit-5) * 0.7);" data-modal="future3">
        <div class="planet-content">
            Empathy-driven environmental design
        </div>
    </div>
    
    <div class="planet-node node-star" style="top: calc(50% - var(--orbit-5) * 0.7); left: calc(50% - var(--orbit-5) * 0.7);" data-modal="future4">
        <div class="planet-content">
            Awareness → empathy → action
        </div>
    </div>
    
    <!-- Micro-luces distribuidas -->
    <div id="microLights"></div>
    
    <!-- Contenedor de conexiones -->
    <div id="expandedConnections"></div>
</div>

<!-- =============================================== -->
<!-- JAVASCRIPT OPTIMIZADO -->
<!-- =============================================== -->

<script>
// Crear micro-luces distribuidas
function createMicroLights() {
    const container = document.getElementById('microLights');
    const numLights = 60;
    
    for (let i = 0; i < numLights; i++) {
        const light = document.createElement('div');
        light.className = 'node-micro';
        light.style.cssText = `
            --i: ${i};
            top: ${Math.random() * 100}%;
            left: ${Math.random() * 100}%;
            background: ${Math.random() > 0.7 ? 'var(--data-blue)' : 
                        Math.random() > 0.5 ? 'var(--species-violet)' : 
                        Math.random() > 0.3 ? 'var(--bee-yellow)' : 'var(--fog-white)'};
        `;
        container.appendChild(light);
    }
}

// Crear conexiones
function createConnections() {
    const container = document.getElementById('expandedConnections');
    
    // Conexiones del núcleo a los diamantes (intuiciones)
    const core = document.querySelector('.node-core');
    const diamonds = document.querySelectorAll('.node-diamond');
    
    diamonds.forEach(diamond => {
        createConnection(core, diamond, 'connection-strong');
    });
    
    // Conexiones entre anillos adyacentes
    connectLayers('.node-diamond', '.node-hexagon', 'connection-line');
    connectLayers('.node-hexagon', '.node-circle', 'connection-curved');
    connectLayers('.node-circle', '.node-ring', 'connection-strong');
    connectLayers('.node-ring', '.node-star', 'connection-curved');
    
    // Conexiones temáticas específicas
    createSpecificConnection('theme1', 'theme2');
    createSpecificConnection('theme2', 'theme3');
    createSpecificConnection('theme3', 'theme5');
    createSpecificConnection('action1', 'theme2');
    createSpecificConnection('action2', 'theme3');
}

function connectLayers(selector1, selector2, className) {
    const nodes1 = document.querySelectorAll(selector1);
    const nodes2 = document.querySelectorAll(selector2);
    
    nodes1.forEach(node1 => {
        // Conectar a los 2-3 nodos más cercanos
        const closest = Array.from(nodes2)
            .map(node2 => ({
                node: node2,
                distance: calculateDistance(node1, node2)
            }))
            .sort((a, b) => a.distance - b.distance)
            .slice(0, Math.floor(Math.random() * 2) + 2); // 2-3 conexiones
        
        closest.forEach(({node}) => {
            createConnection(node1, node, className);
        });
    });
}

function createSpecificConnection(id1, id2) {
    const node1 = document.querySelector(`[data-modal="${id1}"]`);
    const node2 = document.querySelector(`[data-modal="${id2}"]`);
    
    if (node1 && node2) {
        createConnection(node1, node2, 'connection-strong');
    }
}

function calculateDistance(node1, node2) {
    const rect1 = node1.getBoundingClientRect();
    const rect2 = node2.getBoundingClientRect();
    
    const x1 = rect1.left + rect1.width / 2;
    const y1 = rect1.top + rect1.height / 2;
    const x2 = rect2.left + rect2.width / 2;
    const y2 = rect2.top + rect2.height / 2;
    
    return Math.sqrt(Math.pow(x2 - x1, 2) + Math.pow(y2 - y1, 2));
}

function createConnection(node1, node2, className) {
    const line = document.createElement('div');
    line.className = `connection-line ${className}`;
    
    const rect1 = node1.getBoundingClientRect();
    const rect2 = node2.getBoundingClientRect();
    const container = document.querySelector('.expanded-constellation').getBoundingClientRect();
    
    const x1 = rect1.left + rect1.width / 2 - container.left;
    const y1 = rect1.top + rect1.height / 2 - container.top;
    const x2 = rect2.left + rect2.width / 2 - container.left;
    const y2 = rect2.top + rect2.height / 2 - container.top;
    
    const dx = x2 - x1;
    const dy = y2 - y1;
    const distance = Math.sqrt(dx * dx + dy * dy);
    const angle = Math.atan2(dy, dx) * 180 / Math.PI;
    
    line.style.width = `${distance}px`;
    line.style.left = `${x1}px`;
    line.style.top = `${y1}px`;
    line.style.transform = `rotate(${angle}deg)`;
    
    document.getElementById('expandedConnections').appendChild(line);
}

// Efectos hover mejorados
function setupHoverEffects() {
    const nodes = document.querySelectorAll('.planet-node');
    
    nodes.forEach(node => {
        node.addEventListener('mouseenter', function() {
            this.style.zIndex = '100';
            
            // Resaltar conexiones relacionadas
            document.querySelectorAll('.connection-line').forEach(line => {
                line.style.opacity = '0.1';
            });
            
            // Encontrar conexiones desde/hacia este nodo
            const rect1 = this.getBoundingClientRect();
            const centerX1 = rect1.left + rect1.width / 2;
            const centerY1 = rect1.top + rect1.height / 2;
            
            document.querySelectorAll('.connection-line').forEach(line => {
                const rect2 = line.getBoundingClientRect();
                const centerX2 = rect2.left + rect2.width / 2;
                const centerY2 = rect2.top + rect2.height / 2;
                
                const distance = Math.sqrt(
                    Math.pow(centerX2 - centerX1, 2) + 
                    Math.pow(centerY2 - centerY1, 2)
                );
                
                if (distance < 300) { // Radio de influencia
                    line.style.opacity = '0.6';
                    line.style.filter = 'brightness(1.5)';
                }
            });
        });
        
        node.addEventListener('mouseleave', function() {
            this.style.zIndex = '';
            
            // Restaurar conexiones
            document.querySelectorAll('.connection-line').forEach(line => {
                line.style.opacity = '';
                line.style.filter = '';
            });
        });
    });
}

// Inicialización
window.addEventListener('load', () => {
    createMicroLights();
    createConnections();
    setupHoverEffects();
    
    // Ajustar dinámicamente el tamaño del contenedor
    const container = document.querySelector('.expanded-constellation');
    const resizeObserver = new ResizeObserver(() => {
        document.getElementById('expandedConnections').innerHTML = '';
        createConnections();
    });
    
    resizeObserver.observe(container);
});

// Redimensionar
window.addEventListener('resize', () => {
    document.getElementById('expandedConnections').innerHTML = '';
    createConnections();
});
</script>