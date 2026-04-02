<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>MDEF · Circular Material Lab | Cardboard Systems</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #faf8f4;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            color: #1e1e2a;
            line-height: 1.5;
            scroll-behavior: smooth;
        }

        .menu-container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 1.2rem 2rem 0.5rem 2rem;
        }
        .custom-header-menu {
            display: flex;
            gap: 2rem;
            font-weight: 500;
            border-bottom: 1px solid #e2e0d8;
            padding-bottom: 0.75rem;
            flex-wrap: wrap;
        }
        .custom-header-menu a {
            text-decoration: none;
            color: #2c2c2c;
            font-size: 1rem;
            transition: color 0.2s ease;
        }
        .custom-header-menu a:hover {
            color: #7c6e5d;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem 2rem 4rem 2rem;
        }

        h1 {
            font-size: 3rem;
            font-weight: 600;
            letter-spacing: -0.02em;
            margin: 1rem 0 0.5rem 0;
            color: #1f1f28;
        }

        h2 {
            font-size: 1.8rem;
            font-weight: 600;
            margin: 2rem 0 1rem 0;
            border-left: 5px solid #bbaa8a;
            padding-left: 1rem;
        }

        h3 {
            font-size: 1.3rem;
            font-weight: 600;
            margin: 1.5rem 0 0.75rem 0;
        }

        .card {
            background: #ffffff;
            border-radius: 24px;
            padding: 1.5rem;
            margin: 1.5rem 0;
            box-shadow: 0 4px 12px rgba(0,0,0,0.03);
            border: 1px solid #ece8e0;
        }

        .grid-2col {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            margin: 1.5rem 0;
        }

        .canvas-card {
            background: #fefcf7;
            border-radius: 28px;
            border: 1px solid #e5dfd3;
            padding: 1.2rem 1.5rem 1.8rem 1.5rem;
            margin: 2rem 0;
        }

        .canvas-title {
            font-weight: 700;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .badge-material {
            background: #d9cfbc;
            padding: 0.2rem 0.8rem;
            border-radius: 40px;
            font-size: 0.8rem;
        }

        hr {
            margin: 1.5rem 0;
            border: none;
            border-top: 2px dotted #ddd6cc;
        }

        .insight-box {
            background: #f3efe8;
            border-left: 5px solid #9c896c;
            padding: 1.2rem 1.5rem;
            border-radius: 20px;
            margin: 1rem 0;
        }

        footer {
            text-align: center;
            margin-top: 4rem;
            padding: 2rem;
            border-top: 1px solid #e2dbd0;
            font-size: 0.85rem;
            color: #6b6256;
        }

        @media (max-width: 700px) {
            .container {
                padding: 1rem;
            }
            .grid-2col {
                grid-template-columns: 1fr;
                gap: 1rem;
            }
            h1 {
                font-size: 2.4rem;
            }
        }

        .matrix-container {
            background: #ffffff;
            border-radius: 24px;
            padding: 1rem;
            margin: 1rem 0;
        }
        canvas#materialMatrixChart {
            max-width: 100%;
            height: auto;
            background: #fffcf5;
            border-radius: 20px;
        }
        
        .fullwidth-gallery {
            margin: 3rem 0;
            width: 100%;
        }
        .slideshow-wrapper {
            position: relative;
            width: 100%;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 12px 28px rgba(0,0,0,0.1);
            background: #1a1a1a;
        }
        .slideshow-container {
            width: 100%;
            height: 550px;
            position: relative;
            background: #e8e4dc;
        }
        .slide {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: none;
            align-items: center;
            justify-content: center;
            background: #f0ede7;
        }
        .slide.active {
            display: flex;
        }
        .slide img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            background: #f8f5ef;
        }
        .nav-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(30,30,30,0.7);
            backdrop-filter: blur(4px);
            border: none;
            border-radius: 50%;
            width: 48px;
            height: 48px;
            font-size: 2rem;
            font-weight: 300;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 20;
            color: white;
            transition: all 0.2s ease;
            font-family: monospace;
        }
        .nav-btn:hover {
            background: rgba(0,0,0,0.85);
            transform: translateY(-50%) scale(1.05);
        }
        .nav-left {
            left: 1.5rem;
        }
        .nav-right {
            right: 1.5rem;
        }
        .slide-indicators {
            position: absolute;
            bottom: 1.2rem;
            left: 0;
            right: 0;
            display: flex;
            justify-content: center;
            gap: 0.75rem;
            z-index: 20;
        }
        .indicator-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: rgba(255,255,255,0.6);
            border: none;
            cursor: pointer;
            transition: all 0.2s;
            padding: 0;
        }
        .indicator-dot.active {
            background: white;
            transform: scale(1.2);
        }
        .diagram-block {
            margin-top: 2rem;
            background: #ffffff;
            border-radius: 24px;
            padding: 1rem;
            border: 1px solid #ece2d4;
        }
        .diagram-block img {
            width: 100%;
            border-radius: 16px;
            display: block;
        }
        @media (max-width: 800px) {
            .slideshow-container {
                height: 380px;
            }
            .nav-btn {
                width: 36px;
                height: 36px;
                font-size: 1.5rem;
            }
        }
    </style>
    <script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js"></script>
