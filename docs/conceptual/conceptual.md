<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE INVISIBLE CITY - Full Screen Constellation</title>
    <style>
        /* RESET RADICAL - TODO ES EL MAPA */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            width: 100vw;
            height: 100vh;
            overflow: hidden;
            background: #000000;
            font-family: 'Arial', sans-serif;
        }

        /* CONTENEDOR PRINCIPAL - 100% PANTALLA */
        .universe {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #000;
            overflow: hidden;
        }

        /* FONDO ESTRELLADO */
        .stars {
            position: absolute;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(2px 2px at 20% 30%, rgba(255,255,255,0.1) 1px, transparent 0),
                radial-gradient(2px 2px at 40% 70%, rgba(255,255,255,0.1) 1px, transparent 0),
                radial-gradient(2px 2px at 60% 20%, rgba(255,255,255,0.1) 1px, transparent 0),
                radial-gradient(2px 2px at 80% 50%, rgba(255,255,255,0.1) 1px, transparent 0),
                radial-gradient(2px 2px at 30% 80%, rgba(255,255,255,0.1) 1px, transparent 0);
            animation: twinkle 3s infinite alternate;
        }

        @keyframes twinkle {
            0% { opacity: 0.7; }
            100% { opacity: 1; }
        }

        /* CENTRO ABSOLUTO DEL UNIVERSO */
        .center-point {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 20px;
            height: 20px;
            background: #00ff00;
            border-radius: 50%;
            z-index: 1000;
        }

        /* ==== NODOS GIGANTES ==== */
        .node {
            position: absolute;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            z-index: 10;
            padding: 25px;
            box-sizing: border-box;
            overflow: hidden;
            word-wrap: break-word;
            hyphens: auto;
        }

        /* NÚCLEO - ENORME */
        .core {
            width: 320px !important;
            height: 320px !important;
            background: radial-gradient(circle at center, #1C64F2, #000);
            border: 8px solid #00ffff;
            box-shadow: 0 0 80px #00ffff;
            color: white;
            font-size: 1.4rem;
            font-weight: bold;
            animation: pulse 4s infinite;
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 0 80px #00ffff; transform: translate(-50%, -50%) scale(1); }
            50% { box-shadow: 0 0 120px #00ffff; transform: translate(-50%, -50%) scale(1.05); }
        }

        /* INTUICIONES - GRANDES */
        .intuition {
            width: 200px !important;
            height: 200px !important;
            background: radial-gradient(circle at center, #B51EFF, #000);
            border: 6px solid #B51EFF;
            box-shadow: 0 0 60px #B51EFF;
            color: white;
            font-size: 1.2rem;
        }

        /* PREGUNTAS - GRANDES */
        .question {
            width: 220px !important;
            height: 220px !important;
            background: radial-gradient(circle at center, #FFFFFF, #333);
            border: 6px solid #FFFFFF;
            box-shadow: 0 0 60px #FFFFFF;
            color: black;
            font-size: 1.2rem;
            font-weight: bold;
        }

        /* TEMAS - ENORMES */
        .theme {
            width: 280px !important;
            height: 280px !important;
            background: radial-gradient(circle at center, currentColor, #000);
            border: 8px solid;
            box-shadow: 0 0 70px currentColor;
            color: inherit;
            font-size: 1.3rem;
            font-weight: bold;
        }

        /* ACCIONES - GRANDES */
        .action {
            width: 240px !important;
            height: 240px !important;
            background: radial-gradient(circle at center, transparent, #000);
            border: 8px solid;
            box-shadow: 0 0 60px currentColor;
            color: inherit;
            font-size: 1.2rem;
            position: relative;
        }

        .action::before {
            content: '';
            position: absolute;
            top: 20px;
            left: 20px;
            right: 20px;
            bottom: 20px;
            border: 4px solid;
            border-radius: 50%;
            opacity: 0.5;
        }

        /* FUTUROS - ENORMES */
        .future {
            width: 260px !important;
            height: 260px !important;
            background: radial-gradient(circle at center, #00D4FF, #000);
            border: 8px solid #00D4FF;
            box-shadow: 0 0 80px #00D4FF;
            color: white;
            font-size: 1.3rem;
            font-weight: bold;
            clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        }

        /* ==== COLORES ==== */
        .color-1 { color: #8A3FFC; } /* Violeta */
        .color-2 { color: #FF9F1C; } /* Ámbar */
        .color-3 { color: #FFDD00; } /* Amarillo */
        .color-4 { color: #00C49A; } /* Verde */
        .color-5 { color: #E11D48; } /* Rojo */
        .color-6 { color: #1C64F2; } /* Azul */

        /* ==== CONTENIDO DE NODOS ==== */
        .node-content {
            padding: 20px;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .node-title {
            font-weight: bold;
            margin-bottom: 10px;
            font-size: 1.4em;
            text-transform: uppercase;
            line-height: 1.2;
        }

        .node-description {
            font-size: 1em;
            opacity: 0.9;
            line-height: 1.3;
        }

        /* ==== CONEXIONES VISIBLES ==== */
        .connection {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .connection-line {
            stroke: rgba(255, 255, 255, 0.4);
            stroke-width: 3;
            fill: none;
            filter: drop-shadow(0 0 10px rgba(255,255,255,0.5));
        }

        .connection-strong {
            stroke: rgba(0, 212, 255, 0.6);
            stroke-width: 4;
            filter: drop-shadow(0 0 15px rgba(0,212,255,0.7));
        }

        /* ==== HOVER EFECTS ==== */
        .node:hover {
            transform: translate(-50%, -50%) scale(1.2) !important;
            z-index: 100 !important;
            filter: brightness(1.5);
        }

        .core:hover {
            box-shadow: 0 0 150px #00ffff;
        }

        /* ==== TOOLTIP SIMPLE ==== */
        .tooltip {
            position: fixed;
            background: rgba(0, 0, 0, 0.95);
            border: 2px solid #00ffff;
            border-radius: 10px;
            padding: 20px;
            max-width: 400px;
            color: white;
            font-size: 1.1rem;
            z-index: 10000;
            pointer-events: none;
            opacity: 0;
            transform: translateY(10px);
            transition: all 0.3s ease;
            box-shadow: 0 0 40px rgba(0,255,255,0.5);
        }

        .tooltip.active {
            opacity: 1;
            transform: translateY(0);
        }

        .tooltip-title {
            color: #00ffff;
            font-size: 1.4rem;
            margin-bottom: 10px;
            font-weight: bold;
        }

        /* ==== CONTROLES ==== */
        .controls {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1000;
            display: flex;
            gap: 10px;
        }

        .control-btn {
            background: rgba(0, 0, 0, 0.8);
            border: 2px solid #00ffff;
            color: white;
            padding: 12px 24px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .control-btn:hover {
            background: rgba(0, 212, 255, 0.3);
            transform: scale(1.1);
        }

        /* ==== RESPONSIVE EXTREMO ==== */
        @media (max-width: 1200px) {
            .core { width: 280px !important; height: 280px !important; font-size: 1.2rem; }
            .theme { width: 240px !important; height: 240px !important; }
            .future { width: 220px !important; height: 220px !important; }
            .action { width: 200px !important; height: 200px !important; }
            .intuition { width: 180px !important; height: 180px !important; }
            .question { width: 190px !important; height: 190px !important; }
        }

        @media (max-width: 768px) {
            .core { width: 220px !important; height: 220px !important; font-size: 1rem; padding: 15px; }
            .theme { width: 180px !important; height: 180px !important; }
            .future { width: 160px !important; height: 160px !important; }
            .action { width: 150px !important; height: 150px !important; }
            .intuition { width: 140px !important; height: 140px !important; }
            .question { width: 150px !important; height: 150px !important; }
            
            .node-title { font-size: 1.1em; }
            .node-description { font-size: 0.9em; }
            
            .tooltip {
                max-width: 300px;
                padding: 15px;
                font-size: 0.9rem;
            }
        }

        @media (max-width: 480px) {
            .core { width: 180px !important; height: 180px !important; font-size: 0.9rem; padding: 10px; }
            .theme { width: 150px !important; height: 150px !important; }
            .future { width: 130px !important; height: 130px !important; }
            .action { width: 120px !important; height: 120px !important; }
            .intuition { width: 110px !important; height: 110px !important; }
            .question { width: 120px !important; height: 120px !important; }
            
            .controls {
                bottom: 10px;
                right: 10px;
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- UNIVERSO COMPLETO -->
    <div class="universe" id="universe">
        <!-- Fondo -->
        <div class="stars"></div>
        
        <!-- Punto central (referencia) -->
        <div class="center-point"></div>
        
        <!-- Conexiones -->
        <div class="connection" id="connections"></div>
        
        <!-- Nodos se insertan aquí -->
        <div id="nodesContainer"></div>
        
        <!-- Tooltip -->
        <div class="tooltip" id="tooltip">
            <div class="tooltip-title" id="tooltipTitle"></div>
            <div id="tooltipContent"></div>
        </div>
    </div>

    <!-- Controles -->
    <div class="controls">
        <button class="control-btn" onclick="toggleConnections()">Conexiones ON/OFF</button>
        <button class="control-btn" onclick="toggleFullscreen()">Pantalla Completa</button>
        <button class="control-btn" onclick="resetZoom()">Reiniciar Zoom</button>
    </div>

    <script>
        // ==== DATOS COMPLETOS DEL MAPA ====
        const mapData = {
            core: {
                id: "core",
                type: "core",
                title: "THE INVISIBLE CITY",
                description: "Urban aesthetics conceal systemic violence against human and non-human life.",
                tooltip: "The central concept: Beauty in cities often hides violence and exclusion against vulnerable lives and species.",
                color: "color-6",
                x: 50, // Porcentaje del ancho
                y: 50  // Porcentaje del alto
            },
            
            intuitions: [
                {
                    id: "intuition1",
                    type: "intuition",
                    title: "Beauty Excludes",
                    description: "Aesthetic standards as tools of power",
                    tooltip: "Clean spaces, curated nature, orderly facades that make some lives 'dirt' and others 'proper'.",
                    color: "color-1",
                    angle: 0,   // Grados desde el centro
                    distance: 25 // % de distancia del centro
                },
                {
                    id: "intuition2",
                    type: "intuition",
                    title: "Violence Hidden",
                    description: "Aesthetics mask structural harm",
                    tooltip: "The violence of absence: what is systematically removed or made invisible in the name of beauty.",
                    color: "color-1",
                    angle: 90,
                    distance: 25
                },
                {
                    id: "intuition3",
                    type: "intuition",
                    title: "Nature Expelled",
                    description: "Non-curated life removed",
                    tooltip: "Plants as decoration, animals as pests, ecosystems as 'mess' to be cleaned from urban spaces.",
                    color: "color-1",
                    angle: 180,
                    distance: 25
                },
                {
                    id: "intuition4",
                    type: "intuition",
                    title: "Order as Control",
                    description: "Disguised as care, enacted as power",
                    tooltip: "Safety measures that exclude, cleanliness that erases, maintenance that displaces vulnerable lives.",
                    color: "color-1",
                    angle: 270,
                    distance: 25
                }
            ],
            
            questions: [
                {
                    id: "question1",
                    type: "question",
                    title: "Who Can Rest?",
                    description: "Politics of pause in public space",
                    tooltip: "Questioning benches designed against sleeping, surfaces that deny comfort, temporal restrictions on presence.",
                    color: "",
                    angle: 30,
                    distance: 40
                },
                {
                    id: "question2",
                    type: "question",
                    title: "Whose Lives Matter?",
                    description: "Hierarchy of urban citizenship",
                    tooltip: "From homeless humans to pigeons: which lives are welcomed, tolerated, or actively eliminated?",
                    color: "",
                    angle: 90,
                    distance: 40
                },
                {
                    id: "question3",
                    type: "question",
                    title: "Beauty Justifies?",
                    description: "Aesthetic rationale for exclusion",
                    tooltip: "How visual pleasure becomes an alibi for systemic violence in urban 'improvement' projects.",
                    color: "",
                    angle: 150,
                    distance: 40
                },
                {
                    id: "question4",
                    type: "question",
                    title: "Design Empathy?",
                    description: "Cross-species understanding",
                    tooltip: "Can interfaces help humans feel what other species feel in cities?",
                    color: "",
                    angle: 210,
                    distance: 40
                },
                {
                    id: "question5",
                    type: "question",
                    title: "Normalized Violence?",
                    description: "Invisible systemic harm",
                    tooltip: "Violence of spikes, smooth benches, pesticides, constant noise.",
                    color: "",
                    angle: 270,
                    distance: 40
                },
                {
                    id: "question6",
                    type: "question",
                    title: "Species Design?",
                    description: "Non-human urban planning",
                    tooltip: "What would a pigeon's ideal plaza look like? A bee's transportation system?",
                    color: "",
                    angle: 330,
                    distance: 40
                }
            ],
            
            themes: [
                {
                    id: "theme1",
                    type: "theme",
                    title: "Urban Aesthetics",
                    description: "Politics of beauty",
                    tooltip: "How aesthetic standards normalize exclusion and control. Beauty as ideology.",
                    color: "color-1",
                    angle: 20,
                    distance: 55
                },
                {
                    id: "theme2",
                    type: "theme",
                    title: "Hostile Design",
                    description: "Architecture expels",
                    tooltip: "Anti-homeless benches, pigeon spikes, seating deterrents.",
                    color: "color-2",
                    angle: 80,
                    distance: 55
                },
                {
                    id: "theme3",
                    type: "theme",
                    title: "Multispecies Justice",
                    description: "Beyond human rights",
                    tooltip: "Questioning anthropocentric cities. Rights for all species.",
                    color: "color-3",
                    angle: 140,
                    distance: 55
                },
                {
                    id: "theme4",
                    type: "theme",
                    title: "Embodied Research",
                    description: "Body as method",
                    tooltip: "Walking, sitting, wearing, performing to reveal hidden violence.",
                    color: "color-4",
                    angle: 200,
                    distance: 55
                },
                {
                    id: "theme5",
                    type: "theme",
                    title: "Sensory Translation",
                    description: "Cross-species perception",
                    tooltip: "Interfaces for perceiving pollution, noise, vibration as other species do.",
                    color: "color-5",
                    angle: 260,
                    distance: 55
                },
                {
                    id: "theme6",
                    type: "theme",
                    title: "Environmental Empathy",
                    description: "Feeling-with ecosystems",
                    tooltip: "Developing emotional connections to non-human urban residents.",
                    color: "color-6",
                    angle: 320,
                    distance: 55
                }
            ],
            
            actions: [
                {
                    id: "action1",
                    type: "action",
                    title: "Sitting Hostile",
                    description: "Body as sensor",
                    tooltip: "Using the body to experience exclusionary urban furniture.",
                    color: "color-2",
                    angle: 45,
                    distance: 70
                },
                {
                    id: "action2",
                    type: "action",
                    title: "Returning Life",
                    description: "Rewilding acts",
                    tooltip: "Soil deposits, seed bombs, moss graffiti. Reintroducing non-curated life.",
                    color: "color-4",
                    angle: 135,
                    distance: 70
                },
                {
                    id: "action3",
                    type: "action",
                    title: "Wearing Hostility",
                    description: "Material translation",
                    tooltip: "Turning anti-pigeon spikes into clothing. Making violence visible.",
                    color: "color-5",
                    angle: 225,
                    distance: 70
                },
                {
                    id: "action4",
                    type: "action",
                    title: "Sensory Experiments",
                    description: "Perception interfaces",
                    tooltip: "Devices that translate urban conditions across species.",
                    color: "color-6",
                    angle: 315,
                    distance: 70
                }
            ],
            
            futures: [
                {
                    id: "future1",
                    type: "future",
                    title: "Multispecies Perception",
                    description: "Cross-sensing tools",
                    tooltip: "Wearables that help humans perceive as other species do.",
                    color: "",
                    angle: 60,
                    distance: 85
                },
                {
                    id: "future2",
                    type: "future",
                    title: "Embodied Translation",
                    description: "Full-body ecology",
                    tooltip: "Haptic suits, olfactory displays making environments tangible.",
                    color: "",
                    angle: 150,
                    distance: 85
                },
                {
                    id: "future3",
                    type: "future",
                    title: "Empathy-Driven Design",
                    description: "Compassionate planning",
                    tooltip: "Design centering multispecies wellbeing and sensory justice.",
                    color: "",
                    angle: 240,
                    distance: 85
                },
                {
                    id: "future4",
                    type: "future",
                    title: "Urban Coexistence",
                    description: "Multispecies community",
                    tooltip: "Cities where all residents are recognized as citizens.",
                    color: "",
                    angle: 330,
                    distance: 85
                }
            ]
        };

        // ==== CREAR EL MAPA ====
        function createMap() {
            const container = document.getElementById('nodesContainer');
            container.innerHTML = '';
            
            // Crear nodo central
            createNode(mapData.core, container);
            
            // Crear todos los nodos
            const allNodes = [
                ...mapData.intuitions,
                ...mapData.questions,
                ...mapData.themes,
                ...mapData.actions,
                ...mapData.futures
            ];
            
            allNodes.forEach(node => createNode(node, container));
            
            // Crear conexiones
            createConnections();
        }

        function createNode(nodeData, container) {
            const node = document.createElement('div');
            node.className = `node ${nodeData.type} ${nodeData.color}`;
            node.id = nodeData.id;
            
            // Calcular posición
            let x, y;
            if (nodeData.type === 'core') {
                x = nodeData.x;
                y = nodeData.y;
            } else {
                // Convertir ángulo y distancia a coordenadas
                const angleRad = (nodeData.angle * Math.PI) / 180;
                x = 50 + (nodeData.distance * Math.cos(angleRad));
                y = 50 + (nodeData.distance * Math.sin(angleRad));
            }
            
            node.style.left = `${x}%`;
            node.style.top = `${y}%`;
            
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
            node.addEventListener('click', () => highlightNode(nodeData));
            
            container.appendChild(node);
        }

        function createConnections() {
            const connections = document.getElementById('connections');
            connections.innerHTML = '';
            
            const svgNS = "http://www.w3.org/2000/svg";
            const svg = document.createElementNS(svgNS, "svg");
            svg.setAttribute('width', '100%');
            svg.setAttribute('height', '100%');
            
            // Conexiones principales
            connectNodes(svg, "core", "intuition1", "strong");
            connectNodes(svg, "core", "theme1", "normal");
            connectNodes(svg, "core", "theme2", "normal");
            connectNodes(svg, "theme2", "action1", "normal");
            connectNodes(svg, "theme3", "action2", "normal");
            connectNodes(svg, "theme5", "future1", "normal");
            connectNodes(svg, "theme6", "future3", "normal");
            
            connections.appendChild(svg);
        }

        function connectNodes(svg, id1, id2, strength) {
            const node1 = document.getElementById(id1);
            const node2 = document.getElementById(id2);
            
            if (!node1 || !node2) return;
            
            const svgNS = "http://www.w3.org/2000/svg";
            const line = document.createElementNS(svgNS, "line");
            
            const x1 = parseFloat(node1.style.left);
            const y1 = parseFloat(node1.style.top);
            const x2 = parseFloat(node2.style.left);
            const y2 = parseFloat(node2.style.top);
            
            line.setAttribute('x1', x1 + '%');
            line.setAttribute('y1', y1 + '%');
            line.setAttribute('x2', x2 + '%');
            line.setAttribute('y2', y2 + '%');
            line.setAttribute('class', `connection-line ${strength === 'strong' ? 'connection-strong' : ''}`);
            
            svg.appendChild(line);
        }

        // ==== INTERACCIÓN ====
        const tooltip = document.getElementById('tooltip');
        const tooltipTitle = document.getElementById('tooltipTitle');
        const tooltipContent = document.getElementById('tooltipContent');

        function showTooltip(event, nodeData) {
            tooltipTitle.textContent = nodeData.title;
            tooltipContent.textContent = nodeData.tooltip;
            
            tooltip.style.left = `${event.clientX + 20}px`;
            tooltip.style.top = `${event.clientY + 20}px`;
            tooltip.classList.add('active');
        }

        function hideTooltip() {
            tooltip.classList.remove('active');
        }

        function highlightNode(nodeData) {
            console.log(`Nodo seleccionado: ${nodeData.title}`);
            // Aquí puedes añadir efectos especiales
            const node = document.getElementById(nodeData.id);
            node.style.animation = 'none';
            setTimeout(() => {
                node.style.animation = '';
            }, 10);
        }

        // ==== CONTROLES ====
        let connectionsVisible = true;

        function toggleConnections() {
            connectionsVisible = !connectionsVisible;
            const connections = document.getElementById('connections');
            connections.style.opacity = connectionsVisible ? '1' : '0';
        }

        function toggleFullscreen() {
            const elem = document.documentElement;
            
            if (!document.fullscreenElement) {
                if (elem.requestFullscreen) {
                    elem.requestFullscreen();
                } else if (elem.mozRequestFullScreen) {
                    elem.mozRequestFullScreen();
                } else if (elem.webkitRequestFullscreen) {
                    elem.webkitRequestFullscreen();
                } else if (elem.msRequestFullscreen) {
                    elem.msRequestFullscreen();
                }
            } else {
                if (document.exitFullscreen) {
                    document.exitFullscreen();
                } else if (document.mozCancelFullScreen) {
                    document.mozCancelFullScreen();
                } else if (document.webkitExitFullscreen) {
                    document.webkitExitFullscreen();
                } else if (document.msExitFullscreen) {
                    document.msExitFullscreen();
                }
            }
        }

        function resetZoom() {
            const universe = document.getElementById('universe');
            universe.style.transform = 'scale(1)';
            universe.style.transformOrigin = 'center center';
        }

        // ==== INICIALIZAR ====
        document.addEventListener('DOMContentLoaded', () => {
            createMap();
            
            // Mover tooltip con el mouse
            document.addEventListener('mousemove', (e) => {
                if (tooltip.classList.contains('active')) {
                    tooltip.style.left = `${e.clientX + 20}px`;
                    tooltip.style.top = `${e.clientY + 20}px`;
                }
            });
            
            // Zoom con scroll
            const universe = document.getElementById('universe');
            let scale = 1;
            
            universe.addEventListener('wheel', (e) => {
                e.preventDefault();
                
                if (e.ctrlKey) {
                    scale += e.deltaY * -0.01;
                    scale = Math.min(Math.max(0.5, scale), 3);
                    
                    universe.style.transform = `scale(${scale})`;
                    universe.style.transformOrigin = `${e.clientX / window.innerWidth * 100}% ${e.clientY / window.innerHeight * 100}%`;
                }
            });
        });

        // Salir de pantalla completa con Escape
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape' && document.fullscreenElement) {
                toggleFullscreen();
            }
        });
    </script>
</body>
</html>