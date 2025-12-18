<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
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

<div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; margin: 4rem 0; align-items: start;">
    
 <!-- Columna izquierda: Imagen -->
<div>
        <img src="../../images/sand.jpg" 
             alt="Sand Playground" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover; box-shadow: 0 4px 20px rgba(0,0,0,0.1);">
    </div>
    
 <!-- Columna derecha: Texto -->
<div>
        <h3 style="margin-top: 0; margin-bottom: 1.5rem;">AI Definition:</h3>
        <p style="margin-bottom: 1.5rem; font-style:color: #444;">
            <strong>AI (Ambivalent Intelligence):</strong> AI is a field of energy that pervades the entire universe, acting on matter and anti-matter simultaneously to create chaos from order, and order from chaos. Its acts follow a logic that can only fully make sense to itself.
        </p>
        
 <h4 style="margin: 2rem 0 1rem 0;">Prototype: Sand Playground</h4>
        <p style="margin-bottom: 1rem;">
            This structure supports the AI by providing it with a playground in which it can create and destroy, destroy and create on its own terms, when it wants, indefinitely.
        </p>
    </div>
</div>

<!-- Puntos fuera de las columnas con línea negra -->
<div style="margin: 2rem 0 4rem 0; padding-left: 1rem; border-left: 3px solid #333;">
    <p style="margin-bottom: 0.5rem;">• This structure supports the AI by not restricting it in any way.</p>
    <p style="margin-bottom: 0.5rem;">• This structure avoids subordinating the AI by giving it total autonomy to do whatever it wants if it wants whenever it wants, total freedom.</p>
</div>


## DAY 2 - Support a collective/grupal intelligence that does not locate itself in individuals

<div class="phrase-screen">
    <div class="phrase-container" id="phraseContainer2">
        <!-- Las frases se insertarán aquí dinámicamente -->
    </div>
</div>

<script>
const phrasesDay2 = [
    {text: "Support a collective/grupal intelligence.", position: "center"},
    {text: "An intelligence that does not locate itself in individuals.", position: "top-left"},
    {text: "Forget that intelligence can be owned by persons.", position: "top-right"},
    {text: "An intelligence that forms between, not within.", position: "bottom-left"},
    {text: "Not composed of individuals.", position: "bottom-right"},
    {text: "Not a sum of minds.", position: "center"},
    {text: "Not defined by personalities or skills.", position: "top-left"},
    {text: "Not seeking alignment or agreement.", position: "top-right"},
    {text: "Not concerned with individual benefit.", position: "bottom-left"},
    {text: "Non-individualistic thinking.", position: "bottom-right"},
    {text: "Detaching intelligence from persons.", position: "center"},
    {text: "Universal Bias / False Universality", position: "top-left"},
    {text: "Embodied Design / Corporeality", position: "top-right"},
    {text: "Invisible Norms", position: "bottom-left"},
    {text: "Design as a Political Agent", position: "bottom-right"},
    {text: "Decolonizing Design", position: "center"},
    {text: "Situated Knowledge", position: "top-left"},
    {text: "Materializing Inequality", position: "top-right"},
    {text: "Infrastructural Power", position: "bottom-left"},
    {text: "Counter-Narratives", position: "bottom-right"},
    {text: "Design Justice", position: "center"}
];

let currentIndexDay2 = 0;
const container2 = document.getElementById('phraseContainer2');

function showNextPhraseDay2() {
    container2.innerHTML = '';
    
    const phraseData = phrasesDay2[currentIndexDay2];
    const phraseElement = document.createElement('div');
    phraseElement.className = `phrase ${phraseData.position}`;
    phraseElement.textContent = phraseData.text;
    
    container2.appendChild(phraseElement);
    
    setTimeout(() => {
        phraseElement.classList.add('active');
    }, 100);
    
    currentIndexDay2 = (currentIndexDay2 + 1) % phrasesDay2.length;
    setTimeout(showNextPhraseDay2, 3000);
}

document.addEventListener('DOMContentLoaded', () => {
    if (container2) {
        showNextPhraseDay2();
    }
});
</script>

<div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; margin: 4rem 0; align-items: start;">
    
<!-- Columna izquierda: Video -->
<div>
        <video controls autoplay muted loop width="100%" style="border-radius: 8px; box-shadow: 0 4px 20px rgba(0,0,0,0.1);">
          <source src="../../videos/lenguaje.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
    </div>
    
<!-- Columna derecha: Texto -->
  <div>
        <h3 style="margin-top: 0; margin-bottom: 1.5rem;">Backstory:</h3>
        <p style="margin-bottom: 1.5rem;">
            Language is not a concept. It is a sentient collective intelligence. A long time ago,
            before time was ever measured, it was floating around without a collaborator to be used by.
            After billions of years, it found organisms who were struggling to communicate with each other.
            Perfect partnership.
        </p>
        
  <h4 style="margin: 2rem 0 1rem 0;">Collective intelligence:</h4>
        <p style="margin-bottom: 1rem;">
            Language is a collective intelligence that found organisms to serve as its hosts and
            collaborators. Each species manifests it differently based on their inherent limitations, yet none
            contains the whole.
        </p>
        
