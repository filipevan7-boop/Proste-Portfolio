<!DOCTYPE html>
<html lang="pl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portfolio - Twoje Imię</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

body, html {
    margin: 0;
    padding: 0;
    font-family: 'Roboto', sans-serif;
    overflow-x: hidden;
    background: #0d1117;
    color: #ffffff;
}

/* Canvas tło */
#particle-canvas {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -2;
}

/* Banner */
header {
    position: relative;
    width: 100%;
    height: 350px;
    background: url('banner.png') center/cover no-repeat fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    z-index: 1;
}

header img {
    width: 160px;
    height: auto;
    border-radius: 50%;
    animation: logoAnimation 3s ease-in-out infinite alternate;
    z-index: 2;
    box-shadow: 0 0 25px rgba(0,229,255,0.7);
}

@keyframes logoAnimation {
    0% { transform: scale(1) rotate(0deg); }
    100% { transform: scale(1.1) rotate(10deg); }
}

/* Sekcje */
section {
    padding: 70px 20px;
    max-width: 1200px;
    margin: auto;
    position: relative;
    z-index: 2;
    border-radius: 15px;
}

/* Nagłówki */
h1, h2, h3, h4 {
    text-align: center;
    margin-bottom: 25px;
    letter-spacing: 1px;
}

/* Fade-in + slide animacja przy scrollu */
.fade-slide {
    opacity: 0;
    transform: translateY(50px);
    transition: all 1s ease-out;
}
.fade-slide.visible {
    opacity: 1;
    transform: translateY(0);
}

/* Karty */
.card, .project-card {
    background: rgba(255,255,255,0.05);
    border-radius: 18px;
    padding: 25px;
    transition: transform 0.3s, box-shadow 0.3s;
    cursor: default;
    box-shadow: 0 8px 15px rgba(0,0,0,0.3);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255,255,255,0.1);
    position: relative;
}

/* Ikony przy projektach */
.project-card .icons, .card .icons {
    display: flex;
    justify-content: flex-start;
    gap: 10px;
    margin-top: 15px;
}
.project-card .icons img, .card .icons img {
    width: 32px;
    height: 32px;
    transition: transform 0.3s, opacity 0.3s;
}
.project-card .icons img:hover, .card .icons img:hover {
    transform: scale(1.2) rotate(10deg);
    opacity: 1;
}

/* Hover karty */
.card:hover, .project-card:hover {
    transform: translateY(-10px) scale(1.05) perspective(1000px) rotateY(2deg) rotateX(2deg);
    box-shadow: 0 20px 35px rgba(0,229,255,0.5);
}

/* Grid */
.certificates, .projects {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 25px;
}

/* Projekty */
.project-card h4 {
    color: #00e5ff;
    margin-bottom: 10px;
}
.project-card p {
    line-height: 1.6;
    font-size: 0.95rem;
}

/* Umiejętności - paski */
.skill-bar {
    background: rgba(255,255,255,0.1);
    border-radius: 12px;
    margin: 10px 0;
    overflow: hidden;
    height: 20px;
}
.skill-fill {
    height: 100%;
    width: 0;
    background: #00e5ff;
    border-radius: 12px;
    transition: width 2s ease-out;
}

/* Sekcje przezroczyste */
section:nth-of-type(even) {
    background: rgba(0,0,0,0.5);
}
section:nth-of-type(odd) {
    background: rgba(0,0,0,0.25);
}

section p {
    max-width: 900px;
    margin: 0 auto;
    text-align: center;
}

/* Kontakt */
.contact {
    text-align: center;
    font-size: 1.2rem;
}
.contact a {
    color: #00e5ff;
    text-decoration: none;
    font-weight: 700;
    transition: color 0.3s;
}
.contact a:hover {
    color: #ffeb3b;
}

