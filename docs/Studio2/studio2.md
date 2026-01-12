<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

## 5 Errors

A reflection on the mistakes and learnings from the design process.

<div class="slides-section">
    <div class="slider">
        <!-- Error 1 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">01</div>
                <h3 class="slide-title">Staying Too Long in Ideation</h3>
                <p class="slide-text">I spent too much time in the ideation phase, circling around the same core idea without moving into prototyping or testing.</p>
            </div>
        </div>
        
        <!-- Error 2 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">02</div>
                <h3 class="slide-title">Confusing Awareness with Impact</h3>
                <p class="slide-text">At first, I focused primarily on raising awareness, assuming that making issues visible would be enough to generate change. I later realized that awareness without a path to action risks becoming passive and purely aesthetic.</p>
            </div>
        </div>
        
        <!-- Error 3 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">03</div>
                <h3 class="slide-title">Avoiding Positioning</h3>
                <p class="slide-text">I hesitated to take a strong stance, trying to keep the project open for as long as possible.</p>
            </div>
        </div>
        
        <!-- Error 4 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">04</div>
                <h3 class="slide-title">Trying to Overachieve Across Too Many Scales</h3>
                <p class="slide-text">I attempted to address multiple scales and concerns simultaneously, which prevented me from choosing a clear entry point.</p>
            </div>
        </div>
        
        <!-- Error 5 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">05</div>
                <h3 class="slide-title">Starting from Tools Instead of the Question</h3>
                <p class="slide-text">I initially began the project driven by a desire to work with technology and biomaterials, rather than by a clearly defined research question. When I became aware of this bias, I tried to overcompensate by exploring alternative directions, but ended up overthinking and returning to the same idea.</p>
            </div>
        </div>
    </div>
    
    <button class="slider-btn prev-btn">‹</button>
    <button class="slider-btn next-btn">›</button>
</div>

<div class="dots-container"></div>

## 5 Fascinations

The core themes and questions that continue to drive my research.

<div class="slides-section">
    <div class="slider">
        <!-- Fascination 1 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">01</div>
                <h3 class="slide-title">Invisible Forms of Violence</h3>
                <p class="slide-text">Especially in urban environments, where systemic violence becomes embedded in infrastructure, policies, and everyday practices.</p>
            </div>
        </div>
        
        <!-- Fascination 2 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">02</div>
                <h3 class="slide-title">Multispecies Justice</h3>
                <p class="slide-text">Who is allowed to inhabit the city and who is excluded. Questioning anthropocentric urban planning and advocating for more-than-human coexistence.</p>
            </div>
        </div>
        
        <!-- Fascination 3 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">03</div>
                <h3 class="slide-title">Embodied Knowledge</h3>
                <p class="slide-text">How bodies act as sensors and reveal what data by itself cannot do. The physical, affective, and situated ways of knowing that challenge purely rational approaches.</p>
            </div>
        </div>
        
        <!-- Fascination 4 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">04</div>
                <h3 class="slide-title">Immersive and Experiential Translation</h3>
                <p class="slide-text">Translating abstract systems into lived experiences. Creating spaces, situations, or objects that make complex issues tangible and emotionally resonant.</p>
            </div>
        </div>
        
        <!-- Fascination 5 -->
        <div class="slide">
            <div class="slide-content">
                <div class="slide-number">05</div>
                <h3 class="slide-title">From Awareness to Action</h3>
                <p class="slide-text">Connecting research insights to concrete shifts in perception, responsibility and behavior. Moving beyond critique to propose actionable alternatives.</p>
            </div>
        </div>
    </div>
    
    <button class="slider-btn prev-btn">‹</button>
    <button class="slider-btn next-btn">›</button>
</div>

<div class="dots-container"></div>

