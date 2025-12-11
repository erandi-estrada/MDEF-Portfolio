<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

<style>
/* Estilos generales para las secciones */
.workshop-section {
    margin: 5rem 0;
    padding: 2rem;
    background: #f8f9fa;
    border-radius: 12px;
    border-left: 4px solid #333;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
}

.workshop-section:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 30px rgba(0,0,0,0.1);
}

.section-header {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    margin-bottom: 2rem;
    cursor: pointer;
}

.section-icon {
    font-size: 2.5rem;
    opacity: 0.7;
    transition: all 0.3s ease;
}

.section-title {
    font-size: 2rem;
    font-weight: 700;
    color: #1a1a1a;
    margin: 0;
    transition: all 0.3s ease;
}

.workshop-section:hover .section-title {
    color: #0066cc;
}

.workshop-section:hover .section-icon {
    opacity: 1;
    transform: scale(1.1);
}

.content-wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: start;
}

.image-container {
    position: relative;
    overflow: hidden;
    border-radius: 8px;
    height: 300px;
}

.workshop-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: all 0.5s ease;
    cursor: zoom-in;
}

.workshop-image:hover {
    transform: scale(1.05);
}

.image-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0,0,0,0.7);
    color: white;
    padding: 0.5rem 1rem;
    font-size: 0.9rem;
    opacity: 0;
    transform: translateY(20px);
    transition: all 0.3s ease;
}

.image-container:hover .image-overlay {
    opacity: 1;
    transform: translateY(0);
}

.text-content {
    font-size: 1.1rem;
    line-height: 1.6;
    color: #444;
}

.lesson-learned {
    background: rgba(255, 193, 7, 0.1);
    border-left: 3px solid #ffc107;
    padding: 1rem;
    margin: 1.5rem 0;
    font-style: italic;
    transform: translateX(-20px);
    opacity: 0;
    transition: all 0.5s ease 0.2s;
}

.lesson-learned.visible {
    transform: translateX(0);
    opacity: 1;
}

.tools-used {
    display: flex;
    gap: 0.5rem;
    flex-wrap: wrap;
    margin-top: 1.5rem;
}

.tool-tag {
    background: #e9ecef;
    padding: 0.3rem 0.8rem;
    border-radius: 20px;
    font-size: 0.85rem;
    color: #495057;
    transition: all 0.3s ease;
}

.tool-tag:hover {
    background: #0066cc;
    color: white;
    transform: translateY(-2px);
}

/* Modal para imagen ampliada */
.image-modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.9);
    justify-content: center;
    align-items: center;
}

.modal-content {
    max-width: 90%;
    max-height: 90%;
    object-fit: contain;
}

.close-modal {
    position: absolute;
    top: 20px;
    right: 30px;
    color: white;
    font-size: 40px;
    cursor: pointer;
}

/* Responsive */
@media (max-width: 768px) {
    .content-wrapper {
        grid-template-columns: 1fr;
    }
    
    .workshop-section {
        margin: 3rem 0;
        padding: 1.5rem;
    }
}
</style>

<!-- Modal para imagen ampliada -->
<div id="imageModal" class="image-modal">
    <span class="close-modal">&times;</span>
    <img class="modal-content" id="modalImage">
</div>

<script>
// Interacción para las secciones
document.addEventListener('DOMContentLoaded', function() {
    // Abrir/cerrar modal de imágenes
    const modal = document.getElementById('imageModal');
    const modalImg = document.getElementById('modalImage');
    const closeModal = document.querySelector('.close-modal');
    
    document.querySelectorAll('.workshop-image').forEach(img => {
        img.addEventListener('click', function() {
            modal.style.display = 'flex';
            modalImg.src = this.src;
        });
    });
    
    closeModal.addEventListener('click', function() {
        modal.style.display = 'none';
    });
    
    modal.addEventListener('click', function(e) {
        if (e.target === modal) {
            modal.style.display = 'none';
        }
    });
    
    // Revelar lecciones aprendidas al hacer scroll
    const observerOptions = {
        threshold: 0.1,
        rootMargin: '0px 0px -50px 0px'
    };
    
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, observerOptions);
    
    document.querySelectorAll('.lesson-learned').forEach(el => {
        observer.observe(el);
    });
});
</script>

