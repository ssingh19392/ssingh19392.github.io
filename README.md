<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Kanishka ❤️ Saurabh</title>
<style>
body{
 margin:0;height:100vh;display:flex;align-items:center;justify-content:center;
 font-family:Arial;background:linear-gradient(135deg,#ff9a9e,#fad0c4);
 overflow:hidden;
}
.card{
 background:white;padding:30px;border-radius:22px;
 text-align:center;width:360px;
 box-shadow:0 12px 35px rgba(0,0,0,.25);
 position:relative;
}
.names{color:#666;margin-bottom:8px}
h1{color:#ff4d6d}
button{
 padding:12px 26px;border:none;border-radius:30px;
 font-size:18px;cursor:pointer;margin:10px;
}
#yes{background:#ff4d6d;color:white}
#no{background:#ccc;position:absolute}
.section{display:none;color:#ff4d6d}
.ring{
 font-size:60px;margin:10px 0;
 animation:sparkle 1.5s infinite;
}
@keyframes sparkle{
 0%{filter:drop-shadow(0 0 5px gold);transform:scale(1)}
 50%{filter:drop-shadow(0 0 20px gold);transform:scale(1.15)}
 100%{filter:drop-shadow(0 0 5px gold);transform:scale(1)}
}
.timer{font-size:14px;color:#555}
.heart{
 position:fixed;bottom:-10px;font-size:20px;
 animation:float 4s linear infinite;color:#ff4d6d;
}
@keyframes float{
 to{transform:translateY(-100vh);opacity:0}
}
.proposal{
 display:none;color:#ff4d6d;
}
.footer{margin-top:10px;font-size:13px;color:#777}
</style>
</head>
<body>
<div class="card">
<div class="names">Kanishka 💕 Saurabh</div>
<!-- STEP 1 -->
<div id="step1">
<h1>Will you be my Valentine, Kanishka? 💖</h1>
<button id="yes">Yes ❤️</button>
<button id="no">No 🙈</button>
</div>
<!-- STEP 2 -->
<div class="section" id="step2">
<p>I love you ❤️</p>
<div class="ring">💍</div>
<div><i>Forever starts today</i></div>
<div class="timer" id="timer"></div>
</div>
<!-- STEP 3 -->
<div class="proposal" id="step3">
<h2>Will you marry me? 💍</h2>
<button onclick="finalYes()">Yes, forever ❤️</button>
<div class="footer">
     Engraved on <span id="date"></span><br>— Saurabh
</div>
</div>
</div>
<audio id="music" loop>
<source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3">
</audio>
<script>
const yes=document.getElementById("yes"),
no=document.getElementById("no"),
step1=document.getElementById("step1"),
step2=document.getElementById("step2"),
step3=document.getElementById("step3"),
music=document.getElementById("music"),
timer=document.getElementById("timer");
let start=localStorage.getItem("foreverStart");
if(start){showForever();}
yes.onclick=()=>{
 start=Date.now();
 localStorage.setItem("foreverStart",start);
 showForever();
 setTimeout(()=>step3.style.display="block",7000);
};
no.onmouseover=()=>{
 no.style.left=Math.random()*80+"%";
 no.style.top=Math.random()*80+"%";
};
function showForever(){
 step1.style.display="none";
 step2.style.display="block";
 music.play();
 hearts();
 update();setInterval(update,1000);
}
function update(){
 const d=Date.now()-start;
 timer.innerText=
  `Together for ${Math.floor(d/86400000)}d ${new Date(d).toISOString().substr(11,8)} 💖`;
}
function hearts(){
 setInterval(()=>{
   const h=document.createElement("div");
   h.className="heart";h.innerText="❤️";
   h.style.left=Math.random()*100+"vw";
   document.body.appendChild(h);
   setTimeout(()=>h.remove(),5000);
 },300);
}
document.getElementById("date").innerText=
new Date().toLocaleDateString("en-GB",{day:"2-digit",month:"long",year:"numeric"});
function finalYes(){
 alert("Forever locked ❤️💍");
}
</script>
</body>
</html>
