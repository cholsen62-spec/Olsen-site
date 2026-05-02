# Olsen-site
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Olsen World</title>

<style>
body {
    margin:0;
    font-family: Arial;
    background: radial-gradient(circle, #0b0b14, #000);
    color:white;
}

/* NAV */
nav {
    position:fixed;
    top:0;
    width:100%;
    display:flex;
    justify-content:space-around;
    background:rgba(20,20,30,0.9);
    padding:12px;
    backdrop-filter: blur(10px);
}

nav button {
    background:none;
    border:none;
    color:white;
    font-size:14px;
}

/* PAGE */
section {
    display:none;
    padding:90px 20px;
    max-width:900px;
    margin:auto;
}

.active {
    display:block;
}

/* CARD */
.card {
    background:rgba(255,255,255,0.05);
    padding:20px;
    border-radius:12px;
    margin-top:15px;
}

/* INPUT */
textarea {
    width:100%;
    height:120px;
    background:#111;
    border:none;
    color:white;
    padding:10px;
    border-radius:10px;
}

/* BUTTON */
button.post {
    padding:10px 15px;
    margin-top:10px;
    border:none;
    border-radius:20px;
    background:linear-gradient(90deg,#7a4dff,#ff4df0);
    color:white;
}

/* POST */
.post {
    background:#151525;
    padding:15px;
    margin-top:10px;
    border-radius:10px;
}
</style>
</head>

<body>

<nav>
    <button onclick="go('home')">🏠</button>
    <button onclick="go('ai')">🤖</button>
    <button onclick="go('posts')">📸</button>
    <button onclick="go('library')">📚</button>
</nav>

<section id="home" class="active">
    <h1>Olsen World</h1>
    <div class="card">
        Ton espace numérique personnel.  
        Un monde où tu crées tout.
    </div>
</section>

<section id="ai">
    <h2>IA Créative</h2>
    <div class="card">
        <textarea placeholder="Écris ton idée..."></textarea>
        <button class="post">Générer (simulation IA)</button>
    </div>
</section>

<section id="posts">
    <h2>Posts</h2>

    <div class="card">
        <textarea placeholder="Publie quelque chose..."></textarea>
        <button class="post">Publier</button>
    </div>

    <div class="post">🔥 Ton futur feed apparaîtra ici</div>
</section>

<section id="library">
    <h2>Librairie</h2>
    <div class="card">
        📘 Romans<br>
        📖 Histoires<br>
        📄 Notes personnelles<br>
        📂 Téléchargements (futur)
    </div>
</section>

<script>
function go(id){
    document.querySelectorAll('section').forEach(s=>s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
}
</script>

</body>
</html>
