<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

# Extended Intelligences II: Co-Creative Music Agent

## Project Overview

This project explores a distributed intelligence system where humans and AI collaborate to create music through physical interaction. The system interprets emotional and rhythmic inputs from sensors, processes them through an LLM agent, and generates lyrics, musical references, and light behavior. Despite technical constraints, the project demonstrates how imperfect sensing can still facilitate meaningful co-creative experiences between human and non-human intelligences.

## System Logic

<div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; margin: 4rem 0; align-items: center;">
    
<div>
    <img src="../../images/LLM.png" 
         alt="System Architecture Diagram" 
         width="100%" 
         style="border-radius: 8px; object-fit: cover; box-shadow: 0 4px 20px rgba(0,0,0,0.1);">
</div>

<div>
    <h3 style="margin-top: 0;">Interaction Pipeline:</h3>
    <ol style="line-height: 1.8; padding-left: 1.5rem;">
        <li><strong>Physical Inputs:</strong> Touch (rhythm) + Color (mood)</li>
        <li><strong>AI Interpretation:</strong> LLM maps inputs to emotional tone</li>
        <li><strong>Generative Output:</strong> Original lyrics + YouTube reference</li>
        <li><strong>Physical Feedback:</strong> NeoPixel light patterns</li>
        <li><strong>Closed Loop:</strong> Human responds to generated content</li>
    </ol>
</div>
</div>

## AI Prompting & Agent Behavior

<div class="phrase-screen">
    <div class="phrase-container" id="phraseContainerAgent">
        <!-- Las frases se insertarán aquí dinámicamente -->
    </div>
</div>

<script>
const phrasesAgent = [
    {text: "Agent Architecture", position: "center"},
    {text: "MCP-based sensor interface", position: "top-left"},
    {text: "Color → Mood mapping", position: "top-right"},
    {text: "Rhythm → Lyrical structure", position: "bottom-left"},
    {text: "Cross-domain decision making", position: "bottom-right"},
    {text: "Distributed Intelligence", position: "center"},
    {text: "Human touch as creative input", position: "top-left"},
    {text: "AI as composer & interpreter", position: "top-right"},
    {text: "Hardware as responsive body", position: "bottom-left"},
    {text: "System orchestrator", position: "bottom-right"},
    {text: "Meaning from imperfection", position: "center"}
];

let currentIndexAgent = 0;
const containerAgent = document.getElementById('phraseContainerAgent');

function showNextPhraseAgent() {
    containerAgent.innerHTML = '';
    
    const phraseData = phrasesAgent[currentIndexAgent];
    const phraseElement = document.createElement('div');
    phraseElement.className = `phrase ${phraseData.position}`;
    phraseElement.textContent = phraseData.text;
    
    containerAgent.appendChild(phraseElement);
    
    setTimeout(() => {
        phraseElement.classList.add('active');
    }, 100);
    
    currentIndexAgent = (currentIndexAgent + 1) % phrasesAgent.length;
    setTimeout(showNextPhraseAgent, 3000);
}

document.addEventListener('DOMContentLoaded', () => {
    if (containerAgent) {
        showNextPhraseAgent();
    }
});
</script>

<div style="background-color: #f8f9fa; padding: 2rem; border-radius: 8px; margin: 2rem 0; border-left: 4px solid #4a6fa5;">
    <h4>AI Agent Prompt Logic (Working Implementation):</h4>
    <pre style="background-color: #fff; padding: 1rem; border-radius: 4px; overflow-x: auto; font-size: 0.9rem;">
When user provides color input:
1. Map color to mood spectrum:
   - Red → Passionate/Intense
   - Blue → Melancholic/Calm
   - Green → Hopeful/Growing
   - Yellow → Joyful/Energetic
   - Purple → Mysterious/Introspective

2. Generate lyrics incorporating:
   - Mood-derived emotional tone
   - Randomized rhythmic structure
   - Coherent thematic development

3. Search YouTube for matching song:
   - Similar emotional vibe
   - Compatible musical genre
   - Contemporary relevance