</head>
<body>
<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>
<div class="container">
    
    <h1>Cardboard as a Local Material System</h1>
    <p style="font-size: 1.2rem; margin-bottom: 1.5rem; color: #3e3a33;">From waste to resource — transforming Fab Lab leftovers into rigid structures and flexible fibers.</p>

    <div class="card">
        <h2 style="margin-top: 0; border-left: none; padding-left: 0;">Week Summary</h2>
        <p><strong>Monday:</strong> Introduction to circular economy and Fab Labs as local nodes. Visit to <strong>Transfolab</strong>: a makerspace focused on community growth and upcycling.</p>
        <p><strong>Tuesday:</strong> Material experimentation matrix based on waste streams at Fab Lab Barcelona. Selected <strong>cardboard</strong> for its potential vs. accessibility. Later, <strong>Museo Terra</strong> exhibition: plastic's duality (durability vs. single-use crisis) and biomaterials.</p>
        <p><strong>Wednesday and Thursday:</strong> Hands-on experiments with cardboard — different binders, shredding, extrusion, molding and drying cycles.</p>
        <div class="insight-box">
             <strong>Key takeaway:</strong> Fab Labs can become active nodes transforming local waste into new material resources, fostering circular systems.
        </div>
    </div>

    <h2>Material System Canvas · Cardboard</h2>
    <div class="canvas-card">
        <div class="canvas-title">Source and Flow</div>
        <div class="grid-2col">
            <div><strong>Origin:</strong> Fab Lab Barcelona (packaging, prototyping leftovers). Generated by students, staff, workshops — continuous stream.<br>
            <strong>Estimated quantity:</strong> ~75.6 kg/week → ~3 tons/year.<br>
            <span class="badge-material">insight: consistent underused local stream</span></div>
            <div><strong>Characteristics:</strong> Fibrous, porous; works with water-based binders; rigid when dry, sensitive to water deformation. Strong in compression, weak in flexibility.</div>
        </div>
        <hr>
        <div class="canvas-title">Transformation and Fablab Infrastructure</div>
        <p><strong>Process:</strong> Shredding → mixing starch-based binder (water + cornstarch + glycerin) → molding / pressing / extrusion → air or heat drying.<br>
        <strong>Available machines:</strong> Laser cutter, CNC molds, 3D printer (extrusion experiments), heat press. <em>Existing infrastructure enables full local cycle.</em></p>
        <hr>
        <div class="canvas-title">Applications and End of Life</div>
        <div class="grid-2col">
            <div><strong>Products:</strong> Interlocking tiles (modular), coasters, 3D printed forms (with shrinkage limits), extruded fibers for weaving and braiding.<br>
            <strong>Not suitable for packaging →</strong> better for rigid modular and hybrid materials.</div>
            <div><strong>End of life:</strong> Fully recyclable (if clean), compostable with natural binder, can be reprocessed → fits closed-loop inside Fab Lab.</div>
        </div>
    </div>

    <h2>Distributed Production Canvas</h2>
    <div class="canvas-card" style="background: #fef7ed;">
        <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 1rem;">
            <div style="flex:1; min-width: 170px;"><strong>01 · Waste Source</strong><br>Cardboard waste from Fab Lab Barcelona, ~3 tons/year.</div>
            <div style="flex:1; min-width: 170px;"><strong>02 · Collection</strong><br>Bins managed by staff, mixed condition. <span class="badge-material">challenge: no quality sorting</span></div>
            <div style="flex:1; min-width: 170px;"><strong>03 · FabLab Processing</strong><br>Shredding → bio-binder → pressing/extrusion → drying and flattening → assembly.</div>
            <div style="flex:1; min-width: 170px;"><strong>04 · Application/Product</strong><br>Modular tiles, coasters, woven hybrids. For designers, students, temporary installations.</div>
            <div style="flex:1; min-width: 170px;"><strong>05 · Next Life</strong><br>Reuse, reprocess (reshred), compost. Material stays inside continuous local loop.</div>
        </div>
        <div class="insight-box" style="margin-top: 1rem;">The FabLab acts as a local processing node — connecting urban waste flows with distributed manufacturing.</div>
    </div>

    <h2>Material Experimentation Matrix</h2>
    <div class="canvas-card">
        <p style="margin-bottom: 0.75rem;">Prioritising experiments: mapping materials by <strong>potential performance</strong> vs. <strong>technical complexity</strong>. Cardboard offers high potential and low-medium complexity.</p>
        <div class="matrix-container">
            <canvas id="materialMatrixChart" width="800" height="450" style="width:100%; height:auto; max-width:1000px; margin:0 auto; display:block;"></canvas>
        </div>
        <p class="insight-box" style="margin-top: 1rem;"><strong>Decision:</strong> Cardboard balances accessibility, processability, and circular potential → ideal for local experimentation.</p>
    </div>

    <h2>Material Exploration · Cardboard Experiments</h2>
    <div class="grid-2col">
        <div class="card">
            <h3>Experiment 1</h3>
            <p><strong>Very dry shredded + 3 parts binder</strong> → not homogeneous, hard to control.</p>
            <h3>Experiment 2</h3>
            <p><strong>Finer shredding + less drying (moist) + 2 parts binder</strong> → extrusion failed (lumps in binder), blockages.</p>
            <h3>Experiment 3 (best result)</h3>
            <p><strong>Finer shredding, higher moisture, homogeneous mix</strong> → successful extrusion, smooth flow, better control.</p>
        </div>
        <div class="card">
            <h3>Material Behavior and Insights</h3>
            <p>Strong and rigid when dry. Can hold thin shapes but deforms during drying (shrinkage). Heat press flattens pieces.<br>
            <strong>Extruded strands:</strong> "straw-like", braidable, high shrinkage → potential for textiles and connectors.<br>
            <strong>Tiles and coasters:</strong> interlocking system, rigid, good compression resistance.<br>
            <strong>Water content is critical:</strong> shrinkage must be designed, not avoided.</p>
        </div>
    </div>

    <div class="insight-box" style="background: #e7e2d7;">
        <strong>Multi-state material system:</strong> Cardboard is not waste — it is a versatile resource shifting between rigid structures and flexible fibers, enabling circular, distributed production.
    </div>

    <!-- FULL WIDTH SLIDESHOW GALLERY - USING LOCAL IMAGES -->
    <div class="fullwidth-gallery">
        <div class="slideshow-wrapper">
            <div class="slideshow-container" id="mainSlideshow">
                <!-- slides injected by javascript -->
            </div>
            <button class="nav-btn nav-left" id="prevSlideBtn">‹</button>
            <button class="nav-btn nav-right" id="nextSlideBtn">›</button>
            <div class="slide-indicators" id="slideIndicators"></div>
        </div>
        <p style="text-align: center; margin-top: 1rem; color: #5a5548; font-size: 0.9rem;">Process documentation: shredding, binder mixing, extrusion, tiles, braided fibers and heat pressing.</p>
    </div>

    <!-- System diagram with local image -->
    <div class="diagram-block">
        <h3 style="margin-left: 0.5rem;">Circular Production Flow Diagram</h3>
        <img src="../../images/circular_diagram.jpg" 
             alt="Circular production flow diagram" 
             width="100%" 
             style="border-radius: 16px; object-fit: cover;">
        <p style="margin-top: 0.75rem; text-align: center; font-size: 0.85rem;">Conceptual diagram: from waste collection to reprocessing and new applications within Fab Lab.</p>
    </div>

    <div class="canvas-card">
        <div class="canvas-title">Hybrid experiments: rigid and flexible</div>
        <div class="grid-2col">
            <div><strong>Extruded straws braiding:</strong> Combining rigid connectors with flexible woven elements opens new possibilities for modular furniture, biodegradable textiles and architectural components.</div>
            <div><strong>Heat-press flattening:</strong> Post-drying correction allows precise thickness and flatness for interlocking joints. Laser cutting of final tiles tested at Fab Lab.</div>
        </div>
    </div>