/* Pulsujący gradient */
body::before {
    content: '';
    position: fixed;
    top:0; left:0;
    width:100%; height:100%;
    background: linear-gradient(-45deg, #0d1117, #001f33, #003366, #0d1117);
    background-size: 400% 400%;
    animation: gradientBG 20s ease infinite;
    z-index: -3;
    opacity: 0.3;
}
@keyframes gradientBG {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}
</style>
</head>
<body>

<canvas id="particle-canvas"></canvas>

<header>
    <img src="download.png" alt="Logo">
</header>

<section class="fade-slide">
    <h1>O mnie</h1>
    <p>Jestem pasjonatem IT z szerokim doświadczeniem w programowaniu, tworzeniu aplikacji, bazach danych oraz cybersecurity. Posiadam liczne certyfikaty w dziedzinach takich jak Java, Python, C++, HTML/CSS, bazy danych. Tworzę profesjonalne projekty i innowacyjne rozwiązania osobiste.</p>
</section>

<section class="fade-slide">
    <h2>Umiejętności techniczne</h2>
    <div class="projects">
        <div class="project-card">
            <h4>Programowanie</h4>
            <p>Java, Python, C++, HTML/CSS/JS</p>
            <div class="skill-bar"><div class="skill-fill" data-percent="90%"></div></div>
            <div class="icons">

            </div>
        </div>
        <div class="project-card">
            <h4>Bazy danych</h4>
            <p>MySQL, PostgreSQL, MongoDB</p>
            <div class="skill-bar"><div class="skill-fill" data-percent="85%"></div></div>
            <div class="icons">

            </div>
        </div>
        <div class="project-card">
            <h4>Cybersecurity</h4>
            <p>Testy penetracyjne, audyty, bezpieczeństwo systemów</p>
            <div class="skill-bar"><div class="skill-fill" data-percent="80%"></div></div>
            <div class="icons">
            
            </div>
        </div>
        <div class="project-card">
            <h4>Inne technologie</h4>
            <p>Docker, Git, Linux, API, AWS / Azure</p>
            <div class="skill-bar"><div class="skill-fill" data-percent="75%"></div></div>
            <div class="icons">
            </div>
        </div>
    </div>
</section>

<section class="fade-slide">
    <h2>Certyfikaty</h2>
    <div class="certificates">
        <div class="card">Java SE 8 OCA</div>
        <div class="card">Java SE 8 OCP</div>
        <div class="card">Spring Framework</div>
        <div class="card">Python PCEP</div>
        <div class="card">Python PCAP</div>
        <div class="card">C++ CPA</div>
        <div class="card">HTML5 & CSS3 Developer</div>
        <div class="card">CompTIA Security+</div>
        <div class="card">CEH – Ethical Hacker</div>
        <div class="card">CISSP</div>
    </div>
</section>

<section class="fade-slide">
    <h2>Projekty</h2>
    <div class="projects">
        <div class="project-card">
            <h4>Bot do automatyzacji zadań</h4>
            <p><strong>Technologie:</strong> Python, Selenium, API, Cron</p>
            <p>Automatyzacja powtarzalnych zadań w firmie, generowanie raportów i wysyłka powiadomień. Integracja z systemami zewnętrznymi i optymalizacja czasowa.</p>
            <div class="icons">
            </div>
        </div>
        <div class="project-card">
            <h4>Aplikacja webowa do zarządzania danymi</h4>
            <p><strong>Technologie:</strong> Java, Spring Boot, MySQL</p>
            <p>System CRUD z autoryzacją i rolami użytkowników, interaktywny interfejs do zarządzania danymi klientów i raportowania statystyk.</p>
            <div class="icons">

            </div>
        </div>
        <div class="project-card">
            <h4>System bezpieczeństwa dla firmy</h4>
            <p><strong>Technologie:</strong> Kali Linux, Wireshark, Firewall, Python</p>
            <p>Analiza ryzyka, wdrożenie firewalli, testy penetracyjne, monitorowanie sieci i raportowanie zagrożeń.</p>
            <div class="icons">

            </div>
        </div>
        <div class="project-card">
            <h4>Portfolio online</h4>
            <p><strong>Technologie:</strong> HTML5, CSS3, JavaScript</p>
            <p>Responsywne portfolio z animacjami, interaktywnym UI i integracją multimediów. Projekt prezentuje umiejętności i certyfikaty.</p>
            <div class="icons">

            </div>
        </div>
        <div class="project-card">
            <h4>Aplikacja mobilna do notatek</h4>
            <p><strong>Technologie:</strong> Java, Android SDK, SQLite</p>
            <p>Synchronizacja notatek z chmurą, przypomnienia push, organizacja kategorii i szybkie wyszukiwanie.</p>
            <div class="icons">

            </div>
        </div>
        <div class="project-card">
            <h4>Dashboard analityczny</h4>
            <p><strong>Technologie:</strong> Python, Pandas, Matplotlib, Seaborn</p>
            <p>Wizualizacja statystyk w czasie rzeczywistym, automatyczne raporty, analizy trendów i przewidywania.</p>
            <div class="icons">

            </div>
        </div>
    </div>
</section>

<section class="contact fade-slide">
    <h2>Kontakt</h2>
    <p>Masz pytania lub chcesz współpracować?</p>
    <p><a href="https://discord.gg/VwJwbbah3g" target="_blank">DISCORD</a><br>Gmail: filipevan7@gmail.com</p>
</section>

<audio id="backgroundAudio" loop>
    <source src="muzyka.mp3" type="audio/mpeg">
</audio>

<script>
// Muzyka autoplay
window.addEventListener('click', () => {
    const audio = document.getElementById('backgroundAudio');
    if (audio.paused) audio.play();
});

// Particle background
const canvas = document.getElementById('particle-canvas');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

const particles = [];
for(let i=0;i<120;i++){
    particles.push({x:Math.random()*canvas.width, y:Math.random()*canvas.height, size:Math.random()*3+1, dx:(Math.random()-0.5), dy:(Math.random()-0.5)});
}

function animateParticles(){
    ctx.clearRect(0,0,canvas.width,canvas.height);
    for(let p of particles){
        p.x += p.dx; p.y += p.dy;
        if(p.x<0||p.x>canvas.width)p.dx*=-1;
        if(p.y<0||p.y>canvas.height)p.dy*=-1;
        ctx.fillStyle = '#00e5ff';
        ctx.beginPath(); ctx.arc(p.x,p.y,p.size,0,Math.PI*2); ctx.fill();
    }
    requestAnimationFrame(animateParticles);
}
animateParticles();

// Scroll fade-slide
const faders = document.querySelectorAll('.fade-slide');
const observer = new IntersectionObserver(entries=>{
    entries.forEach(entry=>{
        if(entry.isIntersecting){entry.target.classList.add('visible');}
    });
},{threshold:0.2});
faders.forEach(f=>observer.observe(f));

// Animacja skill-bar
const skills = document.querySelectorAll('.skill-fill');
window.addEventListener('scroll', ()=>{
    skills.forEach(skill=>{
        const rect = skill.getBoundingClientRect();
        if(rect.top < window.innerHeight-50){
            skill.style.width = skill.dataset.percent;
        }
    });
});
</script>

</body>
</html>
