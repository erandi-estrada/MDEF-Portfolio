<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<!-- Imagen completa -->
<img src="../../images/AllCards.png" 
     alt="Tarjetas Atlas" 
     width="100%" 
     style="border-radius: 8px; margin: 1rem 0 2rem 0; object-fit: cover;">  

<div class="venn-page"> 

<!-- Diagrama de Venn simplificado -->
<div class="venn-container">
        <div class="venn-diagram">
            <!-- Círculo 1: Rural Punk -->
            <div class="venn-circle circle-1">
                <div class="circle-label">Rural Punk</div>
            </div>
            
<!-- Círculo 2: Anarch Governance -->
<div class="venn-circle circle-2">
                <div class="circle-label">Anarch Governance</div>
            </div>
            
<!-- Círculo 3: Restorative Justice -->
<div class="venn-circle circle-3">
                <div class="circle-label">Restorative Justice</div>
            </div>
            
<!-- Random Triggers -->
<div class="random-triggers">
                <div class="trigger trigger-1">Avatars</div>
                <div class="trigger trigger-2">Ancestral Knowledge</div>
            </div>
            
</div>
    </div>

<!-- Contenedor de dos columnas: Imagen y Definición -->
<div class="two-column-container">
        <div class="column-left">
             <img src="../../images/card.jpg" 
             alt="tarjeta" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover;">
        </div>
        <div class="column-right">
            <div class="definition-box">
                <h3>Digital Squatting:</h3>
                <p>As a form of digital activism or digital disobedience, is the act of claiming online spaces such as domains or usernames to challenge control and digital capitalism. It reclaims virtual ground as an act of resistance, using the architecture of the internet to stage protests.</p>
            </div>
            
 <!-- Equipo -->
<div class="team-note">
                <p><strong>Weak Signal worked in team:</strong> Sila, Ishan, Ludo, Aishwarya, Erandi, Francesco</p>
            </div>
        </div>
    </div>

<!-- Video de YouTube -->
   <div class="video-container">
        <div class="youtube-video">
            <iframe 
                src="https://www.youtube.com/embed/0VJFyfiYXVs" 
                title="Atlas of Weak Signals"
                frameborder="0" 
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                allowfullscreen>
            </iframe>
        </div>
        <p class="video-caption">Atlas of Weak Signals - Digital Squatting</p>
    </div>
</div>

<!-- Nueva imagen cards2.jpg -->
<div class="image-section">
    <img src="../../images/cards2.jpg" 
         alt="Tarjetas adicionales del Atlas" 
         width="100%" 
         style="border-radius: 8px; margin: 3rem 0 4rem 0; object-fit: cover; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
</div>

<!-- Nuevo diagrama Post-Capitalist Care -->
<div class="diagram-section">
    <h2 class="diagram-title">Post-Capitalist Care Framework</h2>
    
<div class="care-diagram">
        <!-- Nodo central -->
        <div class="central-node">
            <div class="node-content">
                <h3>Post-Capitalist Care</h3>
            </div>
        </div>
        
<!-- Rama 1: Tech Abolition -->
<div class="branch branch-1">
            <div class="branch-line"></div>
            <div class="branch-node">
                <div class="node-content">
                    <h4>Tech Abolition</h4>
                    <p>Rethinking technology beyond capitalist paradigms</p>
                </div>
            </div>
            <div class="branch-arrow">
                <div class="arrow-line"></div>
                <div class="arrow-head"></div>
            </div>
            <div class="end-node kit-node">
                <div class="node-content">
                    <span class="kit-badge">Kit</span>
                </div>
            </div>
        </div>
        
 <!-- Rama 2: Border Regimes -->
   <div class="branch branch-2">
            <div class="branch-line"></div>
            <div class="branch-node">
                <div class="node-content">
                    <h4>Border Regimes</h4>
                    <p>Challenging territorial and social boundaries</p>
                </div>
            </div>
            <div class="branch-arrow">
                <div class="arrow-line"></div>
                <div class="arrow-head"></div>
            </div>
            <div class="end-node kit-node">
                <div class="node-content">
                    <span class="kit-badge">Kit</span>
                </div>
            </div>
        </div>
        
<!-- Rama 3: Boredom and Laziness -->
 <div class="branch branch-3">
            <div class="branch-line"></div>
            <div class="branch-node">
                <div class="node-content">
                    <h4>Boredom and Laziness</h4>
                    <p>Reclaiming time and resisting productivity culture</p>
                </div>
            </div>
            <div class="branch-arrow">
                <div class="arrow-line"></div>
                <div class="arrow-head"></div>
            </div>
            <div class="end-node kit-node">
                <div class="node-content">
                    <span class="kit-badge">Kit</span>
                </div>
            </div>
        </div>
    </div>
