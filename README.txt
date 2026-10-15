<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
    <title>RoboMedix - Robótica Médica y Salud de Precisión</title>
    <meta name="description" content="RoboMedix: historia, evolución y clasificación de la robótica médica. PUMA 560, Da Vinci, Mako, exoesqueletos, robots de desinfección UVC y nanorrobots." />
    <meta name="author" content="RoboMedix" />

    <!-- Tipografía -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<style>
/* =========================================
   ROBOMEDIX — ESMERALDA & TURQUESA SALUD
   (Estilo original, versión de mayor calidad)
   ========================================= */
:root {
    --bg-dark: #8C2E5D;
    --bg-card: rgba(8, 28, 22, 0.8);
    --bg-card-hover: rgba(14, 42, 33, 0.9);
    --med-blue: #C75283;
    --med-cyan: #1A0015;
    --med-teal: #FFB6C1;
    --text-light: #FFD1DC;
    --text-muted: #83a79d;
    --glass-border: rgba(0, 245, 196, 0.22);
    --glass-border-glow: rgba(0, 245, 196, 0.65);
    --shadow-glow: rgba(0, 245, 196, 0.18);
}

* { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; scroll-padding-top: 90px; }

body {
    background-color: var(--bg-dark);
    color: var(--text-light);
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 16px;
    line-height: 1.7;
    overflow-x: hidden;
}

/* Scanlines sutiles */
body::before {
    content: ""; position: fixed; inset: 0; z-index: 9999; pointer-events: none;
    background: repeating-linear-gradient(0deg, rgba(0,0,0,.08) 0 1px, transparent 1px 2px);
}

h1, h2, h3, h4 { font-family: 'Space Grotesk', sans-serif; color: #fff; letter-spacing: -0.02em; }
a { text-decoration: none; transition: all 0.3s ease; }
img { max-width: 100%; display: block; }

::selection { background: var(--med-cyan); color: var(--bg-dark); }

/* ============ HEADER ============ */
#header {
    position: fixed; top: 0; width: 100%; z-index: 1000;
    padding: 0.9rem 6%;
    display: flex; justify-content: space-between; align-items: center;
    background: rgba(3, 18, 14, 0.88);
    backdrop-filter: blur(16px); -webkit-backdrop-filter: blur(16px);
    border-bottom: 1px solid var(--glass-border);
}
#logo-container { display: flex; align-items: center; gap: 12px; }
.logo-svg { width: 48px; height: 48px; filter: drop-shadow(0 0 10px rgba(0, 245, 196, 0.5)); transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
.logo-svg:hover { transform: scale(1.1) rotate(5deg); }
#logo a { font-family: 'Space Grotesk', sans-serif; font-size: 1.3rem; font-weight: 700; color: #fff; display: flex; flex-direction: column; line-height: 1.1; }
#logo .brand { color: var(--med-cyan); text-shadow: 0 0 12px rgba(0, 245, 196, 0.4); }
#logo .tagline { font-size: 0.65rem; color: var(--med-teal); font-family: 'Plus Jakarta Sans', sans-serif; letter-spacing: 1.5px; font-weight: 600; }

#nav ul { display: flex; list-style: none; gap: 2.2rem; }
#nav a { color: var(--text-muted); font-weight: 600; font-size: 0.95rem; position: relative; padding: 6px 0; }
#nav a:hover, #nav a.active { color: var(--med-cyan); }
#nav a::after {
    content: ''; position: absolute; bottom: 0; left: 0; width: 0; height: 2px;
    background: linear-gradient(90deg, var(--med-cyan), var(--med-teal));
    transition: width 0.3s ease; box-shadow: 0 0 8px var(--med-cyan);
}
#nav a:hover::after, #nav a.active::after { width: 100%; }

#menu-toggle {
    display: none; background: none; border: 1px solid var(--glass-border);
    color: var(--med-cyan); width: 44px; height: 44px; border-radius: 10px; font-size: 1.1rem; cursor: pointer;
}

