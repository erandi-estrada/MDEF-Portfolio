<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<div class="diagram-container">
    <div class="hexagon-diagram">
        <!-- Imagen central grande CON FONDO BLANCO -->
        <div class="center-image">
            <div class="center-circle"></div>
            <img src="../../images/Diagrama/Centro.png" alt="Urban Sparrow Center" class="center-img">
        </div>
        
        <!-- Nodo 1 - Parte superior -->
        <div class="hexagon-node node-1" data-node="1">
            <div class="node-position">
                <img src="../../images/Diagrama/1.png" alt="Urban Attractors and Constraints" class="node-img">
                <div class="node-glow" style="background: radial-gradient(circle, rgba(25, 118, 210, 0.4) 0%, transparent 70%);"></div>
                <div class="click-hint">Click here</div>
            </div>
            <div class="arrow arrow-1"></div>
        </div>
        
        <!-- Nodo 2 - Superior derecha -->
        <div class="hexagon-node node-2" data-node="2">
            <div class="node-position">
                <img src="../../images/Diagrama/2.png" alt="Dietary Poverty & Toxic Intake" class="node-img">
                <div class="node-glow" style="background: radial-gradient(circle, rgba(56, 142, 60, 0.4) 0%, transparent 70%);"></div>
                <div class="click-hint">Click here</div>
            </div>
            <div class="arrow arrow-2"></div>
        </div>
        
        <!-- Nodo 3 - Inferior derecha -->
        <div class="hexagon-node node-3" data-node="3">
            <div class="node-position">
                <img src="../../images/Diagrama/3.png" alt="Chronic Stress and Energetic Drain" class="node-img">
                <div class="node-glow" style="background: radial-gradient(circle, rgba(245, 124, 0, 0.4) 0%, transparent 70%);"></div>
                <div class="click-hint">Click here</div>
            </div>
            <div class="arrow arrow-3"></div>
        </div>
        
        <!-- Nodo 4 - Parte inferior -->
        <div class="hexagon-node node-4" data-node="4">
            <div class="node-position">
                <img src="../../images/Diagrama/4.png" alt="Impaired Foraging Behavior and Decision-Making" class="node-img">
                <div class="node-glow" style="background: radial-gradient(circle, rgba(211, 47, 47, 0.4) 0%, transparent 70%);"></div>
                <div class="click-hint">Click here</div>
            </div>
            <div class="arrow arrow-4"></div>
        </div>
        
        <!-- Nodo 5 - Inferior izquierda -->
        <div class="hexagon-node node-5" data-node="5">
            <div class="node-position">
                <img src="../../images/Diagrama/5.png" alt="Density, Waste, and Compounding Exposure" class="node-img">
                <div class="node-glow" style="background: radial-gradient(circle, rgba(123, 31, 162, 0.4) 0%, transparent 70%);"></div>
                <div class="click-hint">Click here</div>
            </div>
            <div class="arrow arrow-5"></div>
        </div>
        
        <!-- Nodo 6 - Superior izquierda -->
        <div class="hexagon-node node-6" data-node="6">
            <div class="node-position">
                <img src="../../images/Diagrama/6.png" alt="Health Decline Without Escape" class="node-img">
                <div class="node-glow" style="background: radial-gradient(circle, rgba(0, 121, 107, 0.4) 0%, transparent 70%);"></div>
                <div class="click-hint">Click here</div>
            </div>
            <div class="arrow arrow-6"></div>
        </div>
    </div>
    
    <!-- Panel de información que aparece al hacer clic -->
    <div class="info-overlay">
        <div class="info-panel">
            <button class="close-btn">&times;</button>
            <div class="info-content">
                <h3 class="info-title">House Sparrow</h3>
                <div class="info-subtitle">Urban Attractors and Constraints</div>
                <p>Concentrates sparrows in small spatial ranges (~60 m from nests), especially in densely populated human neighborhoods, where population density correlates more strongly with sparrow health decline than light or noise alone.</p>
                
                <div class="info-subtitle">Habitat structure</div>
                <p>Favors presence near allotments, medium-height tree clusters, and low shrub cover, offering nesting and shelter.</p>
                
                <div class="info-subtitle">Anthropogenic food availability</div>
                <p>Peaks in areas with abundant litter and food waste, creating predictable foraging hotspots.</p>
                
                <div class="info-note">
                    Urban environments initially function as ecological traps: they offer reliable food and nesting opportunities while masking long-term costs.
                </div>
            </div>
        </div>
    </div>
