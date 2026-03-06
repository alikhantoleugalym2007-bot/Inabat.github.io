<!DOCTYPE html>
<html lang="kk">
<head>
<meta charset="UTF-8">
<title>8 Наурыз</title>

<style>

body{
margin:0;
height:100vh;
display:flex;
justify-content:center;
align-items:center;
background:linear-gradient(135deg,#ffb6d9,#ffddee);
font-family:Arial;
overflow:hidden;
}

.card{
width:360px;
height:480px;
perspective:1000px;
}

.card-inner{
width:100%;
height:100%;
position:relative;
transition:transform 1s;
transform-style:preserve-3d;
}

.card.open .card-inner{
transform:rotateY(180deg);
}

.card-front,.card-back{
position:absolute;
width:100%;
height:100%;
backface-visibility:hidden;
border-radius:15px;
box-shadow:0 10px 25px rgba(0,0,0,0.2);
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
text-align:center;
padding:20px;
}

.card-front{
background:#ff4fa3;
color:white;
}

.card-back{
background:white;
transform:rotateY(180deg);
overflow:auto;
}

button{
padding:10px 20px;
margin:8px;
font-size:18px;
border:none;
border-radius:10px;
cursor:pointer;
}

#yes{
background:#4CAF50;
color:white;
}

#no{
background:#ff4444;
color:white;
position:relative;
}

.photo-frame{
width:220px;
height:220px;
border:6px solid #ff6fb5;
border-radius:15px;
overflow:hidden;
box-shadow:0 6px 15px rgba(0,0,0,0.2);
margin-bottom:15px;
}

.photo-frame img{
width:100%;
height:100%;
object-fit:cover;
}

.text{
font-size:15px;
line-height:1.5;
color:#333;
}

.heart{
position:absolute;
color:red;
font-size:22px;
animation:fall linear infinite;
}

@keyframes fall{

0%{
transform:translateY(-100px);
opacity:1;
}

100%{
transform:translateY(100vh);
opacity:0;
}

}

</style>
</head>

<body>

<div class="card" id="card">
<div class="card-inner">

<div class="card-front">

<h2>Открыть? 💌</h2>

<div>
<button id="yes">Да</button>
<button id="no">Нет</button>
</div>

</div>

<div class="card-back">

<div class="photo-frame">

<img src="https://i.ibb.co.com/vtS03jQ/Whats-App-Image-2026-03-05-at-23-26-11.jpg">

</div>

<div class="text">

💐 Қадірлі де қымбатты Инабат! 💐 <br><br>

Көктемнің шуақты мерекесі –  
8 наурыз күнімен шын жүректен құттықтаймын.

Жаратқан саған нәзіктік пен көрік,  
ақыл мен мейірім берген екен.

Жүрегің әрдайым қуанышқа толы болып,  
өмір жолың бақыт пен берекеге кенелсін.

Көңілің көктемнің гүліндей құлпырып,  
жүзіңнен күлкі кетпесін.

❤️

</div>

</div>

</div>
</div>

<audio id="bgMusic" autoplay loop>
<source src="https://github.com/alikhantoleugalym2007-bot/alikhan4/raw/refs/heads/main/Lana%20Del%20Rey%20-%20Cinnamon%20Girl%20Lyrics%20(4).mp3" type="audio/mpeg">
</audio>

<script>
window.addEventListener("click", function() {
  const music = document.getElementById("bgMusic");
  music.play();
});
</script>

<script>

const yes=document.getElementById("yes");
const no=document.getElementById("no");
const card=document.getElementById("card");

yes.onclick=()=>{
card.classList.add("open");
setInterval(createHeart,200);
}

no.onmouseover=()=>{

const x=Math.random()*200-100;
const y=Math.random()*200-100;

no.style.transform=`translate(${x}px,${y}px)`;

}

function createHeart(){

const heart=document.createElement("div");

heart.className="heart";
heart.innerHTML="❤️";

heart.style.left=Math.random()*100+"%";
heart.style.animationDuration=(Math.random()*3+2)+"s";

document.body.appendChild(heart);

setTimeout(()=>{
heart.remove();
},5000);

}

</script>

</body>
</html>
