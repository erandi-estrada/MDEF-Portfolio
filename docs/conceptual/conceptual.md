<!-- =============================================== -->
<!-- MAPA DE LA CIUDAD INVISIBLE - ESTILO RUEDA DE EMOCIONES -->
<!-- =============================================== -->

<style>
    /* VARIABLES CON ESPACIADO AMPLIO */
    :root {
        /* Paleta de la rueda de emociones */
        --bg-dark: #0D1117;
        --orbit-gray: rgba(255, 255, 255, 0.03);
        --text-primary: #E6EDF3;
        --text-secondary: #8B949E;
        
        /* Colores por categoría (inspirados en la imagen) */
        --color-core: #238636;        /* Verde principal */
        --color-intuition: #DB61A2;   /* Rosa */
        --color-question: #1F6FEB;    /* Azul */
        --color-theme: #FF7B72;       /* Rojo/naranja */
        --color-action: #FFA657;      /* Naranja */
        --color-bee: #D29922;         /* Amarillo/dorado */
        --color-future: #3FB950;      /* Verde claro */
        
        /* Espaciado MUY amplio como la imagen */
        --orbit-1: 0px;      /* Núcleo */
        --orbit-2: 180px;    /* Intuiciones */
        --orbit-3: 350px;    /* Preguntas */
        --orbit-4: 550px;    /* Temas */
        --orbit-5: 750px;    /* Acciones */
        --orbit-6: 950px;    /* Proyecto Abeja */
        --orbit-7: 1200px;   /* Futuros */
        
        /* Tamaños proporcionales */
        --size-core: 180px;
        --size-layer: 100px;
    }
    
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&display=swap');
    
    /* CONTENEDOR PRINCIPAL - FONDO LIMPIO */
    .emotion-map {
        position: relative;
        width: 1400px;
        height: 1400px;
        max-width: 90vw;
        max-height: 90vh;
        margin: 2rem auto;
        background: var(--bg-dark);
        border-radius: 12px;
        overflow: hidden;
        font-family: 'Inter', sans-serif;
    }
    
    /* FONDO CON ANILLOS MUY SÚTILES */
    .map-background {
        position: absolute;
        width: 100%;
        height: 100%;
        background: 
            radial-gradient(circle at center, transparent 0%, var(--bg-dark) 70%),
            repeating-radial-gradient(circle at center, 
                var(--orbit-gray) 0px, 
                var(--orbit-gray) 1px, 
                transparent 1px, 
                transparent 180px
            );
        z-index: 1;
    }
    
    /* ANILLOS ORBITALES (MUY TENUES) */
    .map-orbit {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 50%;
        border: 0.5px solid rgba(255, 255, 255, 0.05);
        z-index: 2;
    }
    
    .orbit-2 { width: var(--orbit-2); height: var(--orbit-2); }
    .orbit-3 { width: var(--orbit-3); height: var(--orbit-3); }
    .orbit-4 { width: var(--orbit-4); height: var(--orbit-4); }
    .orbit-5 { width: var(--orbit-5); height: var(--orbit-5); }
    .orbit-6 { width: var(--orbit-6); height: var(--orbit-6); }
    .orbit-7 { width: var(--orbit-7); height: var(--orbit-7); }
    
    /* ETIQUETAS DE CAPA (como en la imagen) */
    .orbit-label {
        position: absolute;
        color: var(--text-secondary);
        font-size: 0.75rem;
        font-weight: 500;
        text-transform: uppercase;
        letter-spacing: 1px;
        z-index: 3;
        opacity: 0.6;
    }
    
    /* ===== NÚCLEO CENTRAL GRANDE ===== */
    .core-node {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: var(--size-core);
        height: var(--size-core);
        background: var(--color-core);
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        color: white;
        font-weight: 600;
        font-size: 1.1rem;
        line-height: 1.3;
        padding: 2rem;
        cursor: pointer;
        z-index: 20;
        box-shadow: 
            0 0 0 4px rgba(35, 134, 54, 0.1),
            0 0 0 8px rgba(35, 134, 54, 0.05),
            0 10px 40px rgba(35, 134, 54, 0.3);
        transition: all 0.3s ease;
    }
    
    .core-node:hover {
        transform: translate(-50%, -50%) scale(1.05);
        box-shadow: 
            0 0 0 6px rgba(35, 134, 54, 0.15),
            0 0 0 12px rgba(35, 134, 54, 0.08),
            0 15px 60px rgba(35, 134, 54, 0.4);
    }
    
    /* ===== NODOS DE CAPA - CÍRCULOS SIMPLES ===== */
    .layer-node {
        position: absolute;
        width: var(--size-layer);
        height: var(--size-layer);
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        color: white;
        font-weight: 500;
        font-size: 0.85rem;
        line-height: 1.2;
        padding: 0.75rem;
        cursor: pointer;
        transition: all 0.3s ease;
        z-index: 10;
        box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
    }
    
    /* Colores por tipo de nodo */
    .node-intuition { background: var(--color-intuition); }
    .node-question { background: var(--color-question); }
    .node-theme { background: var(--color-theme); }
    .node-action { background: var(--color-action); }
    .node-bee { background: var(--color-bee); }
    .node-future { background: var(--color-future); }
    
    .layer-node:hover {
        transform: scale(1.1);
        z-index: 100;
        box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
    }
    
    /* Contenido del nodo */
    .node-content {
        max-width: 100%;
        word-wrap: break-word;
    }
    
    .node-title {
        font-weight: 600;
        margin-bottom: 0.25rem;
        font-size: 0.9rem;
    }
    
    .node-subtitle {
        font-size: 0.75rem;
        opacity: 0.9;
        font-weight: 400;
    }
    
    /* ===== CONEXIONES MUY SÚTILES ===== */
    .connection {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 5;
        pointer-events: none;
    }
    
    .connection-line {
        stroke: rgba(255, 255, 255, 0.08);
        stroke-width: 1;
        fill: none;
        transition: all 0.3s ease;
    }
    
    /* ===== TOOLTIP ===== */
    .map-tooltip {
        position: fixed;
        background: rgba(13, 17, 23, 0.98);
        border: 1px solid rgba(255, 255, 255, 0.1);
        border-radius: 8px;
        padding: 1.25rem;
        max-width: 300px;
        z-index: 1000;
        pointer-events: none;
        opacity: 0;
        transform: translateY(10px);
        transition: all 0.2s ease;
        color: var(--text-primary);
        font-size: 0.9rem;
        line-height: 1.5;
        box-shadow: 0 10px 40px rgba(0, 0, 0, 0.4);
    }
    
    .map-tooltip.active {
        opacity: 1;
        transform: translateY(0);
    }
    
    .tooltip-title {
        color: white;
        font-weight: 600;
        margin-bottom: 0.75rem;
        font-size: 1rem;
    }
    
    .tooltip-content {
        opacity: 0.9;
    }
    
    /* ===== LEYENDA ===== */
    .map-legend {
        position: absolute;
        bottom: 2rem;
        right: 2rem;
        background: rgba(13, 17, 23, 0.9);
        border: 1px solid rgba(255, 255, 255, 0.1);
        border-radius: 8px;
        padding: 1.5rem;
        z-index: 50;
        width: 200px;
    }
    
    .legend-title {
        color: var(--text-primary);
        font-size: 0.9rem;
        font-weight: 600;
        margin-bottom: 1rem;
        text-transform: uppercase;
        letter-spacing: 0.5px;
    }
    
    .legend-item {
        display: flex;
        align-items: center;
        margin-bottom: 0.75rem;
        font-size: 0.8rem;
        color: var(--text-secondary);
    }
    
    .legend-color {
        width: 12px;
        height: 12px;
        border-radius: 50%;
        margin-right: 0.75rem;
        flex-shrink: 0;
    }
    
    /* ===== RESPONSIVE ===== */
    @media (max-width: 1200px) {
        .emotion-map {
            width: 1000px;
            height: 1000px;
        }
        
        :root {
            --orbit-2: 150px;
            --orbit-3: 280px;
            --orbit-4: 420px;
            --orbit-5: 560px;
            --orbit-6: 700px;
            --orbit-7: 850px;
            
            --size-core: 160px;
            --size-layer: 90px;
        }
    }
    
    @media (max-width: 768px) {
        .emotion-map {
            width: 800px;
            height: 800px;
        }
        
        :root {
            --orbit-2: 120px;
            --orbit-3: 220px;
            --orbit-4: 340px;
            --orbit-5: 460px;
            --orbit-6: 580px;
            --orbit-7: 700px;
            
            --size-core: 140px;
            --size-layer: 80px;
        }
        
        .core-node {
            font-size: 1rem;
            padding: 1.5rem;
        }
        
        .layer-node {
            font-size: 0.8rem;
            padding: 0.5rem;
        }
        
        .map-legend {
            display: none;
        }
    }
