<div class="menu-container">
    <div class="custom-header-menu">
        <a href="../..">MDEF</a>
        <a href="../../projects/Portfolio">Projects</a>
        <a href="../../about/me">About me</a>
    </div>
</div>

# Forensic Report: Apple Macbook

A detailed teardown and analysis of a Late 2009 MacBook, exploring obsolescence, component reuse, and the hidden complexity behind Apple's design.

![Macbook Bird's Eye View](https://hackmd.io/_uploads/SkvUWDoxZl.jpg)

## Case Details

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0; align-items: start;">
    
<!-- Left Column -->
<div>
        <h3 style="margin-top: 0;">Case Information</h3>
        <div style="background: #f8f9fa; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
            <p><strong>Reporting Agency:</strong> MDEF</p>
            <p><strong>Case Identifier:</strong> Forensics of the Obsolescence</p>
            <p><strong>Date of Receipt:</strong> 19/11/2025</p>
            <p><strong>Date of Report:</strong> 21/11/2025</p>
        </div>
    </div>
    
<!-- Right Column -->
<div>
        <h3 style="margin-top: 0;">Device Specifications</h3>
        <div style="background: #f8f9fa; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #333;">
            <p><strong>Model:</strong> MacBook (13-inch, Late 2009) A1181</p>
            <p><strong>Serial Number:</strong> 9G8280BTEWY2A</p>
            <p><strong>Color:</strong> White</p>
            <p><strong>Origin:</strong> USA, China, International</p>
        </div>
    </div>
</div>

## Component Inventory

<div class="slideshow-container" style="position: relative; max-width: 100%; margin: 2rem 0; border-radius: 8px; overflow: hidden; background: #000;">
    
<!-- Slides -->
<div class="slide fade">
        <img src="https://hackmd.io/_uploads/BJGf6sTxbe.png" style="width:100%; display: block;">
        <div style="position: absolute; bottom: 0; background: rgba(0,0,0,0.7); color: white; padding: 1rem; width: 100%; text-align: center;">MacBook Rechargeable Battery</div>
    </div>
    <div class="slide fade">
        <img src="https://hackmd.io/_uploads/BklP1Oox-g.jpg" style="width:100%; display: block;">
        <div style="position: absolute; bottom: 0; background: rgba(0,0,0,0.7); color: white; padding: 1rem; width: 100%; text-align: center;">Hard Drive - 160GB Fujitsu</div>
    </div>
    <div class="slide fade">
        <img src="https://hackmd.io/_uploads/HkjupiTeWg.png" style="width:100%; display: block;">
        <div style="position: absolute; bottom: 0; background: rgba(0,0,0,0.7); color: white; padding: 1rem; width: 100%; text-align: center;">Super Multi DVD Rewriter</div>
    </div>
    <div class="slide fade">
        <img src="https://hackmd.io/_uploads/SkajJ3alZl.png" style="width:100%; display: block;">
        <div style="position: absolute; bottom: 0; background: rgba(0,0,0,0.7); color: white; padding: 1rem; width: 100%; text-align: center;">Optical Drive Flex Cable</div>
    </div>
    <div class="slide fade">
        <img src="https://hackmd.io/_uploads/rkeJTipe-e.png" style="width:100%; display: block;">
        <div style="position: absolute; bottom: 0; background: rgba(0,0,0,0.7); color: white; padding: 1rem; width: 100%; text-align: center;">DC Brushless Fan</div>
    </div>

 <!-- Navigation buttons -->
 <a class="prev" onclick="plusSlides(-1)" style="cursor: pointer; position: absolute; top: 50%; left: 0; padding: 20px; color: white; font-weight: bold; font-size: 24px; transform: translateY(-50%); user-select: none; background: rgba(0,0,0,0.3); border-radius: 0 5px 5px 0;">❮</a>
    <a class="next" onclick="plusSlides(1)" style="cursor: pointer; position: absolute; top: 50%; right: 0; padding: 20px; color: white; font-weight: bold; font-size: 24px; transform: translateY(-50%); user-select: none; background: rgba(0,0,0,0.3); border-radius: 5px 0 0 5px;">❯</a>

<!-- Dots indicator -->
<div style="text-align: center; padding: 15px; position: absolute; bottom: 0; width: 100%; background: rgba(0,0,0,0.5);">
        <span class="dot" onclick="currentSlide(1)"></span>
        <span class="dot" onclick="currentSlide(2)"></span>
        <span class="dot" onclick="currentSlide(3)"></span>
        <span class="dot" onclick="currentSlide(4)"></span>
        <span class="dot" onclick="currentSlide(5)"></span>
    </div>
</div>

<script>
let slideIndex = 1;
showSlides(slideIndex);

function plusSlides(n) {
    showSlides(slideIndex += n);
}

function currentSlide(n) {
    showSlides(slideIndex = n);
}

function showSlides(n) {
    let i;
    let slides = document.getElementsByClassName("slide");
    let dots = document.getElementsByClassName("dot");
    
    if (n > slides.length) {slideIndex = 1}
    if (n < 1) {slideIndex = slides.length}
    
    for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";
    }
    for (i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(" active", "");
    }
    
    slides[slideIndex-1].style.display = "block";
    dots[slideIndex-1].className += " active";
}

