<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&display=swap">
<link rel="stylesheet" href="../stylesheets/mapa-galaxia.css">

<style>
/* ==== ESTO OCULTA "CONCEPTUAL" Y ELEMENTOS DE MKDOCS ==== */
.md-header, .md-tabs, .md-sidebar, .md-nav__title, 
h1:first-of-type, .md-typeset h1,
.md-footer, .md-search, .md-logo {
    display: none !important;
    visibility: hidden !important;
    height: 0 !important;
    margin: 0 !important;
    padding: 0 !important;
    font-size: 0 !important;
    line-height: 0 !important;
}

body {
    margin-top: 0 !important;
    padding-top: 0 !important;
    overflow-x: hidden !important;
}

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
    z-index: 1000;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --pigeons-color: #3498db;
    --microorganisms-color: #9b59b6;
    --pollution-color: #e74c3c;
    --ecology-color: #2ecc71;
    --human-color: #f39c12;
    --connection-color: #1abc9c;
    --stress-color: #e67e22;
    --injustice-color: #c0392b;
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
    min-height: 100vh;
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

/* ==== CONTENEDOR PRINCIPAL ==== */
.main-container {
    flex: 1;
    position: relative;
    overflow: hidden;
    width: 100%;
    height: calc(100vh - 80px);
}

/* Fondo cósmico con estrellas */
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

/* Viewport para navegación */
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
    width: 4000px;
    height: 4000px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0.35);
    transform-origin: center center;
    transition: transform 0.1s ease;
    will-change: transform;
}

/* Canvas para conexiones radiales */
#galaxy-canvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
}

/* Nodo central principal */
.central-node {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 400px;
    height: 400px;
    border-radius: 50%;
    background: radial-gradient(circle, 
        rgba(52, 152, 219, 0.9) 0%, 
        rgba(155, 89, 182, 0.7) 50%,
        transparent 100%);
    box-shadow: 
        0 0 100px rgba(52, 152, 219, 0.6),
        0 0 150px rgba(155, 89, 182, 0.4);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    z-index: 10;
    transition: all 0.3s ease;
    border: 3px solid rgba(255, 255, 255, 0.3);
}

.central-node:hover {
    transform: translate(-50%, -50%) scale(1.15);
    box-shadow: 
        0 0 150px rgba(52, 152, 219, 0.8),
        0 0 200px rgba(155, 89, 182, 0.6);
}

.central-node-content {
    text-align: center;
    padding: 40px;
    width: 100%;
}

.central-node-title {
    font-weight: 800;
    font-size: 2.2rem;
    text-transform: uppercase;
    letter-spacing: 1.8px;
    margin-bottom: 15px;
    color: #ffffff;
    text-shadow: 0 2px 15px rgba(0, 0, 0, 0.9);
    line-height: 1.2;
}

.central-node-subtitle {
    font-weight: 400;
    font-size: 1.1rem;
    color: rgba(255, 255, 255, 0.85);
    letter-spacing: 1.2px;
}

/* Contenedor de nodos orbitales */
.orbit {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 50%;
    border: 1px solid rgba(255, 255, 255, 0.08);
}

/* Nodos orbitales */
.node {
    position: absolute;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s ease;
    z-index: 5;
    overflow: hidden;
    padding: 20px;
    text-align: center;
    border: 2px solid rgba(255, 255, 255, 0.1);
}

.node-icon {
    font-size: 2.2rem;
    margin-bottom: 12px;
    opacity: 0.95;
    filter: drop-shadow(0 2px 4px rgba(0,0,0,0.3));
}

.node-title {
    font-weight: 700;
    font-size: 1rem;
    text-transform: uppercase;
    letter-spacing: 0.9px;
    color: #ffffff;
    text-shadow: 0 1px 4px rgba(0, 0, 0, 0.8);
    line-height: 1.3;
    width: 100%;
    word-wrap: break-word;
}

.node-subtitle {
    font-size: 0.75rem;
    color: rgba(255, 255, 255, 0.75);
    margin-top: 8px;
    font-weight: 400;
}

/* Colores de nodos por categoría */
.pigeons-node {
    background: radial-gradient(circle, 
        var(--pigeons-color) 0%, 
        rgba(52, 152, 219, 0.7) 60%,
        transparent 100%);
    box-shadow: 
        0 0 50px rgba(52, 152, 219, 0.7),
        inset 0 0 30px rgba(255, 255, 255, 0.1);
}

.microorganisms-node {
    background: radial-gradient(circle, 
        var(--microorganisms-color) 0%, 
        rgba(155, 89, 182, 0.7) 60%,
        transparent 100%);
    box-shadow: 
        0 0 50px rgba(155, 89, 182, 0.7),
        inset 0 0 30px rgba(255, 255, 255, 0.1);
}

