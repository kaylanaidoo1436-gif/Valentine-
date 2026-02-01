# Valentine-
Index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Thomas 💘 Will You Be My Valentine?</title>

<style>
  body {
    margin: 0;
    height: 100vh;
    background: radial-gradient(circle at top, #ffb6c1, #ff4d6d);
    font-family: 'Georgia', serif;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    color: white;
    text-align: center;
  }

  .card {
    background: rgba(255,255,255,0.18);
    backdrop-filter: blur(10px);
    padding: 30px;
    border-radius: 25px;
    width: 340px;
    box-shadow: 0 20px 40px rgba(0,0,0,0.3);
    z-index: 2;
  }

  h1 {
    margin-bottom: 10px;
  }

  p {
    font-size: 16px;
  }

  img {
    width: 100%;
    border-radius: 20px;
    margin: 15px 0;
  }

  button {
    padding: 10px 22px;
    margin: 10px;
    border: none;
    border-radius: 30px;
    font-size: 16px;
    cursor: pointer;
  }

  .yes {
    background: #ff4d6d;
    color: white;
  }

  .no {
    background: white;
    color: #ff4d6d;
    position: absolute;
  }

  .heart {
    position: absolute;
    bottom: -20px;
    font-size: 22px;
    animation: float 6s linear infinite;
    opacity: 0.85;
  }

  .name-heart {
    position: absolute;
    top: 20%;
    font-size: 32px;
    animation: glow 2s infinite alternate;
  }

  @keyframes float {
    0% { transform: translateY(0) scale(1); opacity: 1; }
    100% { transform: translateY(-100vh) scale(1.4); opacity: 0; }
  }

  @keyframes glow {
    from { text-shadow: 0 0 10px #fff; }
    to { text-shadow: 0 0 25px #ffccd5; }
  }
</style>
</head>

<body>

<audio autoplay loop>
  <source src="https://cdn.pixabay.com/download/audio/2023/03/02/audio_94d1f64f2c.mp3" type="audio/mpeg">
</audio>

<div class="card" id="card">
  <h1 id="question">Hey Thomas 💕</h1>
  <p id="text">I have something special to ask you…</p>
  <button class="yes" onclick="next()">Yes</button>
  <button class="no" id="noBtn" onmouseover="runAway()">No</button>
</div>

<script>
let step = 0;

function vibrate() {
  if (navigator.vibrate) {
    navigator.vibrate([120, 60, 120]);
  }
}

function next() {
  vibrate();
  step++;
  if (step === 1) {
    question.innerText = "Be honest 😌";
    text.innerText = "Do you know how much I love you?";
  } 
  else if (step === 2) {
    question.innerText = "Just one more 💘";
    text.innerText = "Do you see a future with me?";
  } 
  else if (step === 3) {
    question.innerText = "My Heart ❤️";
    text.innerText = "Will you be my Valentine?";
  } 
  else {
    showName();
    card.innerHTML = `
      <h1>YAYYYY 💖</h1>
      <img src="us.jpg">
      <p><em>I can’t wait to spend many more years with you.</em></p>
      <p>You mean everything to me 🥰</p>
    `;
  }
}

function runAway() {
  const btn = document.getElementById("noBtn");
  btn.style.left = Math.random() * 80 + "vw";
  btn.style.top = Math.random() * 80 + "vh";
}

function showName() {
  const letters = ["T","H","O","M","A","S"];
  letters.forEach((l, i) => {
    const heart = document.createElement("div");
    heart.className = "name-heart";
    heart.innerText = l + " 💖";
    heart.style.left = 15 + i * 12 + "%";
    document.body.appendChild(heart);
  });
}

setInterval(() => {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerText = "💗";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = Math.random() * 18 + 18 + "px";
  document.body.appendChild(heart);
  setTimeout(() => heart.remove(), 6000);
}, 350);
</script>

</body>
</html>
