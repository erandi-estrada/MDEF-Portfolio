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
        </div>
    </div>
    
    <!-- Panel de información que aparece al pasar el cursor -->
    <div class="info-panel">
        <div class="info-content">
            <h3 class="info-title">House Sparrow</h3>
            <div class="info-subtitle">Health Decline Without Escape</div>
            <ul class="info-list">
                <li>Urban Attractors and Constraints</li>
                <li>Dietary Poverty & Toxic Intake</li>
                <li>Chronic Stress and Energetic Drain</li>
                <li>Impaired Foraging Behavior and Decision-Making</li>
                <li>Density, Waste, and Compounding Exposure</li>
                <li>Health Decline Without Escape</li>
            </ul>
            
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
        max-width: 1600px;
        margin: 2rem auto;
        padding: 0 1rem;
        position: relative;
    }
    
    .diagram-title {
        font-size: 2.8rem;
        font-weight: 700;
        color: #2d3748;
        text-align: center;
        margin-bottom: 0.5rem;
    }
    
    .diagram-subtitle {
        font-size: 1.4rem;
        color: #4a5568;
        text-align: center;
        margin-bottom: 3rem;
        font-style: italic;
    }
    
    /* Contenedor hexagonal - MÁS GRANDE Y ESPACIADO */
    .hexagon-diagram {
        position: relative;
        width: 1200px;
        height: 1100px;
        margin: 0 auto;
    }
    
    /* Imagen central */
    .center-image {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 250px;
        height: 250px;
        z-index: 1;
    }
    
    .center-image img {
        width: 100%;
        height: 100%;
        object-fit: contain;
        border-radius: 50%;
        box-shadow: 0 8px 30px rgba(0,0,0,0.15);
        border: 4px solid #1976d2;
    }
    
    /* Nodos del hexágono - MÁS GRANDES Y ESPACIADOS */
    .hexagon-node {
        position: absolute;
        width: 220px;
        height: 220px;
        cursor: pointer;
        transition: all 0.3s ease;
        z-index: 2;
    }
    
    .hexagon-node:hover {
        transform: scale(1.1);
    }
    
    /* POSICIONES MÁS ESPACIADAS - HEXÁGONO MÁS GRANDE */
    .node-1 { 
        top: 50px; 
        left: 50%; 
        transform: translateX(-50%);
    }
    .node-2 { 
        top: 200px; 
        right: 280px; 
    }
    .node-3 { 
        top: 500px; 
        right: 220px; 
    }
    .node-4 { 
        bottom: 50px; 
        left: 50%; 
        transform: translateX(-50%);
    }
    .node-5 { 
        top: 500px; 
        left: 220px; 
    }
    .node-6 { 
        top: 200px; 
        left: 280px; 
    }
    
    /* Tarjeta que gira - GIRAR EN SU EJE */
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
        display: flex;
        align-items: center;
        justify-content: center;
    }
    
    /* IMÁGENES VISIBLES - CONTENEDOR MÁS PEQUEÑO PARA VER LAS IMÁGENES */
    .card-front img, .card-back img {
        width: 90%;
        height: 90%;
        object-fit: contain;
        border-radius: 50%;
    }
    
    .card-back {
        transform: rotateY(180deg);
    }
    
    /* Panel de información */
    .info-panel {
        position: fixed;
        bottom: 40px;
        right: 40px;
        width: 500px;
        max-height: 650px;
        background: white;
        border-radius: 16px;
        padding: 2.5rem;
        box-shadow: 0 15px 50px rgba(0,0,0,0.2);
        border: 2px solid #e2e8f0;
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
        font-size: 1.8rem;
        font-weight: 700;
        color: #2d3748;
        margin-bottom: 0.8rem;
        padding-bottom: 0.8rem;
        border-bottom: 3px solid #1976d2;
    }
    
    .info-list {
        list-style-type: none;
        padding: 0;
        margin: 1.5rem 0;
        border-left: 3px solid #e2e8f0;
        padding-left: 1.5rem;
    }
    
    .info-list li {
        font-size: 1rem;
        color: #4a5568;
        margin-bottom: 0.8rem;
        padding-left: 0.5rem;
        position: relative;
    }
    
    .info-list li:before {
        content: "•";
        color: #1976d2;
        font-weight: bold;
        position: absolute;
        left: -0.8rem;
    }
    
    .info-subtitle {
        font-size: 1.2rem;
        font-weight: 600;
        color: #1976d2;
        margin: 1.5rem 0 0.8rem 0;
        padding-top: 1rem;
        border-top: 1px solid #e2e8f0;
    }
    
    .info-content p {
        font-size: 1.05rem;
        line-height: 1.6;
        color: #4a5568;
        margin-bottom: 1.2rem;
    }
    
    .info-note {
        font-size: 1rem;
        font-style: italic;
        color: #718096;
        padding: 1.5rem;
        background: #f7fafc;
        border-left: 4px solid #e2e8f0;
        margin-top: 1.5rem;
        border-radius: 8px;
        line-height: 1.6;
    }
    
    /* Responsive */
    @media (max-width: 1400px) {
        .hexagon-diagram {
            width: 1000px;
            height: 900px;
        }
        
        .node-1 { top: 40px; }
        .node-2 { top: 170px; right: 230px; }
        .node-3 { top: 420px; right: 180px; }
        .node-4 { bottom: 40px; }
        .node-5 { top: 420px; left: 180px; }
        .node-6 { top: 170px; left: 230px; }
        
        .info-panel {
            width: 450px;
        }
    }
    
    @media (max-width: 1100px) {
        .hexagon-diagram {
            width: 850px;
            height: 800px;
        }
        
        .center-image {
            width: 200px;
            height: 200px;
        }
        
        .hexagon-node {
            width: 190px;
            height: 190px;
        }
        
        .node-1 { top: 35px; }
        .node-2 { top: 150px; right: 190px; }
        .node-3 { top: 370px; right: 150px; }
        .node-4 { bottom: 35px; }
        .node-5 { top: 370px; left: 150px; }
        .node-6 { top: 150px; left: 190px; }
        
        .diagram-title {
            font-size: 2.4rem;
        }
        
        .diagram-subtitle {
            font-size: 1.2rem;
        }
        
        .info-panel {
            width: 400px;
            right: 30px;
            bottom: 30px;
        }
    }
    
    @media (max-width: 900px) {
        .hexagon-diagram {
            width: 700px;
            height: 650px;
        }
        
        .center-image {
            width: 180px;
            height: 180px;
        }
        
        .hexagon-node {
            width: 170px;
            height: 170px;
        }
        
        .node-1 { top: 30px; }
        .node-2 { top: 130px; right: 150px; }
        .node-3 { top: 310px; right: 120px; }
        .node-4 { bottom: 30px; }
        .node-5 { top: 310px; left: 120px; }
        .node-6 { top: 130px; left: 150px; }
        
        .info-panel {
            width: 380px;
        }
    }
    
    @media (max-width: 768px) {
        .hexagon-diagram {
            width: 100%;
            height: 600px;
            max-width: 600px;
        }
        
        .center-image {
            width: 160px;
            height: 160px;
        }
        
        .hexagon-node {
            width: 150px;
            height: 150px;
        }
        
        .node-1 { top: 25px; }
        .node-2 { top: 110px; right: 120px; }
        .node-3 { top: 270px; right: 90px; }
        .node-4 { bottom: 25px; }
        .node-5 { top: 270px; left: 90px; }
        .node-6 { top: 110px; left: 120px; }
        
        .info-panel {
            position: static;
            width: 100%;
            max-width: 600px;
            margin: 3rem auto 0;
            opacity: 1;
            transform: none;
        }
        
        .diagram-title {
            font-size: 2rem;
        }
        
        .diagram-subtitle {
            font-size: 1.1rem;
        }
    }
    
    @media (max-width: 480px) {
        .hexagon-diagram {
            height: 500px;
        }
        
        .center-image {
            width: 140px;
            height: 140px;
        }
        
        .hexagon-node {
            width: 130px;
            height: 130px;
        }
        
        .node-1 { top: 20px; }
        .node-2 { top: 90px; right: 90px; }
        .node-3 { top: 220px; right: 70px; }
        .node-4 { bottom: 20px; }
        .node-5 { top: 220px; left: 70px; }
        .node-6 { top: 90px; left: 90px; }
        
        .card-front img, .card-back img {
            width: 85%;
            height: 85%;
        }
        
        .info-title {
            font-size: 1.5rem;
        }
        
        .info-content p {
            font-size: 1rem;
        }
        
        .diagram-title {
            font-size: 1.8rem;
        }
        
        .diagram-subtitle {
            font-size: 1rem;
        }
    }
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const nodes = document.querySelectorAll('.hexagon-node');
    const infoPanel = document.querySelector('.info-panel');
    const infoTitle = infoPanel.querySelector('.info-title');
    const infoContent = infoPanel.querySelector('.info-content');
    
    // Datos para cada nodo CORREGIDOS
    const nodeData = {
        1: {
            title: "House Sparrow",
            subtitle: "Urban Attractors and Constraints",
            content: `
                <ul class="info-list">
                    <li>Urban Attractors and Constraints</li>
                    <li>Dietary Poverty & Toxic Intake</li>
                    <li>Chronic Stress and Energetic Drain</li>
                    <li>Impaired Foraging Behavior and Decision-Making</li>
                    <li>Density, Waste, and Compounding Exposure</li>
                    <li>Health Decline Without Escape</li>
                </ul>
                
                <div class="info-subtitle">Urban Attractors and Constraints</div>
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
                <ul class="info-list">
                    <li>Urban Attractors and Constraints</li>
                    <li>Dietary Poverty & Toxic Intake</li>
                    <li>Chronic Stress and Energetic Drain</li>
                    <li>Impaired Foraging Behavior and Decision-Making</li>
                    <li>Density, Waste, and Compounding Exposure</li>
                    <li>Health Decline Without Escape</li>
                </ul>
                
                <div class="info-subtitle">Dietary Poverty & Toxic Intake</div>
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
                <ul class="info-list">
                    <li>Urban Attractors and Constraints</li>
                    <li>Dietary Poverty & Toxic Intake</li>
                    <li>Chronic Stress and Energetic Drain</li>
                    <li>Impaired Foraging Behavior and Decision-Making</li>
                    <li>Density, Waste, and Compounding Exposure</li>
                    <li>Health Decline Without Escape</li>
                </ul>
                
                <div class="info-subtitle">Chronic Stress and Energetic Drain</div>
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
                <ul class="info-list">
                    <li>Urban Attractors and Constraints</li>
                    <li>Dietary Poverty & Toxic Intake</li>
                    <li>Chronic Stress and Energetic Drain</li>
                    <li>Impaired Foraging Behavior and Decision-Making</li>
                    <li>Density, Waste, and Compounding Exposure</li>
                    <li>Health Decline Without Escape</li>
                </ul>
                
                <div class="info-subtitle">Impaired Foraging Behavior and Decision-Making</div>
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
                <ul class="info-list">
                    <li>Urban Attractors and Constraints</li>
                    <li>Dietary Poverty & Toxic Intake</li>
                    <li>Chronic Stress and Energetic Drain</li>
                    <li>Impaired Foraging Behavior and Decision-Making</li>
                    <li>Density, Waste, and Compounding Exposure</li>
                    <li>Health Decline Without Escape</li>
                </ul>
                
                <div class="info-subtitle">Density, Waste, and Compounding Exposure</div>
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
                <ul class="info-list">
                    <li>Urban Attractors and Constraints</li>
                    <li>Dietary Poverty & Toxic Intake</li>
                    <li>Chronic Stress and Energetic Drain</li>
                    <li>Impaired Foraging Behavior and Decision-Making</li>
                    <li>Density, Waste, and Compounding Exposure</li>
                    <li>Health Decline Without Escape</li>
                </ul>
                
                <div class="info-subtitle">Health Decline Without Escape</div>
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
                // Agregar el subtítulo específico al contenido
                let fullContent = `<div class="info-subtitle" style="margin-top: 0; padding-top: 0; border-top: none; color: #2d3748; font-size: 1.4rem;">${data.subtitle}</div>`;
                fullContent += data.content;
                infoContent.innerHTML = fullContent;
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
                let fullContent = `<div class="info-subtitle" style="margin-top: 0; padding-top: 0; border-top: none; color: #2d3748; font-size: 1.4rem;">${data.subtitle}</div>`;
                fullContent += data.content;
                infoContent.innerHTML = fullContent;
                infoPanel.classList.toggle('active');
            }
        });
    });
});
</script>