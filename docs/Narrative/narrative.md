<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<h2>Short Proposal</h2>
<p>This pictorial proposes an open visual exploration of multispecies justice, without fixing a single subject, scale, or outcome. Rather than presenting conclusions, it assembles images, textures, overlays, and partial texts to speculate on how non-human lives intersect with urban environments and human-centered systems. Inspired by visual essays the work treats images as the main thinking tool, layering, obscuring, and contrasting elements to surface relationships that are usually overlooked. The format remains fluid and modular, functioning as a provisional map of questions, observations, and possible directions, allowing the project to evolve as new species, sites, and perspectives emerge.</p>

<h2>Draft Pictorial</h2>
<p>The current pictorial draft takes the form of a series of images arranged within a minimal and flexible layout, where visual material leads the narrative. Yellow and blue are used as provisional colors to differentiate images, textures, and visual layers, rather than as a fixed palette. At this stage, color operates as a placeholder for different material qualities, atmospheres, or sensory conditions, and is expected to shift as the project develops.</p>

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

<p>White space is intentionally present, creating pauses between images and text, and allowing each element to be read independently while still contributing to an overall flow. The emphasis remains on images as carriers of meaning, with text acting as a subtle guide rather than an explanation. This draft functions as an exploratory structure, testing rhythm, contrast, and visual hierarchy, rather than a finalized composition.</p>

<style>
.menu-container {
    margin-bottom: 3rem;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid #eaeaea;
}

.custom-header-menu {
    display: flex;
    gap: 2.5rem;
    font-size: 0.95rem;
    font-weight: 500;
}

.custom-header-menu a {
    color: #555;
    text-decoration: none;
    letter-spacing: 0.3px;
    transition: color 0.2s ease;
    padding: 0.5rem 0;
}

.custom-header-menu a:hover {
    color: #1976d2;
}

.custom-header-menu a:first-child {
    color: #333;
    font-weight: 600;
}

h2 {
    font-weight: 400;
    font-size: 1.8rem;
    margin-bottom: 1.8rem;
    color: #444;
    padding-bottom: 0.5rem;
    border-bottom: 1px solid #f0f0f0;
}

p {
    font-weight: 350;
    font-size: 1.15rem;
    margin-bottom: 3rem;
    max-width: 900px;
    color: #555;
    line-height: 1.7;
}

.slides-section {
    margin: 4rem 0;
    height: 600px;
    position: relative;
    overflow: hidden;
}

.slider {
    display: flex;
    height: 100%;
    transition: transform 0.5s ease;
}

.slide {
    min-width: 100%;
    height: 100%;
}

.slide img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
}

.slider-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(255, 255, 255, 0.7);
    border: none;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 1.2rem;
    color: #333;
    transition: background 0.2s;
}

.slider-btn:hover {
    background: rgba(255, 255, 255, 0.9);
}

.prev-btn {
    left: 20px;
}

.next-btn {
    right: 20px;
}

.dots-container {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin: 1.5rem 0 3rem 0;
}

.dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #ddd;
    cursor: pointer;
}

.dot.active {
    background: #777;
}

@media (max-width: 768px) {
    .slides-section {
        height: 400px;
    }
    
    .slider-btn {
        width: 40px;
        height: 40px;
    }
    
    .custom-header-menu {
        gap: 1.5rem;
        font-size: 0.9rem;
    }
}

@media (max-width: 480px) {
    .slides-section {
        height: 300px;
    }
    
    .slider-btn {
        width: 35px;
        height: 35px;
        font-size: 1rem;
    }
    
    .prev-btn {
        left: 10px;
    }
    
    .next-btn {
        right: 10px;
    }
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const slider = document.querySelector('.slider');
    const slides = document.querySelectorAll('.slide');
    const prevBtn = document.querySelector('.prev-btn');
    const nextBtn = document.querySelector('.next-btn');
    const dotsContainer = document.querySelector('.dots-container');
    
    let currentSlide = 0;
    const totalSlides = slides.length;
    
    for (let i = 0; i < totalSlides; i++) {
        const dot = document.createElement('div');
        dot.classList.add('dot');
        if (i === 0) dot.classList.add('active');
        dot.addEventListener('click', () => goToSlide(i));
        dotsContainer.appendChild(dot);
    }
    
    const dots = document.querySelectorAll('.dot');
    
    function goToSlide(n) {
        currentSlide = (n + totalSlides) % totalSlides;
        slider.style.transform = `translateX(-${currentSlide * 100}%)`;
        updateDots();
    }
    
    function updateDots() {
        dots.forEach((dot, index) => {
            dot.classList.toggle('active', index === currentSlide);
        });
    }
    
    function nextSlide() {
        goToSlide(currentSlide + 1);
    }
    
    function prevSlide() {
        goToSlide(currentSlide - 1);
    }
    
    nextBtn.addEventListener('click', nextSlide);
    prevBtn.addEventListener('click', prevSlide);
    
    let slideInterval = setInterval(nextSlide, 4000);
    
    const slidesSection = document.querySelector('.slides-section');
    slidesSection.addEventListener('mouseenter', () => clearInterval(slideInterval));
    slidesSection.addEventListener('mouseleave', () => {
        slideInterval = setInterval(nextSlide, 4000);
    });
    
    goToSlide(0);
});
</script>