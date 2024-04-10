<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mensagem do Celso</title>
<style>
  body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    background-color: #b81414;
    color: #ffffff;
  }
  .container {
    text-align: center;
    margin-top: 20%;
  }
  .button {
    background-color: #ffffff;
    color: #b81414;
    border: none;
    padding: 10px 20px;
    text-align: center;
    display: inline-block;
    font-size: 16px;
    cursor: pointer;
    border-radius: 20px;
    margin: 10px;
  }
  #noButton {
    position: relative;
  }
  #footerMessage {
    position: fixed;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 14px;
  }
</style>
</head>
<body>
<div class="container" id="container">
  <p id="message">Mensagem do Celso recebida</p>
  <button class="button" id="openButton" onclick="showQuestion()">Abrir</button>
</div>

<script>
  function showQuestion() {
    document.getElementById("container").innerHTML = `
      <p>Vem dormir comigo hoje?</p>
      <button class="button" id="yesButton" onclick="showImage()">Sim</button>
      <button class="button" id="noButton" onclick="moveNoButton()">Não</button>
    `;
    document.getElementById("footerMessage").style.display = "block";
  }

  function moveNoButton() {
    var button = document.getElementById("noButton");
    var containerWidth = document.getElementById("container").offsetWidth;
    var buttonWidth = button.offsetWidth;
    var randomPosition = Math.floor(Math.random() * (containerWidth - buttonWidth));
    button.style.left = randomPosition + "px";
    document.getElementById("footerMessage").innerText = "Você precisa tomar uma decisão...";
  }

  function showImage() {
    document.body.innerHTML = `
      <img src="https://i.imgur.com/jEMNbUh.jpg" alt="Imagem" style="max-width: 100%; height: auto;">
      <div class="container">
        <a href="https://www.youtube.com/watch?v=1YKmCV0TcfQ&ab_channel=Gledson" class="button">Clique aqui, vai...</a>
      </div>
    `;
  }
</script>

<div id="footerMessage" style="display: none;"></div>
</body>
</html>
