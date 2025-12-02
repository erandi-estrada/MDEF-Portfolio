<!-- =============================================== -->
<!-- MAPA CONSTELACIÓN - VERSIÓN CORREGIDA -->
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
        
        /* Tamaños de órbitas - AJUSTADOS PARA NODOS GRANDES */
        --orbit-intuitions: 280px;    /* Aumentado para nodos de 140px */
        --orbit-questions: 420px;     /* Aumentado para nodos de 130px */
        --orbit-themes: 600px;        /* Aumentado para nodos de 170px */
        --orbit-actions: 800px;       /* Aumentado para nodos de 150px */
        --orbit-futures: 1100px;      /* Aumentado para nodos de 150px */
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
    
    /* ===== SISTEMA DE NODOS - CORREGIDO PARA EVITAR TRASLAPES ===== */
    
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
        transform-origin: center center;
    }
    
    @keyframes cosmic-float {
        0%, 100% { transform: translate(-50%, -50%) scale(1); }
        50% { transform: translate(-50%, -50%) scale(1.02); }
    }
    
    /* CONTENEDOR DE CONTENIDO - PADDING AMPLIO */
    .node-content {
        position: relative;
        z-index: 3;
        padding: 24px;
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
    
    /* ===== TIPOS DE NODOS CON DEGRADADOS NÍTIDOS ===== */
    
    /* 🌞 NÚCLEO - CÍRCULO GRANDE */
    .node-type-core {
        width: 220px;
        height: 220px;
        border-radius: 50%;
        background: radial-gradient(
            circle at center,
            #1C64F2 0%,
            #1C64F2 35%,
            rgba(28, 100, 242, 0.20) 60%,
            transparent 100%
        );
        box-shadow: 
            inset 0 0 40px rgba(255, 255, 255, 0.3),
            0 0 80px rgba(28, 100, 242, 0.4);
        animation: core-pulse 8s ease-in-out infinite;
        z-index: 20;
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
    
    /* 💎 INTUICIONES - ROMBOS */
    .node-type-intuition {
        width: 140px;
        height: 140px;
        background: radial-gradient(
            circle at center,
            var(--magenta-intuition) 0%,
            var(--magenta-intuition) 35%,
            rgba(181, 30, 255, 0.20) 60%,
            transparent 100%
        );
        clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
        box-shadow: 
            inset 0 0 20px rgba(255, 255, 255, 0.2),
            0 0 40px rgba(181, 30, 255, 0.3);
        z-index: 15;
    }
    
    /* 🧠 PREGUNTAS - HEXÁGONOS */
    .node-type-question {
        width: 130px;
        height: 130px;
        background: radial-gradient(
            circle at center,
            rgba(242, 242, 242, 0.95) 0%,
            rgba(242, 242, 242, 0.95) 35%,
            rgba(242, 242, 242, 0.20) 60%,
            transparent 100%
        );
        clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
        color: var(--space-black);
        box-shadow: 
            inset 0 0 20px rgba(255, 255, 255, 0.3),
            0 0 35px rgba(242, 242, 242, 0.3);
        z-index: 16;
    }
    
    /* 🟣 CAMPOS TEÓRICOS - CÍRCULOS GRANDES */
    .node-type-theme {
        width: 170px;
        height: 170px;
        border-radius: 50%;
        box-shadow: 
            inset 0 0 30px rgba(255, 255, 255, 0.25),
            0 0 50px currentColor;
        background: radial-gradient(
            circle at center,
            currentColor 0%,
            currentColor 35%,
            rgba(255, 255, 255, 0.10) 60%,
            transparent 100%
        );
        z-index: 17;
    }
    
    /* ◉ ACCIONES - CÍRCULO DOBLE BORDE */
    .node-type-action {
        width: 150px;
        height: 150px;
        border-radius: 50%;
        background: transparent;
        border: 3px solid;
        box-shadow: 
            inset 0 0 30px rgba(255, 255, 255, 0.2),
            0 0 50px currentColor;
        position: relative;
        z-index: 18;
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
    
    /* ⭐ FUTUROS - ESTRELLAS */
    .node-type-future {
        width: 150px;
        height: 150px;
        background: radial-gradient(
            circle at center,
            var(--emergent-blue) 0%,
            var(--emergent-blue) 35%,
            rgba(0, 212, 255, 0.20) 60%,
            transparent 100%
        );
        clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        box-shadow: 
            inset 0 0 25px rgba(255, 255, 255, 0.25),
            0 0 40px rgba(0, 212, 255, 0.3);
        animation: star-sparkle 6s ease-in-out infinite;
        z-index: 19;
    }
    
    @keyframes star-sparkle {
        0%, 100% { opacity: 0.95; transform: translate(-50%, -50%) scale(1) rotate(0deg); }
        50% { opacity: 1; transform: translate(-50%, -50%) scale(1.05) rotate(3deg); }
    }
    
    /* ✦ MICRO-NODOS */
    .node-type-micro {
        width: 26px;
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
        z-index: 5;
    }
    
    @keyframes micro-pulse {
        0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0.5; }
        50% { transform: translate(-50%, -50%) scale(1.2); opacity: 0.8; }
    }
    
    /* ===== COLORES ESPECÍFICOS ===== */
    
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
    
    /* ===== CONEXIONES - MUCHO MÁS LIMPIAS ===== */
    
    .cosmic-connection {
        position: absolute;
        z-index: 4;
        transition: all 0.3s ease;
        pointer-events: none;
    }
    
    /* Línea fuerte - SOLO 4 */
    .connection-strong {
        height: 1.8px;
        background: linear-gradient(90deg, 
            var(--violet-injustice) 0%,
            var(--emergent-blue) 100%);
        opacity: 0.4;
        filter: drop-shadow(0 0 8px rgba(138, 63, 252, 0.3));
    }
    
    /* Línea normal - Grosor reducido, opacidad baja */
    .connection-normal {
        height: 0.8px;
        background: linear-gradient(90deg, 
            currentColor 0%,
            rgba(255, 255, 255, 0.3) 100%);
        opacity: 0.22;
        border-radius: 1px;
    }
    
    /* Línea débil - Muy tenue */
    .connection-weak {
        height: 0.5px;
        border: none;
        background-image: repeating-linear-gradient(
            90deg,
            transparent,
            transparent 4px,
            rgba(242, 242, 242, 0.15) 4px,
            rgba(242, 242, 242, 0.15) 8px
        );
        opacity: 0.15;
    }
    
    /* ===== TOOLTIP ELEGANTE ===== */
    
    .cosmic-tooltip {
        position: fixed;
        background: rgba(5, 5, 9, 0.95);
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
    
    /* ===== LEYENDA DISCRETA ===== */
    
    .galaxy-legend {
        position: absolute;
        bottom: 2rem;
        right: 2rem;
        background: rgba(5, 5, 9, 0.85);
        border: 1px solid rgba(242, 242, 242, 0.08);
        border-radius: 16px;
        padding: 1.25rem;
        z-index: 50;
        backdrop-filter: blur(15px);
        max-width: 240px;
        box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        transition: all 0.3s ease;
    }
    
    /* ===== RESPONSIVE OPTIMIZADO ===== */
    
    @media (max-width: 1400px) {
        :root {
            --orbit-intuitions: 250px;
            --orbit-questions: 380px;
            --orbit-themes: 540px;
            --orbit-actions: 720px;
            --orbit-futures: 1000px;
        }
        
        .node-type-core { width: 200px; height: 200px; }
        .node-type-intuition { width: 125px; height: 125px; }
        .node-type-question { width: 115px; height: 115px; }
        .node-type-theme { width: 150px; height: 150px; }
        .node-type-action { width: 135px; height: 135px; }
        .node-type-future { width: 135px; height: 135px; }
    }
    
    @media (max-width: 1024px) {
        :root {
            --orbit-intuitions: 220px;
            --orbit-questions: 340px;
            --orbit-themes: 480px;
            --orbit-actions: 640px;
            --orbit-futures: 880px;
        }
        
        .node-type-core { width: 180px; height: 180px; }
        .node-type-intuition { width: 110px; height: 110px; }
        .node-type-question { width: 100px; height: 100px; }
        .node-type-theme { width: 130px; height: 130px; }
        .node-type-action { width: 120px; height: 120px; }
        .node-type-future { width: 120px; height: 120px; }
    }
</style>

<!-- =============================================== -->
<!-- HTML DEL MAPA GALÁCTICO CORREGIDO -->
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
<!-- JAVASCRIPT CORREGIDO - POSICIONAMIENTO PRECISO -->
<!-- =============================================== -->

<script>
// ===== CONFIGURACIÓN DE NODOS =====

const galaxyData = {
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
    
    intuitions: [
        { id: "intuition1", type: "intuition", title: "Beauty excludes", content: "Aesthetic standards as tools of power", tooltip: "Clean spaces, curated nature, orderly facades that make some lives 'dirt' and others 'proper'.", angle: 0, orbit: 1 },
        { id: "intuition2", type: "intuition", title: "Violence hidden", content: "Aesthetics mask structural harm", tooltip: "The violence of absence: what is systematically removed or made invisible in the name of beauty.", angle: 90, orbit: 1 },
        { id: "intuition3", type: "intuition", title: "Nature expelled", content: "Non-curated life removed", tooltip: "Plants as decoration, animals as pests, ecosystems as 'mess' to be cleaned from urban spaces.", angle: 180, orbit: 1 },
        { id: "intuition4", type: "intuition", title: "Order as control", content: "Disguised as care, enacted as power", tooltip: "Safety measures that exclude, cleanliness that erases, maintenance that displaces vulnerable lives.", angle: 270, orbit: 1 }
    ],
    
    questions: [
        { id: "question1", type: "question", title: "Who can rest?", content: "Politics of pause in public space", tooltip: "Questioning benches designed against sleeping, surfaces that deny comfort, temporal restrictions on presence.", angle: 0, orbit: 2 },
        { id: "question2", type: "question", title: "Whose lives matter?", content: "Hierarchy of urban citizenship", tooltip: "From homeless humans to pigeons: which lives are welcomed, tolerated, or actively eliminated in cities?", angle: 60, orbit: 2 },
        { id: "question3", type: "question", title: "Beauty justifies?", content: "Aesthetic rationale for exclusion", tooltip: "How visual pleasure becomes an alibi for systemic violence in urban 'improvement' projects.", angle: 120, orbit: 2 },
        { id: "question4", type: "question", title: "Design empathy?", content: "Cross-species understanding", tooltip: "Can interfaces, installations, or experiences help humans feel what other species feel in cities?", angle: 180, orbit: 2 },
        { id: "question5", type: "question", title: "Normalized violence?", content: "Invisible systemic harm", tooltip: "The violence of spikes on ledges, smooth benches, pesticide spraying, constant noise pollution.", angle: 240, orbit: 2 },
        { id: "question6", type: "question", title: "Species design?", content: "Non-human urban planning", tooltip: "What would a pigeon's ideal plaza look like? A bee's transportation system? A tree's housing development?", angle: 300, orbit: 2 }
    ],
    
    themes: [
        { id: "theme1", type: "theme", title: "Urban Aesthetics", colorClass: "theme-urban", content: "Politics of beauty", tooltip: "How aesthetic standards in urban design serve to normalize exclusion and control. Beauty as ideology.", angle: 0, orbit: 3, connections: ["intuition1", "question3", "action1"] },
        { id: "theme2", type: "theme", title: "Hostile Design", colorClass: "theme-hostile", content: "Architecture expels", tooltip: "Anti-homeless benches, pigeon spikes, seating deterrents. Violence normalized through design.", angle: 60, orbit: 3, connections: ["intuition4", "question1", "action1"] },
        { id: "theme3", type: "theme", title: "Multispecies Justice", colorClass: "theme-species", content: "Beyond human rights", tooltip: "Questioning anthropocentric cities. Rights to shelter, food, movement for all species.", angle: 120, orbit: 3, connections: ["intuition3", "question2", "action2"] },
        { id: "theme4", type: "theme", title: "Embodied Research", colorClass: "theme-research", content: "Body as method", tooltip: "Walking, sitting, wearing, performing. First-person ethnography to reveal hidden urban violence.", angle: 180, orbit: 3, connections: ["question4", "action1", "action3"] },
        { id: "theme5", type: "theme", title: "Sensory Translation", colorClass: "theme-sensory", content: "Cross-species perception", tooltip: "Interfaces for perceiving pollution, noise, vibration as other species might experience them.", angle: 240, orbit: 3, connections: ["question4", "question6", "future1"] },
        { id: "theme6", type: "theme", title: "Environmental Empathy", colorClass: "theme-urban", content: "Feeling-with ecosystems", tooltip: "Developing emotional connections to non-human urban residents and their living conditions.", angle: 300, orbit: 3, connections: ["question4", "future3"] }
    ],
    
    actions: [
        { id: "action1", type: "action", title: "Sitting hostile", colorClass: "action-amber", content: "Body as sensor", tooltip: "Using the body to experience and reveal the normalized violence of exclusionary urban furniture.", angle: 45, orbit: 4, connections: ["theme2", "theme4"] },
        { id: "action2", type: "action", title: "Returning Life", colorClass: "action-green", content: "Rewilding acts", tooltip: "Soil deposits, seed bombs, moss graffiti. Reintroducing non-curated life into controlled spaces.", angle: 135, orbit: 4, connections: ["theme3", "future4"] },
        { id: "action3", type: "action", title: "Wearing Hostility", colorClass: "action-red", content: "Material translation", tooltip: "Turning anti-pigeon spikes into clothing. Making architectural violence visible on the body.", angle: 225, orbit: 4, connections: ["theme2", "theme4"] },
        { id: "action4", type: "action", title: "Sensory experiments", colorClass: "action-blue", content: "Perception interfaces", tooltip: "Prototyping devices that translate urban conditions across sensory modalities and species.", angle: 315, orbit: 4, connections: ["theme5", "future1"] }
    ],
    
    futures: [
        { id: "future1", type: "future", title: "Multispecies perception", content: "Cross-sensing tools", tooltip: "Wearables and installations that help humans perceive pollution, vibration, signals as other species do.", angle: 45, orbit: 5, connections: ["theme5", "action4"] },
        { id: "future2", type: "future", title: "Embodied translation", content: "Full-body ecology", tooltip: "Haptic suits, olfactory displays that make environmental conditions tangibly felt by humans.", angle: 135, orbit: 5, connections: ["theme5", "action4"] },
        { id: "future3", type: "future", title: "Empathy-driven design", content: "Compassionate planning", tooltip: "Design processes centering multispecies wellbeing, sensory justice, and ecological empathy.", angle: 225, orbit: 5, connections: ["theme6", "future4"] },
        { id: "future4", type: "future", title: "Urban coexistence", content: "Multispecies community", tooltip: "Reimagining cities where all residents are recognized as citizens with rights and needs.", angle: 315, orbit: 5, connections: ["theme6", "action2"] }
    ],
    
    microNodes: [
        { id: "micro1", word: "care", colorClass: "micro-care", x: 30, y: 25 },
        { id: "micro2", word: "friction", colorClass: "micro-friction", x: 70, y: 20 },
        { id: "micro3", word: "presence", colorClass: "micro-presence", x: 85, y: 45 },
        { id: "micro4", word: "erasure", colorClass: "micro-erasure", x: 75, y: 75 },
        { id: "micro5", word: "vulnerability", colorClass: "micro-vulnerability", x: 45, y: 85 },
        { id: "micro6", word: "coexistence", colorClass: "micro-coexistence", x: 20, y: 70 }
    ]
};

// ===== FUNCIONES CORREGIDAS =====

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
    
    // Crear conexiones LIMITADAS (para mantenerlo limpio)
    setTimeout(() => {
        createCleanConnections(connectionsContainer);
    }, 100);
}

function createNode(nodeData, container, index) {
    const node = document.createElement('div');
    node.className = `cosmic-node node-type-${nodeData.type}`;
    node.dataset.id = nodeData.id;
    node.dataset.type = nodeData.type;
    node.style.setProperty('--node-index', index);
    
    // Añadir clase de color
    if (nodeData.colorClass) {
        node.classList.add(nodeData.colorClass);
    }
    
    // Contenido
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
    
    // CALCULAR POSICIÓN CON CORRECCIÓN DE TAMAÑO
    setTimeout(() => {
        const rect = node.getBoundingClientRect();
        const containerRect = document.getElementById('galaxyMap').getBoundingClientRect();
        
        // Obtener tamaño del nodo en porcentaje del contenedor
        const nodeWidthPercent = (rect.width / containerRect.width) * 100;
        const nodeHeightPercent = (rect.height / containerRect.height) * 100;
        
        let x, y;
        
        if (nodeData.type === 'core') {
            x = 50;
            y = 50;
        } else {
            // Usar órbitas ajustadas según el tamaño del nodo
            const orbitRadius = getAdjustedOrbitRadius(nodeData.orbit, Math.max(nodeWidthPercent, nodeHeightPercent));
            const angle = (nodeData.angle * Math.PI) / 180;
            
            x = 50 + (orbitRadius * Math.cos(angle));
            y = 50 + (orbitRadius * Math.sin(angle));
        }
        
        node.style.left = `${x}%`;
        node.style.top = `${y}%`;
    }, 50);
    
    // Event listeners
    setupNodeInteractions(node, nodeData);
}

function getAdjustedOrbitRadius(orbitNumber, nodeSizePercent) {
    // Radios base en porcentaje del contenedor
    const baseOrbits = {
        1: 14,   // intuitions: 280px / 2000px * 100 = 14%
        2: 21,   // questions: 420px / 2000px * 100 = 21%
        3: 30,   // themes: 600px / 2000px * 100 = 30%
        4: 40,   // actions: 800px / 2000px * 100 = 40%
        5: 55    // futures: 1100px / 2000px * 100 = 55%
    };
    
    let baseRadius = baseOrbits[orbitNumber] || 0;
    
    // Ajustar por tamaño del nodo (evitar traslapes)
    if (orbitNumber > 1) {
        // Para órbitas exteriores, dar más espacio
        baseRadius += nodeSizePercent * 0.3;
    }
    
    return baseRadius;
}

// ===== CONEXIONES LIMITADAS Y LIMPIAS =====

function createCleanConnections(container) {
    container.innerHTML = '';
    
    // SOLO 4 líneas fuertes (máximo)
    createSimpleConnection("core", "intuition1", "strong", container);
    createSimpleConnection("theme1", "action1", "strong", container);
    createSimpleConnection("theme3", "action2", "strong", container);
    createSimpleConnection("theme5", "future1", "strong", container);
    
    // SOLO 8 líneas normales (máximo)
    createSimpleConnection("core", "theme1", "normal", container);
    createSimpleConnection("core", "theme2", "normal", container);
    createSimpleConnection("intuition1", "question3", "normal", container);
    createSimpleConnection("theme2", "question1", "normal", container);
    createSimpleConnection("theme4", "action3", "normal", container);
    createSimpleConnection("theme6", "future3", "normal", container);
    createSimpleConnection("question4", "theme5", "normal", container);
    createSimpleConnection("action2", "future4", "normal", container);
    
    // SOLO 4 líneas débiles (máximo)
    createSimpleConnection("micro1", "theme3", "weak", container);
    createSimpleConnection("micro4", "theme2", "weak", container);
    createSimpleConnection("micro6", "future4", "weak", container);
    createSimpleConnection("intuition2", "question5", "weak", container);
}

function createSimpleConnection(sourceId, targetId, strength, container) {
    const source = document.querySelector(`[data-id="${sourceId}"]`);
    const target = document.querySelector(`[data-id="${targetId}"]`);
    
    if (!source || !target) return;
    
    const connection = document.createElement('div');
    connection.className = `cosmic-connection connection-${strength}`;
    connection.dataset.source = sourceId;
    connection.dataset.target = targetId;
    
    // Posicionar línea recta simple
    const updatePosition = () => {
        const sourceRect = source.getBoundingClientRect();
        const targetRect = target.getBoundingClientRect();
        const containerRect = container.parentElement.getBoundingClientRect();
        
        const x1 = sourceRect.left + sourceRect.width/2 - containerRect.left;
        const y1 = sourceRect.top + sourceRect.height/2 - containerRect.top;
        const x2 = targetRect.left + targetRect.width/2 - containerRect.left;
        const y2 = targetRect.top + targetRect.height/2 - containerRect.top;
        
        // Calcular ángulo y distancia
        const dx = x2 - x1;
        const dy = y2 - y1;
        const distance = Math.sqrt(dx * dx + dy * dy);
        const angle = Math.atan2(dy, dx) * 180 / Math.PI;
        
        // Establecer posición y rotación
        connection.style.width = `${distance}px`;
        connection.style.left = `${x1}px`;
        connection.style.top = `${y1}px`;
        connection.style.transform = `rotate(${angle}deg)`;
        connection.style.transformOrigin = '0 0';
    };
    
    updatePosition();
    container.appendChild(connection);
    
    // Actualizar en resize
    window.addEventListener('resize', updatePosition);
    
    return connection;
}

// ===== INTERACCIÓN =====

const tooltip = document.getElementById('cosmicTooltip');
const tooltipTitle = document.getElementById('tooltipTitle');
const tooltipContent = document.getElementById('tooltipContent');

function setupNodeInteractions(node, nodeData) {
    node.addEventListener('mouseenter', (e) => {
        tooltipTitle.textContent = nodeData.title;
        tooltipContent.textContent = nodeData.tooltip || nodeData.content;
        
        tooltip.style.left = `${e.clientX + 20}px`;
        tooltip.style.top = `${e.clientY + 20}px`;
        tooltip.classList.add('active');
    });
    
    node.addEventListener('mouseleave', () => {
        tooltip.classList.remove('active');
    });
}

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
    
    // Ajustar tooltip al mover mouse
    document.addEventListener('mousemove', (e) => {
        if (tooltip.classList.contains('active')) {
            tooltip.style.left = `${e.clientX + 20}px`;
            tooltip.style.top = `${e.clientY + 20}px`;
        }
    });
});
</script>