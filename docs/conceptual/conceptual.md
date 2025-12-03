<!-- =============================================== -->
<!-- MAPA CONSTELACIÓN - RUEDA DE EMOCIONES VERSION -->
<!-- =============================================== -->

<style>
    /* VARIABLES CON ESPACIADO AMPLIO COMO LA IMAGEN */
    :root {
        /* Paleta inspirada en la rueda de emociones */
        --space-black: #0A0A14;
        --core-blue: #1C64F2;
        --intuition-magenta: #B51EFF;
        --question-teal: #00C49A;
        --theme-amber: #FF9F1C;
        --theme-violet: #8A3FFC;
        --theme-green: #10B981;
        --theme-red: #E11D48;
        --action-blue: #3B82F6;
        --project-gold: #FFDD00;
        --connection-blue: #00D4FF;
        --text-light: #F8FAFC;
        --text-dim: #94A3B8;
        
        /* Capas concéntricas - ESPACIOS AMPLIOS COMO LA IMAGEN */
        --orbit-core: 0px;
        --orbit-intuitions: 180px;
        --orbit-questions: 320px;
        --orbit-themes: 480px;
        --orbit-actions: 680px;
        --orbit-bee-project: 900px;
        --orbit-futures: 1100px;
        
        /* Tamaños de nodos - JERARQUÍA VISUAL */
        --size-core: 240px;
        --size-intuition: 100px;
        --size-question: 90px;
        --size-theme: 140px;
        --size-action: 110px;
        --size-bee: 160px;
        --size-future: 130px;
    }
    
    @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&display=swap');
    
    /* CONTENEDOR PRINCIPAL - FONDO PROFUNDO */
    .emotion-wheel {
        position: relative;
        width: 100%;
        height: 140vh;
        min-height: 1300px;
        background: 
            radial-gradient(circle at center, rgba(28, 100, 242, 0.05) 0%, transparent 70%),
            var(--space-black);
        overflow: hidden;
        border-radius: 24px;
        margin: 3rem 0;
        font-family: 'Space Grotesk', 'Inter', sans-serif;
        font-weight: 400;
    }
    
    /* FONDO DE ESTRELLAS SÚTIL */
    .cosmic-background {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-image: 
            radial-gradient(1.5px 1.5px at 20% 30%, rgba(255, 255, 255, 0.1) 1px, transparent 0),
            radial-gradient(1px 1px at 40% 70%, rgba(0, 212, 255, 0.08) 1px, transparent 0),
            radial-gradient(1px 1px at 60% 40%, rgba(181, 30, 255, 0.06) 1px, transparent 0),
            radial-gradient(1.5px 1.5px at 80% 60%, rgba(255, 221, 0, 0.07) 1px, transparent 0);
        background-size: 400px 400px;
        animation: star-drift 40s infinite linear;
        z-index: 1;
        opacity: 0.4;
    }
    
    @keyframes star-drift {
        from { transform: translateY(0) translateX(0); }
        to { transform: translateY(-200px) translateX(100px); }
    }
    
    /* LÍNEAS ORBITALES - MUY SÚTILES */
    .orbit-line {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 50%;
        border: 0.7px solid rgba(248, 250, 252, 0.07);
        z-index: 2;
        pointer-events: none;
    }
    
    .orbit-2 { width: var(--orbit-intuitions); height: var(--orbit-intuitions); }
    .orbit-3 { width: var(--orbit-questions); height: var(--orbit-questions); }
    .orbit-4 { width: var(--orbit-themes); height: var(--orbit-themes); }
    .orbit-5 { width: var(--orbit-actions); height: var(--orbit-actions); }
    .orbit-6 { width: var(--orbit-bee-project); height: var(--orbit-bee-project); }
    .orbit-7 { width: var(--orbit-futures); height: var(--orbit-futures); }
    
    /* ETIQUETAS DE CAPA - COMO EN LA IMAGEN */
    .layer-label {
        position: absolute;
        color: var(--text-dim);
        font-size: 0.75rem;
        font-weight: 600;
        text-transform: uppercase;
        letter-spacing: 1px;
        z-index: 3;
        pointer-events: none;
        opacity: 0.7;
    }
    
    /* ===== SISTEMA DE NODOS - JERARQUÍA VISUAL ===== */
    
    .wheel-node {
        position: absolute;
        cursor: pointer;
        z-index: 10;
        transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        font-weight: 500;
        filter: drop-shadow(0 4px 12px rgba(0, 0, 0, 0.3));
        transform-origin: center center;
    }
    
    /* EFECTO FLOTANTE */
    @keyframes gentle-float {
        0%, 100% { transform: translate(-50%, -50%) scale(1); }
        50% { transform: translate(-50%, -50%) scale(1.03); }
    }
    
    /* 🌑 NÚCLEO - CENTRO DE LA GALAXIA */
    .node-core {
        width: var(--size-core);
        height: var(--size-core);
        border-radius: 50%;
        background: radial-gradient(
            circle at center,
            var(--core-blue) 0%,
            var(--core-blue) 30%,
            rgba(28, 100, 242, 0.25) 60%,
            transparent 85%
        );
        box-shadow: 
            inset 0 0 50px rgba(255, 255, 255, 0.2),
            0 0 100px rgba(28, 100, 242, 0.4),
            0 0 0 1px rgba(255, 255, 255, 0.1);
        z-index: 20;
        animation: core-pulse 8s ease-in-out infinite;
    }
    
    @keyframes core-pulse {
        0%, 100% { box-shadow: 
            inset 0 0 50px rgba(255, 255, 255, 0.2),
            0 0 100px rgba(28, 100, 242, 0.4),
            0 0 0 1px rgba(255, 255, 255, 0.1); }
        50% { box-shadow: 
            inset 0 0 60px rgba(255, 255, 255, 0.25),
            0 0 140px rgba(28, 100, 242, 0.5),
            0 0 0 1px rgba(255, 255, 255, 0.15); }
    }
    
    /* 💎 INTUICIONES - ROMBOS MAGENTA */
    .node-intuition {
        width: var(--size-intuition);
        height: var(--size-intuition);
        background: radial-gradient(
            circle at center,
            var(--intuition-magenta) 0%,
            var(--intuition-magenta) 40%,
            rgba(181, 30, 255, 0.2) 70%,
            transparent 100%
        );
        clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
        box-shadow: 
            inset 0 0 15px rgba(255, 255, 255, 0.15),
            0 0 30px rgba(181, 30, 255, 0.3);
        z-index: 11;
        animation: gentle-float 6s ease-in-out infinite;
    }
    
    /* ⚪ PREGUNTAS MOTOR - HEXÁGONOS TEAL */
    .node-question {
        width: var(--size-question);
        height: var(--size-question);
        background: radial-gradient(
            circle at center,
            var(--question-teal) 0%,
            var(--question-teal) 40%,
            rgba(0, 196, 154, 0.2) 70%,
            transparent 100%
        );
        clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
        box-shadow: 
            inset 0 0 12px rgba(255, 255, 255, 0.2),
            0 0 25px rgba(0, 196, 154, 0.25);
        z-index: 12;
        animation: gentle-float 7s ease-in-out infinite;
        animation-delay: 0.5s;
    }
    
    /* 🟠 CAMPOS TEMÁTICOS - CÍRCULOS COLORES VARIOS */
    .node-theme {
        width: var(--size-theme);
        height: var(--size-theme);
        border-radius: 50%;
        background: radial-gradient(
            circle at center,
            currentColor 0%,
            currentColor 35%,
            rgba(255, 255, 255, 0.15) 65%,
            transparent 90%
        );
        box-shadow: 
            inset 0 0 20px rgba(255, 255, 255, 0.2),
            0 0 40px currentColor;
        z-index: 13;
        animation: gentle-float 8s ease-in-out infinite;
        animation-delay: 1s;
    }
    
    /* 🌙 ACCIONES - CÍRCULOS DOBLE ANILLO */
    .node-action {
        width: var(--size-action);
        height: var(--size-action);
        border-radius: 50%;
        background: transparent;
        border: 2.5px solid currentColor;
        box-shadow: 
            inset 0 0 20px rgba(255, 255, 255, 0.15),
            0 0 35px currentColor;
        position: relative;
        z-index: 14;
    }
    
    .node-action::before {
        content: '';
        position: absolute;
        top: 20%;
        left: 20%;
        right: 20%;
        bottom: 20%;
        border-radius: 50%;
        border: 1.5px solid currentColor;
        opacity: 0.4;
    }
    
    /* 🐝 PROYECTO ABEJA - ESTRELLAS DORADAS */
    .node-bee {
        width: var(--size-bee);
        height: var(--size-bee);
        background: radial-gradient(
            circle at center,
            var(--project-gold) 0%,
            var(--project-gold) 40%,
            rgba(255, 221, 0, 0.2) 70%,
            transparent 100%
        );
        clip-path: polygon(
            50% 0%, 61% 35%, 98% 35%, 
            68% 57%, 79% 91%, 50% 70%, 
            21% 91%, 32% 57%, 2% 35%, 39% 35%
        );
        box-shadow: 
            inset 0 0 20px rgba(255, 255, 255, 0.2),
            0 0 40px rgba(255, 221, 0, 0.3);
        z-index: 15;
        animation: bee-glow 5s ease-in-out infinite;
    }
    
    @keyframes bee-glow {
        0%, 100% { opacity: 0.95; }
        50% { opacity: 1; }
    }
    
    /* ⭐ FUTUROS - CÍRCULOS BRILLANTES */
    .node-future {
        width: var(--size-future);
        height: var(--size-future);
        border-radius: 50%;
        background: radial-gradient(
            circle at center,
            var(--connection-blue) 0%,
            var(--connection-blue) 35%,
            rgba(0, 212, 255, 0.2) 65%,
            transparent 90%
        );
        box-shadow: 
            inset 0 0 15px rgba(255, 255, 255, 0.2),
            0 0 30px rgba(0, 212, 255, 0.25);
        z-index: 16;
        animation: gentle-float 9s ease-in-out infinite;
        animation-delay: 1.5s;
    }
    
    /* CONTENIDO DE NODO - TEXTO LIMPIO */
    .node-content {
        position: relative;
        z-index: 5;
        padding: 16px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
        color: var(--text-light);
        font-size: 0.9rem;
        line-height: 1.25;
        text-shadow: 0 1px 3px rgba(0, 0, 0, 0.5);
    }
    
    .node-title {
        font-weight: 700;
        margin-bottom: 0.3rem;
        font-size: 0.95rem;
    }
    
    .node-subtitle {
        font-size: 0.8rem;
        opacity: 0.9;
        font-weight: 400;
    }
    
    /* ===== COLORES POR CATEGORÍA ===== */
    .color-urban { color: var(--theme-violet); }
    .color-hostile { color: var(--theme-amber); }
    .color-species { color: var(--theme-green); }
    .color-research { color: var(--question-teal); }
    .color-sensory { color: var(--theme-red); }
    .color-empathy { color: var(--intuition-magenta); }
    .color-translation { color: var(--action-blue); }
    
    /* ===== CONEXIONES ORGÁNICAS - COMO LA IMAGEN ===== */
    .organic-connection {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 5;
        pointer-events: none;
        overflow: visible;
    }
    
    .connection-path {
        fill: none;
        stroke-width: 1.5;
        stroke-linecap: round;
        transition: all 0.3s ease;
    }
    
    .connection-strong {
        stroke: rgba(0, 212, 255, 0.4);
        stroke-width: 2;
        filter: drop-shadow(0 0 4px rgba(0, 212, 255, 0.2));
    }
    
    .connection-medium {
        stroke: rgba(248, 250, 252, 0.25);
        stroke-width: 1;
        opacity: 0.6;
    }
    
    .connection-weak {
        stroke: rgba(248, 250, 252, 0.15);
        stroke-width: 0.7;
        stroke-dasharray: 3, 3;
        opacity: 0.4;
    }
    
    /* ===== TOOLTIP ELEGANTE ===== */
    .wheel-tooltip {
        position: fixed;
        background: rgba(10, 10, 20, 0.95);
        border: 1px solid rgba(248, 250, 252, 0.1);
        border-radius: 12px;
        padding: 1.5rem;
        max-width: 320px;
        z-index: 1000;
        pointer-events: none;
        opacity: 0;
        transform: translateY(10px) scale(0.98);
        transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
        backdrop-filter: blur(10px);
        box-shadow: 
            0 12px 40px rgba(0, 0, 0, 0.4),
            0 0 0 1px rgba(28, 100, 242, 0.1);
        color: var(--text-light);
        font-size: 0.9rem;
        line-height: 1.5;
    }
    
    .wheel-tooltip.active {
        opacity: 1;
        transform: translateY(0) scale(1);
    }
    
    .tooltip-header {
        color: var(--core-blue);
        font-weight: 700;
        margin-bottom: 0.75rem;
        font-size: 1.1rem;
        display: flex;
        align-items: center;
        gap: 0.5rem;
    }
    
    .tooltip-body {
        opacity: 0.9;
        font-weight: 300;
    }
    
    /* ===== LEYENDA COMO LA IMAGEN ===== */
    .wheel-legend {
        position: absolute;
        bottom: 2rem;
        right: 2rem;
        background: rgba(10, 10, 20, 0.85);
        border: 1px solid rgba(248, 250, 252, 0.08);
        border-radius: 16px;
        padding: 1.5rem;
        z-index: 50;
        backdrop-filter: blur(10px);
        width: 260px;
        box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
    }
    
    .legend-title {
        color: var(--text-light);
        font-size: 0.9rem;
        font-weight: 600;
        margin-bottom: 1.25rem;
        text-transform: uppercase;
        letter-spacing: 1px;
        opacity: 0.9;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
    
    .legend-items {
        display: flex;
        flex-direction: column;
        gap: 0.75rem;
    }
    
    .legend-item {
        display: flex;
        align-items: center;
        gap: 0.75rem;
        font-size: 0.85rem;
        color: var(--text-dim);
    }
    
    .legend-shape {
        width: 24px;
        height: 24px;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-shrink: 0;
    }
    
    /* ===== RESPONSIVE ===== */
    @media (max-width: 1400px) {
        :root {
            --orbit-intuitions: 160px;
            --orbit-questions: 280px;
            --orbit-themes: 420px;
            --orbit-actions: 600px;
            --orbit-bee-project: 800px;
            --orbit-futures: 1000px;
            
            --size-core: 220px;
            --size-intuition: 90px;
            --size-question: 80px;
            --size-theme: 120px;
            --size-action: 100px;
            --size-bee: 140px;
            --size-future: 120px;
        }
    }
    
    @media (max-width: 1024px) {
        .emotion-wheel {
            height: 120vh;
            min-height: 1100px;
        }
        
        :root {
            --orbit-intuitions: 140px;
            --orbit-questions: 240px;
            --orbit-themes: 360px;
            --orbit-actions: 520px;
            --orbit-bee-project: 700px;
            --orbit-futures: 880px;
            
            --size-core: 200px;
            --size-intuition: 80px;
            --size-question: 70px;
            --size-theme: 110px;
            --size-action: 90px;
            --size-bee: 130px;
            --size-future: 110px;
        }
        
        .node-content {
            padding: 12px;
            font-size: 0.85rem;
        }
        
        .wheel-legend {
            width: 220px;
            padding: 1.25rem;
            right: 1rem;
            bottom: 1rem;
        }
    }
    
    @media (max-width: 768px) {
        .wheel-legend {
            display: none;
        }
    }
</style>

<!-- =============================================== -->
<!-- HTML - RUEDA DE LA CIUDAD INVISIBLE -->
<!-- =============================================== -->

<div class="emotion-wheel" id="cityWheel">
    <!-- Fondo cósmico -->
    <div class="cosmic-background"></div>
    
    <!-- Líneas orbitales (muy sutiles) -->
    <div class="orbit-line orbit-2"></div>
    <div class="orbit-line orbit-3"></div>
    <div class="orbit-line orbit-4"></div>
    <div class="orbit-line orbit-5"></div>
    <div class="orbit-line orbit-6"></div>
    <div class="orbit-line orbit-7"></div>
    
    <!-- Etiquetas de capa -->
    <div class="layer-label" style="top: calc(50% - 90px); left: calc(50% + 95px);">Intuitions</div>
    <div class="layer-label" style="top: calc(50% - 160px); left: calc(50% + 165px);">Questions</div>
    <div class="layer-label" style="top: calc(50% - 240px); left: calc(50% + 245px);">Themes</div>
    <div class="layer-label" style="top: calc(50% - 340px); left: calc(50% + 345px);">Actions</div>
    <div class="layer-label" style="top: calc(50% - 450px); left: calc(50% + 455px);">Bee Project</div>
    <div class="layer-label" style="top: calc(50% - 550px); left: calc(50% + 555px);">Futures</div>
    
    <!-- Contenedores -->
    <div id="wheelNodes"></div>
    <div id="wheelConnections"></div>
    
    <!-- Tooltip -->
    <div class="wheel-tooltip" id="wheelTooltip">
        <div class="tooltip-header" id="tooltipHeader"></div>
        <div class="tooltip-body" id="tooltipBody"></div>
    </div>
    
    <!-- Leyenda -->
    <div class="wheel-legend">
        <div class="legend-title">
            <span>LAYERS</span>
            <span>● ○ ◇</span>
        </div>
        <div class="legend-items">
            <div class="legend-item">
                <div class="legend-shape node-core" style="transform: scale(0.4);"></div>
                <span>Core Concept</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-intuition" style="transform: scale(0.5);"></div>
                <span>Intuitions (12)</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-question" style="transform: scale(0.5);"></div>
                <span>Motor Questions</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-theme color-urban" style="transform: scale(0.5);"></div>
                <span>Thematic Fields</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-action color-translation" style="transform: scale(0.5);"></div>
                <span>Actions</span>
            </div>
            <div class="legend-item">
                <div class="legend-shape node-bee" style="transform: scale(0.5);"></div>
                <span>Bee Project</span>
            </div>
        </div>
    </div>
</div>

<script>
// ===== DATOS COMPLETOS DE LA CIUDAD INVISIBLE =====

const cityWheelData = {
    // 🌑 CAPA 1 - NÚCLEO
    core: {
        id: "core",
        type: "core",
        title: "THE INVISIBLE CITY",
        subtitle: "How urban beauty hides violence",
        content: "The city appears clean and orderly, but this beauty conceals structural violence against humans and nonhuman species.",
        tooltip: "The city appears clean, beautiful and orderly, but this beauty often conceals structural violence against both humans and nonhuman species. By exposing hidden infrastructures of exclusion, we can move from awareness → empathy → multispecies futures.",
        x: 50,
        y: 50
    },
    
    // 💎 CAPA 2 - INTUICIONES (12 como en tus datos)
    intuitions: [
        { id: "i1", type: "intuition", title: "Make the invisible visible", content: "Urban beauty hides infrastructures of violence", tooltip: "Urban beauty hides infrastructures of violence toward humans, animals, and ecosystems.", angle: 0, orbit: 2 },
        { id: "i2", type: "intuition", title: "Feel what others feel", content: "Empathy requires inhabiting sensory vulnerabilities", tooltip: "Empathy requires temporarily inhabiting sensory vulnerabilities we do not normally perceive.", angle: 30, orbit: 2 },
        { id: "i3", type: "intuition", title: "Beauty feels wrong", content: "Aesthetic order disguises exclusion", tooltip: "The city is beautiful, but something feels wrong. Aesthetic order often disguises exclusion.", angle: 60, orbit: 2 },
        { id: "i4", type: "intuition", title: "Violence is silent", content: "Architectural, aesthetic, hidden", tooltip: "Violence is not only physical — it can be architectural, aesthetic, silent. It can appear as 'cleanliness', 'order', or 'maintenance.'", angle: 90, orbit: 2 },
        { id: "i5", type: "intuition", title: "Some lives erased", content: "Cities decide which bodies can inhabit space", tooltip: "Some forms of life are allowed; others are erased. Cities decide which bodies can inhabit space — humans and nonhumans alike.", angle: 120, orbit: 2 },
        { id: "i6", type: "intuition", title: "Nature as decoration", content: "Spontaneous life is undesirable", tooltip: "Nature is permitted only when it behaves as decoration. Spontaneous, uncontrolled life is considered undesirable.", angle: 150, orbit: 2 },
        { id: "i7", type: "intuition", title: "Life returns", content: "When we invite it back", tooltip: "Life returns when we invite it back. Plants growing through cracks, pigeons resting, bees visiting flowers — life persists.", angle: 180, orbit: 2 },
        { id: "i8", type: "intuition", title: "Empathy through embodiment", content: "Not through information", tooltip: "Empathy emerges through embodiment, not information. Data alone does not generate change; sensory and embodied experience does.", angle: 210, orbit: 2 },
        { id: "i9", type: "intuition", title: "Human-centric design", content: "Ignores nonhuman sensory worlds", tooltip: "Human-designed environments do not consider nonhuman sensory worlds. Urban space is tuned only to human comfort, not multispecies survival.", angle: 240, orbit: 2 },
        { id: "i10", type: "intuition", title: "Sense like another species", content: "Would we act differently?", tooltip: "If humans could sense the city like another species, would we act differently? This question anchors your main research.", angle: 270, orbit: 2 },
        { id: "i11", type: "intuition", title: "Control behind beauty", content: "What appears safe can be hostile", tooltip: "The city hides infrastructures of control behind beauty. What appears 'safe', 'nice', or 'clean' can be deeply hostile.", angle: 300, orbit: 2 },
        { id: "i12", type: "intuition", title: "Tiny interventions", content: "Reveal huge systems", tooltip: "Tiny interventions reveal huge systems. Sitting on hostile architecture, planting a leaf, modifying a dress — micro-actions uncover macro-patterns.", angle: 330, orbit: 2 }
    ],
    
    // ⚪ CAPA 3 - PREGUNTAS MOTOR
    questions: [
        { id: "q1", type: "question", title: "What lives are allowed?", content: "In the city", tooltip: "What lives are allowed in the city? What bodies can rest? How does beauty justify exclusion?", angle: 0, orbit: 3 },
        { id: "q2", type: "question", title: "Violence sanitized", content: "Through aesthetics", tooltip: "How is violence sanitized through aesthetics? Would other species design differently?", angle: 45, orbit: 3 },
        { id: "q3", type: "question", title: "Translate nonhuman senses", content: "Sensory worlds", tooltip: "How can we translate nonhuman sensory worlds? How can embodied experience reveal hidden infrastructures?", angle: 90, orbit: 3 },
        { id: "q4", type: "question", title: "Awareness to action", content: "Pathway", tooltip: "How can we move from awareness → empathy → action? What interventions create multispecies empathy?", angle: 135, orbit: 3 },
        { id: "q5", type: "question", title: "Hidden infrastructures", content: "Make visible", tooltip: "How to make invisible infrastructures of control visible through design and intervention?", angle: 180, orbit: 3 },
        { id: "q6", type: "question", title: "Multispecies justice", content: "In urban space", tooltip: "What does justice look like for nonhuman urban residents? How to design for multispecies coexistence?", angle: 225, orbit: 3 },
        { id: "q7", type: "question", title: "Sensory translation", content: "Methods and tools", tooltip: "What methods can translate bee vision, vibration, chemical signals into human-perceivable experiences?", angle: 270, orbit: 3 },
        { id: "q8", type: "question", title: "From empathy to change", content: "Pathways", tooltip: "How does embodied empathy translate to behavioral and systemic change in urban environments?", angle: 315, orbit: 3 }
    ],
    
    // 🟠 CAPA 4 - CAMPOS TEMÁTICOS
    themes: [
        { id: "t1", type: "theme", title: "Urban Aesthetics", colorClass: "color-urban", content: "Beauty as political tool", tooltip: "Beauty, order, cleanliness as political tools. Tourism-driven visual control. Aesthetic erasure of life.", angle: 0, orbit: 4 },
        { id: "t2", type: "theme", title: "Hostile Design", colorClass: "color-hostile", content: "Architecture that expels", tooltip: "Anti-homeless architecture. Anti-pigeon measures. Urban surfaces that deny rest. Violence normalized through design.", angle: 60, orbit: 4 },
        { id: "t3", type: "theme", title: "Multispecies Justice", colorClass: "color-species", content: "Beyond human rights", tooltip: "Rights to presence, rest, shelter. Nonhuman citizenship. Shared urban vulnerabilities.", angle: 120, orbit: 4 },
        { id: "t4", type: "theme", title: "Embodied Research", colorClass: "color-research", content: "Body as sensor", tooltip: "Your body as sensor. Ethnographic walking. Feeling architecture. First-person experience as research method.", angle: 180, orbit: 4 },
        { id: "t5", type: "theme", title: "Sensory Translation", colorClass: "color-sensory", content: "Cross-species perception", tooltip: "Translating nonhuman senses. Designing for a body unlike yours. Interfaces for multispecies understanding.", angle: 240, orbit: 4 },
        { id: "t6", type: "theme", title: "Environmental Empathy", colorClass: "color-empathy", content: "Feeling-with ecosystems", tooltip: "Empathy towards ecosystems. Cross-species communication. Emotional connection through experience.", angle: 300, orbit: 4 }
    ],
    
    // 🌙 CAPA 5 - ACCIONES
    actions: [
        { id: "a1", type: "action", title: "Sitting Hostile", colorClass: "color-hostile", content: "Body as sensor", tooltip: "Sitting on hostile architecture. Revealing architectural micro-violence through embodied experience.", angle: 30, orbit: 5 },
        { id: "a2", type: "action", title: "Wearing Hostility", colorClass: "color-sensory", content: "Material translation", tooltip: "Transferring anti-pigeon spikes to the human body. Making architectural violence visible and wearable.", angle: 90, orbit: 5 },
        { id: "a3", type: "action", title: "Returning Life", colorClass: "color-species", content: "Rewilding acts", tooltip: "Planting spontaneous life in concrete spaces. Soil deposits, seed bombs, moss graffiti. Reintroducing non-curated life.", angle: 150, orbit: 5 },
        { id: "a4", type: "action", title: "Beauty That Excludes", colorClass: "color-urban", content: "Documenting erasure", tooltip: "Documenting aesthetic erasure. Urban Violence Photography Map. Mapping exclusions across Barcelona.", angle: 210, orbit: 5 },
        { id: "a5", type: "action", title: "Hidden Infrastructures", colorClass: "color-research", content: "Patterns of control", tooltip: "Documenting hidden infrastructures. Patterns of control in tourist zones. Your practice uses the body and micro-interventions.", angle: 270, orbit: 5 },
        { id: "a6", type: "action", title: "Sensory Experiments", colorClass: "color-translation", content: "Perception interfaces", tooltip: "Prototyping devices that translate urban conditions across sensory modalities and species.", angle: 330, orbit: 5 }
    ],
    
    // 🐝 CAPA 6 - PROYECTO ABEJA
    beeProject: [
        { id: "b1", type: "bee", title: "Bee Vulnerabilities", content: "Pesticides, habitat loss", tooltip: "Pesticides, habitat fragmentation, urban monoculture plants, heat islands, pollution.", angle: 20, orbit: 6 },
        { id: "b2", type: "bee", title: "Bee Sensory World", content: "UV vision, vibrations", tooltip: "UV vision, vibrational communication, chemical signaling, spatial memory, magnetoreception.", angle: 60, orbit: 6 },
        { id: "b3", type: "bee", title: "Human-Bee Conflicts", content: "Aesthetic removal", tooltip: "Beehives removed for aesthetics, fear-driven extermination, landscaping hostile to pollinators.", angle: 100, orbit: 6 },
        { id: "b4", type: "bee", title: "Infrastructures of Violence", content: "Bee edition", tooltip: "Corporate agriculture, industrial pesticides, urban 'beautification' that removes wildflowers, lack of nesting spaces.", angle: 140, orbit: 6 },
        { id: "b5", type: "bee", title: "Multi-Species Translation", content: "Methods", tooltip: "Sensors that convert vibrations to sound, UV → visible spectrum mapping, temperature → haptic pulses, pheromone patterns → scent.", angle: 180, orbit: 6 },
        { id: "b6", type: "bee", title: "Empathy Pathway", content: "Awareness to action", tooltip: "Awareness → Embodied Experience → Multispecies Empathy → Action. Your main conceptual structure.", angle: 220, orbit: 6 },
        { id: "b7", type: "bee", title: "Sensory Installation", content: "Final outcome", tooltip: "Immersive multisensory environment. Human body temporarily tuned to bee senses. Visual, auditory, haptic translation.", angle: 260, orbit: 6 },
        { id: "b8", type: "bee", title: "Future Prototypes", content: "Safe zones, habitats", tooltip: "Multispecies safe zones, bee-friendly architectures, restorative micro-habitats, urban sensory inclusivity.", angle: 300, orbit: 6 },
        { id: "b9", type: "bee", title: "Awareness", content: "First step", tooltip: "Recognizing bee presence, understanding their vulnerabilities, seeing urban spaces through their needs.", angle: 340, orbit: 6 }
    ],
    
    // ⭐ CAPA 7 - FUTUROS
    futures: [
        { id: "f1", type: "future", title: "Multispecies Cities", content: "Coexistence design", tooltip: "Urban planning that considers all residents. Shared spaces for humans and nonhumans. Inclusive sensory environments.", angle: 0, orbit: 7 },
        { id: "f2", type: "future", title: "Empathetic Infrastructure", content: "Feeling-based design", tooltip: "Infrastructure designed through empathy. Buildings that consider animal navigation. Public spaces that welcome all bodies.", angle: 72, orbit: 7 },
        { id: "f3", type: "future", title: "Sensory Justice", content: "Accessible perception", tooltip: "Cities where different sensory worlds can coexist. Translation tools as public infrastructure. Cross-species communication systems.", angle: 144, orbit: 7 },
        { id: "f4", type: "future", title: "Restorative Urbanism", content: "Healing damaged ecologies", tooltip: "Urban design that repairs ecosystems. Green corridors for migration. Pollution-remediating architecture.", angle: 216, orbit: 7 },
        { id: "f5", type: "future", title: "Embodied Policy", content: "Experience-driven governance", tooltip: "Policy informed by embodied research. Decision-makers experiencing multispecies perspectives. Empathy as political tool.", angle: 288, orbit: 7 }
    ]
};

// ===== FUNCIONES PARA CONSTRUIR LA RUEDA =====

function buildCityWheel() {
    const nodesContainer = document.getElementById('wheelNodes');
    const connectionsContainer = document.getElementById('wheelConnections');
    
    // Crear nodos
    createNode(cityWheelData.core, nodesContainer, 0);
    
    // Todas las capas en orden
    const allLayers = [
        ...cityWheelData.intuitions,
        ...cityWheelData.questions,
        ...cityWheelData.themes,
        ...cityWheelData.actions,
        ...cityWheelData.beeProject,
        ...cityWheelData.futures
    ];
    
    allLayers.forEach((node, index) => {
        createNode(node, nodesContainer, index + 1);
    });
    
    // Crear conexiones orgánicas
    setTimeout(() => {
        createOrganicConnections(connectionsContainer);
    }, 200);
}

function createNode(nodeData, container, index) {
    const node = document.createElement('div');
    node.className = `wheel-node node-${nodeData.type}`;
    node.dataset.id = nodeData.id;
    node.dataset.type = nodeData.type;
    node.style.setProperty('--node-index', index);
    
    // Añadir clase de color si existe
    if (nodeData.colorClass) {
        node.classList.add(nodeData.colorClass);
    }
    
    // Calcular posición radial
    const orbitRadius = getOrbitRadius(nodeData.orbit);
    const angle = (nodeData.angle * Math.PI) / 180;
    
    const x = 50 + (orbitRadius * Math.cos(angle));
    const y = 50 + (orbitRadius * Math.sin(angle));
    
    node.style.left = `${x}%`;
    node.style.top = `${y}%`;
    
    // Contenido
    const content = document.createElement('div');
    content.className = 'node-content';
    
    const title = document.createElement('div');
    title.className = 'node-title';
    title.textContent = nodeData.title;
    
    const subtitle = document.createElement('div');
    subtitle.className = 'node-subtitle';
    subtitle.textContent = nodeData.content;
    
    content.appendChild(title);
    content.appendChild(subtitle);
    node.appendChild(content);
    
    container.appendChild(node);
    
    // Interacciones
    setupNodeInteractions(node, nodeData);
}

function getOrbitRadius(orbitNumber) {
    const orbitValues = {
        2: 9,    // intuitions: 180px / 2000px * 100 = 9%
        3: 16,   // questions: 320px / 2000px * 100 = 16%
        4: 24,   // themes: 480px / 2000px * 100 = 24%
        5: 34,   // actions: 680px / 2000px * 100 = 34%
        6: 45,   // bee project: 900px / 2000px * 100 = 45%
        7: 55    // futures: 1100px / 2000px * 100 = 55%
    };
    
    return orbitValues[orbitNumber] || 0;
}

// ===== CONEXIONES ORGÁNICAS (BÉZIER) =====

function createOrganicConnections(container) {
    // Crear SVG para conexiones
    const svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
    svg.className = "organic-connection";
    svg.setAttribute("viewBox", "0 0 100 100");
    svg.setAttribute("preserveAspectRatio", "none");
    
    // Conexiones fuertes (núcleo a temas principales)
    createBezierPath(svg, "core", "t1", "strong");
    createBezierPath(svg, "core", "t2", "strong");
    createBezierPath(svg, "core", "t3", "strong");
    createBezierPath(svg, "core", "i1", "strong");
    createBezierPath(svg, "core", "i10", "strong");
    
    // Conexiones entre proyecto abeja y temas relacionados
    createBezierPath(svg, "b6", "t6", "medium");
    createBezierPath(svg, "b2", "t5", "medium");
    createBezierPath(svg, "b1", "t3", "medium");
    createBezierPath(svg, "b7", "t4", "medium");
    
    // Conexiones entre acciones y temas
    createBezierPath(svg, "a1", "t2", "medium");
    createBezierPath(svg, "a2", "t4", "medium");
    createBezierPath(svg, "a3", "t3", "medium");
    createBezierPath(svg, "a6", "t5", "medium");
    
    // Conexiones débiles (red de relaciones)
    createBezierPath(svg, "i1", "q1", "weak");
    createBezierPath(svg, "i4", "q5", "weak");
    createBezierPath(svg, "i10", "b2", "weak");
    createBezierPath(svg, "t4", "a5", "weak");
    createBezierPath(svg, "t5", "f3", "weak");
    createBezierPath(svg, "t6", "f5", "weak");
    
    container.appendChild(svg);
}

function createBezierPath(svg, sourceId, targetId, strength) {
    const source = document.querySelector(`[data-id="${sourceId}"]`);
    const target = document.querySelector(`[data-id="${targetId}"]`);
    
    if (!source || !target) return;
    
    const sourceRect = source.getBoundingClientRect();
    const targetRect = target.getBoundingClientRect();
    const container = document.getElementById('cityWheel');
    const containerRect = container.getBoundingClientRect();
    
    // Coordenadas relativas al contenedor (0-100%)
    const x1 = ((sourceRect.left + sourceRect.width/2 - containerRect.left) / containerRect.width) * 100;
    const y1 = ((sourceRect.top + sourceRect.height/2 - containerRect.top) / containerRect.height) * 100;
    const x2 = ((targetRect.left + targetRect.width/2 - containerRect.left) / containerRect.width) * 100;
    const y2 = ((targetRect.top + targetRect.height/2 - containerRect.top) / containerRect.height) * 100;
    
    // Puntos de control para curva Bézier
    const dx = x2 - x1;
    const dy = y2 - y1;
    const distance = Math.sqrt(dx * dx + dy * dy);
    const curvature = distance * 0.3;
    
    const cx1 = x1 + dx * 0.4 + curvature;
    const cy1 = y1 + dy * 0.4 - curvature;
    const cx2 = x1 + dx * 0.6 - curvature;
    const cy2 = y1 + dy * 0.6 + curvature;
    
    // Crear path
    const path = document.createElementNS("http://www.w3.org/2000/svg", "path");
    const d = `M ${x1} ${y1} C ${cx1} ${cy1}, ${cx2} ${cy2}, ${x2} ${y2}`;
    path.setAttribute("d", d);
    path.classList.add("connection-path", `connection-${strength}`);
    
    svg.appendChild(path);
}

// ===== INTERACCIONES =====

const tooltip = document.getElementById('wheelTooltip');
const tooltipHeader = document.getElementById('tooltipHeader');
const tooltipBody = document.getElementById('tooltipBody');

function setupNodeInteractions(node, nodeData) {
    node.addEventListener('mouseenter', (e) => {
        // Mostrar tooltip
        tooltipHeader.textContent = nodeData.title;
        tooltipBody.textContent = nodeData.tooltip || nodeData.content;
        
        tooltip.style.left = `${e.clientX + 20}px`;
        tooltip.style.top = `${e.clientY + 20}px`;
        tooltip.classList.add('active');
        
        // Resaltar nodo
        node.style.zIndex = "100";
        node.style.filter = "brightness(1.3) drop-shadow(0 0 25px rgba(255,255,255,0.2))";
        node.style.transform = "translate(-50%, -50%) scale(1.15)";
    });
    
    node.addEventListener('mouseleave', () => {
        tooltip.classList.remove('active');
        
        // Restaurar nodo
        node.style.zIndex = "";
        node.style.filter = "";
        node.style.transform = "";
    });
}

// ===== INICIALIZACIÓN =====

document.addEventListener('DOMContentLoaded', () => {
    buildCityWheel();
    
    // Mover tooltip con el mouse
    document.addEventListener('mousemove', (e) => {
        if (tooltip.classList.contains('active')) {
            tooltip.style.left = `${e.clientX + 20}px`;
            tooltip.style.top = `${e.clientY + 20}px`;
        }
    });
    
    // Ajustar en resize
    let resizeTimeout;
    window.addEventListener('resize', () => {
        clearTimeout(resizeTimeout);
        resizeTimeout = setTimeout(() => {
            document.getElementById('wheelConnections').innerHTML = '';
            createOrganicConnections(document.getElementById('wheelConnections'));
        }, 300);
    });
});
</script>