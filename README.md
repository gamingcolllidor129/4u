# 4u
Line wrap
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>For My Love ❤️</title>
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Nunito:wght@400;700&display=swap" rel="stylesheet">
<style>
/* --- CSS STYLES --- */
* { margin: 0; padding: 0; box-sizing: border-box; }
body {
background: linear-gradient(135deg, #fad0c4 0%, #ffd1ff 100%);
height: 100vh;
width: 100vw;
display: flex;
justify-content: center;
align-items: center;
font-family: 'Nunito', sans-serif; /* CHANGED FONT */
overflow: hidden;
position: relative;
}

/* --- BACKGROUND RAIN OF HEARTS --- */
.rain-heart {
position: absolute;
top: -10%;
color: #ff6b81;
opacity: 0.6;
font-size: 20px;
user-select: none;
z-index: 1;
animation: fall linear forwards;
}

@keyframes fall {
to { transform: translateY(110vh) rotate(360deg); }
}

/* 1. LOADING SCREEN */
#loader {
position: fixed; top: 0; left: 0; width: 100%; height: 100%;
background: #fff0f5; z-index: 200;
display: flex; flex-direction: column; justify-content: center; align-items: center;
transition: opacity 0.8s ease;
}
.heart-box { width: 80px; height: 80px; position: relative; animation: beat 1.2s infinite ease-in-out; }
@keyframes beat { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.15); } }
.heart-shape {
width: 100%; height: 100%; background-color: #ffe4e1;
clip-path: path('M12 21.593c-5.63-5.539-11-10.297-11-14.402 0-3.791 3.068-5.191 5.281-5.191 1.312 0 4.151.501 5.719 4.457 1.59-3.968 4.464-4.447 5.726-4.447 2.54 0 5.274 1.621 5.274 5.181 0 4.069-5.136 8.625-11 14.402m5.726-20.583c-2.203 0-4.446 1.042-5.726 3.238-1.285-2.206-3.522-3.248-5.719-3.248-3.183 0-6.281 2.187-6.281 6.191 0 4.661 5.571 9.429 12 15.809 6.43-6.38 12-11.148 12-15.809 0-4.011-3.095-6.181-6.274-6.181');
position: absolute; top: 0; left: 0;
}
.heart-fill {
width: 100%; height: 0%; background-color: #ff4757;
position: absolute; bottom: 0; left: 0; transition: height 0.3s ease;
}
#loading-text { margin-top: 20px; color: #ff4757; font-size: 14px; letter-spacing: 2px; text-transform: uppercase; font-weight: bold; }

/* 2. LOCK SCREEN */
#lock-screen {
position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 100;
display: none; flex-direction: column; justify-content: center; align-items: center;
background: radial-gradient(circle at center, rgba(255,255,255,0.8) 0%, rgba(255,230,230,0.8) 100%);
}
.glass-card {
background: rgba(255, 255, 255, 0.6);
backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
border: 2px solid #fff;
padding: 40px; border-radius: 40px;
box-shadow: 0 15px 35px rgba(255, 107, 129, 0.2);
text-align: center; width: 90%; max-width: 350px;
animation: bounceIn 1s cubic-bezier(0.68, -0.55, 0.27, 1.55);
}
@keyframes bounceIn {
0% { transform: scale(0.3); opacity: 0; }
50% { transform: scale(1.05); opacity: 1; }
70% { transform: scale(0.9); }
100% { transform: scale(1); }
}
.cute-icon { font-size: 50px; margin-bottom: 10px; animation: float 3s ease-in-out infinite; }
@keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }

