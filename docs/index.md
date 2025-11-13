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
    <!-- Zonas de desplazamiento automático -->
    <div class="carousel-scroll-zone left" id="scrollLeft"></div>
    <div class="carousel-scroll-zone right" id="scrollRight"></div>
    
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
</div>

<script>
// Carrusel con desplazamiento automático al acercar el cursor
const carousel = document.getElementById('cardsCarousel');
const scrollLeftZone = document.getElementById('scrollLeft');
const scrollRightZone = document.getElementById('scrollRight');
const cards = document.querySelectorAll('.cards-carousel .card');
const cardWidth = cards[0].offsetWidth;
let scrollInterval;

function scrollToNext() {
    const currentScroll = carousel.scrollLeft;
    const maxScroll = carousel.scrollWidth - carousel.clientWidth;
    
    if (currentScroll < maxScroll) {
        carousel.scrollTo({
            left: currentScroll + cardWidth,
            behavior: 'smooth'
        });
    }
}

function scrollToPrev() {
    const currentScroll = carousel.scrollLeft;
    
    if (currentScroll > 0) {
        carousel.scrollTo({
            left: currentScroll - cardWidth,
            behavior: 'smooth'
        });
    }
}

// Desplazamiento automático cuando el cursor está en las zonas
scrollRightZone.addEventListener('mouseenter', () => {
    scrollInterval = setInterval(scrollToNext, 1000); // Se mueve cada segundo
});

scrollLeftZone.addEventListener('mouseenter', () => {
    scrollInterval = setInterval(scrollToPrev, 1000);
});

// Detener el desplazamiento cuando el cursor sale
scrollRightZone.addEventListener('mouseleave', () => {
    clearInterval(scrollInterval);
});

scrollLeftZone.addEventListener('mouseleave', () => {
    clearInterval(scrollInterval);
});

// También desplazamiento con clic en las zonas (por si acaso)
scrollRightZone.addEventListener('click', scrollToNext);
scrollLeftZone.addEventListener('click', scrollToPrev);
</script>