</style>

<!-- =============================================== -->
<!-- HTML - MAPA LIMPIO Y ESPACIADO -->
<!-- =============================================== -->

<div class="emotion-map" id="emotionMap">
    <!-- Fondo con anillos -->
    <div class="map-background"></div>
    
    <!-- Anillos orbitales -->
    <div class="map-orbit orbit-2"></div>
    <div class="map-orbit orbit-3"></div>
    <div class="map-orbit orbit-4"></div>
    <div class="map-orbit orbit-5"></div>
    <div class="map-orbit orbit-6"></div>
    <div class="map-orbit orbit-7"></div>
    
    <!-- Etiquetas de capa -->
    <div class="orbit-label" style="top: 50%; left: calc(50% + 95px);">Intuitions</div>
    <div class="orbit-label" style="top: 50%; left: calc(50% + 180px);">Questions</div>
    <div class="orbit-label" style="top: 50%; left: calc(50% + 280px);">Themes</div>
    <div class="orbit-label" style="top: 50%; left: calc(50% + 380px);">Actions</div>
    <div class="orbit-label" style="top: 50%; left: calc(50% + 480px);">Bee Project</div>
    <div class="orbit-label" style="top: 50%; left: calc(50% + 600px);">Futures</div>
    
    <!-- Contenedores -->
    <div class="core-node" id="coreNode">
        THE INVISIBLE CITY<br>
        <span style="font-size: 0.9rem; opacity: 0.9;">Beauty hides violence</span>
    </div>
    
    <div id="layerNodes"></div>
    <div class="connection" id="connections"></div>
    
    <!-- Tooltip -->
    <div class="map-tooltip" id="mapTooltip">
        <div class="tooltip-title" id="tooltipTitle"></div>
        <div class="tooltip-content" id="tooltipContent"></div>
    </div>
    
    <!-- Leyenda -->
    <div class="map-legend">
        <div class="legend-title">Map Layers</div>
        <div class="legend-item">
            <div class="legend-color" style="background: var(--color-intuition);"></div>
            <span>Intuitions (12)</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background: var(--color-question);"></div>
            <span>Motor Questions</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background: var(--color-theme);"></div>
            <span>Thematic Fields</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background: var(--color-action);"></div>
            <span>Actions</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background: var(--color-bee);"></div>
            <span>Bee Project</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background: var(--color-future);"></div>
            <span>Emergent Futures</span>
        </div>
    </div>
