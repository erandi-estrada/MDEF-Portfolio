<link rel="stylesheet" href="../stylesheets/mapa-galaxia.css">

<style>
/* ===== FORZAR MENÚ VISIBLE Y CENTRADO ===== */
.menu-container {
    display: flex !important;
    justify-content: center !important;
    align-items: center !important;
    width: 100% !important;
    margin: 0 !important;
    padding: 1rem 0 !important;
    background-color: #fefaf0 !important;
    border-bottom: 1px solid #e8dfd0 !important;
    position: relative !important;
}

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
    margin: 0;
    padding: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
    position: relative;
}

/* MENÚ - IDÉNTICO A OTRAS PÁGINAS */
.menu-container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    background-color: #fefaf0;
    border-bottom: 1px solid #e8dfd0;
    position: relative;
    padding: 1rem 0;
    margin: 0;
}

.custom-header-menu {
    display: flex;
    align-items: center;
    gap: 3rem;
    margin: 0;
    padding: 0;
}

.custom-header-menu a {
    color: #2d3748;
    text-decoration: none;
    font-weight: 600;
    font-size: 1rem;
    padding: 0.5rem 0;
    border-bottom: 2px solid transparent;
    transition: all 0.3s ease;
}

.custom-header-menu a:hover {
    color: #1976d2;
    border-bottom-color: #1976d2;
}

/* Contenedor principal - AJUSTADO */
.main-container {
    flex: 1;
    position: relative;
    overflow: hidden;
    width: 100%;
    height: calc(100vh - 70px); /* Ajusta según el tamaño del menú */
}

/* Contenedor principal - DEBAJO DEL MENÚ */
.main-container {
    flex: 1;
    position: relative;
    overflow: hidden;
    width: 100%;
    height: calc(100vh - 60px); /* Restar altura del menú */
    margin-top: 20px; /* Espacio para el menú fijo */
}

/* Fondo cósmico con estrellas - SOLO EN EL ÁREA DEL MAPA */
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
    background-color: white;
    border-radius: 50%;
    opacity: 0;
    animation: twinkle 5s infinite;
}

@keyframes twinkle {
    0%, 100% { opacity: 0.1; }
    50% { opacity: 0.8; }
}

/* Viewport para navegación - DENTRO DEL CONTENEDOR PRINCIPAL */
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

/* Galaxia */
#galaxy {
    position: absolute;
    width: 3000px;
    height: 3000px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0.4);
    transform-origin: center center;
    transition: transform 0.1s ease;
    will-change: transform;
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

/* Nodo central - ENORMEMENTE GRANDE */
.central-node {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 400px;
    height: 400px;
    border-radius: 50%;
    background: radial-gradient(circle, var(--core-color) 0%, rgba(0, 198, 255, 0.4) 70%, transparent 100%);
    box-shadow: 0 0 100px rgba(0, 198, 255, 0.8);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    z-index: 10;
    transition: all 0.3s ease;
}

.central-node:hover {
    transform: translate(-50%, -50%) scale(1.1);
    box-shadow: 0 0 150px rgba(0, 198, 255, 1);
}

.central-node-content {
    text-align: center;
    padding: 30px;
    width: 100%;
}

.central-node-title {
    font-weight: 800;
    font-size: 2.5rem;
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 15px;
    color: #000000;
    text-shadow: 0 2px 4px rgba(255, 255, 255, 0.8);
    line-height: 1.2;
}

/* Contenedor de nodos orbitales */
.orbit {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 50%;
    border: 1px solid rgba(255, 255, 255, 0.1);
}

/* Nodos - ENORMES */
.node {
    position: absolute;
    width: 220px;
    height: 220px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s ease;
    z-index: 5;
    overflow: hidden;
}

.node-title {
    font-weight: 700;
    font-size: 1.2rem;
    text-align: center;
    text-transform: uppercase;
    letter-spacing: 1px;
    padding: 15px;
    color: #000000;
    text-shadow: 0 2px 3px rgba(255, 255, 255, 0.7);
    line-height: 1.3;
    width: 100%;
    word-wrap: break-word;
    overflow-wrap: break-word;
}

