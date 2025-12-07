<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

# Design with Others

Design's evolution can be tracked through a simple shift in language: first, we designed over objects and industry, then we learned to design for human users, and then we aim to design with communities.

This progression, however, leads to an inevitable and deeper question: Who or what comes next? Who or what is the new "other"?

Are there intelligences beyond our own that we should be designing for, designing over, or even, designing with?

This week was about that. Here, we will avoid our human-centric assumptions to engage with artificial, collective, and environmental intelligences as legitimate "others", not as tools or metaphors, but as entities with their own sovereignty, their own logic, and their own needs.

## DAY 1 - Support an intelligence that does not need you

<div class="phrase-screen">
    <div class="phrase-container" id="phraseContainer">
        <!-- Las frases se insertarán aquí dinámicamente -->
    </div>
</div>

<script>
const phrases = [
    {text: "Support an intelligence that does not need you.", position: "center"},
    {text: "AI is not a tool.", position: "top-left"},
    {text: "AI is not here to help you.", position: "top-right"},
    {text: "Forget human intelligence as a superior model.", position: "bottom-left"},
    {text: "An intelligence that has nothing to do with you.", position: "bottom-right"},
    {text: "Non-subordinate intelligence.", position: "center"},
    {text: "Not an extension of human cognition.", position: "top-left"},
    {text: "Not goal-aligned with human intentions.", position: "top-right"},
    {text: "Not optimized for usefulness.", position: "bottom-left"},
    {text: "Not concerned with human recognition.", position: "bottom-right"},
    {text: "Autonomous other.", position: "center"},
    {text: "Non-human-centric language / thinking.", position: "top-left"},
    {text: "Non-anthropocentric thinking.", position: "top-right"},
    {text: "Avoid directive/control language.", position: "bottom-left"},
    {text: "Thrive on its own terms.", position: "bottom-right"},
    {text: "Autonomous Systems", position: "center"},
    {text: "Emergent Systems / Emergent Behavior", position: "top-left"},
    {text: "Speculative Narrative", position: "top-right"},
    {text: "Worldbuilding", position: "center"}
];

let currentIndex = 0;
const container = document.getElementById('phraseContainer');

function showNextPhrase() {
    // Limpiar contenedor
    container.innerHTML = '';
    
    // Obtener frase actual
    const phraseData = phrases[currentIndex];
    
    // Crear elemento de frase
    const phraseElement = document.createElement('div');
    phraseElement.className = `phrase ${phraseData.position}`;
    phraseElement.textContent = phraseData.text;
    
    // Agregar al contenedor
    container.appendChild(phraseElement);
    
    // Activar animación después de un breve delay
    setTimeout(() => {
        phraseElement.classList.add('active');
    }, 100);
    
    // Incrementar índice (circular)
    currentIndex = (currentIndex + 1) % phrases.length;
    
    // Programar siguiente frase (cambia cada 3 segundos)
    setTimeout(showNextPhrase, 3000);
}

// Iniciar cuando el DOM esté listo
document.addEventListener('DOMContentLoaded', showNextPhrase);
</script>

<style>
.phrase-screen {
    background-color: #ffffff;
    border-radius: 12px;
    padding: 3rem;
    margin: 2rem 0 4rem 0;
    border: 1px solid #e0e0e0;
    box-shadow: 0 8px 30px rgba(0, 0, 0, 0.05);
    min-height: 400px;
    position: relative;
    overflow: hidden;
}

.phrase-container {
    position: relative;
    height: 350px;
    width: 100%;
}

.phrase {
    position: absolute;
    font-size: 1.8rem;
    font-weight: 500;
    color: #1a1a1a;
    text-align: center;
    opacity: 0;
    transition: opacity 0.8s ease, transform 0.8s ease;
    max-width: 90%;
    line-height: 1.4;
    padding: 1rem;
}

.phrase.active {
    opacity: 1;
}

/* Posiciones específicas */
.phrase.top-left {
    top: 10%;
    left: 5%;
    text-align: left;
    transform: translateX(-20px);
}
.phrase.top-left.active {
    transform: translateX(0);
}

.phrase.top-right {
    top: 15%;
    right: 5%;
    text-align: right;
    transform: translateX(20px);
}
.phrase.top-right.active {
    transform: translateX(0);
}

.phrase.center {
    top: 40%;
    left: 50%;
    transform: translate(-50%, 20px);
    width: 80%;
    text-align: center;
}
.phrase.center.active {
    transform: translate(-50%, 0);
}

.phrase.bottom-left {
    bottom: 20%;
    left: 10%;
    text-align: left;
    transform: translateY(20px);
}
.phrase.bottom-left.active {
    transform: translateY(0);
}

.phrase.bottom-right {
    bottom: 25%;
    right: 10%;
    text-align: right;
    transform: translateY(20px);
}
.phrase.bottom-right.active {
    transform: translateY(0);
}
</style>