<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday My Love 🎂</title>

<style>
  body {
    margin: 0;
    height: 100vh;
    background: radial-gradient(circle, #ffe6f2, #ffd1e8);
    font-family: 'Segoe UI', sans-serif;
    overflow: hidden;
    text-align: center;
  }

  h1 {
    margin-top: 80px;
    font-size: 3em;
    color: #ff3d8b;
    text-shadow: 0 0 15px pink;
  }

  .heart, .sparkle {
    position: absolute;
    font-size: 24px;
    animation: float 6s infinite;
  }

  @keyframes float {
    0% { transform: translateY(0); opacity: 1; }
    100% { transform: translateY(-800px); opacity: 0; }
  }

  .popup {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    padding: 30px;
    border-radius: 25px;
    box-shadow: 0 0 30px pink;
    display: none;
    z-index: 10;
    max-width: 300px;
  }

  .popup p {
    font-size: 18px;
    color: #444;
  }

  button {
    margin: 10px;
    padding: 10px 18px;
    border: none;
    border-radius: 20px;
    font-size: 15px;
    cursor: pointer;
  }

  .love {
    background: #ff4fa3;
    color: white;
  }

  .nope {
    background: #ccc;
  }

  .celebrate {
    display: none;
    position: fixed;
    inset: 0;
    background: linear-gradient(45deg, #ffb3d9, #ffe6f2);
    z-index: 20;
    overflow: hidden;
  }

  .celebrate h2 {
    margin-top: 100px;
    font-size: 3em;
    color: #ff1f7a;
    text-shadow: 0 0 20px white;
  }

  .balloon {
    position: absolute;
    bottom: -100px;
    font-size: 40px;
    animation: rise 6s infinite;
  }

  @keyframes rise {
    0% { transform: translateY(0); }
    100% { transform: translateY(-900px); }
  }
</style>
</head>

<body>

<h1>🎉 HAPPY BIRTHDAY MY LOVE 🎉</h1>

<!-- Popup -->
<div class="popup" id="popup">
  <p>
    I just want to say…<br><br>
    I love you endlessly 💕<br>
    Do you love me too? 🥺
  </p>
  <button class="love" onclick="yesLove()">I love you more 💖</button>
  <button class="nope" onclick="noLove()">I don’t love you 😌</button>
</div>

<!-- Celebration -->
<div class="celebrate" id="celebrate">
  <h2>✨ I KNEW IT 😭💖 ✨<br>LOVE YOU FOREVER 🎂</h2>
</div>

<script>
  // show popup after load
  setTimeout(() => {
    document.getElementById("popup").style.display = "block";
  }, 1500);

  function noLove() {
    alert("Wrong answer 😌 Try again!");
    document.getElementById("popup").style.display = "block";
  }

  function yesLove() {
    document.getElementById("popup").style.display = "none";
    document.getElementById("celebrate").style.display = "block";
    createBalloons();
    createSparkles();
  }

  // floating hearts & sparkles
  function createSparkles() {
    setInterval(() => {
      const s = document.createElement("div");
      s.className = Math.random() > 0.5 ? "heart" : "sparkle";
      s.innerHTML = Math.random() > 0.5 ? "💖" : "✨";
      s.style.left = Math.random() * 100 + "vw";
      s.style.top = "100vh";
      s.style.animationDuration = (4 + Math.random() * 4) + "s";
      document.body.appendChild(s);
      setTimeout(() => s.remove(), 8000);
    }, 300);
  }

  // balloons
  function createBalloons() {
    setInterval(() => {
      const b = document.createElement("div");
      b.className = "balloon";
      b.innerHTML = "🎈";
      b.style.left = Math.random() * 100 + "vw";
      b.style.animationDuration = (4 + Math.random() * 4) + "s";
      document.getElementById("celebrate").appendChild(b);
      setTimeout(() => b.remove(), 8000);
    }, 400);
  }

  // initial hearts
  createSparkles();
</script>

</body>
</html>
