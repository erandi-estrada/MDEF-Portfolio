<!-- =============================================== -->
<!-- MAPA DE LA CIUDAD INVISIBLE - ESTILO PROFESIONAL -->
<!-- =============================================== -->

<style>
    /* INTEGRACIÓN CON TU ESTILO EXISTENTE */
    .constellation-page {
        max-width: 1400px !important;
        margin: 0 auto !important;
        padding: 0 2rem 4rem 2rem !important;
        background: #fefaf0 !important;
        font-family: 'Be Vietnam', -apple-system, BlinkMacSystemFont, sans-serif !important;
    }

    /* TÍTULO DE PÁGINA - CONSISTENTE CON TU DISEÑO */
    .page-title {
        font-size: 2.5rem !important;
        font-weight: 800 !important;
        color: #2d3748 !important;
        text-align: left !important;
        margin: 2rem 0 1.5rem 0 !important;
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

    /* ===== CONTENEDOR DEL MAPA CIRCULAR ===== */
    .emotion-map-container {
        position: relative;
        width: 1200px;
        height: 1200px;
        margin: 0 auto 4rem auto;
        background: #fefaf0;
        border-radius: 50%;
        overflow: hidden;
        box-shadow: 0 20px 60px rgba(0, 0, 0, 0.08),
                    0 0 0 1px rgba(0, 0, 0, 0.03);
    }

    /* ANILLOS CONCÉNTRICOS MUY SÚTILES */
    .concentric-ring {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 50%;
        border: 1px solid rgba(0, 0, 0, 0.04);
        pointer-events: none;
    }

    .ring-1 { width: 200px; height: 200px; }
    .ring-2 { width: 400px; height: 400px; }
    .ring-3 { width: 600px; height: 600px; }
    .ring-4 { width: 800px; height: 800px; }
    .ring-5 { width: 1000px; height: 1000px; }
    .ring-6 { width: 1200px; height: 1200px; }

    /* ETIQUETAS DE CAPA (como en la imagen original) */
    .layer-label {
        position: absolute;
        color: #718096;
        font-size: 0.75rem;
        font-weight: 600;
        text-transform: uppercase;
        letter-spacing: 1px;
        pointer-events: none;
        opacity: 0.7;
    }

    /* ===== NÚCLEO CENTRAL ===== */
    .core-circle {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 180px;
        height: 180px;
        background: #1976d2;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        color: white;
        font-weight: 700;
        font-size: 1.1rem;
        line-height: 1.3;
        padding: 2rem;
        cursor: pointer;
        z-index: 20;
        box-shadow: 
            0 10px 40px rgba(25, 118, 210, 0.25),
            0 0 0 1px rgba(255, 255, 255, 0.1) inset;
        transition: all 0.3s ease;
    }

    .core-circle:hover {
        transform: translate(-50%, -50%) scale(1.05);
        box-shadow: 
            0 15px 50px rgba(25, 118, 210, 0.35),
            0 0 0 1px rgba(255, 255, 255, 0.15) inset;
    }

    /* ===== NODOS DE CAPA ===== */
    .layer-node {
        position: absolute;
        width: 140px;
        height: 140px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        color: white;
        font-weight: 600;
        font-size: 0.9rem;
        line-height: 1.2;
        padding: 1rem;
        cursor: pointer;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        z-index: 10;
        box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        overflow: hidden;
    }

    /* COLORES INSPIRADOS EN LA RUEDA DE EMOCIONES */
    .node-intuition { background: #e91e63; } /* Rosa vibrante */
    .node-question { background: #2196f3; }  /* Azul */
    .node-theme { background: #ff9800; }     /* Naranja */
    .node-action { background: #4caf50; }    /* Verde */
    .node-bee { background: #ffc107; }       /* Amarillo dorado */
    .node-future { background: #9c27b0; }    /* Púrpura */

    .layer-node:hover {
        transform: scale(1.15);
        z-index: 100;
        box-shadow: 0 15px 40px rgba(0, 0, 0, 0.25);
    }

    /* CONTENIDO DENTRO DE LOS NODOS */
    .node-title {
        font-weight: 700;
        margin-bottom: 0.5rem;
        font-size: 0.95rem;
        text-shadow: 0 1px 3px rgba(0, 0, 0, 0.3);
    }

    .node-subtitle {
        font-size: 0.8rem;
        opacity: 0.95;
        font-weight: 400;
        text-shadow: 0 1px 2px rgba(0, 0, 0, 0.3);
    }

    /* ===== CONEXIONES ORGÁNICAS ===== */
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
        stroke: rgba(0, 0, 0, 0.1);
        stroke-width: 1.5;
        fill: none;
        stroke-linecap: round;
    }

    /* ===== PANEL DE INFORMACIÓN ===== */
    .info-panel {
        position: fixed;
        right: 2rem;
        top: 50%;
        transform: translateY(-50%);
        width: 350px;
        background: white;
        border-radius: 16px;
        padding: 2rem;
        box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
        z-index: 1000;
        opacity: 0;
        transform: translateY(-50%) translateX(20px);
        transition: all 0.4s ease;
        border: 1px solid rgba(0, 0, 0, 0.08);
    }

    .info-panel.active {
        opacity: 1;
        transform: translateY(-50%) translateX(0);
    }

    .panel-header {
        color: #2d3748;
        font-size: 1.3rem;
        font-weight: 700;
        margin-bottom: 1rem;
        padding-bottom: 1rem;
        border-bottom: 2px solid #1976d2;
    }

    .panel-content {
        color: #4a5568;
        font-size: 0.95rem;
        line-height: 1.6;
        max-height: 400px;
        overflow-y: auto;
        padding-right: 0.5rem;
    }

    .panel-content::-webkit-scrollbar {
        width: 4px;
    }

    .panel-content::-webkit-scrollbar-track {
        background: #f1f1f1;
        border-radius: 2px;
    }

    .panel-content::-webkit-scrollbar-thumb {
        background: #c1c1c1;
        border-radius: 2px;
    }

    /* ===== LEYENDA ===== */
    .map-legend {
        position: absolute;
        bottom: 2rem;
        left: 2rem;
        background: white;
        border-radius: 12px;
        padding: 1.5rem;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        border: 1px solid rgba(0, 0, 0, 0.08);
        width: 250px;
    }

    .legend-title {
        color: #2d3748;
        font-size: 0.9rem;
        font-weight: 700;
        margin-bottom: 1rem;
        text-transform: uppercase;
        letter-spacing: 0.5px;
    }

    .legend-items {
        display: flex;
        flex-direction: column;
        gap: 0.75rem;
    }

    .legend-item {
        display: flex;
        align-items: center;
        font-size: 0.85rem;
        color: #4a5568;
    }

    .legend-color {
        width: 16px;
        height: 16px;
        border-radius: 50%;
        margin-right: 0.75rem;
        flex-shrink: 0;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
    }

    /* ===== RESPONSIVE ===== */
    @media (max-width: 1300px) {
        .emotion-map-container {
            width: 1000px;
            height: 1000px;
        }
        
        .concentric-ring.ring-1 { width: 160px; height: 160px; }
        .concentric-ring.ring-2 { width: 320px; height: 320px; }
        .concentric-ring.ring-3 { width: 480px; height: 480px; }
        .concentric-ring.ring-4 { width: 640px; height: 640px; }
        .concentric-ring.ring-5 { width: 800px; height: 800px; }
        .concentric-ring.ring-6 { width: 1000px; height: 1000px; }
        
        .layer-node {
            width: 120px;
            height: 120px;
            font-size: 0.85rem;
        }
        
        .info-panel {
            width: 300px;
        }
    }

    @media (max-width: 1100px) {
        .emotion-map-container {
            width: 800px;
            height: 800px;
        }
        
        .concentric-ring.ring-1 { width: 120px; height: 120px; }
        .concentric-ring.ring-2 { width: 240px; height: 240px; }
        .concentric-ring.ring-3 { width: 360px; height: 360px; }
        .concentric-ring.ring-4 { width: 480px; height: 480px; }
        .concentric-ring.ring-5 { width: 600px; height: 600px; }
        .concentric-ring.ring-6 { width: 800px; height: 800px; }
        
        .layer-node {
            width: 100px;
            height: 100px;
            font-size: 0.8rem;
            padding: 0.75rem;
        }
        
        .core-circle {
            width: 140px;
            height: 140px;
            font-size: 1rem;
            padding: 1.5rem;
        }
        
        .info-panel {
            position: relative;
            right: auto;
            top: auto;
            transform: none;
            width: 100%;
            margin-top: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .map-legend {
            position: relative;
            bottom: auto;
            left: auto;
            width: 100%;
            max-width: 600px;
            margin: 2rem auto;
        }
    }

    @media (max-width: 850px) {
        .emotion-map-container {
            width: 600px;
            height: 600px;
        }
        
        .concentric-ring.ring-1 { width: 90px; height: 90px; }
        .concentric-ring.ring-2 { width: 180px; height: 180px; }
        .concentric-ring.ring-3 { width: 270px; height: 270px; }
        .concentric-ring.ring-4 { width: 360px; height: 360px; }
        .concentric-ring.ring-5 { width: 450px; height: 450px; }
        .concentric-ring.ring-6 { width: 600px; height: 600px; }
        
        .layer-node {
            width: 80px;
            height: 80px;
            font-size: 0.75rem;
            padding: 0.5rem;
        }
        
        .core-circle {
            width: 100px;
            height: 100px;
            font-size: 0.9rem;
            padding: 1rem;
        }
    }

    @media (max-width: 650px) {
        .constellation-page {
            padding: 0 1rem 2rem 1rem !important;
        }
        
        .emotion-map-container {
            width: 500px;
            height: 500px;
        }
        
        .concentric-ring.ring-1 { width: 70px; height: 70px; }
        .concentric-ring.ring-2 { width: 140px; height: 140px; }
        .concentric-ring.ring-3 { width: 210px; height: 210px; }
        .concentric-ring.ring-4 { width: 280px; height: 280px; }
        .concentric-ring.ring-5 { width: 350px; height: 350px; }
        .concentric-ring.ring-6 { width: 500px; height: 500px; }
    }
</style>

<!-- =============================================== -->
<!-- HTML - PÁGINA DE CONSTELACIÓN -->
<!-- =============================================== -->

<div class="constellation-page">
    
    <!-- Título de página -->
    <h1 class="page-title">Mapa Conceptual: La Ciudad Invisible</h1>
    <div class="page-subtitle">
        Una exploración visual de cómo la belleza urbana oculta violencias estructurales contra especies humanas y no humanas. Interactúa con los nodos para descubrir las conexiones conceptuales.
    </div>
    
    <!-- Contenedor del mapa circular -->
    <div class="emotion-map-container" id="emotionMap">
        
        <!-- Anillos concéntricos (muy sutiles) -->
        <div class="concentric-ring ring-1"></div>
        <div class="concentric-ring ring-2"></div>
        <div class="concentric-ring ring-3"></div>
        <div class="concentric-ring ring-4"></div>
        <div class="concentric-ring ring-5"></div>
        <div class="concentric-ring ring-6"></div>
        
        <!-- Etiquetas de capa -->
        <div class="layer-label" style="top: 50%; left: calc(50% + 220px);">Intuiciones</div>
        <div class="layer-label" style="top: 50%; left: calc(50% + 320px);">Preguntas</div>
        <div class="layer-label" style="top: 50%; left: calc(50% + 420px);">Temas</div>
        <div class="layer-label" style="top: 50%; left: calc(50% + 520px);">Acciones</div>
        <div class="layer-label" style="top: 50%; left: calc(50% + 620px);">Proyecto Abeja</div>
        
        <!-- Núcleo central -->
        <div class="core-circle" id="coreNode">
            LA CIUDAD INVISIBLE
        </div>
        
        <!-- Los nodos se insertarán aquí por JavaScript -->
        <div id="layerNodes"></div>
        
        <!-- Conexiones -->
        <div class="connection" id="connections"></div>
        
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
                    <span>Acciones como Conocimiento</span>
                </div>
                <div class="legend-item">
                    <div class="legend-color" style="background: #ffc107;"></div>
                    <span>Proyecto Multiespecies</span>
                </div>
                <div class="legend-item">
                    <div class="legend-color" style="background: #9c27b0;"></div>
                    <span>Futuros Emergentes</span>
                </div>
            </div>
        </div>
        
    </div>
    
    <!-- Panel de información flotante -->
    <div class="info-panel" id="infoPanel">
        <div class="panel-header" id="panelTitle">Selecciona un nodo</div>
        <div class="panel-content" id="panelContent">
            Haz clic o pasa el cursor sobre cualquier nodo del mapa para ver información detallada sobre ese concepto y sus conexiones con otros elementos del sistema.
        </div>
    </div>
    
</div>

<script>
// ===== DATOS COMPLETOS DEL SISTEMA =====

const constellationData = {
    core: {
        id: "core",
        title: "LA CIUDAD INVISIBLE",
        content: "La ciudad aparece limpia, hermosa y ordenada, pero esta belleza a menudo oculta violencia estructural contra especies humanas y no humanas. Al exponer infraestructuras ocultas de exclusión, podemos pasar de la conciencia → empatía → futuros multiespecies.",
        tooltip: "Concepto central: Cómo la belleza urbana esconde violencias sistémicas"
    },
    
    // 💎 CAPA 1: INTUICIONES (12 nodos - Rosa)
    intuitions: [
        { id: "i1", title: "Hacer visible lo invisible", subtitle: "La belleza urbana esconde violencia", angle: 0, radius: 2,
          content: "Urban beauty hides infrastructures of violence toward humans, animals, and ecosystems. Make the invisible visible." },
        { id: "i2", title: "Sentir lo que otros sienten", subtitle: "Empatía requiere vulnerabilidad", angle: 30, radius: 2,
          content: "Empathy requires temporarily inhabiting sensory vulnerabilities we do not normally perceive. Make humans feel what other species feel." },
        { id: "i3", title: "Belleza que engaña", subtitle: "El orden estético disfraza exclusión", angle: 60, radius: 2,
          content: "The city is beautiful, but something feels wrong. Aesthetic order often disguises exclusion." },
        { id: "i4", title: "Violencia silenciosa", subtitle: "Arquitectónica, estética, oculta", angle: 90, radius: 2,
          content: "Violence is not only physical — it can be architectural, aesthetic, silent. It can appear as 'cleanliness', 'order', or 'maintenance.'" },
        { id: "i5", title: "Vidas permitidas, vidas borradas", subtitle: "Ciudades deciden qué cuerpos existen", angle: 120, radius: 2,
          content: "Some forms of life are allowed; others are erased. Cities decide which bodies can inhabit space — humans and nonhumans alike." },
        { id: "i6", title: "Naturaleza como decoración", subtitle: "La vida espontánea es indeseable", angle: 150, radius: 2,
          content: "Nature is permitted only when it behaves as decoration. Spontaneous, uncontrolled life is considered undesirable." },
        { id: "i7", title: "La vida regresa", subtitle: "Cuando la invitamos de vuelta", angle: 180, radius: 2,
          content: "Life returns when we invite it back. Plants growing through cracks, pigeons resting, bees visiting flowers — life persists." },
        { id: "i8", title: "Empatía a través del cuerpo", subtitle: "No a través de información", angle: 210, radius: 2,
          content: "Empathy emerges through embodiment, not information. Data alone does not generate change; sensory and embodied experience does." },
        { id: "i9", title: "Diseño antropocéntrico", subtitle: "Ignora mundos sensoriales no humanos", angle: 240, radius: 2,
          content: "Human-designed environments do not consider nonhuman sensory worlds. Urban space is tuned only to human comfort, not multispecies survival." },
        { id: "i10", title: "Sentir como otra especie", subtitle: "¿Actuaríamos diferente?", angle: 270, radius: 2,
          content: "If humans could sense the city like another species, would we act differently? This question anchors your main research." },
        { id: "i11", title: "Control tras la belleza", subtitle: "Lo que parece seguro puede ser hostil", angle: 300, radius: 2,
          content: "The city hides infrastructures of control behind beauty. What appears 'safe', 'nice', or 'clean' can be deeply hostile." },
        { id: "i12", title: "Intervenciones pequeñas", subtitle: "Revelan sistemas grandes", angle: 330, radius: 2,
          content: "Tiny interventions reveal huge systems. Sitting on hostile architecture, planting a leaf, modifying a dress — micro-actions uncover macro-patterns." }
    ],
    
    // ⚪ CAPA 2: PREGUNTAS (8 nodos - Azul)
    questions: [
        { id: "q1", title: "¿Qué vidas están permitidas?", subtitle: "En la ciudad", angle: 0, radius: 3,
          content: "What lives are allowed in the city? What bodies can rest? How does beauty justify exclusion?" },
        { id: "q2", title: "Violencia sanitizada", subtitle: "A través de la estética", angle: 45, radius: 3,
          content: "How is violence sanitized through aesthetics? Would other species design differently?" },
        { id: "q3", title: "Traducir sentidos", subtitle: "Mundos sensoriales no humanos", angle: 90, radius: 3,
          content: "How can we translate nonhuman sensory worlds? How can embodied experience reveal hidden infrastructures?" },
        { id: "q4", title: "Conciencia → acción", subtitle: "Camino de transformación", angle: 135, radius: 3,
          content: "How can we move from awareness → empathy → action? What interventions create multispecies empathy?" },
        { id: "q5", title: "Sistemas ocultos", subtitle: "Hacer visible", angle: 180, radius: 3,
          content: "How to make invisible infrastructures of control visible through design and intervention?" },
        { id: "q6", title: "Justicia multiespecies", subtitle: "En el espacio urbano", angle: 225, radius: 3,
          content: "What does justice look like for nonhuman urban residents? How to design for multispecies coexistence?" },
        { id: "q7", title: "Traducción sensorial", subtitle: "Métodos y herramientas", angle: 270, radius: 3,
          content: "What methods can translate bee vision, vibration, chemical signals into human-perceivable experiences?" },
        { id: "q8", title: "Empatía → cambio", subtitle: "¿Cómo?", angle: 315, radius: 3,
          content: "How does embodied empathy translate to behavioral and systemic change in urban environments?" }
    ],
    
    // 🟠 CAPA 3: TEMAS (6 nodos - Naranja)
    themes: [
        { id: "t1", title: "Estética Urbana", subtitle: "Belleza como herramienta política", angle: 0, radius: 4,
          content: "Beauty, order, cleanliness as political tools. Tourism-driven visual control. Aesthetic erasure of life." },
        { id: "t2", title: "Diseño Hostil", subtitle: "Arquitectura que expulsa", angle: 60, radius: 4,
          content: "Anti-homeless architecture. Anti-pigeon measures. Urban surfaces that deny rest. Violence normalized through design." },
        { id: "t3", title: "Justicia Multiespecies", subtitle: "Más allá de derechos humanos", angle: 120, radius: 4,
          content: "Rights to presence, rest, shelter. Nonhuman citizenship. Shared urban vulnerabilities." },
        { id: "t4", title: "Investigación Corpórea", subtitle: "El cuerpo como sensor", angle: 180, radius: 4,
          content: "Your body as sensor. Ethnographic walking. Feeling architecture. First-person experience as research method." },
        { id: "t5", title: "Traducción Sensorial", subtitle: "Percepción entre especies", angle: 240, radius: 4,
          content: "Translating nonhuman senses. Designing for a body unlike yours. Interfaces for multispecies understanding." },
        { id: "t6", title: "Empatía Ambiental", subtitle: "Sentir-con ecosistemas", angle: 300, radius: 4,
          content: "Empathy towards ecosystems. Cross-species communication. Emotional connection through experience." }
    ],
    
    // 🌙 CAPA 4: ACCIONES (6 nodos - Verde)
    actions: [
        { id: "a1", title: "Sentarse en lo Hostil", subtitle: "Cuerpo como sensor", angle: 30, radius: 5,
          content: "Sitting on hostile architecture. Revealing architectural micro-violence through embodied experience." },
        { id: "a2", title: "Vestir la Hostilidad", subtitle: "Traducción material", angle: 90, radius: 5,
          content: "Transferring anti-pigeon spikes to the human body. Making architectural violence visible and wearable." },
        { id: "a3", title: "Devolver la Vida", subtitle: "Actos de renaturalización", angle: 150, radius: 5,
          content: "Planting spontaneous life in concrete spaces. Soil deposits, seed bombs, moss graffiti. Reintroducing non-curated life." },
        { id: "a4", title: "Belleza que Excluye", subtitle: "Documentar el borrado", angle: 210, radius: 5,
          content: "Documenting aesthetic erasure. Urban Violence Photography Map. Mapping exclusions across Barcelona." },
        { id: "a5", title: "Infraestructuras Ocultas", subtitle: "Patrones de control", angle: 270, radius: 5,
          content: "Documenting hidden infrastructures. Patterns of control in tourist zones. Your practice uses the body and micro-interventions." },
        { id: "a6", title: "Experimentos Sensoriales", subtitle: "Interfaces de percepción", angle: 330, radius: 5,
          content: "Prototyping devices that translate urban conditions across sensory modalities and species." }
    ],
    
    // 🐝 CAPA 5: PROYECTO ABEJA (8 nodos - Amarillo)
    beeProject: [
        { id: "b1", title: "Vulnerabilidades", subtitle: "Pesticidas, pérdida de hábitat", angle: 20, radius: 6,
          content: "Pesticides, habitat fragmentation, urban monoculture plants, heat islands, pollution." },
        { id: "b2", title: "Mundo Sensorial", subtitle: "Visión UV, vibraciones", angle: 60, radius: 6,
          content: "UV vision, vibrational communication, chemical signaling, spatial memory, magnetoreception." },
        { id: "b3", title: "Conflictos Humanos-Abejas", subtitle: "Remoción estética", angle: 100, radius: 6,
          content: "Beehives removed for aesthetics, fear-driven extermination, landscaping hostile to pollinators." },
        { id: "b4", title: "Infraestructuras de Violencia", subtitle: "Edición abeja", angle: 140, radius: 6,
          content: "Corporate agriculture, industrial pesticides, urban 'beautification' that removes wildflowers, lack of nesting spaces." },
        { id: "b5", title: "Traducción Multiespecies", subtitle: "Métodos", angle: 180, radius: 6,
          content: "Sensors that convert vibrations to sound, UV → visible spectrum mapping, temperature → haptic pulses, pheromone patterns → scent." },
        { id: "b6", title: "Camino de Empatía", subtitle: "Conciencia → acción", angle: 220, radius: 6,
          content: "Awareness → Embodied Experience → Multispecies Empathy → Action. Your main conceptual structure." },
        { id: "b7", title: "Instalación Sensorial", subtitle: "Resultado final", angle: 260, radius: 6,
          content: "Immersive multisensory environment. Human body temporarily tuned to bee senses. Visual, auditory, haptic translation." },
        { id: "b8", title: "Prototipos Futuros", subtitle: "Zonas seguras, hábitats", angle: 300, radius: 6,
          content: "Multispecies safe zones, bee-friendly architectures, restorative micro-habitats, urban sensory inclusivity." }
    ]
};

// ===== CONSTRUCCIÓN DEL MAPA =====

function buildConstellationMap() {
    const container = document.getElementById('layerNodes');
    const connectionsContainer = document.getElementById('connections');
    
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
        const radiusPercent = node.radius * 15; // 15% por capa
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
        nodeElement.addEventListener('mouseenter', (e) => showNodeInfo(node, e));
        nodeElement.addEventListener('mouseleave', hideNodeInfo);
        nodeElement.addEventListener('click', () => focusNode(node));
        
        container.appendChild(nodeElement);
    });
}

function setupCoreNode() {
    const coreNode = document.getElementById('coreNode');
    coreNode.addEventListener('mouseenter', (e) => {
        showNodeInfo(constellationData.core, e);
    });
    coreNode.addEventListener('mouseleave', hideNodeInfo);
    coreNode.addEventListener('click', () => focusNode(constellationData.core));
}

// ===== CONEXIONES =====

function createConnections(container) {
    const svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
    svg.setAttribute("viewBox", "0 0 100 100");
    svg.setAttribute("preserveAspectRatio", "none");
    svg.style.width = "100%";
    svg.style.height = "100%";
    
    // Conexiones principales
    connectNodes(svg, 'core', 't1');
    connectNodes(svg, 'core', 't3');
    connectNodes(svg, 'core', 'i10');
    connectNodes(svg, 't5', 'b2');
    connectNodes(svg, 't3', 'b1');
    connectNodes(svg, 't4', 'a1');
    connectNodes(svg, 't4', 'a2');
    connectNodes(svg, 't6', 'b6');
    connectNodes(svg, 'i1', 'q1');
    connectNodes(svg, 'i4', 'q5');
    connectNodes(svg, 'i10', 'q7');
    
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

// ===== INTERACCIÓN CON NODOS =====

const infoPanel = document.getElementById('infoPanel');
const panelTitle = document.getElementById('panelTitle');
const panelContent = document.getElementById('panelContent');

function showNodeInfo(node, event) {
    panelTitle.textContent = node.title;
    panelContent.textContent = node.content;
    infoPanel.classList.add('active');
    
    // Resaltar el nodo
    const nodeElement = event.target.closest('.layer-node, .core-circle');
    if (nodeElement) {
        nodeElement.style.zIndex = "100";
        nodeElement.style.boxShadow = "0 20px 50px rgba(0, 0, 0, 0.3)";
    }
}

function hideNodeInfo() {
    // No ocultar completamente el panel, pero actualizar contenido por defecto
    panelTitle.textContent = "Mapa Conceptual";
    panelContent.textContent = "Explora las capas concéntricas del sistema: desde las intuiciones centrales hasta los futuros emergentes. Cada capa representa un nivel de análisis diferente de la Ciudad Invisible.";
    
    // Restaurar todos los nodos
    document.querySelectorAll('.layer-node, .core-circle').forEach(node => {
        node.style.zIndex = "";
        node.style.boxShadow = "";
    });
}

function focusNode(node) {
    // En una versión avanzada, esto podría hacer zoom en el nodo
    panelTitle.textContent = `Foco en: ${node.title}`;
    panelContent.innerHTML = `
        <strong>${node.title}</strong><br><br>
        ${node.content}<br><br>
        <em>Haz clic en otros nodos para explorar conexiones.</em>
    `;
    infoPanel.classList.add('active');
}

// ===== INICIALIZACIÓN =====

document.addEventListener('DOMContentLoaded', () => {
    buildConstellationMap();
    
    // Cerrar panel al hacer clic fuera
    document.addEventListener('click', (e) => {
        if (!e.target.closest('.layer-node') && 
            !e.target.closest('.core-circle') && 
            !e.target.closest('.info-panel')) {
            hideNodeInfo();
        }
    });
});
</script>