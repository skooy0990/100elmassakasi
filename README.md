# 100elmassakasi
100 elmas şakasî
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Gem Reward • Fan Made</title>

<style>
*{box-sizing:border-box;margin:0;padding:0}

body{
    min-height:100vh;
    overflow:hidden;
    font-family:Arial,sans-serif;
    background:
      radial-gradient(circle at 50% 20%,#3156b8 0,#18285c 35%,#080d20 100%);
    color:white;
    display:flex;
    justify-content:center;
    align-items:center;
}

.bg{
    position:fixed;
    inset:0;
    overflow:hidden;
    pointer-events:none;
}

.star{
    position:absolute;
    width:4px;
    height:4px;
    background:white;
    border-radius:50%;
    opacity:.7;
    animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
    from{opacity:.15;transform:scale(.7)}
    to{opacity:1;transform:scale(1.4)}
}

.card{
    position:relative;
    width:min(92%,430px);
    padding:34px 25px;
    text-align:center;
    border-radius:28px;
    background:rgba(10,18,48,.78);
    border:1px solid rgba(255,255,255,.2);
    box-shadow:0 25px 80px rgba(0,0,0,.55);
    backdrop-filter:blur(15px);
}

.badge{
    display:inline-block;
    padding:7px 13px;
    border-radius:20px;
    background:rgba(255,255,255,.1);
    color:#b9caff;
    font-size:12px;
    font-weight:bold;
    letter-spacing:1px;
    margin-bottom:20px;
}

.gem{
    font-size:90px;
    filter:drop-shadow(0 0 25px #54bfff);
    animation:gemFloat 2.2s ease-in-out infinite;
}

@keyframes gemFloat{
    0%,100%{transform:translateY(0) rotate(-4deg)}
    50%{transform:translateY(-12px) rotate(4deg)}
}

h1{
    font-size:36px;
    margin:10px 0 5px;
}

.amount{
    font-size:23px;
    font-weight:bold;
    color:#7edcff;
    margin-bottom:18px;
}

.description{
    color:#c5d0ed;
    line-height:1.5;
    font-size:15px;
    margin-bottom:25px;
}

.reward{
    background:rgba(255,255,255,.07);
    border-radius:17px;
    padding:16px;
    margin-bottom:22px;
}

.reward strong{
    display:block;
    font-size:27px;
}

.reward span{
    color:#9eafd9;
    font-size:12px;
}

button{
    width:100%;
    padding:17px;
    border:0;
    border-radius:15px;
    background:linear-gradient(135deg,#ffe65b,#ffbd22);
    color:#241900;
    font-size:18px;
    font-weight:900;
    cursor:pointer;
    box-shadow:0 6px 0 #b78300,0 10px 25px rgba(255,196,30,.25);
    transition:.15s;
}

button:hover{
    transform:translateY(-2px);
}

button:active{
    transform:translateY(4px);
    box-shadow:0 2px 0 #b78300;
}

.disclaimer{
    margin-top:20px;
    font-size:11px;
    color:#8995b5;
}

/* Loading */
#loading{
    display:none;
    margin-top:22px;
}

.progress{
    height:9px;
    background:#111a38;
    border-radius:20px;
    overflow:hidden;
}

.bar{
    width:0;
    height:100%;
    background:#64d7ff;
    box-shadow:0 0 15px #64d7ff;
    transition:width .15s linear;
}

.loadingText{
    margin-top:9px;
    color:#aebce0;
    font-size:12px;
}

/* Jumpscare */
#scare{
    display:none;
    position:fixed;
    inset:0;
    z-index:99;
    background:#030303;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    text-align:center;
}

#scare.active{
    display:flex;
    animation:screenFlash .09s infinite alternate;
}

