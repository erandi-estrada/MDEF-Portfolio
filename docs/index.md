<div class="menu-container">
    <div class="custom-header-menu">
        <a href=".">MDEF</a>
        <a href="projects/Portfolio">Projects</a>
        <a href="about/me">About me</a>
    </div>
</div>

<div class="content-wrapper">
    <div class="header-container">
        <h1 class="main-title">MDEF Projects</h1>
        <div class="welcome-text">
           <p>Welcome to my journey through the <a href="https://mdef.fablabbcn.org/" target="_blank" style="font-weight: bold; color: #1976d2; text-decoration: none;">Master in Design for Emergent Futures (MDEF)</a>, a program by Fab Lab Barcelona and IAAC. This space documents the ideas, experiments, and reflections that shaped my learning process, from early prototypes to collective explorations.</p>
            <p>Join me as I navigate the projects, collaborations, and discoveries that defined this stage of my path as a designer.</p>
        </div>
    </div>
</div>

<div class="content-wrapper">
    <div class="carousel-container">
        <div class="cards-carousel" id="cardsCarousel">
            <a href="Prosthesis/Prosthesis" class="card">
                <img src="images/prosthesis.jpeg" alt="Prosthesis">
                <h3>Prosthesis</h3>
                <p>A research on extensions that question what it means to be human in a hybrid world.</p>
            </a>

 <a href="project/project/" class="card">
                <img src="images/initial-ideas.jpg" alt="Initial Ideas">
                <h3>Initial Ideas</h3>
                <p>Early explorations that became the foundation of future projects.</p>
            </a>

  <a href="term1/01-Bootcamp/" class="card">
                <img src="images/bootcamp.jpg" alt="Bootcamp"> 
                <h3>Bootcamp</h3> 
                <p>Hands-on learning, rapid prototyping, and collaboration.</p> 
            </a> 

  <a href="term1/02-Atlas/" class="card">
                <img src="images/atlas.jpg" alt="Atlas of Weak Signals">
                <h3>Atlas of Weak Signals</h3>
                <p>Researching emerging signals and future-oriented thinking.</p>
            </a>

  <a href="digi/digi/" class="card">
                <img src="images/digi.jpg" alt="Digi">
                <h3>Digi</h3>
                <p>Digital tools and interactive systems.</p>
            </a>

  <a href="studio/studio/" class="card">
                <img src="images/studio.jpg" alt="Studio">
                <h3>Studio</h3>
                <p>Design, experimentation, and material explorations.</p>
            </a>
        </div>
    </div>
</div>

<script>
// Carrusel automático continuo
const carousel = document.getElementById('cardsCarousel');
const cards = document.querySelectorAll('.cards-carousel .card');
const cardWidth = 380; // Mismo ancho que en CSS

// Duplicar las tarjetas para efecto infinito
cards.forEach(card => {
    const clone = card.cloneNode(true);
    carousel.appendChild(clone);
});

let autoScrollInterval;
let currentScroll = 0;
const scrollSpeed = 1; // Velocidad de desplazamiento (píxeles por frame)

function startAutoScroll() {
    autoScrollInterval = setInterval(() => {
        currentScroll += scrollSpeed;
        carousel.scrollLeft = currentScroll;
        
        // Reiniciar scroll cuando llegue al final (efecto infinito)
        if (currentScroll >= carousel.scrollWidth / 2) {
            currentScroll = 0;
            carousel.scrollLeft = 0;
        }
    }, 16); // ~60fps
}

function stopAutoScroll() {
    clearInterval(autoScrollInterval);
}

// Iniciar automáticamente al cargar la página
document.addEventListener('DOMContentLoaded', function() {
    startAutoScroll();
});

// Pausar al hacer hover sobre el carrusel
carousel.addEventListener('mouseenter', stopAutoScroll);
carousel.addEventListener('mouseleave', startAutoScroll);

// También pausar al hacer hover sobre una tarjeta específica
document.querySelectorAll('.cards-carousel .card').forEach(card => {
    card.addEventListener('mouseenter', stopAutoScroll);
    card.addEventListener('mouseleave', startAutoScroll);
});
</script>