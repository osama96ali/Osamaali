<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>لعبة أسامة علي</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="game-container">
    <h1>لعبة أسامة علي 🎮</h1>
    <p>هل تستطيع الفوز؟</p>
    <button onclick="winGame()">اضغط للفوز</button>
    <p id="result"></p>
  </div>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: 'Tahoma', sans-serif;
  background-color: #222;
  color: #fff;
  text-align: center;
  padding-top: 50px;
}

.game-container {
  background-color: #333;
  padding: 30px;
  border-radius: 15px;
  width: 300px;
  margin: auto;
  box-shadow: 0 0 10px #555;
}

button {
  padding: 10px 20px;
  font-size: 18px;
  background-color: #0d6efd;
  border: none;
  border-radius: 8px;
  color: white;
  cursor: pointer;
}

button:hover {
  background-color: #0a58ca;
}
function winGame() {
  document.getElementById("result").innerText = "🎉 مبروك يا أسامة علي، لقد فزت!";
}
