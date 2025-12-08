<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    :root {
        --core-color: #00c6ff;
        --intuitions-color: #b967ff;
        --questions-color: #ffffff;
        --thematic-color: #ffb347;
        --actions-color: #ff5e7d;
        --bee-color: #00d8a7;
        --fieldwork-color: #ff8a65;
        --bg-dark: #0a0e17;
        --bg-darker: #050811;
        --text-light: #f0f4ff;
        --text-muted: #a0a8c9;
    }

    body {
        font-family: 'Montserrat', sans-serif;
        background-color: var(--bg-dark);
        color: var(--text-light);
        overflow: hidden;
        height: 100vh;
        position: relative;
    }

    /* Fondo cósmico con estrellas */
    #stars {
        position: absolute;
        width: 100%;
        height: 100%;
        z-index: -1;
    }

    .star {
        position: absolute;
        background-color: white;
        border-radius: 50%;
        opacity: 0;
        animation: twinkle 5s infinite;
    }

    @keyframes twinkle {
        0%, 100% { opacity: 0.1; }
        50% { opacity: 0.8; }
    }

    /* Contenedor principal - AHORA ES DESPLAZABLE */
    .container {
        width: 200%; /* Más ancho para permitir scroll */
        height: 200%; /* Más alto para permitir scroll */
        position: relative;
        transform-origin: 0 0;
        transform: scale(1);
        transition: transform 0.3s ease;
    }

    /* Galaxia ahora ocupa toda la pantalla */
    #galaxy {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: visible;
    }

    /* Canvas para la galaxia radial */
    #galaxy-canvas {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
    }

    /* Nodo central - MÁS GRANDE */
    .central-node {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 200px; /* Aumentado de 120px */
        height: 200px; /* Aumentado de 120px */
        border-radius: 50%;
        background: radial-gradient(circle, var(--core-color) 0%, rgba(0, 198, 255, 0.3) 70%, transparent 100%);
        box-shadow: 0 0 60px rgba(0, 198, 255, 0.7);
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        z-index: 2;
        transition: all 0.3s ease;
    }

    .central-node:hover {
        transform: translate(-50%, -50%) scale(1.1);
        box-shadow: 0 0 80px rgba(0, 198, 255, 0.9);
    }

    .central-node-content {
        text-align: center;
        padding: 20px;
    }

    .central-node-title {
        font-weight: 700;
        font-size: 1.6rem; /* Aumentado */
        text-transform: uppercase;
        letter-spacing: 1px;
        margin-bottom: 10px;
        color: #000000; /* TEXTO NEGRO */
    }

    /* Contenedor de nodos orbitales */
    .orbit {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 50%;
        border: 1px solid rgba(255, 255, 255, 0.05);
    }

    /* Nodos - MUCHO MÁS GRANDES */
    .node {
        position: absolute;
        width: 120px; /* Aumentado de 60px */
        height: 120px; /* Aumentado de 60px */
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        transition: all 0.3s ease;
        z-index: 1;
    }

    .node-title {
        font-weight: 600;
        font-size: 0.9rem; /* Aumentado */
        text-align: center;
        text-transform: uppercase;
        letter-spacing: 0.5px;
        padding: 0 10px;
        color: #000000; /* TEXTO NEGRO - Cambiado de blanco */
        text-shadow: 0 1px 2px rgba(255, 255, 255, 0.5); /* Sombra para mejor legibilidad */
    }

    /* Colores de nodos según categoría - MÁS BRILLANTES */
    .intuition-node {
        background: radial-gradient(circle, var(--intuitions-color) 0%, rgba(185, 103, 255, 0.6) 70%, transparent 100%);
        box-shadow: 0 0 30px rgba(185, 103, 255, 0.7);
    }

    .question-node {
        background: radial-gradient(circle, var(--questions-color) 0%, rgba(255, 255, 255, 0.6) 70%, transparent 100%);
        box-shadow: 0 0 30px rgba(255, 255, 255, 0.7);
    }

    .thematic-node {
        background: radial-gradient(circle, var(--thematic-color) 0%, rgba(255, 179, 71, 0.6) 70%, transparent 100%);
        box-shadow: 0 0 30px rgba(255, 179, 71, 0.7);
    }

    .action-node {
        background: radial-gradient(circle, var(--actions-color) 0%, rgba(255, 94, 125, 0.6) 70%, transparent 100%);
        box-shadow: 0 0 30px rgba(255, 94, 125, 0.7);
    }

    .bee-node {
        background: radial-gradient(circle, var(--bee-color) 0%, rgba(0, 216, 167, 0.6) 70%, transparent 100%);
        box-shadow: 0 0 30px rgba(0, 216, 167, 0.7);
    }

    .fieldwork-node {
        background: radial-gradient(circle, var(--fieldwork-color) 0%, rgba(255, 138, 101, 0.6) 70%, transparent 100%);
        box-shadow: 0 0 30px rgba(255, 138, 101, 0.7);
    }

    /* Efectos hover en nodos */
    .node:hover {
        transform: scale(1.2); /* Efecto hover más pronunciado */
        z-index: 3;
    }

    /* Panel de contenido */
    .content-panel {
        position: absolute;
        top: 20px;
        right: 20px;
        width: 350px;
        background: rgba(10, 14, 23, 0.9);
        backdrop-filter: blur(10px);
        border-radius: 12px;
        padding: 25px;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        border: 1px solid rgba(255, 255, 255, 0.08);
        z-index: 100; /* Mayor z-index para que esté encima de todo */
        display: none;
        transition: all 0.4s ease;
    }

    .content-panel.active {
        display: block;
        animation: fadeIn 0.4s ease;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
    }

    .panel-title {
        font-size: 1.3rem;
        font-weight: 700;
        margin-bottom: 10px;
        text-transform: uppercase;
        letter-spacing: 0.5px;
        color: #ffffff;
    }

    .panel-category {
        display: inline-block;
        font-size: 0.8rem;
        padding: 4px 12px;
        border-radius: 20px;
        margin-bottom: 15px;
        font-weight: 600;
        color: #000000; /* Texto negro en etiquetas */
    }

    .panel-text {
        font-size: 0.95rem;
        line-height: 1.6;
        color: var(--text-muted);
        margin-bottom: 20px;
    }

    .panel-close {
        position: absolute;
        top: 15px;
        right: 15px;
        background: none;
        border: none;
        color: var(--text-muted);
        font-size: 1.2rem;
        cursor: pointer;
        transition: color 0.3s;
    }

    .panel-close:hover {
        color: var(--text-light);
    }

    /* Leyenda */
    .legend {
        position: fixed;
        bottom: 20px;
        left: 20px;
        background: rgba(10, 14, 23, 0.9);
        backdrop-filter: blur(5px);
        border-radius: 10px;
        padding: 15px;
        border: 1px solid rgba(255, 255, 255, 0.08);
        z-index: 100;
        max-width: 300px;
    }

    .legend-title {
        font-size: 0.9rem;
        font-weight: 600;
        margin-bottom: 10px;
        text-transform: uppercase;
        letter-spacing: 0.5px;
        color: #ffffff;
    }

    .legend-items {
        display: flex;
        flex-wrap: wrap;
        gap: 8px;
    }

    .legend-item {
        display: flex;
        align-items: center;
        margin-bottom: 5px;
        font-size: 0.8rem;
    }

    .legend-color {
        width: 12px;
        height: 12px;
        border-radius: 50%;
        margin-right: 8px;
    }

    /* Instrucciones */
    .instructions {
        position: fixed;
        bottom: 20px;
        right: 20px;
        text-align: right;
        font-size: 0.9rem;
        color: var(--text-muted);
        z-index: 100;
        background: rgba(10, 14, 23, 0.7);
        padding: 10px 15px;
        border-radius: 8px;
        border: 1px solid rgba(255, 255, 255, 0.05);
    }

    /* Controles de navegación */
    .navigation-controls {
        position: fixed;
        top: 20px;
        left: 20px;
        z-index: 100;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }

    .nav-button {
        background: rgba(10, 14, 23, 0.8);
        border: 1px solid rgba(255, 255, 255, 0.1);
        color: white;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        font-size: 1.2rem;
        transition: all 0.3s ease;
    }

    .nav-button:hover {
        background: rgba(0, 198, 255, 0.3);
        transform: scale(1.1);
    }

    /* Responsive */
    @media (max-width: 1200px) {
        .content-panel {
            width: 300px;
        }
        
        .legend {
            max-width: 250px;
        }
    }

    @media (max-width: 768px) {
        .content-panel {
            width: calc(100% - 40px);
            right: 20px;
            left: 20px;
        }
        
        .legend {
            max-width: 200px;
            bottom: 10px;
            left: 10px;
        }
        
        .instructions {
            display: none;
        }
        
        .central-node {
            width: 150px;
            height: 150px;
        }
        
        .node {
            width: 100px;
            height: 100px;
        }
    }
