<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

# Meluza: The Deceptive Machine

A project about a self-centered machine that uses beauty to deceive.

<video controls autoplay muted loop width="100%" style="border-radius: 8px; margin: 2rem 0;">
  <source src="../../videos/Meluza.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Project Introduction

Meluza was born from three simple ideas: a machine that tricks you, a machine that only cares about itself, and a machine designed to be pretty above all else.

Our interest in transparency, both literal and metaphorical, began when we found glasses and started thinking about how things appear versus how they actually work. Using parts from a disassembled MacBook, we built a device that looks attractive and inviting, but behaves in a selfish and deceptive way.

The machine draws you in with its appearance, then frustrates you with messages of rejection and disinterest. It's beautiful, but useless, a mirror that doesn't reflect you back, only its own perfect image.

> **Note:** This documentation is a personal reflexion about the Meluza project. For collaborative context and additional resources, visit:
> 
> **[Full Group Documentation →](https://drive.google.com/drive/folders/1SaJp7rSrbgC6_TBm4SuqNJTPU5xxVxo5?usp=drive_link)**  


## Concept Overview

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0; align-items: start;">
    
<!-- Left Column -->
<div>
        <h3 style="margin-top: 0;">What This Machine Does</h3>
        <div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
            <p>• Invites you to press a button, reels you in, gets your hopes up...</p>
            <p>• Blinds your eyes.</p>
            <p>• Makes you confused.</p>
        </div>
    </div>
    
<!-- Right Column -->
<div>
        <h3 style="margin-top: 0;">What This Machine Does NOT Do</h3>
        <div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
            <p>• Be helpful in any way.</p>
            <p>• Be useful.</p>
            <p>• Reflect your image.</p>
        </div>
    </div>
</div>

Meluza Machine Concept
<img src="../../images/meluza-concept.jpg" 
             alt="Meluza Concept" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover;">

## Design Process

First Prototype
<img src="../../images/prototype.jpg" 
             alt="Prototype" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover;">

Preparing for laser
<img src="../../images/rhino.jpg" 
             alt="Rhino file" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover;">

Iteration Process
<video controls autoplay muted loop width="100%" style="border-radius: 8px; margin: 2rem 0;">
  <source src="../../videos/process.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

### Design Elements

<div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333; margin: 2rem 0;">
    <h3 style="margin-top: 0;">Key Design Components</h3>
    <p><strong>Ultrasonic Sensor HC-SR04</strong> Measures distance to detect when users approach the machine, triggering the deceptive interaction sequence.</p>
    <p><strong>LCD Display 2004 I2C</strong> Shows the machine's selfish messages, inviting users in only to reject them with words like "Ur not worthy to look at me."</p>
    <p><strong>5V recessed LED spotlight with built-in resistor</strong> Creates the blinding light sequence that confuses and disorients users during interaction.</p>
    <p><strong>Protoboard</strong> Used to connect and organize all electronic components.</p>
    <p><strong>Barduino</strong> The main microcontroller that runs the deceptive logic, controlling sensors, lights, and display messages.</p>
    <p><strong>MOSFET IRFZ44N</strong> Controls the power to the bright LEDs, enabling the intense blinking patterns that overwhelm users.</p>
</div>

## Technical Implementation

### System Architecture

Schematic Diagram
<img src="../../images/electric-components.jpg" 
             alt="Electric Components" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover;">

System Diagram 
<img src="../../images/electric-diagram.jpg" 
             alt="Electric Diagram" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover;">

### Coding Logic

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <h2 style="font-size: 1.8rem; font-weight: bold; margin-top: 0;">Flow Chart Sequence</h2>
    
<div style="background: white; padding: 1.5rem; border-radius: 8px; border: 1px solid #ddd; margin-top: 1rem;">
        <ol style="line-height: 2;">
            <li><strong>Baseline:</strong> Stay further than 100cm of Proximity Sensor</li>
            <li><strong>Initial Invitation:</strong> LED Displays: "Come touch my gold button"</li>
            <li><strong>User Interaction:</strong> Press gold button (capacitive touch sensor)</li>
            <li><strong>Initial Feedback:</strong> Green LED turns on (0-25s)</li>
            <li><strong>Secondary Invitation:</strong> LED Displays: "Come look inside my screen" (0-6s)</li>
            <li><strong>Visual Stimulation:</strong> Right LEDs switch on (6-8s)</li>
            <li><strong>Disorientation:</strong> Right LEDs blink quickly [50ms on/off] (8-14s)</li>
            <li><strong>Rejection:</strong> LED Displays: "Ur not worthy to look at me" (14-19s)</li>
            <li><strong>Re-engagement:</strong> LED Displays: "Wanna play again?" (19-25s)</li>
        </ol>
    </div>
</div>

### Pseudocode Implementation

Initialize sensors, LEDs, screen states
trigger = 100cm

loop:
    read distance
    read touch
    
    if not in sequence:
        if distance > trigger: baseline OFF state
        else if distance <= trigger: show "turn me on"
        if touch detected: start sequence
    
    if in sequence:
        small LED blinks continuously
        screen state + LED behavior based on elapsed time:
            0–6s: peek message, strong LEDs off
            6–8s: strong LEDs solid on
            8–14s: strong LEDs fast blink
            14–19s: not worthy message
            19–25s: try again message
    
    if sequence finished: reset everything to OFF

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; margin: 4rem 0; align-items: start;">
    <!-- Left Column: Image -->
    <div>
        <img src="../../images/machine.jpg" 
             alt="The Meluza Machine" 
             width="100%" 
             style="border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); object-fit: cover;">
    </div>
    
    <!-- Right Column: Reflection -->
    <div>
        <h2 style="font-size: 2rem; font-weight: bold; margin-top: 0; color: #222; margin-bottom: 1.5rem;">Reflection on Machine Paradox</h2>
        <div style="font-size: 1.1rem; line-height: 1.7; color: #444;">
            <p style="margin-bottom: 1.5rem;">
                The Machine Paradox project marked a new approach to my work with Arduino. Previously, I had always used it with a clear objective in mind: to create something functional, to solve a problem, or to make a device work efficiently. Meluza challenged that mindset completely. Instead of designing for utility or performance, the goal was to build something intentionally useless—a machine that refuses to cooperate, a device that exists for its own sake.
            </p>
            <p style="margin-bottom: 1.5rem;">
                This shift opened an unexpected kind of creative freedom. Without the pressure to be practical, the process became more playful and experimental. We could explore ideas that might normally feel "wrong," experiment with timing, lights, and messages, and embrace imperfections as part of the character of the machine. The absurdity of a device that prioritizes beauty and deception over function made the process fun, unpredictable, and deeply engaging.
            </p>
        </div>
    </div>
</div>

<!-- Full width paragraph -->
<div style="width: 100%; margin: 2rem 0 4rem 0;">
    <p style="font-size: 1.1rem; line-height: 1.7; color: #444; max-width: 800px; margin: 0 auto; padding: 0 1rem;">
        In the end, Meluza feels complete not because it solves a problem or serves a practical purpose, but because it embodies the concepts it set out to explore: self-centeredness, allure, and the joy of doing nothing. The project reminded me that sometimes the most valuable lessons in design come from letting go of utility and allowing space for creativity, humor, and experimentation.
    </p>
</div>

<!-- Slideshow and Zine Section -->
<div style="display: grid; grid-template-columns: 2fr 1fr; gap: 3rem; margin: 4rem 0; align-items: start;">
    <!-- Left Column: Slideshow -->
    <div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-bottom: 1.5rem;">Project Documentation</h2>
        <div style="position: relative; width: 100%; border-radius: 12px; overflow: hidden; box-shadow: 0 6px 16px rgba(0,0,0,0.1);">
            <!-- Slideshow Container -->
            <div id="meluza-slideshow" style="width: 100%; height: 600px; background: #f0f0f0;">
                <!-- Images will be inserted here by JavaScript -->
            </div>
            
            <!-- Navigation Buttons -->
            <button onclick="prevSlide()" style="position: absolute; top: 50%; left: 1rem; transform: translateY(-50%); background: rgba(255,255,255,0.9); border: none; border-radius: 50%; width: 40px; height: 40px; font-size: 1.5rem; cursor: pointer; display: flex; align-items: center; justify-content: center; z-index: 10;">‹</button>
            <button onclick="nextSlide()" style="position: absolute; top: 50%; right: 1rem; transform: translateY(-50%); background: rgba(255,255,255,0.9); border: none; border-radius: 50%; width: 40px; height: 40px; font-size: 1.5rem; cursor: pointer; display: flex; align-items: center; justify-content: center; z-index: 10;">›</button>
            
            <!-- Slide Indicator -->
            <div id="slide-indicator" style="position: absolute; bottom: 1rem; left: 0; right: 0; display: flex; justify-content: center; gap: 0.5rem; z-index: 10;">
                <!-- Indicators will be generated by JavaScript -->
            </div>
        </div>
        <p style="text-align: center; margin-top: 1rem; color: #666; font-style: italic;">Use arrows to navigate through the project documentation</p>
    </div>
    
    <!-- Right Column: Zine -->
    <div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-bottom: 1.5rem;">Project Zine</h2>
        <div style="border-radius: 12px; overflow: hidden; box-shadow: 0 6px 16px rgba(0,0,0,0.1);">
            <img src="../../images/zine.jpg" 
                 alt="Meluza Project Zine" 
                 width="100%" 
                 style="display: block; object-fit: cover;">
        </div>
        <p style="text-align: center; margin-top: 1rem; color: #666; font-style: italic;">The Meluza project documented in zine format</p>
    </div>
</div>

<script>
// Slideshow functionality
let currentSlide = 0;
const totalSlides = 9; // 1.jpg through 9.jpg
const slideshowContainer = document.getElementById('meluza-slideshow');
const indicatorContainer = document.getElementById('slide-indicator');

// Calculate dimensions for vertical images (105mm x 148.5mm)
// Convert to pixels for web display (assuming ~96 DPI screen)
const mmToPx = 3.7795275591; // 1mm = 3.78px approx
const targetWidth = 105 * mmToPx; // ~397px
const targetHeight = 148.5 * mmToPx; // ~561px

// Initialize slideshow
function initializeSlideshow() {
    // Clear containers
    slideshowContainer.innerHTML = '';
    indicatorContainer.innerHTML = '';
    
    // Create container for centered slides
    const slidesContainer = document.createElement('div');
    slidesContainer.style.width = '100%';
    slidesContainer.style.height = '100%';
    slidesContainer.style.display = 'flex';
    slidesContainer.style.alignItems = 'center';
    slidesContainer.style.justifyContent = 'center';
    slidesContainer.style.background = '#f0f0f0';
    slideshowContainer.appendChild(slidesContainer);
    
    // Create slides
    for (let i = 1; i <= totalSlides; i++) {
        // Create slide wrapper
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
        
        // Create slide image
        const img = document.createElement('img');
        img.src = `../../images/MELUZA/${i}.jpg`;
        img.alt = `Meluza project image ${i}`;
        img.style.width = '100%';
        img.style.height = '100%';
        img.style.objectFit = 'cover';
        
        slideWrapper.appendChild(img);
        slidesContainer.appendChild(slideWrapper);
        
        // Create indicator
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

// Navigation functions
function goToSlide(index) {
    // Hide current slide
    document.getElementById(`slide-wrapper-${currentSlide + 1}`).style.display = 'none';
    // Update indicator
    indicatorContainer.children[currentSlide].style.backgroundColor = '#ccc';
    
    // Update current slide
    currentSlide = index;
    
    // Show new slide
    document.getElementById(`slide-wrapper-${currentSlide + 1}`).style.display = 'flex';
    // Update indicator
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

// Initialize on load
document.addEventListener('DOMContentLoaded', () => {
    initializeSlideshow();
    
    // Add keyboard navigation
    document.addEventListener('keydown', (e) => {
        if (e.key === 'ArrowLeft') prevSlide();
        if (e.key === 'ArrowRight') nextSlide();
    });
});
</script>

<style>
/* Additional styles for the slideshow */
#meluza-slideshow {
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

/* Responsive adjustments */
@media (max-width: 768px) {
    .slideshow-section {
        grid-template-columns: 1fr;
    }
    
    #meluza-slideshow {
        height: 500px;
    }
}
</style>