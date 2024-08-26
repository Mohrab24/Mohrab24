<!DOCTYPE html>
<html lang="sv">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trygg El & Installation</title>
    <style>
        body {
            font-family: 'Lato', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }

        header {
            background-color: #2A3F54;
            color: #fff;
            padding: 20px 0;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 2.5em;
            font-weight: 700;
        }

        nav {
            background-color: #3498db;
            padding: 10px;
            text-align: center;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            margin: 0 15px;
            font-size: 1.1em;
        }

        nav a:hover {
            text-decoration: underline;
        }

        /* Bildkarusell */
        .carousel {
            position: relative;
            max-width: 100%;
            margin: 20px auto;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        .carousel-track {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }

        .carousel-slide {
            min-width: 100%;
            box-sizing: border-box;
        }

        .carousel img {
            width: 100%;
            vertical-align: middle;
        }

        .carousel-nav {
            position: absolute;
            top: 50%;
            width: 100%;
            display: flex;
            justify-content: space-between;
            transform: translateY(-50%);
        }

        .carousel-nav button {
            background-color: rgba(0, 0, 0, 0.5);
            border: none;
            color: #fff;
            padding: 10px;
            cursor: pointer;
            border-radius: 50%;
        }

        .carousel-nav button:hover {
            background-color: rgba(0, 0, 0, 0.7);
        }
    </style>
</head>
<body>

    <header>
        <h1>Trygg El & Installation</h1>
        <nav>
            <a href="#about">Om oss</a>
            <a href="#services">Tjänster</a>
            <a href="#contact">Kontakt</a>
        </nav>
    </header>

    <!-- Bildkarusell -->
    <div class="carousel">
        <div class="carousel-track">
            <div class="carousel-slide">
                <img src="https://images.unsplash.com/photo-1592850122355-85aad167dcaa?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwxOTMzODN8MHwxfGFsbHwxfHx8fHx8fHwxNjM1NjcyMjM0&ixlib=rb-1.2.1&q=80&w=1080" alt="Laddboxar">
                <h3>Laddboxar Installationer</h3>
                <p>Vi installerar laddboxar för både hem och företag.</p>
            </div>
            <div class="carousel-slide">
                <img src="https://images.unsplash.com/photo-1563438102747-1f521205a58e?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwxOTMzODN8MHwxfGFsbHwxfHx8fHx8fHwxNjM1NjcyMjM0&ixlib=rb-1.2.1&q=80&w=1080" alt="Akut Elservice">
                <h3>Akut Elservice</h3>
                <p>Snabb och pålitlig elservice vid akuta problem.</p>
            </div>
            <div class="carousel-slide">
                <img src="https://images.unsplash.com/photo-1581093458798-5d04c5a3b59f?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwxOTMzODN8MHwxfGFsbHwxfHx8fHx8fHwxNjM1NjcyMjM0&ixlib=rb-1.2.1&q=80&w=1080" alt="Security System">
                <h3>Security System</h3>
                <p>Installation av avancerade säkerhetssystem för att skydda ditt hem och företag.</p>
            </div>
            <!-- Fler slides kan läggas till här -->
        </div>
        <div class="carousel-nav">
            <button class="carousel-button prev">⟨</button>
            <button class="carousel-button next">⟩</button>
        </div>
    </div>

    <footer>
        <p>Trygg El & Installation - All rights reserved</p>
        <p>Carl Bondes Väg 16, Hässelby Vilastad, Stockholm</p>
    </footer>

    <script>
        const track = document.querySelector('.carousel-track');
        const slides = Array.from(track.children);
        const nextButton = document.querySelector('.next');
        const prevButton = document.querySelector('.prev');
        const slideWidth = slides[0].getBoundingClientRect().width;

        // Arrange slides next to each other
        slides.forEach((slide, index) => {
            slide.style.left = slideWidth * index + 'px';
        });

        // Move to the next slide
        const moveToSlide = (track, currentSlide, targetSlide) => {
            track.style.transform = 'translateX(-' + targetSlide.style.left + ')';
            currentSlide.classList.remove('current-slide');
            targetSlide.classList.add('current-slide');
        }

        // Click next button
        nextButton.addEventListener('click', e => {
            const currentSlide = track.querySelector('.current-slide');
            const nextSlide = currentSlide.nextElementSibling;
            if (nextSlide) {
                moveToSlide(track, currentSlide, nextSlide);
            }
        });

        // Click prev button
        prevButton.addEventListener('click', e => {
            const currentSlide = track.querySelector('.current-slide');
            const prevSlide = currentSlide.previousElementSibling;
            if (prevSlide) {
                moveToSlide(track, currentSlide, prevSlide);
            }
        });
    </script>
</body>
</html>