/* Colores de nodos según categoría */
.intuition-node {
    background: radial-gradient(circle, var(--intuitions-color) 0%, rgba(185, 103, 255, 0.8) 70%, transparent 100%);
    box-shadow: 0 0 50px rgba(185, 103, 255, 0.9);
}

.question-node {
    background: radial-gradient(circle, var(--questions-color) 0%, rgba(255, 255, 255, 0.8) 70%, transparent 100%);
    box-shadow: 0 0 50px rgba(255, 255, 255, 0.9);
}

.thematic-node {
    background: radial-gradient(circle, var(--thematic-color) 0%, rgba(255, 179, 71, 0.8) 70%, transparent 100%);
    box-shadow: 0 0 50px rgba(255, 179, 71, 0.9);
}

.action-node {
    background: radial-gradient(circle, var(--actions-color) 0%, rgba(255, 94, 125, 0.8) 70%, transparent 100%);
    box-shadow: 0 0 50px rgba(255, 94, 125, 0.9);
}

.bee-node {
    background: radial-gradient(circle, var(--bee-color) 0%, rgba(0, 216, 167, 0.8) 70%, transparent 100%);
    box-shadow: 0 0 50px rgba(0, 216, 167, 0.9);
}

.fieldwork-node {
    background: radial-gradient(circle, var(--fieldwork-color) 0%, rgba(255, 138, 101, 0.8) 70%, transparent 100%);
    box-shadow: 0 0 50px rgba(255, 138, 101, 0.9);
}

/* Efectos hover en nodos */
.node:hover {
    transform: scale(1.15);
    z-index: 20;
    box-shadow: 0 0 80px rgba(255, 255, 255, 0.6);
}

/* Panel de contenido */
.content-panel {
    position: fixed;
    top: 100px; /* Debajo del menú */
    right: 20px;
    width: 400px;
    background: rgba(10, 14, 23, 0.95);
    backdrop-filter: blur(15px);
    border-radius: 15px;
    padding: 25px;
    box-shadow: 0 15px 40px rgba(0, 0, 0, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.1);
    z-index: 1000;
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
    font-size: 1.8rem;
    font-weight: 700;
    margin-bottom: 15px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: #ffffff;
    line-height: 1.3;
}

.panel-category {
    display: inline-block;
    font-size: 0.9rem;
    padding: 6px 15px;
    border-radius: 20px;
    margin-bottom: 20px;
    font-weight: 700;
    color: #000000;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.panel-text {
    font-size: 1.05rem;
    line-height: 1.7;
    color: var(--text-muted);
    margin-bottom: 25px;
}

.panel-close {
    position: absolute;
    top: 15px;
    right: 15px;
    background: rgba(255, 255, 255, 0.1);
    border: none;
    color: var(--text-muted);
    font-size: 1.5rem;
    cursor: pointer;
    transition: all 0.3s;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.panel-close:hover {
    background: rgba(255, 255, 255, 0.2);
    color: var(--text-light);
    transform: rotate(90deg);
}

/* Instrucciones mínimas - ABAJO DEL TODO */
.instructions {
    position: fixed;
    bottom: 20px;
    right: 20px;
    text-align: right;
    font-size: 0.85rem;
    color: rgba(255, 255, 255, 0.5);
    z-index: 1000;
    background: rgba(10, 14, 23, 0.3);
    padding: 10px 15px;
    border-radius: 8px;
    border: 1px solid rgba(255, 255, 255, 0.05);
    max-width: 250px;
    backdrop-filter: blur(5px);
}

/* Responsive */
@media (max-width: 1200px) {
    #galaxy {
        width: 2500px;
        height: 2500px;
    }
    
    .central-node {
        width: 350px;
        height: 350px;
    }
    
    .node {
        width: 200px;
        height: 200px;
    }
    
    .content-panel {
        width: 350px;
    }
    
    .menu-container {
        padding: 15px 20px;
    }
}