<!-- Sección Laser Cutting -->
<section class="workshop-section" id="laser-cutting">
    <div class="section-header" onclick="document.getElementById('laser-content').classList.toggle('expanded')">
        <div class="section-icon">⚡</div>
        <h2 class="section-title">Laser Cutting</h2>
    </div>
    
    <div class="content-wrapper">
        <div class="image-container">
            <img src="../../images/laser.jpg" alt="Laser cutting process" class="workshop-image">
            <div class="image-overlay">MDF box for silicone mold containment</div>
        </div>
        
        <div class="text-content">
            <p>During this session, we used MDF to laser-cut the box that would later hold our silicone mold.</p>
            
            <div class="lesson-learned">
                <strong>Key Insight:</strong> Our main issue appeared when we realized the box did not have zero tolerance, which allowed gaps where the silicone could escape. This pushed us to improvise a temporary solution using tape to seal the edges.
            </div>
            
            <p>In the end, the experience reinforced how small inaccuracies at this stage can affect all the following steps.</p>
            
            <div class="tools-used">
                <span class="tool-tag">Laser Cutter</span>
                <span class="tool-tag">MDF</span>
                <span class="tool-tag">Rhino</span>
                <span class="tool-tag">Tolerance Testing</span>
            </div>
        </div>
    </div>
</section>

<!-- Sección 3D Printing -->
<section class="workshop-section" id="3d-printing">
    <div class="section-header" onclick="document.getElementById('printing-content').classList.toggle('expanded')">
        <div class="section-icon">🔶</div>
        <h2 class="section-title">3D Printing</h2>
    </div>
    
    <div class="content-wrapper">
        <div class="image-container">
            <img src="../../images/3d.jpg" alt="3D printed maze" class="workshop-image">
            <div class="image-overlay">Concentric layer pattern on maze surface</div>
        </div>
        
        <div class="text-content">
            <p>For the 3D printing session, we decided to create a small maze as the positive piece for our mold. Choosing concentric top layers resulted in a surface with very visible lines, making the finish look rougher than expected.</p>
            
            <div class="lesson-learned">
                <strong>Material Expression:</strong> This became an interesting lesson on how printing settings directly shape the material expression of an object.
            </div>
            
            <p>It became clear how each setting directly shapes the material expression of the piece, and how easily a single parameter can shift the result.</p>
            
            <div class="tools-used">
                <span class="tool-tag">Bambu Printer</span>
                <span class="tool-tag">PLA</span>
                <span class="tool-tag">Slicing Software</span>
            </div>
        </div>
    </div>
</section>

<!-- Sección CNC Milling -->
<section class="workshop-section" id="cnc-milling">
    <div class="section-header" onclick="document.getElementById('cnc-content').classList.toggle('expanded')">
        <div class="section-icon">⚙️</div>
        <h2 class="section-title">CNC Milling</h2>
    </div>
    
    <div class="content-wrapper">
        <div class="image-container">
            <img src="../../images/cnc.jpg" alt="CNC milling frame" class="workshop-image">
            <div class="image-overlay">Precision-cut frame for cast piece</div>
        </div>
        
        <div class="text-content">
            <p>With the CNC, we produced the frame where the final cast piece would be placed. This session highlighted the importance of understanding tolerances, tool types, and machining strategies.</p>
            
            <div class="lesson-learned">
                <strong>Strategic Planning:</strong> Our main challenge was deciding which tools and operations were appropriate for the design, especially given how many options CNC workflows offer.
            </div>
            
            <p>It reminded me that subtractive manufacturing demands both technical knowledge and careful planning.</p>
            
            <div class="tools-used">
                <span class="tool-tag">CNC Router</span>
                <span class="tool-tag">Plywood</span>
                <span class="tool-tag">CAM Software</span>
            </div>
        </div>
    </div>
</section>

<!-- Sección Molding & Casting -->
<section class="workshop-section" id="molding-casting">
    <div class="section-header" onclick="document.getElementById('mold-content').classList.toggle('expanded')">
        <div class="section-icon">🧪</div>
        <h2 class="section-title">Molding & Casting</h2>
    </div>
    
    <div class="content-wrapper">
        <div class="image-container">
            <img src="../../images/molding.jpg" alt="Silicone mold curing" class="workshop-image">
            <div class="image-overlay">Silicone capturing 3D print details</div>
        </div>
        
        <div class="text-content">
            <p>For the mold, we worked with silicone and learned about locks, wall thickness, and proper sealing. Despite preparing everything carefully, the laser-cut box still leaked due to its imperfect tolerances.</p>
            
            <div class="lesson-learned">
                <strong>Adaptive Making:</strong> After sealing it with tape, the mold cured well and captured the details of the 3D print accurately.
            </div>
            
            <p>This step showed how even basic containment structures need precision, and how adaptable you must be when something unexpected happens.</p>
            
            <div class="tools-used">
                <span class="tool-tag">Silicone</span>
                <span class="tool-tag">Mold Release</span>
            </div>
        </div>
    </div>
</section>

