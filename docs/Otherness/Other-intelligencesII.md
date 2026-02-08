<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>
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
                <h4 style="margin-top: 0; color: #6c5ce7;">System Logic</h4>
                <p style="margin-bottom: 0.5rem; font-size: 0.95rem;">
                    • User input (touch / color)<br>
                    • AI agent (mood + rhythm interpretation)<br>
                    • Lyrics generation <br>
                    • Song reference (YouTube)<br>
                    • Light behavior (NeoPixel)
                </p>
            </div>
        </div>
    </div>
<!-- System & Agent Behavior -->
<div class="section" style="margin-bottom: 4rem;">
    <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">
        System & Agent Behavior
    </h2>

    <div style="max-width: 900px;">
        <p style="margin-bottom: 1rem; line-height: 1.6;">
            At the core of the project is an AI agent acting as an interpreter between human intention and physical response. 
            Instead of receiving precise musical instructions, the agent works with abstract inputs such as mood, rhythm, 
            and symbolic gestures.
        </p>

        <p style="margin-bottom: 1rem; line-height: 1.6;">
            Color input is translated into emotional states, while touch interaction is intended to communicate rhythm. 
            Based on these parameters, the agent generates song lyrics, identifies a matching musical reference, and defines 
            the behavior of a NeoPixel light strip to visually reinforce the atmosphere of the generated song.
        </p>

        <p style="margin-bottom: 0; line-height: 1.6;">
            The intelligence of the system does not rely on exact sensing, but on interpretation—embracing ambiguity as part 
            of the creative exchange between human and machine.
        </p>
    </div>
</div>

<!-- Physical Computing Setup -->
<div class="section" style="margin-bottom: 4rem;">
    <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">
        Physical Computing Setup
    </h2>

    <div class="two-column-layout" style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: start;">
        <div>
            <p style="margin-bottom: 1rem; line-height: 1.6;">
                The system was developed using a Raspberry Pi Pico 2W connected to physical sensors and actuators. 
                A capacitive touch sensor made from a copper strip was designed to capture rhythmic interaction, 
                while a color sensor was planned to communicate emotional tone.
            </p>

            <p style="margin-bottom: 0; line-height: 1.6;">
                Due to time constraints and hardware instability, the touch sensor was only partially functional, 
                detecting presence rather than continuous rhythm. Connectivity issues also limited the integration 
                of the color sensor and NeoPixel strip during the final implementation.
            </p>
        </div>

        <div style="background-color: #f8f9fa; padding: 1.5rem; border-radius: 8px;">
            <h4 style="margin-top: 0;">Components</h4>
            <p style="font-size: 0.95rem; line-height: 1.6; margin-bottom: 0;">
                • Raspberry Pi Pico 2W<br>
                • Capacitive touch sensor (copper strip)<br>
                • Planned color sensor<br>
                • NeoPixel LED strip<br>
                • MCP-based communication with AI agent
            </p>
        </div>
    </div>
</div>
<!-- Process & Challenges -->
<div class="section" style="margin-bottom: 4rem;">
    <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">
        Process & Challenges
    </h2>

    <div style="max-width: 900px;">
        <p style="margin-bottom: 1rem; line-height: 1.6;">
            The course took place over only three days, which strongly shaped both the scope and direction of the project. 
            Much of the development time was spent troubleshooting hardware communication, operating system constraints, 
            and sensor calibration.
        </p>

        <p style="margin-bottom: 1rem; line-height: 1.6;">
            Attempting to extract rhythmic information from a simple capacitive sensor revealed how fragile physical 
            interaction can be when signal stability is not guaranteed. These limitations ultimately shifted the project 
            toward a more AI-driven interaction, where the agent compensated for incomplete or symbolic inputs.
        </p>

        <p style="margin-bottom: 0; line-height: 1.6;">
            Rather than abandoning the concept, the project embraced this imbalance, allowing the AI agent to become 
            more speculative, interpretive, and autonomous in its creative decisions.
        </p>
    </div>
</div>

<!-- Reflection -->
<div class="section" style="margin-bottom: 4rem;">
    <h2 style="border-bottom: 2px solid #333; padding-bottom: 0.5rem; margin-bottom: 2rem;">
        Reflection
    </h2>

    <div style="max-width: 900px;">
        <p style="margin-bottom: 1rem; line-height: 1.6;">
            This project started with the intention of creating a shared musical experience between a human and an AI agent, 
            where physical interaction would directly shape sound, mood, and atmosphere. The idea was simple but ambitious: 
            touching, sensing color, and moving rhythmically would become a way of talking to an AI.
        </p>

        <p style="margin-bottom: 1rem; line-height: 1.6;">
            In practice, the project quickly became a lesson about friction. Hardware limitations, connectivity issues, 
            and the short timeframe meant that many interactions remained incomplete or unstable. What I imagined as a 
            fluid, embodied exchange often turned into negotiation with the tools themselves.
        </p>

        <p style="margin-bottom: 0; line-height: 1.6;">
            This process made me realize that intelligence in physical systems is rarely clean or finished. It is shaped 
            by improvisation, failure, and adaptation. Rather than seeing these constraints as shortcomings, the project 
            reframed them as part of how agentic systems come into being.
        </p>
    </div>
</div>


