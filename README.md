# Olsen-site
Site personnel — Le Jardin d’Olsen
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Olsen — Le Jardin Intérieur</title>

<style>
body {
    margin: 0;
    font-family: 'Arial', sans-serif;
    background: radial-gradient(circle at top, #1a0f2e, #000);
    color: white;
    overflow-x: hidden;
}

/* HERO */
.hero {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    position: relative;
}

.hero h1 {
    font-size: 4em;
    letter-spacing: 3px;
    text-shadow: 0 0 25px rgba(180,120,255,0.6);
}

.hero p {
    opacity: 0.7;
    margin-top: 10px;
}

/* IMAGE STYLE */
.profile {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    margin-bottom: 20px;
    border: 3px solid rgba(255,255,255,0.2);
    box-shadow: 0 0 30px rgba(180,120,255,0.4);
    object-fit: cover;
}

/* SECTIONS */
section {
    padding: 80px 20px;
    max-width: 850px;
    margin: auto;
}

.card {
    background: rgba(255,255,255,0.05);
    padding: 25px;
    border-radius: 15px;
    backdrop-filter: blur(10px);
    margin-top: 20px;
    border: 1px solid rgba(255,255,255,0.08);
}

/* BUTTONS */
.btn {
    display: inline-block;
    margin-top: 20px;
    padding: 12px 20px;
    border-radius: 30px;
    background: linear-gradient(90deg, #7b4dff, #ff4df0);
    color: white;
    text-decoration: none;
    font-weight: bold;
}

/* GLOW TEXT */
.glow {
    color: #caa6ff;
    text-shadow: 0 0 15px rgba(202,166,255,0.6);
}

/* FLOAT EFFECT */
@keyframes float {
    0% {transform: translateY(0px);}
    50% {transform: translateY(-10px);}
    100% {transform: translateY(0px);}
}

.hero h1 {
    animation: float 4s ease-in-out infinite;
}
</style>
</head>

<body>

<div class="hero">
    <!-- 🔥 Mets ici ta photo -->
    <img src="https://via.placeholder.com/180" class="profile">

    <h1>Olsen</h1>
    <p>Je construis un monde dans ma tête, et je le rends réel.</p>

    <a class="btn" href="https://www.tiktok.com" target="_blank">Voir mon TikTok</a>
</div>

<section>
    <h2 class="glow">Mon Univers</h2>
    <div class="card">
        <p>
        Je ne suis pas seulement une personne.  
        Je suis une vision, un monde intérieur, une esthétique.
        </p>
    </div>
</section>

<section>
    <h2 class="glow">Créations</h2>
    <div class="card">
        <p>
        Contenus, idées, images mentales, storytelling.  
        Tout commence dans le silence.
        </p>
    </div>
</section>

<section>
    <h2 class="glow">Réseaux</h2>
    <div class="card">
        TikTok : @tonpseudo<br>
        Instagram : @tonpseudo
    </div>
</section>

</body>
</html>
