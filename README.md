<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>BitMiner Login</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="login-container">
    <h1>BitMiner Cloud</h1>
    <input type="text" id="username" placeholder="Seu nome de usuário">
    <button onclick="login()">Entrar</button>
  </div>
  <script>
    function login() {
      const user = document.getElementById('username').value;
      if (user) {
        localStorage.setItem('username', user);
        window.location.href = "dashboard.html";
      } else {
        alert("Digite um nome de usuário!");
      }
    }
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Dashboard - BitMiner</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="dashboard">
    <h2>Bem-vindo, <span id="user"></span>!</h2>
    <p>Minerando BTC em nuvem...</p>
    <div class="miner-box">
      <h3>Saldo: <span id="balance">0.00000000</span> BTC</h3>
      <button onclick="withdraw()">Sacar</button>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  background: #111;
  color: #eee;
  text-align: center;
  margin-top: 100px;
}
.login-container, .dashboard {
  background: #222;
  padding: 20px;
  border-radius: 8px;
  width: 300px;
  margin: auto;
}
input {
  padding: 10px;
  width: 80%;
  margin-bottom: 10px;
}
button {
  padding: 10px 20px;
  background: #0f0;
  border: none;
  color: black;
  font-weight: bold;
  cursor: pointer;
}
.miner-box {
  background: #333;
  padding: 15px;
  margin-top: 20px;
  border-radius: 5px;
}
let balance = 0;

document.addEventListener("DOMContentLoaded", () => {
  const user = localStorage.getItem("username");
  document.getElementById("user").textContent = user;

  // Simula mineração a cada segundo
  setInterval(() => {
    balance += Math.random() * 0.00001;
    document.getElementById("balance").textContent = balance.toFixed(8);
  }, 1000);
});

function withdraw() {
  alert("Função de saque indisponível nesta demo.");
}
/bitminer-simples
├── index.html      → Página de login
├── dashboard.html  → Painel de mineração
├── style.css       → Estilo do site
├── script.js       → Simulação de mineração
