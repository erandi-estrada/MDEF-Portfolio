<!-- Ya tienes el menú, así que continúo con el contenido de la página -->
<div class="content-container">
    
    <h1>Extended Intelligences II</h1>
    
    <div class="intro-section" style="margin: 2rem 0 3rem 0;">
        <p style="font-size: 1.1rem; line-height: 1.6; color: #444;">
            This module explored the design of agentic systems that connect physical computing with artificial intelligence, 
            creating distributed intelligences across digital and material domains. The challenge was to build a meaningful 
            interface between human input, AI interpretation, and physical response—not as tools, but as collaborative agents.
        </p>
    </div>

    <!-- Project Overview -->
    <div class="section" style="margin-bottom: 4rem;">
        <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">Project Overview</h2>
        
        <div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; margin: 2rem 0; align-items: start;">
            <div>
                <p style="margin-bottom: 1rem; line-height: 1.6;">
                    <strong>Human + AI Co-creative Music Agent:</strong> A system where physical touch and color become a language for 
                    musical co-creation with an AI agent. The user provides rhythmic input through touch and emotional tone through 
                    color, which the AI interprets to generate lyrics, suggest musical references, and orchestrate light behavior.
                </p>
                <p style="margin-bottom: 1rem; line-height: 1.6;">
                    The project reimagines musical composition as a distributed intelligence—neither fully human nor fully artificial, 
                    but emerging through the interaction between physical sensing, AI interpretation, and atmospheric feedback.
                </p>
            </div>
            <div style="background-color: #f8f9fa; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #6c5ce7;">
                <h4 style="margin-top: 0; color: #6c5ce7;">Core Architecture</h4>
                <p style="margin-bottom: 0.5rem; font-size: 0.95rem;">
                    • Physical Inputs (touch, color) → MCP Server<br>
                    • LLM Interpretation (mood, rhythm analysis)<br>
                    • Generative Output (lyrics, song references)<br>
                    • Physical Feedback (NeoPixel light patterns)<br>
                    • Continuous loop of interpretation and response
                </p>
            </div>
        </div>
    </div>

    <!-- System Logic -->
    <div class="section" style="margin-bottom: 4rem;">
        <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">System Logic & Pipeline</h2>
        
        <div style="background-color: #fff; border-radius: 10px; padding: 2rem; margin: 2rem 0; border: 1px solid #e0e0e0; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">
            <div style="text-align: center; margin-bottom: 2rem;">
                <h4 style="color: #2d3436; margin-bottom: 1.5rem;">Interaction Pipeline</h4>
                <div style="display: inline-block; text-align: left; position: relative;">
                    <div style="display: flex; flex-direction: column; align-items: center; gap: 2rem;">
                        <!-- Step 1 -->
                        <div style="display: flex; align-items: center; gap: 1rem;">
                            <div style="background-color: #6c5ce7; color: white; width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: bold;">1</div>
                            <div style="padding: 1rem 1.5rem; background-color: #f8f9fa; border-radius: 8px; min-width: 200px;">
                                <strong>User Input</strong><br>
                                Touch (rhythm) + Color (mood)
                            </div>
                        </div>
                        
                        <!-- Arrow -->
                        <div style="font-size: 1.5rem; color: #6c5ce7;">↓</div>
                        
                        <!-- Step 2 -->
                        <div style="display: flex; align-items: center; gap: 1rem;">
                            <div style="background-color: #00b894; color: white; width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: bold;">2</div>
                            <div style="padding: 1rem 1.5rem; background-color: #f8f9fa; border-radius: 8px; min-width: 200px;">
                                <strong>AI Agent</strong><br>
                                Mood + rhythm interpretation
                            </div>
                        </div>
                        
                        <!-- Arrow -->
                        <div style="font-size: 1.5rem; color: #00b894;">↓</div>
                        
                        <!-- Step 3 -->
                        <div style="display: flex; align-items: center; gap: 1rem;">
                            <div style="background-color: #fd79a8; color: white; width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: bold;">3</div>
                            <div style="padding: 1rem 1.5rem; background-color: #f8f9fa; border-radius: 8px; min-width: 200px;">
                                <strong>Lyrics Generation</strong><br>
                                + Song reference (YouTube)
                            </div>
                        </div>
                        
                        <!-- Arrow -->
                        <div style="font-size: 1.5rem; color: #fd79a8;">↓</div>
                        
                        <!-- Step 4 -->
                        <div style="display: flex; align-items: center; gap: 1rem;">
                            <div style="background-color: #fdcb6e; color: white; width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: bold;">4</div>
                            <div style="padding: 1rem 1.5rem; background-color: #f8f9fa; border-radius: 8px; min-width: 200px;">
                                <strong>Light Behavior</strong><br>
                                NeoPixel pattern generation
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; margin-top: 2rem;">
                <div>
                    <h4 style="color: #2d3436;">What Actually Worked</h4>
                    <ul style="padding-left: 1.2rem; line-height: 1.6;">
                        <li>MCP-based architecture connecting physical inputs to AI agent</li>
                        <li>Prompt logic interpreting color as emotional mood</li>
                        <li>Mapping mood → lyrical tone and narrative structure</li>
                        <li>Randomized rhythm pattern generation from touch input</li>
                        <li>Matching generated lyrics to existing musical references</li>
                        <li>Conceptual pipeline from sensor → interpretation → generative output</li>
                    </ul>
                </div>
                <div>
                    <h4 style="color: #2d3436;">What Didn't Fully Materialize</h4>
                    <ul style="padding-left: 1.2rem; line-height: 1.6;">
                        <li>Capacitive touch sensor reached only binary detection (touched/not touched)</li>
                        <li>Complex rhythm detection required signal stability beyond available time</li>
                        <li>OS and connectivity issues limited real-time deployment to NeoPixel LEDs</li>
                        <li>Color sensor integration remained at conceptual stage</li>
                        <li>Full hardware-software feedback loop couldn't be closed in timeframe</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <!-- AI Prompting & Agent Behavior -->
    <div class="section" style="margin-bottom: 4rem;">
        <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">AI Prompting & Agent Behavior</h2>
        
        <div style="margin-bottom: 3rem;">
            <p style="margin-bottom: 1.5rem; line-height: 1.6;">
                The AI agent was designed to act as an interpretive composer—translating abstract physical inputs 
                into musical and lyrical outputs. Rather than simply reacting, it made creative decisions across 
                emotional, rhythmic, and atmospheric domains.
            </p>
            
            <div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0;">
                <div style="background-color: #f8f9fa; border-radius: 8px; padding: 1.5rem; border: 1px solid #e0e0e0;">
                    <h4 style="margin-top: 0; color: #6c5ce7;">Example Prompt Structure</h4>
                    <div style="background-color: #2d3436; color: #dfe6e9; padding: 1rem; border-radius: 5px; font-family: monospace; font-size: 0.85rem; overflow-x: auto;">
                        <code>
                            User input: Color=Blue (mood: melancholic), Touch pattern=slow, irregular<br>
                            Task: Generate lyrics reflecting melancholic mood with slow, irregular rhythm<br>
                            Additional: Suggest a YouTube song matching this atmosphere<br>
                            Output format: Lyrics + Song reference + Light pattern code for NeoPixel
                        </code>
                    </div>
                </div>
                <div style="background-color: #f8f9fa; border-radius: 8px; padding: 1.5rem; border: 1px solid #e0e0e0;">
                    <h4 style="margin-top: 0; color: #00b894;">Sample AI Output</h4>
                    <div style="padding: 0.5rem; line-height: 1.5; font-style: italic;">
                        "The rain falls in uneven beats,<br>
                        Like memories on windowpanes...<br>
                        <br>
                        Song reference: 'River Flows in You' by Yiruma<br>
                        Light pattern: Slow blue pulses with occasional white flickers"
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Placeholder for screenshot - you'll need to add your actual image -->
        <div style="text-align: center; margin: 3rem 0;">
            <div style="background-color: #f1f2f6; border: 2px dashed #a4b0be; border-radius: 8px; padding: 3rem; margin-bottom: 1rem;">
                <p style="color: #747d8c; margin: 0;">[Screenshot of AI prompt interface and outputs]</p>
                <p style="color: #a4b0be; font-size: 0.9rem; margin-top: 0.5rem;">Replace with your actual screenshot</p>
            </div>
            <p style="font-size: 0.9rem; color: #666;">Example of the AI agent interpreting physical inputs and generating creative outputs</p>
        </div>
    </div>

    <!-- Physical Computing Setup -->
    <div class="section" style="margin-bottom: 4rem;">
        <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">Physical Computing Setup</h2>
        
        <p style="margin-bottom: 2rem; line-height: 1.6;">
            The hardware infrastructure was built around a Raspberry Pi Pico 2W, with capacitive touch sensing 
            and NeoPixel LED control. Despite technical constraints, the setup demonstrates how physical and 
            digital intelligences can be architecturally connected.
        </p>
        
        <div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0;">
            <div>
                <h4 style="margin-bottom: 1rem;">Hardware Components</h4>
                <ul style="padding-left: 1.2rem; line-height: 1.6;">
                    <li>Raspberry Pi Pico 2W (MicroPython)</li>
                    <li>Capacitive copper strip touch sensor</li>
                    <li>NeoPixel LED strip (WS2812B)</li>
                    <li>Breadboard and wiring infrastructure</li>
                    <li>Color sensor (conceptual/planned)</li>
                </ul>
                
                <div style="margin-top: 2rem; background-color: #fff8e1; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #ffb300;">
                    <h5 style="margin-top: 0; color: #ff8f00;">Code Structure (MCP Server)</h5>
                    <pre style="background-color: #2d3436; color: #dfe6e9; padding: 1rem; border-radius: 5px; font-size: 0.8rem; overflow-x: auto;">