.pollution-node {
    background: radial-gradient(circle, 
        var(--pollution-color) 0%, 
        rgba(231, 76, 60, 0.7) 60%,
        transparent 100%);
    box-shadow: 
        0 0 50px rgba(231, 76, 60, 0.7),
        inset 0 0 30px rgba(255, 255, 255, 0.1);
}

.ecology-node {
    background: radial-gradient(circle, 
        var(--ecology-color) 0%, 
        rgba(46, 204, 113, 0.7) 60%,
        transparent 100%);
    box-shadow: 
        0 0 50px rgba(46, 204, 113, 0.7),
        inset 0 0 30px rgba(255, 255, 255, 0.1);
}

.human-node {
    background: radial-gradient(circle, 
        var(--human-color) 0%, 
        rgba(243, 156, 18, 0.7) 60%,
        transparent 100%);
    box-shadow: 
        0 0 50px rgba(243, 156, 18, 0.7),
        inset 0 0 30px rgba(255, 255, 255, 0.1);
}

.connection-node {
    background: radial-gradient(circle, 
        var(--connection-color) 0%, 
        rgba(26, 188, 156, 0.7) 60%,
        transparent 100%);
    box-shadow: 
        0 0 50px rgba(26, 188, 156, 0.7),
        inset 0 0 30px rgba(255, 255, 255, 0.1);
}

.injustice-node {
    background: radial-gradient(circle, 
        var(--injustice-color) 0%, 
        rgba(192, 57, 43, 0.7) 60%,
        transparent 100%);
    box-shadow: 
        0 0 50px rgba(192, 57, 43, 0.7),
        inset 0 0 30px rgba(255, 255, 255, 0.1);
}

.stress-node {
    background: radial-gradient(circle, 
        var(--stress-color) 0%, 
        rgba(230, 126, 34, 0.7) 60%,
        transparent 100%);
    box-shadow: 
        0 0 50px rgba(230, 126, 34, 0.7),
        inset 0 0 30px rgba(255, 255, 255, 0.1);
}

/* Efectos hover en nodos */
.node:hover {
    transform: scale(1.25) translate(-50%, -50%);
    z-index: 20;
    box-shadow: 
        0 0 80px rgba(255, 255, 255, 0.4),
        inset 0 0 40px rgba(255, 255, 255, 0.15);
    border-color: rgba(255, 255, 255, 0.4);
}

/* Panel de contenido mejorado */
.content-panel {
    position: fixed;
    top: 100px;
    right: 20px;
    width: 500px;
    max-height: 80vh;
    overflow-y: auto;
    background: rgba(10, 14, 23, 0.98);
    backdrop-filter: blur(20px);
    border-radius: 15px;
    padding: 35px;
    box-shadow: 
        0 25px 60px rgba(0, 0, 0, 0.8),
        inset 0 1px 0 rgba(255, 255, 255, 0.1);
    border: 1px solid rgba(255, 255, 255, 0.15);
    z-index: 1000;
    display: none;
    transition: all 0.4s ease;
}

.content-panel.active {
    display: block;
    animation: fadeIn 0.4s ease;
}

@keyframes fadeIn {
    from { 
        opacity: 0; 
        transform: translateY(25px) scale(0.95); 
    }
    to { 
        opacity: 1; 
        transform: translateY(0) scale(1); 
    }
}

