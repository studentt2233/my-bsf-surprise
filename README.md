# my-bsf-surprise
A cute surprise website for my best friend
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BSF Surprise 💖</title>

<style>
  body {
    font-family: Arial, sans-serif;
    background: #ffe6f0;
    margin: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .slide {
    display: none;
    flex-direction: column;
    align-items: center;
    padding: 20px;
  }

  .active {
    display: flex;
  }

  h1 {
    color: #ff2f92;
    font-size: 2.2em;
  }

  p {
    font-size: 1.4em;   /* NOTE BADA KAR DIYA */
    color: #333;
    max-width: 90%;
    line-height: 1.6;
  }

  button {
    padding: 12px 24px;
    font-size: 1.2em;
    margin: 10px;
    border: none;
    border-radius: 10px;
    background: #ff2f92;
    color: white;
    cursor: pointer;
  }

  #noBtn {
    position: absolute;
  }
</style>
</head>

<body>

<!-- Slide 1: Game -->
<div class="slide active" id="slide1">
  <h1>Mini Game 🎮</h1>
  <p>Click the button 5 times to unlock your surprise 💕</p>
  <button onclick="gameClick()">Click Me</button>
  <p id="score">0 / 5</p>
</div>

<!-- Slide 2: Big Message -->
<div class="slide" id="slide2">
  <h1>For My Bestie 💖</h1>
  <p>
    You are not just my best friend,  
    you are my comfort, my smile,  
    and my favorite person 🥰  
    <br><br>
    Life feels better with you in it ❤️
  </p>
  <button onclick="nextSlide()">Next</button>
</div>

<!-- Slide 3: Love -->
<div class="slide" id="slide3">
  <h1>One Last Question 💕</h1>
  <p>Do you love me? 💖</p>
  <button onclick="loveYes()">Yes ❤️</button>
  <button id="noBtn" onmouseover="moveNo()">No 😅</button>
</div>

<script>
let slide = 1;
let count = 0;

function gameClick() {
  count++;
  document.getElementById("score").innerText = count + " / 5";
  if (count === 5) {
    nextSlide();
  }
}

function nextSlide() {
  document.getElementById("slide" + slide).classList.remove("active");
  slide++;
  document.getElementById("slide" + slide).classList.add("active");
}

function moveNo() {
  const btn = document.getElementById("noBtn");
  btn.style.left = Math.random() * (window.innerWidth - 100) + "px";
  btn.style.top = Math.random() * (window.innerHeight - 50) + "px";
}

function loveYes() {
  document.getElementById("slide3").innerHTML = `
    <h1>Love you too ❤️🥹</h1>
    <p>
      I knew it 💕  
      You mean a lot to me  
      and this smile of yours  
      is my favorite 😘
    </p>
  `;
}
</script>

</body>
</html>