4. Return structured response:
   - Generated lyrics
   - Song recommendation with link
   - NeoPixel light pattern code</pre>
</div>

<div class="carousel-container" style="margin: 3rem 0; padding: 1rem; background-color: #fff; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.05); position: relative;">
    <h4 style="text-align: center; margin-bottom: 1.5rem;">Agent Interactions</h4>
    
    <div class="carousel-wrapper">
        <div class="carousel-slides">
            <div class="carousel-slide active">
                <img src="../../images/Agent1.png" alt="Agent Interaction 1" style="width: 100%; border-radius: 4px; max-height: 400px; object-fit: contain;">
            </div>
            <div class="carousel-slide">
                <img src="../../images/Agent2.png" alt="Agent Interaction 2" style="width: 100%; border-radius: 4px; max-height: 400px; object-fit: contain;">
            </div>
            <div class="carousel-slide">
                <img src="../../images/Agent3.png" alt="Agent Interaction 3" style="width: 100%; border-radius: 4px; max-height: 400px; object-fit: contain;">
            </div>
            <div class="carousel-slide">
                <img src="../../images/Agent4.png" alt="Agent Interaction 4" style="width: 100%; border-radius: 4px; max-height: 400px; object-fit: contain;">
            </div>
            <div class="carousel-slide">
                <img src="../../images/Agent5.png" alt="Agent Interaction 5" style="width: 100%; border-radius: 4px; max-height: 400px; object-fit: contain;">
            </div>
            <div class="carousel-slide">
                <img src="../../images/Agent6.png" alt="Agent Interaction 6" style="width: 100%; border-radius: 4px; max-height: 400px; object-fit: contain;">
            </div>
            <div class="carousel-slide">
                <img src="../../images/Agent7.png" alt="Agent Interaction 7" style="width: 100%; border-radius: 4px; max-height: 400px; object-fit: contain;">
            </div>
        </div>
        
        <button class="carousel-btn prev" onclick="moveSlide(-1)">‹</button>
        <button class="carousel-btn next" onclick="moveSlide(1)">›</button>
        
        <div class="carousel-indicators">
            <span class="indicator active" onclick="currentSlide(0)"></span>
            <span class="indicator" onclick="currentSlide(1)"></span>
            <span class="indicator" onclick="currentSlide(2)"></span>
            <span class="indicator" onclick="currentSlide(3)"></span>
            <span class="indicator" onclick="currentSlide(4)"></span>
            <span class="indicator" onclick="currentSlide(5)"></span>
            <span class="indicator" onclick="currentSlide(6)"></span>
        </div>
    </div>
</div>

<script>
let currentSlideIndex = 0;
const slides = document.querySelectorAll('.carousel-slide');
const indicators = document.querySelectorAll('.indicator');

function showSlide(index) {
    // Asegurarse de que el índice esté dentro del rango
    if (index >= slides.length) {
        currentSlideIndex = 0;
    } else if (index < 0) {
        currentSlideIndex = slides.length - 1;
    } else {
        currentSlideIndex = index;
    }
    
    // Ocultar todas las slides
    slides.forEach(slide => {
        slide.classList.remove('active');
    });
    
    // Remover activo de todos los indicadores
    indicators.forEach(indicator => {
        indicator.classList.remove('active');
    });
    
    // Mostrar slide actual
    slides[currentSlideIndex].classList.add('active');
    
    // Activar indicador actual
    if (indicators[currentSlideIndex]) {
        indicators[currentSlideIndex].classList.add('active');
    }
}

function moveSlide(n) {
    showSlide(currentSlideIndex + n);
}

function currentSlide(n) {
    showSlide(n);
}

// Auto-avance cada 5 segundos
let slideInterval = setInterval(() => {
    moveSlide(1);
}, 5000);

// Pausar auto-avance al interactuar
const carousel = document.querySelector('.carousel-wrapper');
carousel.addEventListener('mouseenter', () => {
    clearInterval(slideInterval);
});

