<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Para Sayury 💛</title>
<style>
*{
    box-sizing:border-box;
    -webkit-tap-highlight-color:transparent;
}
body{
    margin:0;
    height:100vh;
    overflow:hidden;
    font-family:Georgia,serif;
    background:
        radial-gradient(circle at 50% 20%,#fffde9,#fff5b5 45%,#f5d968);
}
/* =========================
   PANTALLA INICIAL
========================= */
.start{
    position:fixed;
    inset:0;
    z-index:50;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
    background:
        radial-gradient(circle,#fffef1,#fff1a8);
    transition:opacity 1.5s ease;
}
.start.hide{
    opacity:0;
    pointer-events:none;
}
.start h1{
    color:#9b7200;
    font-size:42px;
    margin:0 20px 10px;
    animation:fadeUp 2s ease;
}
.start p{
    color:#806c35;
    font-size:18px;
    margin-bottom:35px;
}
.start button{
    border:none;
    padding:16px 30px;
    border-radius:40px;
    background:#d9aa18;
    color:white;
    font-size:18px;
    box-shadow:0 8px 25px rgba(100,70,0,.25);
    animation:pulse 2s infinite;
}
/* =========================
   ESCENA
========================= */
.scene{
    width:100%;
    height:100vh;
    position:relative;
    display:flex;
    justify-content:center;
    align-items:flex-end;
}
/* estrellas */
.sparkle{
    position:absolute;
    color:#fff6a8;
    font-size:20px;
    animation:twinkle 2s infinite;
}
.s1{top:15%;left:15%}
.s2{top:22%;right:18%;animation-delay:.5s}
.s3{top:35%;left:8%;animation-delay:1s}
.s4{top:30%;right:8%;animation-delay:1.5s}
/* =========================
   NOMBRE
========================= */
.name{
    position:absolute;
    top:45px;
    width:100%;
    text-align:center;
    color:#9c7500;
    font-size:34px;
    letter-spacing:1px;
    animation:fadeDown 2s ease;
}
.name span{
    display:block;
    font-size:15px;
    margin-top:5px;
    color:#a28a4b;
}
/* =========================
   RAMO
========================= */
.bouquet{
    position:relative;
    width:340px;
    height:500px;
    margin-bottom:5px;
}
/* tallos */
.stem{
    position:absolute;
    bottom:105px;
    left:50%;
    width:7px;
    height:270px;
    background:linear-gradient(to right,#3c753a,#6ca85a);
    border-radius:20px;
    transform-origin:bottom;
}
.stem:nth-child(1){transform:rotate(-32deg)}
.stem:nth-child(2){transform:rotate(-18deg)}
.stem:nth-child(3){transform:rotate(-8deg)}
.stem:nth-child(4){transform:rotate(8deg)}
.stem:nth-child(5){transform:rotate(18deg)}
.stem:nth-child(6){transform:rotate(32deg)}
/* flores */
.flower{
    position:absolute;
    width:80px;
    height:80px;
    border-radius:50%;
    opacity:0;
    animation:flowerAppear 1.5s ease forwards,
             flowerFloat 4s ease-in-out infinite 1.5s;
    background:
      radial-gradient(circle at 50% 7%,#fff06a 0 18%,transparent 19%),
      radial-gradient(circle at 93% 35%,#ffd936 0 18%,transparent 19%),
      radial-gradient(circle at 77% 88%,#ffe45a 0 18%,transparent 19%),
      radial-gradient(circle at 23% 88%,#ffd936 0 18%,transparent 19%),
      radial-gradient(circle at 7% 35%,#ffe45a 0 18%,transparent 19%);
    
    filter:drop-shadow(0 5px 7px rgba(100,70,0,.2));
}
.flower:after{
    content:"";
    position:absolute;
    width:27px;
    height:27px;
    top:27px;
    left:27px;
    border-radius:50%;
    background:#a66a00;
    box-shadow:inset 0 0 0 5px #d58e00;
}
.f1{left:20px;top:120px;animation-delay:.4s}
.f2{left:75px;top:70px;animation-delay:.7s}
.f3{left:130px;top:40px;animation-delay:1s}
.f4{left:185px;top:75px;animation-delay:.8s}
.f5{left:240px;top:125px;animation-delay:.5s}
.f6{left:130px;top:105px;animation-delay:1.2s}
/* hojas */
.leaf{
    position:absolute;
    width:80px;
    height:35px;
    background:#57934d;
    border-radius:100% 0 100% 0;
}
.l1{
    left:35px;
    bottom:180px;
    transform:rotate(-35deg);
}
.l2{
    right:35px;
    bottom:200px;
    transform:scaleX(-1) rotate(-35deg);
}
.l3{
    left:95px;
    bottom:145px;
    transform:rotate(-20deg);
}
.l4{
    right:90px;
    bottom:135px;
    transform:scaleX(-1) rotate(-20deg);
}
/* papel */
.paper{
    position:absolute;
    bottom:10px;
    left:50%;
    transform:translateX(-50%);
    width:250px;
    height:160px;
    background:
        linear-gradient(135deg,#fffbe6,#eadc9c);
    clip-path:polygon(5% 0,95% 0,73% 100%,27% 100%);
    filter:drop-shadow(0 10px 12px rgba(0,0,0,.15));
}
.ribbon{
    position:absolute;
    bottom:105px;
    left:50%;
    width:130px;
    height:20px;
    transform:translateX(-50%);
    background:#d4a51a;
    border-radius:10px;
    z-index:3;
}
.ribbon:after,
.ribbon:before{
    content:"";
    position:absolute;
    width:35px;
    height:35px;
    border:5px solid #d4a51a;
    border-radius:50%;
    top:-8px;
}
.ribbon:before{
    left:-30px;
}
.ribbon:after{
    right:-30px;
}
/* =========================
   BOTÓN CARTA
========================= */
.open{
    position:absolute;
    bottom:25px;
    left:50%;
    transform:translateX(-50%);
    z-index:10;
    border:none;
    padding:14px 25px;
    border-radius:30px;
    background:#d5a817;
    color:white;
    font-size:16px;
    box-shadow:0 8px 20px rgba(100,70,0,.25);
}
/* =========================
   PÉTALOS
========================= */
.petal{
    position:absolute;
    top:-30px;
    width:13px;
    height:19px;
    background:#ffe34e;
    border-radius:70% 30% 70% 30%;
    opacity:.75;
    animation:fall linear infinite;
}
.p1{left:5%;animation-duration:8s}
.p2{left:20%;animation-duration:11s;animation-delay:2s}
.p3{left:40%;animation-duration:9s;animation-delay:1s}
.p4{left:65%;animation-duration:12s;animation-delay:3s}
.p5{left:85%;animation-duration:7s;animation-delay:1s}
/* =========================
   CARTA
========================= */
.letterScreen{
    position:fixed;
    inset:0;
    z-index:100;
    display:none;
    justify-content:center;
    align-items:center;
    padding:22px;
    background:rgba(255,247,196,.96);
}
.letterScreen.show{
    display:flex;
    animation:fadeUp .8s ease;
}
.letter{
    position:relative;
    width:100%;
    max-width:390px;
    padding:45px 28px 35px;
    background:#fffdf3;
    border-radius:5px;
    box-shadow:0 20px 60px rgba(70,50,0,.25);
    text-align:center;
}
.letter:before{
    content:"";
    position:absolute;
    inset:12px;
    border:1px solid #ead99a;
    pointer-events:none;
}
.letter h2{
    position:relative;
    color:#a87900;
    font-size:32px;
    margin:0 0 22px;
}
.letter p{
    position:relative;
    color:#574d2e;
    font-size:19px;
    line-height:1.8;
}
.signature{
    position:relative;
    margin-top:25px;
    color:#a87900;
    font-size:20px;
    font-style:italic;
}
.bigHeart{
    font-size:42px;
    margin-top:15px;
    animation:heart 1.3s infinite;
}
.close{
    margin-top:20px;
    border:none;
    background:none;
    color:#a87900;
    font-size:15px;
}
/* =========================
   ANIMACIONES
========================= */
@keyframes flowerAppear{
    from{
        opacity:0;
        transform:scale(0);
    }
    to{
        opacity:1;
        transform:scale(1);
    }
}
@keyframes flowerFloat{
    0%,100%{margin-top:0}
    50%{margin-top:-7px}
}
@keyframes fall{
    from{
        transform:translateY(-30px) rotate(0);
    }
    to{
        transform:translateY(110vh) rotate(360deg);
    }
}
@keyframes twinkle{
    0%,100%{opacity:.2;transform:scale(.7)}
    50%{opacity:1;transform:scale(1.3)}
}
@keyframes pulse{
    0%,100%{transform:scale(1)}
    50%{transform:scale(1.06)}
}
@keyframes heart{
    0%,100%{transform:scale(1)}
    50%{transform:scale(1.2)}
}
@keyframes fadeUp{
    from{
        opacity:0;
        transform:translateY(20px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}
@keyframes fadeDown{
    from{
        opacity:0;
        transform:translateY(-20px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}
</style>
</head>
<body>
<!-- PANTALLA DE INICIO -->
<div class="start" id="start">
    <h1>Para Sayury 💛</h1>
    <p>
        Hay algo que preparé especialmente para ti...
    </p>
    <button onclick="startGift()">
        🌻 Abrir mi regalo
    </button>
</div>
<!-- ESCENA -->
<div class="scene">
    <div class="name">
        Sayury 💛
        <span>Un pequeño detalle hecho con mucho amor</span>
    </div>
    <div class="sparkle s1">✦</div>
    <div class="sparkle s2">✧</div>
    <div class="sparkle s3">✦</div>
    <div class="sparkle s4">✧</div>
    <div class="bouquet">
        <!-- tallos -->
        <div class="stem"></div>
        <div class="stem"></div>
        <div class="stem"></div>
        <div class="stem"></div>
        <div class="stem"></div>
        <div class="stem"></div>
        <!-- flores -->
        <div class="flower f1"></div>
        <div class="flower f2"></div>
        <div class="flower f3"></div>
        <div class="flower f4"></div>
        <div class="flower f5"></div>
        <div class="flower f6"></div>
        <!-- hojas -->
        <div class="leaf l1"></div>
        <div class="leaf l2"></div>
        <div class="leaf l3"></div>
        <div class="leaf l4"></div>
        <div class="paper"></div>
        <div class="ribbon"></div>
        <button class="open" onclick="openLetter()">
            💌 Abrir mi carta
        </button>
    </div>
    <!-- pétalos -->
    <div class="petal p1"></div>
    <div class="petal p2"></div>
    <div class="petal p3"></div>
    <div class="petal p4"></div>
    <div class="petal p5"></div>
</div>
<!-- CARTA -->
<div class="letterScreen" id="letterScreen">
    <div class="letter">
        <h2>Para Sayury 💛</h2>
        <p>
            Perdón por no entregarte esto
            personalmente, pero lo hago de manera
            digital porque en verdad quiero
            demostrarte que te amo.
        </p>
        <p>
            Tal vez unas flores digitales no sean
            lo mismo que tener un ramo entre tus manos,
            pero cada una de ellas lleva un poquito
            del cariño que siento por ti.
        </p>
        <div class="bigHeart">💛</div>
        <div class="signature">
            Con todo mi amor.
        </div>
        <button class="close" onclick="closeLetter()">
            Cerrar carta
        </button>
    </div>
</div>
<script>
function startGift(){
    document.getElementById("start").classList.add("hide");
}
function openLetter(){
    document.getElementById("letterScreen").classList.add("show");
}
function closeLetter(){
    document.getElementById("letterScreen").classList.remove("show");
}
</script>
</body>
</html>