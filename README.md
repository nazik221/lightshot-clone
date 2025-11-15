<!DOCTYPE html><html lang="uk">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Jumpscare</title>
    <style>
        body {
            margin: 0;
            background: #000;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            cursor: pointer;
        }
        #image {
            max-width: 80vw;
            max-height: 80vh;
            transition: opacity 0.2s ease;
        }
        #scare {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            object-fit: cover;
            display: none;
        }
    </style>
</head>
<body>
    <!-- Звичайна картинка -->
    <img id="image" src="preview.png" alt="preview" /><!-- Скример -->
<img id="scare" src="jumpscare.png" alt="scare" />

<!-- Гучний звук -->
<audio id="sound" src="scream.mp3"></audio>

<script>
    const img = document.getElementById("image");
    const scare = document.getElementById("scare");
    const sound = document.getElementById("sound");

    // Показ скримера через кілька секунд після кліку
    img.addEventListener("click", () => {
        img.style.opacity = 0;
        setTimeout(() => {
            scare.style.display = "block";
            sound.volume = 1.0;
            sound.play();
        }, 500);
    });
</script>

</body>
</html>
