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
    --microorganisms-color: #6a11cb;
    --pigeons-color: #00c6ff;
    --pollution-color: #ff416c;
    --temperature-color: #ff9966;
    --chemical-color: #ff5e62;
    --biology-color: #00d8a7;
    --ecology-color: #36d1dc;
    --human-color: #ff8a00;
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
    width: 3500px;
    height: 3500px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0.4);
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
    width: 350px;
    height: 350px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(106, 17, 203, 0.9) 0%, rgba(106, 17, 203, 0.4) 70%, transparent 100%);
    box-shadow: 0 0 100px rgba(106, 17, 203, 0.8);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    z-index: 10;
    transition: all 0.3s ease;
    border: 3px solid rgba(255, 255, 255, 0.2);
}

.central-node:hover {
    transform: translate(-50%, -50%) scale(1.1);
    box-shadow: 0 0 150px rgba(106, 17, 203, 1);
}

.central-node-content {
    text-align: center;
    padding: 30px;
    width: 100%;
}

.central-node-title {
    font-weight: 800;
    font-size: 2rem;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    margin-bottom: 10px;
    color: #ffffff;
    text-shadow: 0 2px 10px rgba(0, 0, 0, 0.8);
    line-height: 1.2;
}

.central-node-subtitle {
    font-weight: 400;
    font-size: 1rem;
    color: rgba(255, 255, 255, 0.8);
    letter-spacing: 1px;
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

/* Nodos orbitales */
.node {
    position: absolute;
    width: 180px;
    height: 180px;
    border-radius: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s ease;
    z-index: 5;
    overflow: hidden;
    padding: 15px;
    text-align: center;
    border: 2px solid rgba(255, 255, 255, 0.1);
}

.node-icon {
    font-size: 2rem;
    margin-bottom: 10px;
    opacity: 0.9;
}

.node-title {
    font-weight: 700;
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 0.8px;
    color: #ffffff;
    text-shadow: 0 1px 3px rgba(0, 0, 0, 0.8);
    line-height: 1.3;
    width: 100%;
    word-wrap: break-word;
}

.node-subtitle {
    font-size: 0.7rem;
    color: rgba(255, 255, 255, 0.7);
    margin-top: 5px;
    font-weight: 400;
}

/* Colores de nodos por categoría */
.microorganisms-node {
    background: radial-gradient(circle, var(--microorganisms-color) 0%, rgba(106, 17, 203, 0.7) 70%, transparent 100%);
    box-shadow: 0 0 40px rgba(106, 17, 203, 0.8);
}

.pigeons-node {
    background: radial-gradient(circle, var(--pigeons-color) 0%, rgba(0, 198, 255, 0.7) 70%, transparent 100%);
    box-shadow: 0 0 40px rgba(0, 198, 255, 0.8);
}

.pollution-node {
    background: radial-gradient(circle, var(--pollution-color) 0%, rgba(255, 65, 108, 0.7) 70%, transparent 100%);
    box-shadow: 0 0 40px rgba(255, 65, 108, 0.8);
}

.temperature-node {
    background: radial-gradient(circle, var(--temperature-color) 0%, rgba(255, 153, 102, 0.7) 70%, transparent 100%);
    box-shadow: 0 0 40px rgba(255, 153, 102, 0.8);
}

.chemical-node {
    background: radial-gradient(circle, var(--chemical-color) 0%, rgba(255, 94, 98, 0.7) 70%, transparent 100%);
    box-shadow: 0 0 40px rgba(255, 94, 98, 0.8);
}

.biology-node {
    background: radial-gradient(circle, var(--biology-color) 0%, rgba(0, 216, 167, 0.7) 70%, transparent 100%);
    box-shadow: 0 0 40px rgba(0, 216, 167, 0.8);
}

.ecology-node {
    background: radial-gradient(circle, var(--ecology-color) 0%, rgba(54, 209, 220, 0.7) 70%, transparent 100%);
    box-shadow: 0 0 40px rgba(54, 209, 220, 0.8);
}

.human-node {
    background: radial-gradient(circle, var(--human-color) 0%, rgba(255, 138, 0, 0.7) 70%, transparent 100%);
    box-shadow: 0 0 40px rgba(255, 138, 0, 0.8);
}

/* Efectos hover en nodos */
.node:hover {
    transform: scale(1.2) translate(-50%, -50%);
    z-index: 20;
    box-shadow: 0 0 60px rgba(255, 255, 255, 0.6);
    border-color: rgba(255, 255, 255, 0.3);
}

/* Panel de contenido mejorado */
.content-panel {
    position: fixed;
    top: 100px;
    right: 20px;
    width: 450px;
    max-height: 80vh;
    overflow-y: auto;
    background: rgba(10, 14, 23, 0.98);
    backdrop-filter: blur(20px);
    border-radius: 15px;
    padding: 30px;
    box-shadow: 0 20px 50px rgba(0, 0, 0, 0.7);
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
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}

.panel-category {
    display: inline-block;
    font-size: 0.85rem;
    padding: 6px 15px;
    border-radius: 20px;
    margin-bottom: 20px;
    font-weight: 700;
    color: #000000;
    text-transform: uppercase;
    letter-spacing: 0.8px;
}

.panel-title {
    font-size: 1.8rem;
    font-weight: 700;
    margin-bottom: 20px;
    color: #ffffff;
    line-height: 1.3;
}

.panel-text {
    font-size: 1.05rem;
    line-height: 1.7;
    color: var(--text-muted);
    margin-bottom: 25px;
}

.panel-references {
    background: rgba(255, 255, 255, 0.05);
    border-left: 3px solid;
    padding: 15px;
    margin: 20px 0;
    border-radius: 0 8px 8px 0;
}

.panel-references-title {
    font-size: 0.9rem;
    font-weight: 700;
    margin-bottom: 10px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.reference-item {
    font-size: 0.85rem;
    color: rgba(255, 255, 255, 0.7);
    margin-bottom: 8px;
    line-height: 1.4;
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
    z-index: 1001;
}

.panel-close:hover {
    background: rgba(255, 255, 255, 0.2);
    color: var(--text-light);
    transform: rotate(90deg);
}

/* Leyenda */
.legend {
    position: fixed;
    bottom: 20px;
    left: 20px;
    background: rgba(10, 14, 23, 0.9);
    backdrop-filter: blur(10px);
    padding: 20px;
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.1);
    z-index: 1000;
    max-width: 300px;
}

.legend-title {
    font-size: 1rem;
    font-weight: 700;
    margin-bottom: 15px;
    color: #ffffff;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.legend-items {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.legend-item {
    display: flex;
    align-items: center;
    gap: 10px;
}

.legend-color {
    width: 15px;
    height: 15px;
    border-radius: 50%;
}

.legend-label {
    font-size: 0.85rem;
    color: rgba(255, 255, 255, 0.8);
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
    padding: 10px 15px;
    border-radius: 8px;
    border: 1px solid rgba(255, 255, 255, 0.05);
    max-width: 250px;
    backdrop-filter: blur(5px);
}

/* Responsive */
@media (max-width: 1200px) {
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
        width: 400px;
    }
}

