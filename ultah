<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Happy Birthday ✨</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
    body {
        margin: 0;
        font-family: 'Poppins', sans-serif;
        height: 100vh;
        overflow: hidden;
        background: linear-gradient(135deg, #0d1b3d, #2b5876, #4e4376);
        background-size: 300% 300%;
        animation: bgmove 10s ease infinite;
        display: flex;
        justify-content: center;
        align-items: center;
        color: #fff;
    }

    @keyframes bgmove {
        0% {background-position: 0% 50%;}
        50% {background-position: 100% 50%;}
        100% {background-position: 0% 50%;}
    }

    .card {
        background: rgba(255,255,255,0.08);
        backdrop-filter: blur(12px);
        padding: 40px;
        border-radius: 20px;
        width: 90%;
        max-width: 600px;
        text-align: center;
        box-shadow: 0 0 25px rgba(255,255,255,0.15);
        border: 1px solid rgba(255,255,255,0.1);
    }

    h1 {
        font-size: 38px;
        margin-bottom: 10px;
        text-shadow: 0 0 10px #ffd166;
    }

    #typed {
        font-size: 18px;
        min-height: 60px;
    }

    .btns {
        margin-top: 20px;
        display: flex;
        justify-content: center;
        gap: 10px;
    }

    button {
        padding: 10px 16px;
        border-radius: 10px;
        font-size: 16px;
        border: none;
        cursor: pointer;
        background: #ffd166;
        color: #222;
        font-weight: 600;
        transition: 0.3s;
    }

    button:hover {
        transform: scale(1.08);
        background: #ffca55;
    }

    #confetti-canvas {
        position: fixed;
        top: 0; left: 0;
        width: 100%; height: 100%;
        pointer-events: none;
    }
</style>
</head>
<body>

<canvas id="confetti-canvas"></canvas>

<div class="card">
    <h1>🎉 Selamat Ulang Tahun! 🎂</h1>
    <div id="typed"></div>

    <div class="btns">
        <button id="play">Putar Musik</button>
        <button id="boom">Kejutan!</button>
    </div>
</div>

<audio id="song" loop src="ssstik.io_1763480074936.mp3"></audio>


<script>
/* ------------------ Teks Mengetik ------------------ */
const text = [
    "HBD Bang",
    "",
    "",
    "",
];
let idx = 0;
let char = 0;

function typeWriter() {
    if (idx < text.length) {
        if (char < text[idx].length) {
            document.getElementById("typed").innerHTML += text[idx][char];
            char++;
            setTimeout(typeWriter, 40);
        } else {
            document.getElementById("typed").innerHTML += "<br><br>";
            char = 0;
            idx++;
            setTimeout(typeWriter, 500);
        }
    }
}
typeWriter();

/* ------------------ Musik ------------------ */
const song = document.getElementById("song");
document.getElementById("play").onclick = () => {
    if (song.paused) {
        song.play();
        play.textContent = "Hentikan Musik";
    } else {
        song.pause();
        play.textContent = "Putar Musik";
    }
};

/* ------------------ Confetti ------------------ */
const canvas = document.getElementById("confetti-canvas");
const ctx = canvas.getContext("2d");

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

function confetti() {
    const pieces = [];
    for (let i = 0; i < 150; i++) {
        pieces.push({
            x: Math.random() * canvas.width,
            y: Math.random() * canvas.height - canvas.height,
            size: Math.random() * 8 + 4,
            color: ["#FFD166", "#FF6B6B", "#4ECDC4", "#A29BFE"][Math.floor(Math.random() * 4)],
            speed: Math.random() * 3 + 1
        });
    }

    function fall() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        for (let p of pieces) {
            ctx.fillStyle = p.color;
            ctx.fillRect(p.x, p.y, p.size, p.size);
            p.y += p.speed;

            if (p.y > canvas.height) p.y = -10;
        }
        requestAnimationFrame(fall);
    }
    fall();
}

document.getElementById("boom").onclick = confetti;
</script>

</body>
</html>
