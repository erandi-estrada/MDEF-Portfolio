<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>




<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Constellation Map – The Invisible City</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            /* Paleta de colores - inspirada en tu visión */
            --black-phosphor: #050509;
            --data-blue: #1C64F2;
            --species-violet: #8A3FFC;
            --hostility-amber: #FF9F1C;
            --bee-yellow: #FFDD00;
            --ecosystem-green: #00C49A;
            --toxicity-red: #E11D48;
            --fog-white: #F2F2F2;
            --node-glow: rgba(28, 100, 242, 0.4);
            
/* Gradientes */
            --gradient-blue-yellow: linear-gradient(135deg, var(--data-blue) 0%, var(--bee-yellow) 100%);
            --gradient-violet-red: linear-gradient(135deg, var(--species-violet) 0%, var(--toxicity-red) 100%);
            --gradient-green-white: linear-gradient(135deg, var(--ecosystem-green) 0%, var(--fog-white) 100%);
            
            /* Espaciado y tamaños */
            --orbit-1: 180px;
            --orbit-2: 320px;
            --orbit-3: 460px;
            --orbit-4: 600px;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
body {
            background-color: var(--black-phosphor);
            color: var(--fog-white);
            font-family: 'Space Grotesk', sans-serif;
            overflow-x: hidden;
            min-height: 100vh;
            position: relative;
        }
        
        /* Estrellas de fondo */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(1px 1px at 20px 30px, rgba(242, 242, 242, 0.3) 1px, transparent 0),
                radial-gradient(1px 1px at 40px 70px, rgba(242, 242, 242, 0.3) 1px, transparent 0),
                radial-gradient(1px 1px at 60px 20px, rgba(242, 242, 242, 0.3) 1px, transparent 0),
                radial-gradient(1.5px 1.5px at 80px 50px, rgba(255, 221, 0, 0.4) 1px, transparent 0),
                radial-gradient(1.5px 1.5px at 100px 80px, rgba(138, 63, 252, 0.4) 1px, transparent 0),
                radial-gradient(2px 2px at 120px 30px, rgba(28, 100, 242, 0.4) 1px, transparent 0);
            background-size: 200px 200px;
            z-index: -1;
            animation: twinkle 8s infinite alternate;
        }
        
        @keyframes twinkle {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }
        
        /* MENU - Tu código exacto con estilos mejorados */
        .menu-container {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            padding: 1rem 2rem;
            background: rgba(5, 5, 9, 0.9);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(242, 242, 242, 0.1);
        }
        
        .custom-header-menu {
            display: flex;
            justify-content: flex-end;
            gap: 2.5rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .custom-header-menu a {
            color: var(--fog-white);
            text-decoration: none;
            font-weight: 500;
            font-size: 1rem;
            padding: 0.5rem 0;
            position: relative;
            transition: color 0.3s ease;
        }
        
        .custom-header-menu a:hover {
            color: var(--data-blue);
        }
        
        .custom-header-menu a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gradient-blue-yellow);
            transition: width 0.3s ease;
        }
        
        .custom-header-menu a:hover::after {
            width: 100%;
        }
        
        /* Contenedor principal del mapa */
        .constellation-map {
            padding-top: 80px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
        }
        
        /* Título principal */
        .main-title {
            text-align: center;
            padding: 2rem 1rem 4rem;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .main-title h1 {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: var(--gradient-blue-yellow);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            line-height: 1.1;
        }
        
        .main-title p {
            font-size: 1.2rem;
            font-weight: 300;
            opacity: 0.8;
            line-height: 1.6;
        }
        
        /* Contenedor de la constelación */
        .constellation-container {
            position: relative;
            width: 100%;
            max-width: 1300px;
            height: 1300px;
            margin: 0 auto;
        }
        
        /* Órbitas (círculos concéntricos) */
        .orbit {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            border: 1px solid rgba(242, 242, 242, 0.1);
        }
        
        .orbit-1 { width: var(--orbit-1); height: var(--orbit-1); }
        .orbit-2 { width: var(--orbit-2); height: var(--orbit-2); }
        .orbit-3 { width: var(--orbit-3); height: var(--orbit-3); }
        .orbit-4 { width: var(--orbit-4); height: var(--orbit-4); }
        
        /* NÚCLEO CENTRAL */
        .central-node {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 160px;
            height: 160px;
            border-radius: 50%;
            background: var(--gradient-blue-yellow);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 10;
            box-shadow: 
                0 0 60px var(--node-glow),
                inset 0 0 20px rgba(255, 255, 255, 0.5);
            animation: pulse 4s infinite alternate;
            transition: all 0.4s ease;
        }
        
        .central-node:hover {
            transform: translate(-50%, -50%) scale(1.1);
            box-shadow: 
                0 0 80px var(--node-glow),
                inset 0 0 30px rgba(255, 255, 255, 0.7);
        }
        
        .central-node-content {
            text-align: center;
            padding: 1.5rem;
            color: var(--black-phosphor);
            font-weight: 700;
        }
        
        .central-node h2 {
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
        }
        
        .central-node p {
            font-size: 0.9rem;
            font-weight: 500;
        }
        
        @keyframes pulse {
            0% { box-shadow: 0 0 60px var(--node-glow); }
            100% { box-shadow: 0 0 90px var(--node-glow); }
        }
        
        /* NODOS ORBITALES */
        .node {
            position: absolute;
            width: 120px;
            height: 120px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
            padding: 1rem;
            font-weight: 600;
            z-index: 5;
        }
        
        .node:hover {
            transform: scale(1.15);
            z-index: 20;
        }
        
        .node-content {
            position: relative;
            z-index: 2;
        }
        
        /* Colores de nodos según categoría */
        .node-urban { background-color: var(--species-violet); }
        .node-hostile { background-color: var(--hostility-amber); color: var(--black-phosphor); }
        .node-species { background-color: var(--bee-yellow); color: var(--black-phosphor); }
        .node-research { background-color: var(--ecosystem-green); }
        .node-question { background-color: transparent; border: 2px solid var(--fog-white); width: 80px; height: 80px; }
        .node-action { background-color: var(--toxicity-red); }
        .node-project { background: var(--gradient-violet-red); }
        
        /* Líneas de conexión */
        .connection {
            position: absolute;
            height: 2px;
            background: var(--gradient-green-white);
            transform-origin: 0 0;
            z-index: 1;
            opacity: 0.3;
            transition: opacity 0.3s ease;
        }
        
        .node:hover ~ .connection,
        .connection:hover {
            opacity: 0.8;
        }
        
        /* Modal para contenido expandido */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(5, 5, 9, 0.9);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 10000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
            backdrop-filter: blur(5px);
        }
        
        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal-content {
            background: var(--black-phosphor);
            border-radius: 20px;
            padding: 2.5rem;
            max-width: 800px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
            border: 1px solid rgba(242, 242, 242, 0.1);
            box-shadow: 0 0 50px rgba(28, 100, 242, 0.3);
            position: relative;
        }
        
        .modal-close {
            position: absolute;
            top: 1rem;
            right: 1.5rem;
            background: none;
            border: none;
            color: var(--fog-white);
            font-size: 1.8rem;
            cursor: pointer;
            line-height: 1;
        }
        
        .modal-header {
            margin-bottom: 1.5rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid rgba(242, 242, 242, 0.1);
        }
        
        .modal-title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }
        
        .modal-subtitle {
            font-size: 1.1rem;
            opacity: 0.8;
            font-weight: 300;
        }
        
        .modal-body ul {
            list-style-type: none;
            margin-left: 0;
        }
        
        .modal-body li {
            padding: 0.5rem 0;
            position: relative;
            padding-left: 1.5rem;
        }
        
        .modal-body li::before {
            content: '✦';
            position: absolute;
            left: 0;
            color: var(--data-blue);
        }
        
        /* Leyenda de colores */
        .color-legend {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: rgba(5, 5, 9, 0.8);
            border: 1px solid rgba(242, 242, 242, 0.1);
            border-radius: 12px;
            padding: 1.2rem;
            z-index: 100;
            backdrop-filter: blur(10px);
            max-width: 220px;
        }
        
        .color-legend h3 {
            font-size: 1rem;
            margin-bottom: 0.8rem;
            color: var(--data-blue);
        }
        
        .legend-item {
            display: flex;
            align-items: center;
            margin-bottom: 0.6rem;
            font-size: 0.85rem;
        }
        
        .legend-color {
            width: 16px;
            height: 16px;
            border-radius: 50%;
            margin-right: 0.7rem;
        }
        
        /* Responsive */
        @media (max-width: 1100px) {
            .constellation-container {
                transform: scale(0.8);
                height: 1000px;
            }
            
            .main-title h1 {
                font-size: 2.5rem;
            }
        }
        
        @media (max-width: 768px) {
            .constellation-container {
                transform: scale(0.6);
                height: 800px;
            }
            
            .main-title {
                padding: 1rem 1rem 3rem;
            }
            
            .main-title h1 {
                font-size: 2rem;
            }
            
            .color-legend {
                display: none;
            }
            
            .custom-header-menu {
                justify-content: center;
                gap: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Tu menú exacto -->
    <div class="menu-container">
        <div class="custom-header-menu">
            <a href="../..">MDEF</a>
            <a href="../../projects/Portfolio">Projects</a>
            <a href="../../about/me">About me</a>
        </div>
    </div>
    
    <!-- Mapa de constelación -->
    <main class="constellation-map">
        <div class="main-title">
            <h1>🌌 MAPA CONSTELACIÓN — THE INVISIBLE CITY</h1>
            <p>Your universe conceptual as a navigable sky of ideas. Hover over nodes to reveal connections, click to explore in depth.</p>
        </div>
        
        <div class="constellation-container">
            <!-- Órbitas visuales -->
            <div class="orbit orbit-1"></div>
            <div class="orbit orbit-2"></div>
            <div class="orbit orbit-3"></div>
            <div class="orbit orbit-4"></div>
            
            <!-- NÚCLEO CENTRAL -->
            <div class="node central-node" data-modal="central">
                <div class="central-node-content">
                    <h2>THE INVISIBLE CITY</h2>
                    <p>Núcleo Central</p>
                </div>
            </div>
            
            <!-- PRIMERA ÓRBITA - 4 clusters -->
            <div class="node node-urban" style="top: 30%; left: 30%;" data-modal="urban">
                <div class="node-content">Urban Aesthetics</div>
            </div>
            
            <div class="node node-hostile" style="top: 30%; left: 70%;" data-modal="hostile">
                <div class="node-content">Hostile Design</div>
            </div>
            
            <div class="node node-species" style="top: 70%; left: 30%;" data-modal="species">
                <div class="node-content">Multispecies Justice</div>
            </div>
            
            <div class="node node-research" style="top: 70%; left: 70%;" data-modal="research">
                <div class="node-content">Embodied Research</div>
            </div>
            
            <!-- SEGUNDA ÓRBITA - Preguntas -->
            <div class="node node-question" style="top: 15%; left: 50%;" data-modal="question1">
                <div class="node-content">What lives are allowed?</div>
            </div>
            
            <div class="node node-question" style="top: 50%; left: 85%;" data-modal="question2">
                <div class="node-content">How does beauty justify exclusion?</div>
            </div>
            
            <div class="node node-question" style="top: 85%; left: 50%;" data-modal="question3">
                <div class="node-content">Can design generate empathy?</div>
            </div>
            
            <div class="node node-question" style="top: 50%; left: 15%;" data-modal="question4">
                <div class="node-content">What bodies can rest?</div>
            </div>
            
            <!-- TERCERA ÓRBITA - Acciones -->
            <div class="node node-action" style="top: 20%; left: 20%;" data-modal="action1">
                <div class="node-content">Sitting on hostile architecture</div>
            </div>
            
            <div class="node node-action" style="top: 20%; left: 80%;" data-modal="action2">
                <div class="node-content">Returning Life interventions</div>
            </div>
            
            <div class="node node-action" style="top: 80%; left: 20%;" data-modal="action3">
                <div class="node-content">Wearing Hostility (spike dress)</div>
            </div>
            
            <div class="node node-action" style="top: 80%; left: 80%;" data-modal="action4">
                <div class="node-content">Sensory translation</div>
            </div>
            
            <!-- CUARTA ÓRBITA - Proyectos -->
            <div class="node node-project" style="top: 10%; left: 10%;" data-modal="project1">
                <div class="node-content">Beauty That Excludes</div>
            </div>
            
            <div class="node node-project" style="top: 10%; left: 90%;" data-modal="project2">
                <div class="node-content">Sensory Multispecies Translation</div>
            </div>
            
            <!-- Líneas de conexión (se generan dinámicamente con JS) -->
            <div class="connections-container" id="connections"></div>
        </div>
        
        <!-- Leyenda de colores -->
        <div class="color-legend">
            <h3>COLOR LEGEND</h3>
            <div class="legend-item">
                <div class="legend-color" style="background: var(--data-blue);"></div>
                <span>Core Concept</span>
            </div>
            <div class="legend-item">
                <div class="legend-color" style="background: var(--species-violet);"></div>
                <span>Urban Aesthetics</span>
            </div>
            <div class="legend-item">
                <div class="legend-color" style="background: var(--hostility-amber);"></div>
                <span>Hostile Design</span>
            </div>
            <div class="legend-item">
                <div class="legend-color" style="background: var(--bee-yellow);"></div>
                <span>Multispecies Justice</span>
            </div>
            <div class="legend-item">
                <div class="legend-color" style="background: var(--ecosystem-green);"></div>
                <span>Embodied Research</span>
            </div>
            <div class="legend-item">
                <div class="legend-color" style="background: var(--toxicity-red);"></div>
                <span>Actions as Knowledge</span>
            </div>
        </div>
    </main>
    
    <!-- Modal para contenido detallado -->
    <div class="modal-overlay" id="modalOverlay">
        <div class="modal-content">
            <button class="modal-close" id="modalClose">×</button>
            <div class="modal-header">
                <h2 class="modal-title" id="modalTitle">Node Title</h2>
                <p class="modal-subtitle" id="modalSubtitle">Node Subtitle</p>
            </div>
            <div class="modal-body" id="modalBody">
                <!-- Content will be inserted here by JavaScript -->
            </div>
        </div>
    </div>
    
    <script>
        // Datos para cada nodo del mapa
        const nodeData = {
            central: {
                title: "🌌 THE INVISIBLE CITY",
                subtitle: "The core intuition that powers all your work",
                content: `
                    <blockquote style="border-left: 3px solid var(--data-blue); padding-left: 1rem; margin: 1.5rem 0; font-style: italic;">
                        "The city looks beautiful, but its beauty hides systematic violence against both humans and non-human life."
                    </blockquote>
                    <p>This central node is large, luminous and contains three sub-intuitions that expand on hover:</p>
                    <ul>
                        <li><strong>Beauty as control</strong> - How aesthetic standards become tools of power</li>
                        <li><strong>Violence as absence</strong> - The violence of what is systematically removed or made invisible</li>
                        <li><strong>Life expelled from the urban image</strong> - The exclusion of non-curated life from the city's self-representation</li>
                    </ul>
                    <p>This node connects to all other elements in the constellation, serving as the gravitational center of your conceptual universe.</p>
                `
            },
            urban: {
                title: "🟣 Urban Aesthetics",
                subtitle: "Beauty as ideology, cleanliness as political tool",
                content: `
                    <p><strong>Cluster of concepts orbiting the central intuition:</strong></p>
                    <ul>
                        <li>Beauty as ideology</li>
                        <li>Cleanliness as political tool</li>
                        <li>City as spectacle</li>
                        <li>Nature as decoration</li>
                        <li>Controlled public space</li>
                        <li>Aesthetic erasure (graffiti removal)</li>
                        <li>Order vs Life</li>
                    </ul>
                    <p>This cluster examines how aesthetic standards in urban design serve to normalize exclusion and control, creating cities that privilege visual order over lived experience.</p>
                `
            },
            hostile: {
                title: "🔵 Hostile Design / Urban Violence",
                subtitle: "Architecture that excludes and controls through discomfort",
                content: `
                    <p><strong>Physical manifestations of invisible violence:</strong></p>
                    <ul>
                        <li>Anti-homeless architecture</li>
                        <li>Anti-pigeon spikes</li>
                        <li>Spacing barriers</li>
                        <li>Seating deterrents</li>
                        <li>Smooth surfaces that deny rest</li>
                        <li>Safety disguised as exclusion</li>
                        <li>Violence normalized through design</li>
                    </ul>
                    <p>Hostile design makes systemic exclusion tangible and physical. These interventions reveal how urban spaces are engineered to control which bodies can exist, rest, or thrive in the city.</p>
                `
            },
            species: {
                title: "🟢 Multispecies Justice",
                subtitle: "Questioning the urban hierarchy of life",
                content: `
                    <p><strong>Expanding the right to the city beyond the human:</strong></p>
                    <ul>
                        <li>Urban species hierarchy</li>
                        <li>Non-human citizenship</li>
                        <li>Pigeons as expelled residents</li>
                        <li>Plant life removed as "dirt"</li>
                        <li>Pollution impacting insects + birds</li>
                        <li>Who has the right to the city?</li>
                        <li>Urban ecosystems as political bodies</li>
                    </ul>
                    <p>This framework challenges the anthropocentric assumptions of urban planning, asking how cities might be redesigned to accommodate and respect multispecies communities.</p>
                `
            },
            research: {
                title: "🟠 Embodied & Situated Research",
                subtitle: "Using the body as method to reveal invisible structures",
                content: `
                    <p><strong>Methodologies for sensing the invisible city:</strong></p>
                    <ul>
                        <li>Walking as method</li>
                        <li>First-person ethnography</li>
                        <li>Your body as sensor</li>
                        <li>Using presence to reveal absence</li>
                        <li>Being ignored / being seen</li>
                        <li>Friction as data</li>
                        <li>Performing the invisible</li>
                    </ul>
                    <p>These approaches center embodied experience as a form of knowledge production, using the researcher's own physical presence to make visible the exclusionary logics embedded in urban space.</p>
                `
            },
            question1: {
                title: "❓ Motor Question",
                subtitle: "What lives are allowed to exist in the city?",
                content: `
                    <p>This question connects directly to:</p>
                    <ul>
                        <li><strong>Multispecies Justice</strong> - Which species are welcomed vs. excluded?</li>
                        <li><strong>Urban Aesthetics</strong> - How do beauty standards determine what life forms are "appropriate"?</li>
                        <li><strong>Hostile Design</strong> - What physical barriers prevent certain lives from thriving?</li>
                    </ul>
                    <p>It serves as a guiding inquiry for investigating the boundaries of urban inclusion and the criteria used to determine which forms of life belong in the "proper" city.</p>
                `
            },
            action1: {
                title: "🌑 Action: Sitting on hostile architecture",
                subtitle: "Revealing normalized micro-violence through embodied practice",
                content: `
                    <p><strong>Key learnings from this action:</strong></p>
                    <ul>
                        <li>Human discomfort exposes architectural hostility</li>
                        <li>The body becomes a sensor for urban violence</li>
                        <li>What feels "normal" when observed becomes painful when experienced</li>
                        <li>Public space is designed for movement, not rest</li>
                    </ul>
                    <p>By physically occupying hostile designs meant to deter certain bodies, this action makes visible the normalized violence of urban furniture and creates a moment of cognitive dissonance for observers.</p>
                `
            },
            project1: {
                title: "⭐ Constellation A — Beauty That Excludes",
                subtitle: "How aesthetic standards create invisible boundaries",
                content: `
                    <p><strong>This project constellation connects most strongly with:</strong></p>
                    <ul>
                        <li>Urban Aesthetics (beauty as control)</li>
                        <li>Hostile Design (physical exclusion)</li>
                        <li>Embodied Research (experiencing exclusion firsthand)</li>
                    </ul>
                    <p><strong>Core thesis:</strong> The city's beauty is not neutral but actively produces exclusion. By making beautiful spaces that systematically exclude certain lives, urban design naturalizes violence through aesthetic pleasure.</p>
                    <p>This project traces how aesthetic standards in urban planning and design create invisible boundaries that determine who and what belongs in the city.</p>
                `
            },
            project2: {
                title: "⭐ Constellation B — Sensory Multispecies Translation",
                subtitle: "Translating urban experience across species boundaries",
                content: `
                    <p><strong>This project constellation connects most strongly with:</strong></p>
                    <ul>
                        <li>Multispecies Justice (expanding urban citizenship)</li>
                        <li>Pollution and environmental sensing</li>
                        <li>Sensory translation technologies</li>
                        <li>Biomaterials and sensing interfaces</li>
                    </ul>
                    <p><strong>Core thesis:</strong> Human perception limits our understanding of urban environments. By developing technologies that translate sensory experiences across species boundaries, we can design more inclusive cities that account for multispecies needs.</p>
                    <p>This project explores how sensing technologies and biomaterial interfaces might help humans perceive urban environments as other species do, revealing invisible forms of pollution and exclusion.</p>
                `
            }
        };
        
        // Elementos del DOM
        const modalOverlay = document.getElementById('modalOverlay');
        const modalClose = document.getElementById('modalClose');
        const modalTitle = document.getElementById('modalTitle');
        const modalSubtitle = document.getElementById('modalSubtitle');
        const modalBody = document.getElementById('modalBody');
        const nodes = document.querySelectorAll('.node');
        const connectionsContainer = document.getElementById('connections');
        
        // Crear conexiones entre nodos
        function createConnections() {
            // Conexiones desde el núcleo central a los 4 clusters principales
            const centralNode = document.querySelector('.central-node');
            const clusterNodes = document.querySelectorAll('.node-urban, .node-hostile, .node-species, .node-research');
            
            clusterNodes.forEach(clusterNode => {
                const connection = document.createElement('div');
                connection.className = 'connection';
                
                // Posicionar la línea entre el núcleo y el cluster
                const centralRect = centralNode.getBoundingClientRect();
                const clusterRect = clusterNode.getBoundingClientRect();
                const containerRect = document.querySelector('.constellation-container').getBoundingClientRect();
                
                // Calcular posición relativa al contenedor
                const x1 = centralRect.left + centralRect.width/2 - containerRect.left;
                const y1 = centralRect.top + centralRect.height/2 - containerRect.top;
                const x2 = clusterRect.left + clusterRect.width/2 - containerRect.left;
                const y2 = clusterRect.top + clusterRect.height/2 - containerRect.top;
                
                // Calcular longitud y ángulo
                const length = Math.sqrt(Math.pow(x2 - x1, 2) + Math.pow(y2 - y1, 2));
                const angle = Math.atan2(y2 - y1, x2 - x1) * 180 / Math.PI;
                
                // Establecer propiedades de la conexión
                connection.style.width = `${length}px`;
                connection.style.left = `${x1}px`;
                connection.style.top = `${y1}px`;
                connection.style.transform = `rotate(${angle}deg)`;
                
                connectionsContainer.appendChild(connection);
            });
            
            // Conexiones adicionales entre clusters y preguntas/acciones
            // (Estas podrían expandirse según sea necesario)
        }
        
        // Inicializar conexiones cuando se cargue la página
        window.addEventListener('load', createConnections);
        
        // Abrir modal al hacer clic en un nodo
        nodes.forEach(node => {
            node.addEventListener('click', function() {
                const modalId = this.getAttribute('data-modal');
                
                if (nodeData[modalId]) {
                    modalTitle.textContent = nodeData[modalId].title;
                    modalSubtitle.textContent = nodeData[modalId].subtitle;
                    modalBody.innerHTML = nodeData[modalId].content;
                    
                    modalOverlay.classList.add('active');
                    document.body.style.overflow = 'hidden';
                }
            });
        });
        
        // Cerrar modal
        modalClose.addEventListener('click', closeModal);
        modalOverlay.addEventListener('click', function(e) {
            if (e.target === modalOverlay) {
                closeModal();
            }
        });
        
        function closeModal() {
            modalOverlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        }
        
        // Efecto de partículas en el fondo (opcional)
        function createParticles() {
            const container = document.querySelector('.constellation-container');
            for (let i = 0; i < 20; i++) {
                const particle = document.createElement('div');
                particle.style.position = 'absolute';
                particle.style.width = Math.random() * 3 + 1 + 'px';
                particle.style.height = particle.style.width;
                particle.style.background = `rgba(${Math.random() > 0.5 ? '138, 63, 252' : '28, 100, 242'}, ${Math.random() * 0.5 + 0.3})`;
                particle.style.borderRadius = '50%';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.zIndex = '0';
                
                // Animación de parpadeo
                particle.style.animation = `twinkle ${Math.random() * 5 + 3}s infinite alternate`;
                
                container.appendChild(particle);
            }
        }
        
        // Inicializar partículas
        createParticles();
        
        // Redibujar conexiones al redimensionar la ventana
        window.addEventListener('resize', function() {
            // Limpiar conexiones existentes
            connectionsContainer.innerHTML = '';
            // Volver a crear conexiones
            createConnections();
        });
    </script>
</body>
