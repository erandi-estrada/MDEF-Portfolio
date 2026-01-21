<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<div class="diagram-container">
    <h1 class="diagram-title">House Sparrow Urban Trap</h1>
    <p class="diagram-subtitle">Health Decline Without Escape</p>
    
    <div class="hexagon-diagram">
        <!-- Imagen central fija -->
        <div class="center-image">
            <img src="../../Diagrama/Centro.png" alt="House Sparrow Urban Trap Center">
        </div>
        
        <!-- Nodo 1 - Parte superior -->
        <div class="hexagon-node node-1" data-node="1">
            <div class="hexagon-card">
                <div class="card-front">
                    <img src="../../Diagrama/1.png" alt="Urban Attractors and Constraints">
                </div>
                <div class="card-back">
                    <img src="../../Diagrama/1b.png" alt="Urban Attractors Details">
                </div>
            </div>
            <!-- Flecha hacia el centro -->
            <div class="arrow arrow-1"></div>
        </div>
        
        <!-- Nodo 2 - Superior derecha -->
        <div class="hexagon-node node-2" data-node="2">
            <div class="hexagon-card">
                <div class="card-front">
                    <img src="../../Diagrama/2.png" alt="Dietary Poverty & Toxic Intake">
                </div>
                <div class="card-back">
                    <img src="../../Diagrama/2b.png" alt="Dietary Poverty Details">
                </div>
            </div>
            <div class="arrow arrow-2"></div>
        </div>
        
        <!-- Nodo 3 - Inferior derecha -->
        <div class="hexagon-node node-3" data-node="3">
            <div class="hexagon-card">
                <div class="card-front">
                    <img src="../../Diagrama/3.png" alt="Chronic Stress and Energetic Drain">
                </div>
                <div class="card-back">
                    <img src="../../Diagrama/3b.png" alt="Chronic Stress Details">
                </div>
            </div>
            <div class="arrow arrow-3"></div>
        </div>
        
        <!-- Nodo 4 - Parte inferior -->
        <div class="hexagon-node node-4" data-node="4">
            <div class="hexagon-card">
                <div class="card-front">
                    <img src="../../Diagrama/4.png" alt="Impaired Foraging Behavior and Decision-Making">
                </div>
                <div class="card-back">
                    <img src="../../Diagrama/4b.png" alt="Foraging Behavior Details">
                </div>
            </div>
            <div class="arrow arrow-4"></div>
        </div>
        
        <!-- Nodo 5 - Inferior izquierda -->
        <div class="hexagon-node node-5" data-node="5">
            <div class="hexagon-card">
                <div class="card-front">
                    <img src="../../Diagrama/5.png" alt="Density, Waste, and Compounding Exposure">
                </div>
                <div class="card-back">
                    <img src="../../Diagrama/5b.png" alt="Density Waste Details">
                </div>
            </div>
            <div class="arrow arrow-5"></div>
        </div>
        
        <!-- Nodo 6 - Superior izquierda -->
        <div class="hexagon-node node-6" data-node="6">
            <div class="hexagon-card">
                <div class="card-front">
                    <img src="../../Diagrama/6.png" alt="Health Decline Without Escape">
                </div>
                <div class="card-back">
                    <img src="../../Diagrama/6b.png" alt="Health Decline Details">
                </div>
            </div>
            <div class="arrow arrow-6"></div>
        </div>
    </div>
    
    <!-- Panel de información que aparece al pasar el cursor -->
    <div class="info-panel">
        <div class="info-content">
            <h3 class="info-title">Urban Attractors and Constraints</h3>
            <div class="info-subtitle">High urban density</div>
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
        max-width: 1200px;
        margin: 2rem auto;
        padding: 0 1rem;
        position: relative;
    }
    
    .diagram-title {
        font-size: 2.5rem;
        font-weight: 700;
        color: #2d3748;
        text-align: center;
        margin-bottom: 0.5rem;
    }
    
    .diagram-subtitle {
        font-size: 1.2rem;
        color: #4a5568;
        text-align: center;
        margin-bottom: 3rem;
        font-style: italic;
    }
    
    /* Contenedor hexagonal */
    .hexagon-diagram {
        position: relative;
        width: 800px;
        height: 700px;
        margin: 0 auto;
    }
    
    /* Imagen central */
    .center-image {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 200px;
        height: 200px;
        z-index: 1;
    }
    
    .center-image img {
        width: 100%;
        height: 100%;
        object-fit: contain;
        border-radius: 50%;
        box-shadow: 0 8px 30px rgba(0,0,0,0.15);
        border: 3px solid #1976d2;
    }
    
    /* Nodos del hexágono */
    .hexagon-node {
        position: absolute;
        width: 140px;
        height: 140px;
        cursor: pointer;
        transition: transform 0.3s ease;
        z-index: 2;
    }
    
    .hexagon-node:hover {
        transform: scale(1.05);
    }
    
    /* Posiciones de los nodos en forma de hexágono */
    .node-1 { top: 50px; left: 50%; transform: translateX(-50%); }
    .node-2 { top: 150px; right: 200px; }
    .node-3 { top: 350px; right: 150px; }
    .node-4 { bottom: 50px; left: 50%; transform: translateX(-50%); }
    .node-5 { top: 350px; left: 150px; }
    .node-6 { top: 150px; left: 200px; }
    
    /* Tarjeta que gira */
    .hexagon-card {
        width: 100%;
        height: 100%;
        position: relative;
        transform-style: preserve-3d;
        transition: transform 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        border-radius: 50%;
    }
    
    .hexagon-node:hover .hexagon-card {
        transform: rotateY(180deg);
    }
    
    .card-front, .card-back {
        position: absolute;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;
        border-radius: 50%;
        overflow: hidden;
    }
    
    .card-front img, .card-back img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
    
    .card-back {
        transform: rotateY(180deg);
    }
    
    /* Flechas hacia el centro */
    .arrow {
        position: absolute;
        background: linear-gradient(to right, #1976d2, #42a5f5);
        height: 3px;
        z-index: 0;
    }
    
    .arrow::after {
        content: '';
        position: absolute;
        right: -10px;
        top: -5px;
        border-left: 10px solid #1976d2;
        border-top: 5px solid transparent;
        border-bottom: 5px solid transparent;
    }
    
    /* Posiciones y ángulos de las flechas */
    .arrow-1 {
        width: 150px;
        top: 140px;
        left: 50%;
        transform: translateX(-50%) rotate(180deg);
    }
    
    .arrow-2 {
        width: 170px;
        top: 70px;
        left: -60px;
        transform: rotate(120deg);
    }
    
    .arrow-3 {
        width: 170px;
        top: 100px;
        left: -140px;
        transform: rotate(60deg);
    }
    
    .arrow-4 {
        width: 150px;
        bottom: 140px;
        left: 50%;
        transform: translateX(-50%);
    }
    
    .arrow-5 {
        width: 170px;
        bottom: 70px;
        right: -60px;
        transform: rotate(240deg);
    }
    
    .arrow-6 {
        width: 170px;
        bottom: 100px;
        right: -140px;
        transform: rotate(300deg);
    }
    
    /* Panel de información */
    .info-panel {
        position: fixed;
        bottom: 30px;
        right: 30px;
        width: 400px;
        max-height: 500px;
        background: white;
        border-radius: 12px;
        padding: 1.5rem;
        box-shadow: 0 10px 40px rgba(0,0,0,0.15);
        border: 1px solid #e2e8f0;
        opacity: 0;
        transform: translateY(20px);
        transition: opacity 0.4s ease, transform 0.4s ease;
        z-index: 100;
        overflow-y: auto;
    }
    
    .info-panel.active {
        opacity: 1;
        transform: translateY(0);
    }
    
    .info-title {
        font-size: 1.4rem;
        font-weight: 700;
        color: #2d3748;
        margin-bottom: 1rem;
        padding-bottom: 0.5rem;
        border-bottom: 2px solid #1976d2;
    }
    
    .info-subtitle {
        font-size: 1rem;
        font-weight: 600;
        color: #1976d2;
        margin: 1rem 0 0.5rem 0;
    }
    
    .info-content p {
        font-size: 0.95rem;
        line-height: 1.5;
        color: #4a5568;
        margin-bottom: 1rem;
    }
    
    .info-note {
        font-size: 0.9rem;
        font-style: italic;
        color: #718096;
        padding: 1rem;
        background: #f7fafc;
        border-left: 3px solid #e2e8f0;
        margin-top: 1rem;
        border-radius: 4px;
    }
    
    /* Responsive */
    @media (max-width: 1024px) {
        .hexagon-diagram {
            width: 600px;
            height: 550px;
        }
        
        .center-image {
            width: 150px;
            height: 150px;
        }
        
        .hexagon-node {
            width: 110px;
            height: 110px;
        }
        
        .node-1 { top: 40px; }
        .node-2 { top: 120px; right: 150px; }
        .node-3 { top: 280px; right: 120px; }
        .node-4 { bottom: 40px; }
        .node-5 { top: 280px; left: 120px; }
        .node-6 { top: 120px; left: 150px; }
        
        .arrow-1 { width: 120px; top: 110px; }
        .arrow-2 { width: 140px; top: 50px; left: -50px; }
        .arrow-3 { width: 140px; top: 80px; left: -110px; }
        .arrow-4 { width: 120px; bottom: 110px; }
        .arrow-5 { width: 140px; bottom: 50px; right: -50px; }
        .arrow-6 { width: 140px; bottom: 80px; right: -110px; }
        
        .info-panel {
            width: 350px;
            right: 20px;
            bottom: 20px;
        }
    }
    
    @media (max-width: 768px) {
        .hexagon-diagram {
            width: 100%;
            height: 500px;
            max-width: 500px;
        }
        
        .center-image {
            width: 120px;
            height: 120px;
        }
        
        .hexagon-node {
            width: 90px;
            height: 90px;
        }
        
        .node-1 { top: 30px; }
        .node-2 { top: 100px; right: 100px; }
        .node-3 { top: 220px; right: 80px; }
        .node-4 { bottom: 30px; }
        .node-5 { top: 220px; left: 80px; }
        .node-6 { top: 100px; left: 100px; }
        
        .arrow {
            display: none; /* Ocultar flechas en móvil para simplificar */
        }
        
        .diagram-title {
            font-size: 2rem;
        }
        
        .diagram-subtitle {
            font-size: 1rem;
        }
        
        .info-panel {
            position: static;
            width: 100%;
            max-width: 500px;
            margin: 2rem auto 0;
            opacity: 1;
            transform: none;
        }
    }
    
    @media (max-width: 480px) {
        .hexagon-diagram {
            height: 400px;
        }
        
        .center-image {
            width: 100px;
            height: 100px;
        }
        
        .hexagon-node {
            width: 70px;
            height: 70px;
        }
        
        .node-1 { top: 20px; }
        .node-2 { top: 80px; right: 70px; }
        .node-3 { top: 180px; right: 50px; }
        .node-4 { bottom: 20px; }
        .node-5 { top: 180px; left: 50px; }
        .node-6 { top: 80px; left: 70px; }
        
        .info-title {
            font-size: 1.2rem;
        }
        
        .info-content p {
            font-size: 0.9rem;
        }
    }
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const nodes = document.querySelectorAll('.hexagon-node');
    const infoPanel = document.querySelector('.info-panel');
    const infoTitle = infoPanel.querySelector('.info-title');
    const infoContent = infoPanel.querySelector('.info-content');
    
    // Datos para cada nodo
    const nodeData = {
        1: {
            title: "Urban Attractors and Constraints",
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
            title: "Dietary Poverty & Toxic Intake",
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
            title: "Chronic Stress and Energetic Drain",
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
            title: "Impaired Foraging Behavior and Decision-Making",
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
            title: "Density, Waste, and Compounding Exposure",
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
            title: "Health Decline Without Escape",
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
    
    // Event listeners para cada nodo
    nodes.forEach(node => {
        const nodeId = node.dataset.node;
        
        node.addEventListener('mouseenter', function() {
            const data = nodeData[nodeId];
            if (data) {
                infoTitle.textContent = data.title;
                infoContent.innerHTML = data.content;
                infoPanel.classList.add('active');
            }
        });
        
        node.addEventListener('mouseleave', function() {
            infoPanel.classList.remove('active');
        });
    });
    
    // Cerrar panel al hacer clic fuera
    document.addEventListener('click', function(event) {
        if (!event.target.closest('.hexagon-node') && !event.target.closest('.info-panel')) {
            infoPanel.classList.remove('active');
        }
    });
    
    // Para dispositivos táctiles
    nodes.forEach(node => {
        node.addEventListener('touchstart', function(e) {
            e.preventDefault();
            const nodeId = node.dataset.node;
            const data = nodeData[nodeId];
            
            if (data) {
                infoTitle.textContent = data.title;
                infoContent.innerHTML = data.content;
                infoPanel.classList.toggle('active');
            }
        });
    });
});
</script>