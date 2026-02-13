<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

# Nomadic Infrastructure for Urban Microecosystems  
### Individual Reflective Post  

<img src="../../images/nomadic1.jpg" 
     alt="Nomadic Infrastructure concept" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

## Project Introduction  

This project started from a discomfort. Cities are designed almost exclusively for humans. Shade, ventilation, mobility, comfort, protection. All optimized for us. Meanwhile, insects and small organisms experience the city as an unstable and often hostile territory. Heat accumulates, soil dries out, surfaces radiate temperature, and exposure shifts constantly throughout the day.

At first I was thinking in terms of shelter. How can we design protective spaces for non‑human species? But that logic felt static. The city is not static. Environmental hostility moves. Shade disappears. Pavement heats up. Moisture evaporates. So the question changed. What if infrastructure could move in response?

Inspired by walking mechanisms like the Strandbeest system, the project shifted from object to organism. Instead of designing a container, we designed something that senses and reacts. The idea became less about protection and more about mobility as survival.

> **Note:** This documentation is a personal reflection. For collaborative context and full technical details, visit:  
> **[Full Group Documentation on Hackster →](https://www.hackster.io/antoniogarciafernandez/nomadic-infrastructure-for-urban-microecosistems-b799ea)**  

---

## 1. Cognitive Trace  

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">Trying to design from a non‑human perspective exposed a limitation. We cannot fully understand how insects experience temperature or dryness. What we can do is translate environmental variables into measurable signals. Soil humidity, light intensity, temperature. These become proxies for discomfort. It is an imperfect translation, but it makes response possible.</p>
</div>

<img src="../../images/nomadic2.jpg" 
     alt="Cognitive mapping" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 2. Moral Trace  

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">Designing for other species is not neutral. There is an ethical tension in deciding what conditions are “better” and when movement should happen. We defined the thresholds. We determined when the environment becomes hostile. That means the autonomy of the artifact is always framed by human assumptions.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">At the same time, cities distribute vulnerability unevenly. Some species can escape heat or dryness. Others cannot. This project explores whether mobility can act as a small redistribution mechanism. It does not fix urban injustice, but it tries to create a moving pocket of survivability.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">Another question that stayed with me is intervention versus coexistence. Are we supporting life, or are we imposing another layer of artificial control? The artifact carries living matter. That responsibility changes how I think about design. It becomes less about performance and more about care.</p>
</div>

<img src="../../images/nomadic3.jpg" 
     alt="Ethical considerations" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 3. Technical and Process Trace  

### Mechanical system  

We built a 12‑leg walking structure based on the Theo Jansen mechanism. The assembly was much more delicate than expected. The system is extremely precise. If one screw is slightly misaligned or tightened too much, the whole walking pattern collapses. Precision is not aesthetic here, it is structural necessity.

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0;">
    <img src="../../images/nomadic4.jpg" 
         alt="Mechanical assembly" 
         width="100%" 
         style="border-radius: 8px; object-fit: cover;">
    <img src="../../images/nomadic5.jpg" 
         alt="Leg mechanism detail" 
         width="100%" 
         style="border-radius: 8px; object-fit: cover;">
</div>

During the time we had, the servo motors did not function as they should. They were not strong or synchronized enough to properly activate the mechanism under the weight of the terrarium. Because the model we chose is so sensitive, any small mechanical inconsistency amplified the failure. This revealed something important. When you miniaturize complex walking systems, tolerances become critical. We now know that we need to modify the transmission system and possibly rethink torque and structural reinforcement.

Failure here was informative. It showed that mechanical ecosystems are fragile assemblies.

### Sensing and electronics  

We integrated three sensors: soil moisture, light sensitivity through an LDR, and temperature and humidity with the DHT11. These sensors feed the ESP32 and determine when the motors should activate.

<div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333; margin: 2rem 0;">
    <h3 style="margin-top: 0;">Sensor logic</h3>
    <p>The challenge was not only wiring and coding, but deciding the logic. What counts as too dry? Too hot? Too exposed? Those thresholds are design decisions disguised as technical parameters.</p>
    <p>The movement itself is reactive and simple. The artifact does not navigate intelligently. It moves when conditions exceed limits. It searches blindly. In that sense it behaves more like a primitive organism than a robot.</p>
</div>

<img src="../../images/nomadic6.jpg" 
     alt="Electronics and sensors" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

### Terrarium integration  

We designed and laser cut a terrarium in MDF to host soil, moss and worms. Integrating living matter into a moving structure introduced new constraints. Weight distribution, vibration, ventilation. The more we stabilized the ecosystem, the harder it became to move it.

<img src="../../images/nomadic7.jpg" 
     alt="Terrarium design" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 4. Review and Future Direction  

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">Today, February 13, we had a review session with Grandeza Studio. Their feedback shifted the scale of the project. They suggested thinking beyond a single artifact and imagining how these systems could function in the future as ecological corridors.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">That idea expanded the scope. Instead of isolated moving microecosystems, what if multiple units could operate across the city? What if each one hosted different microhabitats? Some optimized for humidity‑dependent organisms, others for pollinators, others for decomposers. Together they could form a distributed network of moving ecological infrastructure.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">This reframes the artifact from prototype to speculative infrastructure model. It becomes less about one walking object and more about how cities could integrate nomadic ecological support systems.</p>
</div>

<img src="../../images/nomadic8.jpg" 
     alt="Future vision" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 5. What This Prototype Is  

<div style="background: #ffffff; padding: 2rem; border-radius: 8px; border-left: 4px solid #333; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">This is not a finished solution. It is a working question. Can infrastructure become mobile care? Can mechanical systems redistribute environmental conditions?</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The fact that the motors failed to perform properly is part of the narrative. It reveals the complexity of translating ecological ideas into mechanical reality. Precision matters. Energy matters. Weight matters. Care is not abstract. It is mechanical.</p>
</div>

---

## 6. Next Steps  

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0;">
    <div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
        <h3 style="margin-top: 0;">If we continue developing this project, the priorities would be:</h3>
        <ul style="line-height: 1.8;">
            <li>Redesigning the motor system to increase torque and reliability</li>
            <li>Adjusting the mechanical tolerances of the walking structure</li>
            <li>Improving sensor calibration</li>
            <li>Adding directional logic instead of simple reactive movement</li>
        </ul>
    </div>
    <div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
        <h3 style="margin-top: 0;">Further exploration:</h3>
        <ul style="line-height: 1.8;">
            <li>Exploring solar power for greater autonomy</li>
            <li>Researching specific species requirements more rigorously</li>
            <li>Developing a network model of multiple mobile microecosystems functioning as ecological corridors</li>
        </ul>
    </div>
</div>

---

<!-- Slideshow Gallery (nomadic images) -->
<div style="display: grid; grid-template-columns: 2fr 1fr; gap: 3rem; margin: 4rem 0; align-items: start;">
    <!-- Left Column: Slideshow -->
    <div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-bottom: 1.5rem;">Project Gallery</h2>
        <div style="position: relative; width: 100%; border-radius: 12px; overflow: hidden; box-shadow: 0 6px 16px rgba(0,0,0,0.1);">
            <!-- Slideshow Container -->
            <div id="nomadic-slideshow" style="width: 100%; height: 600px; background: #f0f0f0;">
                <!-- Images will be inserted by JavaScript -->
            </div>
            
            <!-- Navigation Buttons -->
            <button onclick="prevSlide()" style="position: absolute; top: 50%; left: 1rem; transform: translateY(-50%); background: rgba(255,255,255,0.9); border: none; border-radius: 50%; width: 40px; height: 40px; font-size: 1.5rem; cursor: pointer; display: flex; align-items: center; justify-content: center; z-index: 10;">‹</button>
            <button onclick="nextSlide()" style="position: absolute; top: 50%; right: 1rem; transform: translateY(-50%); background: rgba(255,255,255,0.9); border: none; border-radius: 50%; width: 40px; height: 40px; font-size: 1.5rem; cursor: pointer; display: flex; align-items: center; justify-content: center; z-index: 10;">›</button>
            
            <!-- Slide Indicator -->
            <div id="slide-indicator" style="position: absolute; bottom: 1rem; left: 0; right: 0; display: flex; justify-content: center; gap: 0.5rem; z-index: 10;">
                <!-- Indicators will be generated by JavaScript -->
            </div>
        </div>
        <p style="text-align: center; margin-top: 1rem; color: #666; font-style: italic;">Use arrows to navigate through project images</p>
    </div>
    
    <!-- Right Column: Schematic / Diagram -->
    <div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-bottom: 1.5rem;">System Diagram</h2>
        <div style="border-radius: 12px; overflow: hidden; box-shadow: 0 6px 16px rgba(0,0,0,0.1);">
            <img src="../../images/nomadic9.jpg" 
                 alt="Nomadic system diagram" 
                 width="100%" 
                 style="display: block; object-fit: cover;">
        </div>
        <p style="text-align: center; margin-top: 1rem; color: #666; font-style: italic;">Schematic of sensors, ESP32, and motor control</p>
    </div>
</div>

<script>
// Slideshow functionality (adapted for nomadic images)
let currentSlide = 0;
const totalSlides = 5; // nomadic1.jpg to nomadic5.jpg (adjust as needed)
const slideshowContainer = document.getElementById('nomadic-slideshow');
const indicatorContainer = document.getElementById('slide-indicator');

// Dimensions for vertical images (105mm x 148.5mm) – same as original
const mmToPx = 3.7795275591;
const targetWidth = 105 * mmToPx; // ~397px
const targetHeight = 148.5 * mmToPx; // ~561px

// Initialize slideshow
function initializeSlideshow() {
    slideshowContainer.innerHTML = '';
    indicatorContainer.innerHTML = '';
    
    const slidesContainer = document.createElement('div');
    slidesContainer.style.width = '100%';
    slidesContainer.style.height = '100%';
    slidesContainer.style.display = 'flex';
    slidesContainer.style.alignItems = 'center';
    slidesContainer.style.justifyContent = 'center';
    slidesContainer.style.background = '#f0f0f0';
    slideshowContainer.appendChild(slidesContainer);
    
    for (let i = 1; i <= totalSlides; i++) {
        const slideWrapper = document.createElement('div');
        slideWrapper.id = `slide-wrapper-${i}`;
        slideWrapper.style.width = `${targetWidth}px`;
        slideWrapper.style.height = `${targetHeight}px`;
        slideWrapper.style.display = i === 1 ? 'flex' : 'none';
        slideWrapper.style.alignItems = 'center';
        slideWrapper.style.justifyContent = 'center';
        slideWrapper.style.overflow = 'hidden';
        slideWrapper.style.borderRadius = '4px';
        slideWrapper.style.boxShadow = '0 2px 8px rgba(0,0,0,0.2)';
        
        const img = document.createElement('img');
        img.src = `../../images/nomadic${i}.jpg`;
        img.alt = `Nomadic project image ${i}`;
        img.style.width = '100%';
        img.style.height = '100%';
        img.style.objectFit = 'cover';
        
        slideWrapper.appendChild(img);
        slidesContainer.appendChild(slideWrapper);
        
        const indicator = document.createElement('button');
        indicator.onclick = () => goToSlide(i - 1);
        indicator.style.width = '10px';
        indicator.style.height = '10px';
        indicator.style.borderRadius = '50%';
        indicator.style.border = 'none';
        indicator.style.cursor = 'pointer';
        indicator.style.backgroundColor = i === 1 ? '#333' : '#ccc';
        indicator.style.transition = 'background-color 0.3s ease';
        indicatorContainer.appendChild(indicator);
    }
}

// Navigation functions (same as original)
function goToSlide(index) {
    document.getElementById(`slide-wrapper-${currentSlide + 1}`).style.display = 'none';
    indicatorContainer.children[currentSlide].style.backgroundColor = '#ccc';
    
    currentSlide = index;
    
    document.getElementById(`slide-wrapper-${currentSlide + 1}`).style.display = 'flex';
    indicatorContainer.children[currentSlide].style.backgroundColor = '#333';
}

function prevSlide() {
    const newIndex = (currentSlide - 1 + totalSlides) % totalSlides;
    goToSlide(newIndex);
}

function nextSlide() {
    const newIndex = (currentSlide + 1) % totalSlides;
    goToSlide(newIndex);
}

// Initialize on load and add keyboard navigation
document.addEventListener('DOMContentLoaded', () => {
    initializeSlideshow();
    
    document.addEventListener('keydown', (e) => {
        if (e.key === 'ArrowLeft') prevSlide();
        if (e.key === 'ArrowRight') nextSlide();
    });
});
</script>

<style>
/* Additional styles (preserved from original) */
#nomadic-slideshow {
    display: flex;
    align-items: center;
    justify-content: center;
}

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
    
    #nomadic-slideshow {
        height: 500px;
    }
}
</style>