@media (max-width: 900px) {
    #galaxy {
        width: 2500px;
        height: 2500px;
    }
    
    .central-node {
        width: 250px;
        height: 250px;
    }
    
    .node {
        width: 140px;
        height: 140px;
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
        padding: 20px;
    }
    
    .central-node {
        width: 200px;
        height: 200px;
    }
    
    .node {
        width: 120px;
        height: 120px;
    }
    
    .central-node-title {
        font-size: 1.5rem;
    }
    
    .node-title {
        font-size: 0.8rem;
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
                    <div class="central-node-title">INFRASTRUCTURE OF NON-HUMAN URBAN LIFE</div>
                    <div class="central-node-subtitle">Urban Microorganisms & Urban Pigeons</div>
                </div>
            </div>
            
            <!-- Nodos serán generados por JavaScript -->
        </div>
    </div>
</div>

<!-- Panel de contenido -->
<div class="content-panel" id="contentPanel">
    <button class="panel-close" id="closePanel">×</button>
    <div class="panel-category" id="panelCategory">Scientific Background</div>
    <h2 class="panel-title" id="panelTitle">INFRASTRUCTURE OF NON-HUMAN URBAN LIFE</h2>
    <p class="panel-text" id="panelText">Mapping the invisible systems that support and constrain life in the city. How microorganisms and pigeons experience urban environments through different sensory worlds and biological responses to human-made pressures.</p>
    
    <div class="panel-references" id="panelReferences">
        <div class="panel-references-title">KEY REFERENCES</div>
        <div class="reference-item" id="reference1"></div>
        <div class="reference-item" id="reference2"></div>
        <div class="reference-item" id="reference3"></div>
    </div>
</div>

<!-- Leyenda de colores -->
<div class="legend">
    <div class="legend-title">LEGEND</div>
    <div class="legend-items">
        <div class="legend-item">
            <div class="legend-color" style="background-color: #6a11cb;"></div>
            <div class="legend-label">Urban Microorganisms</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #00c6ff;"></div>
            <div class="legend-label">Urban Pigeons</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #ff416c;"></div>
            <div class="legend-label">Pollution Pressures</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #00d8a7;"></div>
            <div class="legend-label">Biological Responses</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #36d1dc;"></div>
            <div class="legend-label">Ecological Roles</div>
        </div>
        <div class="legend-item">
            <div class="legend-color" style="background-color: #ff8a00;"></div>
            <div class="legend-label">Human Interaction</div>
        </div>
    </div>
</div>

<!-- Instrucciones -->
<div class="instructions">
    Click on any node to see details<br>
    Use mouse wheel to zoom<br>
    Drag to move the map<br>
    Double-click to reset view
</div>

<script>
    // Datos completos para la infraestructura
    const nodesData = {
        central: {
            id: "central",
            title: "INFRASTRUCTURE OF NON-HUMAN URBAN LIFE",
            text: "Urban Microorganisms & Urban Pigeons represent two poles of urban non-human life: one invisible but essential (microorganisms), one visible but excluded (pigeons). Both experience the city through environmental pressures shaped by human activity, with biological responses that reveal the hidden costs of urban living.",
            category: "Scientific Framework",
            color: "var(--microorganisms-color)",
            references: [
                "Nature Reviews Microbiology — Urban microbiome studies",
                "British Trust for Ornithology — Urban pigeon ecology",
                "Environmental Pollution — Multispecies urban impacts"
            ]
        },
        
        microorganisms: [
            {
                id: "micro1",
                title: "URBAN MICROORGANISMS",
                subtitle: "Invisible Infrastructure",
                text: "Bacteria, fungi, archaea, and microscopic eukaryotes living in air, soil, water, and surfaces. They form the urban microbiome—a dynamic ecological layer shaped by human activity, providing essential ecosystem services while being deeply affected by pollution.",
                category: "Urban Microorganisms",
                references: [
                    "Nature Reviews Microbiology",
                    "NIH Urban Microbiome Studies",
                    "Microbiome Journal"
                ]
            },
            {
                id: "micro2",
                title: "AIR POLLUTION",
                subtitle: "PM as Microbial Carrier",
                text: "Particulate Matter (PM1, PM2.5, PM10) acts as a carrier for microorganisms and toxic compounds. Pollutants alter microbial diversity and survival. Heavy metals bind to microbial cells, affecting metabolism and ecosystem functions.",
                category: "Environmental Pressure",
                references: [
                    "Nature Microbiology — 'Urban microbiomes are shaped by air pollution'",
                    "Atmospheric Environment Journal"
                ]
            },
            {
                id: "micro3",
                title: "TEMPERATURE",
                subtitle: "Heat Island Effects",
                text: "Higher urban temperatures select for heat-tolerant microbial species. Climate stress reduces microbial diversity and alters metabolic rates. Urban heat islands restructure microbial communities toward less diverse, more resilient strains.",
                category: "Environmental Pressure",
                references: [
                    "Environmental Microbiology Reports — 'Urban heat islands restructure microbial communities'"
                ]
            },
            {
                id: "micro4",
                title: "BIOLOGICAL RESPONSES",
                subtitle: "Internal Changes",
                text: "Shift in microbial community composition. Increase of pollution-resistant strains. Reduction in ecosystem-supporting species. Emergence of antimicrobial resistance. Changes in metabolic pathways affecting nutrient cycling.",
                category: "Biological Response",
                references: [
                    "NIH — Microbial adaptation studies",
                    "Frontiers in Microbiology"
                ]
            },
            {
                id: "micro5",
                title: "ECOLOGICAL ROLES",
                subtitle: "Ecosystem Services",
                text: "Nutrient cycling (carbon, nitrogen). Soil regeneration and air purification. Plant health support through symbiosis. Regulation of urban ecological balance. Biodegradation of pollutants and waste processing.",
                category: "Ecological Role",
                references: [
                    "Science Journal — 'Microbial life as planetary infrastructure'",
                    "Nature Ecology & Evolution"
                ]
            },
            {
                id: "micro6",
                title: "HUMAN INTERACTION",
                subtitle: "Invisibility & Ignorance",
                text: "Humans rarely perceive microbial life unless it causes disease. Urban planning completely ignores microbial ecosystems. Cleaning, sterilization, and pollution disrupt microbial balance. Treated as either irrelevant or dangerous.",
                category: "Human Dimension",
                references: [
                    "Philosophy of Science & STS literature",
                    "Social Studies of Science"
                ]
            }
        ],
        
        pigeons: [
            {
                id: "pigeon1",
                title: "URBAN PIGEONS",
                subtitle: "Visible Exclusion",
                text: "Columba livia—one of the most widespread urban bird species globally. Descendants of cliff-dwelling birds adapted to buildings. Live in close proximity to humans but are systematically excluded through hostile design and social stigma.",
                category: "Urban Pigeons",
                references: [
                    "British Trust for Ornithology",
                    "European Urban Ecology Studies"
                ]
            },
            {
                id: "pigeon2",
                title: "AIR POLLUTION",
                subtitle: "Respiratory Impact",
                text: "Exposure to PM and heavy metals through inhalation and ingestion. Pollutants accumulate in tissues, impacting respiratory and immune systems. Feather contamination affects insulation and flight efficiency.",
                category: "Environmental Pressure",
                references: [
                    "Environmental Pollution Journal",
                    "Science of the Total Environment"
                ]
            },
            {
                id: "pigeon3",
                title: "NOISE POLLUTION",
                subtitle: "Communication Disruption",
                text: "Chronic urban noise disrupts pigeon communication, stress regulation, and nesting behavior. Alters vocalization patterns and mate selection. Constant noise exposure increases cortisol levels and reduces reproductive success.",
                category: "Environmental Pressure",
                references: [
                    "Proceedings of the Royal Society B",
                    "Urban Ecosystems Journal"
                ]
            },
            {
                id: "pigeon4",
                title: "HOSTILE ARCHITECTURE",
                subtitle: "Designed Exclusion",
                text: "Spikes, nets, repellents, and sloped surfaces deny resting and nesting opportunities. Constant displacement causes chronic stress. Energy spent avoiding exclusion instead of survival activities like foraging and breeding.",
                category: "Environmental Pressure",
                references: [
                    "Urban Studies Journal — Hostile design and non-human species",
                    "Architecture & Violence"
                ]
            },
            {
                id: "pigeon5",
                title: "BIOLOGICAL RESPONSES",
                subtitle: "Physiological Stress",
                text: "Altered gut microbiota linked to environmental toxins. Increased physiological stress markers (corticosterone). Higher disease susceptibility and reduced immune function. Changes in reproductive success in polluted areas.",
                category: "Biological Response",
                references: [
                    "PubMed — Avian microbiome research",
                    "Comparative Biochemistry and Physiology"
                ]
            },
            {
                id: "pigeon6",
                title: "ECOLOGICAL ROLES",
                subtitle: "Urban Ecosystem Functions",
                text: "Seed dispersal across urban landscapes. Nutrient cycling through droppings. Serve as prey for urban predators (falcons, cats). Act as bioindicators of urban pollution levels. Contribute to urban biodiversity.",
                category: "Ecological Role",
                references: [
                    "MDPI — Birds as bioindicators",
                    "Urban Ecology"
                ]
            },
            {
                id: "pigeon7",
                title: "HUMAN PERCEPTION",
                subtitle: "Political Status",
                text: "Seen as pests rather than wildlife. Managed through exclusion rather than coexistence. Violence toward pigeons normalized when framed as aesthetic protection. Represent multispecies injustice in urban planning.",
                category: "Human Dimension",
                references: [
                    "Urban Ethics & Multispecies Justice literature",
                    "Animal Studies Journal"
                ]
            }
        ],
        
        shared: [
            {
                id: "shared1",
                title: "POLLUTION CASCADE",
                subtitle: "Cross-Species Impacts",
                text: "Pollution → Biology → Ecosystem → Human Health. Microbial shifts affect air and soil quality. Pigeons reflect environmental toxicity through bioaccumulation. Humans are indirectly affected through degraded ecosystem services.",
                category: "Shared Infrastructure",
                references: [
                    "Science Advances",
                    "Lancet Planetary Health"
                ]
            },
            {
                id: "shared2",
                title: "FEEDBACK LOOPS",
                subtitle: "System Dynamics",
                text: "Human design decisions impact multiple species simultaneously. Effects cascade across scales from molecular to urban. Most consequences remain unseen until systems collapse. Resilience emerges from multispecies interactions.",
                category: "Shared Infrastructure",
                references: [
                    "Nature Sustainability",
                    "Ecological Economics"
                ]
            },
            {
                id: "shared3",
                title: "PROJECT RELEVANCE",
                subtitle: "Scientific Grounding",
                text: "This infrastructure map provides scientific justification for species choice. It grounds multisensory translation in real biological processes. Enables moving from metaphor to material reality in design. Ensures ethical, informed, and radical interventions.",
                category: "Methodological Application",
                references: [
                    "Design Studies",
                    "Environmental Humanities"
                ]
            }
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

    // Iconos para nodos
    const icons = {
        microorganisms: "🦠",
        pigeons: "🕊️",
        pollution: "☁️",
        temperature: "🌡️",
        noise: "🔊",
        architecture: "🏗️",
        biology: "🧬",
        ecology: "🌿",
        human: "👤",
        shared: "🔄"
    };

    // Inicializar estrellas
    function initStars() {
        const starsContainer = document.getElementById('stars');
        starsContainer.innerHTML = '';
        
        for (let i = 0; i < 400; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            
            const size = Math.random() * 3 + 1;
            star.style.width = `${size}px`;
            star.style.height = `${size}px`;
            star.style.left = `${Math.random() * 100}%`;
            star.style.top = `${Math.random() * 100}%`;
            star.style.animationDelay = `${Math.random() * 5}s`;
            star.style.opacity = Math.random() * 0.5 + 0.1;
            
            starsContainer.appendChild(star);
        }
    }

    // Crear nodos orbitales
    function createOrbitalNodes() {
        // Órbita de microorganismos (más cerca)
        createOrbit(600, nodesData.microorganisms, 'microorganisms-node', icons.microorganisms);
        
        // Órbita de palomas
        createOrbit(900, nodesData.pigeons, 'pigeons-node', icons.pigeons);
        
        // Órbita compartida (más lejos)
        createOrbit(1200, nodesData.shared, 'biology-node', icons.shared);
        
        // Conectar nodo central
        document.getElementById('centralNode').addEventListener('click', (e) => {
            e.stopPropagation();
            showNodeContent(nodesData.central);
        });
    }
    
    function createOrbit(radius, nodes, className, icon) {
        const orbitElement = document.createElement('div');
        orbitElement.classList.add('orbit');
        orbitElement.style.width = `${radius * 2}px`;
        orbitElement.style.height = `${radius * 2}px`;
        galaxy.appendChild(orbitElement);
        
        nodes.forEach((nodeData, index) => {
            const node = document.createElement('div');
            node.classList.add('node', className);
            node.id = nodeData.id;
            node.dataset.title = nodeData.title;
            node.dataset.text = nodeData.text;
            node.dataset.category = nodeData.category;
            node.dataset.references = JSON.stringify(nodeData.references);
            
            const angle = (index / nodes.length) * 2 * Math.PI;
            const x = radius * Math.cos(angle);
            const y = radius * Math.sin(angle);
            
            node.style.left = `calc(50% + ${x}px)`;
            node.style.top = `calc(50% + ${y}px)`;
            node.style.transform = 'translate(-50%, -50%)';
            
            // Icono
            const iconElement = document.createElement('div');
            iconElement.classList.add('node-icon');
            iconElement.textContent = icon || '●';
            
            // Título
            const titleElement = document.createElement('div');
            titleElement.classList.add('node-title');
            titleElement.textContent = nodeData.title;
            
            // Subtítulo
            const subtitleElement = document.createElement('div');
            subtitleElement.classList.add('node-subtitle');
            subtitleElement.textContent = nodeData.subtitle || '';
            
            node.appendChild(iconElement);
            node.appendChild(titleElement);
            if (nodeData.subtitle) {
                node.appendChild(subtitleElement);
            }
            
            node.addEventListener('click', (e) => {
                e.stopPropagation();
                showNodeContent(nodeData);
            });
            
            galaxy.appendChild(node);
        });
    }

    // Mostrar contenido del nodo
    function showNodeContent(nodeData) {
        const panel = document.getElementById('contentPanel');
        const panelTitle = document.getElementById('panelTitle');
        const panelText = document.getElementById('panelText');
        const panelCategory = document.getElementById('panelCategory');
        const panelReferences = document.getElementById('panelReferences');
        
        panelTitle.textContent = nodeData.title;
        panelText.textContent = nodeData.text;
        panelCategory.textContent = nodeData.category;
        
        // Establecer color según categoría
        let color = '';
        switch(nodeData.category) {
            case 'Urban Microorganisms': color = 'var(--microorganisms-color)'; break;
            case 'Urban Pigeons': color = 'var(--pigeons-color)'; break;
            case 'Environmental Pressure': 
                if (nodeData.title.includes('AIR') || nodeData.title.includes('POLLUTION')) {
                    color = 'var(--pollution-color)';
                } else if (nodeData.title.includes('TEMPERATURE')) {
                    color = 'var(--temperature-color)';
                } else if (nodeData.title.includes('CHEMICAL')) {
                    color = 'var(--chemical-color)';
                } else if (nodeData.title.includes('NOISE')) {
                    color = 'var(--temperature-color)';
                } else if (nodeData.title.includes('HOSTILE')) {
                    color = 'var(--human-color)';
                } else {
                    color = 'var(--pollution-color)';
                }
                break;
            case 'Biological Response': color = 'var(--biology-color)'; break;
            case 'Ecological Role': color = 'var(--ecology-color)'; break;
            case 'Human Dimension': color = 'var(--human-color)'; break;
            case 'Shared Infrastructure': color = 'var(--biology-color)'; break;
            case 'Methodological Application': color = 'var(--ecology-color)'; break;
            case 'Scientific Framework': color = 'var(--microorganisms-color)'; break;
            default: color = 'var(--microorganisms-color)';
        }
        
        panelCategory.style.backgroundColor = color;
        panelCategory.style.color = '#000000';
        
        // Actualizar referencias
        if (nodeData.references) {
            panelReferences.style.display = 'block';
            panelReferences.style.borderLeftColor = color;
            
            const referenceItems = panelReferences.querySelectorAll('.reference-item');
            referenceItems.forEach((item, index) => {
                if (nodeData.references[index]) {
                    item.textContent = nodeData.references[index];
                    item.style.display = 'block';
                } else {
                    item.style.display = 'none';
                }
            });
        } else {
            panelReferences.style.display = 'none';
        }
        
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

    // Dibujar conexiones radiales
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
            
            // Determinar color de conexión basado en clase del nodo
            let color = 'rgba(255, 255, 255, 0.15)';
            let lineWidth = 1.5;
            
            if (node.classList.contains('microorganisms-node')) {
                color = 'rgba(106, 17, 203, 0.25)';
            } else if (node.classList.contains('pigeons-node')) {
                color = 'rgba(0, 198, 255, 0.25)';
            } else if (node.classList.contains('biology-node')) {
                color = 'rgba(0, 216, 167, 0.25)';
            }
            
            drawConnectionLine(centerX, centerY, nodeX, nodeY, color, lineWidth);
        });
    }

    function drawConnectionLine(x1, y1, x2, y2, color, width) {
        ctx.beginPath();
        ctx.moveTo(x1, y1);
        ctx.lineTo(x2, y2);
        ctx.strokeStyle = color;
        ctx.lineWidth = width;
        ctx.stroke();
        
        // Añadir efecto de desenfoque sutil
        ctx.shadowBlur = 10;
        ctx.shadowColor = color;
        ctx.stroke();
        ctx.shadowBlur = 0;
    }

    // Actualizar transformación de la galaxia
    function updateTransform() {
        galaxy.style.transform = `translate(calc(-50% + ${offsetX}px), calc(-50% + ${offsetY}px)) scale(${scale})`;
        drawConnections();
    }

    // Manejar zoom
    function handleWheel(e) {
        e.preventDefault();
        
        const zoomFactor = 0.08;
        const oldScale = scale;
        
        if (e.deltaY < 0) {
            scale = Math.min(scale + zoomFactor, 1.2);
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
        if (e.target === viewport || e.target.classList.contains('orbit') || e.target.classList.contains('node')) {
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
            
            if (!isNode && !panel.contains(e.target) && !isCloseBtn && panel.classList.contains('active')) {
                panel.classList.remove('active');
            }
        });
    });
</script>