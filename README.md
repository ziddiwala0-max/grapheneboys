<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#050508">

<title>GRAPHENEBOYS — The Beginning</title>

<style>

@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&family=Poppins:wght@300;400;500;600;700&display=swap');

:root{
    --bg:#050508;
    --bg2:#0b0b12;
    --card:#11111a;
    --purple:#9b4dff;
    --purple2:#6f20ff;
    --cyan:#00e5ff;
    --white:#f5f5f7;
    --muted:#9b9ba8;
    --border:rgba(255,255,255,.09);
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    scroll-behavior:smooth;
}

body{
    background:var(--bg);
    color:var(--white);
    font-family:Poppins,sans-serif;
    overflow-x:hidden;
}

/* BACKGROUND */

.bg-glow{
    position:fixed;
    width:600px;
    height:600px;
    border-radius:50%;
    background:rgba(112,35,255,.13);
    filter:blur(100px);
    top:-250px;
    left:-250px;
    z-index:-2;
    pointer-events:none;
}

.bg-glow.two{
    width:500px;
    height:500px;
    top:60%;
    left:auto;
    right:-250px;
    background:rgba(0,200,255,.08);
}

.grid{
    position:fixed;
    inset:0;
    background-image:
        linear-gradient(rgba(255,255,255,.025) 1px,transparent 1px),
        linear-gradient(90deg,rgba(255,255,255,.025) 1px,transparent 1px);
    background-size:60px 60px;
    mask-image:linear-gradient(to bottom,black,transparent 80%);
    pointer-events:none;
    z-index:-3;
}

/* LOADER */

.loader{
    position:fixed;
    inset:0;
    background:#030305;
    z-index:9999;
    display:flex;
    align-items:center;
    justify-content:center;
    transition:.7s ease;
}

.loader.hide{
    opacity:0;
    pointer-events:none;
}

.loader-content{
    text-align:center;
}

