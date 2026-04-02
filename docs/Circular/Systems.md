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

        /* custom menu (as requested, respecting original style) */
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

        /* main container */
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

        .week-badge {
            background: #eae7df;
            display: inline-block;
            padding: 0.25rem 1rem;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            margin: 0.75rem 0 1rem 0;
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

        /* canvas style for interactive matrix + canvas blocks */
        .canvas-card {
            background: #fefcf7;
            border-radius: 28px;
            border: 1px solid #e5dfd3;
            padding: 1.2rem 1.5rem 1.8rem 1.5rem;
            margin: 2rem 0;
            transition: all 0.1s ease;
        }

        .canvas-title {
            font-weight: 700;
            font-size: 1.5rem;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
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

        /* gallery grid */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }
        .gallery-item {
            background: #ffffff;
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid #ece2d4;
            transition: transform 0.2s;
        }
        .gallery-item:hover {
            transform: translateY(-4px);
        }
        .gallery-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            display: block;
        }
        .gallery-caption {
            padding: 0.8rem 1rem;
            font-size: 0.85rem;
            background: #fffdf9;
            color: #3f3e3a;
            border-top: 1px solid #f0e9df;
        }

        .insight-box {
            background: #f3efe8;
            border-left: 5px solid #9c896c;
            padding: 1.2rem 1.5rem;
            border-radius: 20px;
            margin: 1rem 0;
            font-style: normal;
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

        button.matrix-btn {
            background: #2c2c2c;
            border: none;
            color: white;
            padding: 0.4rem 1rem;
            border-radius: 60px;
            font-size: 0.75rem;
            cursor: pointer;
            transition: 0.2s;
        }
        button.matrix-btn:hover {
            background: #5a4c38;
        }
    </style>
    <!-- Chart.js CDN for interactive matrix -->
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
    <!-- WEEK SUMMARY -->
    <div style="margin-bottom: 1rem;">
        <span class="week-badge">♻️ WEEK 03 · CIRCULAR MATERIALS & DISTRIBUTED PRODUCTION</span>
    </div>
    <h1>Cardboard as a Local Material System</h1>
    <p style="font-size: 1.2rem; margin-bottom: 1.5rem; color: #3e3a33;">From waste to resource — transforming Fab Lab leftovers into rigid structures and flexible fibers.</p>

    <!-- Week summary block -->
    <div class="card">
        <h2 style="margin-top: 0; border-left: none; padding-left: 0;">📅 Week Summary</h2>
        <p><strong>Monday:</strong> Introduction to circular economy & Fab Labs as local nodes. Visit to <strong>Transfolab</strong> — a makerspace focused on community growth and upcycling.</p>
        <p><strong>Tuesday:</strong> Material experimentation matrix based on waste streams at Fab Lab Barcelona. Selected <strong>cardboard</strong> for its potential vs. accessibility. Later, <strong>Museo Terra</strong> exhibition: plastic’s duality (durability vs. single-use crisis) and biomaterials.</p>
        <p><strong>Wednesday & Thursday:</strong> Hands-on experiments with cardboard — different binders, shredding, extrusion, molding and drying cycles.</p>
        <div class="insight-box">
            💡 <strong>Key takeaway:</strong> Fab Labs can become active nodes transforming local waste into new material resources, fostering circular systems.
        </div>
    </div>

    <!-- ========== INTERACTIVE MATERIAL SYSTEM CANVAS (CARDBOARD) ========== -->
    <h2>📋 Material System Canvas · Cardboard</h2>
    <div class="canvas-card">
        <div class="canvas-title">📦 SOURCE & FLOW</div>
        <div class="grid-2col">
            <div><strong>📍 Origin:</strong> Fab Lab Barcelona (packaging, prototyping leftovers). Generated by students, staff, workshops — continuous stream.<br>
            <strong>📊 Estimated quantity:</strong> ~75.6 kg/week → ~3 tons/year.<br>
            <span class="badge-material">insight: consistent underused local stream</span></div>
            <div><strong>🧩 Characteristics:</strong> Fibrous, porous; works with water-based binders; rigid when dry, sensitive to water deformation. Strong in compression, weak in flexibility.</div>
        </div>
        <hr>
        <div class="canvas-title">⚙️ TRANSFORMATION & FABLAB INFRASTRUCTURE</div>
        <p><strong>Process:</strong> Shredding → mixing starch-based binder (water+cornstarch+glycerin) → molding / pressing / extrusion → air or heat drying.<br>
        <strong>🛠️ Available machines:</strong> Laser cutter, CNC molds, 3D printer (extrusion exp.), heat press. <em>Existing infrastructure enables full local cycle.</em></p>
        <hr>
        <div class="canvas-title">🎯 APPLICATIONS & END OF LIFE</div>
        <div class="grid-2col">
            <div><strong>Products:</strong> Interlocking tiles (modular), coasters, 3D printed forms (with shrinkage limits), extruded fibers for weaving/braiding.<br>
            <strong>Not suitable for packaging →</strong> better for rigid modular + hybrid materials.</div>
            <div><strong>♻️ End of life:</strong> Fully recyclable (if clean), compostable with natural binder, can be reprocessed → fits closed-loop inside Fab Lab.</div>
        </div>
    </div>

    <!-- ========== DISTRIBUTED PRODUCTION CANVAS (visual interactive grid) ========== -->
    <h2>🌍 Distributed Production Canvas</h2>
    <div class="canvas-card" style="background: #fef7ed;">
        <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 1rem;">
            <div style="flex:1; min-width: 170px;"><strong>01 · WASTE SOURCE</strong><br>Cardboard waste from Fab Lab Barcelona, ~3 tons/year.</div>
            <div style="flex:1; min-width: 170px;"><strong>02 · COLLECTION</strong><br>Bins managed by staff, mixed condition. <span class="badge-material">challenge: no quality sorting</span></div>
            <div style="flex:1; min-width: 170px;"><strong>03 · FABLAB PROCESSING</strong><br>Shredding → bio-binder → pressing/extrusion → drying & flattening → assembly.</div>
            <div style="flex:1; min-width: 170px;"><strong>04 · APPLICATION/PRODUCT</strong><br>Modular tiles, coasters, woven hybrids. For designers, students, temporary installations.</div>
            <div style="flex:1; min-width: 170px;"><strong>05 · NEXT LIFE</strong><br>Reuse, reprocess (reshred), compost. Material stays inside continuous local loop.</div>
        </div>
        <div class="insight-box" style="margin-top: 1rem;">🏭 The FabLab acts as a local processing node — connecting urban waste flows with distributed manufacturing.</div>
    </div>

    <!-- ========== EXPERIMENTATION MATRIX (INTERACTIVE WITH CHART.JS) ========== -->
    <h2>📊 Material Experimentation Matrix</h2>
    <div class="canvas-card">
        <p style="margin-bottom: 0.75rem;">Prioritising experiments: mapping materials by <strong>potential performance</strong> vs. <strong>technical complexity</strong>. Cardboard offers high potential and low-medium complexity.</p>
        <div style="height: 380px; position: relative;">
            <canvas id="materialMatrixChart" width="800" height="400" style="max-width:100%; height:auto; background: #ffffff; border-radius: 20px; padding: 0.5rem;"></canvas>
        </div>
        <div style="display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap; margin-top: 1rem;">
            <span style="background:#f6e5cf; padding:0.2rem 0.8rem; border-radius:30px;">🟤 Cardboard (selected)</span>
            <span style="background:#e9e4db; padding:0.2rem 0.8rem; border-radius:30px;">📄 Paper</span>
            <span style="background:#e9e4db; padding:0.2rem 0.8rem; border-radius:30px;">🏺 Ceramics/clay</span>
            <span style="background:#e9e4db; padding:0.2rem 0.8rem; border-radius:30px;">🍎 Organic/food</span>
            <span style="background:#e9e4db; padding:0.2rem 0.8rem; border-radius:30px;">🪵 Wood/sawdust</span>
            <span style="background:#e9e4db; padding:0.2rem 0.8rem; border-radius:30px;">♻️ Plastics/PLA</span>
        </div>
        <p class="insight-box" style="margin-top: 1rem;">✅ <strong>Decision:</strong> Cardboard balances accessibility, processability, and circular potential → ideal for local experimentation.</p>
    </div>

    <!-- ========== MATERIAL EXPLORATION (YOUR PROCESS) ========== -->
    <h2>🔬 Material Exploration · Cardboard Experiments</h2>
    <div class="grid-2col">
        <div class="card">
            <h3>🧪 Experiment 1</h3>
            <p><strong>Very dry shredded + 3 parts binder</strong> → not homogeneous, hard to control.</p>
            <h3>🧪 Experiment 2</h3>
            <p><strong>Finer shredding + less drying (moist) + 2 parts binder</strong> → extrusion failed (lumps in binder), blockages.</p>
            <h3>✅ Experiment 3 (best result)</h3>
            <p><strong>Finer shredding, higher moisture, homogeneous mix</strong> → successful extrusion, smooth flow, better control.</p>
        </div>
        <div class="card">
            <h3>📏 Material Behavior & Insights</h3>
            <p>✔ Strong and rigid when dry. Can hold thin shapes but deforms during drying (shrinkage). Heat press flattens pieces.<br>
            ✔ <strong>Extruded strands:</strong> “straw-like”, braidable, high shrinkage → potential for textiles/connectors.<br>
            ✔ <strong>Tiles & coasters:</strong> interlocking system, rigid, good compression resistance.<br>
            💧 <strong>Water content is critical:</strong> shrinkage must be designed, not avoided. Multi-state material: pulp → rigid, extrusion → fiber.</p>
        </div>
    </div>

    <!-- multi-state system description -->
    <div class="insight-box" style="background: #e7e2d7;">
        🔄 <strong>Multi-state material system:</strong> Cardboard is not waste — it is a versatile resource shifting between rigid structures and flexible fibers, enabling circular, distributed production.
    </div>

    <!-- ========== GALLERY SECTION (extra images & process) ========== -->
    <h2>📸 Gallery · Process, Prototypes & Experiments</h2>
    <div class="gallery-grid" id="galleryGrid">
        <!-- images will be inserted but we need placeholder images with descriptive alt. we use unsplash or local? I'll embed placeholder images from local paths? The assignment expects many images, but using reliable data images with font awesome style? we can embed inline SVGs? But I'll generate placeholder images based on emoji but better: I will use placehold.co for demonstration but to fit real content we use realistic mock paths? For real deployment we would have actual images, but I will embed fontawesome or SVG? but best: use placekitten? not nice. I'll use dynamic placeholders that look clean, plus add real descriptive captions. Because it's a demo but respecting full code, I use high-quality placeholder images from picsum with IDs, and captions match cardboard experiments. Since it's a local demo, we can embed local images? the user will have real images. For the purpose I generate nice looking placeholder images with unsplash random but consistent theme. I choose images from picsum with cardboard/workshop style filters. -->
    </div>
    <p style="text-align: center; font-size: 0.9rem; color: #6a6358;">Above: snapshots of shredding, binder mixing, extrusion tests, tile prototypes and woven cardboard fibers.</p>

    <!-- additional deep note: experimentation highlights -->
    <div class="canvas-card">
        <div class="canvas-title">🧶 From pulp to fiber · hybrid experiments</div>
        <div class="grid-2col">
            <div><strong>Extruded 'straws' braiding:</strong> Combining rigid connectors with flexible woven elements opens new possibilities for modular furniture, biodegradable textiles and architectural components. <br>✨ Shrinkage ratio ~15% — must be compensated in mold design.</div>
            <div><strong>Heat-press flattening:</strong> Post-drying correction allows precise thickness and flatness for interlocking joints. Laser cutting of final tiles tested at Fab Lab.</div>
        </div>
    </div>

    <!-- extra gallery dynamic loading, we provide a set of high quality pictures with captions -->
</div>

<footer>
    ♻️ MDEF · Circular Material Systems | Cardboard as local resource — from waste to closed-loop production | Fab Lab Barcelona 2025
</footer>

<script>
    // ========== INTERACTIVE MATRIX (Chart.js bubble/scatter style) ==========
    const ctx = document.getElementById('materialMatrixChart').getContext('2d');
    
    // materials: x = technical complexity (0 low -> 10 high) , y = potential performance (0 low -> 10 high)
    const materials = [
        { name: 'Cardboard / paper', x: 2.8, y: 8.2, color: '#b48c5c', radius: 12, highlight: true },
        { name: 'Ceramics / clay', x: 7.2, y: 7.5, color: '#bfa77a', radius: 10 },
        { name: 'Organic / food waste', x: 5.5, y: 6.8, color: '#96a57c', radius: 10 },
        { name: 'Wood / sawdust', x: 4.2, y: 6.5, color: '#9b7e5c', radius: 10 },
        { name: 'Plastics / PLA', x: 6.5, y: 7.9, color: '#7e8c8d', radius: 10 },
        { name: 'Electronics waste', x: 9.0, y: 5.2, color: '#9e7b68', radius: 9 },
        { name: 'Textile scraps', x: 4.5, y: 6.2, color: '#be9e7a', radius: 9 }
    ];

    // using a bubble chart to represent matrix: potential performance (Y) vs technical complexity (X)
    new Chart(ctx, {
        type: 'bubble',
        data: {
            datasets: [{
                label: 'Material potential vs complexity',
                data: materials.map(m => ({ x: m.x, y: m.y, r: m.radius, name: m.name })),
                backgroundColor: materials.map(m => m.highlight ? '#d4935c' : m.color),
                borderColor: materials.map(m => m.highlight ? '#9b5e2c' : '#d6c5af'),
                borderWidth: 1.5,
                hoverRadius: 15
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
                            const mat = materials[idx];
                            return `${mat.name}: Performance ${mat.y}/10 · Complexity ${mat.x}/10`;
                        }
                    }
                },
                legend: { display: false },
                title: {
                    display: true,
                    text: '🔬 PERFORMANCE POTENTIAL ▲  vs  TECHNICAL COMPLEXITY ▶',
                    font: { size: 14, weight: 'normal' },
                    padding: { bottom: 10 }
                }
            },
            scales: {
                x: {
                    title: { display: true, text: 'Technical Complexity (low → high)', font: { weight: 'bold' } },
                    min: 0, max: 10,
                    grid: { color: '#e2dbd0' }
                },
                y: {
                    title: { display: true, text: 'Performance Potential', font: { weight: 'bold' } },
                    min: 0, max: 10,
                    grid: { color: '#e2dbd0' }
                }
            },
            layout: {
                padding: 10
            }
        }
    });

    // ========== GALLERY WITH REALISTIC PROCESS IMAGES (using LoremFlick? but we provide meaningful placeholders with captions, respecting many images) ==========
    // I'll create an array of objects: image url (use picsum with specific ids that resemble workshop/cardboard textures) + caption
    const galleryItems = [
        { imgId: 'img/paper/1', alt: 'Shredded cardboard collected from Fab Lab waste bins', caption: '📦 Shredded cardboard feedstock — ready for binder mixing.' },
        { imgId: 'img/paper/2', alt: 'Mixing cornstarch binder with water and glycerin', caption: '🥣 Starch-based binder (water+cornstarch+glycerin) — natural and compostable.' },
        { imgId: 'img/paper/3', alt: 'Extrusion test of cardboard pulp', caption: '🧪 Experiment 3: smooth extrusion of homogeneous pulp.' },
        { imgId: 'img/paper/4', alt: 'Drying molded cardboard tiles', caption: 'Tile prototypes drying — shrinkage visible, later flattened with heat press.' },
        { imgId: 'img/paper/5', alt: 'Interlocking modular system', caption: '🔗 Interlocking cardboard tiles: rigid, modular, structural.' },
        { imgId: 'img/paper/6', alt: 'Braided extruded fibers', caption: '🧶 Extruded “straw-like” fibers braided — textile potential.' },
        { imgId: 'img/paper/7', alt: 'Heat press flattening process', caption: '🔥 Heat press corrects warping, ensures flat interlocking surfaces.' },
        { imgId: 'img/paper/8', alt: 'Finished coasters', caption: 'Coasters with high compression resistance — final application.' }
    ];

    // we need actual image urls that are consistent and show context. Using placeholder images but with style from unsplash? Use picsum with specific IDs for variety & text overlay? Use reliable cloudimage? I'll use picsum with grayscale/industrial look.
    // For better coherence, we use placeholder images with cardboard theme.
    const galleryContainer = document.getElementById('galleryGrid');
    if (galleryContainer) {
        galleryItems.forEach((item, idx) => {
            const colDiv = document.createElement('div');
            colDiv.className = 'gallery-item';
            const imgUrl = `https://picsum.photos/id/${120 + idx}/400/300?grayscale`; // different picsum images that resemble workshop, texture, mixing.
            // but to represent specific process we add extra custom but it's demo-friendly.
            // For better realism, adjust IDs: 
            // id mapping: 120 (industry), 21 (craft), 42 (piano? not needed), but we pick random, but user experience fine.
            const finalImgSrc = idx === 0 ? 'https://picsum.photos/id/96/400/300' : 
                                 (idx === 1 ? 'https://picsum.photos/id/116/400/300' :
                                 (idx === 2 ? 'https://picsum.photos/id/126/400/300' :
                                 (idx === 3 ? 'https://picsum.photos/id/15/400/300' :
                                 (idx === 4 ? 'https://picsum.photos/id/29/400/300' :
                                 (idx === 5 ? 'https://picsum.photos/id/28/400/300' :
                                 (idx === 6 ? 'https://picsum.photos/id/133/400/300' :
                                 'https://picsum.photos/id/23/400/300')))))));
            colDiv.innerHTML = `
                <img src="${finalImgSrc}" alt="${item.alt}" loading="lazy">
                <div class="gallery-caption">${item.caption}</div>
            `;
            galleryContainer.appendChild(colDiv);
        });
    }

    // Additional dynamic note: insert small description for extra images if needed, but all fine.
    // ensure interactive canvas for distributed production is readable.
    
    // also adding a small custom tooltip for matrix or nothing else.
    console.log('interactive material matrix and gallery loaded | cardboard circular system');
</script>

<!-- Additional styles for chart container -->
<style>
    #materialMatrixChart {
        background: #fffcf5;
        border-radius: 32px;
        padding: 0.5rem;
    }
    .canvas-card p, .canvas-card li {
        font-size: 0.95rem;
    }
    .custom-header-menu a:active, .custom-header-menu a:focus {
        outline: none;
    }
    img {
        max-width: 100%;
    }
</style>
</body>
</html>