carousel.addEventListener('mouseleave', () => {
    slideInterval = setInterval(() => {
        moveSlide(1);
    }, 5000);
});

// Inicializar
document.addEventListener('DOMContentLoaded', () => {
    showSlide(0);
});
</script>

<style>
.carousel-wrapper {
    position: relative;
    overflow: hidden;
    border-radius: 6px;
}

.carousel-slides {
    display: flex;
    transition: transform 0.5s ease-in-out;
}

.carousel-slide {
    min-width: 100%;
    opacity: 0;
    transition: opacity 0.5s ease;
    display: none;
}

.carousel-slide.active {
    opacity: 1;
    display: block;
}

.carousel-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    font-size: 24px;
    cursor: pointer;
    z-index: 10;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: background-color 0.3s;
}

.carousel-btn:hover {
    background-color: rgba(0, 0, 0, 0.8);
}

.carousel-btn.prev {
    left: 15px;
}

.carousel-btn.next {
    right: 15px;
}

.carousel-indicators {
    position: absolute;
    bottom: 15px;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    gap: 10px;
    z-index: 10;
}

.indicator {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background-color: rgba(255, 255, 255, 0.5);
    cursor: pointer;
    transition: background-color 0.3s;
}

.indicator.active {
    background-color: #4a6fa5;
}

.indicator:hover {
    background-color: rgba(255, 255, 255, 0.8);
}
</style>

## Physical Computing Setup

<div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; margin: 4rem 0; align-items: start;">
    
<div>
    <h3 style="margin-top: 0;">Hardware Components</h3>
    <ul style="line-height: 1.8;">
        <li><strong>Raspberry Pi Pico 2W:</strong> Main controller with WiFi</li>
        <li><strong>Capacitive Copper Strips:</strong> Rhythm detection (touch sensing)</li>
        <li><strong>Color Sensor (TCS34725):</strong> Mood input detection</li>
        <li><strong>NeoPixel LED Strip:</strong> Visual feedback system</li>
        <li><strong>Breadboard & Wiring:</strong> Prototyping infrastructure</li>
    </ul>
    
    <div style="margin-top: 2rem; padding: 1rem; background-color: #f0f0f0; border-radius: 6px;">
        <h4>Working Raspberry Pi Code</h4>
        <pre style="background-color: #fff; padding: 1rem; border-radius: 4px; font-size: 0.8rem; overflow-x: auto;">
import time
import network
from machine import Pin, ADC
from micro_mcp import MCPServer

# Touch sensor on ADC Pin 26
sensor = ADC(Pin(26))

# Debounce settings
DEBOUNCE_SAMPLES = 3
DEBOUNCE_TOLERANCE = 100
SAMPLE_INTERVAL = 0.05

def read_debounced():
    stable_count = 0
    last_stable = None
    
    while stable_count < DEBOUNCE_SAMPLES:
        value = sensor.read_u16()
        if last_stable is None:
            last_stable = value
            stable_count = 1
        elif abs(value - last_stable) <= DEBOUNCE_TOLERANCE:
            stable_count += 1
        else:
            last_stable = value
            stable_count = 1
        time.sleep(SAMPLE_INTERVAL)
    return last_stable

# WiFi connection
wlan = network.WLAN(network.STA_IF)
wlan.active(True)
wlan.connect("Iaac-Wifi", "EnterIaac22@")

# MCP server setup
mcp = MCPServer(name="music-agent", version="1.0.0")

@mcp.tool(
    name="read_touch_sensor",
    description="Read touch sensor state",
    input_schema={"type": "object", "properties": {}}
)
def read_touch_sensor():
    readings = []
    for _ in range(5):
        readings.append(sensor.read_u16())
        time.sleep(0.2)
    zeros = sum(1 for v in readings if v == 0)
    return "Touched" if zeros >= 3 else "Not Touched"

mcp.run(port=8080)</pre>
    </div>
</div>