.loader-logo{
    font-family:Orbitron,sans-serif;
    font-size:clamp(28px,7vw,65px);
    font-weight:900;
    letter-spacing:8px;
    background:linear-gradient(90deg,#fff,#a24dff,#00e5ff);
    -webkit-background-clip:text;
    color:transparent;
    animation:pulse 1.5s infinite alternate;
}

.loader-line{
    width:180px;
    height:2px;
    background:rgba(255,255,255,.15);
    margin:25px auto 12px;
    overflow:hidden;
}

.loader-line span{
    display:block;
    width:40%;
    height:100%;
    background:var(--purple);
    animation:loading 1.2s infinite;
}

.loader-text{
    font-size:11px;
    letter-spacing:4px;
    color:#777;
}

/* NAVBAR */

nav{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:75px;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 6%;
    z-index:1000;
    background:rgba(5,5,8,.55);
    backdrop-filter:blur(18px);
    border-bottom:1px solid transparent;
    transition:.3s;
}

nav.scrolled{
    border-bottom-color:var(--border);
    background:rgba(5,5,8,.88);
}

.logo{
    font-family:Orbitron,sans-serif;
    font-weight:900;
    font-size:21px;
    letter-spacing:3px;
}

.logo span{
    color:var(--purple);
}

.nav-links{
    display:flex;
    gap:30px;
    list-style:none;
}

.nav-links a{
    color:#aaa;
    text-decoration:none;
    font-size:13px;
    transition:.3s;
}

.nav-links a:hover{
    color:#fff;
}

.nav-button{
    border:1px solid rgba(155,77,255,.6);
    padding:9px 17px;
    border-radius:30px;
    color:#fff !important;
    background:rgba(155,77,255,.08);
}

.menu{
    display:none;
    font-size:27px;
    cursor:pointer;
}

/* HERO */

.hero{
    min-height:100vh;
    display:flex;
    align-items:center;
    position:relative;
    padding:120px 7% 80px;
    overflow:hidden;
}

.hero-content{
    max-width:850px;
    z-index:2;
}

.eyebrow{
    display:inline-flex;
    align-items:center;
    gap:10px;
    padding:8px 14px;
    border:1px solid rgba(155,77,255,.35);
    background:rgba(155,77,255,.06);
    border-radius:50px;
    color:#cba9ff;
    font-size:11px;
    letter-spacing:2px;
    margin-bottom:25px;
}

.dot{
    width:7px;
    height:7px;
    border-radius:50%;
    background:#b45cff;
    box-shadow:0 0 15px #9b4dff;
}

.hero h1{
    font-family:Orbitron,sans-serif;
    font-size:clamp(45px,9vw,105px);
    line-height:.95;
    letter-spacing:-3px;
    font-weight:900;
}

.gradient{
    background:linear-gradient(90deg,#fff 10%,#b865ff 55%,#00dfff);
    -webkit-background-clip:text;
    color:transparent;
}

.hero-sub{
    margin-top:25px;
    max-width:650px;
    color:#a6a6b2;
    line-height:1.8;
    font-size:15px;
}

.hero-buttons{
    display:flex;
    gap:14px;
    margin-top:35px;
    flex-wrap:wrap;
}

.btn{
    text-decoration:none;
    color:white;
    padding:14px 23px;
    border-radius:7px;
    font-size:13px;
    font-weight:600;
    display:inline-flex;
    align-items:center;
    gap:9px;
    transition:.3s;
    border:1px solid var(--border);
}

.btn-primary{
    background:linear-gradient(135deg,#8d3cff,#5e16e9);
    box-shadow:0 0 30px rgba(140,50,255,.2);
}

.btn-primary:hover{
    transform:translateY(-3px);
    box-shadow:0 10px 40px rgba(140,50,255,.35);
}

.btn-outline:hover{
    background:rgba(255,255,255,.07);
}

.hero-meta{
    display:flex;
    gap:35px;
    margin-top:60px;
}

.meta-item small{
    display:block;
    color:#666;
    font-size:9px;
    letter-spacing:2px;
    margin-bottom:5px;
}

.meta-item strong{
    font-family:Orbitron,sans-serif;
    font-size:12px;
}

.hero-orb{
    position:absolute;
    width:550px;
    height:550px;
    right:2%;
    top:50%;
    transform:translateY(-50%);
    border-radius:50%;
    border:1px solid rgba(155,77,255,.25);
    box-shadow:
        0 0 100px rgba(110,25,255,.12),
        inset 0 0 100px rgba(110,25,255,.08);
    animation:float 5s ease-in-out infinite;
}

.hero-orb:before,
.hero-orb:after{
    content:"";
    position:absolute;
    inset:45px;
    border:1px solid rgba(0,229,255,.18);
    border-radius:50%;
    transform:rotate(35deg) scaleX(1.7);
}

.hero-orb:after{
    transform:rotate(-35deg) scaleX(1.7);
}

.orb-core{
    position:absolute;
    width:150px;
    height:150px;
    border-radius:50%;
    background:radial-gradient(circle,#fff 0%,#bd6cff 15%,#691dff 45%,transparent 70%);
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    box-shadow:0 0 100px #7c2cff;
}

/* SECTIONS */

section{
    padding:110px 7%;
    position:relative;
}

.section-head{
    margin-bottom:50px;
}

.section-tag{
    font-size:10px;
    letter-spacing:4px;
    color:var(--purple);
    margin-bottom:12px;
}

.section-title{
    font-family:Orbitron,sans-serif;
    font-size:clamp(27px,4vw,48px);
    letter-spacing:-1px;
}

.section-desc{
    color:#777;
    max-width:650px;
    line-height:1.8;
    margin-top:13px;
    font-size:14px;
}

/* STORY */

.story{
    background:linear-gradient(
        180deg,
        transparent,
        rgba(112,35,255,.035),
        transparent
    );
}

.story-grid{
    display:grid;
    grid-template-columns:1.2fr .8fr;
    gap:60px;
    align-items:center;
}

.story-text{
    color:#a9a9b2;
    line-height:2;
    font-size:14px;
}

.story-text strong{
    color:#fff;
}

.story-box{
    border:1px solid var(--border);
    background:rgba(255,255,255,.025);
    padding:30px;
    border-radius:15px;
}

.story-box .year{
    font-family:Orbitron,sans-serif;
    color:var(--purple);
    font-size:45px;
    font-weight:800;
}

.story-box h3{
    margin:10px 0;
}

.story-box p{
    color:#777;
    font-size:13px;
    line-height:1.8;
}

/* STONES */

.stones{
    display:grid;
    grid-template-columns:repeat(7,1fr);
    gap:12px;
}

.stone{
    aspect-ratio:1/1.25;
    border:1px solid var(--border);
    background:linear-gradient(145deg,#12121c,#09090d);
    border-radius:13px;
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    gap:12px;
    transition:.4s;
    cursor:pointer;
    position:relative;
    overflow:hidden;
}

.stone:before{
    content:"";
    position:absolute;
    width:70px;
    height:70px;
    border-radius:50%;
    background:var(--stone);
    filter:blur(35px);
    opacity:.25;
}

.stone:hover{
    transform:translateY(-8px);
    border-color:rgba(255,255,255,.25);
}

.stone-icon{
    width:45px;
    height:45px;
    transform:rotate(45deg);
    background:var(--stone);
    box-shadow:0 0 25px var(--stone);
    border-radius:6px;
}

.stone span{
    font-family:Orbitron,sans-serif;
    font-size:10px;
    color:#aaa;
    letter-spacing:1px;
}

/* VIDEO */

.trailer-box{
    width:100%;
    aspect-ratio:16/9;
    min-height:400px;
    border-radius:20px;
    border:1px solid var(--border);
    overflow:hidden;
    background:#000;
    position:relative;
    box-shadow:
        0 0 80px rgba(120,40,255,.08);
}

.trailer-box iframe{
    width:100%;
    height:100%;
    border:0;
    display:block;
}

.video-label{
    position:absolute;
    bottom:18px;
    left:20px;
    z-index:3;
    pointer-events:none;
    background:rgba(0,0,0,.55);
    backdrop-filter:blur(10px);
    border:1px solid rgba(255,255,255,.1);
    padding:8px 13px;
    border-radius:5px;
    font-family:Orbitron,sans-serif;
    font-size:9px;
    letter-spacing:2px;
}

/* MANGA */

.manga-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:18px;
}

.manga-card{
    border:1px solid var(--border);
    background:#0c0c12;
    border-radius:15px;
    overflow:hidden;
    transition:.3s;
}

.manga-card:hover{
    transform:translateY(-5px);
}

.manga-cover{
    height:240px;
    display:flex;
    align-items:flex-end;
    padding:20px;
    background:
        radial-gradient(
            circle at 70% 30%,
            rgba(0,229,255,.25),
            transparent 30%
        ),
        linear-gradient(135deg,#171125,#07070a);
}

.manga-cover h3{
    font-family:Orbitron,sans-serif;
}

.manga-info{
    padding:18px;
}

.manga-info p{
    color:#777;
    font-size:11px;
    margin-bottom:15px;
}

.manga-info a{
    color:#b66cff;
    font-size:11px;
    text-decoration:none;
}

/* ANIMATION TEAM */

.team{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:20px;
}

.team-card{
    border:1px solid var(--border);
    border-radius:18px;
    background:linear-gradient(
        145deg,
        rgba(255,255,255,.045),
        rgba(255,255,255,.015)
    );
    overflow:hidden;
    transition:.4s;
    text-align:center;
}

.team-card:hover{
    transform:translateY(-8px);
    border-color:rgba(155,77,255,.5);
    box-shadow:0 20px 60px rgba(100,30,255,.12);
}

.team-photo-wrap{
    height:300px;
    background:
        radial-gradient(
            circle,
            rgba(155,77,255,.18),
            transparent 60%
        );
    overflow:hidden;
}

.team-photo{
    width:100%;
    height:100%;
    object-fit:cover;
    transition:.5s;
}

.team-card:hover .team-photo{
    transform:scale(1.05);
}

.team-info{
    padding:22px;
}

.team-role{
    color:var(--purple);
    font-size:9px;
    letter-spacing:3px;
}

.team-info h3{
    font-family:Orbitron,sans-serif;
    font-size:17px;
    margin-top:7px;
}

.team-info p{
    color:#666;
    font-size:11px;
    margin-top:7px;
}

/* SOCIAL */

.socials{
    display:flex;
    gap:14px;
    flex-wrap:wrap;
}

.social{
    flex:1;
    min-width:180px;
    padding:25px;
    border:1px solid var(--border);
    border-radius:13px;
    background:rgba(255,255,255,.02);
    text-decoration:none;
    color:#fff;
    transition:.3s;
}

.social:hover{
    background:rgba(155,77,255,.08);
    border-color:rgba(155,77,255,.35);
}

.social small{
    color:#666;
    display:block;
    font-size:9px;
    letter-spacing:2px;
    margin-bottom:8px;
}

.social strong{
    font-family:Orbitron,sans-serif;
    font-size:14px;
}

/* FOOTER */

footer{
    border-top:1px solid var(--border);
    padding:45px 7%;
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:20px;
}

.footer-logo{
    font-family:Orbitron,sans-serif;
    font-weight:900;
    letter-spacing:3px;
}

footer p{
    color:#555;
    font-size:10px;
}

/* REVEAL */

.reveal{
    opacity:0;
    transform:translateY(30px);
    transition:
        opacity .8s ease,
        transform .8s ease;
}

.reveal.active{
    opacity:1;
    transform:none;
}

/* RESPONSIVE */

@media(max-width:950px){

    .hero-orb{
        opacity:.25;
        right:-200px;
    }

    .story-grid{
        grid-template-columns:1fr;
    }

    .stones{
        grid-template-columns:repeat(4,1fr);
    }

    .team{
        grid-template-columns:repeat(3,1fr);
    }
}

@media(max-width:700px){

    nav{
        height:65px;
        padding:0 5%;
    }

    .nav-links{
        position:absolute;
        top:65px;
        left:0;
        width:100%;
        flex-direction:column;
        gap:0;
        background:rgba(5,5,8,.97);
        backdrop-filter:blur(20px);
        border-bottom:1px solid var(--border);
        max-height:0;
        overflow:hidden;
        transition:.4s;
    }

    .nav-links.open{
        max-height:400px;
    }

    .nav-links li{
        padding:17px 25px;
        border-bottom:1px solid rgba(255,255,255,.04);
    }

    .menu{
        display:block;
    }

    .hero{
        padding:120px 6% 70px;
    }

    .hero h1{
        font-size:clamp(40px,13vw,70px);
    }

    .hero-sub{
        font-size:13px;
    }

    .hero-meta{
        gap:20px;
        margin-top:40px;
        flex-wrap:wrap;
    }

    section{
        padding:80px 6%;
    }

    .stones{
        grid-template-columns:repeat(2,1fr);
    }

    .manga-grid{
        grid-template-columns:1fr;
    }

    .team{
        grid-template-columns:1fr;
    }

    .team-photo-wrap{
        height:330px;
    }

    .trailer-box{
        min-height:230px;
        border-radius:12px;
    }

    footer{
        flex-direction:column;
        align-items:flex-start;
    }
}

@media(max-width:400px){

    .hero-buttons{
        flex-direction:column;
    }

    .btn{
        justify-content:center;
    }

    .stones{
        gap:8px;
    }
}

/* ANIMATIONS */

@keyframes pulse{
    from{opacity:.65}
    to{opacity:1}
}

@keyframes loading{
    0%{transform:translateX(-150%)}
    100%{transform:translateX(400%)}
}

@keyframes float{
    0%,100%{
        transform:translateY(-50%) translateY(0);
    }

    50%{
        transform:translateY(-50%) translateY(-15px);
    }
}

</style>
</head>

<body>

<!-- LOADER -->

<div class="loader" id="loader">

    <div class="loader-content">

        <div class="loader-logo">
            GRAPHENEBOYS
        </div>

        <div class="loader-line">
            <span></span>
        </div>

        <div class="loader-text">
            ENTERING THE WORLD
        </div>

    </div>

</div>


<div class="bg-glow"></div>
<div class="bg-glow two"></div>
<div class="grid"></div>


<!-- NAVBAR -->

<nav id="navbar">

    <div class="logo">
        GRAPHENE<span>BOYS</span>
    </div>

    <div class="menu" id="menu">
        ☰
    </div>

    <ul class="nav-links" id="navLinks">

        <li>
            <a href="#home">Home</a>
        </li>

        <li>
            <a href="#story">Story</a>
        </li>

        <li>
            <a href="#trailer">Trailer</a>
        </li>

        <li>
            <a href="#manga">Manga</a>
        </li>

        <li>
            <a href="#team">Creators</a>
        </li>

        <li>
            <a href="#social" class="nav-button">
                Follow
            </a>
        </li>

    </ul>

</nav>


<!-- HERO -->

<header class="hero" id="home">

    <div class="hero-content">

        <div class="eyebrow">
            <span class="dot"></span>
            AN ORIGINAL ANIME PROJECT
        </div>

        <h1>
            GRAPHENE<br>
            <span class="gradient">BOYS</span>
        </h1>

        <p class="hero-sub">
            Chapter 01 — The Beginning.
            In a world where power is created, controlled and hidden,
            one ordinary boy becomes the vessel of something ancient.
        </p>

        <div class="hero-buttons">

            <a href="#trailer" class="btn btn-primary">
                ▶ WATCH TEASER
            </a>

            <a href="#story" class="btn btn-outline">
                EXPLORE THE WORLD
            </a>

        </div>

        <div class="hero-meta">

            <div class="meta-item">
                <small>STATUS</small>
                <strong>COMING 2027</strong>
            </div>

            <div class="meta-item">
                <small>CHAPTER</small>
                <strong>01</strong>
            </div>

            <div class="meta-item">
                <small>FORMAT</small>
                <strong>ANIME / MANGA</strong>
            </div>

        </div>

    </div>


    <div class="hero-orb">

        <div class="orb-core"></div>

    </div>

</header>


<!-- STORY -->

<section class="story reveal" id="story">

    <div class="section-head">

        <div class="section-tag">
            THE WORLD
        </div>

        <h2 class="section-title">
            A POWER THAT SHOULD NEVER EXIST.
        </h2>

        <p class="section-desc">
            The beginning of the GrapheneBoys universe.
        </p>

    </div>


    <div class="story-grid">

        <div class="story-text">

            <p>
                <strong>2029.</strong>
                The world has entered a new era of human enhancement.
                <strong>DarkCom Institute</strong> publicly promises a future
                where human potential has no limits.
            </p>

            <br>

            <p>
                But behind the laboratories lies a secret.
                DarkCom is working with the mysterious
                <strong>Ruler No. 1</strong>.
            </p>

            <br>

            <p>
                An ancient <strong>Power Stone</strong> becomes the center
                of their experiments. Its energy is sealed inside
                an ordinary young man named <strong>Vihaan</strong>.
            </p>

            <br>

            <p>
                He thought he was joining DarkCom to build a better future.
                Instead, he became part of something much bigger.
            </p>

        </div>


        <div class="story-box">

            <div class="year">
                2029
            </div>

            <h3>
                THE NEW ERA
            </h3>

            <p>
                Seven stones. Seven rulers.
                Seven individuals connected by a power
                capable of changing the world.
            </p>

        </div>

    </div>

</section>


<!-- SEVEN STONES -->

<section class="reveal">

    <div class="section-head">

        <div class="section-tag">
            THE SEVEN
        </div>

        <h2 class="section-title">
            THE SEVEN STONES
        </h2>

        <p class="section-desc">
            Ancient powers scattered across the world.
            Their true purpose remains unknown.
        </p>

    </div>


    <div class="stones">

        <div class="stone" style="--stone:#a64cff;">
            <div class="stone-icon"></div>
            <span>POWER</span>
        </div>

        <div class="stone" style="--stone:#00d9ff;">
            <div class="stone-icon"></div>
            <span>???</span>
        </div>

        <div class="stone" style="--stone:#ff3d68;">
            <div class="stone-icon"></div>
            <span>???</span>
        </div>

        <div class="stone" style="--stone:#ffd43d;">
            <div class="stone-icon"></div>
            <span>???</span>
        </div>

        <div class="stone" style="--stone:#42ff88;">
            <div class="stone-icon"></div>
            <span>???</span>
        </div>

        <div class="stone" style="--stone:#ff7a32;">
            <div class="stone-icon"></div>
            <span>???</span>
        </div>

        <div class="stone" style="--stone:#e94cff;">
            <div class="stone-icon"></div>
            <span>???</span>
        </div>

    </div>

</section>


<!-- VIDEO -->

<section id="trailer" class="reveal">

    <div class="section-head">

        <div class="section-tag">
            OFFICIAL TEASER
        </div>

        <h2 class="section-title">
            THE FIRST LOOK
        </h2>

        <p class="section-desc">
            The story begins.
        </p>

    </div>


    <div class="trailer-box">

        <!-- YOUTUBE VIDEO -->

        <iframe
            src="https://www.youtube.com/embed/2LuW5WTGCfI?controls=1&rel=0&playsinline=1"
            title="GRAPHENEBOYS — Official Teaser"
            loading="lazy"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            referrerpolicy="strict-origin-when-cross-origin"
            allowfullscreen>
        </iframe>

    </div>

</section>


<!-- MANGA -->

<section id="manga" class="reveal">

    <div class="section-head">

        <div class="section-tag">
            MANGA
        </div>

        <h2 class="section-title">
            CHAPTER 01
        </h2>

        <p class="section-desc">
            The story begins before the world understands what is coming.
        </p>

    </div>


    <div class="manga-grid">

        <div class="manga-card">

            <div class="manga-cover">
                <h3>
                    THE<br>
                    BEGINNING
                </h3>
            </div>

            <div class="manga-info">

                <p>
                    A normal life. A mysterious institute.
                    And a power hidden inside.
                </p>

                <a href="#">
                    READ CHAPTER →
                </a>

            </div>

        </div>


        <div class="manga-card">

            <div class="manga-cover">
                <h3>
                    THE<br>
                    POWER STONE
                </h3>
            </div>

            <div class="manga-info">

                <p>
                    An ancient stone awakens something
                    that was never meant to be awakened.
                </p>

                <a href="#">
                    COMING SOON →
                </a>

            </div>

        </div>


        <div class="manga-card">

            <div class="manga-cover">
                <h3>
                    THE<br>
                    SEVEN
                </h3>
            </div>

            <div class="manga-info">

                <p>
                    Seven friends.
                    Seven destinies.
                    One impossible future.
                </p>

                <a href="#">
                    COMING SOON →
                </a>

            </div>

        </div>

    </div>

</section>


<!-- ANIMATION TEAM -->

<section id="team" class="reveal">

    <div class="section-head">

        <div class="section-tag">
            THE TEAM
        </div>

        <h2 class="section-title">
            ANIMATED BY
        </h2>

        <p class="section-desc">
            Three people bringing the GrapheneBoys universe to life.
        </p>

    </div>


    <div class="team">


        <!-- BILAL -->

        <div class="team-card">

            <div class="team-photo-wrap">

                <img
                    class="team-photo"
                    src="https://imgs.search.brave.com/YCu_9iD7CZ1FOdp9Sh8loOVjVNo9TzHwnT5ZvmLho1o/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly9zdGF0/aWMucm9ja2V0cmVh/Y2guY28vaW1hZ2Vz/L3Byb2ZpbGVfcGlj/cy92Mi4xL2RwcG05/LnBuZw"
                    alt="Patel Bilal Husain"
                >

            </div>

            <div class="team-info">

                <div class="team-role">
                    CREATOR / ANIMATOR
                </div>

                <h3>
                    PATEL BILAL HUSAIN
                </h3>

                <p>
                    Creator • Director • Animator
                </p>

            </div>

        </div>


        <!-- FALCON -->

        <div class="team-card">

            <div class="team-photo-wrap">

                <img
                    class="team-photo"
                    src="https://i1.feedspot.com/original/7876073.jpg?t=1787456893"
                    alt="Falcon"
                >

            </div>

            <div class="team-info">

                <div class="team-role">
                    ANIMATION TEAM
                </div>

                <h3>
                    FALCON
                </h3>

                <p>
                    Animation • Creative Support
                </p>

            </div>

        </div>


        <!-- MAX HAY -->

        <div class="team-card">

            <div class="team-photo-wrap">

                <img
                    class="team-photo"
                    src="https://i1.feedspot.com/original/5631222.jpg?t=1787094560"
                    alt="Max Hay"
                >

            </div>

            <div class="team-info">

                <div class="team-role">
                    ANIMATION TEAM
                </div>

                <h3>
                    MAX HAY
                </h3>

                <p>
                    Animation • Creative Support
                </p>

            </div>

        </div>


    </div>

</section>


<!-- SOCIAL -->

<section id="social" class="reveal">

    <div class="section-head">

        <div class="section-tag">
            FOLLOW THE PROJECT
        </div>

        <h2 class="section-title">
            GRAPHENEBOYS IS COMING.
        </h2>

        <p class="section-desc">
            Follow the journey from the first frame to the final chapter.
        </p>

    </div>


    <div class="socials">

        <a
            href="https://www.youtube.com/watch?v=2LuW5WTGCfI"
            target="_blank"
            class="social"
        >

            <small>VIDEO</small>

            <strong>
                YouTube ↗
            </strong>

        </a>


        <a
            href="https://www.instagram.com/"
            target="_blank"
            class="social"
        >

            <small>SOCIAL</small>

            <strong>
                Instagram ↗
            </strong>

        </a>


        <a
            href="#"
            class="social"
        >

            <small>COMING</small>

            <strong>
                Crunchyroll
            </strong>

        </a>

    </div>

</section>


<!-- FOOTER -->

<footer>

    <div class="footer-logo">
        GRAPHENEBOYS
    </div>

    <p>
        Created • Directed • Animated by Patel Bilal Husain
    </p>

    <p>
        © 2026 GrapheneBoys
    </p>

</footer>


<script>

/* LOADER */

window.addEventListener("load",function(){

    setTimeout(function(){

        document
        .getElementById("loader")
        .classList.add("hide");

    },900);

});


/* NAVBAR */

const navbar =
document.getElementById("navbar");

window.addEventListener("scroll",function(){

    if(window.scrollY > 30){

        navbar.classList.add("scrolled");

    }else{

        navbar.classList.remove("scrolled");

    }

});


/* MOBILE MENU */

const menu =
document.getElementById("menu");

const navLinks =
document.getElementById("navLinks");

menu.addEventListener("click",function(){

    navLinks.classList.toggle("open");

});


document
.querySelectorAll(".nav-links a")
.forEach(function(link){

    link.addEventListener("click",function(){

        navLinks.classList.remove("open");

    });

});


/* SCROLL REVEAL */

const reveals =
document.querySelectorAll(".reveal");

const observer =
new IntersectionObserver(
function(entries){

    entries.forEach(function(entry){

        if(entry.isIntersecting){

            entry.target.classList.add("active");

        }

    });

},
{
    threshold:.12
});


reveals.forEach(function(el){

    observer.observe(el);

});


/* ESCAPE */

document.addEventListener(
"keydown",
function(e){

    if(e.key === "Escape"){

        navLinks.classList.remove("open");

    }

});

</script>

</body>
</html>