.panel-category {
    display: inline-block;
    font-size: 0.8rem;
    padding: 8px 20px;
    border-radius: 25px;
    margin-bottom: 25px;
    font-weight: 800;
    color: #000000;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.panel-title {
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: 25px;
    color: #ffffff;
    line-height: 1.3;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.panel-text {
    font-size: 1.1rem;
    line-height: 1.8;
    color: var(--text-muted);
    margin-bottom: 30px;
}

.panel-list {
    margin: 20px 0;
    padding-left: 20px;
}

.panel-list-item {
    font-size: 1rem;
    color: var(--text-muted);
    margin-bottom: 10px;
    line-height: 1.6;
    position: relative;
}

.panel-list-item:before {
    content: "•";
    color: currentColor;
    position: absolute;
    left: -15px;
}

.panel-key-concept {
    background: rgba(255, 255, 255, 0.05);
    border-left: 4px solid;
    padding: 20px;
    margin: 25px 0;
    border-radius: 0 8px 8px 0;
}

.panel-key-concept-title {
    font-size: 0.9rem;
    font-weight: 700;
    margin-bottom: 12px;
    text-transform: uppercase;
    letter-spacing: 0.8px;
    color: #ffffff;
}

.panel-close {
    position: absolute;
    top: 20px;
    right: 20px;
    background: rgba(255, 255, 255, 0.1);
    border: none;
    color: var(--text-muted);
    font-size: 1.8rem;
    cursor: pointer;
    transition: all 0.3s;
    width: 45px;
    height: 45px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1001;
}

.panel-close:hover {
    background: rgba(255, 255, 255, 0.2);
    color: var(--text-light);
    transform: rotate(90deg);
}

/* Leyenda mejorada */
.legend {
    position: fixed;
    bottom: 20px;
    left: 20px;
    background: rgba(10, 14, 23, 0.92);
    backdrop-filter: blur(12px);
    padding: 25px;
    border-radius: 12px;
    border: 1px solid rgba(255, 255, 255, 0.12);
    z-index: 1000;
    max-width: 320px;
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
}

.legend-title {
    font-size: 1rem;
    font-weight: 800;
    margin-bottom: 20px;
    color: #ffffff;
    text-transform: uppercase;
    letter-spacing: 1.2px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    padding-bottom: 10px;
}

.legend-items {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
}

.legend-item {
    display: flex;
    align-items: center;
    gap: 12px;
}

.legend-color {
    width: 16px;
    height: 16px;
    border-radius: 50%;
    flex-shrink: 0;
    box-shadow: 0 0 8px currentColor;
}

.legend-label {
    font-size: 0.85rem;
    color: rgba(255, 255, 255, 0.85);
    line-height: 1.3;
}

/* Instrucciones */
.instructions {
    position: fixed;
    bottom: 20px;
    right: 20px;
    text-align: right;
    font-size: 0.85rem;
    color: rgba(255, 255, 255, 0.5);
    z-index: 1000;
    background: rgba(10, 14, 23, 0.3);
    padding: 12px 18px;
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.05);
    max-width: 280px;
    backdrop-filter: blur(5px);
    line-height: 1.5;
}

/* Responsive */
@media (max-width: 1200px) {
    #galaxy {
        width: 3500px;
        height: 3500px;
    }
    
    .central-node {
        width: 350px;
        height: 350px;
    }
    
    .node {
        width: 180px;
        height: 180px;
    }
    
    .content-panel {
        width: 450px;
    }
    
    .legend {
        max-width: 280px;
    }
}