// Auto-advance every 5 seconds
setInterval(() => {
    plusSlides(1);
}, 5000);
</script>

<style>
.slide {
    display: none;
}
.dot {
    cursor: pointer;
    height: 10px;
    width: 10px;
    margin: 0 4px;
    background-color: #bbb;
    border-radius: 50%;
    display: inline-block;
    transition: background-color 0.3s ease;
}
.dot.active, .dot:hover {
    background-color: #fff;
}
.prev:hover, .next:hover {
    background-color: rgba(0,0,0,0.7) !important;
}
</style>

## Technical Analysis

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 3rem 0; align-items: start;">
    
<!-- Left Column -->
<div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-top: 0;">Forensic Questions</h2>
        <div style="line-height: 1.6;">
            <h3>What does it do?</h3>
            <p>The MacBook is a portable computing device designed to process information, display visual output, and allow users to interact with digital content through its screen, keyboard, camera, trackpad, and built-in media and connectivity ports.</p>
            
   <h3>How does it work?</h3>
            <p><strong>Mechanical:</strong> The MacBook's mechanical systems support and protect its internal components through hinges, pressure switches, and cooling systems.</p>
            <p><strong>Electrical:</strong> Power flows from the battery through voltage regulators to the logic board, enabling communication between all components.</p>
            <p><strong>Digital:</strong> Firmware and software translate user actions into computational tasks through the operating system and embedded controllers.</p>
        </div>
    </div>
    
<!-- Right Column -->
<div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-top: 0;">Construction & Failure</h2>
        <div style="line-height: 1.6;">
            <h3>How is it built?</h3>
            <p>The MacBook is assembled primarily with small screws securing plastic cases to an internal frame. The top case integrates keyboard and trackpad, while internal layers contain optical drive, battery, RAM, and logic board with all I/O ports.</p>
            
 <h3>Why did it fail?</h3>
            <p>Our investigation suggests battery failure as the primary cause of obsolescence. The battery showed swelling in one cell and measured 0V. Internal dust accumulation may have contributed to performance degradation.</p>
        </div>
    </div>
</div>

