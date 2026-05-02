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
    background: #0a0a0f;
    color:white;
}

/* MENU */
.menu {
    position: fixed;
    top:0;
    width:100%;
    background: rgba(20,20,30,0.9);
    display:flex;
    justify-content: space-around;
    padding:15px;
    backdrop-filter: blur(10px);
}

.menu button {
    background:none;
    border:none;
    color:white;
    font-size:14px;
}

/* SECTIONS */
section {
    padding:80px 20px;
    max-width:900px;
    margin:auto;
}

.card {
    background: rgba(255,255,255,0.05);
    padding:20px;
    border-radius:12px;
    margin-top:15px;
}

/* INPUT */
textarea {
    width:100%;
    height:120px;
    background:#111;
    color:white;
    border:none;
    padding:10px;
    border-radius:10px;
}

/* BUTTON */
.btn {
    padding:10px 15px;
    background:linear-gradient(90deg,#7a4dff,#ff4df0);
    border:none;
    color:white;
    border-radius:20px;
    margin-top:10px;
}

/* POSTS */
.post {
    background:#151520;
    padding:15px;
    border-radius:10px;
    margin-top:10px;
}
</style>
</head>

<body>

<div class="menu">
    <button onclick="show('home')">🏠 Accueil</button>
    <button onclick="show('ai')">🤖 IA</button>
    <button onclick="show('posts')">📸 Posts</button>
    <button onclick="show('library')">📚 Librairie</button>
</div>

<!-- HOME -->
<section id="home">
    <h1>Olsen World</h1>
    <div class="card">
        Ton espace personnel. Ton univers. Ta création.
    </div>
</section>

<!-- AI -->
<section id="ai" style="display:none;">
    <h2>IA Créative</h2>
    <div class="card">
        <textarea placeholder="Écris ton idée ici..."></textarea>
        <button class="btn">Générer (simulation)</button>
    </div>
</section>

<!-- POSTS -->
<section id="posts" style="display:none;">
    <h2>Posts</h2>

    <div class="card">
        <textarea placeholder="Écris un post..."></textarea>
        <button class="btn">Publier</button>
    </div>

    <div class="post">Ton espace de publication apparaîtra ici.</div>
</section>

<!-- LIBRARY -->
<section id="library" style="display:none;">
    <h2>Librairie</h2>

    <div class="card">
        📘 Romans<br>
        📖 Histoires<br>
        📄 Notes personnelles
    </div>
</section>

<script>
function show(id){
    document.querySelectorAll('section').forEach(s=>s.style.display="none");
    document.getElementById(id).style.display="block";
}
</script>

</body>
</html>