/* ============ HERO ============ */
#hero {
    position: relative; min-height: 100vh;
    display: flex; align-items: center; justify-content: center; text-align: center;
    padding: 0 1.5rem;
    background: radial-gradient(circle at 50% 30%, rgba(0, 245, 196, 0.12) 0%, rgba(3, 18, 14, 0.95) 70%);
}
#particles-canvas { position: absolute; inset: 0; z-index: 1; }
.hero-content {
    position: relative; z-index: 2; max-width: 920px;
    padding: 3.5rem 3rem;
    background: rgba(8, 28, 22, 0.65);
    border: 1px solid var(--glass-border); border-radius: 20px; backdrop-filter: blur(12px);
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.6), inset 0 0 20px rgba(0, 245, 196, 0.05);
    animation: pulseGlow 4s ease-in-out infinite alternate;
}
@keyframes pulseGlow {
    from { box-shadow: 0 20px 60px rgba(0,0,0,.6), 0 0 15px rgba(0,245,196,.1); }
    to   { box-shadow: 0 20px 60px rgba(0,0,0,.6), 0 0 35px rgba(0,245,196,.3); }
}
.badge-health {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(56, 239, 125, 0.12); color: var(--med-teal);
    border: 1px solid rgba(56, 239, 125, 0.35);
    font-size: 0.8rem; font-weight: 700; padding: 6px 16px; border-radius: 30px;
    margin-bottom: 1.5rem; text-transform: uppercase; letter-spacing: 1.5px;
}
.hero-content h1 {
    font-size: 3rem; margin-bottom: 1.2rem; line-height: 1.15;
    background: linear-gradient(90deg, #0052D4, #4364F7, #00c6ff);) 80%);
    -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent;
}
.hero-content p { font-size: 1.15rem; color: var(--text-muted); margin-bottom: 2.2rem; }
.btn-health {
    display: inline-flex; align-items: center; gap: 10px;
    padding: 15px 36px; border-radius: 10px; font-weight: 800; font-size: 0.95rem;
    background: linear-gradient(135deg, var(--med-blue), var(--med-cyan)); color: #03120e;
    box-shadow: 0 8px 25px rgba(0, 245, 196, 0.35);
    transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.btn-health:hover { transform: translateY(-3px) scale(1.02); box-shadow: 0 12px 35px rgba(0, 245, 196, 0.55); color: #03120e; }

.scroll-hint {
    position: absolute; bottom: 28px; left: 50%; transform: translateX(-50%); z-index: 2;
    color: var(--med-teal); font-size: 1.4rem; opacity: .7; animation: bounce 2s infinite;
}
@keyframes bounce { 0%,100%{transform:translate(-50%,0)} 50%{transform:translate(-50%,10px)} }

/* ============ SECCIONES ============ */
section { padding: 7rem 8%; }
.section-header { text-align: center; max-width: 800px; margin: 0 auto 4.5rem; }
.section-header .sub-title {
    color: var(--med-teal); font-weight: 700; font-size: 0.85rem;
    text-transform: uppercase; letter-spacing: 2px; display: block; margin-bottom: 0.6rem;
}
.section-header h2 { font-size: 2.4rem; }
.section-header .lead { color: var(--text-muted); margin-top: 1rem; }

.reveal { opacity: 0; transform: translateY(40px); transition: all 0.8s cubic-bezier(0.215, 0.61, 0.355, 1); }
.reveal.active { opacity: 1; transform: translateY(0); }
.reveal[data-delay="1"] { transition-delay: .12s; }
.reveal[data-delay="2"] { transition-delay: .24s; }
.reveal[data-delay="3"] { transition-delay: .36s; }

/* ============ ESTADÍSTICAS ============ */
#stats { padding: 3rem 8%; border-top: 1px solid rgba(0,245,196,.1); border-bottom: 1px solid rgba(0,245,196,.1); background: linear-gradient(180deg, transparent, rgba(0,168,132,.06), transparent); }
.stats-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(190px, 1fr)); gap: 2rem; max-width: 1100px; margin: 0 auto; text-align: center; }
.stat-number { font-family: 'Space Grotesk', sans-serif; font-size: 2.4rem; font-weight: 700; color: var(--med-cyan); text-shadow: 0 0 18px rgba(0,245,196,.4); }
.stat-label { color: var(--text-muted); font-size: .82rem; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; }

/* ============ LÍNEA DEL TIEMPO ============ */
.timeline-container { display: flex; flex-direction: column; gap: 4.5rem; max-width: 1200px; margin: 0 auto; }
.timeline-card {
    display: grid; grid-template-columns: 1.05fr 1fr; gap: 3rem; align-items: center;
    background: var(--bg-card); border: 1px solid var(--glass-border);
    padding: 2.8rem; border-radius: 20px; backdrop-filter: blur(10px);
    transition: border-color 0.4s ease, box-shadow 0.4s ease, transform .15s ease-out;
    transform-style: preserve-3d; perspective: 1000px;
}
.timeline-card:hover { border-color: var(--glass-border-glow); box-shadow: 0 15px 40px rgba(0, 245, 196, 0.18); }
.timeline-card.reverse { direction: rtl; }
.timeline-card.reverse .card-info { direction: ltr; }

.year-tag {
    display: inline-block; background: rgba(0, 168, 132, 0.25); color: var(--med-cyan);
    border: 1px solid var(--med-blue); padding: 5px 16px; border-radius: 8px;
    font-weight: 700; font-size: 0.85rem; margin-bottom: 1.2rem; letter-spacing: 1px;
}
.card-info h3 { font-size: 1.7rem; margin-bottom: 1rem; }
.card-info p { color: var(--text-muted); margin-bottom: 1.4rem; font-size: 1.01rem; }
.card-info p strong { color: var(--text-light); }
.card-info ul { list-style: none; }
.card-info ul li { position: relative; padding-left: 26px; margin-bottom: 10px; font-size: 0.97rem; }
.card-info ul li::before {
    content: "\f00c"; font-family: "Font Awesome 6 Free"; font-weight: 900;
    position: absolute; left: 0; color: var(--med-teal); font-size: 0.9rem;
}
.card-fact {
    margin-top: 1.3rem; padding: .9rem 1.2rem; border-left: 3px solid var(--med-cyan);
    background: rgba(0, 245, 196, .06); border-radius: 0 10px 10px 0;
    font-size: .9rem; color: var(--med-teal); font-weight: 600;
}
.card-fact i { margin-right: 8px; }

/* Marcos HUD para imágenes */
.image-frame { position: relative; border-radius: 14px; overflow: hidden; border: 1px solid var(--glass-border); box-shadow: 0 10px 30px rgba(0,0,0,0.5); }
.image-frame img { width: 100%; height: 330px; object-fit: cover; transition: transform 0.6s cubic-bezier(0.165, 0.84, 0.44, 1); }
.timeline-card:hover .image-frame img { transform: scale(1.06); }
.hud-overlay { position: absolute; inset: 0; pointer-events: none; border: 1px solid transparent; transition: all 0.4s ease; }
.timeline-card:hover .hud-overlay { border: 1px solid var(--med-cyan); background: radial-gradient(circle, transparent 60%, rgba(0, 245, 196, 0.15)); }
.image-tag {
    position: absolute; bottom: 14px; left: 14px;
    background: rgba(3, 18, 14, 0.88); backdrop-filter: blur(8px);
    border: 1px solid var(--glass-border); color: var(--med-teal);
    padding: 5px 14px; font-size: 0.72rem; font-weight: 700; border-radius: 6px; letter-spacing: 1px;
}

/* ============ GALERÍA ============ */
#galeria { background: rgba(0,168,132,.03); }
.gallery-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1.3rem; max-width: 1200px; margin: 0 auto;
}
.gallery-item {
    position: relative; border-radius: 14px; overflow: hidden;
    border: 1px solid var(--glass-border); cursor: zoom-in; aspect-ratio: 4/3;
}
.gallery-item img { width: 100%; height: 100%; object-fit: cover; transition: transform .6s ease, filter .6s ease; }
.gallery-item:hover img { transform: scale(1.08); filter: brightness(1.1); }
.gallery-caption {
    position: absolute; inset: auto 0 0 0; padding: 2.2rem 1rem .8rem;
    background: linear-gradient(transparent, rgba(1,10,8,.92));
    color: var(--med-teal); font-size: .82rem; font-weight: 700; letter-spacing: .5px;
    opacity: 0; transform: translateY(12px); transition: all .35s ease;
}
.gallery-item:hover .gallery-caption { opacity: 1; transform: translateY(0); }