![Exploded Axonometric of Vintage MacBook](https://hackmd.io/_uploads/S155WeagWe.jpg)

## Component Testing

### Hard Drive Recovery

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0; align-items: start;">
    
<!-- Left Column -->
<div>
        <img src="https://hackmd.io/_uploads/S1ghf3pgbg.jpg" 
             alt="Hard Drive Recovery" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover;">
    </div>
    
<!-- Right Column -->
<div>
        <h3 style="margin-top: 0;">WHY</h3>
        <p>To explore data recovery possibilities and demonstrate how much personal information remains accessible on discarded devices, highlighting digital security concerns.</p>
        
  <h3>HOW</h3>
        <p>Connected the 160GB Fujitsu hard drive to a modern Apple laptop via external adapter, successfully accessing stored data including personal files and user information.</p>

 <h3>RESULT</h3>
        <p>Successfully recovered data, identifying the original owner. This revealed significant privacy implications of improper device disposal.</p>
    </div>
</div>

### Fan Control Hack

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0; align-items: start;">
    
<!-- Left Column -->
<div>
        <img src="https://hackmd.io/_uploads/HJsKTJ6gbl.png" 
             alt="Fan Control Setup" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover;">
    </div>
    
<!-- Right Column -->
<div>
        <h3 style="margin-top: 0;">WHY</h3>
        <p>To understand motor control and PWM (Pulse Width Modulation) principles while repurposing a functional component.</p>
        
  <h3>HOW</h3>
        <p>Used Barduino board with Arduino IDE, requiring pin extraction, transistor integration, and custom wiring to achieve variable speed control.</p>
   <h3>RESULT</h3>
        <p>Successfully controlled fan speed through Arduino code after overcoming wiring challenges and voltage requirements.</p>
    </div>
</div>

### Trackpad Conversion Attempt

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 2rem 0; align-items: start;">
    
<!-- Left Column -->
<div>
        <img src="https://hackmd.io/_uploads/ByQ3TkaeWg.png" 
             alt="Trackpad Soldering" 
             width="100%" 
             style="border-radius: 8px; object-fit: cover;">
    </div>
    
<!-- Right Column -->
<div>
        <h3 style="margin-top: 0;">WHY</h3>
        <p>To convert the MacBook trackpad into a standalone USB input device, exploring component repurposing.</p>
        
<h3>HOW</h3>
        <p>Followed online tutorials to identify pins and solder USB cable directly to the trackpad board.</p>

 <h3>RESULT</h3>
        <p>Despite proper soldering, the trackpad wasn't recognized by computers. Provided valuable soldering practice and component understanding.</p>
    </div>
</div>

## Technical Findings

<div style="background: #f8f9fa; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <h2 style="font-size: 1.8rem; font-weight: bold; margin-top: 0;">Key Discoveries</h2>
    
<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1rem;">
        <div>
            <h3>Motors Identified</h3>
            <ul>
                <li>Cooling fan DC brushless motor</li>
                <li>Hard drive spindle motor</li>
                <li>Hard drive precision stepper motor</li>
                <li>DVD drive mechanism motors</li>
            </ul>
        </div>
        
 <div>
         <h3>Sensors Found</h3>
            <ul>
                <li>Microphones (sound)</li>
                <li>Trackpad multi-touch surface</li>
                <li>iSight camera</li>
                <li>Wi-Fi + Bluetooth modules</li>
                <li>Hall effect lid sensor</li>
                <li>Temperature sensors</li>
                <li>Sudden Motion Sensor (in HDD)</li>
            </ul>
        </div>
    </div>
</div>

## Team Reflections

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin: 3rem 0; align-items: start;">
    
<!-- Left Column -->
<div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-top: 0;">What We Learned</h2>
        <div style="line-height: 1.6;">
            <p>The disassembly revealed Apple's complex internal architecture contrasting with their minimalist external design. We discovered:</p>
            <ul>
                <li>Extensive use of screws and intricate sub-components</li>
                <li>Contrast between user-friendly interface and complex internals</li>
                <li>Varying "hackability" of different components</li>
                <li>Practical skills in soldering, coding, and component testing</li>
            </ul>
        </div>
    </div>
    
<!-- Right Column -->
<div>
        <h2 style="font-size: 1.8rem; font-weight: bold; margin-top: 0;">What Surprised Us</h2>
        <div style="line-height: 1.6;">
            <blockquote style="border-left: 4px solid #333; padding-left: 1rem; margin: 1rem 0; font-style: italic;">
                "I had no idea how many screws were inside my computer. So. Many. Screws." - Ayal
            </blockquote>
            <blockquote style="border-left: 4px solid #333; padding-left: 1rem; margin: 1rem 0; font-style: italic;">
                "Interesting how small technology can be, with high capacity." - Ivan
            </blockquote>
            <blockquote style="border-left: 4px solid #333; padding-left: 1rem; margin: 1rem 0; font-style: italic;">
                "A deceptively complex internal structure compared to the user-friendly interface." - Heba
            </blockquote>
        </div>
    </div>
</div>

![All Components Laid Out](https://hackmd.io/_uploads/BkwRGPolWx.jpg)  

## Documentation & References

<div style="background: #f8f9fa; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <h2 style="font-size: 1.8rem; font-weight: bold; margin-top: 0;">Component Datasheets</h2>
    
 <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 1rem;">
        <div>
            <h3>HDD Hard Drive</h3>
            <p><a href="https://hackmd.io/@L3g4HxxGRESszjwULqN-VQ/Hk5_Kphe-e" style="color: #333; text-decoration: underline;">Technical Documentation</a></p>
        </div>
        
 <div>
            <h3>DC Brushless Fan</h3>
            <p><a href="https://hackmd.io/dpL_RwwtT1ytSJxxy6_43w" style="color: #333; text-decoration: underline;">Control Specifications</a></p>
        </div>
    </div>
</div>

<div style="background: #f8f9fa; padding: 2rem; border-radius: 8px; margin: 2rem 0;">
    <h2 style="font-size: 1.8rem; font-weight: bold; margin-top: 0;">References</h2>
    <ul>
        <li>Apple Inc. (2009). MacBook 13-inch: Late 2009 service manual</li>
        <li>Technical Specifications: support.apple.com/en-us/112623</li>
        <li>Delta Fan Datasheet: KSB0405HBF0D</li>
        <li>Various online maker tutorials and forums</li>
    </ul>
</div>

<div style="text-align: center; margin-top: 3rem; padding: 2rem; background: #333; color: white; border-radius: 8px;">
    <h3 style="margin-top: 0;">Forensic Examination Team</h3>
    <p>Ayal Bark, Heba Elidrisi, Ivan Garcia, Beste Cebeci, Erandi Estrada, Madlen Von Wulffen</p>
    <p><em>MDEF - Forensics of the Obsolescence</em></p>
</div>
