
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