</style>

<!-- Aquí empieza el HTML que debes insertar en tu página -->
<div id="stars"></div>

<!-- Controles de navegación -->
<div class="navigation-controls">
    <button class="nav-button" id="zoomIn">+</button>
    <button class="nav-button" id="zoomOut">-</button>
    <button class="nav-button" id="resetView">↺</button>
</div>

<div class="container" id="mainContainer">
    <div id="galaxy">
        <canvas id="galaxy-canvas"></canvas>
        
        <!-- Nodo central -->
        <div class="central-node" id="centralNode">
            <div class="central-node-content">
                <div class="central-node-title">The Invisible City</div>
            </div>
        </div>
        
        <!-- Nodos serán generados por JavaScript -->
    </div>
</div>

<!-- Panel de contenido -->
<div class="content-panel" id="contentPanel">
    <button class="panel-close" id="closePanel">×</button>
    <div class="panel-category" id="panelCategory">Core Concept</div>
    <h2 class="panel-title" id="panelTitle">The Invisible City</h2>
    <p class="panel-text" id="panelText">How beauty hides violence, and how other species experience the city through sensory worlds we ignore. A framework connecting hostile design, multispecies inequalities, and environmental perception.</p>
    <div id="panelConnections"></div>
</div>

<!-- Leyenda -->
<div class="legend">
    <div class="legend-title">Categorías</div>
    <div class="legend-items">
        <div class="legend-item">
            <div class="legend-color" style="background-color: var(--core-color);"></div>
            <span>Concepto Central</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: var(--intuitions-color);"></div>
            <span>Intuiciones</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: var(--questions-color);"></div>
            <span>Preguntas Motor</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: var(--thematic-color);"></div>
            <span>Campos Temáticos</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: var(--actions-color);"></div>
            <span>Acciones</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: var(--bee-color);"></div>
            <span>Proyecto Abeja</span>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: var(--fieldwork-color);"></div>
            <span>Trabajo de Campo</span>
        </div>
    </div>
