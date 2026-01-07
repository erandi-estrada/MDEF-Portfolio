<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

## Short Proposal

This pictorial proposes an open visual exploration of multispecies justice, without fixing a single subject, scale, or outcome. Rather than presenting conclusions, it assembles images, textures, overlays, and partial texts to speculate on how non-human lives intersect with urban environments and human-centered systems. Inspired by visual essays the work treats images as the main thinking tool, layering, obscuring, and contrasting elements to surface relationships that are usually overlooked. The format remains fluid and modular, functioning as a provisional map of questions, observations, and possible directions, allowing the project to evolve as new species, sites, and perspectives emerge.

## Draft Pictorial

The current pictorial draft takes the form of a series of images arranged within a minimal and flexible layout, where visual material leads the narrative. Yellow and blue are used as provisional colors to differentiate images, textures, and visual layers, rather than as a fixed palette. At this stage, color operates as a placeholder for different material qualities, atmospheres, or sensory conditions, and is expected to shift as the project develops.

<div class="slides-section">
    <div class="slider">
        <div class="slide">
            <img src="../../images/pictorial1.jpg" alt="Pictorial 1">
        </div>
        <div class="slide">
            <img src="../../images/pictorial3.jpg" alt="Pictorial 3">
        </div>
        <div class="slide">
            <img src="../../images/pictorial4.jpg" alt="Pictorial 4">
        </div>
        <div class="slide">
            <img src="../../images/pictorial5.jpg" alt="Pictorial 5">
        </div>
        <div class="slide">
            <img src="../../images/pictorial6.jpg" alt="Pictorial 6">
        </div>
        <div class="slide">
            <img src="../../images/pictorial8.jpg" alt="Pictorial 8">
        </div>
        <div class="slide">
            <img src="../../images/pictorial9.jpg" alt="Pictorial 9">
        </div>
    </div>
    
    <button class="slider-btn prev-btn">‹</button>
    <button class="slider-btn next-btn">›</button>
</div>

<div class="dots-container"></div>

White space is intentionally present, creating pauses between images and text, and allowing each element to be read independently while still contributing to an overall flow. The emphasis remains on images as carriers of meaning, with text acting as a subtle guide rather than an explanation. This draft functions as an exploratory structure, testing rhythm, contrast, and visual hierarchy, rather than a finalized composition.

<style>
/* Slides section - EXACTAMENTE igual que en tu código de referencia */
.slides-section {
    position: relative;
    max-width: 100%;
    margin: 2rem 0;
    border-radius: 8px;
    overflow: hidden;
    padding: 2rem;
}

.slider {
    display: block;
}

.slide {
    display: none;
}

.slide.active-slide {
    display: block;
}

.slide img {
    width: 100%;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

/* Botones - EXACTAMENTE igual que en tu código */
.slider-btn {
    cursor: pointer;
    position: absolute;
    top: 50%;
    padding: 20px;
    color: #333;
    font-weight: bold;
    font-size: 24px;
    transform: translateY(-50%);
    user-select: none;
    background: rgba(255,255,255,0.8);
    border: none;
    border-radius: 5px;
    transition: background-color 0.3s ease;
}

.slider-btn:hover {
    background-color: rgba(255,255,255,1) !important;
}

.prev-btn {
    left: 0;
    border-radius: 0 5px 5px 0;
}

.next-btn {
    right: 0;
    border-radius: 5px 0 0 5px;
}

/* Dots - EXACTAMENTE igual que en tu código */
.dots-container {
    text-align: center;
    padding: 20px;
}

.slide-dot {
    cursor: pointer;
    height: 12px;
    width: 12px;
    margin: 0 6px;
    background-color: #bbb;
    border-radius: 50%;
    display: inline-block;
    transition: background-color 0.3s ease;
}

.slide-dot.active-dot, .slide-dot:hover {
    background-color: #333;
}
</style>

<script>
// JavaScript EXACTAMENTE igual que en tu código de referencia
let slideIndex = 1;
showSlides(slideIndex);

function plusSlides(n) {
    showSlides(slideIndex += n);
}

function currentSlide(n) {
    showSlides(slideIndex = n);
}

function showSlides(n) {
    let slides = document.getElementsByClassName("slide");
    let dots = document.getElementsByClassName("slide-dot");
    
    if (n > slides.length) { slideIndex = 1; }
    if (n < 1) { slideIndex = slides.length; }
    
    // Ocultar todos los slides
    for (let i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";
    }
    
    // Quitar clase active de todos los dots
    for (let i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(" active-dot", "");
    }
    
    // Mostrar slide actual y activar su dot
    if (slides[slideIndex-1]) {
        slides[slideIndex-1].style.display = "block";
    }
    if (dots[slideIndex-1]) {
        dots[slideIndex-1].className += " active-dot";
    }
}

// Auto-advance cada 8 segundos - EXACTAMENTE igual
setInterval(() => {
    plusSlides(1);
}, 8000);

// Cuando cargue la página, crear los dots
document.addEventListener('DOMContentLoaded', function() {
    const slides = document.querySelectorAll('.slide');
    const dotsContainer = document.querySelector('.dots-container');
    
    // Limpiar primero
    dotsContainer.innerHTML = '';
    
    // Crear un dot por cada slide
    slides.forEach((slide, index) => {
        const dot = document.createElement('span');
        dot.className = 'slide-dot';
        if (index === 0) dot.className += ' active-dot';
        dot.onclick = function() { currentSlide(index + 1); };
        dotsContainer.appendChild(dot);
    });
    
    // Mostrar el primer slide
    showSlides(slideIndex);
    
    // Añadir eventos a los botones
    document.querySelector('.prev-btn').addEventListener('click', function() {
        plusSlides(-1);
    });
    
    document.querySelector('.next-btn').addEventListener('click', function() {
        plusSlides(1);
    });
});
</script>