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
            <img src="../../images/Diagrama/1.png" alt="Urban Attractors and Constraints" class="node-img">
            <div class="node-glow" style="background: radial-gradient(circle, rgba(25, 118, 210, 0.4) 0%, transparent 70%);"></div>
        </div>
        
        <!-- Nodo 2 - Superior derecha -->
        <div class="hexagon-node node-2" data-node="2">
            <img src="../../images/Diagrama/2.png" alt="Dietary Poverty & Toxic Intake" class="node-img">
            <div class="node-glow" style="background: radial-gradient(circle, rgba(56, 142, 60, 0.4) 0%, transparent 70%);"></div>
        </div>
        
        <!-- Nodo 3 - Inferior derecha -->
        <div class="hexagon-node node-3" data-node="3">
            <img src="../../images/Diagrama/3.png" alt="Chronic Stress and Energetic Drain" class="node-img">
            <div class="node-glow" style="background: radial-gradient(circle, rgba(245, 124, 0, 0.4) 0%, transparent 70%);"></div>
        </div>
        
        <!-- Nodo 4 - Parte inferior -->
        <div class="hexagon-node node-4" data-node="4">
            <img src="../../images/Diagrama/4.png" alt="Impaired Foraging Behavior and Decision-Making" class="node-img">
            <div class="node-glow" style="background: radial-gradient(circle, rgba(211, 47, 47, 0.4) 0%, transparent 70%);"></div>
        </div>
        
        <!-- Nodo 5 - Inferior izquierda -->
        <div class="hexagon-node node-5" data-node="5">
            <img src="../../images/Diagrama/5.png" alt="Density, Waste, and Compounding Exposure" class="node-img">
            <div class="node-glow" style="background: radial-gradient(circle, rgba(123, 31, 162, 0.4) 0%, transparent 70%);"></div>
        </div>
        
        <!-- Nodo 6 - Superior izquierda -->
        <div class="hexagon-node node-6" data-node="6">
            <img src="../../images/Diagrama/6.png" alt="Health Decline Without Escape" class="node-img">
            <div class="node-glow" style="background: radial-gradient(circle, rgba(0, 121, 107, 0.4) 0%, transparent 70%);"></div>
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
    
    /* Contenedor hexagonal - MUCHO MÁS GRANDE PARA SEPARACIÓN EXTREMA */
    .hexagon-diagram {
        position: relative;
        width: 2200px;  /* MUCHO MÁS ANCHO */
        height: 2000px; /* MUCHO MÁS ALTO */
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
    
    .center-img {
        width: 70%;
        height: 70%;
        object-fit: contain;
        border-radius: 50%;
        position: relative;
        z-index: 2;
    }
    
    /* Nodos - MANTENEMOS EL TAMAÑO PERO LOS ALEJAMOS MÁS */
    .hexagon-node {
        position: absolute;
        width: 300px;
        height: 300px;
        cursor: pointer;
        z-index: 20;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }
    
    /* CORREGIDO: Los nodos de arriba y abajo no se mueven */
    .hexagon-node:hover {
        transform: scale(1.15);
        z-index: 30;
    }
    
    /* Excepción para nodos centrados */
    .node-1:hover, .node-4:hover {
        transform: scale(1.15) translateX(-50%);
    }
    
    .node-img {
        width: 100%;
        height: 100%;
        object-fit: contain;
        border-radius: 50%;
        position: relative;
        z-index: 2;
        border: 3px solid;
        transition: transform 0.3s ease;
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
    
    .hexagon-node:hover .node-glow {
        opacity: 1;
        transform: scale(1.1);
        filter: blur(20px);
    }
    
    /* POSICIONES - MUCHO MÁS ALEJADAS DEL CENTRO */
    /* Calculamos para que haya al menos 200px de separación entre centro y nodos */
    .node-1 { 
        top: 50px;  /* MUY ALEJADO DEL CENTRO */
        left: 50%; 
        transform: translateX(-50%);
    }
    
    .node-2 { 
        top: 250px;  /* MUY ALEJADO DEL CENTRO */
        right: 650px; /* MUCHO MÁS ALEJADO - aumentado drásticamente */
    }
    
    .node-3 { 
        top: 850px;  /* MUY ALEJADO DEL CENTRO */
        right: 500px; /* MUCHO MÁS ALEJADO - aumentado drásticamente */
    }
    
    .node-4 { 
        bottom: 50px; /* MUY ALEJADO DEL CENTRO */
        left: 50%; 
        transform: translateX(-50%);
    }
    
    .node-5 { 
        top: 850px;  /* MUY ALEJADO DEL CENTRO */
        left: 500px;  /* MUCHO MÁS ALEJADO - aumentado drásticamente */
    }
    
    .node-6 { 
        top: 250px;  /* MUY ALEJADO DEL CENTRO */
        left: 650px;  /* MUCHO MÁS ALEJADO - aumentado drásticamente */
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
    
    /* Responsive */
    @media (max-width: 2400px) {
        .hexagon-diagram {
            width: 2000px;
            height: 1800px;
        }
        
        .node-1 { top: 45px; }
        .node-2 { top: 230px; right: 580px; }
        .node-3 { top: 780px; right: 450px; }
        .node-4 { bottom: 45px; }
        .node-5 { top: 780px; left: 450px; }
        .node-6 { top: 230px; left: 580px; }
    }
    
    @media (max-width: 2200px) {
        .hexagon-diagram {
            width: 1800px;
            height: 1600px;
        }
        
        .node-1 { top: 40px; }
        .node-2 { top: 210px; right: 520px; }
        .node-3 { top: 710px; right: 400px; }
        .node-4 { bottom: 40px; }
        .node-5 { top: 710px; left: 400px; }
        .node-6 { top: 210px; left: 520px; }
    }
    
    @media (max-width: 2000px) {
        .hexagon-diagram {
            width: 1600px;
            height: 1400px;
        }
        
        .center-image {
            width: 450px;
            height: 450px;
        }
        
        .hexagon-node {
            width: 280px;
            height: 280px;
        }
        
        .node-1 { top: 35px; }
        .node-2 { top: 190px; right: 460px; }
        .node-3 { top: 640px; right: 360px; }
        .node-4 { bottom: 35px; }
        .node-5 { top: 640px; left: 360px; }
        .node-6 { top: 190px; left: 460px; }
    }
    
    @media (max-width: 1800px) {
        .hexagon-diagram {
            width: 1500px;
            height: 1300px;
        }
        
        .center-image {
            width: 420px;
            height: 420px;
        }
        
        .hexagon-node {
            width: 260px;
            height: 260px;
        }
        
        .node-1 { top: 30px; }
        .node-2 { top: 170px; right: 430px; }
        .node-3 { top: 590px; right: 330px; }
        .node-4 { bottom: 30px; }
        .node-5 { top: 590px; left: 330px; }
        .node-6 { top: 170px; left: 430px; }
    }
    
    @media (max-width: 1600px) {
        .hexagon-diagram {
            width: 1400px;
            height: 1200px;
        }
        
        .center-image {
            width: 400px;
            height: 400px;
        }
        
        .hexagon-node {
            width: 240px;
            height: 240px;
        }
        
        .node-1 { top: 25px; }
        .node-2 { top: 150px; right: 400px; }
        .node-3 { top: 540px; right: 310px; }
        .node-4 { bottom: 25px; }
        .node-5 { top: 540px; left: 310px; }
        .node-6 { top: 150px; left: 400px; }
    }
    
    @media (max-width: 1400px) {
        .hexagon-diagram {
            width: 1200px;
            height: 1100px;
        }
        
        .center-image {
            width: 360px;
            height: 360px;
        }
        
        .hexagon-node {
            width: 220px;
            height: 220px;
        }
        
        .node-1 { top: 20px; }
        .node-2 { top: 130px; right: 350px; }
        .node-3 { top: 490px; right: 270px; }
        .node-4 { bottom: 20px; }
        .node-5 { top: 490px; left: 270px; }
        .node-6 { top: 130px; left: 350px; }
    }
    
    @media (max-width: 1200px) {
        .hexagon-diagram {
            width: 1000px;
            height: 900px;
        }
        
        .center-image {
            width: 320px;
            height: 320px;
        }
        
        .hexagon-node {
            width: 200px;
            height: 200px;
        }
        
        .node-1 { top: 15px; }
        .node-2 { top: 110px; right: 290px; }
        .node-3 { top: 420px; right: 230px; }
        .node-4 { bottom: 15px; }
        .node-5 { top: 420px; left: 230px; }
        .node-6 { top: 110px; left: 290px; }
    }
    
    @media (max-width: 1000px) {
        .hexagon-diagram {
            width: 850px;
            height: 800px;
        }
        
        .center-image {
            width: 280px;
            height: 280px;
        }
        
        .hexagon-node {
            width: 180px;
            height: 180px;
        }
        
        .node-1 { top: 10px; }
        .node-2 { top: 100px; right: 240px; }
        .node-3 { top: 370px; right: 190px; }
        .node-4 { bottom: 10px; }
        .node-5 { top: 370px; left: 190px; }
        .node-6 { top: 100px; left: 240px; }
    }
    
    @media (max-width: 850px) {
        .hexagon-diagram {
            width: 700px;
            height: 700px;
        }
        
        .center-image {
            width: 240px;
            height: 240px;
        }
        
        .hexagon-node {
            width: 160px;
            height: 160px;
        }
        
        .node-1 { top: 8px; }
        .node-2 { top: 90px; right: 190px; }
        .node-3 { top: 320px; right: 150px; }
        .node-4 { bottom: 8px; }
        .node-5 { top: 320px; left: 150px; }
        .node-6 { top: 90px; left: 190px; }
    }
    
    @media (max-width: 700px) {
        .diagram-container {
            min-height: 90vh;
        }
        
        .hexagon-diagram {
            width: 100%;
            height: 650px;
            max-width: 600px;
        }
        
        .center-image {
            width: 200px;
            height: 200px;
        }
        
        .hexagon-node {
            width: 140px;
            height: 140px;
        }
        
        .node-1 { top: 5px; }
        .node-2 { top: 80px; right: 150px; }
        .node-3 { top: 280px; right: 120px; }
        .node-4 { bottom: 5px; }
        .node-5 { top: 280px; left: 120px; }
        .node-6 { top: 80px; left: 150px; }
        
        .info-panel {
            width: 95%;
            padding: 2rem;
            max-height: 85vh;
        }
        
        .info-title {
            font-size: 2rem;
        }
        
        .info-subtitle {
            font-size: 1.3rem;
        }
        
        .info-content p {
            font-size: 1.1rem;
        }
    }
    
    @media (max-width: 480px) {
        .hexagon-diagram {
            height: 550px;
        }
        
        .center-image {
            width: 170px;
            height: 170px;
        }
        
        .hexagon-node {
            width: 120px;
            height: 120px;
        }
        
        .node-1 { top: 3px; }
        .node-2 { top: 70px; right: 110px; }
        .node-3 { top: 240px; right: 90px; }
        .node-4 { bottom: 3px; }
        .node-5 { top: 240px; left: 90px; }
        .node-6 { top: 70px; left: 110px; }
        
        .info-panel {
            padding: 1.5rem;
        }
        
        .info-title {
            font-size: 1.8rem;
        }
        
        .close-btn {
            top: 1rem;
            right: 1rem;
            font-size: 2rem;
            width: 40px;
            height: 40px;
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
        node.addEventListener('click', function(e) {
            e.stopPropagation();
            const nodeId = this.dataset.node;
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