</div>

<script>
// ===== DATOS ORGANIZADOS CON ESPACIADO =====

const emotionMapData = {
    // 💎 INTUICIONES (Capa 2 - 12 elementos bien espaciados)
    intuitions: [
        { id: 'i1', type: 'intuition', title: 'Make visible', content: 'The invisible', angle: 0 },
        { id: 'i2', type: 'intuition', title: 'Feel others', content: 'Cross-species empathy', angle: 30 },
        { id: 'i3', type: 'intuition', title: 'Beauty wrong', content: 'Aesthetic violence', angle: 60 },
        { id: 'i4', type: 'intuition', title: 'Silent violence', content: 'Architectural control', angle: 90 },
        { id: 'i5', type: 'intuition', title: 'Lives erased', content: 'Selective existence', angle: 120 },
        { id: 'i6', type: 'intuition', title: 'Nature controlled', content: 'Decoration only', angle: 150 },
        { id: 'i7', type: 'intuition', title: 'Life returns', content: 'When invited', angle: 180 },
        { id: 'i8', type: 'intuition', title: 'Embodied empathy', content: 'Not information', angle: 210 },
        { id: 'i9', type: 'intuition', title: 'Human-centric', content: 'Ignores others', angle: 240 },
        { id: 'i10', type: 'intuition', title: 'Sense differently', content: 'Would we change?', angle: 270 },
        { id: 'i11', type: 'intuition', title: 'Control hidden', content: 'Behind beauty', angle: 300 },
        { id: 'i12', type: 'intuition', title: 'Tiny acts', content: 'Reveal systems', angle: 330 }
    ],
    
    // ⚪ PREGUNTAS (Capa 3 - 8 elementos)
    questions: [
        { id: 'q1', type: 'question', title: 'Allowed lives?', content: 'In the city', angle: 0 },
        { id: 'q2', type: 'question', title: 'Violence sanitized', content: 'Through aesthetics', angle: 45 },
        { id: 'q3', type: 'question', title: 'Translate senses', content: 'Nonhuman worlds', angle: 90 },
        { id: 'q4', type: 'question', title: 'Awareness → action', content: 'Pathway', angle: 135 },
        { id: 'q5', type: 'question', title: 'Hidden systems', content: 'Make visible', angle: 180 },
        { id: 'q6', type: 'question', title: 'Multispecies justice', content: 'Coexistence', angle: 225 },
        { id: 'q7', type: 'question', title: 'Translation methods', content: 'Tools needed', angle: 270 },
        { id: 'q8', type: 'question', title: 'Empathy → change', content: 'How?', angle: 315 }
    ],
    
    // 🟠 TEMAS (Capa 4 - 6 elementos)
    themes: [
        { id: 't1', type: 'theme', title: 'Urban Aesthetics', content: 'Beauty as politics', angle: 0 },
        { id: 't2', type: 'theme', title: 'Hostile Design', content: 'Architecture expels', angle: 60 },
        { id: 't3', type: 'theme', title: 'Multispecies Justice', content: 'Beyond human rights', angle: 120 },
        { id: 't4', type: 'theme', title: 'Embodied Research', content: 'Body as sensor', angle: 180 },
        { id: 't5', type: 'theme', title: 'Sensory Translation', content: 'Cross-species perception', angle: 240 },
        { id: 't6', type: 'theme', title: 'Environmental Empathy', content: 'Feeling-with ecosystems', angle: 300 }
    ],
    
    // 🌙 ACCIONES (Capa 5 - 6 elementos)
    actions: [
        { id: 'a1', type: 'action', title: 'Sitting Hostile', content: 'Body as sensor', angle: 30 },
        { id: 'a2', type: 'action', title: 'Wearing Hostility', content: 'Material translation', angle: 90 },
        { id: 'a3', type: 'action', title: 'Returning Life', content: 'Rewilding acts', angle: 150 },
        { id: 'a4', type: 'action', title: 'Beauty Excludes', content: 'Documenting erasure', angle: 210 },
        { id: 'a5', type: 'action', title: 'Hidden Infrastructures', content: 'Patterns of control', angle: 270 },
        { id: 'a6', type: 'action', title: 'Sensory Experiments', content: 'Perception interfaces', angle: 330 }
    ],
    
    // 🐝 PROYECTO ABEJA (Capa 6 - 8 elementos)
    beeProject: [
        { id: 'b1', type: 'bee', title: 'Vulnerabilities', content: 'Pesticides, habitat', angle: 0 },
        { id: 'b2', type: 'bee', title: 'Sensory World', content: 'UV, vibrations', angle: 45 },
        { id: 'b3', type: 'bee', title: 'Human Conflicts', content: 'Aesthetic removal', angle: 90 },
        { id: 'b4', type: 'bee', title: 'Violence Infra', content: 'Systems', angle: 135 },
        { id: 'b5', type: 'bee', title: 'Translation Methods', content: 'Tools', angle: 180 },
        { id: 'b6', type: 'bee', title: 'Empathy Pathway', content: 'Awareness → action', angle: 225 },
        { id: 'b7', type: 'bee', title: 'Sensory Install', content: 'Final outcome', angle: 270 },
        { id: 'b8', type: 'bee', title: 'Future Prototypes', content: 'Safe zones', angle: 315 }
    ],
    
    // ⭐ FUTUROS (Capa 7 - 5 elementos)
    futures: [
        { id: 'f1', type: 'future', title: 'Multispecies Cities', content: 'Coexistence design', angle: 0 },
        { id: 'f2', type: 'future', title: 'Empathetic Infra', content: 'Feeling-based design', angle: 72 },
        { id: 'f3', type: 'future', title: 'Sensory Justice', content: 'Accessible perception', angle: 144 },
        { id: 'f4', type: 'future', title: 'Restorative Urbanism', content: 'Healing ecologies', angle: 216 },
        { id: 'f5', type: 'future', title: 'Embodied Policy', content: 'Experience-driven', angle: 288 }
    ]
};

