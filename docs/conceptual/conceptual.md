<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<!-- =============================================== -->
<!-- MAPA CONSTELACIÓN COMPLETO - ESTÉTICA ESPACIAL -->
<!-- =============================================== -->

<style>
    /* ESTÉTICA GLOBAL - ESPACIO PROFUNDO */
    :root {
        /* Paleta cósmica completa */
        --space-black: #050509;
        --nebula-blue: rgba(28, 100, 242, 0.1);
        --nebula-magenta: rgba(181, 30, 255, 0.08);
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
        
        /* Tamaños de órbitas - 5 niveles */
        --orbit-core: 0px;
        --orbit-intuitions: 160px;
        --orbit-questions: 280px;
        --orbit-themes: 420px;
        --orbit-actions: 580px;
        --orbit-futures: 760px;
    }
    
    /* CONTENEDOR PRINCIPAL - FONDO ESPACIAL */
    .galaxy-constellation {
        position: relative;
        width: 100%;
        height: 130vh;
        min-height: 1100px;
        background: 
            radial-gradient(circle at 20% 30%, var(--nebula-blue) 0%, transparent 50%),
            radial-gradient(circle at 80% 70%, var(--nebula-magenta) 0%, transparent 50%),
            var(--space-black);
        overflow: hidden;
        border-radius: 20px;
        margin: 4rem 0;
        font-family: 'Space Grotesk', 'Inter', -apple-system, sans-serif;
    }
    
    /* TEXTURA DE ESTRELLAS - MULTICAPA */
    .star-field {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-image: 
            radial-gradient(1px 1px at 10% 15%, rgba(255, 255, 255, 0.07) 1px, transparent 0),
            radial-gradient(1px 1px at 20% 45%, rgba(255, 221, 0, 0.05) 1px, transparent 0),
            radial-gradient(1.5px 1.5px at 30% 75%, rgba(138, 63, 252, 0.06) 1px, transparent 0),
            radial-gradient(2px 2px at 40% 25%, rgba(28, 100, 242, 0.07) 1px, transparent 0),
            radial-gradient(1px 1px at 50% 55%, rgba(255, 255, 255, 0.04) 1px, transparent 0),
            radial-gradient(1.5px 1.5px at 60% 85%, rgba(255, 46, 136, 0.06) 1px, transparent 0),
            radial-gradient(2px 2px at 70% 35%, rgba(0, 212, 255, 0.05) 1px, transparent 0),
            radial-gradient(1px 1px at 80% 65%, rgba(0, 196, 154, 0.07) 1px, transparent 0),
            radial-gradient(1.5px 1.5px at 90% 15%, rgba(255, 159, 28, 0.06) 1px, transparent 0),
            radial-gradient(3px 3px at 15% 85%, rgba(181, 30, 255, 0.03) 2px, transparent 0);
        background-size: 400px 400px;
        animation: star-twinkle 20s infinite alternate;
        z-index: 1;
        opacity: 0.7;
    }
    
    @keyframes star-twinkle {
        0%, 100% { opacity: 0.5; }
        25% { opacity: 0.8; }
        50% { opacity: 0.6; }
        75% { opacity: 0.9; }
    }
    
    /* ÓRBITAS - LÍNEAS CIRCULARES TENUES */
    .galaxy-orbit {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 50%;
        border: 1px solid;
        opacity: 0.05;
        z-index: 2;
    }
    
    .orbit-1 { width: var(--orbit-intuitions); height: var(--orbit-intuitions); border-color: var(--magenta-intuition); }
    .orbit-2 { width: var(--orbit-questions); height: var(--orbit-questions); border-color: var(--fog-white); }
    .orbit-3 { width: var(--orbit-themes); height: var(--orbit-themes); border-color: var(--data-blue); opacity: 0.08; }
    .orbit-4 { width: var(--orbit-actions); height: var(--orbit-actions); border-color: var(--amber-hostility); }
    .orbit-5 { width: var(--orbit-futures); height: var(--orbit-futures); border-color: var(--emergent-blue); opacity: 0.06; }
    
    /* ===== SISTEMA DE NODOS - ESTILO PLANETARIO ===== */
    
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
        animation: cosmic-float 8s ease-in-out infinite;
        animation-delay: calc(var(--node-index) * 0.1s);
    }
    
    @keyframes cosmic-float {
        0%, 100% { transform: translate(-50%, -50%) scale(1); }
        50% { transform: translate(-50%, -50%) scale(1.02); }
    }
    
    /* CONTENEDOR DE CONTENIDO */
    .node-content {
        position: relative;
        z-index: 3;
        padding: 1rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
        text-shadow: 0 1px 3px rgba(0, 0, 0, 0.5);
    }
    
    /* ===== TIPOS DE NODOS ESPECÍFICOS ===== */
    
    /* 🌞 NÚCLEO - CÍRCULO GRANDE */
    .node-type-core {
        width: 180px;
        height: 180px;
        border-radius: 50%;
        background: radial-gradient(
            circle at 30% 30%,
            #1C64F2 0%,
            #0A4BCF 15%,
            #003399 35%,
            #001F5C 60%,
            transparent 85%
        );
        box-shadow: 
            inset 0 0 60px rgba(255, 255, 255, 0.4),
            0 0 120px rgba(28, 100, 242, 0.6),
            0 0 40px rgba(255, 221, 0, 0.3);
        color: var(--fog-white);
        font-size: 1.1rem;
        animation: core-pulse 6s ease-in-out infinite;
    }
    
    @keyframes core-pulse {
        0%, 100% { 
            box-shadow: 
                inset 0 0 60px rgba(255, 255, 255, 0.4),
                0 0 120px rgba(28, 100, 242, 0.6),
                0 0 40px rgba(255, 221, 0, 0.3);
        }
        50% { 
            box-shadow: 
                inset 0 0 80px rgba(255, 255, 255, 0.5),
                0 0 160px rgba(28, 100, 242, 0.8),
                0 0 60px rgba(255, 221, 0, 0.4);
        }
    }
    
    /* 💎 INTUICIONES - ROMBOS */
    .node-type-intuition {
        width: 100px;
        height: 100px;
        background: radial-gradient(
            circle at 30% 30%,
            var(--magenta-intuition) 0%,
            #9C1AE6 25%,
            #7A00CC 50%,
            #5800A3 75%,
            transparent 100%
        );
        clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
        color: var(--fog-white);
        font-size: 0.85rem;
        box-shadow: 
            inset 0 0 30px rgba(255, 255, 255, 0.3),
            0 0 50px rgba(181, 30, 255, 0.5);
    }
    
    /* 🧠 PREGUNTAS - HEXÁGONOS */
    .node-type-question {
        width: 90px;
        height: 90px;
        background: radial-gradient(
            circle at 30% 30%,
            rgba(242, 242, 242, 0.95) 0%,
            rgba(217, 217, 217, 0.8) 30%,
            rgba(191, 191, 191, 0.6) 60%,
            rgba(140, 140, 140, 0.4) 90%,
            transparent 100%
        );
        clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
        color: var(--space-black);
        font-size: 0.8rem;
        box-shadow: 
            inset 0 0 25px rgba(255, 255, 255, 0.4),
            0 0 40px rgba(242, 242, 242, 0.4);
    }
    
    /* 🟣 CAMPOS TEÓRICOS - CÍRCULOS GRANDES */
    .node-type-theme {
        width: 120px;
        height: 120px;
        border-radius: 50%;
        color: var(--fog-white);
        font-size: 0.9rem;
        box-shadow: 
            inset 0 0 40px rgba(255, 255, 255, 0.3),
            0 0 60px currentColor;
    }
    
    /* ◉ ACCIONES - CÍRCULO DOBLE BORDE */
    .node-type-action {
        width: 110px;
        height: 110px;
        border-radius: 50%;
        background: transparent;
        border: 3px solid;
        box-shadow: 
            inset 0 0 40px rgba(255, 255, 255, 0.3),
            0 0 60px currentColor;
        color: var(--fog-white);
        font-size: 0.85rem;
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
        opacity: 0.6;
    }
    
    /* ⭐ FUTUROS - ESTRELLAS */
    .node-type-future {
        width: 100px;
        height: 100px;
        background: radial-gradient(
            circle at 30% 30%,
            var(--emergent-blue) 0%,
            #00B8E6 20%,
            #009CCC 40%,
            #007FB3 60%,
            transparent 85%
        );
        clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        color: var(--fog-white);
        font-size: 0.85rem;
        box-shadow: 
            inset 0 0 30px rgba(255, 255, 255, 0.3),
            0 0 50px rgba(0, 212, 255, 0.5);
        animation: star-sparkle 4s ease-in-out infinite;
    }
    
    @keyframes star-sparkle {
        0%, 100% { opacity: 0.9; transform: translate(-50%, -50%) scale(1) rotate(0deg); }
        50% { opacity: 1; transform: translate(-50%, -50%) scale(1.1) rotate(5deg); }
    }
    
    /* ✦ MICRO-NODOS */
    .node-type-micro {
        width: 20px;
        height: 20px;
        border-radius: 50%;
        background: radial-gradient(
            circle at 30% 30%,
            var(--fog-white) 0%,
            rgba(242, 242, 242, 0.6) 50%,
            transparent 80%
        );
        font-size: 0;
        box-shadow: 0 0 15px currentColor;
        animation: micro-pulse 2s ease-in-out infinite;
        animation-delay: calc(var(--micro-index) * 0.2s);
    }
    
    @keyframes micro-pulse {
        0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0.6; }
        50% { transform: translate(-50%, -50%) scale(1.3); opacity: 1; }
    }
    
    /* ===== COLORES ESPECÍFICOS ===== */
    
    /* Temas teóricos */
    .theme-urban { color: var(--violet-injustice); box-shadow: 0 0 60px rgba(138, 63, 252, 0.4); }
    .theme-urban .node-content { color: var(--fog-white); }
    
    .theme-hostile { color: var(--amber-hostility); box-shadow: 0 0 60px rgba(255, 159, 28, 0.4); }
    
    .theme-species { color: var(--pollen-yellow); box-shadow: 0 0 60px rgba(255, 221, 0, 0.4); }
    
    .theme-research { color: var(--eco-green); box-shadow: 0 0 60px rgba(0, 196, 154, 0.4); }
    .theme-research .node-content { color: var(--fog-white); }
    
    .theme-sensory { color: var(--toxicity-red); box-shadow: 0 0 60px rgba(225, 29, 72, 0.4); }
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
    
    /* ===== EFECTOS HOVER ===== */
    
    .cosmic-node:hover {
        z-index: 100 !important;
        transform: translate(-50%, -50%) scale(1.12) !important;
        filter: brightness(1.3) !important;
    }
    
    .node-type-core:hover {
        box-shadow: 
            inset 0 0 100px rgba(255, 255, 255, 0.5),
            0 0 180px rgba(28, 100, 242, 0.9),
            0 0 80px rgba(255, 221, 0, 0.5);
    }
    
    .node-type-intuition:hover {
        box-shadow: 
            inset 0 0 40px rgba(255, 255, 255, 0.4),
            0 0 70px rgba(181, 30, 255, 0.7);
    }
    
    .node-type-future:hover {
        animation: star-sparkle-hover 1s ease-in-out infinite;
    }
    
    @keyframes star-sparkle-hover {
        0%, 100% { opacity: 1; transform: translate(-50%, -50%) scale(1.15) rotate(0deg); }
        50% { opacity: 1; transform: translate(-50%, -50%) scale(1.2) rotate(10deg); }
    }
    
    /* ===== CONEXIONES - 3 TIPOS ===== */
    
    .cosmic-connection {
        position: absolute;
        height: 2px;
        transform-origin: 0 0;
        z-index: 4;
        transition: all 0.3s ease;
    }
    
    /* Línea fuerte */
    .connection-strong {
        height: 3px;
        background: linear-gradient(90deg, 
            var(--violet-injustice) 0%,
            var(--emergent-blue) 100%);
        opacity: 0.4;
        box-shadow: 0 0 15px rgba(138, 63, 252, 0.4);
    }
    
    /* Línea moderada */
    .connection-moderate {
        height: 2px;
        background: linear-gradient(90deg, 
            var(--amber-hostility) 0%,
            var(--pollen-yellow) 100%);
        opacity: 0.3;
        border-radius: 50%;
    }
    
    /* Línea débil */
    .connection-weak {
        height: 1px;
        background: linear-gradient(90deg, 
            rgba(242, 242, 242, 0.5) 0%,
            transparent 100%);
        opacity: 0.2;
        border-style: dashed;
        border-width: 0;
        background-image: repeating-linear-gradient(
            90deg,
            transparent,
            transparent 5px,
            rgba(242, 242, 242, 0.3) 5px,
            rgba(242, 242, 242, 0.3) 10px
        );
    }
    
    /* ===== TOOLTIP ===== */
    
    .cosmic-tooltip {
        position: absolute;
        background: rgba(5, 5, 9, 0.95);
        border: 1px solid rgba(242, 242, 242, 0.15);
        border-radius: 12px;
        padding: 1.2rem 1.5rem;
        max-width: 300px;
        z-index: 1000;
        pointer-events: none;
        opacity: 0;
        transform: translateY(10px);
        transition: all 0.3s ease;
        box-shadow: 
            0 10px 40px rgba(0, 0, 0, 0.5),
            0 0 30px rgba(28, 100, 242, 0.2);
        backdrop-filter: blur(10px);
        color: var(--fog-white);
        font-size: 0.95rem;
        line-height: 1.5;
    }
    
    .cosmic-tooltip.active {
        opacity: 1;
        transform: translateY(0);
    }
    
    .tooltip-title {
        color: var(--data-blue);
        font-weight: 700;
        margin-bottom: 0.5rem;
        font-size: 1rem;
    }
    
    .tooltip-content {
        opacity: 0.9;
        font-weight: 300;
    }
    
    /* ===== LEYENDA INTERACTIVA ===== */
    
    .galaxy-legend {
        position: absolute;
        bottom: 2rem;
        right: 2rem;
        background: rgba(5, 5, 9, 0.9);
        border: 1px solid rgba(242, 242, 242, 0.1);
        border-radius: 16px;
        padding: 1.5rem;
        z-index: 50;
        backdrop-filter: blur(10px);
        max-width: 250px;
        box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
        transition: all 0.3s ease;
    }
    
    .legend-title {
        color: var(--data-blue);
        font-size: 0.9rem;
        font-weight: 600;
        margin-bottom: 1rem;
        text-transform: uppercase;
        letter-spacing: 1px;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
    
    .legend-toggle {
        background: none;
        border: none;
        color: var(--fog-white);
        opacity: 0.6;
        cursor: pointer;
        font-size: 1.2rem;
        line-height: 1;
    }
    
    .legend-content {
        transition: all 0.3s ease;
    }
    
    .legend-item {
        display: flex;
        align-items: center;
        margin-bottom: 0.8rem;
        font-size: 0.85rem;
        opacity: 0.9;
    }
    
    .legend-shape {
        width: 22px;
        height: 22px;
        margin-right: 0.8rem;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 4px;
    }
</style>

<!-- =============================================== -->
<!-- HTML DEL MAPA GALÁCTICO -->
<!-- =============================================== -->

<div class="galaxy-constellation" id="galaxyMap">
    <!-- Fondo estrellado -->
    <div class="star-field"></div>
    
    <!-- Órbitas -->
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
    
    <!-- Tooltip -->
    <div class="cosmic-tooltip" id="cosmicTooltip">
        <div class="tooltip-title" id="tooltipTitle"></div>
        <div class="tooltip-content" id="tooltipContent"></div>
    </div>
    
    <!-- Leyenda -->
    <div class="galaxy-legend" id="galaxyLegend">
        <div class="legend-title">
            <span>GALAXY MAP KEY</span>
            <button class="legend-toggle" id="legendToggle">−</button>
        </div>
        <div class="legend-content" id="legendContent">
            <div class="legend-item">
                <div class="legend-shape node-type-core" style="transform: scale(0.6);"></div>
                <span>Core Concept</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-intuition" style="transform: scale(0.7);"></div>
                <span>Intuitions</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-question" style="transform: scale(0.7);"></div>
                <span>Motor Questions</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-theme theme-urban" style="transform: scale(0.7);"></div>
                <span>Thematic Fields</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-action action-amber" style="transform: scale(0.7);"></div>
                <span>Actions as Knowledge</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-type-future" style="transform: scale(0.7);"></div>
                <span>Emergent Futures</span>
            </div>
        </div>
    </div>
</div>

<!-- =============================================== -->
<!-- JAVASCRIPT COMPLETO DEL MAPA -->
<!-- =============================================== -->

<script>
// ===== DATOS COMPLETOS DE LA CONSTELACIÓN =====

const galaxyData = {
    // 🌞 NÚCLEO
    core: {
        id: "core",
        type: "core",
        title: "THE INVISIBLE CITY",
        subtitle: "How beauty hides violence, and how other species inhabit it",
        content: "The central intuition: urban aesthetics systematically conceal violence against both human and non-human life.",
        tooltip: "The gravitational center of your research universe. Where aesthetic pleasure meets systemic exclusion, where visible beauty hides invisible violence.",
        x: 50,
        y: 50,
        connections: ["intuition1", "intuition2", "theme1", "theme2"]
    },
    
    // 💎 INTUICIONES
    intuitions: [
        {
            id: "intuition1",
            type: "intuition",
            title: "Beauty that excludes",
            content: "The realization that what we call 'beautiful' in cities often systematically excludes certain lives.",
            tooltip: "Aesthetic standards as tools of power: clean spaces, curated nature, orderly facades that make some lives 'dirt' and others 'proper'.",
            angle: 0,
            orbit: 1
        },
        {
            id: "intuition2",
            type: "intuition",
            title: "Violence hidden in aesthetics",
            content: "How aesthetic pleasure masks structural violence.",
            tooltip: "The violence of absence: what is systematically removed, erased, or made invisible in the name of beauty and order.",
            angle: 90,
            orbit: 1
        },
        {
            id: "intuition3",
            type: "intuition",
            title: "Nature expelled from the city",
            content: "The systematic removal of non-curated life from urban spaces.",
            tooltip: "Plants as decoration, animals as pests, ecosystems as 'mess' to be cleaned. The urban hierarchy of life forms.",
            angle: 180,
            orbit: 1
        },
        {
            id: "intuition4",
            type: "intuition",
            title: "Order disguised as care",
            content: "How control mechanisms are presented as protection or improvement.",
            tooltip: "Safety measures that exclude, cleanliness that erases, maintenance that displaces. The rhetoric of care as political tool.",
            angle: 270,
            orbit: 1
        }
    ],
    
    // 🧠 PREGUNTAS MOTORAS
    questions: [
        {
            id: "question1",
            type: "question",
            title: "What bodies are allowed to rest?",
            content: "Investigating who can pause, sit, sleep in public space.",
            tooltip: "Questioning the politics of rest: benches designed against sleeping, surfaces that deny comfort, temporal restrictions on presence.",
            angle: 0,
            orbit: 2
        },
        {
            id: "question2",
            type: "question",
            title: "Whose lives are permitted in the city?",
            content: "Examining the hierarchy of urban citizenship.",
            tooltip: "From homeless humans to pigeons, from street vendors to wild plants: which lives are welcomed, tolerated, or actively eliminated?",
            angle: 60,
            orbit: 2
        },
        {
            id: "question3",
            type: "question",
            title: "How does beauty justify exclusion?",
            content: "The aesthetic rationale for removal and control.",
            tooltip: "How visual pleasure becomes an alibi for systemic violence. The politics of 'cleaning up', 'beautifying', 'renovating'.",
            angle: 120,
            orbit: 2
        },
        {
            id: "question4",
            type: "question",
            title: "Can design generate empathy?",
            content: "Exploring design's potential for cross-species understanding.",
            tooltip: "Could interfaces, installations, or experiences help humans feel what other species feel in urban environments?",
            angle: 180,
            orbit: 2
        },
        {
            id: "question5",
            type: "question",
            title: "What violence have we normalized?",
            content: "Identifying invisible systemic harm.",
            tooltip: "The violence of spikes on ledges, of smooth benches, of pesticide spraying, of constant noise and light pollution.",
            angle: 240,
            orbit: 2
        },
        {
            id: "question6",
            type: "question",
            title: "How would species design cities?",
            content: "Imagining urban planning from non-human perspectives.",
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
            content: "The politics of beauty in city design.",
            tooltip: "How aesthetic standards in urban design serve to normalize exclusion and control. Beauty as ideology, cleanliness as political tool.",
            angle: 0,
            orbit: 3,
            connections: ["intuition1", "question3", "action1"]
        },
        {
            id: "theme2",
            type: "theme",
            title: "Hostile Design",
            colorClass: "theme-hostile",
            content: "Architecture that subtly expels unwanted bodies.",
            tooltip: "Anti-homeless benches, pigeon spikes, seating deterrents, smooth surfaces. Violence normalized through everyday design.",
            angle: 60,
            orbit: 3,
            connections: ["intuition4", "question1", "action1", "action3"]
        },
        {
            id: "theme3",
            type: "theme",
            title: "Multispecies Justice",
            colorClass: "theme-species",
            content: "Expanding urban rights beyond the human.",
            tooltip: "Questioning the anthropocentric city. Rights to shelter, food, movement, and community for all species.",
            angle: 120,
            orbit: 3,
            connections: ["intuition3", "question2", "question6", "action2"]
        },
        {
            id: "theme4",
            type: "theme",
            title: "Embodied Research",
            colorClass: "theme-research",
            content: "Using the body as method and sensor.",
            tooltip: "Walking, sitting, wearing, performing. First-person ethnography to reveal what statistics and observation miss.",
            angle: 180,
            orbit: 3,
            connections: ["question4", "action1", "action3", "future1"]
        },
        {
            id: "theme5",
            type: "theme",
            title: "Sensory Translation",
            colorClass: "theme-sensory",
            content: "Translating urban experience across species.",
            tooltip: "Interfaces and methods for perceiving pollution, noise, vibration, chemical signals as other species might.",
            angle: 240,
            orbit: 3,
            connections: ["question4", "question6", "future1", "future2"]
        },
        {
            id: "theme6",
            type: "theme",
            title: "Environmental Empathy",
            colorClass: "theme-urban",
            content: "Feeling-with urban ecosystems.",
            tooltip: "Developing emotional and cognitive connections to non-human urban residents and their conditions.",
            angle: 300,
            orbit: 3,
            connections: ["question4", "future3", "future4"]
        }
    ],
    
    // ◉ ACCIONES
    actions: [
        {
            id: "action1",
            type: "action",
            title: "Sitting on hostile architecture",
            colorClass: "action-amber",
            content: "Embodied investigation of exclusionary design.",
            tooltip: "Using the body as sensor to experience and reveal the normalized violence of urban furniture designed to deny rest.",
            angle: 45,
            orbit: 4,
            connections: ["theme2", "theme4"]
        },
        {
            id: "action2",
            type: "action",
            title: "Returning Life interventions",
            colorClass: "action-green",
            content: "Small acts of rewilding urban spaces.",
            tooltip: "Soil deposits, seed bombs, moss graffiti. Reintroducing non-curated life into controlled urban environments.",
            angle: 135,
            orbit: 4,
            connections: ["theme3", "future4"]
        },
        {
            id: "action3",
            type: "action",
            title: "Wearing Hostility",
            colorClass: "action-red",
            content: "Material translation of architectural violence.",
            tooltip: "Turning anti-pigeon spikes into clothing. Making visible on the body what is normalized on buildings.",
            angle: 225,
            orbit: 4,
            connections: ["theme2", "theme4"]
        },
        {
            id: "action4",
            type: "action",
            title: "Sensory experiments",
            colorClass: "action-blue",
            content: "Testing perception interfaces.",
            tooltip: "Prototyping devices and experiences that translate urban conditions across sensory modalities and species boundaries.",
            angle: 315,
            orbit: 4,
            connections: ["theme5", "future1", "future2"]
        }
    ],
    
    // ⭐ FUTUROS
    futures: [
        {
            id: "future1",
            type: "future",
            title: "Multispecies Perception Interfaces",
            content: "Tools for cross-species urban sensing.",
            tooltip: "Wearables, installations, and apps that help humans perceive pollution, vibration, chemical signals as other species do.",
            angle: 45,
            orbit: 5,
            connections: ["theme5", "action4"]
        },
        {
            id: "future2",
            type: "future",
            title: "Embodied Environmental Translation",
            content: "Full-body experiences of ecological data.",
            tooltip: "Haptic suits, olfactory displays, thermal interfaces that make environmental conditions tangibly felt.",
            angle: 135,
            orbit: 5,
            connections: ["theme5", "action4"]
        },
        {
            id: "future3",
            type: "future",
            title: "Empathy-driven Design Futures",
            content: "Methodologies for compassionate urban planning.",
            tooltip: "Design processes that center multispecies wellbeing, sensory justice, and ecological empathy from concept to implementation.",
            angle: 225,
            orbit: 5,
            connections: ["theme6", "future4"]
        },
        {
            id: "future4",
            type: "future",
            title: "Urban Coexistence Rewriting",
            content: "Reimagining cities as multispecies communities.",
            tooltip: "Policy, architecture, and social practices that recognize all urban residents as citizens with rights and needs.",
            angle: 315,
            orbit: 5,
            connections: ["theme6", "action2", "future3"]
        }
    ],
    
    // ✦ MICRO-NODOS
    microNodes: [
        {id: "micro1", word: "care", colorClass: "micro-care", x: 30, y: 25},
        {id: "micro2", word: "friction", colorClass: "micro-friction", x: 70, y: 20},
        {id: "micro3", word: "presence", colorClass: "micro-presence", x: 85, y: 45},
        {id: "micro4", word: "erasure", colorClass: "micro-erasure", x: 75, y: 75},
        {id: "micro5", word: "vulnerability", colorClass: "micro-vulnerability", x: 45, y: 85},
        {id: "micro6", word: "coexistence", colorClass: "micro-coexistence", x: 20, y: 70},
        {id: "micro7", word: "denial", colorClass: "micro-erasure", x: 15, y: 45},
        {id: "micro8", word: "sensory burden", colorClass: "micro-friction", x: 40, y: 15}
    ]
};

// ===== FUNCIONES DE CONSTRUCCIÓN =====

function createGalaxy() {
    const nodesContainer = document.getElementById('cosmicNodes');
    const connectionsContainer = document.getElementById('cosmicConnections');
    const microContainer = document.getElementById('microNodes');
    
    // Crear nodo central
    createNode(galaxyData.core, nodesContainer, 0);
    
    // Crear todos los nodos por categoría
    [...galaxyData.intuitions, ...galaxyData.questions, ...galaxyData.themes, ...galaxyData.actions, ...galaxyData.futures]
        .forEach((node, index) => {
            createNode(node, nodesContainer, index + 1);
        });
    
    // Crear micro-nodos
    galaxyData.microNodes.forEach((micro, index) => {
        createMicroNode(micro, microContainer, index);
    });
    
    // Crear conexiones
    createAllConnections(connectionsContainer);
}

function createNode(nodeData, container, index) {
    const node = document.createElement('div');
    node.className = `cosmic-node node-type-${nodeData.type}`;
    node.dataset.id = nodeData.id;
    node.dataset.type = nodeData.type;
    node.style.setProperty('--node-index', index);
    
    // Calcular posición
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
    
    // Añadir clase de color si existe
    if (nodeData.colorClass) {
        node.classList.add(nodeData.colorClass);
    }
    
    // Contenido
    const content = document.createElement('div');
    content.className = 'node-content';
    
    const title = document.createElement('div');
    title.textContent = nodeData.title;
    title.style.fontWeight = '700';
    title.style.marginBottom = nodeData.subtitle ? '0.2rem' : '0';
    
    content.appendChild(title);
    
    if (nodeData.subtitle) {
        const subtitle = document.createElement('div');
        subtitle.textContent = nodeData.subtitle;
        subtitle.style.fontSize = '0.75rem';
        subtitle.style.opacity = '0.8';
        content.appendChild(subtitle);
    }
    
    node.appendChild(content);
    container.appendChild(node);
    
    // Event listeners
    node.addEventListener('mouseenter', handleNodeHover);
    node.addEventListener('mouseleave', handleNodeLeave);
    node.addEventListener('click', handleNodeClick);
}

function createMicroNode(microData, container, index) {
    const micro = document.createElement('div');
    micro.className = `cosmic-node node-type-micro ${microData.colorClass}`;
    micro.dataset.id = microData.id;
    micro.dataset.word = microData.word;
    micro.style.setProperty('--micro-index', index);
    micro.style.left = `${microData.x}%`;
    micro.style.top = `${microData.y}%`;
    
    // Tooltip básico para micro-nodos
    micro.addEventListener('mouseenter', (e) => {
        showTooltip(microData.word, 
            `Conceptual thread: ${microData.word} as a lens for reading urban relations.`, 
            e);
    });
    
    micro.addEventListener('mouseleave', hideTooltip);
    
    container.appendChild(micro);
}

function getOrbitRadius(orbitNumber) {
    const orbits = {
        1: 16,   // 160px / 1000px * 100%
        2: 28,   // 280px / 1000px * 100%
        3: 42,   // 420px / 1000px * 100%
        4: 58,   // 580px / 1000px * 100%
        5: 76    // 760px / 1000px * 100%
    };
    return orbits[orbitNumber] || 0;
}

// ===== CONEXIONES =====

function createAllConnections(container) {
    // Conexiones fuertes
    createConnection("theme1", "intuition1", "strong", container);
    createConnection("theme2", "action1", "strong", container);
    createConnection("theme3", "action2", "strong", container);
    createConnection("theme5", "future1", "strong", container);
    
    // Conexiones moderadas
    createConnection("intuition3", "theme1", "moderate", container);
    createConnection("intuition4", "theme2", "moderate", container);
    createConnection("theme4", "action1", "moderate", container);
    createConnection("theme6", "future3", "moderate", container);
    
    // Conexiones del núcleo
    createConnection("core", "intuition1", "strong", container);
    createConnection("core", "intuition2", "strong", container);
    createConnection("core", "theme1", "strong", container);
    createConnection("core", "theme2", "strong", container);
    
    // Conexiones adicionales desde los datos
    [...galaxyData.themes, ...galaxyData.actions, ...galaxyData.futures].forEach(node => {
        if (node.connections) {
            node.connections.forEach(targetId => {
                createConnection(node.id, targetId, "moderate", container);
            });
        }
    });
}

function createConnection(sourceId, targetId, strength, container) {
    const source = document.querySelector(`[data-id="${sourceId}"]`);
    const target = document.querySelector(`[data-id="${targetId}"]`);
    
    if (!source || !target) return;
    
    const connection = document.createElement('div');
    connection.className = `cosmic-connection connection-${strength}`;
    connection.dataset.source = sourceId;
    connection.dataset.target = targetId;
    
    // Posicionamiento
    const sourceRect = source.getBoundingClientRect();
    const targetRect = target.getBoundingClientRect();
    const containerRect = document.getElementById('galaxyMap').getBoundingClientRect();
    
    const x1 = sourceRect.left + sourceRect.width/2 - containerRect.left;
    const y1 = sourceRect.top + sourceRect.height/2 - containerRect.top;
    const x2 = targetRect.left + targetRect.width/2 - containerRect.left;
    const y2 = targetRect.top + targetRect.height/2 - containerRect.top;
    
    const dx = x2 - x1;
    const dy = y2 - y1;
    const distance = Math.sqrt(dx * dx + dy * dy);
    const angle = Math.atan2(dy, dx) * 180 / Math.PI;
    
    // Curvatura para conexiones moderadas
    let curve = 0;
    if (strength === "moderate") {
        curve = distance * 0.1;
        connection.style.borderRadius = `${curve}px`;
    }
    
    connection.style.width = `${distance}px`;
    connection.style.left = `${x1}px`;
    connection.style.top = `${y1}px`;
    connection.style.transform = `rotate(${angle}deg)`;
    
    container.appendChild(connection);
}

// ===== INTERACCIÓN =====

const tooltip = document.getElementById('cosmicTooltip');
const tooltipTitle = document.getElementById('tooltipTitle');
const tooltipContent = document.getElementById('tooltipContent');

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

function handleNodeHover(event) {
    const node = event.currentTarget;
    const nodeId = node.dataset.id;
    
    // Encontrar datos del nodo
    let nodeData = null;
    
    if (nodeId === "core") {
        nodeData = galaxyData.core;
    } else {
        const allNodes = [
            ...galaxyData.intuitions,
            ...galaxyData.questions,
            ...galaxyData.themes,
            ...galaxyData.actions,
            ...galaxyData.futures
        ];
        nodeData = allNodes.find(n => n.id === nodeId);
    }
    
    if (nodeData) {
        showTooltip(nodeData.title, nodeData.tooltip || nodeData.content, event);
    }
    
    // Resaltar conexiones
    document.querySelectorAll('.cosmic-connection').forEach(conn => {
        if (conn.dataset.source === nodeId || conn.dataset.target === nodeId) {
            conn.style.opacity = '0.8';
            conn.style.filter = 'brightness(1.5)';
        } else {
            conn.style.opacity = '0.2';
        }
    });
}

function handleNodeLeave() {
    hideTooltip();
    
    // Restaurar conexiones
    document.querySelectorAll('.cosmic-connection').forEach(conn => {
        conn.style.opacity = '';
        conn.style.filter = '';
    });
}

function handleNodeClick(event) {
    const node = event.currentTarget;
    const nodeId = node.dataset.id;
    
    // Encontrar datos del nodo
    let nodeData = null;
    let nodeType = "";
    
    if (nodeId === "core") {
        nodeData = galaxyData.core;
        nodeType = "Core Concept";
    } else {
        const allNodes = [
            ...galaxyData.intuitions,
            ...galaxyData.questions,
            ...galaxyData.themes,
            ...galaxyData.actions,
            ...galaxyData.futures
        ];
        nodeData = allNodes.find(n => n.id === nodeId);
        
        // Determinar tipo
        if (galaxyData.intuitions.find(n => n.id === nodeId)) nodeType = "Intuition";
        else if (galaxyData.questions.find(n => n.id === nodeId)) nodeType = "Motor Question";
        else if (galaxyData.themes.find(n => n.id === nodeId)) nodeType = "Thematic Field";
        else if (galaxyData.actions.find(n => n.id === nodeId)) nodeType = "Action as Knowledge";
        else if (galaxyData.futures.find(n => n.id === nodeId)) nodeType = "Emergent Future";
    }
    
    if (nodeData) {
        // Mostrar modal o expandir información
        const modalContent = `
            <div style="text-align: center; margin-bottom: 2rem;">
                <div style="font-size: 2rem; font-weight: 800; margin-bottom: 0.5rem; color: var(--data-blue);">${nodeData.title}</div>
                <div style="font-size: 0.9rem; opacity: 0.8; text-transform: uppercase; letter-spacing: 1px;">${nodeType}</div>
            </div>
            <div style="font-size: 1.1rem; line-height: 1.6; margin-bottom: 2rem;">${nodeData.tooltip || nodeData.content}</div>
            <div style="background: rgba(242, 242, 242, 0.05); padding: 1.5rem; border-radius: 12px; border-left: 4px solid var(--data-blue);">
                <div style="font-weight: 600; margin-bottom: 0.5rem; color: var(--data-blue);">Connected to:</div>
                <div style="display: flex; flex-wrap: wrap; gap: 0.5rem;">
                    ${getConnectedNodes(nodeId).map(id => `<span style="background: rgba(28, 100, 242, 0.2); padding: 0.4rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">${getNodeTitle(id)}</span>`).join('')}
                </div>
            </div>
        `;
        
        // Aquí podrías integrar con tu sistema de modales existente
        alert(`✨ ${nodeData.title}\n\n${nodeData.tooltip || nodeData.content}`);
    }
}

function getConnectedNodes(nodeId) {
    const connections = [];
    
    // Buscar conexiones donde este nodo es source o target
    document.querySelectorAll('.cosmic-connection').forEach(conn => {
        if (conn.dataset.source === nodeId) connections.push(conn.dataset.target);
        if (conn.dataset.target === nodeId) connections.push(conn.dataset.source);
    });
    
    return [...new Set(connections)]; // Eliminar duplicados
}

function getNodeTitle(nodeId) {
    if (nodeId === "core") return galaxyData.core.title;
    
    const allNodes = [
        ...galaxyData.intuitions,
        ...galaxyData.questions,
        ...galaxyData.themes,
        ...galaxyData.actions,
        ...galaxyData.futures
    ];
    
    const node = allNodes.find(n => n.id === nodeId);
    return node ? node.title : nodeId;
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

// ===== INICIALIZACIÓN =====

document.addEventListener('DOMContentLoaded', () => {
    createGalaxy();
    
    // Ajustar conexiones al redimensionar
    window.addEventListener('resize', () => {
        document.getElementById('cosmicConnections').innerHTML = '';
        createAllConnections(document.getElementById('cosmicConnections'));
    });
});
</script>