</div>

<style>
    /* Ocultar el header superior con "Atlas" */
    header:first-of-type,
    .header:first-of-type,
    .atlas-header,
    h1:first-of-type {
        display: none !important;
    }
    
    /* SIN FONDO - Usa el fondo por defecto de tu código */
    .diagram-container {
        width: 100%;
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        padding: 2rem 0;
    }
    
    /* Contenedor hexagonal - MÁS GRANDE PARA MÁS SEPARACIÓN */
    .hexagon-diagram {
        position: relative;
        width: 1800px;
        height: 1600px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    
    /* Imagen central - MÁS GRANDE CON FONDO BLANCO */
    .center-image {
        position: absolute;
        width: 500px;
        height: 500px;
        z-index: 10;
        display: flex;
        align-items: center;
        justify-content: center;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
    
    .center-circle {
        position: absolute;
        width: 100%;
        height: 100%;
        background: white;
        border-radius: 50%;
        border: 4px solid #1976d2;
        box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
        z-index: 1;
    }
    
    /* IMAGEN DEL CENTRO MÁS GRANDE */
    .center-img {
        width: 100%;
        height: 85%;
        object-fit: contain;
        border-radius: none;
        position: relative;
        z-index: 2;
    }
    
    /* Nodos - ESTRUCTURA CORREGIDA */
    .hexagon-node {
        position: absolute;
        width: 300px;
        height: 300px;
        z-index: 20;
        /* Posicionamiento absoluto en lugar de transform */
    }
    
    /* Contenedor para el efecto hover - separado del posicionamiento */
    .node-position {
        width: 100%;
        height: 100%;
        cursor: pointer;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        position: relative;
    }
    
    /* EFECTO HOVER MEJORADO - con borde más grueso */
    .node-position:hover {
        transform: scale(1.15);
        z-index: 30;
    }
    
    .node-img {
        width: 100%;
        height: 100%;
        object-fit: contain;
        border-radius: 50%;
        position: relative;
        z-index: 2;
        border: 3px solid;
        transition: all 0.3s ease;
    }
    
    /* BORDES MÁS GRUESOS AL HOVER */
    .node-position:hover .node-img {
        transform: scale(1.05);
        border-width: 6px; /* Borde más grueso al hover */
    }
    
    /* Bordes de colores para cada nodo */
    .node-1 .node-img { border-color: #1976d2; }
    .node-2 .node-img { border-color: #388e3c; }
    .node-3 .node-img { border-color: #f57c00; }
    .node-4 .node-img { border-color: #d32f2f; }
    .node-5 .node-img { border-color: #7b1fa2; }
    .node-6 .node-img { border-color: #00796b; }
    
    .node-glow {
        position: absolute;
        width: 120%;
        height: 120%;
        border-radius: 50%;
        z-index: 1;
        opacity: 0;
        transition: all 0.3s ease;
        pointer-events: none;
    }
    
    .node-position:hover .node-glow {
        opacity: 1;
        transform: scale(1.1);
        filter: blur(20px);
    }
    
    /* Mensaje "Click here" */
    .click-hint {
        position: absolute;
        bottom: -35px;
        left: 50%;
        transform: translateX(-50%);
        background: rgba(0, 0, 0, 0.8);
        color: white;
        padding: 6px 12px;
        border-radius: 20px;
        font-size: 0.9rem;
        font-weight: 600;
        opacity: 0;
        transition: all 0.3s ease;
        white-space: nowrap;
        z-index: 40;
        pointer-events: none;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
    }
    
    .node-position:hover .click-hint {
        opacity: 1;
        transform: translateX(-50%) translateY(-5px);
    }
    
    /* FLECHAS */
    .arrow {
        position: absolute;
        z-index: 5;
        pointer-events: none;
    }
    
    /* Línea de la flecha */
    .arrow::before {
        content: '';
        position: absolute;
        background: linear-gradient(90deg, 
            rgba(255, 255, 255, 0.8) 0%, 
            rgba(255, 255, 255, 0.6) 50%, 
            rgba(255, 255, 255, 0.3) 100%);
        border-radius: 2px;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
    }
    
    /* Punta de la flecha */
    .arrow::after {
        content: '';
        position: absolute;
        border-style: solid;
        border-color: transparent;
    }
    
    /* Flecha 1 - Hacia arriba */
    .arrow-1 {
        width: 6px;
        height: 250px;
        top: 330px;
        left: calc(50% + 147px);
        transform: translateX(-50%);
    }
    
    .arrow-1::before {
        width: 6px;
        height: 100%;
        top: 0;
        left: 0;
    }
    
    .arrow-1::after {
        top: -10px;
        left: -6px;
        border-width: 0 9px 12px 9px;
        border-bottom-color: rgba(255, 255, 255, 0.9);
    }
    
    /* Flecha 2 - Superior derecha */
    .arrow-2 {
        width: 320px;
        height: 6px;
        top: 525px;
        left: 925px;
        transform: rotate(-30deg);
        transform-origin: left center;
    }
    
    .arrow-2::before {
        width: 100%;
        height: 6px;
        top: 0;
        left: 0;
    }
    
    .arrow-2::after {
        top: -9px;
        right: -12px;
        border-width: 6px 0 6px 12px;
        border-left-color: rgba(255, 255, 255, 0.9);
    }
    
    /* Flecha 3 - Inferior derecha */
    .arrow-3 {
        width: 320px;
        height: 6px;
        top: 775px;
        left: 925px;
        transform: rotate(30deg);
        transform-origin: left center;
    }
    
    .arrow-3::before {
        width: 100%;
        height: 6px;
        top: 0;
        left: 0;
    }
    
    .arrow-3::after {
        top: -9px;
        right: -12px;
        border-width: 6px 0 6px 12px;
        border-left-color: rgba(255, 255, 255, 0.9);
    }
    
    /* Flecha 4 - Hacia abajo */
    .arrow-4 {
        width: 6px;
        height: 250px;
        bottom: 330px;
        left: calc(50% + 147px);
        transform: translateX(-50%);
    }
    
    .arrow-4::before {
        width: 6px;
        height: 100%;
        top: 0;
        left: 0;
    }
    
    .arrow-4::after {
        bottom: -10px;
        left: -6px;
        border-width: 12px 9px 0 9px;
        border-top-color: rgba(255, 255, 255, 0.9);
    }
    
    /* Flecha 5 - Inferior izquierda */
    .arrow-5 {
        width: 320px;
        height: 6px;
        top: 775px;
        left: 325px;
        transform: rotate(-30deg);
        transform-origin: right center;
    }
    
    .arrow-5::before {
        width: 100%;
        height: 6px;
        top: 0;
        left: 0;
    }
    
    .arrow-5::after {
        top: -9px;
        left: -12px;
        border-width: 6px 12px 6px 0;
        border-right-color: rgba(255, 255, 255, 0.9);
    }
    
    /* Flecha 6 - Superior izquierda */
    .arrow-6 {
        width: 320px;
        height: 6px;
        top: 525px;
        left: 325px;
        transform: rotate(30deg);
        transform-origin: right center;
    }
    
    .arrow-6::before {
        width: 100%;
        height: 6px;
        top: 0;
        left: 0;
    }
    
    .arrow-6::after {
        top: -9px;
        left: -12px;
        border-width: 6px 12px 6px 0;
        border-right-color: rgba(255, 255, 255, 0.9);
    }
    
    /* POSICIONES CORREGIDAS - HEXÁGONO PERFECTO CON MÁS SEPARACIÓN */
    .node-1 { 
        top: 15px;
        left: calc(900px - 150px);
    }
    
    .node-2 { 
        top: calc(800px - 275px - 150px);
        left: calc(900px + 476px - 150px);
    }
    
    .node-3 { 
        top: calc(800px + 275px - 150px);
        left: calc(900px + 476px - 150px);
    }
    
    .node-4 { 
        top: calc(800px + 550px - 150px);
        left: calc(900px - 150px);
    }
    
    .node-5 { 
        top: calc(800px + 275px - 150px);
        left: calc(900px - 476px - 150px);
    }
    
    .node-6 { 
        top: calc(800px - 275px - 150px);
        left: calc(900px - 476px - 150px);
    }
    
    /* Panel de información */
    .info-overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.85);
        display: none;
        align-items: center;
        justify-content: center;
        z-index: 1000;
        opacity: 0;
        transition: opacity 0.3s ease;
    }
    
    .info-overlay.active {
        display: flex;
        opacity: 1;
    }
    
    .info-panel {
        background: white;
        border-radius: 20px;
        width: 90%;
        max-width: 800px;
        max-height: 85vh;
        padding: 3rem;
        position: relative;
        box-shadow: 0 25px 80px rgba(0, 0, 0, 0.5);
        transform: translateY(20px);
        transition: transform 0.3s ease;
        overflow-y: auto;
    }
    
    .info-overlay.active .info-panel {
        transform: translateY(0);
    }
    
    .close-btn {
        position: absolute;
        top: 1.5rem;
        right: 1.5rem;
        background: none;
        border: none;
        font-size: 2.5rem;
        color: #666;
        cursor: pointer;
        width: 50px;
        height: 50px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.3s ease;
        line-height: 1;
    }
    
    .close-btn:hover {
        background: #f5f5f5;
        color: #333;
        transform: rotate(90deg);
    }
    
    .info-title {
        font-size: 2.5rem;
        font-weight: 700;
        color: #2d3748;
        margin-bottom: 1.5rem;
        padding-bottom: 1rem;
        border-bottom: 3px solid #1976d2;
    }
    
    .info-subtitle {
        font-size: 1.5rem;
        font-weight: 600;
        color: #1976d2;
        margin: 2rem 0 1rem 0;
        padding-top: 1.5rem;
        border-top: 1px solid #e2e8f0;
    }
    
    .info-subtitle:first-of-type {
        margin-top: 1rem;
        padding-top: 0;
        border-top: none;
        color: #2d3748;
        font-size: 1.8rem;
        font-weight: 700;
    }
    
    .info-content p {
        font-size: 1.2rem;
        line-height: 1.7;
        color: #4a5568;
        margin-bottom: 1.5rem;
    }
    
    .info-note {
        font-size: 1.1rem;
        font-style: italic;
        color: #718096;
        padding: 1.8rem;
        background: linear-gradient(135deg, #f7fafc 0%, #edf2f7 100%);
        border-left: 4px solid #e2e8f0;
        margin-top: 2.5rem;
        border-radius: 12px;
        line-height: 1.6;
    }
    
    /* Responsive - Ajustar flechas y posiciones */
    @media (max-width: 2000px) {
        .hexagon-diagram {
            width: 1600px;
            height: 1400px;
        }
        
        .node-1 { 
            top: 20px;
            left: calc(800px - 150px);
        }
        
        .node-2 { 
            top: calc(700px - 250px - 150px);
            left: calc(800px + 433px - 150px);
        }
        
        .node-3 { 
            top: calc(700px + 250px - 150px);
            left: calc(800px + 433px - 150px);
        }
        
        .node-4 { 
            top: calc(700px + 500px - 150px);
            left: calc(800px - 150px);
        }
        
        .node-5 { 
            top: calc(700px + 250px - 150px);
            left: calc(800px - 433px - 150px);
        }
        
        .node-6 { 
            top: calc(700px - 250px - 150px);
            left: calc(800px - 433px - 150px);
        }
        
        /* Ajustar flechas para tamaño 1600px */
        .arrow-1 {
            height: 220px;
            top: 300px;
            left: calc(50% + 140px);
        }
        
        .arrow-2 {
            width: 280px;
            top: 470px;
            left: 830px;
        }
        
        .arrow-3 {
            width: 280px;
            top: 690px;
            left: 830px;
        }
        
        .arrow-4 {
            height: 220px;
            bottom: 300px;
            left: calc(50% + 140px);
        }
        
        .arrow-5 {
            width: 280px;
            top: 690px;
            left: 370px;
        }
        
        .arrow-6 {
            width: 280px;
            top: 470px;
            left: 370px;
        }
    }
    
    @media (max-width: 1800px) {
        .hexagon-diagram {
            width: 1400px;
            height: 1200px;
        }
        
        .center-image {
            width: 450px;
            height: 450px;
        }
        
        .center-img {
            width: 100%;
            height: 85%;
        }
        
        .hexagon-node {
            width: 280px;
            height: 280px;
        }
        
        .node-position {
            width: 280px;
            height: 280px;
        }
        
        .node-1 { 
            top: 20px;
            left: calc(700px - 140px);
        }
        
        .node-2 { 
            top: calc(600px - 225px - 140px);
            left: calc(700px + 390px - 140px);
        }
        
        .node-3 { 
            top: calc(600px + 225px - 140px);
            left: calc(700px + 390px - 140px);
        }
        
        .node-4 { 
            top: calc(600px + 450px - 140px);
            left: calc(700px - 140px);
        }
        
        .node-5 { 
            top: calc(600px + 225px - 140px);
            left: calc(700px - 390px - 140px);
        }
        
        .node-6 { 
            top: calc(600px - 225px - 140px);
            left: calc(700px - 390px - 140px);
        }
        
        /* Ajustar flechas para tamaño 1400px */
        .arrow-1 {
            height: 200px;
            top: 280px;
            left: calc(50% + 134px);
        }
        
        .arrow-2 {
            width: 250px;
            top: 420px;
            left: 730px;
        }
        
        .arrow-3 {
            width: 250px;
            top: 620px;
            left: 730px;
        }
        
        .arrow-4 {
            height: 200px;
            bottom: 280px;
            left: calc(50% + 134px);
        }
        
        .arrow-5 {
            width: 250px;
            top: 620px;
            left: 320px;
        }
        
        .arrow-6 {
            width: 250px;
            top: 420px;
            left: 320px;
        }
    }
    
    @media (max-width: 1600px) {
        .hexagon-diagram {
            width: 1200px;
            height: 1000px;
        }
        
        .center-image {
            width: 400px;
            height: 400px;
        }
        
        .center-img {
            width: 100%;
            height: 85%;
        }
        
        .hexagon-node {
            width: 250px;
            height: 250px;
        }
        
        .node-position {
            width: 250px;
            height: 250px;
        }
        
        .node-1 { 
            top: 40px;
            left: calc(600px - 125px);
        }
        
        .node-2 { 
            top: calc(500px - 200px - 125px);
            left: calc(600px + 346px - 125px);
        }
        
        .node-3 { 
            top: calc(500px + 200px - 125px);
            left: calc(600px + 346px - 125px);
        }
        
        .node-4 { 
            top: calc(500px + 400px - 125px);
            left: calc(600px - 125px);
        }
        
        .node-5 { 
            top: calc(500px + 200px - 125px);
            left: calc(600px - 346px - 125px);
        }
        
        .node-6 { 
            top: calc(500px - 200px - 125px);
            left: calc(600px - 346px - 125px);
        }
        
        /* Ocultar flechas en pantallas más pequeñas para mantener limpieza */
        .arrow {
            display: none;
        }
    }
    
    /* Para pantallas más pequeñas, ocultamos las flechas */
    @media (max-width: 1400px) {
        .arrow {
            display: none;
        }
    }
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const nodes = document.querySelectorAll('.hexagon-node');
    const infoOverlay = document.querySelector('.info-overlay');
    const infoPanel = infoOverlay.querySelector('.info-panel');
    const closeBtn = infoOverlay.querySelector('.close-btn');
    const infoTitle = infoPanel.querySelector('.info-title');
    const infoContent = infoPanel.querySelector('.info-content');
    
    // Datos para cada nodo
    const nodeData = {
        1: {
            title: "House Sparrow",
            subtitle: "Urban Attractors and Constraints",
            content: `
                <div class="info-subtitle">High urban density</div>
                <p>Concentrates sparrows in small spatial ranges (~60 m from nests), especially in densely populated human neighborhoods, where population density correlates more strongly with sparrow health decline than light or noise alone.</p>
                
                <div class="info-subtitle">Habitat structure</div>
                <p>Favors presence near allotments, medium-height tree clusters, and low shrub cover, offering nesting and shelter.</p>
                
                <div class="info-subtitle">Anthropogenic food availability</div>
                <p>Peaks in areas with abundant litter and food waste, creating predictable foraging hotspots.</p>
                
                <div class="info-note">
                    Urban environments initially function as ecological traps: they offer reliable food and nesting opportunities while masking long-term costs.
                </div>
            `
        },
        2: {
            title: "House Sparrow",
            subtitle: "Dietary Poverty & Toxic Intake",
            content: `
                <div class="info-subtitle">Low-quality diets</div>
                <p>Dominated by human food waste (bread, scraps), deficient in protein and micronutrients.</p>
                
                <div class="info-subtitle">High exposure to contaminants</div>
                <p>As food waste, grit, water, and bio-accumulated insects in traffic-dense areas contain elevated levels of lead, copper, and zinc.</p>
                
                <div class="info-note">
                    Birds in the densest human-population patches show the highest blood-lead concentrations, linking urban crowding directly to toxic burden.
                </div>
            `
        },
        3: {
            title: "House Sparrow",
            subtitle: "Chronic Stress and Energetic Drain",
            content: `
                <div class="info-subtitle">Metabolic stress</div>
                <p>Evidenced by altered glucose regulation, reduced uric acid, and depleted liver glycogen.</p>
                
                <div class="info-subtitle">Immune system up-regulation</div>
                <p>Particularly in urban birds, which over-express immune, coagulation, and lipid-metabolism proteins despite lower parasite prevalence than rural counterparts.</p>
                
                <div class="info-note">
                    Urban sparrows maintain heightened immune readiness not because of higher pathogen loads, but as a stress-induced response to pollution, disturbance, and poor nutrition. Both metabolic imbalance and immune vigilance are energetically expensive, rapidly depleting already scarce resources.
                </div>
            `
        },
        4: {
            title: "House Sparrow",
            subtitle: "Impaired Foraging Behavior and Decision-Making",
            content: `
                <div class="info-subtitle">Reduced foraging range and efficiency</div>
                <p>Reinforcing reliance on nearby, low-quality food sources.</p>
                
                <div class="info-subtitle">Lower neophobia and increased risk-taking</div>
                <p>Pushing birds toward highly contaminated areas (roadsides, dense pedestrian zones).</p>
                
                <div class="info-subtitle">Cognitive impairment</div>
                <p>As chronic stress and toxin exposure interfere with learning, memory, and habitat assessment.</p>
                
                <div class="info-note">
                    The bird becomes behaviorally locked into the very spaces that are harming it.
                </div>
            `
        },
        5: {
            title: "House Sparrow",
            subtitle: "Density, Waste, and Compounding Exposure",
            content: `
                <div class="info-subtitle">Sparrow density</div>
                <p>High sparrow density intensifies competition, increasing stress and further narrowing foraging options.</p>
                
                <div class="info-subtitle">Contaminated Diet</div>
                <p>Continued reliance on litter-rich zones elevates toxic intake and nutritional imbalance.</p>
                
                <div class="info-subtitle">Reduced Food Availability</div>
                <p>Improvements in waste management paradoxically remove a critical (though poor-quality) food source, increasing nutritional stress without restoring ecological alternatives.</p>
            `
        },
        6: {
            title: "House Sparrow",
            subtitle: "Health Decline Without Escape",
            content: `
                <div class="info-subtitle">Restricted Movement</div>
                <p>Sparrows remain spatially constrained due to nest fidelity and limited dispersal.</p>
                
                <div class="info-subtitle">Chronic Stress Impacts</div>
                <p>Chronic stress replaces acute mortality, allowing survival but reducing long-term health, resilience, and reproductive potential.</p>
                
                <div class="info-subtitle">Persistent Vulnerability</div>
                <p>The city sustains sparrow presence, but in a state of persistent physiological compromise.</p>
            `
        }
    };
    
    // Event listeners para cada nodo - CLICK
    nodes.forEach(node => {
        const nodePosition = node.querySelector('.node-position');
        
        nodePosition.addEventListener('click', function(e) {
            e.stopPropagation();
            const nodeId = node.dataset.node;
            const data = nodeData[nodeId];
            
            if (data) {
                infoTitle.textContent = data.title;
                let fullContent = `<div class="info-subtitle" style="margin-top: 0; padding-top: 0; border-top: none; color: #2d3748; font-size: 1.8rem; font-weight: 700; margin-bottom: 1.5rem;">${data.subtitle}</div>`;
                fullContent += data.content;
                infoContent.innerHTML = fullContent;
                infoOverlay.classList.add('active');
                document.body.style.overflow = 'hidden';
            }
        });
    });
    
    // Cerrar panel
    closeBtn.addEventListener('click', function() {
        infoOverlay.classList.remove('active');
        document.body.style.overflow = 'auto';
    });
    
    // Cerrar al hacer clic fuera del panel
    infoOverlay.addEventListener('click', function(e) {
        if (e.target === infoOverlay) {
            infoOverlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        }
    });
    
    // Cerrar con tecla ESC
    document.addEventListener('keydown', function(e) {
        if (e.key === 'Escape' && infoOverlay.classList.contains('active')) {
            infoOverlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        }
    });
});
</script>