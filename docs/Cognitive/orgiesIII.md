<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

# Body as Landscape
### Individual Reflective Documentation

<img src="../../images/Landscape/landscape1.jpg" 
     alt="Body as Landscape installation view" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

## Project Introduction

**Body as Landscape – [Full Group Documentation on Hackster.io](https://www.hackster.io/)**

This project explored the relationship between the human body and damaged ecosystems through touch, haptic feedback, sound, and projection. Inspired by the idea that the landscape can be understood as an extension of the body, the installation invited participants to physically interact with wounded environments rather than only observe them.

The project combined an organic sculptural structure, capacitive touch sensing, haptic wearables, biomaterials, and audiovisual feedback into a multisensory installation. By touching projected landscapes of polluted rivers, eroded soil, and damaged ecosystems, participants generated vibrations and sound on a second skin worn on the body, creating a physical connection between environmental damage and bodily sensation.

This documentation is a personal reflection focused on my own learning process, decisions, frustrations, and discoveries throughout the development of the project. For the collaborative process, technical implementation, and full system documentation, please refer to the Hackster documentation above.

---

## 1. Cognitive Trace

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">One of the main cognitive challenges during this project was figuring out how to physically represent the idea of "touching" damaged ecosystems. Conceptually, the relationship between the body and the landscape felt powerful from the beginning, but translating that idea into an interaction that people could immediately understand became much more complex once we started prototyping.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The project was developed in only four days, so many interaction decisions had to emerge directly through experimentation rather than long planning processes. One of the biggest questions became: how can a landscape behave like a touchable body?</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The capacitive copper "rivers" emerged from this problem. Initially, they were simply a practical solution for mapping touch across the structure. However, while building the installation, we realized they also visually reinforced the landscape narrative by resembling rivers or veins running through the terrain.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">At the same time, the copper wires also revealed a limitation in the interaction design. Because the conductive traces remained visible on the surface, the structure looked more technological than we originally intended. Ideally, the sensing system would disappear into the material itself, allowing the landscape to feel more seamless and organic.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">This opened an important line of thinking for future iterations. One possibility would be adding more layers of plaster and embedding separated sections of conductive mesh underneath the surface instead of exposing copper wiring externally. Another possibility would involve exploring alternative conductive materials or hidden sensing systems that preserve the visual cleanliness of the landscape.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">In that sense, the project became less about building a finished installation and more about discovering how environmental empathy could be translated into physical interaction.</p>
</div>

<img src="../../images/Landscape/landscape2.jpg" 
     alt="Cognitive mapping and landscape-body relationship" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 2. Moral Trace

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">One of the biggest moral and collaborative decisions during the project was accepting that we needed to simplify the system in order to preserve the core experience.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">Originally, we planned to integrate the installation with TouchDesigner so the projected ecosystems could visually react and "heal" through touch interactions. The idea was for touch to simultaneously affect sound, haptics, and the projected visuals, creating a fully synchronized immersive system.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">However, as development progressed, we realized that trying to complete every layer of the system within four days would likely compromise the entire installation. We had to decide whether to continue pursuing a technically ambitious setup or focus on making the central interaction stable enough for the presentation.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">This became an important lesson about prioritization in collaborative projects. Letting go of TouchDesigner was frustrating because it represented a significant part of the original vision. At the same time, removing it allowed us to concentrate on the tactile relationship between the participant's body and the wounded landscape, which ultimately became the strongest part of the installation.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The process made me reflect on how prototyping often involves ethical and creative compromises. Sometimes preserving the emotional clarity of an experience is more important than implementing every technological feature originally imagined.</p>
</div>

<img src="../../images/Landscape/landscape3.jpg" 
     alt="Ethical considerations and collaborative decisions" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 3. Technical Trace

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">Technically, the project became a constant negotiation between functionality, instability, and improvisation.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">One of the most frustrating moments happened during the final presentation. Shortly before the exhibition, the wireless communication system between the Barduinos was functioning correctly. The capacitive structure was successfully communicating with the wearable system wirelessly, and the interaction behaved as intended.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">However, during the actual presentation, the system became unstable and stopped functioning reliably in wireless mode. Because of the limited time available before the exhibition started, we had to quickly adapt the setup and reconnect parts of the system directly to the computer in order to keep the installation operational.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">This experience revealed how fragile interactive systems can become once they move from testing environments into public spaces. Small environmental changes, WiFi instability, power inconsistencies, or signal interference can completely alter system behavior.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">Another technical challenge involved the capacitive sensing itself. The touch mapping system worked, but it relied on visible copper wiring distributed across the structure. While effective functionally, the exposed conductive traces made the interaction layer visually apparent.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">Future iterations should focus on creating a cleaner sensing system integrated more directly into the structure itself. One idea would be increasing the number of plaster layers and testing whether the metallic mesh underneath remains conductive enough to function as distributed capacitive zones. This could potentially eliminate the need for visible copper traces on the surface.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The project ultimately taught me that interactive installations are rarely stable, closed systems. They are fragile assemblies where materials, electronics, space, timing, and human interaction continuously affect one another.</p>
</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0;">
    <img src="../../images/Landscape/landscape4.jpg" 
         alt="Technical prototype and capacitive sensing" 
         width="100%" 
         style="border-radius: 8px; object-fit: cover;">
    <img src="../../images/Landscape/landscape5.jpg" 
         alt="Installation technical setup" 
         width="100%" 
         style="border-radius: 8px; object-fit: cover;">
</div>

---

## 4. Challenges & Failures

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">The entire installation was developed within four days, so many decisions became exercises in rapid improvisation.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">One challenge was balancing ambition with feasibility. We initially planned a much more integrated audiovisual system where touch interactions would directly modify the projected landscapes in real time using TouchDesigner. However, integrating projection mapping, sensors, haptics, sound, and wireless communication within the available timeframe became unrealistic.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">Another challenge was debugging distributed systems. Because the project relied on multiple Barduinos communicating wirelessly, diagnosing problems became difficult. Sometimes the issue was code. Other times it was signal interference, unstable WiFi, incorrect thresholds, power inconsistencies, or synchronization problems.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The biomaterials also introduced limitations. Although visually successful, the gelatin skin still needs preservation improvements and stronger durability.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">At moments, the project felt held together by improvisation. But I think this is also part of prototyping interactive installations. The final artifact is not only the successful moments, but also the visible traces of experimentation, instability, and adaptation.</p>
</div>

<img src="../../images/Landscape/landscape6.jpg" 
     alt="Challenges and failures documentation" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 5. Review & Future Directions

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">Rather than understanding this project as a finished artifact, I see it as a first prototype exploring how environmental awareness can become embodied through touch.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The strongest aspect of the installation was not technological complexity, but the moment when participants physically connected touch, vibration, and wounded landscapes together.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">Future iterations would focus on:</p>
    <ul style="line-height: 1.8; margin-top: 0.5rem;">
        <li>integrating cleaner hidden sensing systems</li>
        <li>improving wireless stability</li>
        <li>reintroducing TouchDesigner for reactive visual healing</li>
        <li>creating more precise touch mapping</li>
        <li>strengthening the structure with additional plaster layers</li>
        <li>exploring alternative conductive materials</li>
        <li>refining the haptic responses across the body</li>
    </ul>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The long-term goal would be creating immersive environments where environmental care is experienced.</p>
</div>

<img src="../../images/Landscape/landscape7.jpg" 
     alt="Future vision and directions" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 6. What This Prototype Is

<div style="background: #ffffff; padding: 2rem; border-radius: 8px; border-left: 4px solid #333; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">This project is not a finished product.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">It is a material and technical exploration about how environmental empathy might be translated into physical sensation.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The installation does not attempt to solve environmental issues directly. Instead, it creates a small embodied interaction that asks participants to reconsider the relationship between their bodies and damaged ecosystems.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">For me, the most valuable aspect of the project was discovering how fragile, unstable, and emotional interactive systems can become when the body itself is treated as an interface.</p>
</div>

---

## 7. Next Steps

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0;">
    
    <div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
        <h3 style="margin-top: 0;">If I continue developing this project, the priorities would be:</h3>
        <ul style="line-height: 1.8;">
            <li>integrating TouchDesigner for reactive visual healing</li>
            <li>improving wireless synchronization between devices</li>
            <li>refining the capacitive sensing thresholds</li>
            <li>creating stronger and more durable structures</li>
            <li>improving biomaterial preservation and flexibility</li>
            <li>exploring continuous touch tracking</li>
            <li>designing more nuanced haptic vocabularies</li>
            <li>expanding the installation scale</li>
            <li>experimenting with additional sensory layers such as temperature or airflow</li>
        </ul>
    </div>
    
    <div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
        <h3 style="margin-top: 0;">Further exploration:</h3>
        <p>I would also like to further investigate how interactive installations can create embodied forms of environmental awareness without relying purely on informational narratives.</p>
        <p style="margin-top: 1rem;">The long-term goal would be creating immersive environments where care, touch, and environmental perception become physically inseparable.</p>
    </div>
    
</div>

---

<!-- Slideshow Gallery -->
<div style="display: grid; grid-template-columns: 2fr 1fr; gap: 3rem; margin: 4rem 0; align-items: start;">
    
    <div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-bottom: 1.5rem;">Project Gallery</h2>
        <div style="position: relative; width: 100%; border-radius: 12px; overflow: hidden; box-shadow: 0 6px 16px rgba(0,0,0,0.1);">
            
            <div id="stocksense-slideshow" style="width: 100%; height: 600px; background: #f0f0f0; position: relative;">
            </div>
            
            <button onclick="prevSlide()" style="position: absolute; top: 50%; left: 1rem; transform: translateY(-50%); background: rgba(255,255,255,0.9); border: none; border-radius: 50%; width: 40px; height: 40px; font-size: 1.5rem; cursor: pointer; display: flex; align-items: center; justify-content: center; z-index: 10;">‹</button>
            <button onclick="nextSlide()" style="position: absolute; top: 50%; right: 1rem; transform: translateY(-50%); background: rgba(255,255,255,0.9); border: none; border-radius: 50%; width: 40px; height: 40px; font-size: 1.5rem; cursor: pointer; display: flex; align-items: center; justify-content: center; z-index: 10;">›</button>
            
            <div id="slide-indicator" style="position: absolute; bottom: 1rem; left: 0; right: 0; display: flex; justify-content: center; gap: 0.5rem; z-index: 10;">
            </div>
        </div>
        <p style="text-align: center; margin-top: 1rem; color: #666; font-style: italic;">Use arrows to navigate through project images</p>
    </div>
    
    <div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-bottom: 1.5rem;">System Diagram</h2>
        <div style="border-radius: 12px; overflow: hidden; box-shadow: 0 6px 16px rgba(0,0,0,0.1);">
            <img src="../../images/Landscape/landscape8.jpg" 
                 alt="Body as Landscape system diagram" 
                 width="100%" 
                 style="display: block; object-fit: cover;">
        </div>
    </div>
</div>

<script>
// Slideshow functionality
let currentSlide = 0;

// Define images - UPDATED with new landscape images
const slideImages = [
    "../../images/Landscape/landscape9.jpg",
    "../../images/Landscape/landscape10.jpg",
    "../../images/Landscape/landscape11.jpg",
    "../../images/Landscape/landscape12.jpg",
    "../../images/Landscape/landscape13.jpg",
    "../../images/Landscape/landscape14.jpg"
];

const totalSlides = slideImages.length;
const slideshowContainer = document.getElementById('stocksense-slideshow');
const indicatorContainer = document.getElementById('slide-indicator');

// Initialize slideshow
function initializeSlideshow() {
    if (!slideshowContainer) return;
    
    slideshowContainer.innerHTML = '';
    indicatorContainer.innerHTML = '';
    
    const slidesContainer = document.createElement('div');
    slidesContainer.style.width = '100%';
    slidesContainer.style.height = '100%';
    slidesContainer.style.position = 'relative';
    slideshowContainer.appendChild(slidesContainer);
    
    slideImages.forEach((src, index) => {
        const slideDiv = document.createElement('div');
        slideDiv.className = 'slide';
        slideDiv.style.position = 'absolute';
        slideDiv.style.top = '0';
        slideDiv.style.left = '0';
        slideDiv.style.width = '100%';
        slideDiv.style.height = '100%';
        slideDiv.style.display = index === 0 ? 'block' : 'none';
        slideDiv.style.backgroundColor = '#f0f0f0';
        
        const img = document.createElement('img');
        img.src = src;
        img.alt = `Body as Landscape project image ${index + 1}`;
        img.style.width = '100%';
        img.style.height = '100%';
        img.style.objectFit = 'cover';
        
        img.onerror = function() {
            this.style.display = 'none';
            const errorDiv = document.createElement('div');
            errorDiv.style.display = 'flex';
            errorDiv.style.alignItems = 'center';
            errorDiv.style.justifyContent = 'center';
            errorDiv.style.height = '100%';
            errorDiv.style.backgroundColor = '#e0e0e0';
            errorDiv.style.color = '#666';
            errorDiv.innerText = 'Image not found: ' + src.split('/').pop();
            slideDiv.appendChild(errorDiv);
        };
        
        slideDiv.appendChild(img);
        slidesContainer.appendChild(slideDiv);
        
        const indicator = document.createElement('button');
        indicator.onclick = () => goToSlide(index);
        indicator.style.width = '12px';
        indicator.style.height = '12px';
        indicator.style.borderRadius = '50%';
        indicator.style.border = 'none';
        indicator.style.cursor = 'pointer';
        indicator.style.margin = '0 4px';
        indicator.style.backgroundColor = index === 0 ? '#333' : '#ccc';
        indicator.style.transition = 'background-color 0.3s ease';
        indicatorContainer.appendChild(indicator);
    });
}

function goToSlide(index) {
    const slides = document.querySelectorAll('#stocksense-slideshow .slide');
    const indicators = indicatorContainer.children;
    
    if (slides.length === 0) return;
    
    slides[currentSlide].style.display = 'none';
    if (indicators[currentSlide]) {
        indicators[currentSlide].style.backgroundColor = '#ccc';
    }
    
    currentSlide = index;
    slides[currentSlide].style.display = 'block';
    if (indicators[currentSlide]) {
        indicators[currentSlide].style.backgroundColor = '#333';
    }
}

function prevSlide() {
    if (totalSlides === 0) return;
    const newIndex = (currentSlide - 1 + totalSlides) % totalSlides;
    goToSlide(newIndex);
}

function nextSlide() {
    if (totalSlides === 0) return;
    const newIndex = (currentSlide + 1) % totalSlides;
    goToSlide(newIndex);
}

document.addEventListener('DOMContentLoaded', () => {
    initializeSlideshow();
    
    document.addEventListener('keydown', (e) => {
        if (e.key === 'ArrowLeft') {
            prevSlide();
            e.preventDefault();
        }
        if (e.key === 'ArrowRight') {
            nextSlide();
            e.preventDefault();
        }
    });
});
</script>

<style>
#slide-indicator button:hover {
    background-color: #888 !important;
}

button {
    transition: transform 0.2s ease, background-color 0.2s ease;
}

button:hover {
    transform: scale(1.1);
    background-color: white !important;
}

@media (max-width: 768px) {
    .slideshow-section {
        grid-template-columns: 1fr;
    }
    
    #stocksense-slideshow {
        height: 500px;
    }
}
</style>