// ===== FUNCIONES DE CONSTRUCCIÓN =====

function buildEmotionMap() {
    const container = document.getElementById('layerNodes');
    const connectionsContainer = document.getElementById('connections');
    
    // Construir todas las capas
    buildLayer(emotionMapData.intuitions, 2, container);
    buildLayer(emotionMapData.questions, 3, container);
    buildLayer(emotionMapData.themes, 4, container);
    buildLayer(emotionMapData.actions, 5, container);
    buildLayer(emotionMapData.beeProject, 6, container);
    buildLayer(emotionMapData.futures, 7, container);
    
    // Configurar tooltip del núcleo
    setupCoreNode();
    
    // Crear conexiones mínimas
    setTimeout(() => {
        createMinimalConnections(connectionsContainer);
    }, 100);
}

function buildLayer(nodes, orbitNumber, container) {
    const orbitRadius = getOrbitRadius(orbitNumber);
    const centerX = 50; // Porcentaje
    const centerY = 50;
    
    nodes.forEach(node => {
        const angleRad = (node.angle * Math.PI) / 180;
        const x = centerX + (orbitRadius * Math.cos(angleRad));
        const y = centerY + (orbitRadius * Math.sin(angleRad));
        
        const nodeElement = document.createElement('div');
        nodeElement.className = `layer-node node-${node.type}`;
        nodeElement.style.left = `${x}%`;
        nodeElement.style.top = `${y}%`;
        nodeElement.dataset.id = node.id;
        nodeElement.dataset.type = node.type;
        
        // Contenido
        const content = document.createElement('div');
        content.className = 'node-content';
        
        const title = document.createElement('div');
        title.className = 'node-title';
        title.textContent = node.title;
        
        const subtitle = document.createElement('div');
        subtitle.className = 'node-subtitle';
        subtitle.textContent = node.content;
        
        content.appendChild(title);
        content.appendChild(subtitle);
        nodeElement.appendChild(content);
        
        // Tooltip según tipo
        const tooltipText = getTooltipForNode(node);
        nodeElement.addEventListener('mouseenter', (e) => showTooltip(node.title, tooltipText, e));
        nodeElement.addEventListener('mouseleave', hideTooltip);
        
        container.appendChild(nodeElement);
    });
}