.glass-card h2 { font-family: 'Dancing Script', cursive; font-size: 40px; color: #ff4757; margin-bottom: 5px; }
.glass-card p { font-size: 16px; color: #ff6b81; margin-bottom: 20px; font-weight: 600; }

.input-group input {
width: 100%; padding: 15px; border: 2px solid #ffccd5; border-radius: 50px;
background: #fff0f5; font-size: 18px; text-align: center; font-family: 'Nunito', sans-serif;
color: #ff4757; font-weight: 700; outline: none; margin-top: 10px;
transition: all 0.3s ease;
}
.input-group input:focus { border-color: #ff4757; background: #fff; transform: scale(1.02); }
.unlock-btn {
margin-top: 20px; width: 100%; padding: 15px;
background: linear-gradient(45deg, #ff4757, #ff6b81); color: white;
border: none; border-radius: 50px; font-size: 18px; font-weight: 700; cursor: pointer;
box-shadow: 0 5px 15px rgba(255,71,87,0.3); font-family: 'Nunito', sans-serif;
transition: transform 0.2s;
}
.unlock-btn:hover { transform: scale(1.05) rotate(-1deg); }

/* 3. MAIN CARD */
.card {
background: rgba(255, 255, 255, 0.85);
padding: 30px; border-radius: 35px;
box-shadow: 0 20px 40px rgba(255,182,193,0.3);
text-align: center; width: 380px; max-width: 90%;
display: none; position: relative; z-index: 50;
border: 3px solid #fff;
transition: opacity 0.5s ease;
}
.gif-area img {
width: 160px; height: 160px; object-fit: contain;
border-radius: 20px; margin-bottom: 15px;
border: 4px solid #fff;
box-shadow: 0 5px 15px rgba(0,0,0,0.05);
transition: transform 0.3s;
}
.gif-area img:hover { transform: scale(1.05); }
h1 { color: #ff4757; font-size: 28px; margin: 10px 0; font-family: 'Nunito', sans-serif; font-weight: 800; }
p { color: #777; font-size: 16px; margin-bottom: 25px; font-family: 'Nunito', sans-serif; font-weight: 600; }
.btn-container { display: flex; justify-content: center; gap: 15px; position: relative; min-height: 50px; }
button {
padding: 12px 30px; font-size: 16px; border: none; border-radius: 50px;
cursor: pointer; font-family: 'Nunito', sans-serif; font-weight: 700;
transition: all 0.3s;
}
#yes-btn { background: #ff4757; color: white; z-index: 10; box-shadow: 0 4px 15px rgba(255, 71, 87, 0.4); }
#yes-btn:hover { transform: scale(1.1); background: #ff2e43; }
#no-btn { background: white; color: #ff4757; border: 2px solid #ff4757; z-index: 10; transition: top 0.3s ease, left 0.3s ease; }
/* 4. SUCCESS & TREE */
#success-container {
position: fixed; top: 0; left: 0; width: 100%; height: 100%;
background: #fff0f5; z-index: 60; display: none;
}
#world { display: block; width: 100%; height: 100%; }

.final-message {
position: absolute; top: 15%; left: 50%;
transform: translate(-50%, -50%); text-align: center; z-index: 70;
width: 90%; pointer-events: none;
}
.final-message h2 {
font-family: 'Dancing Script', cursive;
font-size: 3.5rem;
color: #ff4757;
opacity: 0; animation: fadeIn 3s ease forwards;
text-shadow: 3px 3px 0px rgba(255,255,255,1);
line-height: 1.2;
}

@keyframes fadeIn { to { opacity: 1; } }
.shake { animation: shake 0.4s; }
@keyframes shake { 0%, 100% {transform: translateX(0);} 25% {transform: translateX(-10px);} 75% {transform: translateX(10px);} }
</style>
</head>
<body>

<audio id="bg-music" loop>
<source src="audio.mp3" type="audio/mpeg">
</audio>

<div id="loader">
<div class="heart-box">
<div class="heart-shape"><div class="heart-fill" id="fill-anim"></div></div>
</div>
<div id="loading-text">LOADING LOVE... 0%</div>
</div>

<div id="lock-screen">
<div class="glass-card">
<div class="cute-icon">💌</div>
<h2>For My Love</h2>
<p>I have a secret question for you...</p>
<div class="input-group">
<input type="text" id="password-input" placeholder="Type the password...">
</div>
<button class="unlock-btn" onclick="checkPassword()">Open Letter ❤️</button>
</div>
</div>

<div class="card" id="main-card">
<div class="gif-area">
<img id="current-gif" src="1.gif" alt="Cute GIF">
</div>
<h1 id="main-text">Do you love me?? 🥺</h1>
<p id="sub-text">Chiku is all yours ❤️</p>
<div class="btn-container">
<button id="yes-btn">Yes</button>
<button id="no-btn">No</button>
</div>
</div>

<div id="success-container">
<div class="final-message">
<h2>I knew you loved me! ❤️</h2>
</div>
<canvas id="world"></canvas>
</div>

<script>
// --- 1. SETUP & LOADER ---
const assets = ['1.gif', '2.gif', '3.gif', '4.gif', '5.gif', '6.gif', '7.gif', 'audio.mp3'];
let loadedCount = 0;
const fillAnim = document.getElementById('fill-anim');
const loadText = document.getElementById('loading-text');
const loader = document.getElementById('loader');
const lockScreen = document.getElementById('lock-screen');
let heartInterval;

window.onload = function() {
startHeartRain();
assets.forEach(src => {
const img = new Image();
img.src = src;
loadedCount++;
const percent = Math.floor((loadedCount / assets.length) * 100);
fillAnim.style.height = percent + '%';
loadText.innerText = `LOADING LOVE... ${percent}%`;
});
setTimeout(() => {
loader.style.opacity = '0';
setTimeout(() => { loader.style.display = 'none'; lockScreen.style.display = 'flex'; }, 500);
}, 1000);
};

function startHeartRain() {
heartInterval = setInterval(() => {
const heart = document.createElement('div');
heart.classList.add('rain-heart');
heart.innerHTML = Math.random() > 0.5 ? '❤️' : '💖';
heart.style.left = Math.random() * 100 + 'vw';
heart.style.animationDuration = Math.random() * 2 + 3 + 's';
heart.style.opacity = Math.random() * 0.5 + 0.3;
document.body.appendChild(heart);
setTimeout(() => { heart.remove(); }, 5000);
}, 300);
}

// --- 2. LOCK LOGIC (Pass: aksa ) ---
function checkPassword() {
const passInput = document.getElementById('password-input');
const audio = document.getElementById('bg-music');
const mainCard = document.getElementById('main-card');

if (passInput.value.toLowerCase().trim() === 'aksa') {
audio.play().catch(e => console.log("Audio interaction needed"));
lockScreen.style.opacity = '0';
setTimeout(() => {
lockScreen.style.display = 'none';
mainCard.style.display = 'block';
}, 500);
} else {
passInput.classList.add('shake');
setTimeout(() => passInput.classList.remove('shake'), 400);
}
}

// --- 3. PROPOSAL LOGIC ---
const questions = [
{ text: "Please think again!", sub: "Itni jaldi na matt bolo 😣", gif: "2.gif" },
{ text: "Ek aur baar Soch lo!", sub: "kyu aisa kar rahi ho Plzz Man jao 😭", gif: "3.gif" },
{ text: "Baby Man jao na!", sub: "bhut glt baat hai yrr 🥺", gif: "4.gif" },
{ text: "I am gonna cry...", sub: "Pakka ro dunga main! 😭", gif: "5.gif" },
{ text: "You are breaking my heart", sub: "Aisa mat karo please... 💔", gif: "6.gif" },
{ text: "Last chance!", sub: "Dil toot jayega mera 💔", gif: "7.gif" }
];

let clickCount = 0;
let isTeleporting = false;
let teleportCount = 0;

const noBtn = document.getElementById('no-btn');
const yesBtn = document.getElementById('yes-btn');
const mainText = document.getElementById('main-text');
const subText = document.getElementById('sub-text');
const gifImg = document.getElementById('current-gif');

noBtn.addEventListener('click', () => {
if (isTeleporting) return;

if (clickCount < questions.length) {
const q = questions[clickCount];
mainText.style.opacity = 0;
subText.style.opacity = 0;
setTimeout(() => {
mainText.innerText = q.text;
subText.innerText = q.sub;
gifImg.src = q.gif;
mainText.style.opacity = 1;
subText.style.opacity = 1;
}, 200);
clickCount++;
}

if (clickCount === 6) {
isTeleporting = true;
noBtn.innerText = "No 👻";
}
});

const runAway = (e) => {
if (!isTeleporting) return;
e.preventDefault();
teleportCount++;
const x = Math.random() * (window.innerWidth - noBtn.offsetWidth - 40) + 20;
const y = Math.random() * (window.innerHeight - noBtn.offsetHeight - 40) + 20;
noBtn.style.position = 'fixed';
noBtn.style.left = `${x}px`;
noBtn.style.top = `${y}px`;

// CHANGED: Increased to 5 teleports
if (teleportCount >= 5) {
noBtn.style.opacity = '0';
setTimeout(() => { noBtn.style.display = 'none'; }, 300);
}
};

noBtn.addEventListener('mouseover', runAway);
noBtn.addEventListener('touchstart', runAway);

// --- SUCCESS TRIGGER ---
yesBtn.addEventListener('click', () => {
clearInterval(heartInterval);
document.getElementById('main-card').style.display = 'none';
document.getElementById('success-container').style.display = 'block';
initCanvas();
animate();
});

// --- 4. TREE ANIMATION (Reduced Width) ---
const canvas = document.getElementById('world');
const ctx = canvas.getContext('2d');
let width, height;
let branches = [];
let leaves = [];
const maxGeneration = 8;

function initCanvas() {
width = window.innerWidth;
height = window.innerHeight;
canvas.width = width;
canvas.height = height;
const root = {
x: width / 2,
y: height,
angle: -Math.PI / 2,
length: 110, // Slightly shorter for mobile
width: 10, // CHANGED: Thinner width for mobile
generation: 0,
progress: 0,
done: false
};
branches.push(root);
}

function drawHeart(x, y, size, color, angle) {
ctx.save();
ctx.translate(x, y);
ctx.rotate(angle);
ctx.fillStyle = color;
ctx.shadowBlur = 5;
ctx.shadowColor = color;
ctx.beginPath();
const topCurve = size * 0.3;
ctx.moveTo(0, topCurve);
ctx.bezierCurveTo(0, 0, -size/2, 0, -size/2, topCurve);
ctx.bezierCurveTo(-size/2, (size + topCurve)/2, 0, (size + topCurve)/2, 0, size);
ctx.bezierCurveTo(0, (size + topCurve)/2, size/2, (size + topCurve)/2, size/2, topCurve);
ctx.bezierCurveTo(size/2, 0, 0, 0, 0, topCurve);
ctx.closePath();
ctx.fill();
ctx.restore();
}

function animate() {
ctx.clearRect(0, 0, width, height);
branches.forEach((b) => {
if (!b.done) {
b.progress += 0.02;
if (b.progress >= 1) {
b.progress = 1;
b.done = true;
if (b.generation < maxGeneration) {
const leftAngle = b.angle - (0.3 + Math.random() * 0.2);
const rightAngle = b.angle + (0.3 + Math.random() * 0.2);
const newLen = b.length * 0.75;
const newWidth = b.width * 0.7;

branches.push({ x: b.x + Math.cos(b.angle) * b.length, y: b.y + Math.sin(b.angle) * b.length, angle: leftAngle, length: newLen, width: newWidth, generation: b.generation + 1, progress: 0, done: false });
branches.push({ x: b.x + Math.cos(b.angle) * b.length, y: b.y + Math.sin(b.angle) * b.length, angle: rightAngle, length: newLen, width: newWidth, generation: b.generation + 1, progress: 0, done: false });
} else {
createLeaves(b.x + Math.cos(b.angle) * b.length, b.y + Math.sin(b.angle) * b.length);
}
}
}
const currentLen = b.length * b.progress;
const endX = b.x + Math.cos(b.angle) * currentLen;
const endY = b.y + Math.sin(b.angle) * currentLen;
ctx.beginPath();
ctx.moveTo(b.x, b.y);
ctx.lineTo(endX, endY);
ctx.strokeStyle = '#9d5c55';
ctx.lineWidth = b.width;
ctx.lineCap = 'round';
ctx.stroke();
});

leaves.forEach(leaf => {
leaf.scale = Math.min(leaf.scale + 0.02, leaf.maxScale);
leaf.angle += Math.sin(Date.now() / 500 + leaf.x) * 0.002;
drawHeart(leaf.x, leaf.y, leaf.scale * 15, leaf.color, leaf.angle);
});

requestAnimationFrame(animate);
}

function createLeaves(x, y) {
const count = 5 + Math.random() * 5;
for(let i=0; i<count; i++) {
leaves.push({
x: x + (Math.random() - 0.5) * 40,
y: y + (Math.random() - 0.5) * 40,
angle: Math.random() * Math.PI * 2,
color: Math.random() > 0.5 ? '#ec4899' : '#fbcfe8',
maxScale: 0.5 + Math.random() * 1.5,
scale: 0
});
}
}

window.addEventListener('resize', () => {
width = window.innerWidth;
height = window.innerHeight;
canvas.width = width;
canvas.height = height;
});

</script>
</body>
</html>