@media (max-width: 900px) {
    #galaxy {
        width: 2000px;
        height: 2000px;
    }
    
    .central-node {
        width: 300px;
        height: 300px;
    }
    
    .node {
        width: 180px;
        height: 180px;
    }
    
    .content-panel {
        width: calc(100% - 40px);
        max-width: 400px;
        top: 90px;
    }
    
    .instructions {
        display: none;
    }
    
    .custom-header-menu {
        gap: 20px;
    }
    
    .custom-header-menu a {
        font-size: 0.9rem;
    }
}

@media (max-width: 600px) {
    .main-container {
        height: calc(100vh - 60px);
    }
    
    .menu-container {
        padding: 12px 15px;
    }
    
    .custom-header-menu {
        gap: 15px;
        justify-content: center;
    }
    
    .custom-header-menu a {
        font-size: 0.85rem;
    }
    
    .content-panel {
        left: 10px;
        right: 10px;
        max-width: none;
        top: 80px;
    }
    
    .central-node {
        width: 250px;
        height: 250px;
    }
    
    .node {
        width: 150px;
        height: 150px;
    }
    
    .central-node-title {
        font-size: 2rem;
    }
    
    .node-title {
        font-size: 1rem;
        padding: 10px;
    }
}
</style>

<!-- MENÚ (ARRIBA) -->
<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<!-- CONTENEDOR PRINCIPAL (CON EL MAPA) -->
<div class="main-container">
    <div id="stars"></div>
    
    <!-- Viewport para navegación -->
    <div class="viewport" id="viewport">
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
</div>

<!-- Panel de contenido -->
<div class="content-panel" id="contentPanel">
    <button class="panel-close" id="closePanel">×</button>
    <div class="panel-category" id="panelCategory">Core Concept</div>
    <h2 class="panel-title" id="panelTitle">The Invisible City</h2>
    <p class="panel-text" id="panelText">How beauty hides violence, and how other species experience the city through sensory worlds we ignore. A framework connecting hostile design, multispecies inequalities, and environmental perception.</p>
</div>

<!-- Instrucciones mínimas -->
<div class="instructions">
    Haz clic en cualquier nodo para ver detalles<br>
    Usa la rueda del ratón para hacer zoom<br>
    Arrastra para mover el mapa
</div>