function getOrbitRadius(orbitNumber) {
    // Valores en porcentaje del contenedor
    const orbits = {
        2: 9,   // 180px / 2000px * 100
        3: 17.5, // 350px / 2000px * 100
        4: 27.5, // 550px / 2000px * 100
        5: 37.5, // 750px / 2000px * 100
        6: 47.5, // 950px / 2000px * 100
        7: 60    // 1200px / 2000px * 100
    };
    return orbits[orbitNumber] || 0;
}

function getTooltipForNode(node) {
    const tooltips = {
        'i1': 'Make the invisible visible. Urban beauty hides infrastructures of violence toward humans, animals, and ecosystems.',
        'i2': 'Feel what other species feel. Empathy requires temporarily inhabiting sensory vulnerabilities we do not normally perceive.',
        'i3': 'The city is beautiful, but something feels wrong. Aesthetic order often disguises exclusion.',
        'i10': 'If humans could sense the city like another species, would we act differently? This question anchors your main research.',
        't1': 'Urban Aesthetics: Beauty, order, cleanliness as political tools. Tourism-driven visual control. Aesthetic erasure of life.',
        't2': 'Hostile Design: Anti-homeless architecture, pigeon spikes, surfaces that deny rest. Violence normalized through design.',
        't3': 'Multispecies Justice: Rights to presence, rest, shelter. Nonhuman citizenship. Shared urban vulnerabilities.',
        't5': 'Sensory Translation: Interfaces for perceiving pollution, noise, vibration as other species might experience them.',
        'b1': 'Bee Vulnerabilities: Pesticides, habitat fragmentation, urban monoculture plants, heat islands, pollution.',
        'b2': 'Bee Sensory World: UV vision, vibrational communication, chemical signaling, spatial memory, magnetoreception.',
        'f4': 'Restorative Urbanism: Urban design that repairs ecosystems. Green corridors for migration. Healing damaged ecologies.'
    };
    
    return tooltips[node.id] || `${node.title}: ${node.content}`;
}

