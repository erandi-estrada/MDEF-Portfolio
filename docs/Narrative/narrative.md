<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Narrative I</title>
    <style>
        /* ESTILOS GENERALES - Basados en tu referencia */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Helvetica Neue', -apple-system, BlinkMacSystemFont, sans-serif;
        }

        body {
            background-color: #fefefe;
            color: #333;
            line-height: 1.6;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        /* Menú superior estilo MDEF */
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
            position: relative;
        }

        .custom-header-menu a:hover {
            color: #1976d2;
        }

        .custom-header-menu a:first-child {
            color: #333;
            font-weight: 600;
        }

        /* Títulos y texto */
        h1 {
            font-weight: 350;
            font-size: 3.2rem;
            letter-spacing: -0.5px;
            margin-bottom: 1.5rem;
            color: #222;
            line-height: 1.2;
        }

        h2 {
            font-weight: 400;
            font-size: 1.8rem;
            margin-top: 4rem;
            margin-bottom: 1.8rem;
            color: #444;
            padding-bottom: 0.5rem;
            border-bottom: 1px solid #f0f0f0;
        }

        p {
            font-weight: 350;
            font-size: 1.15rem;
            margin-bottom: 1.8rem;
            max-width: 900px;
            color: #555;
            line-height: 1.7;
        }

        /* Sección de Slides - Estilo mejorado */
        .slides-section {
            margin: 5rem 0;
            position: relative;
        }

        .slides-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            margin-bottom: 2.5rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }

        .slides-title {
            font-weight: 400;
            font-size: 1.5rem;
            color: #444;
        }

        .slides-count {
            font-size: 0.9rem;
            color: #888;
            font-weight: 400;
        }

        /* Contenedor principal del slider */
        .slider-container {
            position: relative;
            max-width: 1000px;
            margin: 0 auto;
            overflow: hidden;
            border-radius: 4px;
            background-color: #fafafa;
            border: 1px solid #f0f0f0;
        }

        /* Contenedor de las imágenes */
        .slider {
            display: flex;
            transition: transform 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }

        /* Cada slide */
        .slide {
            min-width: 100%;
            position: relative;
        }

        .slide img {
            width: 100%;
            height: 600px;
            object-fit: cover;
            display: block;
            background: linear-gradient(135deg, #f5f7fa 0%, #e4e8f0 100%);
        }

        /* Texto descriptivo de la imagen */
        .image-info {
            position: absolute;
            bottom: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            padding: 1.8rem 2rem;
            border-top: 1px solid #f0f0f0;
        }

        .image-title {
            font-size: 1.2rem;
            font-weight: 500;
            color: #333;
            margin-bottom: 0.5rem;
        }

        .image-description {
            font-size: 0.95rem;
            color: #666;
            font-weight: 350;
            line-height: 1.5;
            max-width: 700px;
        }

        /* Botones de navegación - Estilo refinado */
        .slider-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(255, 255, 255, 0.9);
            border: 1px solid #e0e0e0;
            color: #444;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            cursor: pointer;
            z-index: 10;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        }

        .slider-btn:hover {
            background-color: white;
            border-color: #ccc;
            box-shadow: 0 4px 12px rgba(0,0,0,0.12);
            transform: translateY(-50%) scale(1.05);
        }

        .prev-btn {
            left: 25px;
        }

        .next-btn {
            right: 25px;
        }

        /* Indicadores/puntos - Estilo minimalista */
        .dots-container {
            display: flex;
            justify-content: center;
            padding: 2rem 0 1rem 0;
            gap: 10px;
        }

        .dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background-color: #ddd;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .dot.active {
            background-color: #777;
            transform: scale(1.2);
        }

        /* Controles adicionales */
        .slider-controls {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 2rem;
            margin-top: 1.5rem;
        }

        .control-btn {
            background: none;
            border: 1px solid #ddd;
            padding: 0.5rem 1.2rem;
            border-radius: 4px;
            font-size: 0.9rem;
            color: #666;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .control-btn:hover {
            border-color: #999;
            color: #333;
        }

        /* Notas al pie */
        .footnote {
            font-size: 0.9rem;
            color: #888;
            font-style: italic;
            margin-top: 0.5rem;
            text-align: center;
        }

        /* Pie de página */
        footer {
            margin-top: 6rem;
            padding-top: 2rem;
            border-top: 1px solid #eee;
            text-align: center;
            font-size: 0.9rem;
            color: #999;
        }

        /* Responsive */
        @media (max-width: 1024px) {
            .slider-container {
                max-width: 100%;
            }
            
            .slide img {
                height: 500px;
            }
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 1.5rem;
                margin-top: 3rem;
            }
            
            .slide img {
                height: 400px;
            }
            
            .image-info {
                padding: 1.2rem 1.5rem;
            }
            
            .image-title {
                font-size: 1.1rem;
            }
            
            .slider-btn {
                width: 40px;
                height: 40px;
                font-size: 1rem;
            }
            
            .prev-btn {
                left: 15px;
            }
            
            .next-btn {
                right: 15px;
            }
            
            .custom-header-menu {
                gap: 1.5rem;
                font-size: 0.9rem;
            }
        }

        @media (max-width: 480px) {
            body {
                padding: 15px;
            }
            
            .slide img {
                height: 300px;
            }
            
            .image-info {
                padding: 1rem;
            }
            
            .image-title {
                font-size: 1rem;
            }
            
            .image-description {
                font-size: 0.85rem;
            }
            
            .slider-btn {
                width: 36px;
                height: 36px;
                font-size: 0.9rem;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .menu-container {
                margin-bottom: 2rem;
            }
        }

        /* Animación sutil para transiciones */
        @keyframes fadeIn {
            from { opacity: 0.7; }
            to { opacity: 1; }
        }

        .slide img {
            animation: fadeIn 0.5s ease-out;
        }
    </style>
</head>
<body>

    <!-- Menú superior estilo tu referencia -->
    <div class="menu-container">
        <div class="custom-header-menu">
            <a href="../..">MDEF</a>
            <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
            <a href="../../about/me">About me</a>
        </div>
    </div>

    <h1>Narrative I</h1>

    <h2>Short Proposal</h2>
    <p>This pictorial proposes an open visual exploration of multispecies justice, without fixing a single subject, scale, or outcome. Rather than presenting conclusions, it assembles images, textures, overlays, and partial texts to speculate on how non-human lives intersect with urban environments and human-centered systems. Inspired by visual essays the work treats images as the main thinking tool, layering, obscuring, and contrasting elements to surface relationships that are usually overlooked. The format remains fluid and modular, functioning as a provisional map of questions, observations, and possible directions, allowing the project to evolve as new species, sites, and perspectives emerge.</p>

    <!-- Sección de Slides -->
    <section class="slides-section">
        <div class="slides-header">
            <div class="slides-title">Pictorial Exploration</div>
            <div class="slides-count">9 visual entries</div>
        </div>
        
        <div class="slider-container">
            <div class="slider">
                <!-- Slide 1 -->
                <div class="slide">
                    <img src="https://images.unsplash.com/photo-1578662996442-48f60103fc96?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Pictorial 1">
                    <div class="image-info">
                        <div class="image-title">Pictorial 1 • Concrete and organic patterns intersecting</div>
                        <div class="image-description">An exploration of how urban materials and natural forms create hybrid textures, questioning boundaries between built and grown environments.</div>
                    </div>
                </div>
                
                <!-- Slide 2 -->
                <div class="slide">
                    <img src="https://images.unsplash.com/photo-1544551763-46a013bb70d5?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Pictorial 2">
                    <div class="image-info">
                        <div class="image-title">Pictorial 2 • Plant life through human-made barriers</div>
                        <div class="image-description">Vegetation finding paths through architectural constraints, illustrating resilience and adaptation in multispecies urban ecosystems.</div>
                    </div>
                </div>
                
                <!-- Slide 3 -->
                <div class="slide">
                    <img src="https://images.unsplash.com/photo-1513475382585-d06e58bcb0e0?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Pictorial 3">
                    <div class="image-info">
                        <div class="image-title">Pictorial 3 • Provisional colors as material placeholders</div>
                        <div class="image-description">Yellow and blue layers acting as temporary markers for different material qualities and sensory conditions in the urban fabric.</div>
                    </div>
                </div>
                
                <!-- Slide 4 -->
                <div class="slide">
                    <img src="https://images.unsplash.com/photo-1550684376-efcbd6e3f031?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Pictorial 4">
                    <div class="image-info">
                        <div class="image-title">Pictorial 4 • Animal traces in architectural spaces</div>
                        <div class="image-description">Evidence of non-human presence within human-designed structures, revealing shared occupancy and invisible habitats.</div>
                    </div>
                </div>
                
                <!-- Slide 5 -->
                <div class="slide">
                    <img src="https://images.unsplash.com/photo-1506905925346-21bda4d32df4?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Pictorial 5">
                    <div class="image-info">
                        <div class="image-title">Pictorial 5 • Shifting scales between micro and macro</div>
                        <div class="image-description">A visual investigation of how perspective changes our understanding of multispecies relationships and urban ecologies.</div>
                    </div>
                </div>
                
                <!-- Slide 6 -->
                <div class="slide">
                    <img src="https://images.unsplash.com/photo-1518834103328-93d45986dce1?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Pictorial 6">
                    <div class="image-info">
                        <div class="image-title">Pictorial 6 • Visual layers and obscured elements</div>
                        <div class="image-description">Overlapping textures and partial visibility as a method to reveal normally hidden interspecies connections.</div>
                    </div>
                </div>
                
                <!-- Slide 7 -->
                <div class="slide">
                    <img src="https://images.unsplash.com/photo-1559827260-dc66d52bef19?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Pictorial 7">
                    <div class="image-info">
                        <div class="image-title">Pictorial 7 • Water as a reflective, connecting element</div>
                        <div class="image-description">Liquid surfaces mirroring both human and non-human worlds, suggesting fluid boundaries and shared dependencies.</div>
                    </div>
                </div>
                
                <!-- Slide 8 -->
                <div class="slide">
                    <img src="https://images.unsplash.com/photo-1507146426996-ef05306b995a?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Pictorial 8">
                    <div class="image-info">
                        <div class="image-title">Pictorial 8 • Ground-level, multispecies viewpoint</div>
                        <div class="image-description">An alternative perspective that challenges human-centered urban planning and reveals non-human spatial experiences.</div>
                    </div>
                </div>
                
                <!-- Slide 9 -->
                <div class="slide">
                    <img src="https://images.unsplash.com/photo-1459478309853-2c33a60058e7?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Pictorial 9">
                    <div class="image-info">
                        <div class="image-title">Pictorial 9 • Abstracted textures suggesting overlooked relationships</div>
                        <div class="image-description">Visual patterns that invite speculation about hidden ecological connections and multispecies justice in urban spaces.</div>
                    </div>
                </div>
            </div>
            
            <!-- Botones de navegación -->
            <button class="slider-btn prev-btn">‹</button>
            <button class="slider-btn next-btn">›</button>
        </div>
        
        <!-- Indicadores de puntos -->
        <div class="dots-container">
            <!-- Los puntos se generan con JavaScript -->
        </div>
        
        <!-- Controles adicionales -->
        <div class="slider-controls">
            <button class="control-btn autoplay-btn">Pause autoplay</button>
            <button class="control-btn fullscreen-btn">View fullscreen</button>
        </div>
        
        <p class="footnote">Images function as primary thinking tools—layering, obscuring, and contrasting to surface overlooked relationships.</p>
    </section>

    <h2>Draft Pictorial</h2>
    <p>The current pictorial draft takes the form of a series of images arranged within a minimal and flexible layout, where visual material leads the narrative. Yellow and blue are used as provisional colors to differentiate images, textures, and visual layers, rather than as a fixed palette. At this stage, color operates as a placeholder for different material qualities, atmospheres, or sensory conditions, and is expected to shift as the project develops.</p>
    
    <p>White space is intentionally present, creating pauses between images and text, and allowing each element to be read independently while still contributing to an overall flow. The emphasis remains on images as carriers of meaning, with text acting as a subtle guide rather than an explanation. This draft functions as an exploratory structure, testing rhythm, contrast, and visual hierarchy, rather than a finalized composition.</p>

    <footer>
        Narrative I — An open visual exploration of multispecies justice • MDEF Research • 2024
    </footer>

    <script>
        // Script para el funcionamiento del slider
        document.addEventListener('DOMContentLoaded', function() {
            const slider = document.querySelector('.slider');
            const slides = document.querySelectorAll('.slide');
            const prevBtn = document.querySelector('.prev-btn');
            const nextBtn = document.querySelector('.next-btn');
            const dotsContainer = document.querySelector('.dots-container');
            const autoplayBtn = document.querySelector('.autoplay-btn');
            const fullscreenBtn = document.querySelector('.fullscreen-btn');
            
            let currentSlide = 0;
            const totalSlides = slides.length;
            let autoplayInterval;
            let isAutoplayActive = true;
            
            // Crear los puntos indicadores
            for (let i = 0; i < totalSlides; i++) {
                const dot = document.createElement('div');
                dot.classList.add('dot');
                if (i === 0) dot.classList.add('active');
                dot.addEventListener('click', () => goToSlide(i));
                dotsContainer.appendChild(dot);
            }
            
            const dots = document.querySelectorAll('.dot');
            
            // Función para ir a un slide específico
            function goToSlide(n) {
                currentSlide = (n + totalSlides) % totalSlides;
                slider.style.transform = `translateX(-${currentSlide * 100}%)`;
                updateDots();
            }
            
            // Actualizar el punto activo
            function updateDots() {
                dots.forEach((dot, index) => {
                    dot.classList.toggle('active', index === currentSlide);
                });
            }
            
            // Slide siguiente
            function nextSlide() {
                goToSlide(currentSlide + 1);
            }
            
            // Slide anterior
            function prevSlide() {
                goToSlide(currentSlide - 1);
            }
            
            // Función de autoplay
            function startAutoplay() {
                if (autoplayInterval) clearInterval(autoplayInterval);
                autoplayInterval = setInterval(nextSlide, 5000); // Cambia cada 5 segundos
                autoplayBtn.textContent = 'Pause autoplay';
                isAutoplayActive = true;
            }
            
            function stopAutoplay() {
                if (autoplayInterval) clearInterval(autoplayInterval);
                autoplayBtn.textContent = 'Start autoplay';
                isAutoplayActive = false;
            }
            
            // Toggle autoplay
            function toggleAutoplay() {
                if (isAutoplayActive) {
                    stopAutoplay();
                } else {
                    startAutoplay();
                }
            }
            
            // Función para pantalla completa
            function toggleFullscreen() {
                const sliderContainer = document.querySelector('.slider-container');
                
                if (!document.fullscreenElement) {
                    if (sliderContainer.requestFullscreen) {
                        sliderContainer.requestFullscreen();
                    } else if (sliderContainer.webkitRequestFullscreen) {
                        sliderContainer.webkitRequestFullscreen();
                    } else if (sliderContainer.msRequestFullscreen) {
                        sliderContainer.msRequestFullscreen();
                    }
                    fullscreenBtn.textContent = 'Exit fullscreen';
                } else {
                    if (document.exitFullscreen) {
                        document.exitFullscreen();
                    } else if (document.webkitExitFullscreen) {
                        document.webkitExitFullscreen();
                    } else if (document.msExitFullscreen) {
                        document.msExitFullscreen();
                    }
                    fullscreenBtn.textContent = 'View fullscreen';
                }
            }
            
            // Event listeners para los botones
            nextBtn.addEventListener('click', function() {
                nextSlide();
                if (isAutoplayActive) {
                    stopAutoplay();
                    startAutoplay(); // Reinicia el autoplay después de interacción manual
                }
            });
            
            prevBtn.addEventListener('click', function() {
                prevSlide();
                if (isAutoplayActive) {
                    stopAutoplay();
                    startAutoplay();
                }
            });
            
            // Event listeners para controles
            autoplayBtn.addEventListener('click', toggleAutoplay);
            fullscreenBtn.addEventListener('click', toggleFullscreen);
            
            // Navegación con teclado
            document.addEventListener('keydown', (e) => {
                if (e.key === 'ArrowLeft') {
                    prevSlide();
                    if (isAutoplayActive) {
                        stopAutoplay();
                        startAutoplay();
                    }
                }
                if (e.key === 'ArrowRight') {
                    nextSlide();
                    if (isAutoplayActive) {
                        stopAutoplay();
                        startAutoplay();
                    }
                }
                if (e.key === ' ') {
                    e.preventDefault();
                    toggleAutoplay();
                }
                if (e.key === 'f' || e.key === 'F') {
                    toggleFullscreen();
                }
            });
            
            // Detectar cambio en pantalla completa
            document.addEventListener('fullscreenchange', function() {
                if (!document.fullscreenElement) {
                    fullscreenBtn.textContent = 'View fullscreen';
                }
            });
            
            // Pausar autoplay al hacer hover sobre el slider
            const sliderContainer = document.querySelector('.slider-container');
            sliderContainer.addEventListener('mouseenter', stopAutoplay);
            sliderContainer.addEventListener('mouseleave', function() {
                if (isAutoplayActive) {
                    startAutoplay();
                }
            });
            
            // Iniciar autoplay al cargar
            startAutoplay();
            
            // Actualizar texto del botón de pantalla completa según capacidad
            if (!document.fullscreenEnabled) {
                fullscreenBtn.style.display = 'none';
            }
        });
    </script>
</body>
</html>