<script>
    // Datos para todos los nodos
    const nodesData = {
        central: {
            id: "central",
            title: "The Invisible City",
            text: "How beauty hides violence, and how other species experience the city through sensory worlds we ignore. A framework connecting hostile design, multispecies inequalities, and environmental perception.",
            category: "Core Concept",
            color: "var(--core-color)",
            connections: ["intuitions", "thematic", "actions", "questions", "bee", "fieldwork"]
        },
        
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
        
        thematic: [
            {id: "thematic1", title: "Urban Aesthetics", text: "Beauty as control; order as exclusion.", category: "Thematic Fields"},
            {id: "thematic2", title: "Hostile Design", text: "Architecture that denies presence, rest, or habitation.", category: "Thematic Fields"},
            {id: "thematic3", title: "Multispecies Justice", text: "Rights, coexistence, and vulnerability beyond the human.", category: "Thematic Fields"},
            {id: "thematic4", title: "Embodied Research", text: "Using the body to reveal invisible systems.", category: "Thematic Fields"},
            {id: "thematic5", title: "Sensory Translation", text: "Rewriting environmental data into human-perceivable forms.", category: "Thematic Fields"},
            {id: "thematic6", title: "Environmental Empathy", text: "Understanding pollution through the sensory worlds of bees.", category: "Thematic Fields"}
        ],
        
        actions: [
            {id: "action1", title: "Sitting on Hostile Architecture", text: "Revealing micro-violence through your body.", category: "Actions"},
            {id: "action2", title: "Returning Life Interventions", text: "Reintroducing plants where nature has been erased.", category: "Actions"},
            {id: "action3", title: "Wearing Hostility", text: "Embodied critique of anti-bird / anti-homeless design.", category: "Actions"},
            {id: "action4", title: "Sensory Experiments", text: "Building tools that translate pollution into sensory experience.", category: "Actions"}
        ],
        
        bee: [
            {id: "bee1", title: "Pollution Translation", text: "How environmental toxins distort bee perception.", category: "Bee Project"},
            {id: "bee2", title: "Urban Threat Mapping", text: "Light, chemicals, noise, temperature stress.", category: "Bee Project"},
            {id: "bee3", title: "Multispecies Perception Interface", text: "Translating bee sensory vulnerability into human experience.", category: "Bee Project"},
            {id: "bee4", title: "Environmental Data Collection", text: "Using tools to understand urban toxicity from the perspective of bees (not human comfort).", category: "Bee Project"},
            {id: "bee5", title: "Ecological Importance", text: "Bees as pollinators, ecosystem stabilizers, and indicators of environmental health.", category: "Bee Project"},
            {id: "bee6", title: "Species-Level Vulnerability", text: "How pollution destabilizes bee navigation, memory, hive health.", category: "Bee Project"}
        ],
        
        fieldwork: [
            {id: "fieldwork1", title: "Hostile Aesthetics Mapping", text: "Photos + notes of spikes, anti-homeless architecture, barriers.", category: "Urban Fieldwork"},
            {id: "fieldwork2", title: "City-as-Performance", text: "Barcelona as spectacle; bodies curated for tourism.", category: "Urban Fieldwork"},
            {id: "fieldwork3", title: "Life Expelled from the City", text: "Plants removed, pigeons denied resting spots.", category: "Urban Fieldwork"},
            {id: "fieldwork4", title: "Life Returning", text: "Plant interventions, pigeons reclaiming benches.", category: "Urban Fieldwork"}
        ]
    };

    // Variables globales
    let canvas, ctx;
    let scale = 0.4;
    let offsetX = 0, offsetY = 0;
    let isDragging = false;
    let lastX = 0, lastY = 0;
    let galaxy = document.getElementById('galaxy');
    let viewport = document.getElementById('viewport');

    // Inicializar estrellas
    function initStars() {
        const starsContainer = document.getElementById('stars');
        starsContainer.innerHTML = '';
        
        for (let i = 0; i < 300; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            
            const size = Math.random() * 4 + 1;
            star.style.width = `${size}px`;
            star.style.height = `${size}px`;
            star.style.left = `${Math.random() * 100}%`;
            star.style.top = `${Math.random() * 100}%`;
            star.style.animationDelay = `${Math.random() * 5}s`;
            
            starsContainer.appendChild(star);
        }
    }

    // Crear nodos orbitales
    function createOrbitalNodes() {
        const orbits = [
            {radius: 600, nodes: nodesData.intuitions, className: 'intuition-node'},
            {radius: 900, nodes: nodesData.questions, className: 'question-node'},
            {radius: 1200, nodes: nodesData.thematic, className: 'thematic-node'},
            {radius: 1500, nodes: nodesData.actions, className: 'action-node'},
            {radius: 1800, nodes: nodesData.bee, className: 'bee-node'},
            {radius: 2100, nodes: nodesData.fieldwork, className: 'fieldwork-node'}
        ];
        
        orbits.forEach((orbit, orbitIndex) => {
            const orbitElement = document.createElement('div');
            orbitElement.classList.add('orbit');
            orbitElement.style.width = `${orbit.radius * 2}px`;
            orbitElement.style.height = `${orbit.radius * 2}px`;
            galaxy.appendChild(orbitElement);
            
            orbit.nodes.forEach((nodeData, nodeIndex) => {
                const node = document.createElement('div');
                node.classList.add('node', orbit.className);
                node.id = nodeData.id;
                node.dataset.title = nodeData.title;
                node.dataset.text = nodeData.text;
                node.dataset.category = nodeData.category;
                
                const angle = (nodeIndex / orbit.nodes.length) * 2 * Math.PI;
                const x = orbit.radius * Math.cos(angle);
                const y = orbit.radius * Math.sin(angle);
                
                node.style.left = `calc(50% + ${x}px)`;
                node.style.top = `calc(50% + ${y}px)`;
                node.style.transform = 'translate(-50%, -50%)';
                
                const titleElement = document.createElement('div');
                titleElement.classList.add('node-title');
                titleElement.textContent = nodeData.title;
                node.appendChild(titleElement);
                
                node.addEventListener('click', (e) => {
                    e.stopPropagation();
                    showNodeContent(nodeData);
                });
                
                galaxy.appendChild(node);
            });
        });
        
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
        
        panelTitle.textContent = nodeData.title;
        panelText.textContent = nodeData.text;
        panelCategory.textContent = nodeData.category;
        
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
        panelCategory.style.color = '#000000';
        
        panel.classList.add('active');
    }

    // Cerrar panel
    document.getElementById('closePanel').addEventListener('click', () => {
        document.getElementById('contentPanel').classList.remove('active');
    });

    // Inicializar canvas para conexiones
    function initCanvas() {
        canvas = document.getElementById('galaxy-canvas');
        ctx = canvas.getContext('2d');
        
        function resizeCanvas() {
            canvas.width = galaxy.offsetWidth;
            canvas.height = galaxy.offsetHeight;
            drawConnections();
        }
        
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();
    }

    // Dibujar conexiones
    function drawConnections() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        
        const centerX = canvas.width / 2;
        const centerY = canvas.height / 2;
        
        const allNodes = document.querySelectorAll('.node:not(.central-node)');
        allNodes.forEach(node => {
            const rect = node.getBoundingClientRect();
            const galaxyRect = galaxy.getBoundingClientRect();
            
            const nodeX = (rect.left + rect.width/2 - galaxyRect.left) / scale;
            const nodeY = (rect.top + rect.height/2 - galaxyRect.top) / scale;
            
            let color = 'rgba(255, 255, 255, 0.2)';
            if (node.classList.contains('thematic-node')) color = 'rgba(255, 179, 71, 0.3)';
            else if (node.classList.contains('intuition-node')) color = 'rgba(185, 103, 255, 0.2)';
            else if (node.classList.contains('question-node')) color = 'rgba(255, 255, 255, 0.25)';
            else if (node.classList.contains('action-node')) color = 'rgba(255, 94, 125, 0.2)';
            else if (node.classList.contains('bee-node')) color = 'rgba(0, 216, 167, 0.2)';
            else if (node.classList.contains('fieldwork-node')) color = 'rgba(255, 138, 101, 0.2)';
            
            drawConnectionLine(centerX, centerY, nodeX, nodeY, color);
        });
    }

    function drawConnectionLine(x1, y1, x2, y2, color) {
        ctx.beginPath();
        ctx.moveTo(x1, y1);
        ctx.lineTo(x2, y2);
        ctx.strokeStyle = color;
        ctx.lineWidth = 2;
        ctx.stroke();
    }

    // Actualizar transformación de la galaxia
    function updateTransform() {
        galaxy.style.transform = `translate(calc(-50% + ${offsetX}px), calc(-50% + ${offsetY}px)) scale(${scale})`;
        drawConnections();
    }

    // Manejar zoom
    function handleWheel(e) {
        e.preventDefault();
        
        const zoomFactor = 0.1;
        const oldScale = scale;
        
        if (e.deltaY < 0) {
            scale = Math.min(scale + zoomFactor, 1.5);
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

    // Manejar arrastre
    function handleMouseDown(e) {
        if (e.target === viewport || e.target.classList.contains('orbit')) {
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

    // Resetear vista al centro
    function resetView() {
        scale = 0.4;
        offsetX = 0;
        offsetY = 0;
        updateTransform();
    }

    // Inicializar la página
    document.addEventListener('DOMContentLoaded', () => {
        initStars();
        createOrbitalNodes();
        initCanvas();
        updateTransform();
        
        setTimeout(() => {
            showNodeContent(nodesData.central);
        }, 1000);
        
        viewport.addEventListener('wheel', handleWheel);
        viewport.addEventListener('mousedown', handleMouseDown);
        document.addEventListener('mousemove', handleMouseMove);
        document.addEventListener('mouseup', handleMouseUp);
        
        viewport.addEventListener('dblclick', resetView);
        
        document.addEventListener('click', (e) => {
            const panel = document.getElementById('contentPanel');
            const isNode = e.target.closest('.node') || e.target.closest('.central-node');
            
            if (!isNode && !panel.contains(e.target) && panel.classList.contains('active')) {
                panel.classList.remove('active');
            }
        });
        
        document.getElementById('closePanel').addEventListener('mousedown', (e) => e.stopPropagation());
    });
</script>