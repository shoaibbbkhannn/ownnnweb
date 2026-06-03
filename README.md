# ownnnweb
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Best Friend</title>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Segoe UI',sans-serif;
}

body{
background:linear-gradient(135deg,#0f172a,#1e1b4b,#312e81);
color:white;
overflow-x:hidden;
min-height:100vh;
}

.hero{
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
text-align:center;
padding:20px;
}

h1{
font-size:4rem;
margin-bottom:20px;
animation:glow 2s infinite alternate;
}

@keyframes glow{
from{ text-shadow:0 0 10px #fff; }
to{ text-shadow:0 0 30px #ff4d94; }
}

.subtitle{
font-size:1.4rem;
max-width:700px;
line-height:1.8;
}

.btn{
margin-top:30px;
padding:15px 35px;
background:#ff4d94;
border:none;
border-radius:50px;
color:white;
font-size:1rem;
cursor:pointer;
transition:.3s;
}

.btn:hover{
transform:scale(1.1);
}

.hidden{
display:none;
}

#surprise{
margin-top:30px;
font-size:1.3rem;
max-width:700px;
line-height:1.8;
}

.memory{
padding:80px 20px;
text-align:center;
}

.memory h2{
margin-bottom:30px;
font-size:2.5rem;
}

.card{
background:rgba(255,255,255,0.1);
backdrop-filter:blur(10px);
padding:20px;
border-radius:20px;
max-width:700px;
margin:auto;
}

.stars{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
z-index:-1;
}

.star{
position:absolute;
background:white;
border-radius:50%;
animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
from{opacity:.2}
to{opacity:1}
}

.balloon{
position:fixed;
bottom:-120px;
width:50px;
height:70px;
border-radius:50%;
animation:float linear infinite;
}

@keyframes float{
to{
transform:translateY(-120vh);
}
}
</style>
</head>

<body>

<div class="stars"></div>

<section class="hero">
<h1>🎂 Happy Birthday, Best Friend! 🎂</h1>

<p class="subtitle" id="typewriter"></p>

<button class="btn" onclick="showSurprise()">
🎁 Open Your Surprise
</button>

<div id="surprise" class="hidden">
❤️ Thank you for being my best friend.
Every memory with you is special.
May your life be filled with happiness, success,
and countless beautiful moments.

Happy Birthday! 🎉
</div>
</section>

<section class="memory">
<h2>📸 Our Friendship Story</h2>

<div class="card">
<p>
Replace this text with your favorite memories together.
Add funny stories, inside jokes, trips, school memories,
or anything that makes your friendship unique.
</p>
</div>
</section>

<script>

// Typewriter Effect
const text =
"Today is all about celebrating one of the most amazing people in my life. Thank you for every laugh, every memory, and every moment of support. You deserve all the happiness in the world.";

let i=0;
function typeWriter(){
if(i<text.length){
document.getElementById("typewriter").innerHTML += text.charAt(i);
i++;
setTimeout(typeWriter,40);
}
}
typeWriter();

// Surprise
function showSurprise(){
document.getElementById("surprise").classList.remove("hidden");
}

// Stars
const stars=document.querySelector(".stars");

for(let i=0;i<150;i++){
let star=document.createElement("div");
star.classList.add("star");
let size=Math.random()*3;
star.style.width=size+"px";
star.style.height=size+"px";
star.style.left=Math.random()*100+"%";
star.style.top=Math.random()*100+"%";
stars.appendChild(star);
}

// Balloons
const colors=["#ff4d94","#ffd700","#00e5ff","#7c4dff","#69f0ae"];

for(let i=0;i<15;i++){
let balloon=document.createElement("div");
balloon.classList.add("balloon");
balloon.style.left=Math.random()*100+"vw";
balloon.style.background=
colors[Math.floor(Math.random()*colors.length)];
balloon.style.animationDuration=
(8+Math.random()*10)+"s";
document.body.appendChild(balloon);
}
</script>

</body>
</html>
```