#lightbox {
    position: fixed; inset: 0; z-index: 10001; background: rgba(1,10,8,.94);
    display: flex; align-items: center; justify-content: center; padding: 2rem;
    opacity: 0; visibility: hidden; transition: all .35s ease;
}
#lightbox.open { opacity: 1; visibility: visible; }
#lightbox img { max-width: min(92vw, 1100px); max-height: 85vh; border-radius: 14px; border: 1px solid var(--glass-border-glow); box-shadow: 0 30px 80px rgba(0,0,0,.8); }
#lightbox-close {
    position: absolute; top: 22px; right: 28px; background: none;
    border: 1px solid var(--glass-border); color: var(--med-cyan);
    width: 48px; height: 48px; border-radius: 50%; font-size: 1.2rem; cursor: pointer; transition: all .3s ease;
}
#lightbox-close:hover { background: var(--med-cyan); color: var(--bg-dark); }

/* ============ CLASIFICACIÓN ============ */
.grid-categories { display: grid; grid-template-columns: repeat(auto-fit, minmax(330px, 1fr)); gap: 2.2rem; max-width: 1200px; margin: 0 auto; }
.category-card {
    background: var(--bg-card); border: 1px solid var(--glass-border);
    border-radius: 16px; overflow: hidden; backdrop-filter: blur(10px);
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    position: relative;
}
.category-card::before {
    content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 3px;
    background: linear-gradient(90deg, transparent, var(--med-cyan), transparent);
    transform: translateX(-100%); transition: transform 0.6s ease; z-index: 2;
}
.category-card:hover { transform: translateY(-8px); border-color: var(--glass-border-glow); box-shadow: 0 15px 35px rgba(0, 245, 196, 0.15); background: var(--bg-card-hover); }
.category-card:hover::before { transform: translateX(100%); }
.category-img { width: 100%; height: 185px; object-fit: cover; }
.category-body { padding: 0 2rem 2.2rem; }
.icon-wrapper {
    width: 58px; height: 58px; background: rgba(0, 168, 132, 0.18);
    border: 1px solid var(--med-blue); border-radius: 14px;
    display: flex; align-items: center; justify-content: center;
    margin: -30px 0 1.2rem; color: var(--med-cyan); font-size: 1.5rem;
    position: relative; z-index: 1; backdrop-filter: blur(6px); transition: all .3s ease;
}
.category-card:hover .icon-wrapper { background: var(--med-cyan); color: var(--bg-dark); box-shadow: 0 0 20px var(--med-cyan); transform: rotateY(180deg); }
.category-card h3 { font-size: 1.3rem; margin-bottom: 0.7rem; }
.category-card p { color: var(--text-muted); font-size: 0.95rem; }
.card-stat { margin-top: 1rem; font-size: .8rem; font-weight: 700; color: var(--med-teal); letter-spacing: .5px; }
.card-stat i { margin-right: 6px; }

/* ============ FOOTER ============ */
#footer { background: #010a08; border-top: 1px solid var(--glass-border); padding: 5rem 8% 2.5rem; }
.footer-body { max-width: 750px; margin: 0 auto 3rem; text-align: center; }
.footer-body h3 { font-size: 1.8rem; margin-bottom: 0.8rem; }
.footer-body p { color: var(--text-muted); margin-bottom: 2rem; }
.social-links { display: flex; justify-content: center; gap: 1.5rem; }
.social-links a {
    width: 48px; height: 48px; border-radius: 50%; background: var(--bg-card);
    border: 1px solid var(--glass-border); color: var(--text-light);
    display: flex; align-items: center; justify-content: center; font-size: 1.1rem; transition: all 0.3s ease;
}
.social-links a:hover { background: var(--med-cyan); color: var(--bg-dark); box-shadow: 0 0 20px var(--med-cyan); transform: translateY(-4px); }
.copyright { font-size: 0.85rem; color: #43635a; border-top: 1px solid rgba(255, 255, 255, 0.06); padding-top: 2rem; text-align: center; }

/* ============ RESPONSIVE ============ */
@media (max-width: 992px) {
    #menu-toggle { display: block; }
    #nav {
        position: fixed; top: 76px; right: -100%; width: min(78%, 320px); height: calc(100vh - 76px);
        background: rgba(3,18,14,.97); backdrop-filter: blur(20px);
        border-left: 1px solid var(--glass-border);
        transition: right .4s ease; padding: 2.5rem 2rem;
    }
    #nav.open { right: 0; }
    #nav ul { flex-direction: column; gap: 1.8rem; }
    #nav a { font-size: 1.1rem; display: block; }

    .timeline-card, .timeline-card.reverse { grid-template-columns: 1fr; direction: ltr; padding: 1.8rem; gap: 1.8rem; }
    .image-frame img { height: 260px; }
    .hero-content h1 { font-size: 2.1rem; }
    .hero-content { padding: 2.4rem 1.6rem; }
    .section-header h2 { font-size: 1.8rem; }
    section { padding: 5rem 6%; }
}
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation-duration: .01ms !important; transition-duration: .01ms !important; }
    html { scroll-behavior: auto; }
}
</style>
</head>
<body>