</div>

<div class="instructions">
    • Haz clic en cualquier nodo para ver detalles<br>
    • Usa la rueda del ratón para hacer zoom<br>
    • Arrastra para mover el mapa<br>
    • Usa los botones + - para controlar el zoom
</div>

<script>
    // Datos para todos los nodos
    const nodesData = {
        // Nodo central
        central: {
            id: "central",
            title: "The Invisible City",
            text: "How beauty hides violence, and how other species experience the city through sensory worlds we ignore. A framework connecting hostile design, multispecies inequalities, and environmental perception.",
            category: "Core Concept",
            color: "var(--core-color)",
            connections: ["intuitions", "thematic", "actions"]
        },
        
        // Intuiciones
        intuitions: [
            {id: "intuition1", title: "Make the invisible visible", text: "Urban beauty hides systems of exclusion.", category: "Intuitions"},
            {id: "intuition2", title: "Humans should feel what other species feel", text: "Embodied empathy is more powerful than awareness.", category: "Intuitions"},
            {id: "intuition3", title: "The city looks beautiful, but something feels wrong", text: "Aesthetic order conceals deeper violence.", category: "Intuitions"},
            {id: "intuition4", title: "Violence can be silent, aesthetic, normalized", text: "Architectural control disguised as 'cleanliness'.", category: "Intuitions"},
            {id: "intuition5", title: "Some lives are allowed; others are erased", text: "Cities decide who belongs — humans and nonhumans.", category: "Intuitions"},
            {id: "intuition6", title: "Nature is only welcome as decoration", text: "Spontaneous life is considered disorder.", category: "Intuitions"},
            {id: "intuition7", title: "Life returns when invited", text: "Plants, birds, insects reclaim space when allowed.", category: "Intuitions"},
            {id: "intuition8", title: "Empathy requires embodiment, not information", text: "Data does not change behavior — felt experience does.", category: "Intuitions"},
            {id: "intuition9", title: "Human design ignores multispecies perception", text: "Urban systems are tuned solely to human comfort.", category: "Intuitions"},
            {id: "intuition10", title: "If humans sensed like them, would they act differently?", text: "This question drives the entire project.", category: "Intuitions"},
            {id: "intuition11", title: "Beauty hides infrastructures of control", text: "Rules, bans, and exclusions disguised as aesthetics.", category: "Intuitions"},
            {id: "intuition12", title: "Small actions expose big systems", text: "Sitting, planting, wearing — micro-actions reveal macro-political structures.", category: "Intuitions"}
        ],
        
        // Preguntas motor
        questions: [
            {id: "question1", title: "What lives are allowed?", text: "Investigating which lives are welcomed and which are excluded in urban spaces.", category: "Motor Questions"},
            {id: "question2", title: "How does beauty justify exclusion?", text: "Exploring how aesthetic decisions mask systems of control.", category: "Motor Questions"},
            {id: "question3", title: "What bodies can rest?", text: "Examining who is allowed to inhabit and rest in public spaces.", category: "Motor Questions"},
            {id: "question4", title: "What violence have we normalized?", text: "Uncovering the everyday violence hidden in urban design.", category: "Motor Questions"},
            {id: "question5", title: "Can design generate empathy?", text: "Questioning whether design can foster multispecies empathy.", category: "Motor Questions"},
            {id: "question6", title: "How would another species design the city?", text: "Imagining urban spaces from non-human perspectives.", category: "Motor Questions"},
            {id: "question7", title: "What sensory worlds are we ignoring?", text: "Exploring the sensory experiences of other species in cities.", category: "Motor Questions"},
            {id: "question8", title: "How does pollution reshape more-than-human life?", text: "Investigating the impact of urban pollution on non-human life.", category: "Motor Questions"}
        ],
        
        // Campos temáticos
        thematic: [
            {id: "thematic1", title: "Urban Aesthetics", text: "Beauty as control; order as exclusion.", category: "Thematic Fields"},
            {id: "thematic2", title: "Hostile Design", text: "Architecture that denies presence, rest, or habitation.", category: "Thematic Fields"},
            {id: "thematic3", title: "Multispecies Justice", text: "Rights, coexistence, and vulnerability beyond the human.", category: "Thematic Fields"},
            {id: "thematic4", title: "Embodied Research", text: "Using the body to reveal invisible systems.", category: "Thematic Fields"},
            {id: "thematic5", title: "Sensory Translation", text: "Rewriting environmental data into human-perceivable forms.", category: "Thematic Fields"},
            {id: "thematic6", title: "Environmental Empathy", text: "Understanding pollution through the sensory worlds of bees.", category: "Thematic Fields"}
        ],
        
        // Acciones
        actions: [
            {id: "action1", title: "Sitting on Hostile Architecture", text: "Revealing micro-violence through your body.", category: "Actions"},
            {id: "action2", title: "Returning Life Interventions", text: "Reintroducing plants where nature has been erased.", category: "Actions"},
            {id: "action3", title: "Wearing Hostility", text: "Embodied critique of anti-bird / anti-homeless design.", category: "Actions"},
            {id: "action4", title: "Sensory Experiments", text: "Building tools that translate pollution into sensory experience.", category: "Actions"}
        ],
        
        // Proyecto abeja
        bee: [
            {id: "bee1", title: "Pollution Translation", text: "How environmental toxins distort bee perception.", category: "Bee Project"},
            {id: "bee2", title: "Urban Threat Mapping", text: "Light, chemicals, noise, temperature stress.", category: "Bee Project"},
            {id: "bee3", title: "Multispecies Perception Interface", text: "Translating bee sensory vulnerability into human experience.", category: "Bee Project"},
            {id: "bee4", title: "Environmental Data Collection", text: "Using tools to understand urban toxicity from the perspective of bees (not human comfort).", category: "Bee Project"},
            {id: "bee5", title: "Ecological Importance", text: "Bees as pollinators, ecosystem stabilizers, and indicators of environmental health.", category: "Bee Project"},
            {id: "bee6", title: "Species-Level Vulnerability", text: "How pollution destabilizes bee navigation, memory, hive health.", category: "Bee Project"}
        ],
        
        // Trabajo de campo
        fieldwork: [
            {id: "fieldwork1", title: "Hostile Aesthetics Mapping", text: "Photos + notes of spikes, anti-homeless architecture, barriers.", category: "Urban Fieldwork"},
            {id: "fieldwork2", title: "City-as-Performance", text: "Barcelona as spectacle; bodies curated for tourism.", category: "Urban Fieldwork"},
            {id: "fieldwork3", title: "Life Expelled from the City", text: "Plants removed, pigeons denied resting spots.", category: "Urban Fieldwork"},
            {id: "fieldwork4", title: "Life Returning", text: "Plant interventions, pigeons reclaiming benches.", category: "Urban Fieldwork"}
        ]
    };

    // Variables globales
    let canvas, ctx;
    let stars = [];
    let nodes = [];
    let connections = [];
    let selectedNode = null;
    let zoom = 0.8; // Zoom inicial más pequeño para ver más
    let offsetX = 0, offsetY = 0;
    let isDragging = false;
    let dragStartX = 0, dragStartY = 0;
    let initialOffsetX = 0, initialOffsetY = 0;

    // Inicializar estrellas
    function initStars() {
        const starsContainer = document.getElementById('stars');
        starsContainer.innerHTML = '';
        
        for (let i = 0; i < 200; i++) { // Más estrellas
            const star = document.createElement('div');
            star.classList.add('star');
            
            // Tamaño aleatorio
            const size = Math.random() * 4 + 1;
            star.style.width = `${size}px`;
            star.style.height = `${size}px`;
            
            // Posición aleatoria
            star.style.left = `${Math.random() * 100}%`;
            star.style.top = `${Math.random() * 100}%`;
            
            // Retraso de animación aleatorio
            star.style.animationDelay = `${Math.random() * 5}s`;
            
            starsContainer.appendChild(star);
        }
    }

    // Crear nodos orbitales - CON ÓRBITAS MÁS GRANDES
    function createOrbitalNodes() {
        const galaxy = document.getElementById('galaxy');
        
        // Crear órbitas - RADIOS MÁS GRANDES PARA MÁS ESPACIO
        const orbits = [
            {radius: 250, nodes: nodesData.intuitions, className: 'intuition-node'}, // Aumentado de 120
            {radius: 400, nodes: nodesData.questions, className: 'question-node'}, // Aumentado de 200
            {radius: 550, nodes: nodesData.thematic, className: 'thematic-node'}, // Aumentado de 300
            {radius: 700, nodes: nodesData.actions, className: 'action-node'}, // Aumentado de 400
            {radius: 850, nodes: nodesData.bee, className: 'bee-node'}, // Aumentado de 500
            {radius: 1000, nodes: nodesData.fieldwork, className: 'fieldwork-node'} // Aumentado de 600
        ];
        
        orbits.forEach((orbit, orbitIndex) => {
            // Crear anillo orbital
            const orbitElement = document.createElement('div');
            orbitElement.classList.add('orbit');
            orbitElement.style.width = `${orbit.radius * 2}px`;
            orbitElement.style.height = `${orbit.radius * 2}px`;
            galaxy.appendChild(orbitElement);
            
            // Crear nodos en esta órbita
            orbit.nodes.forEach((nodeData, nodeIndex) => {
                const node = document.createElement('div');
                node.classList.add('node', orbit.className);
                node.id = nodeData.id;
                node.dataset.title = nodeData.title;
                node.dataset.text = nodeData.text;
                node.dataset.category = nodeData.category;
                
                // Calcular posición angular con distribución más espaciada
                const angle = (nodeIndex / orbit.nodes.length) * 2 * Math.PI;
                const x = orbit.radius * Math.cos(angle);
                const y = orbit.radius * Math.sin(angle);
                
                // Posicionar nodo
                node.style.left = `calc(50% + ${x}px)`;
                node.style.top = `calc(50% + ${y}px)`;
                node.style.transform = 'translate(-50%, -50%)';
                
                // Añadir título - CON TEXTO NEGRO
                const titleElement = document.createElement('div');
                titleElement.classList.add('node-title');
                titleElement.textContent = nodeData.title;
                titleElement.style.color = '#000000'; // Texto negro
                titleElement.style.textShadow = '0 1px 3px rgba(255, 255, 255, 0.7)'; // Sombra blanca para contraste
                node.appendChild(titleElement);
                
                // Añadir evento de clic
                node.addEventListener('click', (e) => {
                    e.stopPropagation();
                    showNodeContent(nodeData);
                });
                
                galaxy.appendChild(node);
            });
        });
        
        // Añadir evento al nodo central
        document.getElementById('centralNode').addEventListener('click', (e) => {
            e.stopPropagation();
            showNodeContent(nodesData.central);
        });
    }

    // Mostrar contenido del nodo
    function showNodeContent(nodeData) {
        const panel = document.getElementById('contentPanel');
        const panelTitle = document.getElementById('panelTitle');
        const panelText = document.getElementById('panelText');
        const panelCategory = document.getElementById('panelCategory');
        const panelConnections = document.getElementById('panelConnections');
        
        // Establecer contenido
        panelTitle.textContent = nodeData.title;
        panelText.textContent = nodeData.text;
        panelCategory.textContent = nodeData.category;
        
        // Establecer color según categoría
        let color = '';
        switch(nodeData.category) {
            case 'Core Concept': color = 'var(--core-color)'; break;
            case 'Intuitions': color = 'var(--intuitions-color)'; break;
            case 'Motor Questions': color = 'var(--questions-color)'; break;
            case 'Thematic Fields': color = 'var(--thematic-color)'; break;
            case 'Actions': color = 'var(--actions-color)'; break;
            case 'Bee Project': color = 'var(--bee-color)'; break;
            case 'Urban Fieldwork': color = 'var(--fieldwork-color)'; break;
            default: color = 'var(--core-color)';
        }
        
        panelCategory.style.backgroundColor = color;
        panelCategory.style.color = '#000000'; // Texto negro en etiqueta
        
        // Mostrar conexiones relevantes
        panelConnections.innerHTML = '';
        if (nodeData.connections) {
            const connectionsTitle = document.createElement('div');
            connectionsTitle.textContent = 'Conectado con:';
            connectionsTitle.style.fontWeight = '600';
            connectionsTitle.style.marginBottom = '10px';
            connectionsTitle.style.color = 'var(--text-light)';
            panelConnections.appendChild(connectionsTitle);
            
            nodeData.connections.forEach(connection => {
                const connectionItem = document.createElement('div');
                connectionItem.textContent = connection;
                connectionItem.style.padding = '5px 10px';
                connectionItem.style.marginBottom = '5px';
                connectionItem.style.backgroundColor = 'rgba(255, 255, 255, 0.05)';
                connectionItem.style.borderRadius = '4px';
                connectionItem.style.fontSize = '0.85rem';
                panelConnections.appendChild(connectionItem);
            });
        }
        
        // Mostrar panel
        panel.classList.add('active');
        
        // Actualizar nodo seleccionado
        selectedNode = nodeData.id;
    }

    // Cerrar panel
    document.getElementById('closePanel').addEventListener('click', () => {
        document.getElementById('contentPanel').classList.remove('active');
        selectedNode = null;
    });

    // Inicializar canvas para conexiones
    function initCanvas() {
        canvas = document.getElementById('galaxy-canvas');
        ctx = canvas.getContext('2d');
        
        // Ajustar tamaño del canvas
        function resizeCanvas() {
            canvas.width = canvas.offsetWidth;
            canvas.height = canvas.offsetHeight;
            drawConnections();
        }
        
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();
        
        // Añadir eventos de zoom y arrastre al documento completo
        document.addEventListener('wheel', handleWheel);
        canvas.addEventListener('mousedown', handleMouseDown);
        document.addEventListener('mousemove', handleMouseMove);
        document.addEventListener('mouseup', handleMouseUp);
        
        // Agregar controles de zoom
        document.getElementById('zoomIn').addEventListener('click', () => adjustZoom(0.1));
        document.getElementById('zoomOut').addEventListener('click', () => adjustZoom(-0.1));
        document.getElementById('resetView').addEventListener('click', resetView);
    }

    // Ajustar zoom
    function adjustZoom(factor) {
        zoom = Math.max(0.3, Math.min(2, zoom + factor));
        applyTransform();
        drawConnections();
    }

    // Resetear vista
    function resetView() {
        zoom = 0.8;
        offsetX = 0;
        offsetY = 0;
        applyTransform();
        drawConnections();
    }

    // Aplicar transformación al contenedor
    function applyTransform() {
        const container = document.getElementById('mainContainer');
        container.style.transform = `translate(${offsetX}px, ${offsetY}px) scale(${zoom})`;
    }

    // Dibujar conexiones entre nodos
    function drawConnections() {
        // Limpiar canvas
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        
        // Dibujar conexiones desde el nodo central a todos los nodos temáticos
        const centralNode = document.querySelector('.central-node');
        if (!centralNode) return;
        
        const centerX = canvas.width / 2;
        const centerY = canvas.height / 2;
        
        // Conexión a campos temáticos
        const thematicNodes = document.querySelectorAll('.thematic-node');
        thematicNodes.forEach(node => {
            const rect = node.getBoundingClientRect();
            const canvasRect = canvas.getBoundingClientRect();
            
            const nodeX = rect.left + rect.width / 2 - canvasRect.left;
            const nodeY = rect.top + rect.height / 2 - canvasRect.top;
            
            drawConnectionLine(centerX, centerY, nodeX, nodeY, 'rgba(255, 179, 71, 0.4)');
        });
        
        // Conexión a intuiciones
        const intuitionNodes = document.querySelectorAll('.intuition-node');
        intuitionNodes.forEach(node => {
            const rect = node.getBoundingClientRect();
            const canvasRect = canvas.getBoundingClientRect();
            
            const nodeX = rect.left + rect.width / 2 - canvasRect.left;
            const nodeY = rect.top + rect.height / 2 - canvasRect.top;
            
            drawConnectionLine(centerX, centerY, nodeX, nodeY, 'rgba(185, 103, 255, 0.3)');
        });
        
        // Conexión a acciones
        const actionNodes = document.querySelectorAll('.action-node');
        actionNodes.forEach(node => {
            const rect = node.getBoundingClientRect();
            const canvasRect = canvas.getBoundingClientRect();
            
            const nodeX = rect.left + rect.width / 2 - canvasRect.left;
            const nodeY = rect.top + rect.height / 2 - canvasRect.top;
            
            drawConnectionLine(centerX, centerY, nodeX, nodeY, 'rgba(255, 94, 125, 0.3)');
        });
    }

    // Dibujar una línea de conexión
    function drawConnectionLine(x1, y1, x2, y2, color) {
        ctx.beginPath();
        ctx.moveTo(x1, y1);
        ctx.lineTo(x2, y2);
        ctx.strokeStyle = color;
        ctx.lineWidth = 2;
        ctx.stroke();
        
        // Añadir efecto de brillo
        ctx.beginPath();
        ctx.moveTo(x1, y1);
        ctx.lineTo(x2, y2);
        ctx.strokeStyle = color.replace('0.3', '0.1').replace('0.4', '0.15');
        ctx.lineWidth = 6;
        ctx.stroke();
    }

    // Manejar zoom con rueda del ratón
    function handleWheel(e) {
        e.preventDefault();
        
        const zoomFactor = 0.1;
        const oldZoom = zoom;
        
        if (e.deltaY < 0) {
            // Zoom in
            zoom = Math.min(zoom + zoomFactor, 2);
        } else {
            // Zoom out
            zoom = Math.max(zoom - zoomFactor, 0.3);
        }
        
        applyTransform();
        drawConnections();
    }

    // Manejar arrastre
    function handleMouseDown(e) {
        // Solo arrastrar si se hace clic en el canvas o en un área vacía
        if (e.target === canvas || e.target.id === 'galaxy' || e.target.classList.contains('orbit')) {
            isDragging = true;
            dragStartX = e.clientX;
            dragStartY = e.clientY;
            initialOffsetX = offsetX;
            initialOffsetY = offsetY;
            
            document.body.style.cursor = 'grabbing';
        }
    }

    function handleMouseMove(e) {
        if (!isDragging) return;
        
        offsetX = initialOffsetX + (e.clientX - dragStartX);
        offsetY = initialOffsetY + (e.clientY - dragStartY);
        
        // Limitar desplazamiento
        const maxOffset = 800; // Más desplazamiento permitido
        offsetX = Math.max(Math.min(offsetX, maxOffset), -maxOffset);
        offsetY = Math.max(Math.min(offsetY, maxOffset), -maxOffset);
        
        applyTransform();
        drawConnections();
    }

    function handleMouseUp() {
        isDragging = false;
        document.body.style.cursor = 'default';
    }

    // Inicializar la página
    document.addEventListener('DOMContentLoaded', () => {
        initStars();
        createOrbitalNodes();
        initCanvas();
        applyTransform(); // Aplicar transformación inicial
        
        // Mostrar contenido del nodo central al cargar
        setTimeout(() => {
            showNodeContent(nodesData.central);
        }, 1000);
        
        // Cerrar panel al hacer clic fuera
        document.addEventListener('click', (e) => {
            const panel = document.getElementById('contentPanel');
            const centralNode = document.getElementById('centralNode');
            const isNode = e.target.closest('.node') || e.target === centralNode || e.target.closest('.central-node');
            
            if (!isNode && !panel.contains(e.target) && panel.classList.contains('active')) {
                panel.classList.remove('active');
                selectedNode = null;
            }
        });
        
        // Aplicar transformación inicial
        applyTransform();
    });
</script>