</div>

<style>
/* Estilos para la página del diagrama de Venn */
.venn-page {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
    font-family: 'Be Vietnam', -apple-system, BlinkMacSystemFont, sans-serif;
}

.venn-title {
    font-size: 2.5rem;
    font-weight: 800;
    color: #2d3748;
    text-align: center;
    margin-bottom: 2rem;
}

/* Contenedor del diagrama de Venn */
.venn-container {
    position: relative;
    height: 500px;
    margin: 3rem 0;
}

/* Diagrama de Venn */
.venn-diagram {
    position: relative;
    width: 100%;
    height: 100%;
    min-height: 400px;
}

/* Estilos para los círculos */
.venn-circle {
    position: absolute;
    border-radius: 50%;
    border: 3px solid;
    opacity: 0.7;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s ease;
}

.venn-circle:hover {
    opacity: 0.9;
    transform: scale(1.02);
}

.circle-1 {
    /* Rural Punk */
    width: 280px;
    height: 280px;
    top: 100px;
    left: 200px;
    background: rgba(25, 118, 210, 0.15);
    border-color: #1976d2;
}

.circle-2 {
    /* Anarch Governance */
    width: 280px;
    height: 280px;
    top: 100px;
    left: 400px;
    background: rgba(156, 39, 176, 0.15);
    border-color: #9c27b0;
}

.circle-3 {
    /* Restorative Justice */
    width: 280px;
    height: 280px;
    top: 250px;
    left: 300px;
    background: rgba(0, 150, 136, 0.15);
    border-color: #009688;
}

.circle-label {
    font-weight: 700;
    font-size: 1.3rem;
    color: #2d3748;
    text-align: center;
    padding: 1rem;
}

/* Random Triggers */
.random-triggers {
    position: absolute;
    top: 50px;
    right: 100px;
}

.trigger {
    padding: 0.8rem 1.5rem;
    border-radius: 25px;
    font-weight: 600;
    margin-bottom: 1rem;
    animation: pulse 2s infinite;
    text-align: center;
    border: 2px dashed;
}

.trigger-1 {
    background: rgba(255, 193, 7, 0.2);
    border-color: #ffc107;
    color: #ff8f00;
}

.trigger-2 {
    background: rgba(121, 85, 72, 0.2);
    border-color: #795548;
    color: #5d4037;
}

@keyframes pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.05); }
    100% { transform: scale(1); }
}

/* Etiquetas de intersección (solo texto) */
.intersection-label {
    position: absolute;
    font-weight: 600;
    font-size: 1rem;
    text-align: center;
    padding: 0.5rem;
    z-index: 10;
}

.int-1-2 {
    /* Rural Anarchy */
    top: 180px;
    left: 320px;
    color: #5e35b1;
}

.int-2-3 {
    /* Just Governance */
    top: 280px;
    left: 410px;
    color: #00897b;
}

.int-1-3 {
    /* Rural Justice */
    top: 320px;
    left: 230px;
    color: #1565c0;
}

.int-center {
    /* Digital Squatting */
    top: 230px;
    left: 320px;
    font-weight: 800;
    font-size: 1.2rem;
    color: #e91e63;
}

/* Contenedor de dos columnas */
.two-column-container {
    display: flex;
    gap: 3rem;
    margin: 4rem 0;
    align-items: flex-start;
}

.column-left {
    flex: 1;
}

.column-right {
    flex: 1;
}

