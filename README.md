[foryou.html](https://github.com/user-attachments/files/26796024/foryou.html)
<!DOCTYPE html>
<html lang="cs">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You ❤️</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial;}
body{background:black;color:white;overflow:hidden;}

.lock-screen{
position:fixed;width:100%;height:100vh;background:black;
display:flex;flex-direction:column;justify-content:center;align-items:center;
z-index:999;text-align:center;
}

.lock-screen input{
padding:10px;margin-top:15px;border:none;border-radius:5px;text-align:center;
}

.lock-screen button{
margin-top:10px;padding:10px 20px;background:#ff2b2b;border:none;color:white;
cursor:pointer;
}

.error{color:#ff2b2b;margin-top:10px;}

.container{
height:100vh;
overflow-y:scroll;
scroll-snap-type:y mandatory;
display:none;
}

.slide{
height:100vh;
scroll-snap-align:start;
position:relative;
display:flex;
justify-content:center;
align-items:center;
text-align:center;
padding:20px;
}

.glow{
font-size:36px;
color:#ff2b2b;
text-shadow:0 0 10px #ff2b2b,0 0 25px #ff0000;
animation:pulse 2s infinite;
}

@keyframes pulse{
0%{text-shadow:0 0 10px #ff2b2b;}
50%{text-shadow:0 0 35px #ff0000;}
100%{text-shadow:0 0 10px #ff2b2b;}
}

.image-slide img{
width:100%;
height:100%;
object-fit:cover;
animation:zoom 10s ease-in-out infinite alternate;
}

@keyframes zoom{
from{transform:scale(1);}
to{transform:scale(1.1);}
}

.side-icons{
position:absolute;
right:15px;
bottom:120px;
display:flex;
flex-direction:column;
gap:20px;
font-size:26px;
z-index:5;
}

.icon{cursor:pointer;}
.count{font-size:13px;}

.caption{
position:absolute;
bottom:40px;
left:15px;
text-align:left;
max-width:70%;
font-size:14px;
}

.comments{
position:fixed;
bottom:-100%;
left:0;
width:100%;
height:60%;
background:#111;
transition:0.4s;
padding:20px;
overflow-y:auto;
z-index:20;
}

.comments.show{bottom:0;}
.comment{margin-bottom:10px;font-size:14px;}
.close-btn{
margin-top:10px;padding:8px;background:#ff2b2b;
border:none;color:white;cursor:pointer;
}

.slide{
position:relative;
}
</style>
</head>

<body>

<!-- LOCK -->
<div class="lock-screen" id="lock">
<h1>Private For You Page</h1>
<p>Zadej heslo</p>
<input type="text" id="passwordInput">
<button onclick="unlock()">Odemknout</button>
<div class="error" id="errorMsg"></div>
</div>

<div class="container" id="feed">

<!-- SLIDE 1 -->
<div class="slide">
<div>
<h1>POV:</h1>
Poznáš někoho online<br>a změní ti běžný dny.
</div>

<div class="side-icons">
<div class="icon" onclick="like(this)">❤️<div class="count">231</div></div>
<div class="icon" onclick="openComments(1)">💬<div class="count">3</div></div>
<div class="icon" onclick="repost(this)">🔁<div class="count">12</div></div>
</div>
</div>

<!-- SLIDE 2 -->
<div class="slide">

<div>
<div class="glow">Simis</div>

<div style="margin-top:12px;font-size:18px;line-height:1.4;">
15 🎂<br>
real vibes only
</div>
</div>

<div class="side-icons">
<div class="icon" onclick="like(this)">❤️<div class="count">487</div></div>
<div class="icon" onclick="openComments(2)">💬<div class="count">4</div></div>
<div class="icon" onclick="repost(this)">🔁<div class="count">21</div></div>
</div>

</div>

<!-- SLIDE 3 -->
<div class="slide image-slide" id="photoSlide">

<img src="simis.jpg">

<div class="side-icons">
<div class="icon" onclick="like(this)">❤️<div class="count">999</div></div>
<div class="icon" onclick="openComments(3)">💬<div class="count">5</div></div>
<div class="icon" onclick="repost(this)">🔁<div class="count">88</div></div>
</div>

<div class="caption"><b>@Simis</b><br>black • red • white</div>
</div>

<!-- SLIDE 4 -->
<div class="slide">
<div>
<h1>Happy Birthday ❤️</h1>
I když jsme na dálku,<br>
některý věci jsou blíž než se zdá.
</div>

<div class="side-icons">
<div class="icon" onclick="like(this)">❤️<div class="count">1200</div></div>
<div class="icon" onclick="openComments(4)">💬<div class="count">6</div></div>
<div class="icon" onclick="repost(this)">🔁<div class="count">150</div></div>
</div>
</div>

<!-- SLIDE 5 -->
<div class="slide">

<div style="text-align:center;max-width:80%;">
<h1>pro Simis ❤️</h1>

<div style="font-size:16px;line-height:1.6;margin-top:15px;">
Někdy člověk nepotřebuje milion věcí.<br><br>

Stačí pár momentů.<br>
Pár „panáků fotbalu“, co zůstanou v hlavě.<br><br>

Smích, co nezmizí ani přes obrazovku.<br>
A RedBull večery, co jsou víc vzpomínka než nápoj.<br><br>

A Mia 🐱<br>
malá kočka, co dělá klidnější svět.<br><br>

Nejde o dokonalost.<br>
Jde o to, že to bylo opravdový.
</div>
</div>

<div class="side-icons">
<div class="icon" onclick="like(this)">❤️<div class="count">777</div></div>
<div class="icon" onclick="openComments(5)">💬<div class="count">8</div></div>
<div class="icon" onclick="repost(this)">🔁<div class="count">33</div></div>
</div>

</div>

</div>

<!-- MUSIC -->
<audio id="music" src="jerusalema.mp3"></audio>

<!-- COMMENTS -->
<div class="comments" id="commentBox">
<div id="commentContent"></div>
<button class="close-btn" onclick="closeComments()">Zavřít</button>
</div>

<script>
let musicStarted=false;

function unlock(){
let pass=document.getElementById("passwordInput").value;
if(pass==="Simis"){
document.getElementById("lock").style.display="none";
document.getElementById("feed").style.display="block";
}else{
document.getElementById("errorMsg").innerText="Špatné heslo.";
}
}

function like(el){
el.querySelector(".count").innerText++;
}

function repost(el){
el.querySelector(".count").innerText++;
}

/* MUSIC ON PHOTO SLIDE */
document.getElementById("feed").addEventListener("scroll",()=>{
let slide=document.elementFromPoint(window.innerWidth/2,window.innerHeight/2);

if(slide && slide.id==="photoSlide" && !musicStarted){
document.getElementById("music").play();
musicStarted=true;
}
});

function openComments(i){
let data={
1:["this is actually cute","bro this is real","she deserves this"],
2:["Simis energy 🔥","15 and iconic","this glow up crazy"],
3:["nah she pretty fr","this pic hits different","black red white vibe 🖤"],
4:["happy birthday ❤️","W effort","this is wholesome"],
5:["this hit deep ❤️","Mia the cat 🐱","RedBull nights >>>"]
};

let box=document.getElementById("commentContent");
box.innerHTML="";
data[i].forEach(t=>{
let d=document.createElement("div");
d.className="comment";
d.innerText=t;
box.appendChild(d);
});

document.getElementById("commentBox").classList.add("show");
}

function closeComments(){
document.getElementById("commentBox").classList.remove("show");
}
</script>

</body>
</html>