</div>

<footer>
    MDEF · Circular Material Systems | Cardboard as local resource — from waste to closed-loop production | Fab Lab Barcelona 2025
</footer>

<script>
    // INTERACTIVE MATRIX CHART
    const ctx = document.getElementById('materialMatrixChart').getContext('2d');
    const materialsData = [
        { name: 'Cardboard / paper', x: 2.8, y: 8.2, color: '#b48c5c', radius: 14, highlight: true },
        { name: 'Ceramics / clay', x: 7.2, y: 7.5, color: '#bfa77a', radius: 11 },
        { name: 'Organic / food waste', x: 5.5, y: 6.8, color: '#96a57c', radius: 11 },
        { name: 'Wood / sawdust', x: 4.2, y: 6.5, color: '#9b7e5c', radius: 11 },
        { name: 'Plastics / PLA', x: 6.5, y: 7.9, color: '#7e8c8d', radius: 11 },
        { name: 'Electronics waste', x: 9.0, y: 5.2, color: '#9e7b68', radius: 10 },
        { name: 'Textile scraps', x: 4.5, y: 6.2, color: '#be9e7a', radius: 10 }
    ];

    new Chart(ctx, {
        type: 'bubble',
        data: {
            datasets: [{
                label: 'Material potential vs complexity',
                data: materialsData.map(m => ({ x: m.x, y: m.y, r: m.radius })),
                backgroundColor: materialsData.map(m => m.highlight ? '#cc9c6c' : m.color),
                borderColor: materialsData.map(m => m.highlight ? '#8b5e2c' : '#cbbfaa'),
                borderWidth: 1.5,
                hoverRadius: 16
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: true,
            plugins: {
                tooltip: {
                    callbacks: {
                        label: (context) => {
                            const idx = context.dataIndex;
                            const mat = materialsData[idx];
                            return `${mat.name}: Performance ${mat.y}/10 · Complexity ${mat.x}/10`;
                        }
                    }
                },
                legend: { display: false },
                title: {
                    display: true,
                    text: 'Performance Potential vs Technical Complexity',
                    font: { size: 14, weight: 'normal', family: 'Inter' },
                    padding: { bottom: 12 }
                }
            },
            scales: {
                x: {
                    title: { display: true, text: 'Technical Complexity (low to high)', font: { weight: 'bold' } },
                    min: 0, max: 10,
                    grid: { color: '#e2dbd0' },
                    ticks: { stepSize: 2 }
                },
                y: {
                    title: { display: true, text: 'Performance Potential', font: { weight: 'bold' } },
                    min: 0, max: 10,
                    grid: { color: '#e2dbd0' },
                    ticks: { stepSize: 2 }
                }
            },
            layout: {
                padding: { top: 15, bottom: 10, left: 10, right: 10 }
            }
        }
    });

    // FULL WIDTH SLIDESHOW WITH LOCAL IMAGES
    // Using your local image paths: ../../images/circular1.jpg, circular2.jpg, etc.
    const slideshowImages = [
        "../../images/circular1.jpg",
        "../../images/circular2.jpg",
        "../../images/circular3.jpg",
        "../../images/circular4.jpg",
        "../../images/circular5.jpg",
        "../../images/circular6.jpg",
        "../../images/circular7.jpg",
        "../../images/circular8.jpg"
    ];
    
    const captionsList = [
        "Shredded cardboard feedstock ready for binder mixing",
        "Starch-based binder preparation (water + cornstarch + glycerin)",
        "Experiment 3: smooth extrusion of homogeneous pulp",
        "Tile prototypes drying — shrinkage visible, later flattened",
        "Interlocking cardboard tiles: rigid, modular, structural",
        "Extruded straw-like fibers braided — textile potential",
        "Heat press corrects warping, ensures flat interlocking surfaces",
        "Finished coasters with high compression resistance"
    ];

    let currentSlideIndex = 0;
    let slidesArray = [];
    let indicatorsArray = [];

    function initSlideshow() {
        const container = document.getElementById('mainSlideshow');
        if (!container) return;
        container.innerHTML = '';
        
        for (let i = 0; i < slideshowImages.length; i++) {
            const slideDiv = document.createElement('div');
            slideDiv.className = 'slide';
            if (i === 0) slideDiv.classList.add('active');
            
            const img = document.createElement('img');
            img.src = slideshowImages[i];
            img.alt = captionsList[i];
            img.loading = 'lazy';
            
            const captionSpan = document.createElement('div');
            captionSpan.innerText = captionsList[i];
            captionSpan.style.position = 'absolute';
            captionSpan.style.bottom = '12px';
            captionSpan.style.left = '12px';
            captionSpan.style.backgroundColor = 'rgba(0,0,0,0.55)';
            captionSpan.style.color = 'white';
            captionSpan.style.padding = '6px 14px';
            captionSpan.style.borderRadius = '40px';
            captionSpan.style.fontSize = '0.8rem';
            captionSpan.style.backdropFilter = 'blur(4px)';
            captionSpan.style.pointerEvents = 'none';
            captionSpan.style.zIndex = '5';
            
            slideDiv.appendChild(img);
            slideDiv.appendChild(captionSpan);
            container.appendChild(slideDiv);
        }
        
        slidesArray = document.querySelectorAll('#mainSlideshow .slide');
        
        const indicatorParent = document.getElementById('slideIndicators');
        indicatorParent.innerHTML = '';
        for (let i = 0; i < slidesArray.length; i++) {
            const dot = document.createElement('button');
            dot.classList.add('indicator-dot');
            if (i === 0) dot.classList.add('active');
            dot.addEventListener('click', () => goToSlide(i));
            indicatorParent.appendChild(dot);
        }
        indicatorsArray = document.querySelectorAll('.indicator-dot');
        
        const prevBtn = document.getElementById('prevSlideBtn');
        const nextBtn = document.getElementById('nextSlideBtn');
        if (prevBtn) prevBtn.onclick = () => { changeSlide(-1); };
        if (nextBtn) nextBtn.onclick = () => { changeSlide(1); };
        
        window.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowLeft') { changeSlide(-1); e.preventDefault(); }
            if (e.key === 'ArrowRight') { changeSlide(1); e.preventDefault(); }
        });
    }
    
    function changeSlide(direction) {
        let newIndex = currentSlideIndex + direction;
        if (newIndex < 0) newIndex = slidesArray.length - 1;
        if (newIndex >= slidesArray.length) newIndex = 0;
        goToSlide(newIndex);
    }
    
    function goToSlide(index) {
        if (!slidesArray.length) return;
        slidesArray[currentSlideIndex].classList.remove('active');
        if (indicatorsArray[currentSlideIndex]) indicatorsArray[currentSlideIndex].classList.remove('active');
        
        currentSlideIndex = index;
        slidesArray[currentSlideIndex].classList.add('active');
        if (indicatorsArray[currentSlideIndex]) indicatorsArray[currentSlideIndex].classList.add('active');
    }
    
    document.addEventListener('DOMContentLoaded', () => {
        initSlideshow();
    });
</script>
<style>
    .slide {
        transition: opacity 0.2s ease;
        background: #2a2824;
        display: flex !important;
        opacity: 0;
        visibility: hidden;
    }
    .slide.active {
        opacity: 1;
        visibility: visible;
        z-index: 2;
    }
    .slide {
        opacity: 0;
        visibility: hidden;
        transition: opacity 0.25s ease, visibility 0.25s;
        align-items: center;
        justify-content: center;
    }
    .slide.active {
        opacity: 1;
        visibility: visible;
    }
    .slideshow-container {
        position: relative;
        background: #e2dbd0;
    }
    .slide img {
        object-fit: cover;
        width: 100%;
        height: 100%;
    }
    .indicator-dot {
        background: rgba(255,255,245,0.7);
        width: 10px;
        height: 10px;
        border-radius: 50%;
        margin: 0 5px;
        border: none;
        transition: 0.2s;
    }
    .indicator-dot.active {
        background: #ffffff;
        transform: scale(1.2);
        box-shadow: 0 0 4px rgba(0,0,0,0.3);
    }
    .diagram-block img {
        max-height: 400px;
        object-fit: cover;
        width: 100%;
    }
    .matrix-container canvas {
        width: 100%;
        height: auto;
    }
</style>
</body>
</html>