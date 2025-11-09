<div class="menu-container">
    <div class="custom-header-menu">
        <a href="/MDEF-Portfolio/">MDEF</a>
        <a href="projects/Portfolio">Projects</a>
        <a href="about/me">About me</a>
    </div>
</div>

<style>
.observer-text {
    position: relative;
    transition: transform 0.1s ease;
    display: inline-block;
    cursor: default;
}

.observer-section {
    background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
    padding: 2rem;
    border-radius: 12px;
    margin: 2rem 0;
    border-left: 4px solid #6c757d;
    position: relative;
    overflow: hidden;
}

.observer-section::before {
    content: "👁️";
    position: absolute;
    top: 1rem;
    right: 1rem;
    font-size: 1.5rem;
    opacity: 0.1;
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const observerTexts = document.querySelectorAll('.observer-text');
    const observerSection = document.querySelector('.observer-section');
    
    document.addEventListener('mousemove', function(e) {
        const mouseX = e.clientX / window.innerWidth;
        const mouseY = e.clientY / window.innerHeight;
        
        // Movimiento sutil del texto
        observerTexts.forEach(text => {
            const moveX = (mouseX - 0.5) * 10; // ±5px
            const moveY = (mouseY - 0.5) * 8;  // ±4px
            text.style.transform = `translate(${moveX}px, ${moveY}px)`;
        });
        
        // Efecto de sombra que sigue el cursor en la sección
        if (observerSection) {
            const rect = observerSection.getBoundingClientRect();
            const x = e.clientX - rect.left;
            const y = e.clientY - rect.top;
            
            observerSection.style.background = `
                radial-gradient(circle at ${x}px ${y}px, 
                    rgba(108, 117, 125, 0.05) 0%,
                    #f8f9fa 50%,
                    #e9ecef 100%)
            `;
        }
    });
    
    // Reset cuando el mouse sale de la ventana
    document.addEventListener('mouseleave', function() {
        observerTexts.forEach(text => {
            text.style.transform = 'translate(0, 0)';
        });
        if (observerSection) {
            observerSection.style.background = 'linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%)';
        }
    });
});
</script>

# BookGrip

<video controls autoplay muted loop width="100%" style="border-radius: 8px; margin: 2rem 0;">
  <source src="../../videos/BookGrip.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Prosthetics go beyond their traditional function. They are not tools to fix or replace, but extensions that question how we evolve.

BookGrip is a prosthesis that forces the body to hold a book again, to pause, to feel its weight, and to reconnect with knowledge through touch.
It reminds us that being the best version of ourselves isn't always about progress, but about remembering what we've forgotten.

---

# Listening Extensions

<video controls autoplay muted loop width="100%" style="border-radius: 8px; margin: 2rem 0;">
  <source src="../../videos/ListeningExtensions.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

This prosthesis explores the idea of human–nature connection beyond enhancement.
Made of wires, threads, and branches, it acts as an interface of sensitivity, a network that expands the human body's perception toward the environment.

It imagines a future where we grow with our surroundings instead of apart from them.
Where technology and nature intertwine, and the body becomes a bridge between both.

---

# To be judge

<img src="../../images/detective.jpg" 
     alt="The Detective" 
     width="100%" 
     style="border-radius: 8px; margin: 2rem 0; object-fit: cover;">

<p>
We played a game of surveillance, half of us became subjects, half became detectives. 
For thirty minutes, I was followed without knowing by whom, and for another thirty, 
I became the one who watched. The constant awareness of being seen changed the way I moved, 
the way I existed.
</p>

<h3>Subject</h3>

<div style="display: flex; align-items: center; gap: 2rem; margin: 2rem 0;">
  <img src="../../images/hide.jpg" 
       alt="Hide" 
       style="width: 45%; border-radius: 8px; object-fit: cover;">
  
  <div style="width: 55%; text-align: justify;">
    <p>
      During the surveillance exercise, I became the subject, followed by an unknown observer. 
      The sensation of being watched made me uneasy, aware of every movement and gesture. 
      Instinctively, I used my own hair as a prosthesis: a way to hide, to create a barrier between myself 
      and the gaze that surrounded me. It wasn't about vanity, but protection, an attempt to control what could 
      be seen when everything else felt exposed.
    </p>
  </div>
</div>

<h3>Detective</h3>

<p>
As the detective, I tried to be discreet, to observe without being noticed.
At 13:02, the subject was working intensely on the computer with Armin, probably something related to the webpage.
At 13:11, the subject closed the laptop, packed a few things, and by 13:12 was gone. I lost the subject almost immediately, 
wandering through the building trying to find them again.
</p>

<p>
When the subject suggested to continue the game, I followed once more.
At 14:01, the subject joined a group on the terrace, Ayal, Max, Armin, talking, laughing, sharing songs.
The subject recommended "Cosa sarà" for sad moments, "Cumbia japonesa" for cooking, "Ella baila sola" for parties, 
and chose bossa nova as their music for stress, though confessed they would rather play techno.
</p>

<p>
Each song revealed a different version of the subject, a small window into how they move through moods and moments.
Trying to document them felt strange, I didn't want to intrude, yet every step I took made my presence more visible.
In the end, being the observer felt just as exposed as being observed.
</p>

