# ownnnweb
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Best Friend ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins',sans-serif;
}

body{
    background:linear-gradient(135deg,#0f172a,#1e293b,#312e81);
    color:white;
    overflow:hidden;
    height:100vh;
}

.container{
    position:relative;
    z-index:10;
    text-align:center;
    top:50%;
    transform:translateY(-50%);
}

h1{
    font-size:4rem;
    color:#ffd700;
    text-shadow:0 0 20px #ffd700;
}

#message{
    margin:20px auto;
    max-width:700px;
    font-size:1.3rem;
    min-height:120px;
}

img{
    width:220px;
    height:220px;
    border-radius:50%;
    object-fit:cover;
    border:5px solid white;
    box-shadow:0 0 30px rgba(255,255,255,.5);
    margin:20px 0;
}

button{
    padding:15px 30px;
    border:none;
    border-radius:30px;
    background:#ff4081;
    color:white;
    font-size:1rem;
    cursor:pointer;
    transition:.3s;
}

button:hover{
    transform:scale(1.1);
}

.balloon{
    position:absolute;
    bottom:-150px;
    width:60px;
    height:80px;
    border-radius:50%;
    animation:float 10s linear infinite;
}

@keyframes float{
    from{
        transform:translateY(0);
    }
    to{
        transform:translateY(-120vh);
    }
}

.stars{
    position:absolute;
    width:100%;
    height:100%;
}

.star{
    position:absolute;
    width:3px;
    height:3px;
    background:white;
    border-radius:50%;
    animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
    from{opacity:.2;}
    to{opacity:1;}
}

#surpriseText{
    margin-top:20px;
    color:#ffeb3b;
    font-size:1.5rem;
    display:none;
}
</style>
</head>

<body>

<div class="stars"></div>

<div class="container">
    <h1>🎂 Happy Birthday!</h1>

    <!-- Replace with your friend's photo -->
    <img src="friend.jpg" alt="Best Friend">

    <div id="message"></div>

    <button onclick="showSurprise()">🎁 Open Surprise</button>

    <div id="surpriseText">
        You are not just my best friend, you are family. ❤️<br>
        Thank you for every laugh, every memory, and every moment.
    </div>

    <!-- Optional Birthday Music -->
    <audio autoplay loop>
        <source src="birthday.mp3" type="audio/mpeg">
    </audio>
</div>

<script>
// Typewriter Effect
const text =
"Dear Best Friend,\n\nToday is all about YOU! ✨\nThank you for being the person who always supports me, understands me, and makes life brighter.\nMay this year bring endless happiness, success, and unforgettable memories.\n\nHappy Birthday! ❤️";

let i = 0;
function typeWriter(){
    if(i < text.length){
        document.getElementById("message").innerHTML +=
        text.charAt(i) === "\n" ? "<br>" : text.charAt(i);
        i++;
        setTimeout(typeWriter, 40);
    }
}
typeWriter();

// Stars
const starsContainer = document.querySelector(".stars");
for(let i=0;i<150;i++){
    let star = document.createElement("div");
    star.classList.add("star");
    star.style.left = Math.random()*100 + "%";
    star.style.top = Math.random()*100 + "%";
    star.style.animationDelay = Math.random()*2 + "s";
    starsContainer.appendChild(star);
}

// Balloons
const colors = ["#ff4081","#ffd700","#00e5ff","#7c4dff","#69f0ae"];

for(let i=0;i<15;i++){
    let balloon = document.createElement("div");
    balloon.classList.add("balloon");
    balloon.style.background = colors[Math.floor(Math.random()*colors.length)];
    balloon.style.left = Math.random()*100 + "%";
    balloon.style.animationDuration = (8 + Math.random()*8) + "s";
    document.body.appendChild(balloon);
}

// Surprise
function showSurprise(){
    document.getElementById("surpriseText").style.display = "block";

    for(let i=0;i<100;i++){
        let confetti = document.createElement("div");
        confetti.style.position="absolute";
        confetti.style.width="8px";
        confetti.style.height="8px";
        confetti.style.background=
            colors[Math.floor(Math.random()*colors.length)];
        confetti.style.left=Math.random()*100+"vw";
        confetti.style.top="-10px";
        confetti.style.borderRadius="50%";
        confetti.style.transition="3s linear";
        document.body.appendChild(confetti);

        setTimeout(()=>{
            confetti.style.top="100vh";
        },50);

        setTimeout(()=>{
            confetti.remove();
        },3000);
    }
}
</script>

</body>
</html>
