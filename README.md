# Voo

<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Для тебя ❤️</title>

<style>
    * {
        box-sizing: border-box;
    }

    body {
        margin: 0;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        font-family: Arial, sans-serif;
        overflow: hidden;
    }

    .card {
        width: 90%;
        max-width: 500px;
        padding: 45px 25px;
        text-align: center;
        background: rgba(255,255,255,0.9);
        border-radius: 25px;
        box-shadow: 0 15px 40px rgba(0,0,0,0.15);
    }

    h1 {
        font-size: 30px;
        color: #222;
        margin-bottom: 40px;
    }

    button {
        border: none;
        border-radius: 14px;
        padding: 15px 35px;
        font-size: 20px;
        font-weight: bold;
        cursor: pointer;
    }

    #yes {
        background: #4caf50;
        color: white;
    }

    #no {
        background: #ff4d4d;
        color: white;
        position: fixed;
        transition: left 0.15s, top 0.15s;
    }

    #message {
        display: none;
        font-size: 28px;
        font-weight: bold;
        color: #ff4d6d;
    }
</style>
</head>

<body>

<div class="card">
    <h1>жаланаш фотонды жыбересынба? ❤️</h1>

    <button id="yes" onclick="yesClick()">Да 😍</button>
    <button id="no">Нет 😏</button>

    <div id="message">
        Рахмет жду❤️😂
    </div>
</div>

<script>
const noButton = document.getElementById("no");

function moveButton() {
    const padding = 15;

    const maxX = window.innerWidth - noButton.offsetWidth - padding;
    const maxY = window.innerHeight - noButton.offsetHeight - padding;

    const x = Math.max(padding, Math.random() * maxX);
    const y = Math.max(padding, Math.random() * maxY);

    noButton.style.left = x + "px";
    noButton.style.top = y + "px";
}

// Компьютер
noButton.addEventListener("mouseenter", moveButton);

// Телефон
noButton.addEventListener("touchstart", function(e) {
    e.preventDefault();
    moveButton();
});

noButton.addEventListener("click", function(e) {
    e.preventDefault();
    moveButton();
});

function yesClick() {
    document.querySelector("h1").style.display = "none";
    document.getElementById("yes").style.display = "none";
    noButton.style.display = "none";
    document.getElementById("message").style.display = "block";
}
</script>

</body>
</html>
