<!-- =============================================== -->
<!-- MAPA CONCEPTUAL - VERSIÓN COMPLETA VISIBLE -->
<!-- =============================================== -->

<style>
    /* INTEGRACIÓN CON TU DISEÑO EXISTENTE */
    .constellation-page {
        max-width: 1400px !important;
        margin: 0 auto !important;
        padding: 0 2rem 3rem 2rem !important;
        background: #fefaf0 !important;
        font-family: 'Be Vietnam', -apple-system, BlinkMacSystemFont, sans-serif !important;
    }

    /* TÍTULO Y DESCRIPCIÓN */
    .page-title {
        font-size: 2.5rem !important;
        font-weight: 800 !important;
        color: #2d3748 !important;
        text-align: left !important;
        margin: 2rem 0 1rem 0 !important;
        line-height: 1.1 !important;
        padding: 0 !important;
    }

    .page-subtitle {
        color: #4a5568 !important;
        font-size: 1.1rem !important;
        line-height: 1.6 !important;
        margin-bottom: 3rem !important;
        max-width: 900px !important;
    }

    /* ===== CONTENEDOR DEL MAPA - TAMAÑO OPTIMIZADO ===== */
    .map-wrapper {
        position: relative;
        width: 100%;
        max-width: 900px; /* REDUCIDO para que quepa */
        height: 900px;
        margin: 0 auto 4rem auto;
        background: #fefaf0;
        border-radius: 50%;
        overflow: visible;
    }

    /* ANILLOS CONCÉNTRICOS MÁS VISIBLES */
    .concentric-ring {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 50%;
        border: 1px solid rgba(0, 0, 0, 0.06);
        pointer-events: none;
    }

    /* TAMAÑOS AJUSTADOS */
    .ring-1 { width: 140px; height: 140px; }
    .ring-2 { width: 280px; height: 280px; }
    .ring-3 { width: 420px; height: 420px; }
    .ring-4 { width: 560px; height: 560px; }
    .ring-5 { width: 700px; height: 700px; }
    .ring-6 { width: 840px; height: 840px; }

    /* ETIQUETAS DE CAPA */
    .layer-label {
        position: absolute;
        color: #718096;
        font-size: 0.7rem;
        font-weight: 600;
        text-transform: uppercase;
        letter-spacing: 0.8px;
        pointer-events: none;
        opacity: 0.7;
        background: rgba(254, 250, 240, 0.9);
        padding: 0.2rem 0.5rem;
        border-radius: 3px;
    }

    /* ===== NÚCLEO CENTRAL ===== */
    .core-circle {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 130px;
        height: 130px;
        background: linear-gradient(135deg, #1976d2, #2196f3);
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        color: white;
        font-weight: 700;
        font-size: 0.95rem;
        line-height: 1.2;
        padding: 1.5rem;
        cursor: pointer;
        z-index: 20;
        box-shadow: 
            0 10px 30px rgba(25, 118, 210, 0.3),
            0 0 0 2px rgba(255, 255, 255, 0.2) inset;
        transition: all 0.3s ease;
    }

    .core-circle:hover {
        transform: translate(-50%, -50%) scale(1.08);
        box-shadow: 
            0 15px 40px rgba(25, 118, 210, 0.4),
            0 0 0 3px rgba(255, 255, 255, 0.3) inset;
    }

    /* ===== NODOS DE CAPA - MÁS PEQUEÑOS ===== */
    .layer-node {
        position: absolute;
        width: 100px;
        height: 100px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        color: white;
        font-weight: 600;
        font-size: 0.8rem;
        line-height: 1.1;
        padding: 0.8rem;
        cursor: pointer;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        z-index: 10;
        box-shadow: 0 6px 20px rgba(0, 0, 0, 0.12);
        overflow: hidden;
    }

    /* COLORES MÁS SUAVES */
    .node-intuition { background: linear-gradient(135deg, #e91e63, #f06292); }
    .node-question { background: linear-gradient(135deg, #2196f3, #64b5f6); }
    .node-theme { background: linear-gradient(135deg, #ff9800, #ffb74d); }
    .node-action { background: linear-gradient(135deg, #4caf50, #81c784); }
    .node-bee { background: linear-gradient(135deg, #ffc107, #ffd54f); }
    .node-future { background: linear-gradient(135deg, #9c27b0, #ba68c8); }

    .layer-node:hover {
        transform: scale(1.12);
        z-index: 100;
        box-shadow: 0 12px 35px rgba(0, 0, 0, 0.2);
    }

    /* CONTENIDO DENTRO DE LOS NODOS */
    .node-title {
        font-weight: 700;
        margin-bottom: 0.3rem;
        font-size: 0.85rem;
        text-shadow: 0 1px 2px rgba(0, 0, 0, 0.4);
    }

    .node-subtitle {
        font-size: 0.7rem;
        opacity: 0.95;
        font-weight: 400;
        text-shadow: 0 1px 2px rgba(0, 0, 0, 0.3);
    }

    /* ===== CONEXIONES ===== */
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
        stroke: rgba(0, 0, 0, 0.08);
        stroke-width: 1.2;
        fill: none;
        stroke-linecap: round;
    }

    /* ===== PANEL DE INFORMACIÓN (AHORA ABAJO) ===== */
    .info-section {
        max-width: 900px;
        margin: 3rem auto 0 auto;
        background: white;
        border-radius: 16px;
        padding: 2rem;
        box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
        border: 1px solid rgba(0, 0, 0, 0.06);
    }

    .info-header {
        color: #2d3748;
        font-size: 1.5rem;
        font-weight: 700;
        margin-bottom: 1.5rem;
        padding-bottom: 1rem;
        border-bottom: 3px solid #1976d2;
    }

    .info-content {
        color: #4a5568;
        font-size: 1rem;
        line-height: 1.7;
    }

    .info-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 1.5rem;
        margin-top: 1.5rem;
    }

    .info-card {
        background: #f8f9fa;
        border-radius: 10px;
        padding: 1.5rem;
        border-left: 4px solid #1976d2;
    }

    .info-card h4 {
        color: #2d3748;
        font-size: 1.1rem;
        font-weight: 600;
        margin-bottom: 0.5rem;
    }

    .info-card p {
        color: #4a5568;
        font-size: 0.9rem;
        line-height: 1.5;
        margin: 0;
    }

    /* ===== LEYENDA ===== */
    .map-legend {
        position: absolute;
        top: 20px;
        right: 20px;
        background: white;
        border-radius: 12px;
        padding: 1.25rem;
        box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
        border: 1px solid rgba(0, 0, 0, 0.08);
        width: 200px;
        z-index: 50;
    }

    .legend-title {
        color: #2d3748;
        font-size: 0.85rem;
        font-weight: 700;
        margin-bottom: 0.75rem;
        text-transform: uppercase;
        letter-spacing: 0.5px;
    }

    .legend-items {
        display: flex;
        flex-direction: column;
        gap: 0.6rem;
    }

    .legend-item {
        display: flex;
        align-items: center;
        font-size: 0.8rem;
        color: #4a5568;
    }

    .legend-color {
        width: 14px;
        height: 14px;
        border-radius: 50%;
        margin-right: 0.6rem;
        flex-shrink: 0;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }

    /* ===== RESPONSIVE ===== */
    @media (max-width: 1000px) {
        .map-wrapper {
            max-width: 750px;
            height: 750px;
        }
        
        .concentric-ring.ring-1 { width: 120px; height: 120px; }
        .concentric-ring.ring-2 { width: 240px; height: 240px; }
        .concentric-ring.ring-3 { width: 360px; height: 360px; }
        .concentric-ring.ring-4 { width: 480px; height: 480px; }
        .concentric-ring.ring-5 { width: 600px; height: 600px; }
        .concentric-ring.ring-6 { width: 750px; height: 750px; }
        
        .layer-node {
            width: 85px;
            height: 85px;
            font-size: 0.75rem;
            padding: 0.6rem;
        }
        
        .core-circle {
            width: 110px;
            height: 110px;
            font-size: 0.85rem;
            padding: 1.2rem;
        }
    }

    @media (max-width: 800px) {
        .map-wrapper {
            max-width: 600px;
            height: 600px;
        }
        
        .concentric-ring.ring-1 { width: 100px; height: 100px; }
        .concentric-ring.ring-2 { width: 200px; height: 200px; }
        .concentric-ring.ring-3 { width: 300px; height: 300px; }
        .concentric-ring.ring-4 { width: 400px; height: 400px; }
        .concentric-ring.ring-5 { width: 500px; height: 500px; }
        .concentric-ring.ring-6 { width: 600px; height: 600px; }
        
        .layer-node {
            width: 70px;
            height: 70px;
            font-size: 0.7rem;
            padding: 0.5rem;
        }
        
        .core-circle {
            width: 90px;
            height: 90px;
            font-size: 0.8rem;
            padding: 1rem;
        }
        
        .map-legend {
            position: relative;
            top: auto;
            right: auto;
            width: 100%;
            max-width: 400px;
            margin: 2rem auto;
        }
        
        .info-grid {
            grid-template-columns: 1fr;
        }
    }

    @media (max-width: 650px) {
        .constellation-page {
            padding: 0 1rem 2rem 1rem !important;
        }
        
        .page-title {
            font-size: 2rem !important;
        }
        
        .page-subtitle {
            font-size: 1rem !important;
        }
        
        .map-wrapper {
            max-width: 500px;
            height: 500px;
        }
        
        .concentric-ring.ring-1 { width: 80px; height: 80px; }
        .concentric-ring.ring-2 { width: 160px; height: 160px; }
        .concentric-ring.ring-3 { width: 240px; height: 240px; }
        .concentric-ring.ring-4 { width: 320px; height: 320px; }
        .concentric-ring.ring-5 { width: 400px; height: 400px; }
        .concentric-ring.ring-6 { width: 500px; height: 500px; }
        
        .layer-node {
            width: 60px;
            height: 60px;
            font-size: 0.65rem;
            padding: 0.4rem;
        }
        
        .core-circle {
            width: 75px;
            height: 75px;
            font-size: 0.75rem;
            padding: 0.8rem;
        }
        
        .info-section {
            padding: 1.5rem;
        }
        
        .info-header {
            font-size: 1.3rem;
        }
    }

    @media (max-width: 500px) {
        .map-wrapper {
            max-width: 400px;
            height: 400px;
        }
        
        .concentric-ring.ring-1 { width: 60px; height: 60px; }
        .concentric-ring.ring-2 { width: 120px; height: 120px; }
        .concentric-ring.ring-3 { width: 180px; height: 180px; }
        .concentric-ring.ring-4 { width: 240px; height: 240px; }
        .concentric-ring.ring-5 { width: 300px; height: 300px; }
        .concentric-ring.ring-6 { width: 400px; height: 400px; }
        
        .layer-node {
            width: 50px;
            height: 50px;
            font-size: 0.6rem;
            padding: 0.3rem;
        }
        
        .core-circle {
            width: 60px;
            height: 60px;
            font-size: 0.65rem;
            padding: 0.6rem;
        }
        
        .layer-label {
            font-size: 0.6rem;
            padding: 0.1rem 0.3rem;
        }
    }
</style>

<!-- =============================================== -->
<!-- HTML - MAPA CONCEPTUAL COMPLETO -->
<!-- =============================================== -->

<div class="constellation-page">
    
    <!-- Título de página -->
    <h1 class="page-title">Mapa Conceptual: La Ciudad Invisible</h1>
    <div class="page-subtitle">
        Una exploración visual de cómo la belleza urbana oculta violencias estructurales contra especies humanas y no humanas. Interactúa con los nodos para descubrir las conexiones conceptuales.
    </div>
    
    <!-- Contenedor del mapa circular -->
    <div class="map-wrapper" id="emotionMap">
        
        <!-- Leyenda -->
        <div class="map-legend">
            <div class="legend-title">Capas del Mapa</div>
            <div class="legend-items">
                <div class="legend-item">
                    <div class="legend-color" style="background: #e91e63;"></div>
                    <span>Intuiciones (12)</span>
                </div>
                <div class="legend-item">
                    <div class="legend-color" style="background: #2196f3;"></div>
                    <span>Preguntas Motor</span>
                </div>
                <div class="legend-item">
                    <div class="legend-color" style="background: #ff9800;"></div>
                    <span>Campos Temáticos</span>
                </div>
                <div class="legend-item">
                    <div class="legend-color" style="background: #4caf50;"></div>
                    <span>Acciones</span>
                </div>
                <div class="legend-item">
                    <div class="legend-color" style="background: #ffc107;"></div>
                    <span>Proyecto Abeja</span>
                </div>
            </div>
        </div>
        
        <!-- Anillos concéntricos -->
        <div class="concentric-ring ring-1"></div>
        <div class="concentric-ring ring-2"></div>
        <div class="concentric-ring ring-3"></div>
        <div class="concentric-ring ring-4"></div>
        <div class="concentric-ring ring-5"></div>
        <div class="concentric-ring ring-6"></div>
        
        <!-- Etiquetas de capa -->
        <div class="layer-label" style="top: 50%; left: calc(50% + 150px);">Intuiciones</div>
        <div class="layer-label" style="top: 50%; left: calc(50% + 220px);">Preguntas</div>
        <div class="layer-label" style="top: 50%; left: calc(50% + 290px);">Temas</div>
        <div class="layer-label" style="top: 50%; left: calc(50% + 360px);">Acciones</div>
        <div class="layer-label" style="top: 50%; left: calc(50% + 430px);">Abejas</div>
        
        <!-- Núcleo central -->
        <div class="core-circle" id="coreNode">
            LA CIUDAD<br>INVISIBLE
        </div>
        
        <!-- Los nodos se insertarán aquí -->
        <div id="layerNodes"></div>
        
        <!-- Conexiones -->
        <div class="connection" id="connections"></div>
        
    </div>
    
    <!-- Sección de información -->
    <div class="info-section" id="infoSection">
        <h2 class="info-header">Mapa Conceptual</h2>
        <div class="info-content">
            Explora las capas concéntricas del sistema: desde las intuiciones centrales hasta los futuros emergentes. Cada capa representa un nivel de análisis diferente de la Ciudad Invisible.
            
            <div class="info-grid">
                <div class="info-card">
                    <h4>Núcleo Central</h4>
                    <p>La ciudad aparece limpia y ordenada, pero esta belleza oculta violencia estructural contra especies humanas y no humanas.</p>
                </div>
                <div class="info-card">
                    <h4>Intuiciones (12)</h4>
                    <p>Insights emocionales y poéticos que guían la investigación: hacer visible lo invisible, sentir como otras especies, etc.</p>
                </div>
                <div class="info-card">
                    <h4>Preguntas Motor</h4>
                    <p>Cuestionamientos que impulsan la investigación: ¿qué vidas están permitidas? ¿cómo se traducen sentidos no humanos?</p>
                </div>
                <div class="info-card">
                    <h4>Campos Temáticos</h4>
                    <p>Áreas conceptuales de análisis: estética urbana, diseño hostil, justicia multiespecies, etc.</p>
                </div>
            </div>
        </div>
    </div>
    
</div>

<script>
// ===== DATOS DEL SISTEMA - MÁS ORGANIZADOS =====

const constellationData = {
    core: {
        id: "core",
        title: "LA CIUDAD INVISIBLE",
        subtitle: "Beauty hides violence",
        content: "La ciudad aparece limpia, hermosa y ordenada, pero esta belleza a menudo oculta violencia estructural contra especies humanas y no humanas. Al exponer infraestructuras ocultas de exclusión, podemos pasar de la conciencia → empatía → futuros multiespecies.",
        tooltip: "Concepto central: Cómo la belleza urbana esconde violencias sistémicas"
    },
    
    // 💎 CAPA 1: INTUICIONES (12 nodos - Rosa)
    intuitions: [
        { id: "i1", title: "Hacer visible", subtitle: "Lo invisible", angle: 0, radius: 2,
          content: "Urban beauty hides infrastructures of violence. Make the invisible visible." },
        { id: "i2", title: "Sentir otros", subtitle: "Empatía", angle: 30, radius: 2,
          content: "Empathy requires temporarily inhabiting sensory vulnerabilities." },
        { id: "i3", title: "Belleza engaña", subtitle: "Orden estético", angle: 60, radius: 2,
          content: "Aesthetic order often disguises exclusion. The city feels wrong." },
        { id: "i4", title: "Violencia silente", subtitle: "Arquitectónica", angle: 90, radius: 2,
          content: "Violence can be architectural, aesthetic, silent. Appears as 'cleanliness'." },
        { id: "i5", title: "Vidas borradas", subtitle: "Cuerpos excluidos", angle: 120, radius: 2,
          content: "Some forms of life are allowed; others are erased by cities." },
        { id: "i6", title: "Naturaleza control", subtitle: "Decoración", angle: 150, radius: 2,
          content: "Nature permitted only as decoration. Spontaneous life is undesirable." },
        { id: "i7", title: "Vida regresa", subtitle: "Cuando invitada", angle: 180, radius: 2,
          content: "Life returns when invited back. Plants, pigeons, bees persist." },
        { id: "i8", title: "Empatía corporal", subtitle: "No información", angle: 210, radius: 2,
          content: "Empathy through embodiment, not information. Sensory experience matters." },
        { id: "i9", title: "Diseño humano", subtitle: "Ignora otros", angle: 240, radius: 2,
          content: "Human design ignores nonhuman sensory worlds. Urban space is anthropocentric." },
        { id: "i10", title: "Sentir diferente", subtitle: "¿Actuaríamos?", angle: 270, radius: 2,
          content: "If humans could sense like other species, would we act differently?" },
        { id: "i11", title: "Control oculto", subtitle: "Tras belleza", angle: 300, radius: 2,
          content: "City hides control infrastructures behind beauty. 'Safe' can be hostile." },
        { id: "i12", title: "Pequeños actos", subtitle: "Sistemas grandes", angle: 330, radius: 2,
          content: "Tiny interventions reveal huge systems. Micro-actions uncover macro-patterns." }
    ],
    
    // ⚪ CAPA 2: PREGUNTAS (8 nodos - Azul)
    questions: [
        { id: "q1", title: "¿Vidas permitidas?", subtitle: "En la ciudad", angle: 0, radius: 3,
          content: "What lives are allowed in the city? What bodies can rest?" },
        { id: "q2", title: "Violencia estética", subtitle: "Sanitizada", angle: 45, radius: 3,
          content: "How is violence sanitized through aesthetics? Species design differences?" },
        { id: "q3", title: "Traducir sentidos", subtitle: "Mundos no humanos", angle: 90, radius: 3,
          content: "How translate nonhuman sensory worlds? Embodied experience reveals?" },
        { id: "q4", title: "Conciencia → acción", subtitle: "Camino", angle: 135, radius: 3,
          content: "How move from awareness → empathy → action? Create multispecies empathy?" },
        { id: "q5", title: "Sistemas ocultos", subtitle: "Hacer visibles", angle: 180, radius: 3,
          content: "Make invisible control infrastructures visible through design." },
        { id: "q6", title: "Justicia especies", subtitle: "Coexistencia", angle: 225, radius: 3,
          content: "Justice for nonhuman residents? Design for multispecies coexistence." },
        { id: "q7", title: "Métodos traducción", subtitle: "Herramientas", angle: 270, radius: 3,
          content: "Methods to translate bee vision, vibration, signals for humans." },
        { id: "q8", title: "Empatía → cambio", subtitle: "Transformación", angle: 315, radius: 3,
          content: "How does embodied empathy translate to systemic urban change?" }
    ],
    
    // 🟠 CAPA 3: TEMAS (6 nodos - Naranja)
    themes: [
        { id: "t1", title: "Estética Urbana", subtitle: "Belleza política", angle: 0, radius: 4,
          content: "Beauty, order, cleanliness as political tools. Tourism-driven control." },
        { id: "t2", title: "Diseño Hostil", subtitle: "Expulsa", angle: 60, radius: 4,
          content: "Anti-homeless architecture. Pigeon spikes. Surfaces deny rest." },
        { id: "t3", title: "Justicia especies", subtitle: "Derechos", angle: 120, radius: 4,
          content: "Rights to presence, rest, shelter. Nonhuman citizenship. Shared vulnerabilities." },
        { id: "t4", title: "Investigación Cuerpo", subtitle: "Sensor", angle: 180, radius: 4,
          content: "Body as sensor. Ethnographic walking. Feeling architecture." },
        { id: "t5", title: "Traducción Sensorial", subtitle: "Entre especies", angle: 240, radius: 4,
          content: "Translating nonhuman senses. Interfaces for multispecies understanding." },
        { id: "t6", title: "Empatía Ambiental", subtitle: "Sentir-con", angle: 300, radius: 4,
          content: "Empathy towards ecosystems. Cross-species communication. Emotional connection." }
    ],
    
    // 🌙 CAPA 4: ACCIONES (6 nodos - Verde)
    actions: [
        { id: "a1", title: "Sentarse Hostil", subtitle: "Cuerpo sensor", angle: 30, radius: 5,
          content: "Sitting on hostile architecture. Revealing micro-violence through body." },
        { id: "a2", title: "Vestir Hostilidad", subtitle: "Traducción", angle: 90, radius: 5,
          content: "Transferring anti-pigeon spikes to human body. Making violence wearable." },
        { id: "a3", title: "Devolver Vida", subtitle: "Renaturalizar", angle: 150, radius: 5,
          content: "Planting spontaneous life in concrete. Soil, seeds, moss graffiti." },
        { id: "a4", title: "Belleza Excluye", subtitle: "Documentar", angle: 210, radius: 5,
          content: "Documenting aesthetic erasure. Urban Violence Photography Map." },
        { id: "a5", title: "Infraestructuras", subtitle: "Patrones", angle: 270, radius: 5,
          content: "Documenting hidden infrastructures. Patterns of control in tourist zones." },
        { id: "a6", title: "Experimentos", subtitle: "Interfaces", angle: 330, radius: 5,
          content: "Prototyping sensory translation devices across modalities and species." }
    ],
    
    // 🐝 CAPA 5: PROYECTO ABEJA (6 nodos - Amarillo)
    beeProject: [
        { id: "b1", title: "Vulnerabilidades", subtitle: "Pesticidas", angle: 0, radius: 6,
          content: "Pesticides, habitat fragmentation, urban monoculture, heat islands." },
        { id: "b2", title: "Mundo Sensorial", subtitle: "UV, vibraciones", angle: 60, radius: 6,
          content: "UV vision, vibrational communication, chemical signaling, memory." },
        { id: "b3", title: "Conflictos", subtitle: "Remoción", angle: 120, radius: 6,
          content: "Beehives removed for aesthetics. Fear-driven extermination." },
        { id: "b4", title: "Violencia Sistémica", subtitle: "Sistemas", angle: 180, radius: 6,
          content: "Corporate agriculture, industrial pesticides, urban 'beautification'." },
        { id: "b5", title: "Traducción", subtitle: "Métodos", angle: 240, radius: 6,
          content: "Sensors convert vibrations to sound. UV mapping. Temperature pulses." },
        { id: "b6", title: "Camino Empatía", subtitle: "Conciencia → acción", angle: 300, radius: 6,
          content: "Awareness → Embodied Experience → Multispecies Empathy → Action." }
    ]
};

// ===== CONSTRUCCIÓN DEL MAPA =====

function buildConstellationMap() {
    const container = document.getElementById('layerNodes');
    const connectionsContainer = document.getElementById('connections');
    
    // Limpiar contenedores
    container.innerHTML = '';
    connectionsContainer.innerHTML = '';
    
    // Construir todas las capas
    buildLayer(constellationData.intuitions, 'intuition', container);
    buildLayer(constellationData.questions, 'question', container);
    buildLayer(constellationData.themes, 'theme', container);
    buildLayer(constellationData.actions, 'action', container);
    buildLayer(constellationData.beeProject, 'bee', container);
    
    // Configurar núcleo
    setupCoreNode();
    
    // Crear conexiones
    setTimeout(() => {
        createConnections(connectionsContainer);
    }, 100);
}

function buildLayer(nodes, type, container) {
    const centerX = 50; // Porcentaje
    const centerY = 50;
    
    nodes.forEach(node => {
        // Calcular posición radial
        const radiusPercent = node.radius * 13; // 13% por capa
        const angleRad = (node.angle * Math.PI) / 180;
        
        const x = centerX + (radiusPercent * Math.cos(angleRad));
        const y = centerY + (radiusPercent * Math.sin(angleRad));
        
        // Crear nodo
        const nodeElement = document.createElement('div');
        nodeElement.className = `layer-node node-${type}`;
        nodeElement.style.left = `${x}%`;
        nodeElement.style.top = `${y}%`;
        nodeElement.dataset.id = node.id;
        nodeElement.dataset.type = type;
        
        // Contenido
        const content = document.createElement('div');
        content.className = 'node-content';
        
        const title = document.createElement('div');
        title.className = 'node-title';
        title.textContent = node.title;
        
        const subtitle = document.createElement('div');
        subtitle.className = 'node-subtitle';
        subtitle.textContent = node.subtitle;
        
        content.appendChild(title);
        content.appendChild(subtitle);
        nodeElement.appendChild(content);
        
        // Eventos
        nodeElement.addEventListener('mouseenter', (e) => {
            showNodeInfo(node, type);
            highlightNode(nodeElement);
        });
        
        nodeElement.addEventListener('mouseleave', () => {
            resetNode(nodeElement);
        });
        
        container.appendChild(nodeElement);
    });
}

function setupCoreNode() {
    const coreNode = document.getElementById('coreNode');
    const infoSection = document.getElementById('infoSection');
    
    coreNode.addEventListener('mouseenter', () => {
        infoSection.innerHTML = `
            <h2 class="info-header">LA CIUDAD INVISIBLE</h2>
            <div class="info-content">
                <p><strong>Concepto central:</strong> La ciudad aparece limpia, hermosa y ordenada, pero esta belleza a menudo oculta violencia estructural contra especies humanas y no humanas.</p>
                <p>Al exponer infraestructuras ocultas de exclusión, podemos pasar de:</p>
                <p><strong>CONCIENCIA → EMPATÍA → FUTUROS MULTIESPECIES</strong></p>
                <div class="info-grid">
                    <div class="info-card">
                        <h4>Belleza que oculta</h4>
                        <p>La estética urbana como fachada que esconde sistemas de exclusión y violencia.</p>
                    </div>
                    <div class="info-card">
                        <h4>Violencia estructural</h4>
                        <p>Contra humanos (sin hogar) y no humanos (palomas, abejas, plantas espontáneas).</p>
                    </div>
                    <div class="info-card">
                        <h4>Infraestructuras ocultas</h4>
                        <p>Sistemas de control disfrazados de mantenimiento, seguridad o limpieza.</p>
                    </div>
                </div>
            </div>
        `;
        coreNode.style.transform = 'translate(-50%, -50%) scale(1.1)';
    });
    
    coreNode.addEventListener('mouseleave', () => {
        coreNode.style.transform = 'translate(-50%, -50%)';
        resetInfoSection();
    });
}

function createConnections(container) {
    const svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
    svg.setAttribute("viewBox", "0 0 100 100");
    svg.setAttribute("preserveAspectRatio", "none");
    svg.style.width = "100%";
    svg.style.height = "100%";
    
    // Conexiones principales (menos para más limpieza)
    const connections = [
        ['core', 'i1'], ['core', 'i10'], ['core', 't3'],
        ['t5', 'b2'], ['t4', 'a1'], ['t6', 'b6'],
        ['i1', 'q1'], ['i4', 'q5'], ['i10', 'b2']
    ];
    
    connections.forEach(([sourceId, targetId]) => {
        connectNodes(svg, sourceId, targetId);
    });
    
    container.appendChild(svg);
}

function connectNodes(svg, sourceId, targetId) {
    const source = sourceId === 'core' 
        ? document.getElementById('coreNode')
        : document.querySelector(`[data-id="${sourceId}"]`);
    
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

function showNodeInfo(node, type) {
    const infoSection = document.getElementById('infoSection');
    const typeNames = {
        'intuition': 'Intuición',
        'question': 'Pregunta Motor',
        'theme': 'Campo Temático',
        'action': 'Acción como Conocimiento',
        'bee': 'Proyecto Abeja'
    };
    
    infoSection.innerHTML = `
        <h2 class="info-header">${node.title}</h2>
        <div class="info-content">
            <p><strong>${typeNames[type]}</strong>: ${node.subtitle}</p>
            <p>${node.content}</p>
            <div class="info-grid">
                <div class="info-card">
                    <h4>Conexiones principales</h4>
                    <p>Relacionado con otros nodos del sistema conceptual.</p>
                </div>
                <div class="info-card">
                    <h4>Nivel de análisis</h4>
                    <p>Parte de la capa de ${typeNames[type]} en el mapa.</p>
                </div>
                <div class="info-card">
                    <h4>Aplicación práctica</h4>
                    <p>Se traduce en intervenciones, investigaciones o prototipos.</p>
                </div>
            </div>
        </div>
    `;
}

function highlightNode(node) {
    node.style.transform = 'scale(1.2)';
    node.style.zIndex = '100';
    node.style.boxShadow = '0 15px 40px rgba(0, 0, 0, 0.25)';
}

function resetNode(node) {
    node.style.transform = '';
    node.style.zIndex = '';
    node.style.boxShadow = '';
}

function resetInfoSection() {
    const infoSection = document.getElementById('infoSection');
    infoSection.innerHTML = `
        <h2 class="info-header">Mapa Conceptual</h2>
        <div class="info-content">
            Explora las capas concéntricas del sistema: desde las intuiciones centrales hasta los futuros emergentes. Cada capa representa un nivel de análisis diferente de la Ciudad Invisible.
            
            <div class="info-grid">
                <div class="info-card">
                    <h4>Núcleo Central</h4>
                    <p>La ciudad aparece limpia y ordenada, pero esta belleza oculta violencia estructural contra especies humanas y no humanas.</p>
                </div>
                <div class="info-card">
                    <h4>Intuiciones (12)</h4>
                    <p>Insights emocionales y poéticos que guían la investigación: hacer visible lo invisible, sentir como otras especies, etc.</p>
                </div>
                <div class="info-card">
                    <h4>Preguntas Motor</h4>
                    <p>Cuestionamientos que impulsan la investigación: ¿qué vidas están permitidas? ¿cómo se traducen sentidos no humanos?</p>
                </div>
                <div class="info-card">
                    <h4>Campos Temáticos</h4>
                    <p>Áreas conceptuales de análisis: estética urbana, diseño hostil, justicia multiespecies, etc.</p>
                </div>
            </div>
        </div>
    `;
}

// ===== INICIALIZACIÓN =====

document.addEventListener('DOMContentLoaded', () => {
    buildConstellationMap();
    
    // Ajustar en redimensionamiento
    let resizeTimeout;
    window.addEventListener('resize', () => {
        clearTimeout(resizeTimeout);
        resizeTimeout = setTimeout(() => {
            buildConstellationMap();
        }, 250);
    });
});
</script>