<div id="page-wrapper">

    <!-- ================= HEADER ================= -->
    <header id="header">
        <div id="logo-container">
            <svg class="logo-svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 500 500" aria-hidden="true">
                <defs>
                    <linearGradient id="medGrad" x1="0%" y1="0%" x2="100%" y2="100%">
                        <stop offset="0%" stop-color="#00f5c4" />
                        <stop offset="100%" stop-color="#00a884" />
                    </linearGradient>
                </defs>
                <circle cx="250" cy="180" r="100" fill="none" stroke="#00f5c4" stroke-width="2" stroke-dasharray="6 6" opacity="0.5"/>
                <rect x="185" y="100" width="130" height="90" rx="30" fill="#081c16" stroke="url(#medGrad)" stroke-width="4"/>
                <path d="M 210 100 L 290 100 L 275 78 L 225 78 Z" fill="url(#medGrad)" />
                <rect x="200" y="125" width="100" height="40" rx="20" fill="#03120e" stroke="#38ef7d" stroke-width="2"/>
                <circle cx="228" cy="145" r="9" fill="#00f5c4"/>
                <circle cx="272" cy="145" r="9" fill="#00f5c4"/>
                <circle cx="250" cy="55" r="7" fill="#38ef7d"/>
                <line x1="250" y1="78" x2="250" y2="62" stroke="#38ef7d" stroke-width="3"/>
                <path d="M 160 270 C 160 220, 340 220, 340 270 L 320 290 H 180 Z" fill="#081c16" stroke="url(#medGrad)" stroke-width="3"/>
                <circle cx="250" cy="245" r="20" fill="#03120e" stroke="#38ef7d" stroke-width="2"/>
                <path d="M 245 235 H 255 V 255 H 245 Z M 240 240 H 260 V 250 H 240 Z" fill="#38ef7d"/>
            </svg>
            <h1 id="logo">
                <a href="#hero">ROBO<span class="brand">MEDIX</span>
                <span class="tagline">"Tecnología al servicio de tu bienestar y salud"</span></a>
            </h1>
        </div>

        <button id="menu-toggle" aria-label="Abrir menú"><i class="fa-solid fa-bars"></i></button>

        <nav id="nav" aria-label="Navegación principal">
            <ul>
                <li><a href="#hero" class="active">Inicio</a></li>
                <li><a href="#historia">Evolución</a></li>
                <li><a href="#galeria">Galería</a></li>
                <li><a href="#clasificacion">Clasificación</a></li>
                <li><a href="#footer">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <!-- ================= HERO ================= -->
    <section id="hero">
        <canvas id="particles-canvas" aria-hidden="true"></canvas>
        <div class="hero-content">
            <span class="badge-health"><i class="fa-solid fa-heart-pulse"></i> Robótica Sanitaria y Quirúrgica</span>
            <h1 style="color:red;">EVOLUCIÓN DE LA ROBÓTICA MÉDICA</h1>
            <p>Desde las primeras asistencias estereotácticas de precisión hasta los sistemas quirúrgicos autónomos guiados por IA de última generación.</p>
            <a href="#historia" class="btn-health">EXPLORAR HISTORIA Y AVANCES <i class="fa-solid fa-arrow-right"></i></a>
        </div>
        <a href="#historia" class="scroll-hint" aria-label="Bajar a la historia"><i class="fa-solid fa-chevron-down"></i></a>
    </section>

    <!-- ================= ESTADÍSTICAS ================= -->
    <section id="stats" aria-label="Cifras de la robótica médica">
        <div class="stats-grid">
            <div class="stat-item reveal"><div class="stat-number" data-target="1985">0</div><div class="stat-label">Primer robot en quirófano</div></div>
            <div class="stat-item reveal" data-delay="1"><div class="stat-number" data-target="9000" data-suffix="+">0</div><div class="stat-label">Robots Da Vinci instalados</div></div>
            <div class="stat-item reveal" data-delay="2"><div class="stat-number" data-target="14" data-suffix="M">0</div><div class="stat-label">Procedimientos realizados</div></div>
            <div class="stat-item reveal" data-delay="3"><div class="stat-number" data-target="70" data-suffix="+">0</div><div class="stat-label">Países con cirugía robótica</div></div>
        </div>
    </section>

    <!-- ================= CRONOLOGÍA ================= -->
    <section id="historia">
        <div class="section-header reveal">
            <span class="sub-title">Línea del tiempo histórica</span>
            <h2>Surgimiento y Desarrollo de la Robótica Médica</h2>
            <p class="lead">Cuatro décadas de innovación que transformaron para siempre la forma de operar, diagnosticar y rehabilitar.</p>
        </div>

        <div class="timeline-container">

            <!-- Etapa 1: 1985 -->
            <article class="timeline-card reveal">
                <div class="card-info">
                    <span class="year-tag">1985 · Los inicios</span>
                    <h3>PUMA 560 y la Neurocirugía Estereotáctica</h3>
                    <p>La robótica médica nació en 1985 cuando el Dr. Yik San Kwoh adaptó el brazo industrial <strong>PUMA 560</strong> (Programmable Universal Machine for Assembly) para guiar una aguja de biopsia cerebral mediante tomografía computarizada, con una precisión submilimétrica imposible para la mano humana.</p>
                    <ul>
                        <li>Primer procedimiento quirúrgico asistido por computadora de la historia.</li>
                        <li>Demostró que un robot podía eliminar el temblor del cirujano.</li>
                        <li>Sentó las bases de la cirugía guiada por imágenes médicas.</li>
                    </ul>
                    <div class="card-fact"><i class="fa-solid fa-circle-info"></i>El PUMA 560 fue originalmente un brazo industrial de la marca Unimation.</div>
                </div>
                <div class="image-frame">
                    <img src="https://kimi-web-img.kimi.ai/img/www.maxongroup.com/eaccad824a4723541cbf7c419422438e919617f3.jpg" alt="Brazo robótico médico asistiendo a un paciente en rehabilitación" loading="lazy">
                    <div class="hud-overlay"></div>
                    <span class="image-tag">HISTÓRICO // PUMA 560 ERA</span>
                </div>
            </article>

            <!-- Etapa 2: 1990s -->
            <article class="timeline-card reverse reveal">
                <div class="card-info">
                    <span class="year-tag">1992 – 2001 · Consolidación</span>
                    <h3>ROBODOC, AESOP y el sistema ZEUS</h3>
                    <p>En 1992 <strong>ROBODOC</strong> fresó el fémur en un reemplazo de cadera con precisión milimétrica. Luego llegó <strong>AESOP</strong> (1994), el primer brazo controlado por comandos de voz para sostener endoscopios, y el sistema <strong>ZEUS</strong>, que culminó en 2001 con la operación Lindbergh: la primera telecirugía transatlántica entre Estrasburgo y Nueva York.</p>
                    <ul>
                        <li>AESOP: control laparoscópico manos libres por voz.</li>
                        <li>ZEUS: colecistectomías y cirugía ginecológica mínimamente invasiva.</li>
                        <li>2001: cirugía a distancia a través del océano Atlántico.</li>
                    </ul>
                    <div class="card-fact"><i class="fa-solid fa-circle-info"></i>La operación Lindbergh tuvo un retardo de datos de solo 155 milisegundos.</div>
                </div>
                <div class="image-frame">
                    <img src="https://kimi-web-img.kimi.ai/img/www.expomedhub.com/81f8216fe0c2bc7f7b284f5086bfc7224bbf15d0.jpg" alt="Cirujano operando con instrumentos laparoscópicos asistidos por robot" loading="lazy">
                    <div class="hud-overlay"></div>
                    <span class="image-tag">CIRUGÍA // MÍNIMAMENTE INVASIVA</span>
                </div>
            </article>

            <!-- Etapa 3: Da Vinci -->
            <article class="timeline-card reveal">
                <div class="card-info">
                    <span class="year-tag">2000 – Presente · Era moderna</span>
                    <h3>Sistema Quirúrgico Da Vinci</h3>
                    <p>Aprobado por la FDA en el año 2000, el robot <strong>Da Vinci</strong> de Intuitive Surgical revolucionó los quirófanos del mundo. Convierte los movimientos de las manos del cirujano en micro-movimientos de instrumentos articulados, con visión tridimensional HD magnificada hasta 10 veces y filtrado total del temblor.</p>
                    <ul>
                        <li>Pinzas EndoWrist con 7 grados de libertad, más que la muñeca humana.</li>
                        <li>Consola ergonómica: el cirujano opera sentado con máxima estabilidad.</li>
                        <li>Estándar de oro en urología, ginecología, cardiología y cirugía general.</li>
                    </ul>
                    <div class="card-fact"><i class="fa-solid fa-circle-info"></i>Más de 14 millones de procedimientos realizados con Da Vinci a nivel mundial.</div>
                </div>
                <div class="image-frame">
                    <img src="https://kimi-web-img.kimi.ai/img/clinicrobotics.com/80f1ec857f27a245a5e0703f7e1a6bf994029947.jpg" alt="Sistema quirúrgico Da Vinci con cuatro brazos robóticos en quirófano" loading="lazy">
                    <div class="hud-overlay"></div>
                    <span class="image-tag">SISTEMA DA VINCI // PRECISIÓN 3D</span>
                </div>
            </article>

            <!-- Etapa 4: especialización -->
            <article class="timeline-card reverse reveal">
                <div class="card-info">
                    <span class="year-tag">2010 – 2020 · Especialización</span>
                    <h3>Mako, ROSA y la nueva generación</h3>
                    <p>La robótica se especializó por disciplinas: <strong>Mako</strong> (Stryker) planifica y ejecuta reemplazos de rodilla y cadera con cortes milimétricos; <strong>ROSA</strong> (Zimmer Biomet) guía la colocación de implantes en neurocirugía y columna; y sistemas compactos como <strong>Versius</strong> y <strong>Hugo</strong> democratizan la cirugía robótica en más hospitales.</p>
                    <ul>
                        <li>Mako: cirugía ortopédica asistida con planificación 3D del paciente.</li>
                        <li>ROSA: navegación robótica para cerebro, columna y rodilla.</li>
                        <li>Nuevos sistemas modulares de menor costo y tamaño.</li>
                    </ul>
                    <div class="card-fact"><i class="fa-solid fa-circle-info"></i>Mako trabaja con un brazo háptico que resiste si el cirujano se desvía del plan.</div>
                </div>
                <div class="image-frame">
                    <img src="https://kimi-web-img.kimi.ai/img/urologiaintegralnsr.com/eceff7613fdb227f65ae4ed604a41671ae6ba71a.jpg" alt="Robot quirúrgico Da Vinci instalado en un quirófano de urología" loading="lazy">
                    <div class="hud-overlay"></div>
                    <span class="image-tag">ORTOPEDIA & NEURO // NAVEGACIÓN</span>
                </div>
            </article>

            <!-- Etapa 5: rehabilitación -->
            <article class="timeline-card reveal">
                <div class="card-info">
                    <span class="year-tag">Era actual · Rehabilitación</span>
                    <h3>Exoesqueletos y Robótica de Soporte</h3>
                    <p>Hoy la robótica médica va más allá del quirófano. Los <strong>exoesqueletos biónicos</strong> como EksoNR, ReWalk y HAL devuelven la marcha a personas con lesión medular o parálisis, mientras que robots móviles autónomos desinfectan quirófanos y transportan suministros por los hospitales.</p>
                    <ul>
                        <li>EksoNR y ReWalk: marcha asistida aprobada por la FDA.</li>
                        <li>HAL (Cyberdyne): se controla leyendo las señales bioeléctricas del cerebro.</li>
                        <li>Robots logísticos TUG que trabajan 24/7 en hospitales.</li>
                    </ul>
                    <div class="card-fact"><i class="fa-solid fa-circle-info"></i>El exoesqueleto ReWalk fue el primero autorizado por la FDA para uso personal.</div>
                </div>
                <div class="image-frame">
                    <img src="https://kimi-web-img.kimi.ai/img/blob.medicinaysaludpublica.com/74213edd4cca4fda2edb433b0218e05944d916d1.png" alt="Exoesqueleto robótico aprobado por la FDA ayudando a un paciente a caminar" loading="lazy">
                    <div class="hud-overlay"></div>
                    <span class="image-tag">BIONIC // REHABILITACIÓN ACTIVA</span>
                </div>
            </article>

            <!-- Etapa 6: futuro -->
            <article class="timeline-card reverse reveal">
                <div class="card-info">
                    <span class="year-tag">Futuro · Frontera científica</span>
                    <h3>IA Autónoma y Nanorrobots</h3>
                    <p>La próxima frontera combina <strong>inteligencia artificial</strong> con micro-robótica: sistemas capaces de reconocer tejidos en tiempo real, suturar de forma semi-autónoma y <strong>nanorrobots</strong> que navegarán por el torrente sanguíneo para administrar fármacos directamente sobre tumores o eliminar placas de arterias.</p>
                    <ul>
                        <li>Algoritmos de visión por computadora para identificar anatomía en vivo.</li>
                        <li>Microrrobots magnéticos guiados por campos externos.</li>
                        <li>Cirugía teledirigida por redes 5G con latencia mínima.</li>
                    </ul>
                    <div class="card-fact"><i class="fa-solid fa-circle-info"></i>Investigadores ya prueban nanorrobots que perforan biofilms bacterianos en laboratorio.</div>
                </div>
                <div class="image-frame">
                    <img src="https://kimi-web-img.kimi.ai/img/www.redeweb.com/a61d5236cea6f0f154927f211f38fc2fe2bcd082.jpeg" alt="Robot médico autónomo del futuro en una habitación hospitalaria" loading="lazy">
                    <div class="hud-overlay"></div>
                    <span class="image-tag">FUTURO // IA & NANOMEDICINA</span>
                </div>
            </article>

        </div>
    </section>

    <!-- ================= GALERÍA ================= -->
    <section id="galeria">
        <div class="section-header reveal">
            <span class="sub-title">Robótica médica en imágenes</span>
            <h2>Galería de Tecnología Sanitaria</h2>
            <p class="lead">Un recorrido visual por los robots que ya están salvando vidas. Haz clic para ampliar.</p>
        </div>

        <div class="gallery-grid">
            <figure class="gallery-item reveal"><img src="https://kimi-web-img.kimi.ai/img/lasaludhospital.es/9b397ec020a08d0a6a8debad03fd53b4d348b437.jpg" alt="Brazos articulados de robot quirúrgico sobre mesa de operaciones" loading="lazy"><figcaption class="gallery-caption">Brazos articulados de precisión</figcaption></figure>
            <figure class="gallery-item reveal" data-delay="1"><img src="https://kimi-web-img.kimi.ai/img/images.ecestaticos.com/dbda9bfa965c8d2b9e5d4f7fe9733f4935cb15ef.jpg" alt="Equipo de cirujanos operando con asistencia robótica en neurocirugía" loading="lazy"><figcaption class="gallery-caption">Neurocirugía y columna asistida</figcaption></figure>
            <figure class="gallery-item reveal" data-delay="2"><img src="https://kimi-web-img.kimi.ai/img/blob.medicinaysaludpublica.com/c0005f229b648975a10941feea5e431f90544022.webp" alt="Robot humanoide asistiendo en tareas de atención hospitalaria" loading="lazy"><figcaption class="gallery-caption">Humanoides hospitalarios</figcaption></figure>
            <figure class="gallery-item reveal" data-delay="3"><img src="https://kimi-web-img.kimi.ai/img/m.media-amazon.com/7d5f0361004345558abc4a723ca4ddbe5b9c1afc.jpg" alt="Exoesqueleto de cadera para asistencia de movilidad" loading="lazy"><figcaption class="gallery-caption">Exoesqueleto de asistencia de marcha</figcaption></figure>
        </div>
    </section>

    <!-- Lightbox -->
    <div id="lightbox" role="dialog" aria-label="Visor de imágenes">
        <button id="lightbox-close" aria-label="Cerrar visor"><i class="fa-solid fa-xmark"></i></button>
        <img src="" alt="Imagen ampliada">
    </div>

    <!-- ================= CLASIFICACIÓN ================= -->
    <section id="clasificacion">
        <div class="section-header reveal">
            <span class="sub-title">Áreas de aplicación</span>
            <h2>Clasificación de los Sistemas Robóticos en Salud</h2>
        </div>

        <div class="grid-categories">

            <article class="category-card reveal">
                <img class="category-img" src="https://kimi-web-img.kimi.ai/img/urologiaintegralnsr.com/eceff7613fdb227f65ae4ed604a41671ae6ba71a.jpg" alt="Robot quirúrgico en quirófano" loading="lazy">
                <div class="category-body">
                    <div class="icon-wrapper"><i class="fa-solid fa-user-doctor"></i></div>
                    <h3>Robots Quirúrgicos</h3>
                    <p>Sistemas de asistencia de alta precisión que amplifican las capacidades del cirujano: filtran el temblor, magnifican la visión 10x en 3D y reducen sangrado y tiempo de recuperación. Ejemplos: Da Vinci, Mako, ROSA, Versius.</p>
                    <div class="card-stat"><i class="fa-solid fa-arrow-trend-up"></i>7 grados de libertad por instrumento</div>
                </div>
            </article>

            <article class="category-card reveal" data-delay="1">
                <img class="category-img" src="https://kimi-web-img.kimi.ai/img/blob.medicinaysaludpublica.com/74213edd4cca4fda2edb433b0218e05944d916d1.png" alt="Exoesqueleto biónico en rehabilitación" loading="lazy">
                <div class="category-body">
                    <div class="icon-wrapper"><i class="fa-solid fa-person-walking-with-cane"></i></div>
                    <h3>Robots de Rehabilitación</h3>
                    <p>Exoesqueletos y prótesis biónicas que guían la terapia de extremidades en pacientes con parálisis, ACV o lesión medular. Repiten el patrón de marcha miles de veces con la constancia que un terapeuta no puede.</p>
                    <div class="card-stat"><i class="fa-solid fa-arrow-trend-up"></i>EksoNR · ReWalk · HAL aprobados por FDA</div>
                </div>
            </article>

            <article class="category-card reveal" data-delay="2">
                <img class="category-img" src="https://kimi-web-img.kimi.ai/img/www.redeweb.com/a61d5236cea6f0f154927f211f38fc2fe2bcd082.jpeg" alt="Robot logístico en habitación hospitalaria" loading="lazy">
                <div class="category-body">
                    <div class="icon-wrapper"><i class="fa-solid fa-pills"></i></div>
                    <h3>Robots Farmacéuticos</h3>
                    <p>Dispensadores automáticos que preparan mezclas intravenosas y administran dosis unitarias con trazabilidad total. Los robots logísticos como TUG transportan medicamentos y suministros por los pasillos del hospital.</p>
                    <div class="card-stat"><i class="fa-solid fa-arrow-trend-up"></i>Cero errores en millones de dosis dispensadas</div>
                </div>
            </article>

            <article class="category-card reveal">
                <img class="category-img" src="https://kimi-web-img.kimi.ai/img/images.ecestaticos.com/dbda9bfa965c8d2b9e5d4f7fe9733f4935cb15ef.jpg" alt="Quirófano con equipo de desinfección robótica" loading="lazy">
                <div class="category-body">
                    <div class="icon-wrapper"><i class="fa-solid fa-pump-medical"></i></div>
                    <h3>Robots de Desinfección UVC</h3>
                    <p>Equipos móviles autónomos con escáners LiDAR que recorren salas de cirugía emitiendo radiación ultravioleta de onda corta, erradicando bacterias, virus y esporas en minutos sin químicos.</p>
                    <div class="card-stat"><i class="fa-solid fa-arrow-trend-up"></i>Eliminan hasta el 99.99% de patógenos</div>
                </div>
            </article>

            <article class="category-card reveal" data-delay="1">
                <img class="category-img" src="https://kimi-web-img.kimi.ai/img/www.maxongroup.com/eaccad824a4723541cbf7c419422438e919617f3.jpg" alt="Brazo robótico de alta precisión médica" loading="lazy">
                <div class="category-body">
                    <div class="icon-wrapper"><i class="fa-solid fa-microscope"></i></div>
                    <h3>Nanorrobótica Diagnóstica</h3>
                    <p>Dispositivos a escala microscópica en fase experimental: microrrobots magnéticos que navegan por el torrente sanguíneo para administrar fármacos directamente sobre tumores o capturar muestras de tejido.</p>
                    <div class="card-stat"><i class="fa-solid fa-arrow-trend-up"></i>Ya probados en modelos animales</div>
                </div>
            </article>

            <article class="category-card reveal" data-delay="2">
                <img class="category-img" src="https://kimi-web-img.kimi.ai/img/blob.medicinaysaludpublica.com/c0005f229b648975a10941feea5e431f90544022.webp" alt="Robot de teleasistencia en hospital" loading="lazy">
                <div class="category-body">
                    <div class="icon-wrapper"><i class="fa-solid fa-headset"></i></div>
                    <h3>Telemedicina y Telepresencia</h3>
                    <p>Plataformas móviles con cámaras HD y estetoscopios digitales que permiten a especialistas pasar consulta, revisar pacientes y dictaminar diagnósticos en zonas remotas en tiempo real.</p>
                    <div class="card-stat"><i class="fa-solid fa-arrow-trend-up"></i>Salva distancias de miles de kilómetros</div>
                </div>
            </article>

        </div>
    </section>

    <!-- ================= FOOTER ================= -->
    <footer id="footer">
        <div class="footer-body">
            <h3>ROBOMEDIX</h3>
            <p>Cuidando vidas mediante la innovación, la ingeniería de precisión y la ciencia médica.</p>
            <div class="social-links">
                <a href="#" aria-label="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="#" aria-label="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
                <a href="#" aria-label="Hospital"><i class="fa-solid fa-hospital"></i></a>
            </div>
        </div>
        <div class="copyright">
            <p>© 2026 RoboMedix - Salud, Ciencia y Robótica de Precisión.</p>
        </div>
    </footer>

