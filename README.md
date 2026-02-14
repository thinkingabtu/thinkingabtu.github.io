<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>💖</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: #ffd6e8; /* aesthetic light pink */
      font-family: "Comic Sans MS", cursive, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
    }

    h2 {
      margin-bottom: 20px;
    }

    button {
      font-size: 18px;
      padding: 10px 20px;
      margin: 10px;
      cursor: pointer;
      border-radius: 8px;
      border: none;
    }

    #gallery {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 12px;
      margin-bottom: 30px;
    }

    #gallery img {
      width: 150px;
      height: 150px;
      object-fit: cover;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    }

    #noBtn {
      position: relative;
    }
  </style>
</head>
<body>

  <!-- Image Gallery -->
  <div id="gallery">
    <img src="bae1.jpg">
    <img src="bae2.jpg">
    <img src="bae3.jpg">
    <img src="bae4.jpg">
    <img src="bae5.jpg">
    <img src="bae6.jpg">
    <img src="bae7.jpg">
    <img src="bae8.png">
  </div>

  <!-- Main Question -->
  <h2 id="question">Will you be my Valentine? 💕</h2>

  <div id="buttons">
    <button id="yesBtn">YES</button>
    <button id="noBtn">NO</button>
  </div>

  <div id="followUp"></div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const question = document.getElementById("question");
    const followUp = document.getElementById("followUp");
    const buttons = document.getElementById("buttons");

    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * 300 - 150;
      const y = Math.random() * 200 - 100;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    });

    yesBtn.addEventListener("click", () => {
      question.innerText = "Do you want sushi? 🍣💖";
      buttons.style.display = "none";
      followUp.innerHTML = `
        <button onclick="alert('Sushi date confirmed 🍣💘')">YES 🍣</button>
        <button onclick="alert('Okay, we’ll pick something else 😌')">NO</button>
      `;
    });
  </script>

</body>
</html>
