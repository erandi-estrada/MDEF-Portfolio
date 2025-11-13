<div class="menu-container">
    <div class="custom-header-menu">
        <a href=".">MDEF</a>
        <a href="projects/Portfolio">Projects</a>
        <a href="about/me">About me</a>
    </div>
</div>

<div class="header-container">
    <h1 class="main-title">MDEF Projects</h1>
    <div class="welcome-text">
        <p>Welcome to my journey through the <strong>Master in Design for Emergent Futures (MDEF)</strong>, a program by Fab Lab Barcelona and IAAC. This space documents the ideas, experiments, and reflections that shaped my learning process, from early prototypes to collective explorations.</p>
        <p>Join me as I navigate the projects, collaborations, and discoveries that defined this stage of my path as a designer.</p>
    </div>
</div>

<div class="carousel-container">
    <div class="cards-carousel" id="cardsCarousel">
        <a href="Prosthesis/Prosthesis" class="card">
            <img src="images/prosthesis.jpg" alt="Prosthesis">
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
    
    <div class="carousel-indicators" id="carouselIndicators">
        <!-- Los indicadores se generan con JavaScript -->
    </div>
</div>

<script>
// Carrusel interactivo
const carousel = document.getElementById('cardsCarousel');
const indicatorsContainer = document.getElementById('carouselIndicators');
const cards = document.querySelectorAll('.cards-carousel .card');
let isDragging = false;
let startX;
let scrollLeft;

// Crear indicadores
cards.forEach((_, index) => {
    const indicator = document.createElement('div');
    indicator.className = 'carousel-indicator' + (index === 0 ? ' active' : '');
    indicator.addEventListener('click', () => {
        scrollToCard(index);
    });
    indicatorsContainer.appendChild(indicator);
});

// Scroll suave al hacer clic en indicadores
function scrollToCard(index) {
    const card = cards[index];
    carousel.scrollTo({
        left: card.offsetLeft - carousel.offsetLeft,
        behavior: 'smooth'
    });
}

// Actualizar indicadores activos
carousel.addEventListener('scroll', () => {
    const scrollPosition = carousel.scrollLeft + carousel.offsetWidth / 2;
    const activeIndex = Math.floor(scrollPosition / cards[0].offsetWidth);
    
    document.querySelectorAll('.carousel-indicator').forEach((indicator, index) => {
        indicator.classList.toggle('active', index === activeIndex);
    });
});

// Drag para desplazamiento
carousel.addEventListener('mousedown', (e) => {
    isDragging = true;
    startX = e.pageX - carousel.offsetLeft;
    scrollLeft = carousel.scrollLeft;
    carousel.style.cursor = 'grabbing';
});

carousel.addEventListener('mouseleave', () => {
    isDragging = false;
    carousel.style.cursor = 'grab';
});

carousel.addEventListener('mouseup', () => {
    isDragging = false;
    carousel.style.cursor = 'grab';
});

carousel.addEventListener('mousemove', (e) => {
    if (!isDragging) return;
    e.preventDefault();
    const x = e.pageX - carousel.offsetLeft;
    const walk = (x - startX) * 2;
    carousel.scrollLeft = scrollLeft - walk;
});
</script>