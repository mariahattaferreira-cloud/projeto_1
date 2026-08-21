function botaoClicado() {
  console.log("O botão foi clicado!");

  const texto = botao.querySelector("span");

  if (curtiu === false) {
    let quantidadeAtual = Number(texto.textContent);
    quantidadeAtual = quantidadeAtual + 1;

    texto.textContent = quantidadeAtual;
    curtiu = true;

    console.log("Você curtiu este conteúdo!");
  } else {
    let quantidadeAtual = Number(texto.textContent);
    quantidadeAtual = quantidadeAtual - 1;

    texto.textContent = quantidadeAtual;
    curtiu = false;

    console.log("Você removeu sua curtida.")

1. HTML
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Copa do Mundo ⚽</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <header>
    <h1>🏆 Copa do Mundo</h1>
    <p>O maior espetáculo do futebol mundial!</p>
  </header>

  <main>

    <section class="jogo">
      <h2>⚽ Jogo de Hoje</h2>

      <div class="times">

        <div class="time">
          <div class="bandeira">🇧🇷</div>
          <h3>Brasil</h3>
          <span id="golsBrasil">0</span>
        </div>

        <div class="versus">
          <strong>VS</strong>
        </div>

        <div class="time">
          <div class="bandeira">🇦🇷</div>
          <h3>Argentina</h3>
          <span id="golsArgentina">0</span>
        </div>

      </div>

      <div class="botoes">
        <button onclick="golBrasil()">⚽ Gol do Brasil</button>
        <button onclick="golArgentina()">⚽ Gol da Argentina</button>
      </div>

    </section>

    <section class="torcida">
      <h2>🇧🇷 Torcida</h2>

      <p>
        Clique no botão para demonstrar seu apoio ao time!
      </p>

      <button id="botaoTorcida" onclick="botaoClicado()">
        ❤️ <span>0</span> torcedores
      </button>

      <p id="mensagem"></p>
    </section>

  </main>

  <footer>
    <p>⚽ Viva o futebol! 🏆</p>
  </footer>

  <script src="script.js"></script>

</body>
</html>

2. CSS
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg, #009c3b, #ffdf00);
  min-height: 100vh;
  color: #ffffff;
}

header {
  text-align: center;
  padding: 40px 20px;
  background: #006b2d;
}

header h1 {
  font-size: 45px;
  margin-bottom: 10px;
}

header p {
  font-size: 20px;
}

main {
  width: 90%;
  max-width: 900px;
  margin: 40px auto;
}

section {
  background: rgba(0, 70, 30, 0.9);
  padding: 30px;
  border-radius: 20px;
  margin-bottom: 30px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

h2 {
  margin-bottom: 30px;
  font-size: 30px;
}

.times {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 50px;
}

.time {
  min-width: 150px;
}

.bandeira {
  font-size: 70px;
}

.time h3 {
  font-size: 25px;
  margin: 10px;
}

.time span {
  font-size: 55px;
  font-weight: bold;
  color: #ffdf00;
}

.versus {
  font-size: 25px;
  color: #ffffff;
}

.botoes {
  margin-top: 35px;
  display: flex;
  justify-content: center;
  gap: 15px;
  flex-wrap: wrap;
}

button {
  background: #ffdf00;
  color: #006b2d;
  border: none;
  padding: 15px 25px;
  border-radius: 10px;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  transform: scale(1.05);
  background: #ffffff;
}

#botaoTorcida {
  background: #e91e63;
  color: white;
}

#mensagem {
  margin-top: 20px;
  font-size: 18px;
  font-weight: bold;
}

footer {
  text-align: center;
  padding: 25px;
  background: #006b2d;
  font-size: 18px;
}

3. JavaScript
let golsDoBrasil = 0;
let golsDaArgentina = 0;

let curtiu = false;

function golBrasil() {
  golsDoBrasil++;

  document.getElementById("golsBrasil").textContent = golsDoBrasil;

  console.log("Brasil marcou um gol!");

  verificarResultado();
}

function golArgentina() {
  golsDaArgentina++;

  document.getElementById("golsArgentina").textContent = golsDaArgentina;

  console.log("Argentina marcou um gol!");

  verificarResultado();
}

function verificarResultado() {
  let mensagem = document.getElementById("mensagem");

  if (golsDoBrasil > golsDaArgentina) {
    mensagem.textContent = "🇧🇷 Brasil está vencendo a partida!";
  } 
  else if (golsDaArgentina > golsDoBrasil) {
    mensagem.textContent = "🇦🇷 Argentina está vencendo a partida!";
  } 
  else {
    mensagem.textContent = "🤝 A partida está empatada!";
  }
}

function botaoClicado() {
  let botao = document.getEleme