# 💖 Will You Be My Valentine?

<div align="center">
  <h2 id="question">Will you be my Valentine? 💘</h2>

  <button id="yesBtn">YES</button>
  <button id="noBtn">NO</button>

  <div id="followUp" style="margin-top:20px;"></div>
</div>

<script>
  const noBtn = document.getElementById("noBtn");
  const yesBtn = document.getElementById("yesBtn");
  const question = document.getElementById("question");
  const followUp = document.getElementById("followUp");

  noBtn.addEventListener("mouseover", () => {
    const x = Math.random() * 300 - 150;
    const y = Math.random() * 200 - 100;
    noBtn.style.transform = `translate(${x}px, ${y}px)`;
  });

  yesBtn.addEventListener("click", () => {
    question.innerText = "YAY 💕 Do you want sushi?";
    followUp.innerHTML = `
      <button onclick="alert('Sushi date locked in 🍣💖')">YES 🍣</button>
      <button onclick="alert('Okay, we’ll pick something else 😌')">NO</button>
    `;
    yesBtn.style.display = "none";
    noBtn.style.display = "none";
  });
</script>
