<!-- =============================================== -->
<!-- MAPA CONCEPTUAL - VERSIÓN CORREGIDA -->
<!-- =============================================== -->

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mapa Conceptual: La Ciudad Invisible</title>
    <style>
        /* RESET Y BASE */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
            background: #fefaf0;
            color: #333;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* CONTENEDOR PRINCIPAL */
        .constellation-page {
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem;
            min-height: 100vh;
        }

        /* TÍTULO Y DESCRIPCIÓN */
        .page-title {
            font-size: 2.5rem;
            font-weight: 800;
            color: #2d3748;
            text-align: left;
            margin: 0 0 1rem 0;
            line-height: 1.1;
        }

        .page-subtitle {
            color: #4a5568;
            font-size: 1.1rem;
            line-height: 1.6;
            margin-bottom: 3rem;
            max-width: 900px;
        }

        /* CONTENEDOR PRINCIPAL DEL MAPA */
        .map-container {
            position: relative;
            width: 100%;
            min-height: 1000px;
            margin: 2rem 0 4rem 0;
        }

        /* LEYENDA - MOVIDA A LA DERECHA */
        .legend-container {
            position: absolute;
            right: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 220px;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(0, 0, 0, 0.08);
            z-index: 100;
        }

        .legend-title {
            color: #2d3748;
            font-size: 0.9rem;
            font-weight: 700;
            margin-bottom: 1rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            text-align: center;
        }

        .legend-items {
            display: flex;
            flex-direction: column;
            gap: 0.7rem;
        }

        .legend-item {
            display: flex;
            align-items: center;
            font-size: 0.8rem;
            color: #4a5568;
        }

        .legend-color {
            width: 16px;
            height: 16px;
            border-radius: 50%;
            margin-right: 0.7rem;
            flex-shrink: 0;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        /* CONTENEDOR DEL MAPA CIRCULAR */
        .map-wrapper {
            position: relative;
            width: 900px;
            height: 900px;
            margin: 0 auto;
            background: #fefaf0;
            border-radius: 50%;
        }

        /* ANILLOS CONCÉNTRICOS */
        .concentric-ring {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            border: 1px solid rgba(0, 0, 0, 0.08);
            pointer-events: none;
        }

        .ring-1 { width: 200px; height: 200px; }
        .ring-2 { width: 350px; height: 350px; }
        .ring-3 { width: 500px; height: 500px; }
        .ring-4 { width: 650px; height: 650px; }
        .ring-5 { width: 800px; height: 800px; }

        /* ETIQUETAS DE CAPA */
        .layer-label {
            position: absolute;
            color: #718096;
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.8px;
            pointer-events: none;
            opacity: 0.7;
            background: rgba(254, 250, 240, 0.9);
            padding: 0.3rem 0.6rem;
            border-radius: 4px;
            z-index: 5;
        }

        /* NÚCLEO CENTRAL */
        .core-circle {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 160px;
            height: 160px;
            background: radial-gradient(circle, #1976d2 0%, #1565c0 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            font-weight: 700;
            font-size: 1rem;
            line-height: 1.2;
            padding: 1.5rem;
            cursor: pointer;
            z-index: 20;
            box-shadow: 0 15px 40px rgba(25, 118, 210, 0.3);
            transition: all 0.3s ease;
            border: 3px solid rgba(255, 255, 255, 0.4);
        }

        .core-circle:hover {
            transform: translate(-50%, -50%) scale(1.08);
            box-shadow: 0 20px 50px rgba(25, 118, 210, 0.4);
        }

        /* NODOS DE CAPA */
        .layer-node {
            position: absolute;
            width: 130px;
            height: 130px;
            border-radius: 50%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            font-weight: 600;
            font-size: 0.8rem;
            line-height: 1.1;
            padding: 1rem;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            z-index: 10;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            overflow: hidden;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        /* COLORES DE NODOS */
        .node-intuition { background: linear-gradient(135deg, #e91e63, #c2185b); }
        .node-question { background: linear-gradient(135deg, #2196f3, #1976d2); }
        .node-theme { background: linear-gradient(135deg, #ff9800, #f57c00); }
        .node-action { background: linear-gradient(135deg, #4caf50, #388e3c); }
        .node-bee { background: linear-gradient(135deg, #ffc107, #ffa000); }

        .layer-node:hover {
            transform: scale(1.15);
            z-index: 100;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.25);
            border-color: rgba(255, 255, 255, 0.6);
        }

        /* CONTENIDO DE NODOS */
        .node-title {
            font-weight: 700;
            margin-bottom: 0.3rem;
            font-size: 0.85rem;
            text-shadow: 0 1px 3px rgba(0, 0, 0, 0.4);
        }

        .node-subtitle {
            font-size: 0.7rem;
            opacity: 0.95;
            font-weight: 400;
            text-shadow: 0 1px 2px rgba(0, 0, 0, 0.3);
        }

        /* TOOLTIP */
        .floating-tooltip {
            position: fixed;
            background: rgba(25, 25, 35, 0.95);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.15);
            border-radius: 12px;
            padding: 1.5rem;
            width: 300px;
            z-index: 1000;
            pointer-events: none;
            opacity: 0;
            transform: translate(-50%, -120%) scale(0.95);
            transition: all 0.2s ease;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            color: #f0f0f0;
        }

        .floating-tooltip.active {
            opacity: 1;
            transform: translate(-50%, -120%) scale(1);
        }

        .tooltip-header {
            color: white;
            font-size: 1.1rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid rgba(255, 255, 255, 0.2);
        }

        .tooltip-type {
            display: inline-block;
            background: rgba(255, 255, 255, 0.15);
            padding: 0.2rem 0.6rem;
            border-radius: 12px;
            font-size: 0.7rem;
            margin-bottom: 0.8rem;
            color: rgba(255, 255, 255, 0.9);
        }

        .tooltip-content {
            font-size: 0.9rem;
            line-height: 1.5;
            opacity: 0.9;
        }

        /* CONEXIONES SVG */
        .connections-layer {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            pointer-events: none;
        }

        .connection-line {
            stroke: rgba(0, 0, 0, 0.15);
            stroke-width: 1.5;
            fill: none;
            stroke-linecap: round;
        }

        /* RESPONSIVE */
        @media (max-width: 1200px) {
            .map-wrapper {
                width: 800px;
                height: 800px;
            }
            
            .ring-1 { width: 180px; height: 180px; }
            .ring-2 { width: 320px; height: 320px; }
            .ring-3 { width: 460px; height: 460px; }
            .ring-4 { width: 600px; height: 600px; }
            .ring-5 { width: 780px; height: 780px; }
            
            .layer-node {
                width: 120px;
                height: 120px;
            }
        }

        @media (max-width: 992px) {
            .map-container {
                display: flex;
                flex-direction: column;
            }
            
            .legend-container {
                position: relative;
                top: auto;
                right: auto;
                transform: none;
                width: 100%;
                max-width: 500px;
                margin: 2rem auto;
                order: 2;
            }
            
            .map-wrapper {
                width: 700px;
                height: 700px;
                order: 1;
            }
            
            .ring-1 { width: 160px; height: 160px; }
            .ring-2 { width: 280px; height: 280px; }
            .ring-3 { width: 400px; height: 400px; }
            .ring-4 { width: 520px; height: 520px; }
            .ring-5 { width: 680px; height: 680px; }
        }

        @media (max-width: 768px) {
            .constellation-page {
                padding: 1.5rem;
            }
            
            .page-title {
                font-size: 2rem;
            }
            
            .map-wrapper {
                width: 600px;
                height: 600px;
            }
            
            .ring-1 { width: 140px; height: 140px; }
            .ring-2 { width: 240px; height: 240px; }
            .ring-3 { width: 340px; height: 340px; }
            .ring-4 { width: 440px; height: 440px; }
            .ring-5 { width: 580px; height: 580px; }
            
            .layer-node {
                width: 100px;
                height: 100px;
                font-size: 0.75rem;
                padding: 0.8rem;
            }
            
            .core-circle {
                width: 140px;
                height: 140px;
                font-size: 0.9rem;
                padding: 1.2rem;
            }
        }

        @media (max-width: 650px) {
            .map-wrapper {
                width: 500px;
                height: 500px;
            }
            
            .ring-1 { width: 120px; height: 120px; }
            .ring-2 { width: 210px; height: 210px; }
            .ring-3 { width: 300px; height: 300px; }
            .ring-4 { width: 390px; height: 390px; }
            .ring-5 { width: 480px; height: 480px; }
            
            .layer-node {
                width: 85px;
                height: 85px;
                font-size: 0.7rem;
                padding: 0.6rem;
            }
            
            .node-title {
                font-size: 0.75rem;
            }
            
            .node-subtitle {
                font-size: 0.65rem;
            }
        }

        @media (max-width: 550px) {
            .map-wrapper {
                width: 450px;
                height: 450px;
            }
            
            .ring-1 { width: 100px; height: 100px; }
            .ring-2 { width: 180px; height: 180px; }
            .ring-3 { width: 260px; height: 260px; }
            .ring-4 { width: 340px; height: 340px; }
            .ring-5 { width: 430px; height: 430px; }
            
            .layer-node {
                width: 75px;
                height: 75px;
                padding: 0.5rem;
            }
            
            .floating-tooltip {
                width: 250px;
            }
        }
    </style>
</head>
<body>
    <div class="constellation-page">
        
        <!-- Título y descripción -->
        <h1 class="page-title">Mapa Conceptual: La Ciudad Invisible</h1>
        <div class="page-subtitle">
            Una exploración visual de cómo la belleza urbana oculta violencias estructurales contra especies humanas y no humanas. Pasa el cursor sobre los nodos para ver información detallada.
        </div>
        
        <!-- Contenedor principal -->
        <div class="map-container">
            
            <!-- Leyenda -->
            <div class="legend-container">
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
            
            <!-- Mapa circular -->
            <div class="map-wrapper" id="emotionMap">
                
                <!-- Anillos concéntricos -->
                <div class="concentric-ring ring-1"></div>
                <div class="concentric-ring ring-2"></div>
                <div class="concentric-ring ring-3"></div>
                <div class="concentric-ring ring-4"></div>
                <div class="concentric-ring ring-5"></div>
                
                <!-- Etiquetas de capa -->
                <div class="layer-label" style="top: 50%; left: calc(50% + 175px); transform: translateY(-50%);">Intuiciones</div>
                <div class="layer-label" style="top: 50%; left: calc(50% + 260px); transform: translateY(-50%);">Preguntas</div>
                <div class="layer-label" style="top: 50%; left: calc(50% + 340px); transform: translateY(-50%);">Temas</div>
                <div class="layer-label" style="top: 50%; left: calc(50% + 420px); transform: translateY(-50%);">Acciones</div>
                <div class="layer-label" style="top: 50%; left: calc(50% + 490px); transform: translateY(-50%);">Abejas</div>
                
                <!-- Núcleo central -->
                <div class="core-circle" id="coreNode">
                    LA CIUDAD<br>INVISIBLE
                </div>
                
                <!-- Nodos del mapa -->
                <div id="layerNodes"></div>
                
                <!-- Conexiones SVG -->
                <div class="connections-layer" id="connections"></div>
                
            </div>
        </div>
        
        <!-- Tooltip flotante -->
        <div class="floating-tooltip" id="floatingTooltip">
            <div class="tooltip-header" id="tooltipHeader"></div>
            <div class="tooltip-type" id="tooltipType"></div>
            <div class="tooltip-content" id="tooltipContent"></div>
        </div>
        
    </div>

    <script>
        // ===== DATOS DEL SISTEMA =====
        const constellationData = {
            core: {
                id: "core",
                title: "LA CIUDAD INVISIBLE",
                type: "Concepto Central",
                content: "La ciudad aparece limpia, hermosa y ordenada, pero esta belleza a menudo oculta violencia estructural contra especies humanas y no humanas. Al exponer infraestructuras ocultas de exclusión, podemos pasar de la conciencia → empatía → futuros multiespecies."
            },
            
            intuitions: [
                { id: "i1", title: "Hacer visible lo invisible", subtitle: "Belleza oculta violencia", angle: 30, radius: 2,
                  content: "La belleza urbana esconde infraestructuras de violencia hacia humanos, animales y ecosistemas. Hacer visible lo invisible." },
                { id: "i2", title: "Sentir lo que otros sienten", subtitle: "Empatía requiere vulnerabilidad", angle: 60, radius: 2,
                  content: "La empatía requiere habitar temporalmente vulnerabilidades sensoriales que normalmente no percibimos." },
                { id: "i3", title: "Belleza que engaña", subtitle: "Orden estético disfraza", angle: 90, radius: 2,
                  content: "La ciudad es hermosa, pero algo se siente mal. El orden estético a menudo disfraza exclusión." },
                { id: "i4", title: "Violencia silenciosa", subtitle: "Arquitectónica, estética", angle: 120, radius: 2,
                  content: "La violencia no es solo física, puede ser arquitectónica, estética, silenciosa." },
                { id: "i5", title: "Vidas permitidas, vidas borradas", subtitle: "Cuerpos excluidos", angle: 150, radius: 2,
                  content: "Algunas formas de vida están permitidas, otras son borradas. Las ciudades deciden qué cuerpos habitan." },
                { id: "i6", title: "Naturaleza como decoración", subtitle: "Vida espontánea indeseable", angle: 180, radius: 2,
                  content: "La naturaleza solo es permitida como decoración. La vida espontánea es considerada indeseable." },
                { id: "i7", title: "La vida regresa", subtitle: "Cuando la invitamos", angle: 210, radius: 2,
                  content: "La vida regresa cuando la invitamos de vuelta. Plantas, palomas, abejas persisten." },
                { id: "i8", title: "Empatía a través del cuerpo", subtitle: "No a través de información", angle: 240, radius: 2,
                  content: "La empatía emerge a través de la corporeidad, no de la información. La experiencia sensorial importa." },
                { id: "i9", title: "Diseño antropocéntrico", subtitle: "Ignora otros mundos", angle: 270, radius: 2,
                  content: "El diseño humano ignora mundos sensoriales no humanos. El espacio urbano es antropocéntrico." },
                { id: "i10", title: "Sentir como otra especie", subtitle: "¿Actuaríamos diferente?", angle: 300, radius: 2,
                  content: "Si los humanos pudiéramos sentir como otras especies, ¿actuaríamos diferente?" },
                { id: "i11", title: "Control tras la belleza", subtitle: "Lo 'seguro' puede ser hostil", angle: 330, radius: 2,
                  content: "La ciudad esconde infraestructuras de control tras la belleza. Lo 'seguro' puede ser hostil." },
                { id: "i12", title: "Pequeños actos", subtitle: "Revelan sistemas grandes", angle: 360, radius: 2,
                  content: "Intervenciones pequeñas revelan sistemas grandes. Micro-acciones descubren macro-patrones." }
            ],
            
            questions: [
                { id: "q1", title: "¿Qué vidas están permitidas?", subtitle: "En la ciudad", angle: 45, radius: 3,
                  content: "¿Qué vidas están permitidas en la ciudad? ¿Qué cuerpos pueden descansar?" },
                { id: "q2", title: "Violencia estetizada", subtitle: "Sanitizada por belleza", angle: 90, radius: 3,
                  content: "¿Cómo se sanitiza la violencia a través de la estética? ¿Diseñarían diferente otras especies?" },
                { id: "q3", title: "Traducir sentidos", subtitle: "Mundos no humanos", angle: 135, radius: 3,
                  content: "¿Cómo traducir mundos sensoriales no humanos? ¿La experiencia corpórea revela?" },
                { id: "q4", title: "Conciencia → acción", subtitle: "Camino de transformación", angle: 180, radius: 3,
                  content: "¿Cómo pasar de conciencia → empatía → acción? ¿Crear empatía multiespecies?" },
                { id: "q5", title: "Sistemas ocultos", subtitle: "Hacerlos visibles", angle: 225, radius: 3,
                  content: "Hacer visibles infraestructuras de control ocultas a través del diseño." },
                { id: "q6", title: "Justicia multiespecies", subtitle: "Coexistencia urbana", angle: 270, radius: 3,
                  content: "¿Justicia para residentes no humanos? Diseñar para coexistencia multiespecies." },
                { id: "q7", title: "Métodos de traducción", subtitle: "Herramientas sensoriales", angle: 315, radius: 3,
                  content: "Métodos para traducir visión UV, vibraciones, señales químicas para humanos." },
                { id: "q8", title: "Empatía → cambio", subtitle: "Transformación urbana", angle: 360, radius: 3,
                  content: "¿Cómo traduce la empatía corpórea en cambio sistémico urbano?" }
            ],
            
            themes: [
                { id: "t1", title: "Estética Urbana", subtitle: "Belleza como política", angle: 60, radius: 4,
                  content: "Belleza, orden, limpieza como herramientas políticas. Control visual impulsado por turismo." },
                { id: "t2", title: "Diseño Hostil", subtitle: "Arquitectura que expulsa", angle: 120, radius: 4,
                  content: "Arquitectura anti-personas sin hogar. Picos anti-palomas. Superficies que niegan descanso." },
                { id: "t3", title: "Justicia Multiespecies", subtitle: "Derechos más allá humanos", angle: 180, radius: 4,
                  content: "Derecho a presencia, descanso, refugio. Ciudadanía no humana. Vulnerabilidades compartidas." },
                { id: "t4", title: "Investigación Corpórea", subtitle: "Cuerpo como sensor", angle: 240, radius: 4,
                  content: "El cuerpo como sensor. Caminata etnográfica. Sentir la arquitectura." },
                { id: "t5", title: "Traducción Sensorial", subtitle: "Entre especies", angle: 300, radius: 4,
                  content: "Traducir sentidos no humanos. Interfaces para comprensión multiespecies." },
                { id: "t6", title: "Empatía Ambiental", subtitle: "Sentir-con ecosistemas", angle: 360, radius: 4,
                  content: "Empatía hacia ecosistemas. Comunicación entre especies. Conexión emocional." }
            ],
            
            actions: [
                { id: "a1", title: "Sentarse en lo Hostil", subtitle: "Cuerpo como sensor", angle: 60, radius: 5,
                  content: "Sentarse en arquitectura hostil. Revelar micro-violencia a través del cuerpo." },
                { id: "a2", title: "Vestir la Hostilidad", subtitle: "Traducción material", angle: 120, radius: 5,
                  content: "Transferir picos anti-palomas al cuerpo humano. Hacer visible la violencia arquitectónica." },
                { id: "a3", title: "Devolver la Vida", subtitle: "Actos de renaturalización", angle: 180, radius: 5,
                  content: "Plantar vida espontánea en concreto. Tierra, semillas, graffiti de musgo." },
                { id: "a4", title: "Belleza que Excluye", subtitle: "Documentar el borrado", angle: 240, radius: 5,
                  content: "Documentar borrado estético. Mapa de Fotografía de Violencia Urbana." },
                { id: "a5", title: "Infraestructuras Ocultas", subtitle: "Patrones de control", angle: 300, radius: 5,
                  content: "Documentar infraestructuras ocultas. Patrones de control en zonas turísticas." },
                { id: "a6", title: "Experimentos Sensoriales", subtitle: "Interfaces de percepción", angle: 360, radius: 5,
                  content: "Prototipar dispositivos de traducción sensorial entre modalidades y especies." }
            ],
            
            beeProject: [
                { id: "b1", title: "Vulnerabilidades", subtitle: "Pesticidas, hábitat", angle: 60, radius: 6,
                  content: "Pesticidas, fragmentación de hábitat, monocultivos urbanos, islas de calor." },
                { id: "b2", title: "Mundo Sensorial", subtitle: "Visión UV, vibraciones", angle: 120, radius: 6,
                  content: "Visión UV, comunicación vibratoria, señalización química, memoria espacial." },
                { id: "b3", title: "Conflictos", subtitle: "Remoción estética", angle: 180, radius: 6,
                  content: "Colmenas removidas por estética. Exterminio impulsado por miedo." },
                { id: "b4", title: "Violencia Sistémica", subtitle: "Sistemas agrícolas", angle: 240, radius: 6,
                  content: "Agricultura corporativa, pesticidas industriales, 'embellecimiento' urbano." },
                { id: "b5", title: "Traducción", subtitle: "Métodos tecnológicos", angle: 300, radius: 6,
                  content: "Sensores que convierten vibraciones en sonido. Mapeo UV. Pulsos hápticos." },
                { id: "b6", title: "Camino de Empatía", subtitle: "Conciencia → acción", angle: 360, radius: 6,
                  content: "Conciencia → Experiencia Corpórea → Empatía Multiespecies → Acción." }
            ]
        };

        // ===== FUNCIONES DEL MAPA =====
        function buildConstellationMap() {
            const container = document.getElementById('layerNodes');
            container.innerHTML = '';
            
            // Construir capas
            buildLayer(constellationData.intuitions, 'intuition');
            buildLayer(constellationData.questions, 'question');
            buildLayer(constellationData.themes, 'theme');
            buildLayer(constellationData.actions, 'action');
            buildLayer(constellationData.beeProject, 'bee');
            
            // Configurar núcleo
            setupCoreNode();
            
            // Crear conexiones
            setTimeout(() => {
                createConnections();
            }, 100);
        }

        function buildLayer(nodes, type) {
            const container = document.getElementById('layerNodes');
            const mapWrapper = document.getElementById('emotionMap');
            const mapRect = mapWrapper.getBoundingClientRect();
            const centerX = mapRect.width / 2;
            const centerY = mapRect.height / 2;
            
            nodes.forEach(node => {
                // Calcular posición
                const radius = node.radius * 60; // Factor de escala
                const angleRad = (node.angle * Math.PI) / 180;
                
                const x = centerX + (radius * Math.cos(angleRad));
                const y = centerY + (radius * Math.sin(angleRad));
                
                // Crear nodo
                const nodeElement = document.createElement('div');
                nodeElement.className = `layer-node node-${type}`;
                nodeElement.style.left = `${x}px`;
                nodeElement.style.top = `${y}px`;
                nodeElement.dataset.id = node.id;
                nodeElement.dataset.type = type;
                
                // Contenido del nodo
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
                    showTooltip(node, type, e);
                    highlightNode(nodeElement);
                });
                
                nodeElement.addEventListener('mouseleave', () => {
                    hideTooltip();
                    resetNode(nodeElement);
                });
                
                container.appendChild(nodeElement);
            });
        }

        function setupCoreNode() {
            const coreNode = document.getElementById('coreNode');
            
            coreNode.addEventListener('mouseenter', (e) => {
                showTooltip(constellationData.core, 'core', e);
            });
            
            coreNode.addEventListener('mouseleave', () => {
                hideTooltip();
            });
        }

        function createConnections() {
            const container = document.getElementById('connections');
            container.innerHTML = '';
            
            const svg = document.createElementNS("http://www.w3.org/2000/svg", "svg");
            svg.setAttribute("width", "100%");
            svg.setAttribute("height", "100%");
            svg.style.position = "absolute";
            svg.style.top = "0";
            svg.style.left = "0";
            
            // Conexiones principales
            const connections = [
                ['core', 'i1'], ['core', 'i6'], ['core', 't3'],
                ['i1', 'q1'], ['i4', 'q5'], ['i10', 'b2'],
                ['t1', 'q2'], ['t2', 'a4'], ['t3', 'b1'],
                ['t4', 'a1'], ['t5', 'b5'], ['t6', 'b6']
            ];
            
            connections.forEach(([sourceId, targetId]) => {
                const source = sourceId === 'core' 
                    ? document.getElementById('coreNode')
                    : document.querySelector(`[data-id="${sourceId}"]`);
                const target = document.querySelector(`[data-id="${targetId}"]`);
                
                if (source && target) {
                    const line = createConnectionLine(source, target);
                    svg.appendChild(line);
                }
            });
            
            container.appendChild(svg);
        }

        function createConnectionLine(source, target) {
            const sourceRect = source.getBoundingClientRect();
            const targetRect = target.getBoundingClientRect();
            const container = document.getElementById('emotionMap');
            const containerRect = container.getBoundingClientRect();
            
            // Calcular posiciones relativas al contenedor
            const x1 = sourceRect.left + sourceRect.width/2 - containerRect.left;
            const y1 = sourceRect.top + sourceRect.height/2 - containerRect.top;
            const x2 = targetRect.left + targetRect.width/2 - containerRect.left;
            const y2 = targetRect.top + targetRect.height/2 - containerRect.top;
            
            const line = document.createElementNS("http://www.w3.org/2000/svg", "line");
            line.setAttribute("x1", x1);
            line.setAttribute("y1", y1);
            line.setAttribute("x2", x2);
            line.setAttribute("y2", y2);
            line.classList.add("connection-line");
            
            return line;
        }

        // ===== TOOLTIP =====
        const tooltip = document.getElementById('floatingTooltip');
        const tooltipHeader = document.getElementById('tooltipHeader');
        const tooltipType = document.getElementById('tooltipType');
        const tooltipContent = document.getElementById('tooltipContent');

        function showTooltip(node, type, event) {
            tooltipHeader.textContent = node.title;
            
            // Traducir tipo
            const typeNames = {
                'intuition': 'Intuición',
                'question': 'Pregunta Motor',
                'theme': 'Campo Temático',
                'action': 'Acción como Conocimiento',
                'bee': 'Proyecto Abeja',
                'core': 'Concepto Central'
            };
            
            tooltipType.textContent = typeNames[type] || type;
            tooltipContent.textContent = node.content;
            
            // Posicionar
            const x = event.clientX;
            const y = event.clientY - 20;
            
            tooltip.style.left = `${x}px`;
            tooltip.style.top = `${y}px`;
            tooltip.classList.add('active');
        }

        function hideTooltip() {
            tooltip.classList.remove('active');
        }

        // ===== EFECTOS =====
        function highlightNode(node) {
            node.style.transform = 'scale(1.15)';
            node.style.zIndex = '100';
            node.style.boxShadow = '0 20px 50px rgba(0, 0, 0, 0.3)';
        }

        function resetNode(node) {
            node.style.transform = '';
            node.style.zIndex = '';
            node.style.boxShadow = '';
        }

        // ===== INICIALIZACIÓN =====
        document.addEventListener('DOMContentLoaded', () => {
            buildConstellationMap();
            
            // Redimensionar
            window.addEventListener('resize', () => {
                setTimeout(buildConstellationMap, 100);
            });
            
            // Mover tooltip con mouse
            document.addEventListener('mousemove', (e) => {
                if (tooltip.classList.contains('active')) {
                    const x = e.clientX;
                    const y = e.clientY - 20;
                    tooltip.style.left = `${x}px`;
                    tooltip.style.top = `${y}px`;
                }
            });
        });
    </script>
</body>
</html>