@media (max-width: 900px) {
    #galaxy {
        width: 3000px;
        height: 3000px;
    }
    
    .central-node {
        width: 300px;
        height: 300px;
    }
    
    .node {
        width: 160px;
        height: 160px;
    }
    
    .content-panel {
        width: calc(100% - 40px);
        max-width: 400px;
        top: 90px;
    }
    
    .legend {
        display: none;
    }
    
    .custom-header-menu {
        gap: 20px;
    }
    
    .legend-items {
        grid-template-columns: 1fr;
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
        padding: 25px;
    }
    
    .central-node {
        width: 250px;
        height: 250px;
    }
    
    .node {
        width: 140px;
        height: 140px;
    }
    
    .central-node-title {
        font-size: 1.8rem;
    }
    
    .node-title {
        font-size: 0.9rem;
    }
    
    .instructions {
        display: none;
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

<!-- CONTENEDOR PRINCIPAL -->
<div class="main-container">
    <div id="stars"></div>
    
    <!-- Viewport para navegación -->
    <div class="viewport" id="viewport">
        <div id="galaxy">
            <canvas id="galaxy-canvas"></canvas>
            
            <!-- Nodo central -->
            <div class="central-node" id="centralNode">
                <div class="central-node-content">
                    <div class="central-node-title">INFRASTRUCTURE OF URBAN NON-HUMAN LIFE</div>
                    <div class="central-node-subtitle">Pigeons & Urban Microorganisms</div>
                </div>
            </div>
            
            <!-- Nodos serán generados por JavaScript -->
        </div>
    </div>
</div>

<!-- Panel de contenido -->
<div class="content-panel" id="contentPanel">
    <button class="panel-close" id="closePanel">×</button>
    <div class="panel-category" id="panelCategory">Core Framework</div>
    <h2 class="panel-title" id="panelTitle">INFRASTRUCTURE OF URBAN NON-HUMAN LIFE</h2>
    <p class="panel-text" id="panelText">A radial map exploring how urban pigeons and microorganisms experience the city through environmental pressures, biological responses, and human relationships. This framework connects visible and invisible life to reveal multispecies injustice.</p>
    
    <div class="panel-key-concept" id="panelConcept">
        <div class="panel-key-concept-title" id="conceptTitle">CORE DICHOTOMY</div>
        <p id="conceptText">One species is visible but rejected (pigeons), one is invisible but essential (microorganisms). Together they expose how cities prioritize human aesthetics over ecological function.</p>
    </div>
    
    <div class="panel-list" id="panelList">
        <!-- List items will be populated by JavaScript -->
    </div>
</div>

<!-- Leyenda de colores -->
<div class="legend">
    <div class="legend-title">MAP LEGEND</div>
    <div class="legend-items">
        <div class="legend-item">
            <div class="legend-color" style="background-color: #3498db;"></div>
            <div class="legend-label">Urban Pigeons</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #9b59b6;"></div>
            <div class="legend-label">Microorganisms</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #e74c3c;"></div>
            <div class="legend-label">Pollution</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #2ecc71;"></div>
            <div class="legend-label">Ecology</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #f39c12;"></div>
            <div class="legend-label">Human Relations</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #c0392b;"></div>
            <div class="legend-label">Injustice</div>
        </div>
    </div>
</div>

<!-- Instrucciones -->
<div class="instructions">
    Click on any node to explore details<br>
    Mouse wheel to zoom in/out<br>
    Drag to navigate the map<br>
    Double-click to reset view
</div>

<script>
    // Datos para el mapa radial basado en la nueva información
    const nodesData = {
        central: {
            id: "central",
            title: "INFRASTRUCTURE OF URBAN NON-HUMAN LIFE",
            text: "This framework maps how urban pigeons (visible but rejected) and microorganisms (invisible but essential) experience the city through shared environmental pressures. Both species reveal how cities prioritize human aesthetics over ecological function, exposing multispecies injustice across scales.",
            category: "Core Framework",
            color: "linear-gradient(135deg, var(--pigeons-color), var(--microorganisms-color))",
            concept: {
                title: "VISIBLE vs INVISIBLE",
                text: "Pigeons represent life that's visible but politically excluded. Microorganisms represent life that's invisible but ecologically essential. Together, they show how cities manage non-human life through different forms of violence."
            },
            keyPoints: [
                "Pollution affects both microscopic and visible scales",
                "Human design ignores ecological functions",
                "Aesthetic control overrides biological needs",
                "Slow violence through environmental degradation"
            ]
        },
        
        // PRIMER ANILLO: ESPECIES
        species: [
            {
                id: "pigeons-overview",
                title: "URBAN PIGEONS",
                subtitle: "Visible Exclusion",
                text: "Columba livia – permanent urban residents descended from cliff-dwelling rock doves. Buildings replicate their natural nesting habitats. Highly adapted to human-made environments but systematically excluded through hostile design and social stigma.",
                category: "Species Overview",
                icon: "🕊️",
                keyPoints: [
                    "Descendants of cliff-dwelling rock doves",
                    "Buildings replicate natural nesting habitats",
                    "Permanent urban residents, not transient wildlife",
                    "Highly adapted to human-made environments"
                ]
            },
            {
                id: "microorganisms-overview",
                title: "URBAN MICROORGANISMS",
                subtitle: "Invisible Infrastructure",
                text: "Bacteria, fungi, archaea inhabiting air, soil, water, surfaces, plants, and buildings. Form the urban microbiome – constantly interacting with pollution and human activity. Invisible but foundational to urban ecosystems.",
                category: "Species Overview",
                icon: "🦠",
                keyPoints: [
                    "Microbial life in air, soil, water, surfaces",
                    "Form the urban microbiome",
                    "Constantly interacting with pollution",
                    "Invisible but ecologically essential"
                ]
            }
        ],
        
        // SEGUNDO ANILLO: IMPORTANCIA ECOLÓGICA
        ecology: [
            {
                id: "pigeon-ecology",
                title: "PIGEON ECOLOGY",
                subtitle: "Urban Ecosystem Roles",
                text: "Pigeons provide critical ecosystem services: seed dispersal in fragmented green spaces, nutrient cycling through droppings, contribution to urban food webs as prey for raptors, and serving as bioindicators of environmental contamination.",
                category: "Ecological Importance",
                icon: "🌿",
                keyPoints: [
                    "Seed dispersal in fragmented urban green spaces",
                    "Nutrient cycling through droppings",
                    "Contribution to urban food webs (prey for raptors)",
                    "Bioindicators of environmental contamination"
                ]
            },
            {
                id: "microbe-ecology",
                title: "MICROBIAL SERVICES",
                subtitle: "Ecosystem Functions",
                text: "Microorganisms sustain urban ecosystems through: nutrient cycling (carbon, nitrogen, phosphorus), soil regeneration and stabilization, decomposition of organic matter, biodegradation of pollutants, and regulation of plant health.",
                category: "Ecological Importance",
                icon: "⚗️",
                keyPoints: [
                    "Nutrient cycling (carbon, nitrogen, phosphorus)",
                    "Soil regeneration and stabilization",
                    "Decomposition of organic matter",
                    "Biodegradation of pollutants",
                    "Regulation of plant health"
                ]
            }
        ],
        
        // TERCER ANILLO: PRESIONES AMBIENTALES
        pressures: [
            {
                id: "air-pollution",
                title: "AIR POLLUTION",
                subtitle: "Shared Stressor",
                text: "Particulate matter (PM2.5, PM10) affects both species: pigeons inhale toxic gases and accumulate heavy metals; microorganisms travel on particles and face chemical damage. Both experience respiratory stress and cellular damage.",
                category: "Environmental Pressure",
                icon: "☁️",
                keyPoints: [
                    "Pigeons: Inhalation of NO₂, SO₂, O₃",
                    "Pigeons: Accumulation of lead, cadmium, mercury",
                    "Microbes: Particles as transport medium",
                    "Microbes: Chemical damage to cells"
                ]
            },
            {
                id: "noise-pollution",
                title: "NOISE POLLUTION",
                subtitle: "Acoustic Stress",
                text: "Chronic traffic and construction noise disrupts pigeon communication and increases stress hormones. While microorganisms aren't directly affected by sound, the urban noise ecosystem alters predator-prey relationships and habitat quality.",
                category: "Environmental Pressure",
                icon: "🔊",
                keyPoints: [
                    "Disruption of pigeon acoustic communication",
                    "Increased stress hormone levels",
                    "Altered mating and nesting behavior",
                    "Indirect effects through ecosystem changes"
                ]
            },
            {
                id: "hostile-design",
                title: "HOSTILE ARCHITECTURE",
                subtitle: "Designed Exclusion",
                text: "Anti-roosting spikes, nets, and repellents deny pigeons resting and nesting spaces. Constant displacement causes chronic stress and reduces reproductive success. Microorganisms face sterilization and surface treatments that eliminate beneficial communities.",
                category: "Environmental Pressure",
                icon: "🚫",
                keyPoints: [
                    "Anti-roosting spikes, nets, repellents",
                    "Removal of nesting spaces",
                    "Constant displacement and stress",
                    "Energy spent avoiding exclusion"
                ]
            },
            {
                id: "temperature-stress",
                title: "HEAT ISLANDS",
                subtitle: "Thermal Pressure",
                text: "Urban heat islands increase temperatures, reducing microbial diversity and favoring heat-tolerant species. Pigeons experience thermal stress, altered metabolism, and reduced access to water sources in overheated urban areas.",
                category: "Environmental Pressure",
                icon: "🌡️",
                keyPoints: [
                    "Increased temperatures reduce microbial diversity",
                    "Favors thermotolerant microbial species",
                    "Pigeon thermal stress and altered metabolism",
                    "Reduced access to water in heat islands"
                ]
            }
        ],
        
        // CUARTO ANILLO: RESPUESTAS BIOLÓGICAS
        responses: [
            {
                id: "biological-stress",
                title: "BIOLOGICAL STRESS",
                subtitle: "Internal Changes",
                text: "Both species show internal adaptations to urban stress: pigeons develop altered gut microbiomes and elevated stress markers; microorganisms shift community composition and develop pollution resistance.",
                category: "Biological Response",
                icon: "🧬",
                keyPoints: [
                    "Pigeons: Altered gut microbiota",
                    "Pigeons: Elevated physiological stress markers",
                    "Microbes: Shift in community composition",
                    "Microbes: Increase in pollution-resistant strains"
                ]
            },
            {
                id: "bioindicators",
                title: "BIOINDICATORS",
                subtitle: "Environmental Sensors",
                text: "Both species serve as living sensors of urban health: pigeons show heavy metal accumulation and disease patterns; microorganisms reveal pollution levels through community changes before human symptoms appear.",
                category: "Biological Response",
                icon: "📊",
                keyPoints: [
                    "Pigeons reflect air, soil, and food pollution",
                    "Microbial composition indicates environmental stress",
                    "Both show damage before human symptoms",
                    "Early warning systems for urban health"
                ]
            }
        ],
        
        // QUINTO ANILLO: RELACIONES HUMANAS
        human: [
            {
                id: "human-perception",
                title: "HUMAN PERCEPTION",
                subtitle: "Cultural Framing",
                text: "Pigeons are perceived as pests or contaminants; microorganisms are mostly ignored or feared. Both are managed through control rather than coexistence, revealing human prioritization of aesthetics over ecology.",
                category: "Human Relations",
                icon: "👁️",
                keyPoints: [
                    "Pigeons seen as pests or contaminants",
                    "Microorganisms ignored or feared as threats",
                    "Managed through exclusion/control",
                    "Aesthetics prioritized over ecology"
                ]
            },
            {
                id: "political-status",
                title: "POLITICAL STATUS",
                subtitle: "Urban Citizenship",
                text: "Pigeons represent life that belongs biologically but not politically – tolerated only when invisible. Microorganisms represent essential infrastructure that's completely excluded from urban planning and decision-making.",
                category: "Human Relations",
                icon: "🏛️",
                keyPoints: [
                    "Life that belongs biologically but not politically",
                    "Species tolerated only when invisible",
                    "Violence normalized through 'clean city' policies",
                    "Essential infrastructure excluded from planning"
                ]
            }
        ],
        
        // SEXTO ANILLO: CONCEPTOS CENTRALES
        concepts: [
            {
                id: "multispecies-injustice",
                title: "MULTISPECIES INJUSTICE",
                subtitle: "Structural Violence",
                text: "The systematic exclusion of non-human life through urban design represents a form of structural violence. This injustice crosses scales from microscopic (microorganisms) to visible (pigeons), revealing how cities are built against life.",
                category: "Core Concept",
                icon: "⚖️",
                keyPoints: [
                    "Systematic exclusion through design",
                    "Structural violence against non-human life",
                    "Crosses microscopic to visible scales",
                    "Cities built against ecological function"
                ]
            },
            {
                id: "slow-violence",
                title: "SLOW VIOLENCE",
                subtitle: "Gradual Damage",
                text: "Pollution, habitat loss, and environmental degradation constitute slow violence – harm that accumulates gradually and invisibly. Both pigeons and microorganisms experience this through chronic exposure to urban stressors.",
                category: "Core Concept",
                icon: "⏳",
                keyPoints: [
                    "Harm that accumulates gradually",
                    "Often invisible until systems collapse",
                    "Chronic exposure to urban stressors",
                    "Delayed consequences for ecosystems"
                ]
            },
            {
                id: "design-intervention",
                title: "DESIGN INTERVENTION",
                subtitle: "Where to Act",
                text: "Potential intervention points: creating pigeon-friendly architecture, designing microbial habitat corridors, developing pollution translation tools, or creating multispecies sensory interfaces that make invisible damage perceptible.",
                category: "Design Application",
                icon: "🎯",
                keyPoints: [
                    "Pigeon-friendly architecture",
                    "Microbial habitat corridors",
                    "Pollution translation tools",
                    "Multispecies sensory interfaces"
                ]
            }
        ]
    };

    // Variables globales
    let canvas, ctx;
    let scale = 0.35;
    let offsetX = 0, offsetY = 0;
    let isDragging = false;
    let lastX = 0, lastY = 0;
    let galaxy = document.getElementById('galaxy');
    let viewport = document.getElementById('viewport');

    // Inicializar estrellas
    function initStars() {
        const starsContainer = document.getElementById('stars');
        starsContainer.innerHTML = '';
        
        for (let i = 0; i < 500; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            
            const size = Math.random() * 3 + 0.5;
            star.style.width = `${size}px`;
            star.style.height = `${size}px`;
            star.style.left = `${Math.random() * 100}%`;
            star.style.top = `${Math.random() * 100}%`;
            star.style.animationDelay = `${Math.random() * 8}s`;
            star.style.opacity = Math.random() * 0.4 + 0.1;
            star.style.animationDuration = `${Math.random() * 3 + 2}s`;
            
            starsContainer.appendChild(star);
        }
    }

    // Crear nodos orbitales organizados
    function createOrbitalNodes() {
        // Configuración de órbitas
        const orbits = [
            { radius: 500, nodes: nodesData.species, classPrefix: 'species' },
            { radius: 800, nodes: nodesData.ecology, classPrefix: 'ecology' },
            { radius: 1100, nodes: nodesData.pressures, classPrefix: 'pressures' },
            { radius: 1400, nodes: nodesData.responses, classPrefix: 'responses' },
            { radius: 1700, nodes: nodesData.human, classPrefix: 'human' },
            { radius: 2000, nodes: nodesData.concepts, classPrefix: 'concepts' }
        ];
        
        orbits.forEach((orbit, orbitIndex) => {
            orbit.nodes.forEach((nodeData, nodeIndex) => {
                const node = document.createElement('div');
                
                // Asignar clase según categoría
                if (nodeData.category.includes('Pigeon')) {
                    node.classList.add('node', 'pigeons-node');
                } else if (nodeData.category.includes('Micro')) {
                    node.classList.add('node', 'microorganisms-node');
                } else if (nodeData.category.includes('Pressure')) {
                    node.classList.add('node', 'pollution-node');
                } else if (nodeData.category.includes('Ecology')) {
                    node.classList.add('node', 'ecology-node');
                } else if (nodeData.category.includes('Human')) {
                    node.classList.add('node', 'human-node');
                } else if (nodeData.category.includes('Concept') && nodeData.title.includes('INJUSTICE')) {
                    node.classList.add('node', 'injustice-node');
                } else if (nodeData.category.includes('Concept') && nodeData.title.includes('VIOLENCE')) {
                    node.classList.add('node', 'stress-node');
                } else if (nodeData.category.includes('Design')) {
                    node.classList.add('node', 'connection-node');
                } else {
                    node.classList.add('node', 'ecology-node');
                }
                
                node.id = nodeData.id;
                node.dataset.title = nodeData.title;
                node.dataset.text = nodeData.text;
                node.dataset.category = nodeData.category;
                node.dataset.keyPoints = JSON.stringify(nodeData.keyPoints);
                
                // Posicionar en órbita
                const angle = (nodeIndex / orbit.nodes.length) * 2 * Math.PI;
                const x = orbit.radius * Math.cos(angle);
                const y = orbit.radius * Math.sin(angle);
                
                node.style.left = `calc(50% + ${x}px)`;
                node.style.top = `calc(50% + ${y}px)`;
                node.style.transform = 'translate(-50%, -50%)';
                
                // Contenido del nodo
                const iconElement = document.createElement('div');
                iconElement.classList.add('node-icon');
                iconElement.textContent = nodeData.icon || '●';
                
                const titleElement = document.createElement('div');
                titleElement.classList.add('node-title');
                titleElement.textContent = nodeData.title;
                
                const subtitleElement = document.createElement('div');
                subtitleElement.classList.add('node-subtitle');
                subtitleElement.textContent = nodeData.subtitle || '';
                
                node.appendChild(iconElement);
                node.appendChild(titleElement);
                if (nodeData.subtitle) {
                    node.appendChild(subtitleElement);
                }
                
                // Evento click
                node.addEventListener('click', (e) => {
                    e.stopPropagation();
                    showNodeContent(nodeData);
                });
                
                galaxy.appendChild(node);
            });
        });
        
        // Conectar nodo central
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
        const panelConcept = document.getElementById('panelConcept');
        const conceptTitle = document.getElementById('conceptTitle');
        const conceptText = document.getElementById('conceptText');
        const panelList = document.getElementById('panelList');
        
        // Actualizar contenido principal
        panelTitle.textContent = nodeData.title;
        panelText.textContent = nodeData.text;
        panelCategory.textContent = nodeData.category;
        
        // Establecer color según categoría
        let color = '';
        if (nodeData.category.includes('Pigeon') || nodeData.title.includes('PIGEON')) {
            color = 'var(--pigeons-color)';
        } else if (nodeData.category.includes('Micro') || nodeData.title.includes('MICRO')) {
            color = 'var(--microorganisms-color)';
        } else if (nodeData.category.includes('Pressure') || nodeData.title.includes('POLLUTION')) {
            color = 'var(--pollution-color)';
        } else if (nodeData.category.includes('Ecology')) {
            color = 'var(--ecology-color)';
        } else if (nodeData.category.includes('Human')) {
            color = 'var(--human-color)';
        } else if (nodeData.category.includes('Injustice')) {
            color = 'var(--injustice-color)';
        } else if (nodeData.category.includes('Design')) {
            color = 'var(--connection-color)';
        } else {
            color = 'var(--pigeons-color)';
        }
        
        panelCategory.style.backgroundColor = color;
        panelCategory.style.color = '#000000';
        
        // Actualizar concepto si existe
        if (nodeData.concept) {
            panelConcept.style.display = 'block';
            panelConcept.style.borderLeftColor = color;
            conceptTitle.textContent = nodeData.concept.title;
            conceptText.textContent = nodeData.concept.text;
        } else {
            panelConcept.style.display = 'none';
        }
        
        // Actualizar lista de puntos clave
        panelList.innerHTML = '';
        if (nodeData.keyPoints && nodeData.keyPoints.length > 0) {
            nodeData.keyPoints.forEach(point => {
                const listItem = document.createElement('div');
                listItem.classList.add('panel-list-item');
                listItem.textContent = point;
                panelList.appendChild(listItem);
            });
        }
        
        // Mostrar panel con animación
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

    // Dibujar conexiones radiales complejas
    function drawConnections() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        
        const centerX = canvas.width / 2;
        const centerY = canvas.height / 2;
        
        // Conectar todos los nodos al centro
        const allNodes = document.querySelectorAll('.node:not(.central-node)');
        
        allNodes.forEach(node => {
            const rect = node.getBoundingClientRect();
            const galaxyRect = galaxy.getBoundingClientRect();
            
            const nodeX = (rect.left + rect.width/2 - galaxyRect.left) / scale;
            const nodeY = (rect.top + rect.height/2 - galaxyRect.top) / scale;
            
            // Determinar color y estilo de conexión
            let color = 'rgba(255, 255, 255, 0.08)';
            let lineWidth = 1;
            
            if (node.classList.contains('pigeons-node')) {
                color = 'rgba(52, 152, 219, 0.2)';
                lineWidth = 1.2;
            } else if (node.classList.contains('microorganisms-node')) {
                color = 'rgba(155, 89, 182, 0.2)';
                lineWidth = 1.2;
            } else if (node.classList.contains('pollution-node')) {
                color = 'rgba(231, 76, 60, 0.15)';
                lineWidth = 1;
            } else if (node.classList.contains('ecology-node')) {
                color = 'rgba(46, 204, 113, 0.15)';
                lineWidth = 1;
            } else if (node.classList.contains('human-node')) {
                color = 'rgba(243, 156, 18, 0.15)';
                lineWidth = 1;
            }
            
            drawConnectionLine(centerX, centerY, nodeX, nodeY, color, lineWidth);
        });
        
        // Conectar nodos relacionados entre sí
        drawSpecialConnections();
    }
    
    function drawSpecialConnections() {
        const centerX = canvas.width / 2;
        const centerY = canvas.height / 2;
        
        // Conexiones especiales entre nodos relacionados
        const specialConnections = [
            { from: 'pigeons-overview', to: 'pigeon-ecology', color: 'rgba(52, 152, 219, 0.3)', width: 1.5 },
            { from: 'microorganisms-overview', to: 'microbe-ecology', color: 'rgba(155, 89, 182, 0.3)', width: 1.5 },
            { from: 'air-pollution', to: 'biological-stress', color: 'rgba(231, 76, 60, 0.25)', width: 1.3 },
            { from: 'human-perception', to: 'political-status', color: 'rgba(243, 156, 18, 0.25)', width: 1.3 },
            { from: 'multispecies-injustice', to: 'slow-violence', color: 'rgba(192, 57, 43, 0.25)', width: 1.8 }
        ];
        
        specialConnections.forEach(conn => {
            const fromNode = document.getElementById(conn.from);
            const toNode = document.getElementById(conn.to);
            
            if (fromNode && toNode) {
                const galaxyRect = galaxy.getBoundingClientRect();
                
                const fromRect = fromNode.getBoundingClientRect();
                const fromX = (fromRect.left + fromRect.width/2 - galaxyRect.left) / scale;
                const fromY = (fromRect.top + fromRect.height/2 - galaxyRect.top) / scale;
                
                const toRect = toNode.getBoundingClientRect();
                const toX = (toRect.left + toRect.width/2 - galaxyRect.left) / scale;
                const toY = (toRect.top + toRect.height/2 - galaxyRect.top) / scale;
                
                // Dibujar línea curva entre nodos
                drawCurvedConnection(fromX, fromY, toX, toY, conn.color, conn.width);
            }
        });
    }
    
    function drawConnectionLine(x1, y1, x2, y2, color, width) {
        ctx.beginPath();
        ctx.moveTo(x1, y1);
        ctx.lineTo(x2, y2);
        ctx.strokeStyle = color;
        ctx.lineWidth = width;
        ctx.lineCap = 'round';
        ctx.stroke();
    }
    
    function drawCurvedConnection(x1, y1, x2, y2, color, width) {
        const centerX = canvas.width / 2;
        const centerY = canvas.height / 2;
        
        const midX = (x1 + x2 + centerX) / 3;
        const midY = (y1 + y2 + centerY) / 3;
        
        ctx.beginPath();
        ctx.moveTo(x1, y1);
        ctx.quadraticCurveTo(midX, midY, x2, y2);
        ctx.strokeStyle = color;
        ctx.lineWidth = width;
        ctx.lineCap = 'round';
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
        
        const zoomFactor = 0.07;
        const oldScale = scale;
        
        if (e.deltaY < 0) {
            scale = Math.min(scale + zoomFactor, 1);
        } else {
            scale = Math.max(scale - zoomFactor, 0.25);
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
        if (e.target === viewport || e.target.classList.contains('orbit') || 
            e.target.classList.contains('node') || e.target.closest('.node')) {
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
        scale = 0.35;
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
        
        // Mostrar contenido central después de un breve retraso
        setTimeout(() => {
            showNodeContent(nodesData.central);
        }, 800);
        
        // Event listeners
        viewport.addEventListener('wheel', handleWheel);
        viewport.addEventListener('mousedown', handleMouseDown);
        document.addEventListener('mousemove', handleMouseMove);
        document.addEventListener('mouseup', handleMouseUp);
        viewport.addEventListener('dblclick', resetView);
        
        // Cerrar panel al hacer clic fuera
        document.addEventListener('click', (e) => {
            const panel = document.getElementById('contentPanel');
            const isNode = e.target.closest('.node') || e.target.closest('.central-node');
            const isCloseBtn = e.target.closest('.panel-close');
            const isPanel = e.target.closest('.content-panel');
            
            if (!isNode && !isCloseBtn && !isPanel && panel.classList.contains('active')) {
                panel.classList.remove('active');
            }
        });
        
        // Prevenir propagación en elementos del panel
        document.getElementById('contentPanel').addEventListener('mousedown', (e) => {
            e.stopPropagation();
        });
    });
</script>