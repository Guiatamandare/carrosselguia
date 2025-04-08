<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carrossel Responsivo</title>
    <style>
       .carrossel-container {
            position: relative;
            width: 100%;
            max-width: 390px;
            height: 240px;
            overflow: hidden;
            border-radius: 10px;
        }
        .carrossel {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }
        .slide {
            min-width: 100%;
        }
        .seta {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            font-size: 20px;
            z-index: 10;
        }
        .seta-esquerda {
            left: 10px;
        }
        .seta-direita {
            right: 10px;
        }
    </style>
</head>
<body>
    <div class="carrossel-container">
        <button class="seta seta-esquerda" onclick="mudarSlide(-1)">&#10094;</button>
        <div class="carrossel" id="carrossel">
            <img class="slide" src="https://imgur.com/9JPO42t.png" alt="Slide 1">
            <img class="slide" src="https://imgur.com/m3wKNOe.png" alt="Slide 2">
            <img class="slide" src="https://imgur.com/m3N454E.png" alt="Slide 3">
            <img class="slide" src="https://imgur.com/ZskvUCv.png" alt="Slide 4">
            <img class="slide" src="https://imgur.com/sHAHyG9.png" alt="Slide 5">
            <img class="slide" src="https://imgur.com/ppSWx0W.png" alt="Slide 6">
            <img class="slide" src="https://imgur.com/1IzW7vO.png" alt="Slide 7">
            <img class="slide" src="https://imgur.com/MR5A743.png" alt="Slide 8">
            <img class="slide" src="https://imgur.com/P7fWRye.png" alt="Slide 9">
            <img class="slide" src="https://imgur.com/s73akuG.png" alt="Slide 10">
        </div>
        <button class="seta seta-direita" onclick="mudarSlide(1)">&#10095;</button>
    </div>

    <script>
        let indice = 0;
        function mudarSlide(direcao) {
            const carrossel = document.getElementById('carrossel');
            const totalSlides = document.querySelectorAll('.slide').length;
            indice = (indice + direcao + totalSlides) % totalSlides;
            carrossel.style.transform = translateX(${-indice * 100}%);
        }
    </script>
</body>
</html>