function setupCoreNode() {
    const coreNode = document.getElementById('coreNode');
    const coreTooltip = `The city appears clean, beautiful and orderly, but this beauty often conceals structural violence against both humans and nonhuman species. By exposing hidden infrastructures of exclusion, we can move from awareness → empathy → multispecies futures.`;
    
    coreNode.addEventListener('mouseenter', (e) => {
        showTooltip('THE INVISIBLE CITY', coreTooltip, e);
    });
    
    coreNode.addEventListener('mouseleave', hideTooltip);
}

// ===== CONEXIONES MÍNIMAS =====

function createMinimalConnections(container) {
    const svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
    svg.setAttribute("viewBox", "0 0 100 100");
    svg.setAttribute("preserveAspectRatio", "none");
    svg.style.width = "100%";
    svg.style.height = "100%";
    
    // Solo 5-6 conexiones principales (como en la rueda de emociones)
    createConnection(svg, 'core', 't1');
    createConnection(svg, 'core', 't3');
    createConnection(svg, 'core', 'i10');
    createConnection(svg, 't5', 'b2');
    createConnection(svg, 't3', 'f4');
    createConnection(svg, 't4', 'a1');
    
    container.appendChild(svg);
}

function createConnection(svg, sourceId, targetId) {
    const source = document.querySelector(`[data-id="${sourceId}"]`) || document.getElementById('coreNode');
    const target = document.querySelector(`[data-id="${targetId}"]`);
    
    if (!source || !target) return;
    
    const sourceRect = source.getBoundingClientRect();
    const targetRect = target.getBoundingClientRect();
    const container = document.getElementById('emotionMap');
    const containerRect = container.getBoundingClientRect();
    
    const x1 = ((sourceRect.left + sourceRect.width/2 - containerRect.left) / containerRect.width) * 100;
    const y1 = ((sourceRect.top + sourceRect.height/2 - containerRect.top) / containerRect.height) * 100;
    const x2 = ((targetRect.left + targetRect.width/2 - containerRect.left) / containerRect.width) * 100;
    const y2 = ((targetRect.top + targetRect.height/2 - containerRect.top) / containerRect.height) * 100;
    
    const line = document.createElementNS("http://www.w3.org/2000/svg", "line");
    line.setAttribute("x1", x1);
    line.setAttribute("y1", y1);
    line.setAttribute("x2", x2);
    line.setAttribute("y2", y2);
    line.classList.add("connection-line");
    
    svg.appendChild(line);
}

// ===== TOOLTIP SYSTEM =====

const tooltip = document.getElementById('mapTooltip');
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

// ===== INICIALIZACIÓN =====

document.addEventListener('DOMContentLoaded', () => {
    buildEmotionMap();
    
    // Mover tooltip con el mouse
    document.addEventListener('mousemove', (e) => {
        if (tooltip.classList.contains('active')) {
            tooltip.style.left = `${e.clientX + 15}px`;
            tooltip.style.top = `${e.clientY + 15}px`;
        }
    });
});
</script>