# Presente-para-ver-nica-<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Uma Surpresa ❤️</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">

<style>
*{margin:0;padding:0;box-sizing:border-box;}
body{
background:linear-gradient(180deg,#0d0d1f,#1c102d,#0d0d1f);
font-family:Poppins,sans-serif;
color:white;
overflow-x:hidden;
}

canvas{
position:fixed;
top:0;
left:0;
z-index:-1;
}

.container{
max-width:900px;
margin:auto;
padding:40px 20px;
text-align:center;
}

h1{
font-family:'Dancing Script';
font-size:65px;
color:#ff7aa8;
margin-top:40px;
text-shadow:0 0 15px #ff4f88;
}

#typing{
font-size:22px;
margin-top:20px;
min-height:70px;
}

.card{
margin-top:40px;
background:rgba(255,255,255,.06);
border-radius:25px;
padding:25px;
backdrop-filter:blur(10px);
box-shadow:0 0 30px rgba(255,0,100,.25);
}

.gallery{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
gap:15px;
margin-top:20px;
}

.gallery img{
width:100%;
border-radius:15px;
transition:.4s;
}

.gallery img:hover{
transform:scale(1.05);
}

button{
margin-top:20px;
padding:15px 35px;
border:none;
border-radius:40px;
background:#ff4f88;
color:white;
font-size:18px;
cursor:pointer;
transition:.3s;
}

button:hover{
transform:scale(1.08);
}

footer{
margin:50px;
font-size:18px;
color:#ffc0d6;
}

.heart{
position:fixed;
color:red;
animation:fall 8s linear infinite;
}

@keyframes fall{
0%{transform:translateY(-100px);}
100%{transform:translateY(110vh);}
}
</style>

</head>
<body>

<canvas id="stars"></canvas>

<div class="container">

<h1>Oi, meu amor ❤️</h1>

<div id="typing"></div>

<div class="card">

<h2>📸 Nossos Momentos</h2>

<div class="gallery">

<img src="https://picsum.photos/300?1">
<img src="https://picsum.photos/300?2">
<img src="https://picsum.photos/300?3">
<img src="https://picsum.photos/300?4">

</div>

<button onclick="window.open('https://open.spotify.com')">
🎵 Nossa Música
</button>

<br>

<button onclick="window.open('https://youtube.com')">
🎥 Minha Mensagem
</button>

</div>

<footer>

❤️ Você é uma das melhores partes da minha vida.<br><br>

Com carinho...

</footer>

</div>

<script>

const texto="Se você chegou até aqui, é porque encontrou este pequeno presente. Espero que cada palavra faça você sorrir. ❤️";

let i=0;

function escrever(){

if(i<texto.length){

document.getElementById("typing").innerHTML+=texto.charAt(i);

i++;

setTimeout(escrever,50);

}

}

escrever();

for(let i=0;i<40;i++){

let h=document.createElement("div");

h.className="heart";

h.innerHTML="❤️";

h.style.left=Math.random()*100+"vw";

h.style.fontSize=(15+Math.random()*20)+"px";

h.style.animationDuration=(4+Math.random()*6)+"s";

document.body.appendChild(h);

}

const canvas=document.getElementById("stars");
const ctx=canvas.getContext("2d");

canvas.width=window.innerWidth;
canvas.height=window.innerHeight;

let stars=[];

for(let i=0;i<120;i++){

stars.push({
x:Math.random()*canvas.width,
y:Math.random()*canvas.height,
r:Math.random()*2
});

}

function draw(){

ctx.clearRect(0,0,canvas.width,canvas.height);

ctx.fillStyle="white";

stars.forEach(s=>{

ctx.beginPath();

ctx.arc(s.x,s.y,s.r,0,Math.PI*2);

ctx.fill();

});

requestAnimationFrame(draw);

}

draw();

</script>

</body>
</html>