@keyframes screenFlash{
    from{background:#020202}
    to{background:#210000}
}

.monster{
    position:relative;
    width:245px;
    height:290px;
    border-radius:48% 48% 38% 38%;
    background:
      radial-gradient(circle at 50% 35%,#333,#111 65%);
    box-shadow:0 0 70px rgba(255,0,0,.35);
    animation:monsterShake .07s infinite;
}

@keyframes monsterShake{
    0%{transform:translate(-6px) rotate(-2deg)}
    50%{transform:translate(6px) rotate(2deg)}
    100%{transform:translate(-3px)}
}

.eye{
    position:absolute;
    top:75px;
    width:48px;
    height:68px;
    background:#eee;
    border-radius:50%;
    box-shadow:0 0 25px white;
}

.eye:after{
    content:"";
    position:absolute;
    width:13px;
    height:38px;
    left:18px;
    top:15px;
    border-radius:50%;
    background:#090909;
}

.left{left:43px}
.right{right:43px}

.mouth{
    position:absolute;
    width:155px;
    height:70px;
    left:45px;
    bottom:32px;
    background:#050505;
    border-radius:50%;
    border:3px solid #333;
    overflow:hidden;
}

.teeth{
    height:22px;
    margin:4px 10px;
    background:repeating-linear-gradient(
      90deg,
      white 0 12px,
      transparent 12px 22px
    );
}

.scareTitle{
    margin-top:25px;
    font-size:30px;
    font-weight:900;
}

.scareSub{
    margin-top:8px;
    color:#aaa;
    font-size:13px;
}

.close{
    margin-top:20px;
    width:auto;
    padding:11px 20px;
    background:#252525;
    color:white;
    box-shadow:none;
    font-size:14px;
}

@media(max-width:420px){
    h1{font-size:30px}
    .gem{font-size:75px}
    .monster{
        width:205px;
        height:245px;
    }
    .mouth{
        width:130px;
        left:38px;
    }
}
</style>
</head>

<body>

<div class="bg" id="stars"></div>

<main class="card">

    <div class="badge">★ FAN-MADE REWARD ★</div>

    <div class="gem">💎</div>

    <h1>ÖDÜL KAZANDIN!</h1>

    <div class="amount">+100 ELMAS</div>

    <p class="description">
        Özel ödülün hazır. Aşağıdaki butona basarak
        ödül ekranını açabilirsin.
    </p>

    <div class="reward">
        <strong>💎 100</strong>
        <span>Özel Elmas Ödülü</span>
    </div>

    <button id="claim" onclick="claimReward()">
        💎 ÖDÜLÜMÜ AL
    </button>

    <div id="loading">
        <div class="progress">
            <div class="bar" id="bar"></div>
        </div>
        <div class="loadingText" id="loadingText">
            Ödül hazırlanıyor... 0%
        </div>
    </div>

    <div class="disclaimer">
        ⚠️ FAN YAPIMI ŞAKA • GERÇEK ELMAS VERMEZ
    </div>

</main>

<div id="scare">

    <div class="monster">
        <div class="eye left"></div>
        <div class="eye right"></div>

        <div class="mouth">
            <div class="teeth"></div>
        </div>
    </div>

    <div class="scareTitle">
        😈 YAKALANDIN!
    </div>

    <div class="scareSub">
        100 elmas yerine korku paketi geldi 💀
        <br>
        Şaka! Gerçek elmas yok.
    </div>

    <button class="close" onclick="closeScare()">
        Tamam 😭
    </button>

</div>

<script>

/* Arka plan yıldızları */
const stars = document.getElementById("stars");

for(let i=0;i<45;i++){
    const star=document.createElement("div");
    star.className="star";

    star.style.left=Math.random()*100+"%";
    star.style.top=Math.random()*100+"%";
    star.style.animationDelay=Math.random()*2+"s";

    stars.appendChild(star);
}

/* Ödül animasyonu */
function claimReward(){

    const button=document.getElementById("claim");
    const loading=document.getElementById("loading");
    const bar=document.getElementById("bar");
    const text=document.getElementById("loadingText");

    button.disabled=true;
    button.style.opacity=".5";
    button.textContent="⏳ HAZIRLANIYOR...";

    loading.style.display="block";

    let progress=0;

    const timer=setInterval(()=>{

        progress+=2;

        bar.style.width=progress+"%";
        text.textContent=
            "Ödül hazırlanıyor... "+progress+"%";

        if(progress>=100){

            clearInterval(timer);

            setTimeout(()=>{
                document
                  .getElementById("scare")
                  .classList.add("active");

                playSound();
            },300);
        }

    },35);
}

/* Basit korku sesi */
function playSound(){

    const AudioContext =
        window.AudioContext ||
        window.webkitAudioContext;

    if(!AudioContext) return;

    const ctx=new AudioContext();

    const osc=ctx.createOscillator();
    const gain=ctx.createGain();

    osc.type="sawtooth";

    osc.frequency.setValueAtTime(
        260,
        ctx.currentTime
    );

    osc.frequency.exponentialRampToValueAtTime(
        45,
        ctx.currentTime+.9
    );

    gain.gain.setValueAtTime(
        .001,
        ctx.currentTime
    );

    gain.gain.exponentialRampToValueAtTime(
        .22,
        ctx.currentTime+.04
    );

    gain.gain.exponentialRampToValueAtTime(
        .001,
        ctx.currentTime+1
    );

    osc.connect(gain);
    gain.connect(ctx.destination);

    osc.start();
    osc.stop(ctx.currentTime+1);
}

function closeScare(){

    document
      .getElementById("scare")
      .classList.remove("active");

    const button=document.getElementById("claim");

    button.disabled=false;
    button.style.opacity="1";
    button.textContent="💎 ÖDÜLÜMÜ AL";

    document.getElementById("loading").style.display="none";
    document.getElementById("bar").style.width="0%";
}

</script>

</body>
</html>
