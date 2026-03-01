<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Situated Design Practices · MDEF</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
            background-color: #fcfcfc;
            color: #1a1e2b;
            line-height: 1.6;
        }

        /* ----- MENU (exacto como en la referencia) ----- */
        .menu-container {
            width: 100%;
            border-bottom: 1px solid #eaeef2;
            background-color: #ffffff;
        }

        .custom-header-menu {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1.2rem 2rem;
            display: flex;
            gap: 2.5rem;
            font-weight: 450;
            letter-spacing: -0.01em;
        }

        .custom-header-menu a {
            text-decoration: none;
            color: #2d3a4a;
            font-size: 1.1rem;
            transition: color 0.2s ease;
            border-bottom: 1px solid transparent;
            padding-bottom: 0.2rem;
        }

        .custom-header-menu a:hover {
            color: #4c6b8a;
            border-bottom-color: #8ba0b8;
        }

        /* ----- LAYOUT PRINCIPAL ----- */
        .main-content {
            max-width: 1000px;
            margin: 3rem auto 5rem;
            padding: 0 2rem;
        }

        h1 {
            font-size: 2.8rem;
            font-weight: 500;
            letter-spacing: -0.02em;
            margin-bottom: 1.2rem;
            color: #1e2b3a;
            border-left: 6px solid #6b8cae;
            padding-left: 1.8rem;
        }

        /* video contenedor - loop, silenciado, 2seg */
        .video-wrapper {
            margin: 3rem 0 3rem;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 12px 30px -8px rgba(0,20,30,0.25);
            background-color: #e9edf2;
            aspect-ratio: 16 / 9;
        }

        .situated-video {
            width: 100%;
            height: 100%;
            display: block;
            object-fit: cover;
            background-color: #1a1f2b; /* fallback mientras carga */
        }

        /* texto principal con estilo de párrafo similar al de las reflexiones */
        .reflection-text {
            background-color: #f8fafc;
            padding: 2.5rem;
            border-radius: 20px;
            margin: 3rem 0 2rem;
            border-left: 5px solid #4c51bf;
            font-size: 1.1rem;
            color: #2d3f4f;
        }

        .reflection-text p {
            margin-bottom: 1.8rem;
        }

        .reflection-text p:last-child {
            margin-bottom: 0;
        }

        /* responsive */
        @media (max-width: 600px) {
            .custom-header-menu {
                padding: 1rem 1.5rem;
                gap: 1.5rem;
            }
            h1 {
                font-size: 2.2rem;
                padding-left: 1.2rem;
            }
            .reflection-text {
                padding: 1.8rem;
            }
        }
    </style>
</head>
<body>

    <!-- MENU EXACTO DE LA REFERENCIA -->
    <div class="menu-container">
        <div class="custom-header-menu">
            <a href="../..">MDEF</a>
            <a href="https://eradesign.portfolio.site/" target="_blank" rel="noopener noreferrer">Projects</a>
            <a href="../../about/me">About me</a>
        </div>
    </div>

    <!-- CONTENIDO PRINCIPAL -->
    <div class="main-content">
        
        <!-- TÍTULO -->
        <h1>Situated Design Practices</h1>

        <!-- VIDEO EN LOOP (2 segundos) -->
        <div class="video-wrapper">
            <video class="situated-video" autoplay loop muted playsinline preload="auto">
                <source src="../../videos/Situated.mp4" type="video/mp4">
                Tu navegador no soporta el elemento de video.
            </video>
        </div>

        <!-- TEXTO COMPLETO -->
        <div class="reflection-text">
            <p>This week helped me understand design not as an abstract or universal practice, but as a situated action, embedded in a territory, shaped by political structures, and connected to specific communities. Throughout the sessions, exploring different contexts in Barcelona made it clear that design does not only produce objects or systems, but also relationships, narratives, and positions.</p>

            <p>The visit to the Barcelona Supercomputing Center made me see how highly complex technological infrastructures are not only scientific devices, but also political and cultural artifacts. High-performance computing structures ways of producing knowledge, sets research priorities, and distributes resources. From a situated design perspective, this means acknowledging that even systems that appear "neutral" are embedded in power dynamics and institutional decisions.</p>

            <p>The experience at Cal Negre introduced a completely different dimension: community life as a design practice in itself. There, design is not expressed as a finished product, but as an ongoing process of negotiation, care, and adaptation to the territory. The proximity to the airport and industrial infrastructures creates ecological and social tensions that directly shape ways of inhabiting the space. In this context, design becomes a tool to sustain alternative forms of coexistence, showing that commitment is not just a discourse, but something practiced daily.</p>

            <p>The discussion around forced communities and border regimes also made visible how design actively participates in the production of exclusion or mobility. Systems, infrastructures, and policies are designed and they shape who can move, who must stay, and under what conditions.</p>

            <p>For me, this reinforces the importance of understanding design as a practice that must explicitly recognize its context and political implications. It means working with communities not as abstract "users," but as agents with history, agency, and their own knowledge.</p>
        </div>
    </div>
</body>
</html>