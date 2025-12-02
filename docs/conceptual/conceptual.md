<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE INVISIBLE CITY - Constellation Map</title>
    <style>
        /* =============================================== */
        /* MAPA PANTALLA COMPLETA - OBJETOS GIGANTES */
        /* =============================================== */

        /* RESET Y BASE */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
            background: #050509;
        }

        /* ESTÉTICA GLOBAL - FONDO ESPACIAL LIMPIO */
        :root {
            /* Paleta cósmica refinada */
            --space-black: #050509;
            --core-gradient: linear-gradient(135deg, #1C64F2 0%, #FFDD00 100%);
            --magenta-intuition: #B51EFF;
            --violet-injustice: #8A3FFC;
            --amber-hostility: #FF9F1C;
            --pollen-yellow: #FFDD00;
            --eco-green: #00C49A;
            --toxicity-red: #E11D48;
            --data-blue: #1C64F2;
            --fog-white: #F2F2F2;
            --emergent-blue: #00D4FF;
            
            /* TAMAÑOS DE ÓRBITAS EN PORCENTAJE - MUCHO MÁS GRANDES */
            --orbit-intuitions: 20vh;     /* Orbits en viewport height */
            --orbit-questions: 35vh;
            --orbit-themes: 50vh;
            --orbit-actions: 65vh;
            --orbit-futures: 80vh;
        }
        
        @import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&display=swap');
        
        /* CONTENEDOR PRINCIPAL - 100% PANTALLA */
        .galaxy-constellation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: var(--space-black);
            overflow: hidden;
            font-family: 'Space Grotesk', 'Inter', -apple-system, sans-serif;
            font-weight: 600;
        }
        
        /* TEXTURA DE ESTRELLAS SUBTIL */
        .star-field {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(2px 2px at 10% 15%, rgba(255, 255, 255, 0.05) 2px, transparent 0),
                radial-gradient(2px 2px at 20% 45%, rgba(255, 221, 0, 0.03) 2px, transparent 0),
                radial-gradient(2px 2px at 30% 75%, rgba(138, 63, 252, 0.04) 2px, transparent 0),
                radial-gradient(2px 2px at 40% 25%, rgba(28, 100, 242, 0.05) 2px, transparent 0),
                radial-gradient(3px 3px at 50% 55%, rgba(255, 255, 255, 0.03) 3px, transparent 0),
                radial-gradient(2px 2px at 60% 85%, rgba(255, 46, 136, 0.04) 2px, transparent 0),
                radial-gradient(2px 2px at 70% 35%, rgba(0, 212, 255, 0.03) 2px, transparent 0),
                radial-gradient(2px 2px at 80% 65%, rgba(0, 196, 154, 0.05) 2px, transparent 0);
            background-size: 500px 500px;
            animation: star-twinkle 25s infinite alternate;
            z-index: 1;
            opacity: 0.6;
        }
        
        @keyframes star-twinkle {
            0%, 100% { opacity: 0.4; }
            50% { opacity: 0.8; }
        }
        
        /* ÓRBITAS - MUY TENUES */
        .galaxy-orbit {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            border: 1px solid;
            opacity: 0.03;
            z-index: 2;
        }
        
        .orbit-1 { width: var(--orbit-intuitions); height: var(--orbit-intuitions); border-color: var(--magenta-intuition); }
        .orbit-2 { width: var(--orbit-questions); height: var(--orbit-questions); border-color: var(--fog-white); }
        .orbit-3 { width: var(--orbit-themes); height: var(--orbit-themes); border-color: var(--data-blue); }
        .orbit-4 { width: var(--orbit-actions); height: var(--orbit-actions); border-color: var(--amber-hostility); }
        .orbit-5 { width: var(--orbit-futures); height: var(--orbit-futures); border-color: var(--emergent-blue); }
        
        /* ===== SISTEMA DE NODOS - TAMAÑOS GIGANTES ===== */
        
        /* CLASE BASE PARA TODOS LOS NODOS */
        .cosmic-node {
            position: absolute;
            cursor: pointer;
            z-index: 10;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            font-weight: 600;
            animation: cosmic-float 10s ease-in-out infinite;
            filter: drop-shadow(0 0 30px rgba(0, 0, 0, 0.5));
            padding: 20px;
            box-sizing: border-box;
            overflow: hidden;
            transform: translate(-50%, -50%);
        }
        
        @keyframes cosmic-float {
            0%, 100% { transform: translate(-50%, -50%) scale(1); }
            50% { transform: translate(-50%, -50%) scale(1.02); }
        }
        
        /* CONTENEDOR DE CONTENIDO */
        .node-content {
            position: relative;
            z-index: 3;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            width: 100%;
            height: 100%;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.7);
            color: var(--fog-white);
            font-size: 1.1rem;
            line-height: 1.4;
            letter-spacing: 0.02em;
            word-wrap: break-word;
            overflow-wrap: break-word;
            hyphens: auto;
            padding: 15px;
        }
        
        /* LÍMITE DE CARACTERES POR LÍNEA */
        .node-title {
            font-weight: 700;
            margin-bottom: 0.5rem;
            max-width: 100%;
            word-break: break-word;
            font-size: 1.3rem;
        }
        
        .node-subtitle {
            font-size: 1rem;
            opacity: 0.9;
            font-weight: 500;
            max-width: 100%;
            word-break: break-word;
        }
        
        /* ===== TIPOS DE NODOS - TAMAÑOS ENORMES ===== */
        
        /* 🌞 NÚCLEO - CÍRCULO GIGANTE */
        .node-type-core {
            width: 300px !important;
            height: 300px !important;
            border-radius: 50%;
            background: radial-gradient(
                circle at center,
                #1C64F2 0%,
                #1C64F2 40%,
                rgba(28, 100, 242, 0.2) 70%,
                transparent 100%
            );
            box-shadow: 
                inset 0 0 60px rgba(255, 255, 255, 0.4),
                0 0 120px rgba(28, 100, 242, 0.6);
            animation: core-pulse 8s ease-in-out infinite;
        }
        
        @keyframes core-pulse {
            0%, 100% { 
                box-shadow: 
                    inset 0 0 60px rgba(255, 255, 255, 0.4),
                    0 0 120px rgba(28, 100, 242, 0.6);
            }
            50% { 
                box-shadow: 
                    inset 0 0 80px rgba(255, 255, 255, 0.5),
                    0 0 160px rgba(28, 100, 242, 0.8);
            }
        }
        
        /* 💎 INTUICIONES - ROMBOS GRANDES */
        .node-type-intuition {
            width: 180px !important;
            height: 180px !important;
            background: radial-gradient(
                circle at center,
                var(--magenta-intuition) 0%,
                var(--magenta-intuition) 40%,
                rgba(181, 30, 255, 0.2) 70%,
                transparent 100%
            );
            clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
            box-shadow: 
                inset 0 0 30px rgba(255, 255, 255, 0.3),
                0 0 60px rgba(181, 30, 255, 0.4);
        }
        
        /* 🧠 PREGUNTAS - HEXÁGONOS GRANDES */
        .node-type-question {
            width: 170px !important;
            height: 170px !important;
            background: radial-gradient(
                circle at center,
                rgba(242, 242, 242, 0.95) 0%,
                rgba(242, 242, 242, 0.95) 40%,
                rgba(242, 242, 242, 0.2) 70%,
                transparent 100%
            );
            clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
            color: var(--space-black);
            box-shadow: 
                inset 0 0 30px rgba(255, 255, 255, 0.4),
                0 0 50px rgba(242, 242, 242, 0.4);
        }
        
        /* 🟣 CAMPOS TEÓRICOS - CÍRCULOS GRANDES */
        .node-type-theme {
            width: 220px !important;
            height: 220px !important;
            border-radius: 50%;
            box-shadow: 
                inset 0 0 40px rgba(255, 255, 255, 0.3),
                0 0 80px currentColor;
            background: radial-gradient(
                circle at center,
                currentColor 0%,
                currentColor 40%,
                rgba(255, 255, 255, 0.15) 70%,
                transparent 100%
            );
        }
        
        /* ◉ ACCIONES - CÍRCULO DOBLE BORDE GRANDE */
        .node-type-action {
            width: 200px !important;
            height: 200px !important;
            border-radius: 50%;
            background: transparent;
            border: 4px solid;
            box-shadow: 
                inset 0 0 40px rgba(255, 255, 255, 0.3),
                0 0 80px currentColor;
            position: relative;
        }
        
        .node-type-action::before {
            content: '';
            position: absolute;
            top: 20%;
            left: 20%;
            right: 20%;
            bottom: 20%;
            border-radius: 50%;
            border: 3px solid;
            opacity: 0.4;
        }
        
        /* ⭐ FUTUROS - ESTRELLAS GRANDES */
        .node-type-future {
            width: 200px !important;
            height: 200px !important;
            background: radial-gradient(
                circle at center,
                var(--emergent-blue) 0%,
                var(--emergent-blue) 40%,
                rgba(0, 212, 255, 0.2) 70%,
                transparent 100%
            );
            clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
            box-shadow: 
                inset 0 0 35px rgba(255, 255, 255, 0.3),
                0 0 60px rgba(0, 212, 255, 0.4);
            animation: star-sparkle 6s ease-in-out infinite;
        }
        
        @keyframes star-sparkle {
            0%, 100% { opacity: 0.95; transform: translate(-50%, -50%) scale(1) rotate(0deg); }
            50% { opacity: 1; transform: translate(-50%, -50%) scale(1.05) rotate(3deg); }
        }
        
        /* ✦ MICRO-NODOS MÁS GRANDES */
        .node-type-micro {
            width: 40px !important;
            height: 40px !important;
            border-radius: 50%;
            background: radial-gradient(
                circle at center,
                var(--fog-white) 0%,
                var(--fog-white) 50%,
                transparent 80%
            );
            font-size: 0;
            box-shadow: 0 0 20px currentColor;
            animation: micro-pulse 3s ease-in-out infinite;
        }
        
        @keyframes micro-pulse {
            0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0.6; }
            50% { transform: translate(-50%, -50%) scale(1.3); opacity: 0.9; }
        }
        
        /* ===== COLORES ESPECÍFICOS ===== */
        
        /* Temas teóricos */
        .theme-urban { color: var(--violet-injustice); }
        .theme-urban .node-content { color: var(--fog-white); }
        
        .theme-hostile { color: var(--amber-hostility); }
        .theme-hostile .node-content { color: var(--space-black); }
        
        .theme-species { color: var(--pollen-yellow); }
        .theme-species .node-content { color: var(--space-black); }
        
        .theme-research { color: var(--eco-green); }
        .theme-research .node-content { color: var(--fog-white); }
        
        .theme-sensory { color: var(--toxicity-red); }
        .theme-sensory .node-content { color: var(--fog-white); }
        
        /* Acciones */
        .action-amber { color: var(--amber-hostility); }
        .action-green { color: var(--eco-green); }
        .action-red { color: var(--toxicity-red); }
        .action-blue { color: var(--data-blue); }
        
        /* Micro-nodos coloreados */
        .micro-care { color: var(--eco-green); }
        .micro-friction { color: var(--amber-hostility); }
        .micro-presence { color: var(--violet-injustice); }
        .micro-erasure { color: var(--toxicity-red); }
        .micro-vulnerability { color: var(--magenta-intuition); }
        .micro-coexistence { color: var(--pollen-yellow); }
        
        /* ===== EFECTOS HOVER REFINADOS ===== */
        
        .cosmic-node:hover {
            z-index: 100 !important;
            transform: translate(-50%, -50%) scale(1.15) !important;
            filter: brightness(1.3) drop-shadow(0 0 40px rgba(255, 255, 255, 0.3));
        }
        
        .node-type-core:hover {
            box-shadow: 
                inset 0 0 80px rgba(255, 255, 255, 0.5),
                0 0 160px rgba(28, 100, 242, 0.8);
        }
        
        .node-type-future:hover {
            animation: star-sparkle-hover 1s ease-in-out infinite;
        }
        
        @keyframes star-sparkle-hover {
            0%, 100% { opacity: 1; transform: translate(-50%, -50%) scale(1.15) rotate(0deg); }
            50% { opacity: 1; transform: translate(-50%, -50%) scale(1.2) rotate(5deg); }
        }
        
        /* ===== CONEXIONES - MÁS GRUESAS ===== */
        
        .cosmic-connection {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 4;
            pointer-events: none;
        }
        
        .cosmic-connection path {
            transition: all 0.3s ease;
        }
        
        /* ===== TOOLTIP ELEGANTE ===== */
        
        .cosmic-tooltip {
            position: fixed;
            background: rgba(5, 5, 9, 0.95);
            border: 1px solid rgba(242, 242, 242, 0.15);
            border-radius: 16px;
            padding: 2rem;
            max-width: 400px;
            z-index: 1000;
            pointer-events: none;
            opacity: 0;
            transform: translateY(20px) scale(0.98);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 
                0 20px 60px rgba(0, 0, 0, 0.6),
                0 0 0 1px rgba(28, 100, 242, 0.15);
            backdrop-filter: blur(15px);
            font-size: 1.1rem;
            line-height: 1.6;
            font-weight: 400;
        }
        
        .cosmic-tooltip.active {
            opacity: 1;
            transform: translateY(0) scale(1);
        }
        
        .tooltip-title {
            color: var(--data-blue);
            font-weight: 700;
            margin-bottom: 1rem;
            font-size: 1.4rem;
            letter-spacing: 0.03em;
        }
        
        .tooltip-content {
            opacity: 0.9;
            font-weight: 300;
            font-size: 1rem;
        }
        
        /* ===== LEYENDA DISCRETA ===== */
        
        .galaxy-legend {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: rgba(5, 5, 9, 0.85);
            border: 1px solid rgba(242, 242, 242, 0.1);
            border-radius: 20px;
            padding: 1.5rem;
            z-index: 50;
            backdrop-filter: blur(20px);
            max-width: 280px;
            box-shadow: 0 12px 40px rgba(0, 0, 0, 0.4);
            transition: all 0.3s ease;
            opacity: 0.9;
        }
        
        .legend-title {
            color: rgba(242, 242, 242, 0.9);
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 1.2rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .legend-toggle {
            background: none;
            border: none;
            color: rgba(242, 242, 242, 0.7);
            cursor: pointer;
            font-size: 1.3rem;
            line-height: 1;
            padding: 0.3rem;
            border-radius: 6px;
            transition: all 0.2s ease;
        }
        
        .legend-toggle:hover {
            background: rgba(242, 242, 242, 0.15);
            color: var(--fog-white);
        }
        
        .legend-content {
            transition: all 0.3s ease;
        }
        
        .legend-item {
            display: flex;
            align-items: center;
            margin-bottom: 0.9rem;
            font-size: 0.9rem;
            opacity: 0.9;
            color: rgba(242, 242, 242, 0.95);
        }
        
        .legend-shape {
            width: 24px;
            height: 24px;
            margin-right: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 6px;
            flex-shrink: 0;
        }
        
        /* ===== BOTÓN FULLSCREEN ===== */
        .fullscreen-toggle {
            position: fixed;
            top: 2rem;
            right: 2rem;
            background: rgba(5, 5, 9, 0.8);
            border: 1px solid rgba(242, 242, 242, 0.15);
            border-radius: 12px;
            padding: 0.8rem 1.2rem;
            z-index: 50;
            backdrop-filter: blur(10px);
            color: var(--fog-white);
            font-family: 'Space Grotesk', sans-serif;
            font-size: 0.9rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .fullscreen-toggle:hover {
            background: rgba(28, 100, 242, 0.3);
            border-color: var(--data-blue);
        }
        
        /* ===== RESPONSIVE PARA PANTALLAS PEQUEÑAS ===== */
        
        @media (max-width: 1024px) {
            :root {
                --orbit-intuitions: 18vh;
                --orbit-questions: 30vh;
                --orbit-themes: 42vh;
                --orbit-actions: 55vh;
                --orbit-futures: 70vh;
            }
            
            .node-type-core { width: 250px !important; height: 250px !important; }
            .node-type-intuition { width: 150px !important; height: 150px !important; }
            .node-type-question { width: 140px !important; height: 140px !important; }
            .node-type-theme { width: 180px !important; height: 180px !important; }
            .node-type-action { width: 160px !important; height: 160px !important; }
            .node-type-future { width: 160px !important; height: 160px !important; }
            
            .node-content {
                font-size: 1rem;
                padding: 12px;
            }
            
            .node-title {
                font-size: 1.1rem;
            }
            
            .node-subtitle {
                font-size: 0.9rem;
            }
            
            .cosmic-tooltip {
                max-width: 350px;
                padding: 1.5rem;
            }
        }
        
        @media (max-width: 768px) {
            :root {
                --orbit-intuitions: 15vh;
                --orbit-questions: 25vh;
                --orbit-themes: 35vh;
                --orbit-actions: 45vh;
                --orbit-futures: 60vh;
            }
            
            .node-type-core { width: 200px !important; height: 200px !important; }
            .node-type-intuition { width: 120px !important; height: 120px !important; }
            .node-type-question { width: 110px !important; height: 110px !important; }
            .node-type-theme { width: 140px !important; height: 140px !important; }
            .node-type-action { width: 130px !important; height: 130px !important; }
            .node-type-future { width: 130px !important; height: 130px !important; }
            
            .node-content {
                font-size: 0.9rem;
                padding: 10px;
            }
            
            .node-title {
                font-size: 1rem;
            }
            
            .node-subtitle {
                font-size: 0.85rem;
            }
            
            .galaxy-legend {
                max-width: 220px;
                padding: 1rem;
                right: 1rem;
                bottom: 1rem;
            }
            
            .fullscreen-toggle {
                top: 1rem;
                right: 1rem;
                padding: 0.6rem 1rem;
                font-size: 0.8rem;
            }
        }
        
        @media (max-width: 480px) {
            :root {
                --orbit-intuitions: 12vh;
                --orbit-questions: 20vh;
                --orbit-themes: 28vh;
                --orbit-actions: 38vh;
                --orbit-futures: 50vh;
            }
            
            .node-type-core { width: 160px !important; height: 160px !important; }
            .node-type-intuition { width: 100px !important; height: 100px !important; }
            .node-type-question { width: 90px !important; height: 90px !important; }
            .node-type-theme { width: 110px !important; height: 110px !important; }
            .node-type-action { width: 100px !important; height: 100px !important; }
            .node-type-future { width: 100px !important; height: 100px !important; }
            
            .node-content {
                font-size: 0.8rem;
                padding: 8px;
            }
            
            .node-title {
                font-size: 0.9rem;
            }
            
            .node-subtitle {
                font-size: 0.75rem;
            }
            
            .galaxy-legend {
                display: none;
            }
            
            .cosmic-tooltip {
                max-width: 300px;
                padding: 1.2rem;
                font-size: 0.9rem;
            }
            
            .tooltip-title {
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>
    <!-- =============================================== -->
    <!-- MAPA GALÁCTICO PANTALLA COMPLETA -->
    <!-- =============================================== -->

    <div class="galaxy-constellation" id="galaxyMap">
        <!-- Fondo estrellado sutil -->
        <div class="star-field"></div>
        
        <!-- Órbitas muy tenues -->
        <div class="galaxy-orbit orbit-1"></div>
        <div class="galaxy-orbit orbit-2"></div>
        <div class="galaxy-orbit orbit-3"></div>
        <div class="galaxy-orbit orbit-4"></div>
        <div class="galaxy-orbit orbit-5"></div>
        
        <!-- Contenedor de nodos -->
        <div id="cosmicNodes"></div>
        
        <!-- Contenedor de conexiones -->
        <div id="cosmicConnections"></div>
        
        <!-- Contenedor de micro-nodos -->
        <div id="microNodes"></div>
        
        <!-- Tooltip elegante -->
        <div class="cosmic-tooltip" id="cosmicTooltip">
            <div class="tooltip-title" id="tooltipTitle"></div>
            <div class="tooltip-content" id="tooltipContent"></div>
        </div>
        
        <!-- Leyenda discreta -->
        <div class="galaxy-legend" id="galaxyLegend">
            <div class="legend-title">
                <span>MAP LEGEND</span>
                <button class="legend-toggle" id="legendToggle">−</button>
            </div>
            <div class="legend-content" id="legendContent">
                <div class="legend-item">
                    <div class="legend-shape node-type-core" style="transform: scale(0.6);"></div>
                    <span>Core Concept</span>
                </div>
                <div class="legend-item">
                    <div class="legend-shape node-type-intuition" style="transform: scale(0.7);"></div>
                    <span>Intuitions</span>
                </div>
                <div class="legend-item">
                    <div class="legend-shape node-type-question" style="transform: scale(0.7);"></div>
                    <span>Motor Questions</span>
                </div>
                <div class="legend-item">
                    <div class="legend-shape node-type-theme theme-urban" style="transform: scale(0.7);"></div>
                    <span>Thematic Fields</span>
                </div>
                <div class="legend-item">
                    <div class="legend-shape node-type-action action-amber" style="transform: scale(0.7);"></div>
                    <span>Actions as Knowledge</span>
                </div>
                <div class="legend-item">
                    <div class="legend-shape node-type-future" style="transform: scale(0.7);"></div>
                    <span>Emergent Futures</span>
                </div>
            </div>
        </div>
        
        <!-- Botón Fullscreen -->
        <button class="fullscreen-toggle" id="fullscreenToggle">Fullscreen</button>
    </div>

    <script>
        // ===== CONFIGURACIÓN DE NODOS =====
        const galaxyData = {
            core: {
                id: "core",
                type: "core",
                title: "THE INVISIBLE CITY",
                content: "Urban aesthetics conceal systemic violence against human and non-human life.",
                tooltip: "The central intuition: what we call beautiful in cities often systematically excludes certain lives and species.",
                x: 50,
                y: 50
            },
            
            intuitions: [
                {
                    id: "intuition1",
                    type: "intuition",
                    title: "Beauty excludes",
                    content: "Aesthetic standards as tools of power",
                    tooltip: "Clean spaces, curated nature, orderly facades that make some lives 'dirt' and others 'proper'.",
                    angle: 0,
                    orbit: 1
                },
                {
                    id: "intuition2",
                    type: "intuition",
                    title: "Violence hidden",
                    content: "Aesthetics mask structural harm",
                    tooltip: "The violence of absence: what is systematically removed or made invisible in the name of beauty.",
                    angle: 90,
                    orbit: 1
                },
                {
                    id: "intuition3",
                    type: "intuition",
                    title: "Nature expelled",
                    content: "Non-curated life removed",
                    tooltip: "Plants as decoration, animals as pests, ecosystems as 'mess' to be cleaned from urban spaces.",
                    angle: 180,
                    orbit: 1
                },
                {
                    id: "intuition4",
                    type: "intuition",
                    title: "Order as control",
                    content: "Disguised as care, enacted as power",
                    tooltip: "Safety measures that exclude, cleanliness that erases, maintenance that displaces vulnerable lives.",
                    angle: 270,
                    orbit: 1
                }
            ],
            
            questions: [
                {
                    id: "question1",
                    type: "question",
                    title: "Who can rest?",
                    content: "Politics of pause in public space",
                    tooltip: "Questioning benches designed against sleeping, surfaces that deny comfort, temporal restrictions on presence.",
                    angle: 0,
                    orbit: 2
                },
                {
                    id: "question2",
                    type: "question",
                    title: "Whose lives matter?",
                    content: "Hierarchy of urban citizenship",
                    tooltip: "From homeless humans to pigeons: which lives are welcomed, tolerated, or actively eliminated in cities?",
                    angle: 60,
                    orbit: 2
                },
                {
                    id: "question3",
                    type: "question",
                    title: "Beauty justifies?",
                    content: "Aesthetic rationale for exclusion",
                    tooltip: "How visual pleasure becomes an alibi for systemic violence in urban 'improvement' projects.",
                    angle: 120,
                    orbit: 2
                },
                {
                    id: "question4",
                    type: "question",
                    title: "Design empathy?",
                    content: "Cross-species understanding",
                    tooltip: "Can interfaces, installations, or experiences help humans feel what other species feel in cities?",
                    angle: 180,
                    orbit: 2
                },
                {
                    id: "question5",
                    type: "question",
                    title: "Normalized violence?",
                    content: "Invisible systemic harm",
                    tooltip: "The violence of spikes on ledges, smooth benches, pesticide spraying, constant noise pollution.",
                    angle: 240,
                    orbit: 2
                },
                {
                    id: "question6",
                    type: "question",
                    title: "Species design?",
                    content: "Non-human urban planning",
                    tooltip: "What would a pigeon's ideal plaza look like? A bee's transportation system? A tree's housing development?",
                    angle: 300,
                    orbit: 2
                }
            ],
            
            themes: [
                {
                    id: "theme1",
                    type: "theme",
                    title: "Urban Aesthetics",
                    colorClass: "theme-urban",
                    content: "Politics of beauty",
                    tooltip: "How aesthetic standards in urban design serve to normalize exclusion and control. Beauty as ideology.",
                    angle: 0,
                    orbit: 3
                },
                {
                    id: "theme2",
                    type: "theme",
                    title: "Hostile Design",
                    colorClass: "theme-hostile",
                    content: "Architecture expels",
                    tooltip: "Anti-homeless benches, pigeon spikes, seating deterrents. Violence normalized through design.",
                    angle: 60,
                    orbit: 3
                },
                {
                    id: "theme3",
                    type: "theme",
                    title: "Multispecies Justice",
                    colorClass: "theme-species",
                    content: "Beyond human rights",
                    tooltip: "Questioning anthropocentric cities. Rights to shelter, food, movement for all species.",
                    angle: 120,
                    orbit: 3
                },
                {
                    id: "theme4",
                    type: "theme",
                    title: "Embodied Research",
                    colorClass: "theme-research",
                    content: "Body as method",
                    tooltip: "Walking, sitting, wearing, performing. First-person ethnography to reveal hidden urban violence.",
                    angle: 180,
                    orbit: 3
                },
                {
                    id: "theme5",
                    type: "theme",
                    title: "Sensory Translation",
                    colorClass: "theme-sensory",
                    content: "Cross-species perception",
                    tooltip: "Interfaces for perceiving pollution, noise, vibration as other species might experience them.",
                    angle: 240,
                    orbit: 3
                },
                {
                    id: "theme6",
                    type: "theme",
                    title: "Environmental Empathy",
                    colorClass: "theme-urban",
                    content: "Feeling-with ecosystems",
                    tooltip: "Developing emotional connections to non-human urban residents and their living conditions.",
                    angle: 300,
                    orbit: 3
                }
            ],
            
            actions: [
                {
                    id: "action1",
                    type: "action",
                    title: "Sitting hostile",
                    colorClass: "action-amber",
                    content: "Body as sensor",
                    tooltip: "Using the body to experience and reveal the normalized violence of exclusionary urban furniture.",
                    angle: 45,
                    orbit: 4
                },
                {
                    id: "action2",
                    type: "action",
                    title: "Returning Life",
                    colorClass: "action-green",
                    content: "Rewilding acts",
                    tooltip: "Soil deposits, seed bombs, moss graffiti. Reintroducing non-curated life into controlled spaces.",
                    angle: 135,
                    orbit: 4
                },
                {
                    id: "action3",
                    type: "action",
                    title: "Wearing Hostility",
                    colorClass: "action-red",
                    content: "Material translation",
                    tooltip: "Turning anti-pigeon spikes into clothing. Making architectural violence visible on the body.",
                    angle: 225,
                    orbit: 4
                },
                {
                    id: "action4",
                    type: "action",
                    title: "Sensory experiments",
                    colorClass: "action-blue",
                    content: "Perception interfaces",
                    tooltip: "Prototyping devices that translate urban conditions across sensory modalities and species.",
                    angle: 315,
                    orbit: 4
                }
            ],
            
            futures: [
                {
                    id: "future1",
                    type: "future",
                    title: "Multispecies perception",
                    content: "Cross-sensing tools",
                    tooltip: "Wearables and installations that help humans perceive pollution, vibration, signals as other species do.",
                    angle: 45,
                    orbit: 5
                },
                {
                    id: "future2",
                    type: "future",
                    title: "Embodied translation",
                    content: "Full-body ecology",
                    tooltip: "Haptic suits, olfactory displays that make environmental conditions tangibly felt by humans.",
                    angle: 135,
                    orbit: 5
                },
                {
                    id: "future3",
                    type: "future",
                    title: "Empathy-driven design",
                    content: "Compassionate planning",
                    tooltip: "Design processes centering multispecies wellbeing, sensory justice, and ecological empathy.",
                    angle: 225,
                    orbit: 5
                },
                {
                    id: "future4",
                    type: "future",
                    title: "Urban coexistence",
                    content: "Multispecies community",
                    tooltip: "Reimagining cities where all residents are recognized as citizens with rights and needs.",
                    angle: 315,
                    orbit: 5
                }
            ],
            
            microNodes: [
                {id: "micro1", word: "care", colorClass: "micro-care", x: 30, y: 25},
                {id: "micro2", word: "friction", colorClass: "micro-friction", x: 70, y: 20},
                {id: "micro3", word: "presence", colorClass: "micro-presence", x: 85, y: 45},
                {id: "micro4", word: "erasure", colorClass: "micro-erasure", x: 75, y: 75},
                {id: "micro5", word: "vulnerability", colorClass: "micro-vulnerability", x: 45, y: 85},
                {id: "micro6", word: "coexistence", colorClass: "micro-coexistence", x: 20, y: 70}
            ]
        };

        // ===== FUNCIONES DE CONSTRUCCIÓN =====
        function createGalaxy() {
            const nodesContainer = document.getElementById('cosmicNodes');
            const microContainer = document.getElementById('microNodes');
            
            // Limpiar contenedores
            nodesContainer.innerHTML = '';
            microContainer.innerHTML = '';
            
            // Crear nodo central
            createNode(galaxyData.core, nodesContainer, 0);
            
            // Crear todos los nodos
            const allNodes = [
                ...galaxyData.intuitions,
                ...galaxyData.questions,
                ...galaxyData.themes,
                ...galaxyData.actions,
                ...galaxyData.futures
            ];
            
            allNodes.forEach((node, index) => {
                createNode(node, nodesContainer, index + 1);
            });
            
            // Crear micro-nodos
            galaxyData.microNodes.forEach((micro, index) => {
                createMicroNode(micro, microContainer, index);
            });
            
            // Crear conexiones después de crear los nodos
            setTimeout(createAllConnections, 100);
        }

        function createNode(nodeData, container, index) {
            const node = document.createElement('div');
            node.className = `cosmic-node node-type-${nodeData.type}`;
            node.dataset.id = nodeData.id;
            node.dataset.type = nodeData.type;
            node.style.animationDelay = `${index * 0.1}s`;
            
            // Añadir clase de color
            if (nodeData.colorClass) {
                node.classList.add(nodeData.colorClass);
            }
            
            // Calcular posición
            let x, y;
            if (nodeData.type === 'core') {
                x = 50;
                y = 50;
            } else {
                // Calcular posición basada en órbita y ángulo
                const orbitPercentage = nodeData.orbit;
                const angleRad = (nodeData.angle * Math.PI) / 180;
                
                // Convertir órbita a porcentaje de pantalla
                const orbitMap = {
                    1: 20,  // 20% del viewport height
                    2: 35,  // 35% del viewport height
                    3: 50,  // 50% del viewport height
                    4: 65,  // 65% del viewport height
                    5: 80   // 80% del viewport height
                };
                
                const orbitRadius = orbitMap[orbitPercentage] || 0;
                
                // Calcular posición en porcentaje
                x = 50 + (orbitRadius * Math.cos(angleRad));
                y = 50 + (orbitRadius * Math.sin(angleRad));
            }
            
            node.style.left = `${x}%`;
            node.style.top = `${y}%`;
            
            // Contenido
            const content = document.createElement('div');
            content.className = 'node-content';
            
            const title = document.createElement('div');
            title.className = 'node-title';
            title.textContent = nodeData.title;
            
            const subtitle = document.createElement('div');
            subtitle.className = 'node-subtitle';
            subtitle.textContent = nodeData.content;
            
            content.appendChild(title);
            content.appendChild(subtitle);
            node.appendChild(content);
            
            container.appendChild(node);
            
            // Event listeners
            setupNodeInteractions(node, nodeData);
        }

        // ===== CONEXIONES =====
        function createAllConnections() {
            const connectionsContainer = document.getElementById('cosmicConnections');
            connectionsContainer.innerHTML = '';
            
            // Crear conexiones principales
            createBezierConnection("core", "intuition1", "strong");
            createBezierConnection("core", "theme1", "normal");
            createBezierConnection("core", "theme2", "normal");
            createBezierConnection("intuition1", "question3", "normal");
            createBezierConnection("theme2", "question1", "normal");
            createBezierConnection("theme3", "action2", "normal");
            createBezierConnection("theme5", "future1", "normal");
            createBezierConnection("theme6", "future3", "normal");
        }

        function createBezierConnection(sourceId, targetId, strength) {
            const source = document.querySelector(`[data-id="${sourceId}"]`);
            const target = document.querySelector(`[data-id="${targetId}"]`);
            
            if (!source || !target) return;
            
            const container = document.getElementById('cosmicConnections');
            const svgNS = "http://www.w3.org/2000/svg";
            const svg = document.createElementNS(svgNS, "svg");
            svg.classList.add("cosmic-connection");
            
            // Obtener posiciones en porcentaje
            const x1 = parseFloat(source.style.left);
            const y1 = parseFloat(source.style.top);
            const x2 = parseFloat(target.style.left);
            const y2 = parseFloat(target.style.top);
            
            // Calcular puntos de control para curva Bézier
            const dx = x2 - x1;
            const dy = y2 - y1;
            const distance = Math.sqrt(dx * dx + dy * dy);
            const curvature = distance * 0.2;
            
            const cx1 = x1 + dx * 0.3 + curvature;
            const cy1 = y1 + dy * 0.3 - curvature;
            const cx2 = x1 + dx * 0.7 - curvature;
            const cy2 = y1 + dy * 0.7 + curvature;
            
            // Crear path
            const path = document.createElementNS(svgNS, "path");
            const d = `M ${x1} ${y1} C ${cx1} ${cy1}, ${cx2} ${cy2}, ${x2} ${y2}`;
            path.setAttribute("d", d);
            path.setAttribute("fill", "none");
            
            // Estilo según fuerza
            if (strength === "strong") {
                path.setAttribute("stroke", "url(#gradient-strong)");
                path.setAttribute("stroke-width", "3");
                path.setAttribute("opacity", "0.5");
                
                // Crear gradiente si no existe
                if (!document.getElementById('gradient-strong')) {
                    const defs = document.createElementNS(svgNS, "defs");
                    const gradient = document.createElementNS(svgNS, "linearGradient");
                    gradient.setAttribute("id", "gradient-strong");
                    gradient.setAttribute("x1", "0%");
                    gradient.setAttribute("y1", "0%");
                    gradient.setAttribute("x2", "100%");
                    gradient.setAttribute("y2", "0%");
                    
                    const stop1 = document.createElementNS(svgNS, "stop");
                    stop1.setAttribute("offset", "0%");
                    stop1.setAttribute("stop-color", "#8A3FFC");
                    
                    const stop2 = document.createElementNS(svgNS, "stop");
                    stop2.setAttribute("offset", "100%");
                    stop2.setAttribute("stop-color", "#00D4FF");
                    
                    gradient.appendChild(stop1);
                    gradient.appendChild(stop2);
                    defs.appendChild(gradient);
                    svg.appendChild(defs);
                }
            } else {
                path.setAttribute("stroke", "rgba(242, 242, 242, 0.4)");
                path.setAttribute("stroke-width", "1.5");
                path.setAttribute("opacity", "0.4");
            }
            
            svg.appendChild(path);
            container.appendChild(svg);
        }

        // ===== INTERACCIÓN =====
        const tooltip = document.getElementById('cosmicTooltip');
        const tooltipTitle = document.getElementById('tooltipTitle');
        const tooltipContent = document.getElementById('tooltipContent');

        function setupNodeInteractions(node, nodeData) {
            node.addEventListener('mouseenter', (e) => {
                handleNodeHover(e, nodeData);
            });
            
            node.addEventListener('mouseleave', handleNodeLeave);
            
            node.addEventListener('click', () => {
                // Animación de clic
                node.style.transform = 'translate(-50%, -50%) scale(1.3)';
                setTimeout(() => {
                    node.style.transform = 'translate(-50%, -50%) scale(1.15)';
                }, 200);
                
                // Mostrar info detallada en consola
                console.log(`Nodo clickeado: ${nodeData.title}`, nodeData);
            });
        }

        function handleNodeHover(event, nodeData) {
            tooltipTitle.textContent = nodeData.title;
            tooltipContent.textContent = nodeData.tooltip;
            
            tooltip.style.left = `${event.clientX + 25}px`;
            tooltip.style.top = `${event.clientY + 25}px`;
            tooltip.classList.add('active');
        }

        function handleNodeLeave() {
            tooltip.classList.remove('active');
        }

        // ===== MICRO-NODOS =====
        function createMicroNode(microData, container, index) {
            const micro = document.createElement('div');
            micro.className = `cosmic-node node-type-micro ${microData.colorClass}`;
            micro.dataset.id = microData.id;
            micro.style.left = `${microData.x}%`;
            micro.style.top = `${microData.y}%`;
            micro.style.animationDelay = `${index * 0.2}s`;
            
            micro.addEventListener('mouseenter', (e) => {
                tooltipTitle.textContent = microData.word;
                tooltipContent.textContent = `Conceptual thread: ${microData.word} as a lens for reading urban relations and violence.`;
                tooltip.style.left = `${e.clientX + 20}px`;
                tooltip.style.top = `${e.clientY + 20}px`;
                tooltip.classList.add('active');
            });
            
            micro.addEventListener('mouseleave', () => {
                tooltip.classList.remove('active');
            });
            
            container.appendChild(micro);
        }

        // ===== LEYENDA INTERACTIVA =====
        const legendToggle = document.getElementById('legendToggle');
        const legendContent = document.getElementById('legendContent');
        let legendVisible = true;

        legendToggle.addEventListener('click', () => {
            legendVisible = !legendVisible;
            
            if (legendVisible) {
                legendContent.style.display = 'block';
                legendToggle.textContent = '−';
            } else {
                legendContent.style.display = 'none';
                legendToggle.textContent = '+';
            }
        });

        // ===== FULLSCREEN FUNCTIONALITY =====
        const fullscreenToggle = document.getElementById('fullscreenToggle');
        
        fullscreenToggle.addEventListener('click', () => {
            const element = document.documentElement;
            
            if (!document.fullscreenElement) {
                if (element.requestFullscreen) {
                    element.requestFullscreen();
                } else if (element.mozRequestFullScreen) { /* Firefox */
                    element.mozRequestFullScreen();
                } else if (element.webkitRequestFullscreen) { /* Chrome, Safari & Opera */
                    element.webkitRequestFullscreen();
                } else if (element.msRequestFullscreen) { /* IE/Edge */
                    element.msRequestFullscreen();
                }
                fullscreenToggle.textContent = 'Exit Fullscreen';
            } else {
                if (document.exitFullscreen) {
                    document.exitFullscreen();
                } else if (document.mozCancelFullScreen) { /* Firefox */
                    document.mozCancelFullScreen();
                } else if (document.webkitExitFullscreen) { /* Chrome, Safari & Opera */
                    document.webkitExitFullscreen();
                } else if (document.msExitFullscreen) { /* IE/Edge */
                    document.msExitFullscreen();
                }
                fullscreenToggle.textContent = 'Fullscreen';
            }
        });

        // Escuchar cambios en fullscreen
        document.addEventListener('fullscreenchange', () => {
            if (!document.fullscreenElement) {
                fullscreenToggle.textContent = 'Fullscreen';
            }
        });

        // ===== INICIALIZACIÓN =====
        document.addEventListener('DOMContentLoaded', () => {
            createGalaxy();
            
            // Ajustar conexiones al redimensionar
            let resizeTimeout;
            window.addEventListener('resize', () => {
                clearTimeout(resizeTimeout);
                resizeTimeout = setTimeout(() => {
                    createAllConnections();
                }, 200);
            });
            
            // Mover tooltip con el mouse
            document.addEventListener('mousemove', (e) => {
                if (tooltip.classList.contains('active')) {
                    tooltip.style.left = `${e.clientX + 25}px`;
                    tooltip.style.top = `${e.clientY + 25}px`;
                }
            });
            
            // Zoom con scroll (opcional)
            let scale = 1;
            const galaxyMap = document.getElementById('galaxyMap');
            
            galaxyMap.addEventListener('wheel', (e) => {
                e.preventDefault();
                
                if (e.ctrlKey) {
                    // Zoom con Ctrl + Scroll
                    scale += e.deltaY * -0.01;
                    scale = Math.min(Math.max(0.5, scale), 3);
                    
                    galaxyMap.style.transform = `scale(${scale})`;
                    galaxyMap.style.transformOrigin = `${e.clientX / window.innerWidth * 100}% ${e.clientY / window.innerHeight * 100}%`;
                }
            });
        });
    </script>
</body>
</html>