<style>
    /* Ocultar el header superior con "Atlas" */
    header:first-of-type,
    .header:first-of-type,
    .atlas-header,
    h1:first-of-type {
        display: none !important;
    }
    
    /* Títulos principales */
    h2 {
        font-size: 2rem;
        font-weight: 700;
        color: #2d3748;
        margin: 3rem 0 2rem 0;
        padding-bottom: 0.5rem;
        border-bottom: 3px solid #1976d2;
    }
    
    /* Slides section - EXACTAMENTE igual que en tu código de referencia */
    .slides-section {
        position: relative;
        max-width: 100%;
        margin: 2rem 0 3rem 0;
        border-radius: 8px;
        overflow: hidden;
        padding: 2rem;
        background: linear-gradient(135deg, #f8f9fa 0%, #f1f3f4 100%);
    }
    
    .slider {
        display: block;
    }
    
    .slide {
        display: none;
        min-height: 300px;
        background: white;
        border-radius: 12px;
        padding: 3rem;
        box-shadow: 0 4px 20px rgba(0,0,0,0.08);
        border: 1px solid #e2e8f0;
    }
    
    .slide.active-slide {
        display: block;
        animation: fadeIn 0.5s ease;
    }
    
    @keyframes fadeIn {
        from { opacity: 0.7; }
        to { opacity: 1; }
    }
    
    .slide-content {
        max-width: 800px;
        margin: 0 auto;
        position: relative;
    }
    
    .slide-number {
        position: absolute;
        top: -20px;
        left: -30px;
        font-size: 5rem;
        font-weight: 900;
        color: rgba(25, 118, 210, 0.15);
        line-height: 1;
        z-index: 0;
    }
    
    .slide-title {
        font-size: 1.8rem;
        font-weight: 700;
        color: #2d3748;
        margin: 0 0 1.5rem 0;
        padding: 0 0 0.5rem 0;
        position: relative;
        z-index: 1;
    }
    
    .slide-text {
        font-size: 1.1rem;
        line-height: 1.7;
        color: #4a5568;
        margin: 0;
        position: relative;
        z-index: 1;
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
        box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        z-index: 10;
    }
    
    .slider-btn:hover {
        background-color: rgba(255,255,255,1) !important;
        transform: translateY(-50%) scale(1.1);
    }
    
    .prev-btn {
        left: 10px;
        border-radius: 50%;
    }
    
    .next-btn {
        right: 10px;
        border-radius: 50%;
    }
    
    /* Dots - EXACTAMENTE igual que en tu código */
    .dots-container {
        text-align: center;
        padding: 20px;
        margin-bottom: 2rem;
    }
    
    .slide-dot {
        cursor: pointer;
        height: 12px;
        width: 12px;
        margin: 0 6px;
        background-color: #bbb;
        border-radius: 50%;
        display: inline-block;
        transition: background-color 0.3s ease, transform 0.3s ease;
    }
    
    .slide-dot.active-dot, .slide-dot:hover {
        background-color: #1976d2;
        transform: scale(1.2);
    }
    
    /* Estilos para el segundo carrusel */
    .slides-section:nth-of-type(2) .slide {
        background: linear-gradient(135deg, #ffffff 0%, #fafafa 100%);
        border: 1px solid #e2e8f0;
    }
    
    .slides-section:nth-of-type(2) .slide-number {
        color: rgba(156, 39, 176, 0.15);
    }
    
    .slides-section:nth-of-type(2) .slide-dot.active-dot, 
    .slides-section:nth-of-type(2) .slide-dot:hover {
        background-color: #9c27b0;
    }
    
    /* Responsive */
    @media (max-width: 768px) {
        h2 {
            font-size: 1.5rem;
            margin: 2rem 0 1.5rem 0;
        }
        
        .slides-section {
            padding: 1rem;
            margin: 1.5rem 0 2rem 0;
        }
        
        .slide {
            padding: 2rem 1.5rem;
            min-height: 250px;
        }
        
        .slide-number {
            font-size: 3.5rem;
            top: -15px;
            left: -15px;
        }
        
        .slide-title {
            font-size: 1.4rem;
        }
        
        .slide-text {
            font-size: 1rem;
        }
        
        .slider-btn {
            padding: 15px;
            font-size: 20px;
        }
    }
    
    @media (max-width: 480px) {
        .slide {
            padding: 1.5rem 1rem;
            min-height: 200px;
        }
        
        .slide-number {
            font-size: 2.5rem;
            top: -10px;
            left: -10px;
        }
        
        .slide-title {
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }
        
        .slide-text {
            font-size: 0.95rem;
        }
        
        .dots-container {
            padding: 15px;
        }
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
        slides[i].className = slides[i].className.replace(" active-slide", "");
    }
    
    // Quitar clase active de todos los dots
    for (let i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(" active-dot", "");
    }
    
    // Mostrar slide actual y activar su dot
    if (slides[slideIndex-1]) {
        slides[slideIndex-1].style.display = "block";
        slides[slideIndex-1].className += " active-slide";
    }
    if (dots[slideIndex-1]) {
        dots[slideIndex-1].className += " active-dot";
    }
}

// Auto-advance cada 8 segundos - EXACTAMENTE igual
setInterval(() => {
    plusSlides(1);
}, 8000);

// Cuando cargue la página, crear los dots para cada slider
document.addEventListener('DOMContentLoaded', function() {
    const sliders = document.querySelectorAll('.slider');
    
    sliders.forEach((slider, sliderIndex) => {
        const slides = slider.querySelectorAll('.slide');
        const dotsContainer = document.querySelectorAll('.dots-container')[sliderIndex];
        
        // Limpiar primero
        dotsContainer.innerHTML = '';
        
        // Crear un dot por cada slide
        slides.forEach((slide, index) => {
            const dot = document.createElement('span');
            dot.className = 'slide-dot';
            if (index === 0) dot.className += ' active-dot';
            dot.onclick = function() { 
                // Resetear slideIndex para cada slider individualmente
                slideIndex = index + 1;
                currentSlide(slideIndex);
            };
            dotsContainer.appendChild(dot);
        });
        
        // Configurar botones para este slider
        const prevBtn = slider.parentElement.querySelector('.prev-btn');
        const nextBtn = slider.parentElement.querySelector('.next-btn');
        
        prevBtn.addEventListener('click', function() {
            plusSlides(-1);
        });
        
        nextBtn.addEventListener('click', function() {
            plusSlides(1);
        });
    });
    
    // Mostrar el primer slide de cada slider
    showSlides(slideIndex);
});
</script>