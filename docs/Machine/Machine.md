<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

# Meluza: The Deceptive Machine

A project about a self-centered machine that uses beauty to deceive.

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

![Meluza Machine Concept](images/meluza_concept.jpg)

## Design Process

### Conceptual Framework

<div style="background: #fefaf0; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <h2 style="font-size: 1.8rem; font-weight: bold; margin-top: 0;">Design Philosophy</h2>
    
<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1rem;">
        <div>
            <h3>THE PRETTY WELL LIVING MATERIALS</h3>
            <ul>
                <li>Primary involved standards</li>
                <li>Multicircularity</li>
                <li>Thriving design approach</li>
                <li>Financing considerations</li>
            </ul>
        </div>
        
<div>
            <h3>THE SELF-CENTERED MATTERS</h3>
            <ul>
                <li>Maximum expectations by human</li>
                <li>Maximum final work and own agency</li>
                <li>Mediums constrained by human interaction</li>
                <li>Sustained tension and agency</li>
            </ul>
        </div>
    </div>
</div>

### Design Elements

<div style="background: #ffffff; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333; margin: 2rem 0;">
    <h3 style="margin-top: 0;">Key Design Components</h3>
    <p><strong>POLING BIGGER MACHINE:</strong> Honesty/lying machine, sincere discomfort, making interaction intentionally unpleasant</p>
    <p><strong>GIVE PRETTY MATERIALS:</strong> Showing what everyone wants, being pretty as the main way to attract users</p>
    <p><strong>FUNCTIONAL ELEMENTS:</strong> Display messaging, political/emotional picking up and moving</p>
</div>

## Technical Implementation

### System Architecture

![System Diagram](images/system_diagram.jpg)

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