</div>

<!-- ================= SCRIPTS ================= -->
<script>
(function () {
    'use strict';

    /* 1. Menú móvil */
    const menuToggle = document.getElementById('menu-toggle');
    const nav = document.getElementById('nav');
    menuToggle.addEventListener('click', () => {
        const open = nav.classList.toggle('open');
        menuToggle.innerHTML = open ? '<i class="fa-solid fa-xmark"></i>' : '<i class="fa-solid fa-bars"></i>';
    });
    document.querySelectorAll('#nav a').forEach(a =>
        a.addEventListener('click', () => {
            nav.classList.remove('open');
            menuToggle.innerHTML = '<i class="fa-solid fa-bars"></i>';
        })
    );

    /* 2. Resaltar enlace activo según sección visible */
    const navLinks = document.querySelectorAll('#nav a');
    function highlightNav() {
        let current = 'hero';
        document.querySelectorAll('section[id]').forEach(sec => {
            if (window.scrollY >= sec.offsetTop - 140) current = sec.id;
        });
        navLinks.forEach(l => l.classList.toggle('active', l.getAttribute('href') === '#' + current));
    }
    window.addEventListener('scroll', highlightNav, { passive: true });
    highlightNav();

    /* 3. Scroll reveal (con IntersectionObserver) */
    const revealObs = new IntersectionObserver(entries => {
        entries.forEach(e => {
            if (e.isIntersecting) { e.target.classList.add('active'); revealObs.unobserve(e.target); }
        });
    }, { threshold: 0.12 });
    document.querySelectorAll('.reveal').forEach(el => revealObs.observe(el));

    /* 4. Contadores animados */
    const counterObs = new IntersectionObserver(entries => {
        entries.forEach(entry => {
            if (!entry.isIntersecting) return;
            const el = entry.target;
            const target = +el.dataset.target;
            const suffix = el.dataset.suffix || '';
            const dur = 1600, start = performance.now();
            (function tick(now) {
                const p = Math.min((now - start) / dur, 1);
                el.textContent = Math.round(target * (1 - Math.pow(1 - p, 3))).toLocaleString('es') + (p === 1 ? suffix : '');
                if (p < 1) requestAnimationFrame(tick);
            })(start);
            counterObs.unobserve(el);
        });
    }, { threshold: 0.6 });
    document.querySelectorAll('.stat-number').forEach(el => counterObs.observe(el));

    /* 5. Fondo de partículas */
    const canvas = document.getElementById('particles-canvas');
    const ctx = canvas.getContext('2d');
    let particles = [];

    function resize() {
        canvas.width = window.innerWidth;
        canvas.height = document.getElementById('hero').offsetHeight;
    }
    resize();
    window.addEventListener('resize', () => { resize(); init(); });

    class Particle {
        constructor() {
            this.x = Math.random() * canvas.width;
            this.y = Math.random() * canvas.height;
            this.size = Math.random() * 2 + 1;
            this.speedX = (Math.random() - 0.5) * 0.7;
            this.speedY = (Math.random() - 0.5) * 0.7;
        }
        update() {
            this.x += this.speedX; this.y += this.speedY;
            if (this.x < 0 || this.x > canvas.width) this.speedX *= -1;
            if (this.y < 0 || this.y > canvas.height) this.speedY *= -1;
        }
        draw() {
            ctx.fillStyle = '#00f5c4';
            ctx.beginPath();
            ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
            ctx.fill();
        }
    }

    function init() {
        particles = [];
        const n = Math.min((canvas.width * canvas.height) / 10000, 150);
        for (let i = 0; i < n; i++) particles.push(new Particle());
    }

    function animate() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        for (let i = 0; i < particles.length; i++) {
            particles[i].update(); particles[i].draw();
            for (let j = i + 1; j < particles.length; j++) {
                const d = Math.hypot(particles[i].x - particles[j].x, particles[i].y - particles[j].y);
                if (d < 110) {
                    ctx.beginPath();
                    ctx.strokeStyle = `rgba(0,245,196,${1 - d / 110})`;
                    ctx.lineWidth = 0.5;
                    ctx.moveTo(particles[i].x, particles[i].y);
                    ctx.lineTo(particles[j].x, particles[j].y);
                    ctx.stroke();
                }
            }
        }
        requestAnimationFrame(animate);
    }
    init(); animate();

    /* 6. Efecto tilt 3D */
    document.querySelectorAll('.timeline-card').forEach(card => {
        card.addEventListener('mousemove', e => {
            const r = card.getBoundingClientRect();
            const rx = (e.clientY - r.top - r.height / 2) / 25;
            const ry = (r.width / 2 - (e.clientX - r.left)) / 25;
            card.style.transform = `perspective(1000px) rotateX(${rx}deg) rotateY(${ry}deg)`;
        });
        card.addEventListener('mouseleave', () => {
            card.style.transform = 'perspective(1000px) rotateX(0deg) rotateY(0deg)';
        });
    });

    /* 7. Lightbox de galería */
    const lightbox = document.getElementById('lightbox');
    const lbImg = lightbox.querySelector('img');
    document.querySelectorAll('.gallery-item').forEach(item => {
        item.addEventListener('click', () => {
            const img = item.querySelector('img');
            lbImg.src = img.src; lbImg.alt = img.alt;
            lightbox.classList.add('open');
            document.body.style.overflow = 'hidden';
        });
    });
    const closeLb = () => { lightbox.classList.remove('open'); document.body.style.overflow = ''; };
    document.getElementById('lightbox-close').addEventListener('click', closeLb);
    lightbox.addEventListener('click', e => { if (e.target === lightbox) closeLb(); });
    document.addEventListener('keydown', e => { if (e.key === 'Escape') closeLb(); });
</script>

</body>
</html>
