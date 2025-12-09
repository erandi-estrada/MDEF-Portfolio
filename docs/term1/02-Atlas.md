<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<div class="venn-page">
    <h1 class="venn-title">Atlas of Weak Signals</h1>
    
    <div class="intro-text">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
    </div>

    <!-- Diagrama de Venn -->
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
            
            <!-- Intersecciones -->
            <div class="intersection int-1-2">Rural Anarchy</div>
            <div class="intersection int-2-3">Just Governance</div>
            <div class="intersection int-1-3">Rural Justice</div>
            <div class="intersection int-1-2-3">Digital Squatting</div>
        </div>
    </div>

    <!-- Definición de Digital Squatting -->
    <div class="definition-box">
        <h3>Digital Squatting:</h3>
        <p>As a form of digital activism or digital disobedience, is the act of claiming online spaces such as domains or usernames to challenge control and digital capitalism. It reclaims virtual ground as an act of resistance, using the architecture of the internet to stage protests.</p>
    </div>

    <!-- Equipo -->
    <div class="team-note">
        <p><strong>Weak Signal worked in team:</strong> Sila, Ishan, Ludo, Aishwarya, Erandi, Francesco</p>
    </div>

    <!-- Video -->
    <div class="video-container">
        <video controls class="atlas-video">
            <source src="atlas.mp4" type="video/mp4">
            Tu navegador no soporta el elemento de video.
        </video>
        <p class="video-caption">Atlas of Weak Signals - Team Project</p>
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
    margin-bottom: 1.5rem;
}

.intro-text {
    font-size: 1.1rem;
    line-height: 1.6;
    color: #4a5568;
    max-width: 800px;
    margin: 0 auto 3rem auto;
    text-align: justify;
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
    background: rgba(25, 118, 210, 0.2);
    border-color: #1976d2;
}

.circle-2 {
    /* Anarch Governance */
    width: 280px;
    height: 280px;
    top: 100px;
    left: 400px;
    background: rgba(156, 39, 176, 0.2);
    border-color: #9c27b0;
}

.circle-3 {
    /* Restorative Justice */
    width: 280px;
    height: 280px;
    top: 250px;
    left: 300px;
    background: rgba(0, 150, 136, 0.2);
    border-color: #009688;
}

.circle-label {
    font-weight: 700;
    font-size: 1.2rem;
    color: #2d3748;
    text-align: center;
    padding: 0.5rem;
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

/* Intersecciones */
.intersection {
    position: absolute;
    font-weight: 600;
    font-size: 0.9rem;
    text-align: center;
    padding: 0.5rem;
    border-radius: 5px;
    background: rgba(255, 255, 255, 0.9);
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.int-1-2 {
    /* Rural Anarchy */
    top: 180px;
    left: 320px;
    color: #6a1b9a;
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

.int-1-2-3 {
    /* Digital Squatting */
    top: 230px;
    left: 320px;
    font-weight: 700;
    font-size: 1rem;
    background: rgba(233, 30, 99, 0.9);
    color: white;
    padding: 0.8rem 1rem;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(233, 30, 99, 0.3);
}

/* Definición */
.definition-box {
    background: #f5f5f5;
    border-left: 4px solid #1976d2;
    padding: 1.5rem;
    margin: 2rem 0;
    border-radius: 0 8px 8px 0;
}

.definition-box h3 {
    color: #2d3748;
    margin-top: 0;
    margin-bottom: 1rem;
}

.definition-box p {
    color: #4a5568;
    line-height: 1.6;
    margin: 0;
}

/* Equipo */
.team-note {
    background: #e8f5e9;
    border: 1px solid #c8e6c9;
    border-radius: 8px;
    padding: 1rem 1.5rem;
    margin: 2rem 0;
    color: #2e7d32;
}

/* Video */
.video-container {
    margin: 3rem auto;
    max-width: 800px;
}

.atlas-video {
    width: 100%;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.video-caption {
    text-align: center;
    color: #666;
    font-style: italic;
    margin-top: 0.5rem;
}

/* Responsive */
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
        font-size: 0.9rem;
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
    
    .intersection {
        font-size: 0.8rem;
        padding: 0.3rem;
    }
    
    .int-1-2-3 {
        top: 120px;
        left: 110px;
    }
}
</style>