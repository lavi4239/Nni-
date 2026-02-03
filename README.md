# Nni-
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bebboo ❤️ NNI 😘🧿</title>

<style>
  :root {
    --primary: #ff4d94;
    --secondary: #ff99cc;
    --glass: rgba(255, 255, 255, 0.25);
  }

  body {
    margin: 0;
    padding: 0;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(135deg, #ff99cc 0%, #ff4d94 100%);
    color: white;
    text-align: center;
    overflow-x: hidden;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    perspective: 1200px;
  }

  h1 { margin-top: 30px; font-size: 2rem; padding: 0 10px; text-shadow: 2px 2px 8px rgba(0,0,0,0.2); }

  .box {
    background: var(--glass);
    border-radius: 30px;
    padding: 30px;
    margin: 20px;
    width: 88%;
    max-width: 450px;
    backdrop-filter: blur(15px);
    box-shadow: 0 20px 50px rgba(0,0,0,0.2);
    animation: fadeUp 1s ease-out;
    border: 1px solid rgba(255,255,255,0.4);
    z-index: 10;
  }

  button {
    background: white;
    color: var(--primary);
    border: none;
    padding: 15px 30px;
    border-radius: 40px;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    margin: 10px;
    transition: all 0.3s ease;
    box-shadow: 0 8px 20px rgba(0,0,0,0.15);
  }

  button:hover { transform: scale(1.05); }
  .hidden { display: none; }
  .option-btn { width: 100%; margin: 12px 0; display: block; }

  .progress {
    width: 100%;
    background: rgba(255,255,255,0.3);
    border-radius: 15px;
    height: 10px;
    margin: 25px 0;
  }

  .progress-bar {
    height: 100%;
    width: 0%;
    background: #fff;
    border-radius: 15px;
    transition: width 0.5s ease;
  }

  /* SCRATCH CARD STYLE */
  .scratch-container {
    position: relative;
    width: 250px;
    height: 120px;
    margin: 20px auto;
    background: white;
    border-radius: 15px;
    overflow: hidden;
    cursor: crosshair;
  }

  .scratch-gift {
    position: absolute;
    top: 0; left: 0; width: 100%; height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.2rem;
    color: var(--primary);
    font-weight: bold;
  }

  #scratchCanvas {
    position: absolute;
    top: 0; left: 0;
    z-index: 2;
    touch-action: none;
  }

  /* ORBS */
  .orb-container {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin: 25px 0;
  }

  .orb {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    background: radial-gradient(circle at 30% 30%, #fff, #ffb3d9, #ff4d94);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    font-weight: 900;
    color: var(--primary);
    animation: float3d 6s infinite ease-in-out;
    box-shadow: 0 15px 30px rgba(0,0,0,0.2);
    border: 2px solid white;
  }

  @keyframes float3d {
    0%, 100% { transform: translateY(0) rotateY(0deg); }
    50% { transform: translateY(-25px) rotateY(180deg); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .heart { position: fixed; z-index: 100; animation: rise 4s linear forwards; }
  @keyframes rise { to { transform: translateY(-115vh) rotate(360deg); opacity: 0; } }

  .no-btn { position: relative; transition: 0.1s; }
</style>
</head>
<body>

<h1>For NNI 😘🧿</h1>

<div id="startBox" class="box">
  <p style="font-size: 1.2rem;">NNI, you are my favorite feeling,<br>my safest place,<br>and my forever ❤️🧿</p>
  <div class="orb-container">
    <div class="orb"><span>🧔🏻‍♂️</span>Bebboo</div>
    <div class="orb"><span>👩🏻‍❤️‍💋‍👨🏻</span>NNI 😘</div>
  </div>
  <button onclick="startApp()">Enter My Heart ❤️</button>
</div>

<div id="questionBox" class="hidden box">
  <h2 id="questionText" style="font-size: 1.3rem;"></h2>
  <div class="progress"><div class="progress-bar" id="progressBar"></div></div>
  <div id="options"></div>
</div>

<div id="final" class="hidden box">
  <h2>NNI 😘🧿 You Are My Forever!</h2>
  <p>Scratch to reveal your gift: 👇</p>
  
  <div class="scratch-container" id="scratchArea">
    <div class="scratch-gift">1000 Kisses & Forever Love 💋🧿</div>
    <canvas id="scratchCanvas" width="250" height="120"></canvas>
  </div>

  <p style="margin-top: 20px;"><b>Always yours, Bebboo ❤️</b></p>
  <button onclick="location.reload()">Replay 😘</button>
</div>

<script>
const questions = [
  { text: "Do you know you are Bebboo's safest place, NNI 😘🧿?", type: "yesno" },
  {
    text: "What is my absolute favorite thing in the world?",
    type: "mcq",
    options: ["Pasta 🍝", "Cold Coffee ☕", "Traveling ✈️", "Sleeping 😴"],
    real: "None of these… it’s YOU NNI 😘🧿"
  },
  {
    text: "If we were in a room full of people, who would my eyes look for?",
    type: "mcq",
    options: ["My Friends 🕺", "The Food 🍕", "The Exit 🚪", "The Mirror 🪞"],
    real: "Wrong! My eyes will always only look for YOU 🥺❤️🧿"
  },
  {
    text: "What did Bebboo give you when we first met?",
    type: "mcq",
    options: ["Rose 🌹", "Chocolates 🍫", "A Gift 🎁", "A Smile 😊"],
    real: "Actually… I gave you my HEART ❤️🥹🧿"
  },
  { text: "Will you stay with Bebboo forever, NNI 😘🧿?", type: "yesno" }
];

let index = 0;
let noScale = 1;

function startApp() {
  document.getElementById("startBox").classList.add("hidden");
  document.getElementById("questionBox").classList.remove("hidden");
  showQuestion();
}

function showQuestion() {
  const q = questions[index];
  document.getElementById("questionText").innerText = q.text;
  const opt = document.getElementById("options");
  opt.innerHTML = "";
  document.getElementById("progressBar").style.width = ((index / questions.length) * 100) + "%";

  if (q.type === "yesno") {
    opt.innerHTML = `
      <button onclick="next()">YES ❤️</button>
      <button id="noBtn" class="no-btn" onmouseover="moveNo()" onclick="moveNo()" ontouchstart="moveNo()">NO 🙄</button>
    `;
  } else {
    q.options.forEach(o => {
      const b = document.createElement("button");
      b.className = "option-btn";
      b.innerText = o;
      b.onclick = () => reveal(q.real);
      opt.appendChild(b);
    });
  }
}

function moveNo() {
  const btn = document.getElementById("noBtn");
  const x = Math.random() * 200 - 100;
  const y = Math.random() * 150 - 75;
  noScale = Math.max(0.3, noScale - 0.1); 
  btn.style.transform = `translate(${x}px, ${y}px) scale(${noScale})`;
}

function reveal(txt) {
  document.getElementById("options").innerHTML = `
    <p style="margin: 20px 0; font-weight: bold;">${txt}</p>
    <button onclick="next()">Aww 🥹❤️</button>
  `;
}

function next() {
  index++;
  if (index < questions.length) {
    showQuestion();
  } else {
    document.getElementById("questionBox").classList.add("hidden");
    document.getElementById("final").classList.remove("hidden");
    initScratch();
    setInterval(createHeart, 250);
  }
}

function initScratch() {
  const canvas = document.getElementById("scratchCanvas");
  const ctx = canvas.getContext("2d");
  
  // Fill with Gold color
  ctx.fillStyle = "#D4AF37";
  ctx.fillRect(0, 0, canvas.width, canvas.height);
  
  // Add some sparkle texture
  ctx.fillStyle = "#FFD700";
  for(let i=0; i<100; i++) {
    ctx.fillRect(Math.random()*canvas.width, Math.random()*canvas.height, 2, 2);
  }

  let isDrawing = false;
  const scratch = (e) => {
    if (!isDrawing) return;
    const rect = canvas.getBoundingClientRect();
    const x = (e.clientX || e.touches[0].clientX) - rect.left;
    const y = (e.clientY || e.touches[0].clientY) - rect.top;
    ctx.globalCompositeOperation = 'destination-out';
    ctx.beginPath();
    ctx.arc(x, y, 15, 0, Math.PI * 2);
    ctx.fill();
  };

  canvas.addEventListener("mousedown", () => isDrawing = true);
  canvas.addEventListener("mouseup", () => isDrawing = false);
  canvas.addEventListener("mousemove", scratch);
  canvas.addEventListener("touchstart", () => isDrawing = true);
  canvas.addEventListener("touchend", () => isDrawing = false);
  canvas.addEventListener("touchmove", scratch);
}

function createHeart() {
  const h = document.createElement("div");
  h.className = "heart";
  const choices = ["❤️", "💖", "🧿", "😘", "💍"];
  h.innerHTML = choices[Math.floor(Math.random() * choices.length)];
  h.style.left = Math.random() * 100 + "vw";
  h.style.bottom = "-5vh";
  document.body.appendChild(h);
  setTimeout(() => h.remove(), 4000);
}
</script>

</body>
</html>