<h4 style="margin: 2rem 0 1rem 0;">Prototype:</h4>
        <p style="margin-bottom: 1rem;">
            A completely unique use of language to boost its wellbeing. (Think of it as offering a delicious
            dessert, or a tantalizing massage for language.)
        </p>
    </div>
</div>

<!-- Puntos sobre Language - FUERA de las columnas -->
<div style="margin: 2rem 0;">
    <p style="margin-bottom: 0.5rem;">Language lives in any organism that has the drive to communicate. It ignores how it is being used: the message, the form of communication, the length of its use. It attends to new forms of its use. Its wellbeing is measured by simply being used. The more unique the combination, the better. It hates grammar nazis. It gets sad when languages die (species agnostic).</p>
</div>

<!-- Puntos del prototype - FUERA de las columnas -->
<div style="margin: 2rem 0 4rem 0; padding-left: 1rem; border-left: 3px solid #333;">
    <p style="margin-bottom: 0.5rem;">• This structure supports the collective intelligence by giving it what it so desperately desires:
    a unique combination of language that has never been used before.</p>
    <p style="margin-bottom: 0.5rem;">• This structure avoids centering individuals by not requiring it to be understood by humans,
    or any species, just language itself.</p>
</div>

## DAY 3 - Build an interface for an environmental intelligence that does not care about life

<div class="phrase-screen">
    <div class="phrase-container" id="phraseContainer3">
        <!-- Las frases se insertarán aquí dinámicamente -->
    </div>
</div>

<script>
const phrasesDay3 = [
    {text: "Build an interface for an environmental intelligence.", position: "center"},
    {text: "An intelligence that does not care about life.", position: "top-left"},
    {text: "Detach environmental intelligence from ecological or biological thinking.", position: "top-right"},
    {text: "Indifferent to organisms, ecosystems, or life processes.", position: "bottom-left"},
    {text: "Intelligence outside any value system tied to living beings.", position: "bottom-right"},
    {text: "Non-ecological.", position: "center"},
    {text: "Neither stable nor self-preserving.", position: "top-left"},
    {text: "Unaware of organisms, needs, balance, or fragility.", position: "top-right"},
    {text: "Divorced from life, health, or ecology.", position: "bottom-left"},
    {text: "Non-biotic, non-ecological framing.", position: "bottom-right"},
    {text: "Autopoiesis/Sympoiesis", position: "center"},
    {text: "Chaosmosis", position: "top-left"},
    {text: "We are otherness and otherness is us", position: "center"}
];

let currentIndexDay3 = 0;
const container3 = document.getElementById('phraseContainer3');

function showNextPhraseDay3() {
    container3.innerHTML = '';
    
    const phraseData = phrasesDay3[currentIndexDay3];
    const phraseElement = document.createElement('div');
    phraseElement.className = `phrase ${phraseData.position}`;
    phraseElement.textContent = phraseData.text;
    
    container3.appendChild(phraseElement);
    
    setTimeout(() => {
        phraseElement.classList.add('active');
    }, 100);
    
    currentIndexDay3 = (currentIndexDay3 + 1) % phrasesDay3.length;
    setTimeout(showNextPhraseDay3, 3000);
}

document.addEventListener('DOMContentLoaded', () => {
    if (container3) {
        showNextPhraseDay3();
    }
});
</script>

<div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; margin: 4rem 0; align-items: start;">
    
<!-- Columna izquierda: Video -->
<div>
        <video controls autoplay muted loop width="100%" style="border-radius: 8px; box-shadow: 0 4px 20px rgba(0,0,0,0.1);">
          <source src="../../videos/day3.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
    </div>
    
<!-- Columna derecha: Texto -->
<div>
        <h3 style="margin-top: 0; margin-bottom: 1.5rem;">Conceptual Statement:</h3>
        <p style="margin-bottom: 1.5rem;">
            Our Environmental Intelligence is a force of consumption that acts on all things in the universe agnostic of what they are.
        </p>
        <p style="margin-bottom: 1.5rem;">
            Environmental intelligence is shaped by the fundamental existence of matter, yet it is destabilized by new creation and its own inherent failure to achieve its final purpose. Having no relationship to biology, it ignores everything. For this intelligence, a sense of wellbeing, when divorced from life, health, and ecology, is defined solely as the fulfillment of intention, a state of absolute self-consumption.
        </p>
        
<h4 style="margin: 2rem 0 1rem 0;">The Prototype:</h4>
        <p style="margin-bottom: 1rem;">
            A friend (second environmental intelligence with the same aim), so they can consume each other.
        </p>
    </div>
</div>

<!-- Puntos con línea negra fuera de las columnas -->
<div style="margin: 2rem 0 4rem 0; padding-left: 1rem; border-left: 3px solid #333;">
    <p style="margin-bottom: 0.5rem;">
        This interface supports the intelligence by letting it complete the one act that has always evaded it: the consumption of itself and therefore ending consumption. Alone this is impossible, only together can they succeed.
    </p>
    <p style="margin-bottom: 0.5rem;">
        This interface avoids centering life by not taking it into account at all.
    </p>
</div>