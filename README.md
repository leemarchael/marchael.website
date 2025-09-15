<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My dearest Patricia ❤️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
    min-height: 100vh;
    overflow-y: auto; /* ginawa kong auto para pwede mag scroll */
    color: #4a2c2c;

        }

        /* Floating hearts animation */
        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .heart {
            position: absolute;
            font-size: 20px;
            opacity: 0.6;
            animation: float 8s linear infinite;
            color: #ff6b6b;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.6;
            }
            90% {
                opacity: 0.6;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }

        /* Intro screen */
        #intro {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #ff6b6b, #ff9a9e, #fad0c4);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 100;
            transition: transform 1.2s cubic-bezier(0.4, 0, 0.2, 1), opacity 1.2s ease;
        }

        .intro-content {
            text-align: center;
            padding: 2rem;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            transform: scale(0.9);
            animation: scaleIn 1.5s ease-out forwards;
        }

        @keyframes scaleIn {
            to {
                transform: scale(1);
            }
        }

        #intro h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #ff6b6b;
            font-weight: 300;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        #intro p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #6d4c4c;
        }

        #enterBtn {
            padding: 1rem 2.5rem;
            font-size: 1.3rem;
            border: none;
            border-radius: 50px;
            background: linear-gradient(45deg, #ff6b6b, #ff9a9e);
            color: white;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 20px rgba(255, 107, 107, 0.3);
        }

        #enterBtn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 25px rgba(255, 107, 107, 0.4);
        }

        /* Main content */
        #mainContent {
            display: none;
            max-width: 800px;
            margin: 2rem auto;
            padding: 3rem;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.1);
            position: relative;
            z-index: 2;
        }

        .message-container {
            background: linear-gradient(135deg, #fffaf0, #fff5ee);
            padding: 2.5rem;
            border-radius: 20px;
            border: 2px solid #ffe4e6;
            margin-bottom: 2rem;
            position: relative;
            overflow: hidden;
        }

        .message-container::before {
            content: '"';
            position: absolute;
            top: -10px;
            left: 20px;
            font-size: 8rem;
            color: #ffe4e6;
            font-family: serif;
            z-index: 0;
        }

        #message {
            font-size: 1.4rem;
            line-height: 1.8;
            color: #5a3e3e;
            position: relative;
            z-index: 1;
            font-weight: 400;
            text-align: center;
        }

        /* Slideshow */
        .slideshow-container {
            position: relative;
            width: 100%;
            height: 400px;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
        }

        .slide {
            position: absolute;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity 1.2s ease-in-out;
            border-radius: 20px;
            background-size: cover;
            background-position: center;
        }

        .slide.active {
            opacity: 1;
        }

        .slide-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.7));
            color: white;
            padding: 2rem;
            text-align: center;
            font-size: 1.1rem;
            border-bottom-left-radius: 20px;
            border-bottom-right-radius: 20px;
        }

        /* Responsive design */
        @media (max-width: 768px) {
            #intro h1 {
                font-size: 2rem;
            }
            
            #intro p {
                font-size: 1rem;
            }
            
            #message {
                font-size: 1.1rem;
            }
            
            .slideshow-container {
                height: 300px;
            }
            
            #mainContent {
                margin: 1rem;
                padding: 2rem;
            }
        }

        /* Additional animations */
        .fade-in {
            animation: fadeIn 2s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .heart-beat {
            animation: heartBeat 1.2s ease-in-out infinite;
        }

        @keyframes heartBeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
    </style>
</head>
<body>
    <div class="hearts" id="hearts"></div>

    <div id="intro">
        <div class="intro-content">
            <h1>❤️ My dearest Patricia ❤️</h1>
            <p>Tap here, mahal 💞</p>
            <button id="enterBtn" class="heart-beat">Enter</button>
        </div>
    </div>

    <div id="mainContent">
        <div class="message-container fade-in">
            <p id="message">
                Hi mahal, I just want to say sorry. Sorry if sometimes I have not been consistent and if I have not always shown the effort that you truly deserve. But please remember, my love for you has never changed from the beginning until now. I still love you so much. Even if at times it feels like I fall short, it does not mean my love for you is less. I am doing my best to make it up to you and to show you again how much you mean to me, because you will always be the most important person in my life.
            </p>
        </div>
        
        <div class="slideshow-container">
            <div class="slide active" style="background-image: url('patricia1.png')">
                <div class="slide-caption">Our First Memory Together</div>
            </div>
            <div class="slide" style="background-image: url('https://github.com/leemarchael/marchael.website/blob/3c8ed0a49f8b792700def9a29efede068526c3f0/IMG_20240123_181023.jpg')">
            </div>
            <div class="slide" style="background-image: url('https://github.com/leemarchael/marchael.website/blob/8829b2a23243d06959bec7fe370d70a17b127c95/patricia1.jpeg')">
                <div class="slide-caption">Happy Times</div>
            </div>
            <div class="slide" style="background-image: url('')">
                <div class="slide-caption">Together Forever</div>
            </div>
            <div class="slide" style="background-image: url('')">
                <div class="slide-caption">My Favorite Smile</div>
            </div>
        </div>
    </div>

    <script>
        // Create floating hearts
        function createHearts() {
            const heartsContainer = document.getElementById('hearts');
            const hearts = ['❤️', '💕', '💖', '💗', '💓', '💘'];
            
            for (let i = 0; i < 30; i++) {
                const heart = document.createElement('div');
                heart.className = 'heart';
                heart.textContent = hearts[Math.floor(Math.random() * hearts.length)];
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDelay = Math.random() * 8 + 's';
                heart.style.fontSize = (Math.random() * 15 + 15) + 'px';
                heartsContainer.appendChild(heart);
            }
        }

        // Slideshow functionality
        function initSlideshow() {
            const slides = document.querySelectorAll('.slide');
            let currentSlide = 0;
            
            function showSlide(index) {
                slides.forEach(slide => slide.classList.remove('active'));
                slides[index].classList.add('active');
            }
            
            function nextSlide() {
                currentSlide = (currentSlide + 1) % slides.length;
                showSlide(currentSlide);
            }
            
            // Change slide every 5 seconds
            setInterval(nextSlide, 5000);
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', function() {
            createHearts();
            
            const enterBtn = document.getElementById('enterBtn');
            const intro = document.getElementById('intro');
            const mainContent = document.getElementById('mainContent');
            
            enterBtn.addEventListener('click', function() {
                intro.style.transform = 'translateY(-100vh)';
                intro.style.opacity = '0';
                
                setTimeout(() => {
                    intro.style.display = 'none';
                    mainContent.style.display = 'block';
                    initSlideshow();
                    
                    // Add typewriter effect to message
                    const message = document.getElementById('message');
                    const text = message.textContent;
                    message.textContent = '';
                    
                    let i = 0;
                    function typeWriter() {
                        if (i < text.length) {
                            message.textContent += text.charAt(i);
                            i++;
                            setTimeout(typeWriter, 30);
                        }
                    }
                    typeWriter();
                }, 1200);
            });
        });
    </script>
</body>
</html>
