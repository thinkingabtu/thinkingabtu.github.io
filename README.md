<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>💖</title>
  <style>
    /* Hide any stray text outside our content */
    body {
      margin: 0;
      padding: 0;
      background: #ffd6e8;
      font-family: "Comic Sans MS", cursive, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      overflow: hidden;
    }

    /* Only show content inside #mainContent */
    #mainContent {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    h2 {
      text-align: center;
    }

    #loveText {
      font-size: 64px;
      font-weight: bold;
      color: #ff3b7d;
      text-shadow: 0 4px 10px rgba(255, 59, 125, 0.4);
      display: none;
      margin-top: 20px;
      text-align: center;
    }

    button {
      font-size: 18px;
      padding: 10px 20px;
      margin: 10px;
      cursor: pointer;
      border-radius: 10px;
      border: none;
    }

    #gallery {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 12px;
      margin-bottom: 30px;
    }

    #gallery img {
      width: 140px;
      height: 140px;
      object-fit: cover;
      border-radius: 14px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    }

    #noBtn {
      position: relative;
    }

    .heart {
      position: absolute;
      color: #ff4d88;
      font-size: 24px;
      animation: floatUp 4s linear infinite;
      opacity: 0.8;
    }

    @keyframes floatUp {
      from {
        transform: translateY(100vh) scale(0.8);
        opacity: 1;
      }
      to {
        transform: translateY(-10vh) scale(1.4);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

<div id="mainContent">
  <!-- Image Gallery -->
  <div id="gallery">
    <img src="https://github.com/user-attachments/assets/ad76f765-c1d6-474c-abc5-ddea43e61bda" alt="bae1">
    <img src="https://github.com/user-attachments/assets/263b45e2-0a42-4ca8-ab2e-e90165447d5c" alt="bae2">
    <img src="https://github.com/user-attachments/assets/9d8d9763-a9e7-4f9c-b4c6-bd5657af4360" alt="bae3">
    <img src="https://github.com/user-attachments/assets/fb2d1c39-a730-4a3c-9a3f-4297a205f6ae" alt="bae4">
    <img src="https://github.com/user-attachments/assets/4af8c225-8178-4b00-84b0-34f6fc092ded" alt="bae5">
    <img src="https://github.com/user-attachments/assets/9bb62026-2203-4d76-9ebb-2f584dd2eba9" alt="bae6">
    <img src="https://github.com/user-attachments/assets/19ce2d80-241a-4b3f-bc65-568bef00612e" alt="bae7">
    <img src="https://github.com/user-attachments/assets/c6d9c528-b532-47df-94de-e45702f5cad0" alt="bae8">
  </div>

  <!-- Main Question -->
  <h2 id="question">Will you be my Valentine? 💕</h2>

  <div id="buttons">
    <button id="yesBtn">YES</button>
    <button id="noBtn">NO</button>
  </div>

  <div id="loveText">I LOVE YOU 💖💖💖</div>
</div>

<script>
  const noBtn = document.getElementById("noBtn");
  const yesBtn = document.getElementById("yesBtn");
  const question = document.getElementById("question");
  const buttons = document.getElementById("buttons");
  const loveText = document.getElementById("loveText");

  // NO button moves away
  noBtn.addEventListener("mouseover", () => {
    const x = Math.random() * 300 - 150;
    const y = Math.random() * 200 - 100;
    noBtn.style.transform = `translate(${x}px, ${y}px)`;
  });

  // YES button sequence
  yesBtn.addEventListener("click", () => {
    buttons.style.display = "none";
    question.innerText = "💖💖💖 You are my Valentine 💖💖💖";

    // After short delay, show I LOVE YOU with hearts
    setTimeout(() => {
      loveText.style.display = "block";
      spawnHearts();
    }, 1500);
  });

  // Floating hearts animation
  function spawnHearts() {
    setInterval(() => {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerText = "💖";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (3 + Math.random() * 2) + "s";
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 5000);
    }, 300);
  }
</script>

</body>
</html>
