<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<div class="diagram-container">
    <div class="hexagon-diagram">
        <!-- Imagen central grande -->
        <div class="center-image">
            <img src="../../Diagrama/Centro.png" alt="Urban Sparrow Center">
            <div class="center-glow"></div>
        </div>
        
        <!-- Nodo 1 - Parte superior -->
        <div class="hexagon-node node-1" data-node="1">
            <div class="node-content">
                <img src="../../Diagrama/1.png" alt="Urban Attractors and Constraints">
                <div class="node-glow" style="background: linear-gradient(45deg, #1976d2, #42a5f5);"></div>
            </div>
            <div class="node-pulse"></div>
        </div>
        
        <!-- Nodo 2 - Superior derecha -->
        <div class="hexagon-node node-2" data-node="2">
            <div class="node-content">
                <img src="../../Diagrama/2.png" alt="Dietary Poverty & Toxic Intake">
                <div class="node-glow" style="background: linear-gradient(45deg, #388e3c, #66bb6a);"></div>
            </div>
            <div class="node-pulse"></div>
        </div>
        
        <!-- Nodo 3 - Inferior derecha -->
        <div class="hexagon-node node-3" data-node="3">
            <div class="node-content">
                <img src="../../Diagrama/3.png" alt="Chronic Stress and Energetic Drain">
                <div class="node-glow" style="background: linear-gradient(45deg, #f57c00, #ffb74d);"></div>
            </div>
            <div class="node-pulse"></div>
        </div>
        
        <!-- Nodo 4 - Parte inferior -->
        <div class="hexagon-node node-4" data-node="4">
            <div class="node-content">
                <img src="../../Diagrama/4.png" alt="Impaired Foraging Behavior and Decision-Making">
                <div class="node-glow" style="background: linear-gradient(45deg, #d32f2f, #ef5350);"></div>
            </div>
            <div class="node-pulse"></div>
        </div>
        
        <!-- Nodo 5 - Inferior izquierda -->
        <div class="hexagon-node node-5" data-node="5">
            <div class="node-content">
                <img src="../../Diagrama/5.png" alt="Density, Waste, and Compounding Exposure">
                <div class="node-glow" style="background: linear-gradient(45deg, #7b1fa2, #ba68c8);"></div>
            </div>
            <div class="node-pulse"></div>
        </div>
        
        <!-- Nodo 6 - Superior izquierda -->
        <div class="hexagon-node node-6" data-node="6">
            <div class="node-content">
                <img src="../../Diagrama/6.png" alt="Health Decline Without Escape">
                <div class="node-glow" style="background: linear-gradient(45deg, #00796b, #4db6ac);"></div>
            </div>
            <div class="node-pulse"></div>
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
    
    /* Estilos del diagrama */
    .diagram-container {
        width: 100%;
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        position: relative;
        overflow: hidden;
    }
    
    /* Contenedor hexagonal */
    .hexagon-diagram {
        position: relative;
        width: 1000px;
        height: 900px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    
    /* Imagen central - LA MÁS GRANDE */
    .center-image {
        position: absolute;
        width: 350px;
        height: 350px;
        z-index: 10;
        animation: float 6s ease-in-out infinite;
    }
    
    .center-image img {
        width: 100%;
        height: 100%;
        object-fit: contain;
        border-radius: 50%;
        border: 4px solid #1976d2;
        box-shadow: 
            0 0 30px rgba(25, 118, 210, 0.3),
            0 0 60px rgba(25, 118, 210, 0.2),
            0 0 90px rgba(25, 118, 210, 0.1);
    }
    
    .center-glow {
        position: absolute;
        width: 400px;
        height: 400px;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        background: radial-gradient(circle, rgba(25, 118, 210, 0.15) 0%, transparent 70%);
        border-radius: 50%;
        z-index: 9;
        animation: pulse 4s ease-in-out infinite;
    }
    
    /* Nodos del hexágono */
    .hexagon-node {
        position: absolute;
        width: 180px;
        height: 180px;
        cursor: pointer;
        z-index: 20;
        transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        filter: drop-shadow(0 5px 15px rgba(0, 0, 0, 0.1));
    }
    
    .hexagon-node:hover {
        transform: scale(1.15) translateZ(0);
        filter: drop-shadow(0 10px 25px rgba(0, 0, 0, 0.2));
        z-index: 30;
    }
    
    .node-content {
        width: 100%;
        height: 100%;
        position: relative;
        border-radius: 50%;
        overflow: hidden;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    
    .node-content img {
        width: 90%;
        height: 90%;
        object-fit: contain;
        border-radius: 50%;
        position: relative;
        z-index: 2;
        transition: transform 0.3s ease;
    }
    
    .hexagon-node:hover .node-content img {
        transform: scale(1.05);
    }
    
    .node-glow {
        position: absolute;
        width: 100%;
        height: 100%;
        border-radius: 50%;
        opacity: 0.3;
        z-index: 1;
        filter: blur(10px);
        transition: opacity 0.3s ease;
    }
    
    .hexagon-node:hover .node-glow {
        opacity: 0.6;
        filter: blur(15px);
    }
    
    .node-pulse {
        position: absolute;
        width: 100%;
        height: 100%;
        border-radius: 50%;
        z-index: 0;
        opacity: 0;
        transition: all 0.3s ease;
    }
    
    .hexagon-node:hover .node-pulse {
        animation: pulse 2s ease-in-out infinite;
    }
    
    /* Posiciones de los nodos en forma de hexágono */
    .node-1 { 
        top: 50px; 
        left: 50%; 
        transform: translateX(-50%);
    }
    .node-2 { 
        top: 180px; 
        right: 250px; 
    }
    .node-3 { 
        top: 450px; 
        right: 200px; 
    }
    .node-4 { 
        bottom: 50px; 
        left: 50%; 
        transform: translateX(-50%);
    }
    .node-5 { 
        top: 450px; 
        left: 200px; 
    }
    .node-6 { 
        top: 180px; 
        left: 250px; 
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
        backdrop-filter: blur(10px);
        opacity: 0;
        transition: opacity 0.3s ease;
    }
    
    .info-overlay.active {
        display: flex;
        opacity: 1;
        animation: fadeIn 0.3s ease;
    }
    
    .info-panel {
        background: white;
        border-radius: 20px;
        width: 90%;
        max-width: 700px;
        max-height: 80vh;
        padding: 2.5rem;
        position: relative;
        box-shadow: 
            0 20px 60px rgba(0, 0, 0, 0.3),
            0 0 0 1px rgba(255, 255, 255, 0.1);
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
        font-size: 2rem;
        color: #666;
        cursor: pointer;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.3s ease;
    }
    
    .close-btn:hover {
        background: #f5f5f5;
        color: #333;
        transform: rotate(90deg);
    }
    
    .info-title {
        font-size: 2.2rem;
        font-weight: 700;
        color: #2d3748;
        margin-bottom: 1.5rem;
        padding-bottom: 1rem;
        border-bottom: 3px solid #1976d2;
    }
    
    .info-subtitle {
        font-size: 1.3rem;
        font-weight: 600;
        color: #1976d2;
        margin: 1.8rem 0 0.8rem 0;
        padding-top: 1.5rem;
        border-top: 1px solid #e2e8f0;
    }
    
    .info-subtitle:first-of-type {
        margin-top: 1rem;
        padding-top: 0;
        border-top: none;
    }
    
    .info-content p {
        font-size: 1.1rem;
        line-height: 1.7;
        color: #4a5568;
        margin-bottom: 1.5rem;
    }
    
    .info-note {
        font-size: 1rem;
        font-style: italic;
        color: #718096;
        padding: 1.5rem;
        background: linear-gradient(135deg, #f7fafc 0%, #edf2f7 100%);
        border-left: 4px solid #e2e8f0;
        margin-top: 2rem;
        border-radius: 10px;
        line-height: 1.6;
    }
    
    /* Animaciones */
    @keyframes float {
        0%, 100% {
            transform: translateY(0);
        }
        50% {
            transform: translateY(-15px);
        }
    }
    
    @keyframes pulse {
        0%, 100% {
            transform: translate(-50%, -50%) scale(1);
            opacity: 0.5;
        }
        50% {
            transform: translate(-50%, -50%) scale(1.1);
            opacity: 0.3;
        }
    }
    
    @keyframes fadeIn {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
    
    /* Responsive */
    @media (max-width: 1200px) {
        .hexagon-diagram {
            width: 850px;
            height: 750px;
        }
        
        .center-image {
            width: 300px;
            height: 300px;
        }
        
        .center-glow {
            width: 350px;
            height: 350px;
        }
        
        .hexagon-node {
            width: 160px;
            height: 160px;
        }
        
        .node-1 { top: 40px; }
        .node-2 { top: 150px; right: 210px; }
        .node-3 { top: 380px; right: 170px; }
        .node-4 { bottom: 40px; }
        .node-5 { top: 380px; left: 170px; }
        .node-6 { top: 150px; left: 210px; }
    }
    
    @media (max-width: 900px) {
        .hexagon-diagram {
            width: 700px;
            height: 650px;
        }
        
        .center-image {
            width: 250px;
            height: 250px;
        }
        
        .center-glow {
            width: 300px;
            height: 300px;
        }
        
        .hexagon-node {
            width: 140px;
            height: 140px;
        }
        
        .node-1 { top: 35px; }
        .node-2 { top: 130px; right: 170px; }
        .node-3 { top: 330px; right: 140px; }
        .node-4 { bottom: 35px; }
        .node-5 { top: 330px; left: 140px; }
        .node-6 { top: 130px; left: 170px; }
    }
    
    @media (max-width: 768px) {
        .diagram-container {
            height: 100vh;
            min-height: 800px;
        }
        
        .hexagon-diagram {
            width: 100%;
            height: 700px;
            max-width: 600px;
        }
        
        .center-image {
            width: 220px;
            height: 220px;
        }
        
        .center-glow {
            width: 260px;
            height: 260px;
        }
        
        .hexagon-node {
            width: 120px;
            height: 120px;
        }
        
        .node-1 { top: 30px; }
        .node-2 { top: 110px; right: 140px; }
        .node-3 { top: 290px; right: 110px; }
        .node-4 { bottom: 30px; }
        .node-5 { top: 290px; left: 110px; }
        .node-6 { top: 110px; left: 140px; }
        
        .info-panel {
            width: 95%;
            padding: 2rem;
            max-height: 85vh;
        }
        
        .info-title {
            font-size: 1.8rem;
        }
        
        .info-subtitle {
            font-size: 1.1rem;
        }
        
        .info-content p {
            font-size: 1rem;
        }
    }
    
    @media (max-width: 480px) {
        .hexagon-diagram {
            height: 600px;
        }
        
        .center-image {
            width: 180px;
            height: 180px;
        }
        
        .center-glow {
            width: 220px;
            height: 220px;
        }
        
        .hexagon-node {
            width: 100px;
            height: 100px;
        }
        
        .node-1 { top: 25px; }
        .node-2 { top: 90px; right: 110px; }
        .node-3 { top: 250px; right: 90px; }
        .node-4 { bottom: 25px; }
        .node-5 { top: 250px; left: 90px; }
        .node-6 { top: 90px; left: 110px; }
        
        .info-panel {
            padding: 1.5rem;
        }
        
        .info-title {
            font-size: 1.6rem;
        }
        
        .close-btn {
            top: 1rem;
            right: 1rem;
            font-size: 1.8rem;
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
        node.addEventListener('click', function() {
            const nodeId = this.dataset.node;
            const data = nodeData[nodeId];
            
            if (data) {
                infoTitle.textContent = data.title;
                let fullContent = `<div class="info-subtitle" style="margin-top: 0; padding-top: 0; border-top: none; color: #2d3748; font-size: 1.6rem; font-weight: 700; margin-bottom: 1.5rem;">${data.subtitle}</div>`;
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
    
    // Efecto hover mejorado
    nodes.forEach(node => {
        node.addEventListener('mouseenter', function() {
            this.style.zIndex = '30';
        });
        
        node.addEventListener('mouseleave', function() {
            this.style.zIndex = '20';
        });
    });
});
</script>