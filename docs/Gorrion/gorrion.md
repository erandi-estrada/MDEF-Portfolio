<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>House Sparrow - Urban Ecology Diagram</title>
    <style>
        /* Estilos del menú (igual que antes) */
        .menu-container {
            background: #fff;
            padding: 1rem 2rem;
            border-bottom: 1px solid #e2e8f0;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
        }
        
        .custom-header-menu {
            display: flex;
            gap: 2rem;
            justify-content: center;
        }
        
        .custom-header-menu a {
            text-decoration: none;
            color: #2d3748;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            transition: all 0.3s ease;
        }
        
        .custom-header-menu a:hover {
            background: #f7fafc;
            color: #1976d2;
        }
        
        /* Espacio para el menú fijo */
        body {
            padding-top: 60px;
            margin: 0;
            background: #fefaf0;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
        }
        
        /* Contenedor principal */
        .diagram-container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }
        
        /* Título principal */
        .main-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            color: #2d3748;
            margin-bottom: 0.5rem;
        }
        
        .subtitle {
            text-align: center;
            font-size: 1.2rem;
            color: #4a5568;
            margin-bottom: 3rem;
        }
        
        /* Contenedor del diagrama */
        .diagram-wrapper {
            position: relative;
            min-height: 600px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        /* Círculo central */
        .central-circle {
            position: relative;
            width: 180px;
            height: 180px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
            transition: transform 0.5s ease;
            overflow: hidden;
        }
        
        .central-circle:hover {
            transform: scale(1.05);
        }
        
        .central-image {
            width: 100%;
            height: 100%;
            object-fit: contain;
            padding: 15px;
        }
        
        /* Círculos radiales */
        .radial-circle {
            position: absolute;
            width: 140px;
            height: 140px;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            z-index: 1;
            transform-origin: center center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            overflow: hidden;
        }
        
        /* Estados del círculo radial */
        .radial-circle:hover {
            transform: scale(1.15) rotate(360deg);
            z-index: 3;
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        }
        
        /* Imágenes del círculo (frontal y trasera) */
        .circle-front, .circle-back {
            position: absolute;
            width: 100%;
            height: 100%;
            object-fit: contain;
            transition: all 0.5s ease;
            backface-visibility: hidden;
            padding: 15px;
        }
        
        .circle-front {
            opacity: 1;
            transform: rotateY(0deg);
        }
        
        .circle-back {
            opacity: 0;
            transform: rotateY(180deg);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 20px;
        }
        
        .radial-circle:hover .circle-front {
            opacity: 0;
            transform: rotateY(180deg);
        }
        
        .radial-circle:hover .circle-back {
            opacity: 1;
            transform: rotateY(0deg);
        }
        
        /* Estilos para el texto en la parte trasera */
        .back-content {
            color: #2d3748;
            font-size: 0.9rem;
            font-weight: 600;
            line-height: 1.3;
            padding: 10px;
        }
        
        .back-number {
            font-size: 2rem;
            font-weight: 900;
            color: #1976d2;
            margin-bottom: 5px;
            line-height: 1;
        }
        
        /* Flechas conectivas */
        .arrow {
            position: absolute;
            stroke: #1976d2;
            stroke-width: 2;
            stroke-dasharray: 5,5;
            fill: none;
            z-index: 0;
            pointer-events: none;
        }
        
        /* Información expandida */
        .expanded-info {
            position: fixed;
            top: 100px;
            right: 2rem;
            width: 300px;
            background: white;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            opacity: 0;
            transform: translateX(20px);
            transition: all 0.4s ease;
            z-index: 100;
            display: none;
        }
        
        .expanded-info.active {
            opacity: 1;
            transform: translateX(0);
            display: block;
        }
        
        .info-title {
            font-size: 1.3rem;
            font-weight: 700;
            color: #1976d2;
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid #e2e8f0;
        }
        
        .info-list {
            list-style: none;
            padding: 0;
            margin: 0;
        }
        
        .info-list li {
            padding: 0.5rem 0;
            border-bottom: 1px solid #f7fafc;
            color: #4a5568;
            font-size: 0.95rem;
            line-height: 1.4;
        }
        
        .info-list li:last-child {
            border-bottom: none;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .diagram-wrapper {
                min-height: 400px;
                transform: scale(0.8);
            }
            
            .central-circle {
                width: 150px;
                height: 150px;
            }
            
            .radial-circle {
                width: 120px;
                height: 120px;
            }
            
            .expanded-info {
                position: relative;
                top: auto;
                right: auto;
                width: 100%;
                margin: 2rem auto;
                max-width: 500px;
            }
        }
        
        @media (max-width: 480px) {
            .diagram-wrapper {
                transform: scale(0.7);
            }
            
            .main-title {
                font-size: 2rem;
            }
            
            .central-circle {
                width: 130px;
                height: 130px;
            }
            
            .radial-circle {
                width: 100px;
                height: 100px;
            }
        }
    </style>
</head>
<body>
    <!-- Menú (igual que en las otras páginas) -->
    <div class="menu-container">
        <div class="custom-header-menu">
            <a href="../..">MDEF</a>
            <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
            <a href="../../about/me">About me</a>
        </div>
    </div>
    
    <!-- Contenedor principal del diagrama -->
    <div class="diagram-container">
        <h1 class="main-title">House Sparrow</h1>
        <p class="subtitle">Urban Ecological Stress Factors</p>
        
        <div class="diagram-wrapper">
            <!-- Círculo central (NO gira) -->
            <div class="central-circle">
                <img src="images/Diagrama/Centro.png" alt="House Sparrow Central" class="central-image">
            </div>
            
            <!-- Círculos radiales (6 en total) -->
            <!-- 1. Health Decline Without Escape -->
            <div class="radial-circle" style="top: 10%; left: 20%;" data-index="1">
                <img src="images/Diagrama/1.png" alt="Health Decline" class="circle-front">
                <div class="circle-back">
                    <div class="back-content">
                        <div class="back-number">01</div>
                        Health Decline Without Escape
                    </div>
                </div>
            </div>
            
            <!-- 2. Urban Attractors and Constraints -->
            <div class="radial-circle" style="top: 10%; right: 20%;" data-index="2">
                <img src="images/Diagrama/2.png" alt="Urban Attractors" class="circle-front">
                <div class="circle-back">
                    <div class="back-content">
                        <div class="back-number">02</div>
                        Urban Attractors and Constraints
                    </div>
                </div>
            </div>
            
            <!-- 3. Dietary Poverty & Toxic Intake -->
            <div class="radial-circle" style="top: 50%; left: 5%;" data-index="3">
                <img src="images/Diagrama/3.png" alt="Dietary Poverty" class="circle-front">
                <div class="circle-back">
                    <div class="back-content">
                        <div class="back-number">03</div>
                        Dietary Poverty & Toxic Intake
                    </div>
                </div>
            </div>
            
            <!-- 4. Chronic Stress and Energetic Drain -->
            <div class="radial-circle" style="top: 50%; right: 5%;" data-index="4">
                <img src="images/Diagrama/4.png" alt="Chronic Stress" class="circle-front">
                <div class="circle-back">
                    <div class="back-content">
                        <div class="back-number">04</div>
                        Chronic Stress and Energetic Drain
                    </div>
                </div>
            </div>
            
            <!-- 5. Impaired Foraging Behavior -->
            <div class="radial-circle" style="bottom: 10%; left: 20%;" data-index="5">
                <img src="images/Diagrama/5.png" alt="Impaired Foraging" class="circle-front">
                <div class="circle-back">
                    <div class="back-content">
                        <div class="back-number">05</div>
                        Impaired Foraging Behavior and Decision-Making
                    </div>
                </div>
            </div>
            
            <!-- 6. Density, Waste, and Compounding Exposure -->
            <div class="radial-circle" style="bottom: 10%; right: 20%;" data-index="6">
                <img src="images/Diagrama/6.png" alt="Density and Waste" class="circle-front">
                <div class="circle-back">
                    <div class="back-content">
                        <div class="back-number">06</div>
                        Density, Waste, and Compounding Exposure
                    </div>
                </div>
            </div>
            
            <!-- SVG para flechas -->
            <svg class="arrow" width="100%" height="100%" style="position: absolute; top: 0; left: 0;">
                <!-- Las flechas se generan con JavaScript -->
            </svg>
        </div>
        
        <!-- Información expandida (se muestra al hacer hover) -->
        <div class="expanded-info" id="expandedInfo">
            <h3 class="info-title" id="infoTitle">Health Decline Without Escape</h3>
            <ul class="info-list" id="infoList">
                <!-- El contenido se llena con JavaScript -->
            </ul>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const circles = document.querySelectorAll('.radial-circle');
            const expandedInfo = document.getElementById('expandedInfo');
            const infoTitle = document.getElementById('infoTitle');
            const infoList = document.getElementById('infoList');
            const arrowSvg = document.querySelector('.arrow');
            
            // Datos para cada círculo
            const circleData = {
                1: {
                    title: "Health Decline Without Escape",
                    items: [
                        "Limited access to natural habitats",
                        "Reduced genetic diversity",
                        "Increased disease susceptibility",
                        "No migratory escape routes",
                        "Cumulative health impacts"
                    ]
                },
                2: {
                    title: "Urban Attractors and Constraints",
                    items: [
                        "Artificial nesting sites",
                        "Food availability in human spaces",
                        "Limited predator-free zones",
                        "Thermal regulation challenges",
                        "Acoustic interference"
                    ]
                },
                3: {
                    title: "Dietary Poverty & Toxic Intake",
                    items: [
                        "Processed human food dependency",
                        "Nutritional deficiencies",
                        "Pesticide accumulation",
                        "Heavy metal exposure",
                        "Plastic ingestion"
                    ]
                },
                4: {
                    title: "Chronic Stress and Energetic Drain",
                    items: [
                        "Constant anthropogenic noise",
                        "Light pollution disrupting cycles",
                        "Air pollution respiratory stress",
                        "Thermal stress extremes",
                        "Predator vigilance exhaustion"
                    ]
                },
                5: {
                    title: "Impaired Foraging Behavior and Decision-Making",
                    items: [
                        "Altered food source recognition",
                        "Reduced foraging efficiency",
                        "Increased risk-taking behavior",
                        "Social learning disruption",
                        "Cognitive overload"
                    ]
                },
                6: {
                    title: "Density, Waste, and Compounding Exposure",
                    items: [
                        "Overcrowding stress",
                        "Waste accumulation exposure",
                        "Pathogen transmission facilitation",
                        "Chemical cocktail effects",
                        "Synergistic stress impacts"
                    ]
                }
            };
            
            // Dibujar flechas desde el centro a cada círculo
            function drawArrows() {
                const container = document.querySelector('.diagram-wrapper');
                const containerRect = container.getBoundingClientRect();
                
                // Coordenadas del centro
                const centerX = containerRect.width / 2;
                const centerY = containerRect.height / 2;
                
                // Coordenadas aproximadas de cada círculo (ajustadas para el layout)
                const circlePositions = [
                    {x: centerX * 0.4, y: centerY * 0.3},    // 1: top-left
                    {x: centerX * 1.6, y: centerY * 0.3},    // 2: top-right
                    {x: centerX * 0.2, y: centerY},          // 3: middle-left
                    {x: centerX * 1.8, y: centerY},          // 4: middle-right
                    {x: centerX * 0.4, y: centerY * 1.7},    // 5: bottom-left
                    {x: centerX * 1.6, y: centerY * 1.7}     // 6: bottom-right
                ];
                
                // Limpiar flechas anteriores
                arrowSvg.innerHTML = '';
                
                // Dibujar cada flecha
                circlePositions.forEach((pos, index) => {
                    // Línea punteada desde el centro
                    const line = document.createElementNS('http://www.w3.org/2000/svg', 'line');
                    line.setAttribute('x1', centerX);
                    line.setAttribute('y1', centerY);
                    line.setAttribute('x2', pos.x);
                    line.setAttribute('y2', pos.y);
                    line.setAttribute('class', 'arrow');
                    line.setAttribute('stroke', '#1976d2');
                    line.setAttribute('stroke-width', '2');
                    line.setAttribute('stroke-dasharray', '5,5');
                    
                    // Flecha al final (triángulo)
                    const marker = document.createElementNS('http://www.w3.org/2000/svg', 'polygon');
                    const angle = Math.atan2(pos.y - centerY, pos.x - centerX);
                    const arrowSize = 8;
                    const circleRadius = 70; // Radio aproximado del círculo
                    
                    // Ajustar el punto final para que termine en el borde del círculo
                    const adjustedX = pos.x - (circleRadius * Math.cos(angle));
                    const adjustedY = pos.y - (circleRadius * Math.sin(angle));
                    
                    // Puntos del triángulo de la flecha
                    const x1 = adjustedX - arrowSize * Math.cos(angle);
                    const y1 = adjustedY - arrowSize * Math.sin(angle);
                    const x2 = x1 - arrowSize * Math.cos(angle - Math.PI/6);
                    const y2 = y1 - arrowSize * Math.sin(angle - Math.PI/6);
                    const x3 = x1 - arrowSize * Math.cos(angle + Math.PI/6);
                    const y3 = y1 - arrowSize * Math.sin(angle + Math.PI/6);
                    
                    marker.setAttribute('points', `${x1},${y1} ${x2},${y2} ${x3},${y3}`);
                    marker.setAttribute('fill', '#1976d2');
                    
                    // Actualizar línea para usar el punto ajustado
                    line.setAttribute('x2', adjustedX);
                    line.setAttribute('y2', adjustedY);
                    
                    arrowSvg.appendChild(line);
                    arrowSvg.appendChild(marker);
                });
            }
            
            // Inicializar flechas después de que todo se cargue
            window.addEventListener('load', drawArrows);
            window.addEventListener('resize', drawArrows);
            
            // Precargar imágenes traseras para evitar delay
            function preloadBackImages() {
                for (let i = 1; i <= 6; i++) {
                    const img = new Image();
                    img.src = `images/Diagrama/${i}b.png`;
                }
            }
            preloadBackImages();
            
            // Event listeners para cada círculo
            circles.forEach(circle => {
                circle.addEventListener('mouseenter', function() {
                    const index = this.dataset.index;
                    const data = circleData[index];
                    
                    // Cambiar a imagen trasera
                    const backDiv = this.querySelector('.circle-back');
                    backDiv.style.backgroundImage = `url('images/Diagrama/${index}b.png')`;
                    backDiv.style.backgroundSize = 'contain';
                    backDiv.style.backgroundPosition = 'center';
                    backDiv.style.backgroundRepeat = 'no-repeat';
                    
                    // Mostrar información expandida
                    infoTitle.textContent = data.title;
                    infoList.innerHTML = '';
                    
                    data.items.forEach(item => {
                        const li = document.createElement('li');
                        li.textContent = item;
                        infoList.appendChild(li);
                    });
                    
                    expandedInfo.classList.add('active');
                });
                
                circle.addEventListener('mouseleave', function() {
                    // Ocultar información después de un pequeño delay
                    setTimeout(() => {
                        if (!expandedInfo.matches(':hover')) {
                            expandedInfo.classList.remove('active');
                        }
                    }, 300);
                });
            });
            
            // Mantener info visible si el cursor está sobre ella
            expandedInfo.addEventListener('mouseenter', function() {
                this.classList.add('active');
            });
            
            expandedInfo.addEventListener('mouseleave', function() {
                this.classList.remove('active');
            });
            
            // Para dispositivos táctiles
            circles.forEach(circle => {
                circle.addEventListener('click', function(e) {
                    e.stopPropagation();
                    const index = this.dataset.index;
                    const data = circleData[index];
                    
                    // Alternar imagen trasera
                    const backDiv = this.querySelector('.circle-back');
                    if (backDiv.style.backgroundImage) {
                        backDiv.style.backgroundImage = '';
                    } else {
                        backDiv.style.backgroundImage = `url('images/Diagrama/${index}b.png')`;
                        backDiv.style.backgroundSize = 'contain';
                        backDiv.style.backgroundPosition = 'center';
                        backDiv.style.backgroundRepeat = 'no-repeat';
                    }
                    
                    infoTitle.textContent = data.title;
                    infoList.innerHTML = '';
                    
                    data.items.forEach(item => {
                        const li = document.createElement('li');
                        li.textContent = item;
                        infoList.appendChild(li);
                    });
                    
                    expandedInfo.classList.toggle('active');
                });
            });
            
            // Cerrar al hacer clic fuera
            document.addEventListener('click', function(e) {
                if (!expandedInfo.contains(e.target) && !Array.from(circles).some(circle => circle.contains(e.target))) {
                    expandedInfo.classList.remove('active');
                }
            });
        });
    </script>
</body>
</html>