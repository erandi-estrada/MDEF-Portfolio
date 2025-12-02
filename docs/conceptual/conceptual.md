<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<!-- =============================================== -->
<!-- CONSTELACIÓN EXPANDIDA - FASE 2 -->
<!-- =============================================== -->

<style>
    /* Variables de color y espacio */
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
        
        /* Gradientes */
        --gradient-core: linear-gradient(135deg, var(--data-blue) 0%, var(--bee-yellow) 100%);
        --gradient-violet-red: linear-gradient(135deg, var(--species-violet) 0%, var(--toxicity-red) 100%);
        --gradient-emergent: linear-gradient(135deg, var(--emergent-blue) 0%, var(--ecosystem-green) 100%);
        
        /* Tamaños de órbitas */
        --orbit-1: 120px;  /* Intuiciones */
        --orbit-2: 200px;  /* Preguntas */
        --orbit-3: 320px;  /* Campos teóricos */
        --orbit-4: 460px;  /* Acciones */
        --orbit-5: 600px;  /* Futuros */
    }
    
    /* Contenedor principal */
    .expanded-constellation {
        position: relative;
        width: 100%;
        height: 100vh;
        min-height: 900px;
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
            radial-gradient(1px 1px at 10% 15%, rgba(255, 255, 255, 0.15) 1px, transparent 0),
            radial-gradient(1px 1px at 20% 45%, rgba(255, 221, 0, 0.2) 1px, transparent 0),
            radial-gradient(1.5px 1.5px at 30% 75%, rgba(138, 63, 252, 0.15) 1px, transparent 0),
            radial-gradient(2px 2px at 40% 25%, rgba(28, 100, 242, 0.2) 1px, transparent 0),
            radial-gradient(1px 1px at 50% 55%, rgba(255, 242, 242, 0.1) 1px, transparent 0),
            radial-gradient(1.5px 1.5px at 60% 85%, rgba(255, 46, 136, 0.15) 1px, transparent 0),
            radial-gradient(2px 2px at 70% 35%, rgba(0, 212, 255, 0.15) 1px, transparent 0),
            radial-gradient(1px 1px at 80% 65%, rgba(0, 196, 154, 0.2) 1px, transparent 0),
            radial-gradient(1.5px 1.5px at 90% 15%, rgba(255, 159, 28, 0.15) 1px, transparent 0);
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
        opacity: 0.1;
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
        opacity: 0.15;
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
        opacity: 0.2;
    }
    
    @keyframes orbit-rotate {
        from { transform: translate(-50%, -50%) rotate(0deg); }
        to { transform: translate(-50%, -50%) rotate(360deg); }
    }
    
    /* ===== TIPOS DE NODOS ===== */
    
    /* Nodo central - El corazón */
    .node-core {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 180px;
        height: 180px;
        border-radius: 50%;
        background: var(--gradient-core);
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        z-index: 100;
        box-shadow: 
            0 0 80px rgba(28, 100, 242, 0.5),
            inset 0 0 40px rgba(255, 255, 255, 0.3);
        animation: core-pulse 6s ease-in-out infinite;
        transition: all 0.4s ease;
    }
    
    .node-core:hover {
        transform: translate(-50%, -50%) scale(1.1);
        box-shadow: 
            0 0 120px rgba(28, 100, 242, 0.7),
            inset 0 0 60px rgba(255, 255, 255, 0.5);
    }
    
    @keyframes core-pulse {
        0%, 100% { 
            box-shadow: 
                0 0 80px rgba(28, 100, 242, 0.5),
                inset 0 0 40px rgba(255, 255, 255, 0.3);
        }
        50% { 
            box-shadow: 
                0 0 100px rgba(28, 100, 242, 0.7),
                inset 0 0 50px rgba(255, 255, 255, 0.4);
        }
    }
    
    /* Rombo - Intuiciones */
    .node-diamond {
        width: 80px;
        height: 80px;
        background: var(--magenta-intuition);
        clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
        cursor: pointer;
        position: absolute;
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 90;
        transition: all 0.3s ease;
        animation: diamond-float 8s ease-in-out infinite;
    }
    
    @keyframes diamond-float {
        0%, 100% { transform: translateY(0px); }
        50% { transform: translateY(-5px); }
    }
    
    /* Hexágono - Preguntas */
    .node-hexagon {
        width: 70px;
        height: 70px;
        background: rgba(242, 242, 242, 0.95);
        clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
        cursor: pointer;
        position: absolute;
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 80;
        color: var(--black-phosphor);
        font-weight: 600;
        font-size: 0.75rem;
        text-align: center;
        padding: 0.5rem;
        transition: all 0.3s ease;
        animation: hexagon-rotate 20s linear infinite;
    }
    
    @keyframes hexagon-rotate {
        from { transform: rotate(0deg); }
        to { transform: rotate(360deg); }
    }
    
    /* Círculo - Campos teóricos */
    .node-circle {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        cursor: pointer;
        position: absolute;
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 70;
        color: var(--black-phosphor);
        font-weight: 700;
        text-align: center;
        padding: 1rem;
        transition: all 0.3s ease;
        animation: circle-breathe 10s ease-in-out infinite;
    }
    
    @keyframes circle-breathe {
        0%, 100% { transform: scale(1); }
        50% { transform: scale(1.05); }
    }
    
    /* Anillo doble - Acciones */
    .node-ring {
        width: 90px;
        height: 90px;
        border-radius: 50%;
        cursor: pointer;
        position: absolute;
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 60;
        background: transparent;
        border: 3px solid;
        box-shadow: 
            inset 0 0 20px rgba(255, 255, 255, 0.2),
            0 0 30px currentColor;
        transition: all 0.3s ease;
        animation: ring-pulse 4s ease-in-out infinite;
    }
    
    @keyframes ring-pulse {
        0%, 100% { 
            box-shadow: 
                inset 0 0 20px rgba(255, 255, 255, 0.2),
                0 0 30px currentColor;
        }
        50% { 
            box-shadow: 
                inset 0 0 30px rgba(255, 255, 255, 0.3),
                0 0 50px currentColor;
        }
    }
    
    /* Estrella - Futuros emergentes */
    .node-star {
        width: 80px;
        height: 80px;
        background: var(--gradient-emergent);
        clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        cursor: pointer;
        position: absolute;
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 50;
        animation: star-sparkle 3s ease-in-out infinite;
    }
    
    @keyframes star-sparkle {
        0%, 100% { opacity: 0.9; transform: scale(1); }
        50% { opacity: 1; transform: scale(1.1); }
    }
    
    /* Micro-luces - Conexiones laterales */
    .node-micro {
        width: 12px;
        height: 12px;
        border-radius: 50%;
        position: absolute;
        background: var(--fog-white);
        opacity: 0.4;
        z-index: 40;
        animation: micro-twinkle 2s ease-in-out infinite;
        animation-delay: calc(var(--i) * 0.1s);
    }
    
    @keyframes micro-twinkle {
        0%, 100% { opacity: 0.2; transform: scale(1); }
        50% { opacity: 0.6; transform: scale(1.3); }
    }
    
    /* ===== CONEXIONES ===== */
    
    .connection-line {
        position: absolute;
        height: 2px;
        background: linear-gradient(90deg, transparent, var(--fog-white), transparent);
        transform-origin: 0 0;
        z-index: 30;
        opacity: 0.15;
        transition: opacity 0.3s ease;
    }
    
    .connection-strong {
        height: 3px;
        background: linear-gradient(90deg, var(--data-blue), var(--ecosystem-green));
        opacity: 0.3;
    }
    
    .connection-curved {
        height: 2px;
        background: linear-gradient(90deg, var(--species-violet), var(--magenta-intuition));
        border-radius: 50%;
        opacity: 0.2;
    }
    
    /* ===== MODAL MEJORADO ===== */
    
    .expanded-modal {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(5, 5, 9, 0.98);
        display: none;
        align-items: center;
        justify-content: center;
        z-index: 10000;
        backdrop-filter: blur(10px);
    }
    
    .expanded-modal.active {
        display: flex;
        animation: modal-appear 0.3s ease-out;
    }
    
    @keyframes modal-appear {
        from { opacity: 0; backdrop-filter: blur(0px); }
        to { opacity: 1; backdrop-filter: blur(10px); }
    }
    
    .modal-content-expanded {
        background: rgba(5, 5, 9, 0.9);
        border-radius: 24px;
        padding: 3rem;
        max-width: 800px;
        width: 90%;
        max-height: 85vh;
        overflow-y: auto;
        border: 1px solid rgba(242, 242, 242, 0.15);
        box-shadow: 
            0 0 100px rgba(28, 100, 242, 0.3),
            0 20px 60px rgba(0, 0, 0, 0.5);
        position: relative;
    }
    
    .modal-close-expanded {
        position: absolute;
        top: 1.5rem;
        right: 1.5rem;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        background: rgba(242, 242, 242, 0.1);
        border: none;
        color: var(--fog-white);
        font-size: 1.5rem;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.3s ease;
    }
    
    .modal-close-expanded:hover {
        background: rgba(242, 242, 242, 0.2);
        transform: rotate(90deg);
    }
    
    /* Leyenda interactiva */
    .constellation-legend {
        position: absolute;
        bottom: 2rem;
        right: 2rem;
        background: rgba(5, 5, 9, 0.85);
        border: 1px solid rgba(242, 242, 242, 0.1);
        border-radius: 16px;
        padding: 1.5rem;
        z-index: 200;
        backdrop-filter: blur(10px);
        max-width: 250px;
        animation: legend-appear 0.5s ease-out;
    }
    
    @keyframes legend-appear {
        from { transform: translateY(20px); opacity: 0; }
        to { transform: translateY(0); opacity: 1; }
    }
    
    .legend-title {
        color: var(--data-blue);
        font-size: 0.9rem;
        font-weight: 600;
        margin-bottom: 1rem;
        text-transform: uppercase;
        letter-spacing: 1px;
    }
    
    .legend-item {
        display: flex;
        align-items: center;
        margin-bottom: 0.8rem;
        font-size: 0.85rem;
        opacity: 0.9;
    }
    
    .legend-shape {
        width: 20px;
        height: 20px;
        margin-right: 0.8rem;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    
    /* Responsive */
    @media (max-width: 1200px) {
        :root {
            --orbit-1: 100px;
            --orbit-2: 170px;
            --orbit-3: 270px;
            --orbit-4: 380px;
            --orbit-5: 500px;
        }
        
        .node-core { width: 150px; height: 150px; }
    }
    
    @media (max-width: 768px) {
        .expanded-constellation {
            height: 700px;
            min-height: 700px;
        }
        
        :root {
            --orbit-1: 80px;
            --orbit-2: 140px;
            --orbit-3: 220px;
            --orbit-4: 300px;
            --orbit-5: 400px;
        }
        
        .node-core { width: 120px; height: 120px; font-size: 0.9rem; }
        .node-diamond { width: 60px; height: 60px; }
        .node-hexagon { width: 55px; height: 55px; font-size: 0.65rem; }
        .node-circle { width: 80px; height: 80px; font-size: 0.8rem; }
        .node-ring { width: 70px; height: 70px; }
        .node-star { width: 60px; height: 60px; }
        
        .constellation-legend {
            display: none;
        }
    }
</style>

<!-- =============================================== -->
<!-- HTML DE LA CONSTELACIÓN -->
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
    <div class="node-core" data-modal="core">
        <div style="text-align: center; padding: 1.5rem;">
            <div style="font-size: 1.4rem; font-weight: 800; margin-bottom: 0.5rem;">THE INVISIBLE CITY</div>
            <div style="font-size: 0.8rem; opacity: 0.9;">Violence hidden under aesthetics</div>
        </div>
    </div>
    
    <!-- ===== ANILLO 1: INTUICIONES ===== -->
    <div class="node-diamond" style="top: calc(50% - var(--orbit-1) * 0.7); left: 50%; transform: translate(-50%, -50%); background: var(--magenta-intuition);" data-modal="intuition1">
        <div style="transform: rotate(45deg); text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600;">Beauty that excludes</div>
    </div>
    
    <div class="node-diamond" style="top: 50%; left: calc(50% + var(--orbit-1) * 0.7); transform: translate(-50%, -50%); background: #FF4DA6;" data-modal="intuition2">
        <div style="transform: rotate(45deg); text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600;">Violence as absence</div>
    </div>
    
    <div class="node-diamond" style="top: calc(50% + var(--orbit-1) * 0.7); left: 50%; transform: translate(-50%, -50%); background: #FF6AB8;" data-modal="intuition3">
        <div style="transform: rotate(45deg); text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600;">Nature expelled</div>
    </div>
    
    <div class="node-diamond" style="top: 50%; left: calc(50% - var(--orbit-1) * 0.7); transform: translate(-50%, -50%); background: #FF88CC;" data-modal="intuition4">
        <div style="transform: rotate(45deg); text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600;">Order as ideology</div>
    </div>
    
    <!-- ===== ANILLO 2: PREGUNTAS ===== -->
    <div class="node-hexagon" style="top: calc(50% - var(--orbit-2) * 0.9); left: 50%; transform: translate(-50%, -50%);" data-modal="question1">
        What bodies can rest?
    </div>
    
    <div class="node-hexagon" style="top: calc(50% - var(--orbit-2) * 0.45); left: calc(50% + var(--orbit-2) * 0.78); transform: translate(-50%, -50%);" data-modal="question2">
        Whose lives are allowed?
    </div>
    
    <div class="node-hexagon" style="top: calc(50% + var(--orbit-2) * 0.45); left: calc(50% + var(--orbit-2) * 0.78); transform: translate(-50%, -50%);" data-modal="question3">
        How does beauty justify exclusion?
    </div>
    
    <div class="node-hexagon" style="top: calc(50% + var(--orbit-2) * 0.9); left: 50%; transform: translate(-50%, -50%);" data-modal="question4">
        Can design generate empathy?
    </div>
    
    <div class="node-hexagon" style="top: calc(50% + var(--orbit-2) * 0.45); left: calc(50% - var(--orbit-2) * 0.78); transform: translate(-50%, -50%);" data-modal="question5">
        What violence is invisible?
    </div>
    
    <div class="node-hexagon" style="top: calc(50% - var(--orbit-2) * 0.45); left: calc(50% - var(--orbit-2) * 0.78); transform: translate(-50%, -50%);" data-modal="question6">
        How would species design cities?
    </div>
    
    <!-- ===== ANILLO 3: CAMPOS TEÓRICOS ===== -->
    <div class="node-circle" style="top: calc(50% - var(--orbit-3)); left: 50%; transform: translate(-50%, -50%); background: var(--species-violet);" data-modal="theme1">
        Urban Aesthetics
    </div>
    
    <div class="node-circle" style="top: calc(50% - var(--orbit-3) * 0.5); left: calc(50% + var(--orbit-3) * 0.87); transform: translate(-50%, -50%); background: var(--hostility-amber);" data-modal="theme2">
        Hostile Design
    </div>
    
    <div class="node-circle" style="top: calc(50% + var(--orbit-3) * 0.5); left: calc(50% + var(--orbit-3) * 0.87); transform: translate(-50%, -50%); background: var(--bee-yellow);" data-modal="theme3">
        Multispecies Justice
    </div>
    
    <div class="node-circle" style="top: calc(50% + var(--orbit-3)); left: 50%; transform: translate(-50%, -50%); background: var(--ecosystem-green);" data-modal="theme4">
        Embodied Research
    </div>
    
    <div class="node-circle" style="top: calc(50% + var(--orbit-3) * 0.5); left: calc(50% - var(--orbit-3) * 0.87); transform: translate(-50%, -50%); background: var(--toxicity-red); color: var(--fog-white);" data-modal="theme5">
        Sensory Translation
    </div>
    
    <div class="node-circle" style="top: calc(50% - var(--orbit-3) * 0.5); left: calc(50% - var(--orbit-3) * 0.87); transform: translate(-50%, -50%); background: var(--data-blue); color: var(--fog-white);" data-modal="theme6">
        Environmental Empathy
    </div>
    
    <!-- ===== ANILLO 4: ACCIONES ===== -->
    <div class="node-ring" style="top: calc(50% - var(--orbit-4) * 0.87); left: calc(50% + var(--orbit-4) * 0.5); transform: translate(-50%, -50%); border-color: var(--hostility-amber); color: var(--hostility-amber);" data-modal="action1">
        <div style="text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600;">Sitting on hostile architecture</div>
    </div>
    
    <div class="node-ring" style="top: calc(50% + var(--orbit-4) * 0.87); left: calc(50% + var(--orbit-4) * 0.5); transform: translate(-50%, -50%); border-color: var(--ecosystem-green); color: var(--ecosystem-green);" data-modal="action2">
        <div style="text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600;">Returning Life</div>
    </div>
    
    <div class="node-ring" style="top: calc(50% + var(--orbit-4) * 0.87); left: calc(50% - var(--orbit-4) * 0.5); transform: translate(-50%, -50%); border-color: var(--toxicity-red); color: var(--toxicity-red);" data-modal="action3">
        <div style="text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600;">Wearing Hostility</div>
    </div>
    
    <div class="node-ring" style="top: calc(50% - var(--orbit-4) * 0.87); left: calc(50% - var(--orbit-4) * 0.5); transform: translate(-50%, -50%); border-color: var(--data-blue); color: var(--data-blue);" data-modal="action4">
        <div style="text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600;">Sensory experiments</div>
    </div>
    
    <!-- ===== ANILLO 5: FUTUROS EMERGENTES ===== -->
    <div class="node-star" style="top: calc(50% - var(--orbit-5) * 0.7); left: calc(50% + var(--orbit-5) * 0.7); transform: translate(-50%, -50%);" data-modal="future1">
        <div style="text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600; color: var(--fog-white);">Multispecies perception</div>
    </div>
    
    <div class="node-star" style="top: calc(50% + var(--orbit-5) * 0.7); left: calc(50% + var(--orbit-5) * 0.7); transform: translate(-50%, -50%);" data-modal="future2">
        <div style="text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600; color: var(--fog-white);">Sensory translation interfaces</div>
    </div>
    
    <div class="node-star" style="top: calc(50% + var(--orbit-5) * 0.7); left: calc(50% - var(--orbit-5) * 0.7); transform: translate(-50%, -50%);" data-modal="future3">
        <div style="text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600; color: var(--fog-white);">Empathy-driven environmental design</div>
    </div>
    
    <div class="node-star" style="top: calc(50% - var(--orbit-5) * 0.7); left: calc(50% - var(--orbit-5) * 0.7); transform: translate(-50%, -50%);" data-modal="future4">
        <div style="text-align: center; padding: 1rem; font-size: 0.8rem; font-weight: 600; color: var(--fog-white);">From awareness → empathy → action</div>
    </div>
    
    <!-- Micro-luces distribuidas -->
    <div id="microLights"></div>
    
    <!-- Contenedor de conexiones -->
    <div id="expandedConnections"></div>
    
    <!-- Leyenda interactiva -->
    <div class="constellation-legend" id="constellationLegend">
        <div class="legend-title">Constellation Map Key</div>
        <div class="legend-item">
            <div class="legend-shape" style="background: var(--gradient-core); border-radius: 50%;"></div>
            <span>Core Concept</span>
        </div>
        <div class="legend-item">
            <div class="legend-shape" style="background: var(--magenta-intuition); clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);"></div>
            <span>Intuitions</span>
        </div>
        <div class="legend-item">
            <div class="legend-shape" style="background: var(--fog-white); clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);"></div>
            <span>Motor Questions</span>
        </div>
        <div class="legend-item">
            <div class="legend-shape" style="background: var(--species-violet); border-radius: 50%;"></div>
            <span>Thematic Fields</span>
        </div>
        <div class="legend-item">
            <div class="legend-shape" style="border: 2px solid var(--hostility-amber); border-radius: 50%;"></div>
            <span>Actions as Knowledge</span>
        </div>
        <div class="legend-item">
            <div class="legend-shape" style="background: var(--gradient-emergent); clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);"></div>
            <span>Emergent Futures</span>
        </div>
    </div>
</div>

<!-- Modal expandido -->
<div class="expanded-modal" id="expandedModal">
    <div class="modal-content-expanded">
        <button class="modal-close-expanded" id="modalCloseExpanded">×</button>
        <h3 id="modalTitleExpanded" style="font-size: 2rem; margin-bottom: 1rem; color: var(--data-blue);"></h3>
        <div id="modalBodyExpanded" style="line-height: 1.7; font-size: 1.1rem;"></div>
        <div id="modalConnections" style="margin-top: 2rem; padding-top: 1.5rem; border-top: 1px solid rgba(242, 242, 242, 0.1);"></div>
    </div>
</div>

<!-- =============================================== -->
<!-- JAVASCRIPT DE LA CONSTELACIÓN EXPANDIDA -->
<!-- =============================================== -->

<script>
// Datos completos de la constelación
const expandedData = {
    core: {
        title: "🌌 THE INVISIBLE CITY",
        content: `
            <p style="font-size: 1.3rem; font-style: italic; color: var(--fog-white); margin-bottom: 2rem;">
                "The city looks beautiful, but its beauty hides systematic violence against both humans and non-human life."
            </p>
            <p><strong>Core intuition:</strong> This is the gravitational center of your conceptual universe — where aesthetics meets ethics, where visibility hides violence.</p>
            
            <div style="margin: 2rem 0;">
                <h4 style="color: var(--magenta-intuition); margin-bottom: 1rem;">Sub-intuitions:</h4>
                <ul style="list-style: none; padding-left: 0;">
                    <li style="padding: 0.5rem 0; border-bottom: 1px solid rgba(242, 242, 242, 0.1);">✦ <strong>Beauty as control</strong> – How aesthetic standards become tools of power and exclusion</li>
                    <li style="padding: 0.5rem 0; border-bottom: 1px solid rgba(242, 242, 242, 0.1);">✦ <strong>Violence as absence</strong> – The violence of what is systematically removed or made invisible</li>
                    <li style="padding: 0.5rem 0; border-bottom: 1px solid rgba(242, 242, 242, 0.1);">✦ <strong>Life expelled from the urban image</strong> – The exclusion of non-curated life from the city's self-representation</li>
                </ul>
            </div>
            
            <p>This node connects to <strong>all layers</strong> of the constellation, serving as the origin point for your research trajectory.</p>
        `,
        connections: ["intuition1", "intuition2", "intuition3", "intuition4", "theme1", "theme2"]
    },
    
    intuition1: {
        title: "◆ Beauty That Excludes",
        content: `
            <p><strong>Initial emotional intuition:</strong> The realization that what we call "beautiful" in cities often systematically excludes certain lives.</p>
            
            <div style="background: rgba(255, 46, 136, 0.1); padding: 1.5rem; border-radius: 12px; margin: 1.5rem 0;">
                <p><em>"When a space is designed to look clean, orderly, and aesthetically pleasing, who pays the price? Whose presence becomes 'dirt' or 'disorder'?"</em></p>
            </div>
            
            <p><strong>Leads to:</strong> Questions about aesthetic standards, investigations into hostile design, and actions that make exclusion visible.</p>
        `,
        connections: ["core", "question2", "theme1", "action3"]
    },
    
    theme1: {
        title: "● Urban Aesthetics",
        content: `
            <p><strong>Thematic field:</strong> How aesthetic standards in urban design serve to normalize exclusion and control.</p>
            
            <h4 style="color: var(--species-violet); margin: 1.5rem 0 1rem 0;">Key concepts:</h4>
            <ul style="columns: 2; list-style: none; padding-left: 0;">
                <li style="padding: 0.3rem 0;">▸ Beauty as ideology</li>
                <li style="padding: 0.3rem 0;">▸ Cleanliness as political tool</li>
                <li style="padding: 0.3rem 0;">▸ City as spectacle</li>
                <li style="padding: 0.3rem 0;">▸ Nature as decoration</li>
                <li style="padding: 0.3rem 0;">▸ Controlled public space</li>
                <li style="padding: 0.3rem 0;">▸ Aesthetic erasure</li>
                <li style="padding: 0.3rem 0;">▸ Order vs Life</li>
                <li style="padding: 0.3rem 0;">▸ Visual politics</li>
            </ul>
            
            <p><strong>Connection to practice:</strong> This field informs interventions that challenge aesthetic norms and reveal their exclusionary effects.</p>
        `,
        connections: ["intuition1", "question2", "theme2", "action1"]
    },
    
    action1: {
        title: "🔵 Sitting on Hostile Architecture",
        content: `
            <p><strong>Action as knowledge:</strong> An embodied investigation that reveals normalized micro-violence through direct physical engagement.</p>
            
            <div style="background: rgba(255, 159, 28, 0.1); padding: 1.5rem; border-radius: 12px; margin: 1.5rem 0;">
                <h4 style="color: var(--hostility-amber); margin-bottom: 0.5rem;">What this action reveals:</h4>
                <ul style="list-style: none; padding-left: 0;">
                    <li style="padding: 0.3rem 0;">▸ Human discomfort exposes architectural hostility</li>
                    <li style="padding: 0.3rem 0;">▸ The body becomes a sensor for urban violence</li>
                    <li style="padding: 0.3rem 0;">▸ What feels "normal" when observed becomes painful when experienced</li>
                    <li style="padding: 0.3rem 0;">▸ Public space is designed for movement, not rest</li>
                </ul>
            </div>
            
            <p><strong>Methodological insight:</strong> By physically occupying hostile designs, this action makes visible the normalized violence of urban furniture and creates moments of cognitive dissonance for observers.</p>
        `,
        connections: ["theme1", "theme2", "question1", "theme4"]
    },
    
    future1: {
        title: "★ Multispecies Perception",
        content: `
            <p><strong>Emergent direction:</strong> Developing interfaces and methods for perceiving urban environments through non-human sensory modalities.</p>
            
            <div style="background: rgba(0, 212, 255, 0.1); padding: 1.5rem; border-radius: 12px; margin: 1.5rem 0;">
                <h4 style="color: var(--emergent-blue); margin-bottom: 0.5rem;">Research questions:</h4>
                <ul style="list-style: none; padding-left: 0;">
                    <li style="padding: 0.3rem 0;">▸ How do pigeons navigate urban soundscapes?</li>
                    <li style="padding: 0.3rem 0;">▸ What chemical signals do plants exchange in polluted areas?</li>
                    <li style="padding: 0.3rem 0;">▸ How do insects experience temperature gradients in concrete jungles?</li>
                    <li style="padding: 0.3rem 0;">▸ Can we design empathy through sensory translation?</li>
                </ul>
            </div>
            
            <p><strong>Future trajectories:</strong> This direction points toward hybrid interfaces, biomaterial sensors, and participatory methods that expand human perception toward multispecies awareness.</p>
        `,
        connections: ["theme3", "theme5", "future2", "future4"]
    }
};

// Elementos DOM
const expandedModal = document.getElementById('expandedModal');
const modalCloseExpanded = document.getElementById('modalCloseExpanded');
const modalTitleExpanded = document.getElementById('modalTitleExpanded');
const modalBodyExpanded = document.getElementById('modalBodyExpanded');
const modalConnections = document.getElementById('modalConnections');
const nodes = document.querySelectorAll('.node-core, .node-diamond, .node-hexagon, .node-circle, .node-ring, .node-star');
const connectionsContainer = document.getElementById('expandedConnections');
const microLightsContainer = document.getElementById('microLights');

// Crear micro-luces distribuidas
function createMicroLights() {
    const numLights = 50;
    for (let i = 0; i < numLights; i++) {
        const light = document.createElement('div');
        light.className = 'node-micro';
        light.style.cssText = `
            --i: ${i};
            top: ${Math.random() * 100}%;
            left: ${Math.random() * 100}%;
        `;
        microLightsContainer.appendChild(light);
    }
}

// Crear conexiones complejas
function createComplexConnections() {
    // Conexiones radiales desde el núcleo
    connectNodes('.node-core', '.node-diamond', 'connection-line');
    connectNodes('.node-core', '.node-hexagon', 'connection-curved');
    connectNodes('.node-core', '.node-circle', 'connection-strong');
    
    // Conexiones entre anillos
    connectNodes('.node-diamond', '.node-hexagon', 'connection-line');
    connectNodes('.node-hexagon', '.node-circle', 'connection-curved');
    connectNodes('.node-circle', '.node-ring', 'connection-strong');
    connectNodes('.node-ring', '.node-star', 'connection-curved');
    
    // Conexiones temáticas específicas
    createThematicConnection('theme1', 'theme2', 'connection-strong');
    createThematicConnection('theme2', 'theme3', 'connection-curved');
    createThematicConnection('theme3', 'theme5', 'connection-strong');
    createThematicConnection('action1', 'theme2', 'connection-line');
    createThematicConnection('action2', 'theme3', 'connection-line');
}

function connectNodes(selector1, selector2, className) {
    const nodes1 = document.querySelectorAll(selector1);
    const nodes2 = document.querySelectorAll(selector2);
    
    nodes1.forEach(node1 => {
        nodes2.forEach(node2 => {
            if (Math.random() > 0.6) { // Solo algunas conexiones
                createConnection(node1, node2, className);
            }
        });
    });
}

function createThematicConnection(id1, id2, className) {
    const node1 = document.querySelector(`[data-modal="${id1}"]`);
    const node2 = document.querySelector(`[data-modal="${id2}"]`);
    
    if (node1 && node2) {
        createConnection(node1, node2, className);
    }
}

function createConnection(node1, node2, className) {
    const line = document.createElement('div');
    line.className = `connection-line ${className}`;
    
    const rect1 = node1.getBoundingClientRect();
    const rect2 = node2.getBoundingClientRect();
    const container = document.querySelector('.expanded-constellation').getBoundingClientRect();
    
    const x1 = rect1.left + rect1.width/2 - container.left;
    const y1 = rect1.top + rect1.height/2 - container.top;
    const x2 = rect2.left + rect2.width/2 - container.left;
    const y2 = rect2.top + rect2.height/2 - container.top;
    
    // Línea curva (aproximación con Bezier)
    const dx = x2 - x1;
    const dy = y2 - y1;
    const distance = Math.sqrt(dx * dx + dy * dy);
    const angle = Math.atan2(dy, dx) * 180 / Math.PI;
    
    // Curvatura aleatoria para efecto orgánico
    const curve = 30;
    
    line.style.width = `${distance}px`;
    line.style.left = `${x1}px`;
    line.style.top = `${y1}px`;
    line.style.transform = `rotate(${angle}deg)`;
    line.style.borderRadius = '50%';
    
    connectionsContainer.appendChild(line);
}

// Mostrar conexiones en modal
function showConnections(modalId) {
    if (expandedData[modalId] && expandedData[modalId].connections) {
        const connections = expandedData[modalId].connections;
        let html = '<h4 style="color: var(--fog-white); margin-bottom: 1rem;">Strongly connected to:</h4><div style="display: flex; flex-wrap: wrap; gap: 0.5rem;">';
        
        connections.forEach(connId => {
            if (expandedData[connId]) {
                html += `<span style="background: rgba(28, 100, 242, 0.2); padding: 0.5rem 1rem; border-radius: 20px; border: 1px solid rgba(28, 100, 242, 0.3); font-size: 0.9rem;">${expandedData[connId].title}</span>`;
            }
        });
        
        html += '</div>';
        modalConnections.innerHTML = html;
    } else {
        modalConnections.innerHTML = '';
    }
}

// Event Listeners
nodes.forEach(node => {
    node.addEventListener('click', function() {
        const modalId = this.getAttribute('data-modal');
        
        if (expandedData[modalId]) {
            modalTitleExpanded.textContent = expandedData[modalId].title;
            modalBodyExpanded.innerHTML = expandedData[modalId].content;
            showConnections(modalId);
            expandedModal.classList.add('active');
            document.body.style.overflow = 'hidden';
        }
    });
    
    // Efecto hover
    node.addEventListener('mouseenter', function() {
        this.style.zIndex = '200';
        const modalId = this.getAttribute('data-modal');
        
        // Resaltar conexiones
        if (expandedData[modalId] && expandedData[modalId].connections) {
            document.querySelectorAll('.connection-line').forEach(line => {
                line.style.opacity = '0.1';
            });
            
            expandedData[modalId].connections.forEach(connId => {
                const connectedNode = document.querySelector(`[data-modal="${connId}"]`);
                if (connectedNode) {
                    connectedNode.style.filter = 'brightness(1.3)';
                    connectedNode.style.transform = connectedNode.style.transform + ' scale(1.1)';
                }
            });
        }
    });
    
    node.addEventListener('mouseleave', function() {
        this.style.zIndex = '';
        
        // Restaurar estilos
        document.querySelectorAll('.connection-line').forEach(line => {
            line.style.opacity = '0.15';
        });
        
        document.querySelectorAll('.node-core, .node-diamond, .node-hexagon, .node-circle, .node-ring, .node-star').forEach(node => {
            node.style.filter = '';
            const transform = node.style.transform;
            if (transform.includes('scale(1.1)')) {
                node.style.transform = transform.replace(' scale(1.1)', '');
            }
        });
    });
});

modalCloseExpanded.addEventListener('click', () => {
    expandedModal.classList.remove('active');
    document.body.style.overflow = 'auto';
});

expandedModal.addEventListener('click', (e) => {
    if (e.target === expandedModal) {
        expandedModal.classList.remove('active');
        document.body.style.overflow = 'auto';
    }
});

// Leyenda interactiva
const legend = document.getElementById('constellationLegend');
let legendTimeout;

document.getElementById('expandedConstellation').addEventListener('mousemove', (e) => {
    clearTimeout(legendTimeout);
    legend.style.opacity = '1';
    legendTimeout = setTimeout(() => {
        legend.style.opacity = '0.5';
    }, 3000);
});

// Inicialización
window.addEventListener('load', () => {
    createMicroLights();
    createComplexConnections();
});

window.addEventListener('resize', () => {
    connectionsContainer.innerHTML = '';
    createComplexConnections();
});
</script>