import time
import network
from machine import Pin, ADC
from micro_mcp import MCPServer

# Touch sensor setup
sensor = ADC(Pin(26))

# MCP server for AI agent communication
mcp = MCPServer(name="music-agent", version="1.0.0")

@mcp.tool(
    name="read_touch_sensor",
    description="Read touch sensor state.",
    input_schema={"type": "object", "properties": {}, "required": []}
)
def read_touch_sensor():
    readings = []
    for _ in range(5):
        readings.append(sensor.read_u16())
        time.sleep(0.2)
    zeros = sum(1 for v in readings if v == 0)
    return "Touched" if zeros >= 3 else "Not Touched"

# Start server
mcp.run(port=8080)</pre>
                </div>
            </div>
            
            <div>
                <!-- Placeholder for hardware photos - you'll need to add your actual images -->
                <div style="background-color: #f1f2f6; border: 2px dashed #a4b0be; border-radius: 8px; padding: 2rem; margin-bottom: 1rem; height: 200px; display: flex; align-items: center; justify-content: center;">
                    <p style="color: #747d8c; text-align: center;">[Photo of Raspberry Pi Pico setup with capacitive sensor]</p>
                </div>
                <div style="background-color: #f1f2f6; border: 2px dashed #a4b0be; border-radius: 8px; padding: 2rem; margin-top: 1rem; height: 200px; display: flex; align-items: center; justify-content: center;">
                    <p style="color: #747d8c; text-align: center;">[Photo of NeoPixel LED strip and wiring]</p>
                </div>
            </div>
        </div>
    </div>

    <!-- Why This Fits Extended Intelligences II -->
    <div class="section" style="margin-bottom: 4rem; background-color: #f8f9fa; padding: 2rem; border-radius: 10px;">
        <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">Why This Fits Extended Intelligences II</h2>
        
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1.5rem; margin-top: 1.5rem;">
            <div style="background-color: white; padding: 1.5rem; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.05);">
                <h4 style="color: #6c5ce7; margin-top: 0;">Distributed Intelligence</h4>
                <p>The system demonstrates intelligence distributed across human touch, AI interpretation, and hardware response—no single component "owns" the creative process.</p>
            </div>
            
            <div style="background-color: white; padding: 1.5rem; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.05);">
                <h4 style="color: #00b894; margin-top: 0;">Interpretive, Not Reactive</h4>
                <p>The AI agent interprets abstract inputs (color=mood, touch=rhythm) rather than simply reacting to signals, exercising creative agency across domains.</p>
            </div>
            
            <div style="background-color: white; padding: 1.5rem; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.05);">
                <h4 style="color: #fd79a8; margin-top: 0;">Agentic Decision-Making</h4>
                <p>The system makes decisions across emotion, rhythm, visuals, and musical references—demonstrating multi-domain agency rather than single-function automation.</p>
            </div>
            
            <div style="background-color: white; padding: 1.5rem; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.05);">
                <h4 style="color: #fdcb6e; margin-top: 0;">Meaning from Constraints</h4>
                <p>The project shows that intelligence in physical systems doesn't require perfect sensing—meaningful interaction emerges from partial, abstract, or even broken inputs.</p>
            </div>
        </div>
    </div>

    <!-- Reflection & Learnings -->
    <div class="section" style="margin-bottom: 4rem;">
        <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">Reflection & Learnings</h2>
        
        <div class="two-column-layout" style="display: grid; grid-template-columns: 2fr 1fr; gap: 3rem; margin: 2rem 0;">
            <div>
                <p style="line-height: 1.7; margin-bottom: 1.5rem;">
                    This project began as an exploration of shared musical creation between human and AI, where physical interaction 
                    would directly shape sound, mood, and atmosphere. The vision was elegant: touch and color becoming a language 
                    for co-creation, with the AI responding through lyrics, music references, and light.
                </p>
                
                <p style="line-height: 1.7; margin-bottom: 1.5rem;">
                    In practice, it became a lesson in friction and negotiation. Working within tight constraints—both temporal and 
                    technical—meant that many envisioned interactions remained incomplete. The capacitive sensor delivered only 
                    binary readings rather than nuanced rhythm detection. OS conflicts prevented real-time LED control. The color 
                    sensor never made it past the conceptual stage.
                </p>
                
                <p style="line-height: 1.7; margin-bottom: 1.5rem;">
                    Yet this very incompleteness revealed something more interesting: that intelligence in hybrid systems isn't 
                    about technical perfection, but about meaning-making within constraints. The AI agent didn't need perfect 
                    rhythm detection to generate compelling lyrics. It didn't need calibrated color sensing to interpret emotional 
                    tone. It worked with what it had—partial, abstract, sometimes broken inputs—and still created coherent, 
                    atmospheric outputs.
                </p>
                
                <p style="line-height: 1.7;">
                    This project taught me that agentic systems thrive not despite their limitations, but through them. The gaps 
                    between intention and implementation become spaces for improvisation and reinterpretation. What began as a 
                    technical challenge became a conceptual insight: intelligence in physical computing isn't something we build 
                    perfectly and then deploy—it's something that emerges, unevenly and unexpectedly, from the dialogue between 
                    human intention, material constraints, and algorithmic interpretation.
                </p>
            </div>
            
            <div style="background-color: #f8f9fa; padding: 2rem; border-radius: 8px; border-top: 4px solid #6c5ce7;">
                <h4 style="margin-top: 0; color: #6c5ce7;">Key Insights</h4>
                <ul style="padding-left: 1.2rem; line-height: 1.6;">
                    <li>Agentic systems make meaning from partial data</li>
                    <li>Technical constraints can drive creative interpretation</li>
                    <li>Intelligence is distributed across the system, not localized</li>
                    <li>Failure modes become part of the system's "personality"</li>
                    <li>Human-AI collaboration emerges through negotiation, not control</li>
                </ul>
                
                <div style="margin-top: 2rem; padding-top: 1.5rem; border-top: 1px solid #e0e0e0;">
                    <h5 style="color: #2d3436;">Technical Realizations</h5>
                    <p style="font-size: 0.9rem; line-height: 1.5;">
                        MCP architecture successfully connected physical and digital domains. Prompt engineering enabled 
                        meaningful interpretation of abstract inputs. Hardware limitations redirected focus to conceptual 
                        robustness over technical perfection.
                    </p>
                </div>
            </div>
        </div>
    </div>

