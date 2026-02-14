# Santiagohellebrandt-cell.github.io
San Valentín 💘 
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>San Valentín Romántico</title>

<style>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: #000;
    color: white;
    text-align: center;
}

.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-size: cover;
    background-position: center;
    transition: 0.5s ease;
    padding: 20px;
}

.initial {
    background-image: url('https://images.unsplash.com/photo-1518709268805-4e9042af2176?auto=format&fit=crop&w=1000&q=80');
}

.yes {
    background-image: url('https://images.unsplash.com/photo-1518199266791-5375a83190b7?auto=format&fit=crop&w=1000&q=80');
}

.no {
    background-image: url('https://images.unsplash.com/photo-1558618666-fcd25c85cd64?auto=format&fit=crop&w=1000&q=80');
}

h1 {
    font-size: 2.5em;
    text-shadow: 2px 2px 5px rgba(0,0,0,0.6);
}

p {
    font-size: 1.2em;
    max-width: 500px;
    text-shadow: 1px 1px 3px rgba(0,0,0,0.6);
}

button {
    background-color: #ff4da6;
    color: white;
    border: none;
    padding: 15px 30px;
    font-size: 1.2em;
    border-radius: 30px;
    cursor: pointer;
    margin: 10px;
    transition: 0.3s;
}

button:hover {
    background-color: #ff1a8c;
    transform: scale(1.1);
}

.buttons {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

/* Corazones flotando */
.heart {
    position: absolute;
    color: pink;
    font-size: 20px;
    animation: floatUp 4s linear infinite;
}

@keyframes floatUp {
    0% {
        transform: translateY(100vh);
        opacity: 1;
    }
    100% {
        transform: translateY(-10vh);
        opacity: 0;
    }
}

/* Responsive */
@media(max-width:600px){
    h1 { font-size: 1.8em; }
    p { font-size: 1em; }
    button { font-size: 1em; padding: 12px 20px; }
}
</style>
</head>

<body>

<audio id="romanticMusic" loop>
    <source src="https://www.soundjay.com/misc/sounds/bell-ringing-05.wav" type="audio/wav">
</audio>

<div id="container" class="container initial">
    <h1 id="title">¿Quieres ser mi San Valentín?</h1>
    <p id="message">No te preocupes princesa… esto viene con abrazos incluidos 💕</p>
    <div class="buttons" id="buttons">
        <button id="yesBtn">Sí</button>
        <button id="noBtn">No</button>
    </div>
</div>

<script>
const container = document.getElementById('container');
const title = document.getElementById('title');
const message = document.getElementById('message');
const buttons = document.getElementById('buttons');
const yesBtn = document.getElementById('yesBtn');
const noBtn = document.getElementById('noBtn');
const music = document.getElementById('romanticMusic');

/* Botón NO se mueve */
noBtn.addEventListener('mouseover', () => {
    noBtn.style.position = 'absolute';
    noBtn.style.top = Math.random() * window.innerHeight + 'px';
    noBtn.style.left = Math.random() * window.innerWidth + 'px';
});

/* Si dice que sí */
yesBtn.addEventListener('click', () => {

    music.play();

    container.className = 'container yes';
    title.textContent = 'Sabía que dirías que sí 💖';
    message.textContent = 'Mi reina hermosa… gracias por elegirme. Quiero seguir construyendo momentos lindos contigo, llenos de paz, confianza y cariño.';
    
    buttons.innerHTML = '<button id="surpriseBtn">Ver sorpresa</button>';

    createHearts();

    document.getElementById('surpriseBtn').addEventListener('click', () => {
        alert('Mi princesa… esto es solo el comienzo de muchos momentos especiales juntos. Gracias por confiar en mí 💕');
    });
});

/* Si intenta decir que no */
noBtn.addEventListener('click', () => {
    container.className = 'container no';
    title.textContent = 'Mmm… creo que ese botón no funciona 😏';
    message.textContent = 'Intenta de nuevo, mi cielo 💕';
});

/* Corazones animados */
function createHearts(){
    setInterval(() => {
        const heart = document.createElement('div');
        heart.classList.add('heart');
        heart.innerHTML = '💖';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.fontSize = (Math.random() * 20 + 20) + 'px';
        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 4000);
    }, 300);
}
</script>

</body>
</html>
