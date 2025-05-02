<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Login Auxílio</title>
  <style>
    body {
      background-color: black;
      color: white;
      font-family: 'Arial', sans-serif;
      text-align: center;
      padding: 20px;
    }

    .login-box, .container {
      width: 90%;
      max-width: 380px;
      margin: auto;
      padding: 15px;
      border-radius: 12px;
      border: 2px solid #0077ff;
      box-shadow: 0 0 10px #0077ff;
    }

    .login-box {
      background-color: #000c1f;
    }

    input[type="password"] {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      font-size: 16px;
      border-radius: 6px;
      border: 1px solid #0077ff;
      background: black;
      color: white;
    }

    .button {
      width: 100%;
      padding: 12px;
      background: linear-gradient(135deg, #0044aa, #002244);
      border: none;
      color: white;
      font-weight: bold;
      border-radius: 6px;
      cursor: pointer;
      margin-top: 10px;
      box-shadow: 0 0 10px #0077ff;
      transition: 0.3s ease-in-out;
    }

    .button:hover {
      background: linear-gradient(135deg, #0066cc, #003366);
      box-shadow: 0 0 15px #0099ff;
    }

    .hidden { display: none; }
  </style>
</head>
<body>

<div id="login" class="login-box">
  <h2>Seja bem vindo-key</h2>
  <p>Digite Seu Login:</p>
  <input type="password" id="password" placeholder="Password">
  <button class="button" onclick="checkPassword()">Login</button>
  <p id="error" style="color: red; display: none; margin-top: 10px;">Senha incorreta!</p>
</div>

<div id="mainContent" class="hidden"></div>

<script>
  function checkPassword() {
    const pwd = document.getElementById("password").value.trim();
    if (pwd === "3628363") {
      document.getElementById("login").style.display = "none";
      document.getElementById("mainContent").innerHTML = createMenu();
      document.getElementById("mainContent").classList.remove("hidden");
      attachScriptEvents();
    } else {
      document.getElementById("error").style.display = "block";
    }
  }

  function attachScriptEvents() {
    document.getElementById("fovRange").addEventListener("input", function () {
      document.getElementById("fovValue").textContent = "Fov " + this.value;
    });

    document.getElementById("injectButton").addEventListener("click", function () {
      let botao = this;
      botao.textContent = "INJETANDO...";
      botao.disabled = true;
      setTimeout(() => {
        botao.textContent = "INJETADO!";
        setTimeout(() => {
          botao.textContent = "INJETADO!";
          botao.disabled = false;
        }, 2000);
      }, 3000);
    });

    document.getElementById("aimlock-tab").addEventListener("click", function () {
      document.getElementById("aimlock").classList.add("active");
      document.getElementById("info").classList.remove("active");
      this.classList.add("active");
      document.getElementById("Olá-tab").classList.remove("active");
    });

    document.getElementById("Olá-tab").addEventListener("click", function () {
      document.getElementById("aimlock").classList.remove("active");
      document.getElementById("info").classList.add("active");
      this.classList.add("active");
      document.getElementById("aimlock-tab").classList.remove("active");
    });
  }

  function createMenu() {
    return `<!-- COLLE TON CODE HTML ICI, COMME DANS createMenu() -->` + `

    <style>
    .tabs {
        display: flex;
        justify-content: space-between;
        margin-bottom: 5px;
    }

    .tab {
        flex: 1;
        padding: 6px;
        cursor: pointer;
        background: #003366;
        color: white;
        border-radius: 10px;
        margin: 2px;
        text-align: center;
        font-weight: bold;
        transition: 0.3s;
        font-size: 14px;
    }

    .tab.active {
        background: linear-gradient(135deg, #004488, #0066cc);
        box-shadow: 0 0 6px #0077ff;
    }

    .content {
        display: none;
        padding-top: 8px;
    }

    .content.active {
        display: block;
    }

    .option {
        display: flex;
        align-items: center;
        margin: 5px 0;
        font-size: 14px;
        font-weight: bold;
    }

    .option input {
        margin-right: 8px;
        transform: scale(1.2);
        accent-color: #0077ff;
    }

    .slider-container {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin: 8px 0;
    }

    .slider {
        flex: 1;
        accent-color: #0077ff;
        height: 4px;
        border-radius: 8px;
        box-shadow: 0 0 6px rgba(0, 119, 255, 0.8);
    }

    .dropdown {
        width: 100%;
        padding: 8px;
        background: #000c1f;
        border: 1px solid #0077ff;
        color: white;
        border-radius: 6px;
        margin: 8px 0;
        font-weight: bold;
        font-size: 14px;
        text-align: center;
    }

    .radio-container {
        display: flex;
        justify-content: space-around;
        margin: 8px 0;
    }

    h4 {
        font-size: 14px;
        margin-bottom: 6px;
        color: #0077ff;
    }

    .radio-container label {
        font-size: 14px;
        font-weight: bold;
        color: white;
        padding: 5px 10px;
        border-radius: 6px;
        transition: 0.3s;
    }

    .radio-container input:checked + label {
        background: #0077ff;
        box-shadow: 0 0 8px #0077ff;
    }
    </style>

    <div class="container">
        <h3>AUXÍLIO SLEEPFZ IOS</h3>
        <div class="tabs">
            <div class="tab active" id="aimlock-tab">Opçoês de Auxílio</div>
            <div class="tab" id="Olá-tab">no recoil</div>
        </div>

        <div id="aimlock" class="content active">
            <div class="option">
                <input type="checkbox" id="auxilio">
                <label for="auxilio">no recoil</label>
            </div>
            <div class="option">
                <input type="checkbox" id="fov">
                <label for="fov">Headtrick</label>
            </div>
            <div class="slider-container">
                <input type="range" id="fovRange" class="slider" min="1" max="10" value="5">
                <span id="fovValue">Fov 5</span>
            </div>
            <select class="dropdown" id="auxilioType">
                <option>Auxilio 50%</option>
                <option>Auxilio 70%</option>
                <option>Auxilio sleepfz</option>
            </select>
            <h4>Tipo de Auxílio de mira:</h4>
            <div class="radio-container">
                <input type="radio" name="aimlockType" id="atirar" checked>
                <label for="atirar">Ao Atirar</label>
                <input type="radio" name="aimlockType" id="olhar">
                <label for="olhar">Ao Olhar boneco</label>
            </div>
            <button class="button" id="injectButton">INJETAR AO JOGO?</button>
        </div>

        <div id="info" class="content">
            <p><b>Modelo:</b> iPhone</p>
            <p><b>Developer:</b> @speed.nss</p>
        </div>
    </div>`;
  }
</script>

</body>
</html>
