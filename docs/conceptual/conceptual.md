<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE INVISIBLE CITY - Full Visual Map</title>
    <style>
        /* RESET TOTAL - MAPA OCUPA TODO */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
            background: #0a0a14;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        /* MAPA COMPLETO - DISTRIBUCIÓN INTELIGENTE */
        .full-map {
            width: 100vw;
            height: 100vh;
            position: relative;
            background: linear-gradient(135deg, #0a0a14 0%, #1a1a2e 100%);
            overflow: hidden;
        }

        /* GRID INVISIBLE PARA DISTRIBUIR */
        .map-grid {
            position: absolute;
            width: 100%;
            height: 100%;
            display: grid;
            grid-template-columns: repeat(12, 1fr);
            grid-template-rows: repeat(12, 1fr);
            gap: 20px;
            padding: 40px;
        }

        /* ==== POSICIONES ESPECÍFICAS PARA CADA NODO ==== */
        /* Core Concept - Centro */
        .pos-core {
            grid-column: 5 / 9;
            grid-row: 5 / 9;
            justify-self: center;
            align-self: center;
        }

        /* Intuitions - Alrededor del centro */
        .pos-intuition1 { grid-column: 3; grid-row: 3; }
        .pos-intuition2 { grid-column: 9; grid-row: 3; }
        .pos-intuition3 { grid-column: 3; grid-row: 9; }
        .pos-intuition4 { grid-column: 9; grid-row: 9; }

        /* Questions - Círculo medio */
        .pos-question1 { grid-column: 2; grid-row: 2; }
        .pos-question2 { grid-column: 6; grid-row: 1; }
        .pos-question3 { grid-column: 10; grid-row: 2; }
        .pos-question4 { grid-column: 11; grid-row: 6; }
        .pos-question5 { grid-column: 10; grid-row: 10; }
        .pos-question6 { grid-column: 6; grid-row: 11; }
        .pos-question7 { grid-column: 2; grid-row: 10; }
        .pos-question8 { grid-column: 1; grid-row: 6; }

        /* Themes - Posiciones estratégicas */
        .pos-theme1 { grid-column: 2; grid-row: 4; }
        .pos-theme2 { grid-column: 4; grid-row: 2; }
        .pos-theme3 { grid-column: 8; grid-row: 2; }
        .pos-theme4 { grid-column: 10; grid-row: 4; }
        .pos-theme5 { grid-column: 10; grid-row: 8; }
        .pos-theme6 { grid-column: 8; grid-row: 10; }
        .pos-theme7 { grid-column: 4; grid-row: 10; }
        .pos-theme8 { grid-column: 2; grid-row: 8; }

        /* Actions - Círculo externo */
        .pos-action1 { grid-column: 1; grid-row: 3; }
        .pos-action2 { grid-column: 3; grid-row: 1; }
        .pos-action3 { grid-column: 9; grid-row: 1; }
        .pos-action4 { grid-column: 11; grid-row: 3; }
        .pos-action5 { grid-column: 11; grid-row: 9; }
        .pos-action6 { grid-column: 9; grid-row: 11; }
        .pos-action7 { grid-column: 3; grid-row: 11; }
        .pos-action8 { grid-column: 1; grid-row: 9; }

        /* Futures - Esquinas */
        .pos-future1 { grid-column: 1; grid-row: 1; }
        .pos-future2 { grid-column: 11; grid-row: 1; }
        .pos-future3 { grid-column: 1; grid-row: 11; }
        .pos-future4 { grid-column: 11; grid-row: 11; }

        /* ==== ESTILOS DE NODOS - TAMAÑOS GRANDES ==== */
        .node {
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            z-index: 10;
            padding: 25px;
            border-radius: 50%;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            overflow: hidden;
            word-wrap: break-word;
            hyphens: auto;
        }

        /* TAMAÑOS ESPECÍFICOS - GRANDES Y LEGIBLES */
        .node.core {
            width: 280px;
            height: 280px;
            background: radial-gradient(circle at center, #1C64F2, #0a0a14);
            border: 6px solid #1C64F2;
            color: white;
            font-size: 1.3rem;
            font-weight: bold;
            animation: pulse 4s infinite;
        }

        .node.intuition {
            width: 180px;
            height: 180px;
            background: radial-gradient(circle at center, #B51EFF, #0a0a14);
            border: 4px solid #B51EFF;
            color: white;
            font-size: 1.1rem;
        }

        .node.question {
            width: 200px;
            height: 200px;
            background: radial-gradient(circle at center, #FFFFFF, #333);
            border: 4px solid #FFFFFF;
            color: black;
            font-size: 1.1rem;
            font-weight: bold;
        }

        .node.theme {
            width: 220px;
            height: 220px;
            background: radial-gradient(circle at center, var(--theme-color, #8A3FFC), #0a0a14);
            border: 5px solid var(--theme-color, #8A3FFC);
            color: white;
            font-size: 1.2rem;
            font-weight: bold;
        }

        .node.action {
            width: 190px;
            height: 190px;
            background: transparent;
            border: 4px solid var(--action-color, #FF9F1C);
            color: var(--action-color, #FF9F1C);
            font-size: 1.1rem;
            position: relative;
        }

        .node.action::before {
            content: '';
            position: absolute;
            top: 15px;
            left: 15px;
            right: 15px;
            bottom: 15px;
            border: 2px solid var(--action-color, #FF9F1C);
            border-radius: 50%;
            opacity: 0.5;
        }

        .node.future {
            width: 210px;
            height: 210px;
            background: radial-gradient(circle at center, #00D4FF, #0a0a14);
            border: 5px solid #00D4FF;
            color: white;
            font-size: 1.2rem;
            font-weight: bold;
            clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); box-shadow: 0 0 30px rgba(28, 100, 242, 0.5); }
            50% { transform: scale(1.05); box-shadow: 0 0 50px rgba(28, 100, 242, 0.8); }
        }

        /* CONTENIDO DE NODOS - TEXTO BIEN DISPUESTO */
        .node-content {
            padding: 15px;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            overflow: visible;
        }

        .node-title {
            font-weight: bold;
            margin-bottom: 8px;
            font-size: 1.4em;
            line-height: 1.2;
            text-transform: uppercase;
            max-width: 90%;
        }

        .node-description {
            font-size: 0.9em;
            opacity: 0.9;
            line-height: 1.3;
            max-width: 90%;
        }

        /* ==== CONEXIONES VISIBLES ==== */
        .connections-layer {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .connection {
            stroke: rgba(255, 255, 255, 0.3);
            stroke-width: 2;
            fill: none;
        }

        .connection-strong {
            stroke: rgba(0, 212, 255, 0.6);
            stroke-width: 3;
        }

        /* ==== HOVER EFECTS ==== */
        .node:hover {
            transform: scale(1.1);
            z-index: 100;
            filter: brightness(1.3);
        }

        .node.core:hover {
            box-shadow: 0 0 60px rgba(28, 100, 242, 0.9);
        }

        /* ==== TOOLTIP MEJORADO ==== */
        .tooltip {
            position: fixed;
            background: rgba(10, 10, 20, 0.95);
            border: 2px solid #1C64F2;
            border-radius: 12px;
            padding: 20px;
            max-width: 350px;
            color: white;
            font-size: 1rem;
            z-index: 1000;
            pointer-events: none;
            opacity: 0;
            transform: translateY(10px);
            transition: all 0.3s ease;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
        }

        .tooltip.active {
            opacity: 1;
            transform: translateY(0);
        }

        .tooltip-title {
            color: #1C64F2;
            font-size: 1.3rem;
            margin-bottom: 10px;
            font-weight: bold;
        }

        .tooltip-content {
            line-height: 1.5;
        }

        /* ==== RESPONSIVE - MANTENER DISTRIBUCIÓN ==== */
        @media (max-width: 1400px) {
            .map-grid {
                padding: 30px;
                gap: 15px;
            }
            
            .node.core { width: 250px; height: 250px; font-size: 1.2rem; }
            .node.theme { width: 200px; height: 200px; font-size: 1.1rem; }
            .node.future { width: 190px; height: 190px; font-size: 1.1rem; }
            .node.question { width: 180px; height: 180px; font-size: 1rem; }
            .node.intuition { width: 160px; height: 160px; font-size: 1rem; }
            .node.action { width: 170px; height: 170px; font-size: 1rem; }
        }

        @media (max-width: 1024px) {
            .map-grid {
                padding: 20px;
                gap: 10px;
            }
            
            .node.core { width: 220px; height: 220px; font-size: 1.1rem; padding: 20px; }
            .node.theme { width: 180px; height: 180px; font-size: 1rem; }
            .node.future { width: 170px; height: 170px; font-size: 1rem; }
            .node.question { width: 160px; height: 160px; font-size: 0.95rem; }
            .node.intuition { width: 140px; height: 140px; font-size: 0.9rem; }
            .node.action { width: 150px; height: 150px; font-size: 0.9rem; }
            
            .node-title { font-size: 1.2em; }
            .node-description { font-size: 0.85em; }
        }

        @media (max-width: 768px) {
            .map-grid {
                grid-template-columns: repeat(8, 1fr);
                grid-template-rows: repeat(8, 1fr);
                padding: 15px;
            }
            
            /* Reajustar posiciones para pantallas más pequeñas */
            .pos-core { grid-column: 3 / 7; grid-row: 3 / 7; }
            .pos-intuition1 { grid-column: 1; grid-row: 1; }
            .pos-intuition2 { grid-column: 7; grid-row: 1; }
            .pos-intuition3 { grid-column: 1; grid-row: 7; }
            .pos-intuition4 { grid-column: 7; grid-row: 7; }
            
            .node.core { width: 180px; height: 180px; font-size: 1rem; }
            .node.theme { width: 150px; height: 150px; font-size: 0.9rem; }
            .node.future { width: 140px; height: 140px; font-size: 0.9rem; }
            .node.question { width: 130px; height: 130px; font-size: 0.85rem; }
            .node.intuition { width: 120px; height: 120px; font-size: 0.8rem; }
            .node.action { width: 120px; height: 120px; font-size: 0.8rem; }
            
            .tooltip {
                max-width: 280px;
                padding: 15px;
                font-size: 0.9rem;
            }
        }

        @media (max-width: 480px) {
            .map-grid {
                grid-template-columns: repeat(6, 1fr);
                grid-template-rows: repeat(6, 1fr);
                padding: 10px;
                gap: 5px;
            }
            
            .pos-core { grid-column: 2 / 6; grid-row: 2 / 6; }
            
            .node.core { width: 150px; height: 150px; font-size: 0.9rem; padding: 15px; }
            .node.theme { width: 120px; height: 120px; font-size: 0.8rem; }
            .node.future { width: 110px; height: 110px; font-size: 0.8rem; }
            .node.question { width: 100px; height: 100px; font-size: 0.75rem; }
            .node.intuition { width: 90px; height: 90px; font-size: 0.7rem; }
            .node.action { width: 90px; height: 90px; font-size: 0.7rem; }
            
            .node-title { font-size: 1em; }
            .node-description { font-size: 0.75em; }
        }
    </style>
</head>
<body>
    <!-- MAPA COMPLETO CON DISTRIBUCIÓN INTELIGENTE -->
    <div class="full-map">
        <!-- Capa de conexiones -->
        <div class="connections-layer" id="connections"></div>
        
        <!-- Grid para distribución -->
        <div class="map-grid" id="mapGrid">
            <!-- Los nodos se insertarán aquí con sus posiciones específicas -->
        </div>
        
        <!-- Tooltip -->
        <div class="tooltip" id="tooltip">
            <div class="tooltip-title" id="tooltipTitle"></div>
            <div class="tooltip-content" id="tooltipContent"></div>
        </div>
    </div>

    <script>
        // ==== DATOS DEL MAPA ====
        const mapData = [
            // Core Concept - CENTRO
            {
                id: "core",
                type: "core",
                title: "THE INVISIBLE CITY",
                description: "Urban aesthetics conceal systemic violence against human and non-human life.",
                tooltip: "The central concept: Beauty in cities often hides violence and exclusion against vulnerable lives and species.",
                position: "pos-core"
            },
            
            // Intuitions - Alrededor del centro
            {
                id: "intuition1",
                type: "intuition",
                title: "Beauty Excludes",
                description: "Aesthetic standards as tools of power",
                tooltip: "Clean spaces, curated nature, orderly facades that make some lives 'dirt' and others 'proper'.",
                position: "pos-intuition1",
                color: "#B51EFF"
            },
            {
                id: "intuition2",
                type: "intuition",
                title: "Violence Hidden",
                description: "Aesthetics mask structural harm",
                tooltip: "The violence of absence: what is systematically removed or made invisible in the name of beauty.",
                position: "pos-intuition2",
                color: "#B51EFF"
            },
            {
                id: "intuition3",
                type: "intuition",
                title: "Nature Expelled",
                description: "Non-curated life removed",
                tooltip: "Plants as decoration, animals as pests, ecosystems as 'mess' to be cleaned from urban spaces.",
                position: "pos-intuition3",
                color: "#B51EFF"
            },
            {
                id: "intuition4",
                type: "intuition",
                title: "Order as Control",
                description: "Disguised as care, enacted as power",
                tooltip: "Safety measures that exclude, cleanliness that erases, maintenance that displaces vulnerable lives.",
                position: "pos-intuition4",
                color: "#B51EFF"
            },
            
            // Questions - Círculo medio
            {
                id: "question1",
                type: "question",
                title: "Who Can Rest?",
                description: "Politics of pause in public space",
                tooltip: "Questioning benches designed against sleeping, surfaces that deny comfort, temporal restrictions on presence.",
                position: "pos-question1"
            },
            {
                id: "question2",
                type: "question",
                title: "Whose Lives Matter?",
                description: "Hierarchy of urban citizenship",
                tooltip: "From homeless humans to pigeons: which lives are welcomed, tolerated, or actively eliminated?",
                position: "pos-question2"
            },
            {
                id: "question3",
                type: "question",
                title: "Beauty Justifies?",
                description: "Aesthetic rationale for exclusion",
                tooltip: "How visual pleasure becomes an alibi for systemic violence in urban 'improvement' projects.",
                position: "pos-question3"
            },
            {
                id: "question4",
                type: "question",
                title: "Design Empathy?",
                description: "Cross-species understanding",
                tooltip: "Can interfaces help humans feel what other species feel in cities?",
                position: "pos-question4"
            },
            {
                id: "question5",
                type: "question",
                title: "Normalized Violence?",
                description: "Invisible systemic harm",
                tooltip: "Violence of spikes, smooth benches, pesticides, constant noise.",
                position: "pos-question5"
            },
            {
                id: "question6",
                type: "question",
                title: "Species Design?",
                description: "Non-human urban planning",
                tooltip: "What would a pigeon's ideal plaza look like? A bee's transportation system?",
                position: "pos-question6"
            },
            
            // Themes - Temas principales
            {
                id: "theme1",
                type: "theme",
                title: "Urban Aesthetics",
                description: "Politics of beauty",
                tooltip: "How aesthetic standards normalize exclusion and control. Beauty as ideology.",
                position: "pos-theme1",
                color: "#8A3FFC"
            },
            {
                id: "theme2",
                type: "theme",
                title: "Hostile Design",
                description: "Architecture expels",
                tooltip: "Anti-homeless benches, pigeon spikes, seating deterrents.",
                position: "pos-theme2",
                color: "#FF9F1C"
            },
            {
                id: "theme3",
                type: "theme",
                title: "Multispecies Justice",
                description: "Beyond human rights",
                tooltip: "Questioning anthropocentric cities. Rights for all species.",
                position: "pos-theme3",
                color: "#FFDD00"
            },
            {
                id: "theme4",
                type: "theme",
                title: "Embodied Research",
                description: "Body as method",
                tooltip: "Walking, sitting, wearing, performing to reveal hidden violence.",
                position: "pos-theme4",
                color: "#00C49A"
            },
            {
                id: "theme5",
                type: "theme",
                title: "Sensory Translation",
                description: "Cross-species perception",
                tooltip: "Interfaces for perceiving pollution, noise, vibration as other species do.",
                position: "pos-theme5",
                color: "#E11D48"
            },
            {
                id: "theme6",
                type: "theme",
                title: "Environmental Empathy",
                description: "Feeling-with ecosystems",
                tooltip: "Developing emotional connections to non-human urban residents.",
                position: "pos-theme6",
                color: "#1C64F2"
            },
            
            // Actions - Acciones
            {
                id: "action1",
                type: "action",
                title: "Sitting Hostile",
                description: "Body as sensor",
                tooltip: "Using the body to experience exclusionary urban furniture.",
                position: "pos-action1",
                color: "#FF9F1C"
            },
            {
                id: "action2",
                type: "action",
                title: "Returning Life",
                description: "Rewilding acts",
                tooltip: "Soil deposits, seed bombs, moss graffiti. Reintroducing non-curated life.",
                position: "pos-action2",
                color: "#00C49A"
            },
            {
                id: "action3",
                type: "action",
                title: "Wearing Hostility",
                description: "Material translation",
                tooltip: "Turning anti-pigeon spikes into clothing. Making violence visible.",
                position: "pos-action3",
                color: "#E11D48"
            },
            {
                id: "action4",
                type: "action",
                title: "Sensory Experiments",
                description: "Perception interfaces",
                tooltip: "Devices that translate urban conditions across species.",
                position: "pos-action4",
                color: "#1C64F2"
            },
            
            // Futures - Futuros emergentes
            {
                id: "future1",
                type: "future",
                title: "Multispecies Perception",
                description: "Cross-sensing tools",
                tooltip: "Wearables that help humans perceive as other species do.",
                position: "pos-future1"
            },
            {
                id: "future2",
                type: "future",
                title: "Embodied Translation",
                description: "Full-body ecology",
                tooltip: "Haptic suits, olfactory displays making environments tangible.",
                position: "pos-future2"
            },
            {
                id: "future3",
                type: "future",
                title: "Empathy-Driven Design",
                description: "Compassionate planning",
                tooltip: "Design centering multispecies wellbeing and sensory justice.",
                position: "pos-future3"
            },
            {
                id: "future4",
                type: "future",
                title: "Urban Coexistence",
                description: "Multispecies community",
                tooltip: "Cities where all residents are recognized as citizens.",
                position: "pos-future4"
            }
        ];

        // ==== CREAR EL MAPA ====
        function createMap() {
            const grid = document.getElementById('mapGrid');
            
            mapData.forEach(nodeData => {
                const node = document.createElement('div');
                node.className = `node ${nodeData.type} ${nodeData.position}`;
                node.id = nodeData.id;
                
                // Aplicar color si existe
                if (nodeData.color) {
                    node.style.setProperty('--theme-color', nodeData.color);
                    node.style.setProperty('--action-color', nodeData.color);
                }
                
                // Contenido
                const content = document.createElement('div');
                content.className = 'node-content';
                
                const title = document.createElement('div');
                title.className = 'node-title';
                title.textContent = nodeData.title;
                
                const description = document.createElement('div');
                description.className = 'node-description';
                description.textContent = nodeData.description;
                
                content.appendChild(title);
                content.appendChild(description);
                node.appendChild(content);
                
                // Eventos
                node.addEventListener('mouseenter', (e) => showTooltip(e, nodeData));
                node.addEventListener('mouseleave', hideTooltip);
                
                grid.appendChild(node);
            });
            
            // Crear conexiones después de que los nodos existan
            setTimeout(createConnections, 100);
        }

        // ==== CREAR CONEXIONES ====
        function createConnections() {
            const connections = document.getElementById('connections');
            connections.innerHTML = '';
            
            const svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
            svg.setAttribute('class', 'connections-layer');
            svg.setAttribute('width', '100%');
            svg.setAttribute('height', '100%');
            
            // Conexiones principales
            connect(svg, "core", "intuition1", "strong");
            connect(svg, "core", "intuition2", "strong");
            connect(svg, "core", "intuition3", "strong");
            connect(svg, "core", "intuition4", "strong");
            
            connect(svg, "intuition1", "theme1", "normal");
            connect(svg, "intuition2", "theme3", "normal");
            connect(svg, "intuition3", "theme7", "normal");
            connect(svg, "intuition4", "theme5", "normal");
            
            connect(svg, "theme2", "action1", "normal");
            connect(svg, "theme3", "action2", "normal");
            connect(svg, "theme5", "action3", "normal");
            connect(svg, "theme6", "action4", "normal");
            
            connect(svg, "action2", "future1", "normal");
            connect(svg, "action4", "future2", "normal");
            connect(svg, "theme6", "future3", "normal");
            connect(svg, "theme4", "future4", "normal");
            
            connections.appendChild(svg);
        }

        function connect(svg, id1, id2, strength) {
            const node1 = document.getElementById(id1);
            const node2 = document.getElementById(id2);
            
            if (!node1 || !node2) return;
            
            // Obtener posiciones centrales de los nodos
            const rect1 = node1.getBoundingClientRect();
            const rect2 = node2.getBoundingClientRect();
            
            const x1 = rect1.left + rect1.width / 2;
            const y1 = rect1.top + rect1.height / 2;
            const x2 = rect2.left + rect2.width / 2;
            const y2 = rect2.top + rect2.height / 2;
            
            const line = document.createElementNS("http://www.w3.org/2000/svg", "line");
            line.setAttribute('x1', x1);
            line.setAttribute('y1', y1);
            line.setAttribute('x2', x2);
            line.setAttribute('y2', y2);
            line.setAttribute('class', `connection ${strength === 'strong' ? 'connection-strong' : ''}`);
            
            svg.appendChild(line);
        }

        // ==== TOOLTIP ====
        const tooltip = document.getElementById('tooltip');
        const tooltipTitle = document.getElementById('tooltipTitle');
        const tooltipContent = document.getElementById('tooltipContent');

        function showTooltip(event, nodeData) {
            tooltipTitle.textContent = nodeData.title;
            tooltipContent.textContent = nodeData.tooltip;
            
            tooltip.style.left = `${event.clientX + 15}px`;
            tooltip.style.top = `${event.clientY + 15}px`;
            tooltip.classList.add('active');
        }

        function hideTooltip() {
            tooltip.classList.remove('active');
        }

        // ==== INICIALIZAR ====
        document.addEventListener('DOMContentLoaded', () => {
            createMap();
            
            // Mover tooltip con el mouse
            document.addEventListener('mousemove', (e) => {
                if (tooltip.classList.contains('active')) {
                    tooltip.style.left = `${e.clientX + 15}px`;
                    tooltip.style.top = `${e.clientY + 15}px`;
                }
            });
            
            // Redibujar conexiones al cambiar tamaño
            window.addEventListener('resize', () => {
                setTimeout(createConnections, 100);
            });
        });
    </script>
</body>
</html>