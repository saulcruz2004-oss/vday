<!DOCTYPE html>  
<html lang="en">  
<head>  
<meta charset="UTF-8">  
<title>For Ana ❤️</title>  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
  
<style>  
  body {  
    margin: 0;  
    font-family: 'Arial', sans-serif;  
    background: linear-gradient(135deg, #ff5f9e, #ff9a9e);  
    overflow: hidden;  
    height: 100vh;  
    color: white;  
  }  
  
  .container {  
    position: relative;  
    z-index: 5;  
    height: 100vh;  
    display: flex;  
    justify-content: center;  
    align-items: center;  
    text-align: center;  
  }  
  
  .card {  
    background: rgba(255,255,255,0.15);  
    padding: 30px;  
    border-radius: 20px;  
    max-width: 360px;  
    box-shadow: 0 20px 40px rgba(0,0,0,0.3);  
    animation: fadeIn 1.2s ease;  
  }  
  
  h1 { margin-bottom: 10px; }  
  p { font-size: 18px; }  
  
  button {  
    padding: 12px 25px;  
    border-radius: 25px;  
    border: none;  
    font-size: 16px;  
    cursor: pointer;  
    margin: 10px;  
    transition: transform 0.2s;  
  }  
  
  button:hover { transform: scale(1.1); }  
  
  .yes {  
    background: #ff3366;  
    color: white;  
  }  
  
  .no {  
    background: white;  
    color: #ff3366;  
    position: absolute;  
  }  
  
  @keyframes fadeIn {  
    from { opacity: 0; transform: scale(0.9); }  
    to { opacity: 1; transform: scale(1); }  
  }  
  
  /* Hearts */  
  .heart {  
    position: absolute;  
    bottom: -20px;  
    font-size: 24px;  
    animation: floatUp 6s linear infinite;  
    opacity: 0.7;  
  }  
  
  @keyframes floatUp {  
    from { transform: translateY(0); opacity: 1; }  
    to { transform: translateY(-110vh); opacity: 0; }  
  }  
  
  /* Rat */  
  .rat {  
    position: fixed;  
    bottom: 10px;  
    left: 10px;  
    font-size: 60px;  
    animation: dance 0.5s infinite alternate;  
  }  
  
  @keyframes dance {  
    from { transform: rotate(-10deg) translateY(0); }  
    to { transform: rotate(10deg) translateY(-5px); }  
  }  
  
  /* Mad emoji */  
  .mad {  
    font-size: 40px;  
    animation: shake 0.4s;  
  }  
  
  @keyframes shake {  
    0% { transform: translateX(0); }  
    25% { transform: translateX(-5px); }  
    50% { transform: translateX(5px); }  
    75% { transform: translateX(-5px); }  
    100% { transform: translateX(0); }  
  }  
</style>  
</head>  
  
<body>  
  
<audio autoplay loop>  
  <source src="conga.mp3" type="audio/mpeg">  
</audio>  
  
<div class="container">  
  <div class="card" id="card">  
    <h1>Hi Ana ❤️</h1>  
    <p>I made this just for you.</p>  
    <button onclick="nextStep()">Continue</button>  
  </div>  
</div>  
  
<div class="rat">🐀🕺</div>  
  
<script>  
  const madMessages = [  
    "😤 hey stop that",  
    "🙄 you know you wanna say yes",  
    "😡 don’t lie to yourself",  
    "😭 why are you like this",  
    "😤 wow… rude",  
    "😠 stop playing with my feelings",  
    "🙃 be serious right now"  
  ];  
  
  function nextStep() {  
    document.getElementById("card").innerHTML = `  
      <h1>So Ana… 💭</h1>  
      <p>You genuinely make me really happy.</p>  
      <button onclick="finalQuestion()">Next</button>  
    `;  
  }  
  
  function finalQuestion() {  
    document.getElementById("card").innerHTML = `  
      <h1>Will you be my Valentine? 💘</h1>  
      <button class="yes" onclick="yesAnswer()">Yes 💖</button>  
      <button class="no" id="noBtn" onmouseover="moveNo()">No 🙈</button>  
      <p id="madText"></p>  
    `;  
  }  
  
  function yesAnswer() {  
    document.getElementById("card").innerHTML = `  
      <h1>YAYYYY 💕</h1>  
      <p>You just made my whole day 🥹</p>  
      <p>Happy Valentine’s Day Ana ❤️</p>  
    `;  
  }  
  
  function moveNo() {  
    const noBtn = document.getElementById("noBtn");  
    const x = Math.random() * (window.innerWidth - 100);  
    const y = Math.random() * (window.innerHeight - 100);  
    noBtn.style.left = x + "px";  
    noBtn.style.top = y + "px";  
  
    const msg = madMessages[Math.floor(Math.random() * madMessages.length)];  
    document.getElementById("madText").innerHTML =  
      `<span class="mad">😤</span><br>${msg}`;  
  }  
  
  // Hearts generator  
  setInterval(() => {  
    const heart = document.createElement("div");  
    heart.className = "heart";  
    heart.innerHTML = "❤️";  
    heart.style.left = Math.random() * 100 + "vw";  
    heart.style.animationDuration = (Math.random() * 3 + 4) + "s";  
    document.body.appendChild(heart);  
  
    setTimeout(() => heart.remove(), 7000);  
  }, 300);  
</script>  
  
</body>  
</html>  