</div>

<!-- Frases animadas al final (similar a tus otras páginas) -->
<div class="phrase-screen" style="margin-top: 4rem;">
    <div class="phrase-container" id="phraseContainerEI">
        <!-- Las frases se insertarán aquí dinámicamente -->
    </div>
</div>

<script>
const phrasesEI = [
    {text: "Intelligence emerges through constraints.", position: "center"},
    {text: "Not perfect sensing, but meaningful interpretation.", position: "top-left"},
    {text: "Distributed across human, AI, and hardware.", position: "top-right"},
    {text: "Making meaning from partial inputs.", position: "bottom-left"},
    {text: "Agentic, not automated.", position: "bottom-right"},
    {text: "Collaboration through negotiation.", position: "center"},
    {text: "Physical computing as dialogue.", position: "top-left"},
    {text: "AI as interpretive composer.", position: "top-right"},
    {text: "Limitations become features.", position: "bottom-left"},
    {text: "Emergent, not engineered.", position: "bottom-right"},
    {text: "Extended Intelligence", position: "center"}
];

let currentIndexEI = 0;
const containerEI = document.getElementById('phraseContainerEI');

function showNextPhraseEI() {
    containerEI.innerHTML = '';
    
    const phraseData = phrasesEI[currentIndexEI];
    const phraseElement = document.createElement('div');
    phraseElement.className = `phrase ${phraseData.position}`;
    phraseElement.textContent = phraseData.text;
    
    containerEI.appendChild(phraseElement);
    
    setTimeout(() => {
        phraseElement.classList.add('active');
    }, 100);
    
    currentIndexEI = (currentIndexEI + 1) % phrasesEI.length;
    setTimeout(showNextPhraseEI, 3000);
}

