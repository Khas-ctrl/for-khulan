# for-khulan
Date Invite To My Love
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>For Khulan 💕</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ff758c, #ff7eb3);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Segoe UI', sans-serif;
  text-align: center;
  overflow: hidden;
  color: white;
}

.container {
  position: relative;
  z-index: 2;
}

h1 {
  font-size: 2.5rem;
  animation: fadeIn 2s ease-in-out;
}

.details {
  margin: 20px 0;
  font-size: 1.2rem;
}

button {
  padding: 15px 30px;
  font-size: 18px;
  border: none;
  border-radius: 30px;
  cursor: pointer;
  margin: 10px;
  transition: transform 0.2s ease;
}

#yesBtn {
  background: white;
  color: #ff4f81;
}

#yesBtn:hover {
  transform: scale(1.2);
}

#noBtn {
  background: #ff4f81;
  color: white;
  position: absolute;
}

@keyframes fadeIn {
  from {opacity: 0;}
  to {opacity: 1;}
}

/* Floating hearts */
.heart {
  position: absolute;
  bottom: -20px;
  font-size: 20px;
  animation: floatUp 6s linear infinite;
}

@keyframes floatUp {
  0% {
    transform: translateY(0) scale(1);
    opacity: 1;
  }
  100% {
    transform: translateY(-100vh) scale(1.5);
    opacity: 0;
  }
}

/* Confetti */
.confetti {
  position: fixed;
  width: 10px;
  height: 10px;
  background: white;
  top: 0;
  animation: fall 3s linear forwards;
}

@keyframes fall {
  to {
    transform: translateY(100vh) rotate(720deg);
  }
}
</style>
</head>

<body>

<div class="container">
  <h1>Khulan 💕</h1>
  <p>Will you go on a romantic date with me?</p>

  <div class="details">
    📅 3.18 Wednesday <br>
    📍 Hidden place in Kyoto
  </div>

  <button id="yesBtn" onclick="yesClicked()">Yes 😍</button>
  <button id="noBtn">No 😐</button>
</div>

<audio id="bgMusic" loop>
  <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mp3">
</audio>

<script>
const noBtn = document.getElementById("noBtn");
const music = document.getElementById("bgMusic");

noBtn.addEventListener("mouseover", () => {
  const x = Math.random() * (window.innerWidth - 100);
  const y = Math.random() * (window.innerHeight - 50);
  noBtn.style.left = x + "px";
  noBtn.style.top = y + "px";
});

// Floating hearts generator
function createHeart() {
  const heart = document.createElement("div");
  heart.classList.add("heart");
  heart.innerHTML = "💖";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.animationDuration = (Math.random() * 3 + 3) + "s";
  document.body.appendChild(heart);

  setTimeout(() => {
    heart.remove();
  }, 6000);
}

setInterval(createHeart, 500);

function yesClicked() {
  music.play();

  // Confetti explosion
  for (let i = 0; i < 100; i++) {
    const confetti = document.createElement("div");
    confetti.classList.add("confetti");
    confetti.style.left = Math.random() * 100 + "vw";
    confetti.style.background = 
      `hsl(${Math.random() * 360}, 100%, 70%)`;
    document.body.appendChild(confetti);

    setTimeout(() => {
      confetti.remove();
    }, 3000);
  }

  document.querySelector(".container").innerHTML = `
    <h1>She said YES 😌💕</h1>
    <p>3.18 Wednesday. Be ready.</p>
  `;
}
</script>

</body>
</html>
