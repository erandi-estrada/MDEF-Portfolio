<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<!-- COMIENZA EL MAPA CONSTELACIÓN -->
<style>
    /* Estilos específicos para el mapa constelación */
    .constellation-container {
        position: relative;
        width: 100%;
        height: 100vh;
        min-height: 800px;
        background: #050509;
        overflow: hidden;
        margin: 3rem 0;
        border-radius: 12px;
    }
    
    /* Fondo estrellado */
    .starfield {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-image: 
            radial-gradient(1px 1px at 20px 30px, rgba(242, 242, 242, 0.3) 1px, transparent 0),
            radial-gradient(1px 1px at 40px 70px, rgba(242, 242, 242, 0.3) 1px, transparent 0),
            radial-gradient(1px 1px at 60px 20px, rgba(242, 242, 242, 0.3) 1px, transparent 0),
            radial-gradient(1.5px 1.5px at 80px 50px, rgba(255, 221, 0, 0.4) 1px, transparent 0),
            radial-gradient(1.5px 1.5px at 100px 80px, rgba(138, 63, 252, 0.4) 1px, transparent 0),
            radial-gradient(2px 2px at 120px 30px, rgba(28, 100, 242, 0.4) 1px, transparent 0);
        background-size: 200px 200px;
        animation: twinkle 8s infinite alternate;
    }
    
    @keyframes twinkle {
        0%, 100% { opacity: 0.5; }
        50% { opacity: 1; }
    }
    
    /* Órbitas */
    .orbit {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border-radius: 50%;
        border: 1px solid rgba(242, 242, 242, 0.1);
    }
    
    .orbit-1 { width: 180px; height: 180px; }
    .orbit-2 { width: 320px; height: 320px; }
    .orbit-3 { width: 460px; height: 460px; }
    .orbit-4 { width: 600px; height: 600px; }
    
    /* Nodos */
    .node {
        position: absolute;
        width: 120px;
        height: 120px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        transition: all 0.3s ease;
        text-align: center;
        padding: 1rem;
        font-weight: 600;
        z-index: 5;
        color: #050509;
    }
    
    .node:hover {
        transform: scale(1.15);
        z-index: 20;
    }
    
    /* Colores según tu paleta */
    .node-central { 
        background: linear-gradient(135deg, #1C64F2 0%, #FFDD00 100%);
        width: 160px;
        height: 160px;
        box-shadow: 0 0 60px rgba(28, 100, 242, 0.4);
        animation: pulse 4s infinite alternate;
    }
    
    .node-urban { background-color: #8A3FFC; }
    .node-hostile { background-color: #FF9F1C; }
    .node-species { background-color: #FFDD00; }
    .node-research { background-color: #00C49A; }
    .node-action { background-color: #E11D48; color: #F2F2F2; }
    .node-question { 
        background-color: transparent; 
        border: 2px solid #F2F2F2; 
        width: 80px; 
        height: 80px; 
        color: #F2F2F2;
    }
    .node-project { background: linear-gradient(135deg, #8A3FFC 0%, #E11D48 100%); }
    
    @keyframes pulse {
        0% { box-shadow: 0 0 60px rgba(28, 100, 242, 0.4); }
        100% { box-shadow: 0 0 90px rgba(28, 100, 242, 0.6); }
    }
    
    /* Líneas de conexión */
    .connection {
        position: absolute;
        height: 2px;
        background: linear-gradient(90deg, #00C49A, #F2F2F2);
        transform-origin: 0 0;
        z-index: 1;
        opacity: 0.3;
        transition: opacity 0.3s ease;
    }
    
    /* Modal para contenido */
    .constellation-modal {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(5, 5, 9, 0.95);
        display: none;
        align-items: center;
        justify-content: center;
        z-index: 10000;
        backdrop-filter: blur(5px);
    }
    
    .constellation-modal.active {
        display: flex;
    }
    
    .modal-content {
        background: #050509;
        border-radius: 20px;
        padding: 2.5rem;
        max-width: 700px;
        width: 90%;
        max-height: 80vh;
        overflow-y: auto;
        border: 1px solid rgba(242, 242, 242, 0.1);
        box-shadow: 0 0 50px rgba(28, 100, 242, 0.3);
        color: #F2F2F2;
    }
    
    .modal-close {
        position: absolute;
        top: 1rem;
        right: 1.5rem;
        background: none;
        border: none;
        color: #F2F2F2;
        font-size: 1.8rem;
        cursor: pointer;
    }
    
    /* Títulos del mapa */
    .map-title {
        text-align: center;
        padding: 2rem;
        color: #F2F2F2;
    }
    
    .map-title h2 {
        font-size: 2.5rem;
        margin-bottom: 1rem;
        background: linear-gradient(90deg, #1C64F2, #8A3FFC);
        -webkit-background-clip: text;
        background-clip: text;
        color: transparent;
    }
    
    /* Responsive */
    @media (max-width: 1100px) {
        .orbit-1 { width: 150px; height: 150px; }
        .orbit-2 { width: 270px; height: 270px; }
        .orbit-3 { width: 390px; height: 390px; }
        .orbit-4 { width: 510px; height: 510px; }
        
        .node { width: 100px; height: 100px; font-size: 0.9rem; }
        .node-central { width: 140px; height: 140px; }
    }
    
    @media (max-width: 768px) {
        .constellation-container {
            height: 600px;
            min-height: 600px;
        }
        
        .orbit-1 { width: 120px; height: 120px; }
        .orbit-2 { width: 220px; height: 220px; }
        .orbit-3 { width: 320px; height: 320px; }
        .orbit-4 { width: 420px; height: 420px; }
        
        .node { width: 80px; height: 80px; font-size: 0.8rem; padding: 0.5rem; }
        .node-central { width: 120px; height: 120px; font-size: 0.9rem; }
        .node-question { width: 60px; height: 60px; }
        
        .map-title h2 { font-size: 2rem; }
    }
</style>

<div class="map-title">
    <h2>🌌 CONSTELLATION MAP — THE INVISIBLE CITY</h2>
    <p>Navigate through interconnected concepts. Click on any node to explore.</p>
</div>

<div class="constellation-container">
    <div class="starfield"></div>
    
 <!-- Órbitas visuales -->
 <div class="orbit orbit-1"></div>
    <div class="orbit orbit-2"></div>
    <div class="orbit orbit-3"></div>
    <div class="orbit orbit-4"></div>
    
   <!-- NÚCLEO CENTRAL -->
<div class="node node-central" style="top: 50%; left: 50%; transform: translate(-50%, -50%);" data-modal="central">
        <div style="text-align: center; padding: 1rem;">
            <strong>THE INVISIBLE CITY</strong>
            <div style="font-size: 0.8rem; margin-top: 0.5rem;">Core Concept</div>
        </div>
    </div>
    
<!-- PRIMERA ÓRBITA - 4 clusters -->
<div class="node node-urban" style="top: 30%; left: 30%;" data-modal="urban">
        <div>Urban Aesthetics</div>
    </div>
    
 <div class="node node-hostile" style="top: 30%; left: 70%;" data-modal="hostile">
        <div>Hostile Design</div>
    </div>
    
  <div class="node node-species" style="top: 70%; left: 30%;" data-modal="species">
        <div>Multispecies Justice</div>
    </div>
    
 <div class="node node-research" style="top: 70%; left: 70%;" data-modal="research">
        <div>Embodied Research</div>
    </div>
    
  <!-- SEGUNDA ÓRBITA - Preguntas -->
  <div class="node node-question" style="top: 15%; left: 50%;" data-modal="question1">
        <div>What lives are allowed?</div>
    </div>
    
 <div class="node node-question" style="top: 50%; left: 85%;" data-modal="question2">
        <div>How does beauty justify exclusion?</div>
    </div>
    
 <div class="node node-question" style="top: 85%; left: 50%;" data-modal="question3">
        <div>Can design generate empathy?</div>
    </div>
    
 <div class="node node-question" style="top: 50%; left: 15%;" data-modal="question4">
        <div>What bodies can rest?</div>
    </div>
    
 <!-- TERCERA ÓRBITA - Acciones -->
<div class="node node-action" style="top: 20%; left: 20%;" data-modal="action1">
        <div>Sitting on hostile architecture</div>
    </div>
    
 <div class="node node-action" style="top: 20%; left: 80%;" data-modal="action2">
        <div>Returning Life interventions</div>
    </div>
    
 <div class="node node-action" style="top: 80%; left: 20%;" data-modal="action3">
        <div>Wearing Hostility</div>
    </div>
    
 <div class="node node-action" style="top: 80%; left: 80%;" data-modal="action4">
        <div>Sensory translation</div>
    </div>
    
 <!-- CUARTA ÓRBITA - Proyectos -->
 <div class="node node-project" style="top: 10%; left: 10%;" data-modal="project1">
        <div>Beauty That Excludes</div>
    </div>
    
 <div class="node node-project" style="top: 10%; left: 90%;" data-modal="project2">
        <div>Sensory Multispecies Translation</div>
    </div>
    
  <!-- Contenedor para líneas de conexión -->
 <div class="connections-container" id="connections"></div>
</div>

<!-- Modal para contenido -->
<div class="constellation-modal" id="constellationModal">
    <div class="modal-content">
        <button class="modal-close" id="modalClose">×</button>
        <h3 id="modalTitle">Title</h3>
        <div id="modalBody">
            Content will appear here
        </div>
    </div>
</div>

<script>
    // Datos para cada nodo
    const constellationData = {
        central: {
            title: "🌌 THE INVISIBLE CITY",
            content: `<p><em>"The city looks beautiful, but its beauty hides systematic violence against both humans and non-human life."</em></p>
                     <p><strong>Core intuition:</strong> This is the gravitational center of your conceptual universe.</p>
                     <p><strong>Sub-intuitions:</strong></p>
                     <ul>
                         <li>Beauty as control</li>
                         <li>Violence as absence</li>
                         <li>Life expelled from the urban image</li>
                     </ul>`
        },
        urban: {
            title: "🟣 Urban Aesthetics",
            content: `<p><strong>Beauty as ideology, cleanliness as political tool</strong></p>
                     <ul>
                         <li>Beauty as ideology</li>
                         <li>Cleanliness as political tool</li>
                         <li>City as spectacle</li>
                         <li>Nature as decoration</li>
                         <li>Controlled public space</li>
                         <li>Aesthetic erasure (graffiti removal)</li>
                         <li>Order vs Life</li>
                     </ul>
                     <p>How aesthetic standards in urban design serve to normalize exclusion and control.</p>`
        },
        hostile: {
            title: "🔵 Hostile Design / Urban Violence",
            content: `<p><strong>Architecture that excludes through discomfort</strong></p>
                     <ul>
                         <li>Anti-homeless architecture</li>
                         <li>Anti-pigeon spikes</li>
                         <li>Spacing barriers</li>
                         <li>Seating deterrents</li>
                         <li>Smooth surfaces that deny rest</li>
                         <li>Safety disguised as exclusion</li>
                         <li>Violence normalized through design</li>
                     </ul>
                     <p>Physical manifestations of invisible systemic exclusion.</p>`
        },
        species: {
            title: "🟢 Multispecies Justice",
            content: `<p><strong>Questioning the urban hierarchy of life</strong></p>
                     <ul>
                         <li>Urban species hierarchy</li>
                         <li>Non-human citizenship</li>
                         <li>Pigeons as expelled residents</li>
                         <li>Plant life removed as "dirt"</li>
                         <li>Pollution impacting insects + birds</li>
                         <li>Who has the right to the city?</li>
                         <li>Urban ecosystems as political bodies</li>
                     </ul>
                     <p>Expanding the right to the city beyond the human.</p>`
        },
        action1: {
            title: "🌑 Action: Sitting on hostile architecture",
            content: `<p><strong>Reveals:</strong></p>
                     <ul>
                         <li>Normalized micro-violence</li>
                         <li>Human discomfort exposes architectural hostility</li>
                         <li>The body as sensor for urban violence</li>
                     </ul>
                     <p>By physically occupying hostile designs, this action makes visible the normalized violence of urban furniture.</p>`
        },
        project1: {
            title: "⭐ Constellation A — Beauty That Excludes",
            content: `<p><strong>Connects most strongly with:</strong></p>
                     <ul>
                         <li>Urban Aesthetics (beauty as control)</li>
                         <li>Hostile Design (physical exclusion)</li>
                         <li>Embodied Research (experiencing exclusion firsthand)</li>
                     </ul>
                     <p><strong>Core thesis:</strong> The city's beauty is not neutral but actively produces exclusion. Urban design naturalizes violence through aesthetic pleasure.</p>`
        }
    };
    
    // Elementos DOM
    const modal = document.getElementById('constellationModal');
    const modalClose = document.getElementById('modalClose');
    const modalTitle = document.getElementById('modalTitle');
    const modalBody = document.getElementById('modalBody');
    const nodes = document.querySelectorAll('.node');
    
    // Abrir modal al hacer clic en nodo
    nodes.forEach(node => {
        node.addEventListener('click', function() {
            const modalId = this.getAttribute('data-modal');
            
            if (constellationData[modalId]) {
                modalTitle.textContent = constellationData[modalId].title;
                modalBody.innerHTML = constellationData[modalId].content;
                modal.classList.add('active');
            }
        });
    });
    
    // Cerrar modal
    modalClose.addEventListener('click', () => modal.classList.remove('active'));
    modal.addEventListener('click', (e) => {
        if (e.target === modal) modal.classList.remove('active');
    });
    
    // Crear líneas de conexión
    function createConnections() {
        const container = document.getElementById('connections');
        const central = document.querySelector('.node-central');
        
        // Conectar nodos principales al centro
        const mainNodes = document.querySelectorAll('.node-urban, .node-hostile, .node-species, .node-research');
        
        mainNodes.forEach(node => {
            const line = document.createElement('div');
            line.className = 'connection';
            
            // Posicionamiento relativo
            const cRect = central.getBoundingClientRect();
            const nRect = node.getBoundingClientRect();
            const contRect = document.querySelector('.constellation-container').getBoundingClientRect();
            
            const x1 = cRect.left + cRect.width/2 - contRect.left;
            const y1 = cRect.top + cRect.height/2 - contRect.top;
            const x2 = nRect.left + nRect.width/2 - contRect.left;
            const y2 = nRect.top + nRect.height/2 - contRect.top;
            
            // Calcular ángulo y distancia
            const length = Math.sqrt(Math.pow(x2 - x1, 2) + Math.pow(y2 - y1, 2));
            const angle = Math.atan2(y2 - y1, x2 - x1) * 180 / Math.PI;
            
            line.style.width = `${length}px`;
            line.style.left = `${x1}px`;
            line.style.top = `${y1}px`;
            line.style.transform = `rotate(${angle}deg)`;
            
            container.appendChild(line);
        });
    }
    
    // Inicializar cuando se cargue la página
    window.addEventListener('load', createConnections);
    window.addEventListener('resize', () => {
        document.getElementById('connections').innerHTML = '';
        createConnections();
    });
</script>
<!-- FIN DEL MAPA CONSTELACIÓN -->