document.addEventListener('DOMContentLoaded', () => {
    if (containerEI) {
        showNextPhraseEI();
    }
});
</script>

<style>
/* Estilos adicionales para esta página (compatibles con tu estilo existente) */
.content-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
}

.section {
    margin-bottom: 4rem;
}

pre {
    background-color: #2d3436;
    color: #dfe6e9;
    padding: 1rem;
    border-radius: 5px;
    font-size: 0.85rem;
    overflow-x: auto;
    font-family: 'Courier New', monospace;
}

code {
    font-family: 'Courier New', monospace;
    background-color: #f1f2f6;
    padding: 0.2rem 0.4rem;
    border-radius: 3px;
    font-size: 0.9rem;
}

/* Estilos para las frases animadas (ya existen en tu CSS, los mantengo) */
.phrase-screen {
    background-color: #ffffff;
    border-radius: 12px;
    padding: 3rem;
    margin: 2rem 0 4rem 0;
    border: 1px solid #e0e0e0;
    box-shadow: 0 8px 30px rgba(0, 0, 0, 0.05);
    min-height: 400px;
    position: relative;
    overflow: hidden;
}

.phrase-container {
    position: relative;
    height: 350px;
    width: 100%;
}

.phrase {
    position: absolute;
    font-size: 1.8rem;
    font-weight: 500;
    color: #1a1a1a;
    text-align: center;
    opacity: 0;
    transition: opacity 0.8s ease, transform 0.8s ease;
    max-width: 90%;
    line-height: 1.4;
    padding: 1rem;
}

.phrase.active {
    opacity: 1;
}

/* Posiciones específicas */
.phrase.top-left {
    top: 10%;
    left: 5%;
    text-align: left;
    transform: translateX(-20px);
}
.phrase.top-left.active {
    transform: translateX(0);
}

.phrase.top-right {
    top: 15%;
    right: 5%;
    text-align: right;
    transform: translateX(20px);
}
.phrase.top-right.active {
    transform: translateX(0);
}

.phrase.center {
    top: 40%;
    left: 50%;
    transform: translate(-50%, 20px);
    width: 80%;
    text-align: center;
}
.phrase.center.active {
    transform: translate(-50%, 0);
}

.phrase.bottom-left {
    bottom: 20%;
    left: 10%;
    text-align: left;
    transform: translateY(20px);
}
.phrase.bottom-left.active {
    transform: translateY(0);
}

.phrase.bottom-right {
    bottom: 25%;
    right: 10%;
    text-align: right;
    transform: translateY(20px);
}
.phrase.bottom-right.active {
    transform: translateY(0);
}
</style>