<!-- Sección Biomaterials -->
<section class="workshop-section" id="biomaterials">
    <div class="section-header" onclick="document.getElementById('bio-content').classList.toggle('expanded')">
        <div class="section-icon">🌱</div>
        <h2 class="section-title">Biomaterials</h2>
    </div>
    
    <div class="content-wrapper">
        <div class="image-container">
            <img src="../../images/biomaterials.jpg" alt="Resin casting samples" class="workshop-image">
            <div class="image-overlay">Two resin batches with different properties</div>
        </div>
        
        <div class="text-content">
            <p>In this session we experimented with resin as the main casting material. We followed the recipe for the first batch, but it turned out to be insufficient, so we mixed a second batch without strictly following the proportions.</p>
            
            <div class="lesson-learned">
                <strong>Surprising Result:</strong> The "improvised" mixture cured much better: stronger, stiffer, and closer to what we intended. The part made with the correct recipe was soft and fragile.
            </div>
            
            <p>This contrast made the session particularly interesting, showing how small deviations in biomaterial formulas can dramatically change their behavior.</p>
            
            <div class="tools-used">
                <span class="tool-tag">Bio-resin</span>
                <span class="tool-tag">Casting</span>
                <span class="tool-tag">Material Testing</span>
                <span class="tool-tag">Recipe Variation</span>
            </div>
        </div>
    </div>
</section>

<!-- Sección TouchDesigner -->
<section class="workshop-section" id="touchdesigner">
    <div class="section-header" onclick="document.getElementById('td-content').classList.toggle('expanded')">
        <div class="section-icon">🎨</div>
        <h2 class="section-title">TouchDesigner</h2>
    </div>
    
    <div class="content-wrapper">
        <video controls autoplay muted loop width="100%" style="border-radius: 8px; margin: 2rem 0;">
  <source src="../../videos/touch.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
        
        <div class="text-content">
            <p>The final session focused on creating a visual composition in TouchDesigner. It was less about fabrication and more about exploring digital expression and real-time visuals.</p>
            
            <div class="lesson-learned">
                <strong>Digital Expression:</strong> Even though it was brief, it connected the making process with a more experiential and interactive layer.
            </div>
            
            <p>It showed how design also expands beyond physical materials, opening possibilities for sensory and temporal dimensions in our work.</p>
            
            <div class="tools-used">
                <span class="tool-tag">TouchDesigner</span>
                <span class="tool-tag">Real-time</span>
                <span class="tool-tag">Visual Programming</span>
            </div>
        </div>
    </div>
</section>

<!-- Final Reflection -->
<section class="workshop-section" id="final-reflection" style="background: #1a1a1a; color: white; border-left-color: #ffc107;">
    <div class="section-header">
        <div class="section-icon" style="color: #ffc107;">✨</div>
        <h2 class="section-title" style="color: white;">Final Reflection</h2>
    </div>
    
    <div style="max-width: 800px; margin: 0 auto;">
        <p style="font-size: 1.2rem; line-height: 1.7;">
            Across these sessions, the goal was to understand the workflow, the potential errors, and the wide range of tools available in the workshop. Even with previous experience in all these techniques, revisiting them through different machines and setups was valuable.
        </p>
        
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem; margin: 2.5rem 0;">
            <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px;">
                <h4 style="color: #ffc107; margin-top: 0;">Anticipation</h4>
                <p>Each stage revealed how critical it is to anticipate mistakes before they happen.</p>
            </div>
            
            <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px;">
                <h4 style="color: #ffc107; margin-top: 0;">Adaptation</h4>
                <p>Learning to adapt when things go wrong is essential in digital fabrication.</p>
            </div>
            
            <div style="background: rgba(255,255,255,0.1); padding: 1.5rem; border-radius: 8px;">
                <h4 style="color: #ffc107; margin-top: 0;">Exploration</h4>
                <p>Prototyping is both technical and exploratory—an essential part of designing with intention.</p>
            </div>
        </div>
        
        <p style="font-size: 1.2rem; line-height: 1.7; border-top: 2px solid rgba(255,255,255,0.2); padding-top: 2rem;">
            This hands-on overview reinforced how prototyping bridges precision and experimentation, reminding us that making is not just about following instructions, but about developing an intuition for materials, machines, and their unpredictable interactions.
        </p>
    </div>
</section>

<script>
// Interacción adicional: expandir/contraer secciones
document.querySelectorAll('.section-header').forEach(header => {
    header.addEventListener('click', function() {
        const section = this.parentElement;
        const content = section.querySelector('.content-wrapper');
        if (content) {
            content.classList.toggle('collapsed');
            content.style.maxHeight = content.classList.contains('collapsed') ? '0' : '1000px';
            content.style.overflow = 'hidden';
            content.style.transition = 'max-height 0.3s ease';
        }
    });
});
</script>

<style>
/* Ocultar el header superior con "Atlas" */
header:first-of-type,
.header:first-of-type,
.atlas-header,
h1:first-of-type {
    display: none !important;
}
</style>