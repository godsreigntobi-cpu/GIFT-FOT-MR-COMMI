# GIFT-FOT-MR-COMMI
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Happy Birthday Mr Commi 🎉</title>

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ff9966,#ff5e62);
    font-family:Arial;
    text-align:center;
    color:white;
    overflow:hidden;
}

.container{
    position:relative;
}

/* Cake */
.cake{
    width:200px;
    height:120px;
    background:#ffcc99;
    border-radius:10px;
    position:relative;
    margin:auto;
}

/* Cake cream */
.cake::before{
    content:"";
    position:absolute;
    top:-25px;
    width:200px;
    height:40px;
    background:#fff;
    border-radius:10px;
}

/* Candle */
.candle{
    width:12px;
    height:40px;
    background:red;
    position:absolute;
    top:-60px;
    left:94px;
}

/* Flame */
.flame{
    width:14px;
    height:20px;
    background:orange;
    border-radius:50%;
    position:absolute;
    top:-20px;
    left:-1px;
    animation:flicker 0.5s infinite alternate;
}

@keyframes flicker{
    from{transform:scale(1);}
    to{transform:scale(1.2);}
}

/* Cake cut animation */
.cut{
    animation:cutCake 1s forwards;
}

@keyframes cutCake{
    to{transform:translateX(-60px) rotate(-10deg);}
}

/* Confetti */
.confetti{
    position:absolute;
    width:8px;
    height:8px;
    animation:fall 4s linear infinite;
}

@keyframes fall{
    0%{transform:translateY(-10vh);}
    100%{transform:translateY(110vh);}
}

button{
    margin-top:20px;
    padding:12px 25px;
    border:none;
    border-radius:12px;
    background:#ffd700;
    font-size:16px;
    cursor:pointer;
}
</style>
</head>

<body>

<div class="container">

<h1>🎉 Happy Birthday Mr Commi 🎂</h1>
<h2>Mentor & Leader of PAI CONSULT</h2>

<div class="cake" id="cake">
    <div class="candle">
        <div class="flame" id="flame"></div>
    </div>
</div>

<button onclick="cutCake()">Cut Cake 🎂</button>

</div>

<script>

/* Cake cutting */
function cutCake(){
    document.getElementById("cake").classList.add("cut");
    document.getElementById("flame").style.display="none";

    confettiBurst();

    setTimeout(()=>{
        document.body.innerHTML=`
        <div style="display:flex;justify-content:center;align-items:center;height:100vh;text-align:center;color:white;">
            <div>
                <h1>🎉 Happy Birthday Mr Commi 🎂</h1>
                <p style="font-size:22px;">
                Wishing you success, wisdom and continued growth.<br><br>
                Thank you for building and leading <b>PAI CONSULT</b> with excellence 🙏
                </p>
            </div>
        </div>`;
    },2000);
}

/* Confetti */
function confettiBurst(){
    for(let i=0;i<80;i++){
        let c=document.createElement("div");
        c.className="confetti";
        c.style.left=Math.random()*100+"vw";
        c.style.backgroundColor=`hsl(${Math.random()*360},100%,50%)`;
        document.body.appendChild(c);
        setTimeout(()=>c.remove(),4000);
    }
}

</script>
</body>
</html>