<div>
    <img src="../../images/raspberry.jpeg" 
         alt="Hardware Setup" 
         width="100%" 
         style="border-radius: 8px; box-shadow: 0 4px 20px rgba(0,0,0,0.1); margin-bottom: 1rem;">
    
    <div style="background-color: #fff5f5; padding: 1.5rem; border-radius: 6px; border-left: 4px solid #e53e3e;">
        <h4>Technical Constraints Encountered:</h4>
        <ul style="margin-bottom: 0;">
            <li>Capacitive sensing limited to binary detection</li>
            <li>Rhythm detection required signal stabilization</li>
            <li>OS compatibility issues with real-time LED control</li>
            <li>Color sensor integration delayed by connectivity problems</li>
            <li>Limited timeframe for calibration and refinement</li>
        </ul>
    </div>
</div>
</div>

## What Worked vs. What Didn't

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 3rem 0;">
    
<div style="background-color: #f0f9f0; padding: 2rem; border-radius: 8px; border: 1px solid #c6f6d5;">
    <h3 style="color: #276749; margin-top: 0;">✅ Successful Implementation</h3>
    <ul style="color: #276749;">
        <li><strong>MCP Architecture:</strong> Stable connection between physical inputs and AI agent</li>
        <li><strong>Prompt Logic:</strong> Effective color-to-mood mapping and lyric generation</li>
        <li><strong>Conceptual Pipeline:</strong> Clear flow from sensor → AI → output → feedback</li>
        <li><strong>Agent Behavior:</strong> AI made coherent cross-domain decisions (emotion, rhythm, visuals, references)</li>
        <li><strong>Distributed Intelligence:</strong> Demonstrated shared agency between human and AI</li>
    </ul>
</div>

<div style="background-color: #fff5f5; padding: 2rem; border-radius: 8px; border: 1px solid #fed7d7;">
    <h3 style="color: #c53030; margin-top: 0;">❌ Limitations & Challenges</h3>
    <ul style="color: #c53030;">
        <li><strong>Sensor Resolution:</strong> Touch detection remained binary, not rhythmic</li>
        <li><strong>Hardware Integration:</strong> NeoPixel and color sensor not fully operational</li>
        <li><strong>Calibration Time:</strong> Signal stability required more development time</li>
        <li><strong>OS Conflicts:</strong> Windows connectivity issues with Raspberry Pi</li>
        <li><strong>Real-time Feedback:</strong> Light patterns not synchronized in final demo</li>
    </ul>
</div>
</div>

## Reflection & Learnings

<div style="background-color: #f8fafc; padding: 2.5rem; border-radius: 8px; margin: 4rem 0; border-left: 5px solid #4c51bf;">
    
    <p style="margin-bottom: 1.5rem; color: #4a5568;">
        This project began as an exploration of shared musical creation between human and AI, where physical interaction—touch, color, movement—would become a language for co-creation. The vision was poetic: an AI that responds not just to words, but to the body's rhythm and the emotion of color.
    </p>
    
    <p style="margin-bottom: 1.5rem; color: #4a5568;">
        In practice, the process revealed something more valuable than technical perfection: the ability of an intelligent system to find meaning in partial, ambiguous, or even broken signals. When capacitive touch resisted nuanced detection, the AI still generated emotionally resonant lyrics from binary input. When color sensing failed, mood mapping continued through fallback logic. The system's intelligence wasn't in flawless execution, but in adaptive interpretation.
    </p>
    
    <p style="margin-bottom: 1.5rem; color: #4a5568;">
        This experience reframed my understanding of Extended Intelligences. True agentic systems don't require perfect sensing or seamless integration. Instead, they thrive in the gaps—interpreting, adapting, and creating coherence from incomplete information. The AI became not just a tool, but a collaborator that could work with whatever signals were available, however imperfect.
    </p>
</div>

<style>
.image-carousel img {
    transition: transform 0.3s ease;
}

.image-carousel img:hover {
    transform: scale(1.02);
}

pre {
    font-family: 'Courier New', monospace;
    line-height: 1.4;
}

ul, ol {
    padding-left: 1.5rem;
}

li {
    margin-bottom: 0.5rem;
}
</style>