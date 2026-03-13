<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

# StockSense
### Individual Reflective Post

<img src="../../images/orgies.jpeg" 
     alt="StockSense wearable prototype" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

## Project Introduction

This project explored the possibility of communication between two different forms of intelligence. From the beginning, our intention was to connect human perception with environmental intelligence something closer to ecological signals or non human systems. However, finding reliable real time environmental data streams and integrating them within the short timeframe proved difficult. As a result, we pivoted toward the stock market as a data source. While this shift initially felt like a compromise, it allowed us to test the core idea of the project: translating complex data from a collective system into somatic signals that the body can perceive. In that sense, the stock market became a proxy for testing how two different intelligences human and systemic might communicate.

> **Note:** This documentation is a personal reflection. For collaborative context and full technical details, visit:
> **[Full Group Documentation on Hackster.io →](https://www.hackster.io/545047/stocksense-610f0b)**

---

## 1. Cognitive Trace

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">One of the main cognitive traces for me was realizing that we had to accept the limits of what could realistically be achieved in a week. Our initial intention was to connect the wearable to environmental intelligence, but integrating those data streams and building the system in such a short timeframe proved too complex. Instead of forcing an incomplete solution, we decided to compromise and use the stock market API as a working data stream. This allowed us to focus on testing the core idea of the project: translating data from an external system into haptic signals that the body can perceive. In that sense, the project became a first prototype that helps me explore how environmental signals could eventually be translated into sensory experiences that humans can feel and respond to.</p>
</div>

<img src="../../images/orgies2.png" 
     alt="Cognitive mapping process" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 2. Moral Trace

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">Another important process trace was how collaboration unfolded in practice. In theory, the fastest strategy would have been to divide tasks and work in parallel. However, both of us wanted to learn every part of the process from soldering to coding to system integration so we intentionally avoided strict specialization. This created moments where efficiency slowed down. For example, soldering motors cannot realistically be done by two people at once, and when we were working on the platform most of the coding happened on a single computer. At times this meant that one person was actively building while the other observed, asked questions, and tried to understand the logic. While slower, this process made the learning experience more shared and transparent.</p>
</div>

<img src="../../images/orgies3.png" 
     alt="Ethical considerations" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 3. Technical Trace

### Material and Mechanical Decisions

We became very excited about the idea of embedding the motors in silicone to create a polished wearable artifact. However, this decision also consumed much more time and material than we anticipated. At one point the silicone failed to cure overnight, which forced us to remove everything and start again with a faster curing material. Because we ran out of both time and silicone, the artifact ultimately shifted from the vest we initially envisioned to something closer to a collar like chest piece. Although this began as a constraint, it ended up shaping the final narrative of the project and its visual identity.

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0;">
    <img src="../../images/orgies4.png" 
         alt="Motor assembly" 
         width="100%" 
         style="border-radius: 8px; object-fit: cover;">
    <img src="../../images/orgies5.png" 
         alt="Silicone molding process" 
         width="100%" 
         style="border-radius: 8px; object-fit: cover;">
</div>


### System Architecture

We built a system that translates real time stock data into haptic patterns across nine motors arranged in a 3x3 grid on the chest. The data flows from a stock market API through Node RED, then via MQTT protocol to a Raspberry Pi Pico W, which controls the vibration intensity and patterns of each motor individually.

<div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333; margin: 2rem 0;">
    <h3 style="margin-top: 0;">Technical Challenges</h3>
    <p>The most persistent challenge was connectivity. We spent hours troubleshooting why the Raspberry Pi Pico W would not connect to WiFi, only to realize that moving to a different room with better signal solved the problem. Another universal fix that worked was simply unplugging and replugging the device. These small moments of frustration became lessons in how infrastructure physical and digital is never as seamless as it appears.</p>
</div>

<img src="../../images/orgies6.png" 
     alt="System diagram" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 4. Review and Future Direction

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">The project is not a finished artifact but a working prototype that opens new questions. The wearable, the data translation pipeline, and the platform together demonstrate a possible framework for somatic interfaces that communicate complex systems through the body. For me personally, this prototype is especially valuable because it establishes a technical and conceptual foundation that I can later adapt toward environmental sensing and ecological intelligence the direction that originally motivated the project.</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The collar form, also took on new meaning through this process. What began as an accident of material constraints became somehow part of the narrative.</p>
</div>

<img src="../../images/orgies7.jpeg" 
     alt="Future vision" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

---

## 5. What This Prototype Is

<div style="background: #ffffff; padding: 2rem; border-radius: 8px; border-left: 4px solid #333; margin: 2rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7;">This is not a finished product. It is a working question. Can we build interfaces that let the body perceive abstract systems directly?</p>
    <p style="font-size: 1.1rem; line-height: 1.7; margin-top: 1rem;">The fact that we pivoted from ecological to financial data is part of the narrative. It reveals how infrastructure choices, data availability, API reliability, time constraints shape what becomes possible. The project is as much about these constraints as it is about the final artifact.</p>
</div>

---

## 6. Next Steps

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0;">
    
    <div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
        <h3 style="margin-top: 0;">If we continue developing this project, the priorities would be:</h3>
        <ul style="line-height: 1.8;">
            <li>Exploring different materials, for example, agar agar</li>
            <li>Creating a proper pouch for the microcontroller and battery in the back</li>
            <li>Refining the aesthetic to more closely resemble an Usekh collar</li>
            <li>Testing different body placements to optimize tactile perception based on two point discrimination maps</li>
        </ul>
    </div>
    
    <div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
        <h3 style="margin-top: 0;">Further exploration:</h3>
        <p>The next layer of development would focus on the data sources themselves.</p>
        <ul style="line-height: 1.8;">
            <li>Reconnecting to the original intention of environmental data streams</li>
            <li>Exploring visual tracking of animal movements using OpenCV as an alternative data source</li>
            <li>Developing more nuanced haptic vocabularies that differentiate between types of change (rate, direction, volatility)</li>
        </ul>
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
            <img src="../../images/orgies8.png" 
                 alt="StockSense system diagram" 
                 width="100%" 
                 style="display: block; object-fit: cover;">
        </div>
    </div>
</div>

<script>
// Slideshow functionality
let currentSlide = 0;

// Define images
const slideImages = [
    "../../images/orgies9.png",
    "../../images/orgies10.png",
    "../../images/orgies11.png",
    "../../images/orgies12.png",
    "../../images/orgies13.png",
    "../../images/orgies14.jpeg"
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
        img.alt = `StockSense project image ${index + 1}`;
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