.definition-image {
    width: 100%;
    max-width: 500px;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

/* Definición */
.definition-box {
    background: #f8f9fa;
    border-left: 4px solid #1976d2;
    padding: 2rem;
    margin-bottom: 2rem;
    border-radius: 0 8px 8px 0;
    box-shadow: 0 2px 8px rgba(0,0,0,0.05);
}

.definition-box h3 {
    color: #2d3748;
    margin-top: 0;
    margin-bottom: 1rem;
    font-size: 1.5rem;
}

.definition-box p {
    color: #4a5568;
    line-height: 1.7;
    margin: 0;
    font-size: 1.1rem;
}

/* Equipo */
.team-note {
    background: #f3e5f5;
    border: 1px solid #ce93d8;
    border-radius: 8px;
    padding: 1.2rem 1.5rem;
    color: #7b1fa2;
    box-shadow: 0 2px 6px rgba(0,0,0,0.05);
}

.team-note p {
    margin: 0;
    font-size: 1rem;
}

.team-note strong {
    color: #6a1b9a;
}

/* Video de YouTube */
.video-container {
    margin: 3rem auto;
    max-width: 800px;
}

.youtube-video {
    position: relative;
    padding-bottom: 56.25%; /* Relación 16:9 */
    height: 0;
    overflow: hidden;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.youtube-video iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: none;
}

.video-caption {
    text-align: center;
    color: #666;
    font-style: italic;
    margin-top: 0.8rem;
    font-size: 0.9rem;
}

/* Responsive */
@media (max-width: 992px) {
    .two-column-container {
        flex-direction: column;
        gap: 2rem;
    }
    
    .column-left, .column-right {
        width: 100%;
    }
    
    .definition-image {
        max-width: 100%;
    }
}

@media (max-width: 768px) {
    .venn-container {
        height: 400px;
    }
    
    .venn-circle {
        width: 180px !important;
        height: 180px !important;
    }
    
    .circle-1 {
        top: 50px;
        left: 50px;
    }
    
    .circle-2 {
        top: 50px;
        left: 150px;
    }
    
    .circle-3 {
        top: 150px;
        left: 100px;
    }
    
    .circle-label {
        font-size: 1rem;
    }
    
    .random-triggers {
        position: relative;
        top: auto;
        right: auto;
        display: flex;
        justify-content: center;
        gap: 1rem;
        margin-top: 2rem;
    }
    
    .trigger {
        margin-bottom: 0;
        font-size: 0.9rem;
    }
    
    .intersection-label {
        font-size: 0.85rem;
    }
    
    .int-center {
        top: 120px;
        left: 110px;
    }
    
    .venn-title {
        font-size: 2rem;
    }
    
    .definition-box h3 {
        font-size: 1.3rem;
    }
    
    .definition-box p {
        font-size: 1rem;
    }
}

@media (max-width: 480px) {
    .venn-container {
        height: 350px;
    }
    
    .venn-circle {
        width: 150px !important;
        height: 150px !important;
    }
    
    .circle-label {
        font-size: 0.9rem;
    }
    
    .random-triggers {
        flex-direction: column;
        align-items: center;
    }
}

/* Ocultar el header superior con "Atlas" */
header:first-of-type,
.header:first-of-type,
.atlas-header,
h1:first-of-type {
    display: none !important;
}

</style>

<style>
/* Estilos para la nueva imagen */
.image-section {
    max-width: 1000px;
    margin: 0 auto;
}

/* Estilos para el nuevo diagrama */
.diagram-section {
    margin: 4rem 0;
    padding: 2rem;
    background: linear-gradient(135deg, #f8f9fa 0%, #e8f4f8 100%);
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
}

.diagram-title {
    text-align: center;
    color: #2d3748;
    font-size: 2rem;
    font-weight: 800;
    margin-bottom: 3rem;
    position: relative;
}

.diagram-title::after {
    content: '';
    position: absolute;
    bottom: -10px;
    left: 50%;
    transform: translateX(-50%);
    width: 100px;
    height: 4px;
    background: linear-gradient(90deg, #1976d2, #9c27b0);
    border-radius: 2px;
}

/* Diagrama de Post-Capitalist Care */
.care-diagram {
    position: relative;
    max-width: 1000px;
    margin: 0 auto;
    min-height: 500px;
}

/* Nodo central */
.central-node {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 200px;
    height: 200px;
    background: linear-gradient(135deg, #1976d2, #9c27b0);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 5;
    box-shadow: 0 8px 25px rgba(25, 118, 210, 0.3);
    border: 5px solid white;
    animation: pulse-glow 3s infinite;
}

.central-node h3 {
    color: white;
    text-align: center;
    font-size: 1.5rem;
    font-weight: 700;
    padding: 1rem;
    margin: 0;
}

/* Estilos generales de las ramas */
.branch {
    position: absolute;
    display: flex;
    align-items: center;
}

.branch-line {
    width: 100px;
    height: 4px;
    background: linear-gradient(90deg, #1976d2, #9c27b0);
}

.branch-node {
    background: white;
    padding: 1.2rem;
    border-radius: 10px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    min-width: 180px;
    border-left: 4px solid;
    transition: transform 0.3s ease;
}

.branch-node:hover {
    transform: translateY(-5px);
}

.branch-node h4 {
    margin: 0 0 0.5rem 0;
    font-size: 1.2rem;
    color: #2d3748;
}

.branch-node p {
    margin: 0;
    font-size: 0.9rem;
    color: #666;
    line-height: 1.4;
}

/* Flecha hacia Kit */
.branch-arrow {
    display: flex;
    align-items: center;
    margin: 0 15px;
}

.arrow-line {
    width: 40px;
    height: 2px;
    background: #4a5568;
}

.arrow-head {
    width: 0;
    height: 0;
    border-top: 6px solid transparent;
    border-bottom: 6px solid transparent;
    border-left: 10px solid #4a5568;
}

/* Nodo Kit */
.end-node {
    background: linear-gradient(135deg, #ff9800, #ff5722);
    border-radius: 8px;
    padding: 0.8rem 1.5rem;
    box-shadow: 0 4px 12px rgba(255, 87, 34, 0.3);
}

.kit-badge {
    color: white;
    font-weight: 800;
    font-size: 1.2rem;
    letter-spacing: 1px;
}

/* Posicionamiento específico de las ramas */
.branch-1 {
    /* Tech Abolition - Superior izquierda */
    top: 20%;
    left: 10%;
    flex-direction: row;
}

.branch-1 .branch-node {
    border-left-color: #1976d2;
}

.branch-2 {
    /* Border Regimes - Superior derecha */
    top: 20%;
    right: 10%;
    flex-direction: row-reverse;
}

.branch-2 .branch-node {
    border-left-color: #9c27b0;
}

.branch-3 {
    /* Boredom and Laziness - Inferior central */
    bottom: 15%;
    left: 50%;
    transform: translateX(-50%);
    flex-direction: column;
    align-items: center;
}

.branch-3 .branch-line {
    width: 4px;
    height: 80px;
    margin-bottom: 10px;
    background: linear-gradient(to bottom, #1976d2, #9c27b0);
}

.branch-3 .branch-arrow {
    flex-direction: column;
    margin: 10px 0;
}

.branch-3 .arrow-line {
    width: 2px;
    height: 30px;
}

.branch-3 .arrow-head {
    border-left: 6px solid transparent;
    border-right: 6px solid transparent;
    border-top: 10px solid #4a5568;
    border-left: none;
}

.branch-3 .branch-node {
    border-left-color: #009688;
}

/* Animación para el nodo central */
@keyframes pulse-glow {
    0% {
        box-shadow: 0 8px 25px rgba(25, 118, 210, 0.3);
    }
    50% {
        box-shadow: 0 8px 30px rgba(25, 118, 210, 0.5);
    }
    100% {
        box-shadow: 0 8px 25px rgba(25, 118, 210, 0.3);
    }
}

/* Responsive para el nuevo diagrama */
@media (max-width: 992px) {
    .care-diagram {
        min-height: 700px;
    }
    
    .branch-1 {
        top: 15%;
        left: 5%;
    }
    
    .branch-2 {
        top: 15%;
        right: 5%;
    }
    
    .branch-3 {
        bottom: 10%;
    }
    
    .central-node {
        width: 180px;
        height: 180px;
    }
    
    .central-node h3 {
        font-size: 1.3rem;
    }
}

@media (max-width: 768px) {
    .care-diagram {
        min-height: 850px;
    }
    
    .branch {
        position: relative;
        top: auto !important;
        left: auto !important;
        right: auto !important;
        bottom: auto !important;
        margin: 2rem 0;
        justify-content: center;
        width: 100%;
    }
    
    .branch-1, .branch-2, .branch-3 {
        flex-direction: column !important;
        align-items: center;
        transform: none !important;
    }
    
    .branch-line {
        width: 4px !important;
        height: 50px !important;
        margin-bottom: 10px;
    }
    
    .branch-arrow {
        margin: 10px 0 !important;
        flex-direction: column;
    }
    
    .arrow-line {
        width: 2px !important;
        height: 30px !important;
    }
    
    .arrow-head {
        border-left: 6px solid transparent !important;
        border-right: 6px solid transparent !important;
        border-top: 10px solid #4a5568 !important;
        border-left: none !important;
    }
    
    .central-node {
        position: relative;
        top: auto;
        left: auto;
        transform: none;
        margin: 0 auto 3rem auto;
    }
    
    .diagram-title {
        font-size: 1.8rem;
    }
}

@media (max-width: 480px) {
    .central-node {
        width: 160px;
        height: 160px;
    }
    
    .central-node h3 {
        font-size: 1.1rem;
        padding: 0.8rem;
    }
    
    .branch-node {
        min-width: 150px;
        padding: 1rem;
    }
    
    .branch-node h4 {
        font-size: 1.1rem;
    }
    
    .diagram-title {
        font-size: 1.5rem;
    }
}
</style>
