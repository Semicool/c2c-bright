<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cat Peeps</title>
    <style>
        /* General body and font styles */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            text-align: center;
            background-color: #fff; /* Light mode background */
            color: #333; /* Light mode text color */
        }

        .dark-mode {
            background-color: #333; /* Dark mode background */
            color: #fff; /* Dark mode text color */
        }

        header {
            background-color: #ffcc99;
            padding: 1rem;
        }

        header h1 {
            margin: 0;
        }

        nav ul {
            list-style: none;
            padding: 0;
        }

        nav ul li {
            display: inline;
            margin-right: 20px;
        }

        nav ul li a {
            text-decoration: none;
            color: #333;
        }

        .dark-mode nav ul li a {
            color: #fff; /* Dark mode link color */
        }

        .carousel {
            position: relative;
            width: 600px;
            margin: 0 auto;
            overflow: hidden;
        }

        .carousel-images {
            display: flex;
            width: 2400px;
            transition: transform 0.5s ease-in-out;
        }

        .carousel-images img {
            width: 600px;
            height: 400px;
            object-fit: cover;
        }

        .prev, .next {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0,0,0,0.5);
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
        }

        .prev {
            left: 0;
        }

        .next {
            right: 0;
        }

        form {
            padding: 20px;
            background-color: #e6e6e6;
            margin: 20px auto;
            width: 50%;
            border-radius: 8px;
        }

        form.dark-mode {
            background-color: #444; /* Dark mode form background */
            color: #ddd; /* Dark mode form text color */
        }

        form label {
            display: block;
            margin: 10px 0 5px;
        }

        form input[type="text"],
        form input[type="email"] {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
        }

        form input[type="submit"] {
            background-color: #ffcc99;
            color: #fff;
            border: none;
            padding: 10px;
            cursor: pointer;
            width: 100%;
        }

        .dark-mode form input[type="submit"] {
            background-color: #666; /* Dark mode submit button */
        }

        footer {
            background-color: #333;
            color: #fff;
            padding: 10px;
        }

        .dark-mode footer {
            background-color: #444; /* Dark mode footer background */
        }

        .quiz-container {
            max-height: 500px;
            overflow-y: auto;
            padding: 20px;
            margin: 20px auto;
            width: 50%;
            background-color: #f4f4f4;
            border-radius: 8px;
        }

        .dark-mode .quiz-container {
            background-color: #555; /* Dark mode quiz background */
        }

        .quiz-button {
            background-color: #ffcc99;
            color: #fff;
            border: none;
            padding: 10px;
            cursor: pointer;
            width: 100%;
        }

        .dark-mode .quiz-button {
            background-color: #666; /* Dark mode quiz button */
        }

        .result {
            font-size: 1.2rem;
            margin-top: 20px;
        }

        .error-message {
            color: red;
            font-size: 1.2rem;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <header>
        <h1>Cat Peeps</h1>
        <nav>
            <ul>
                <li><a href="#about">About Cats</a></li>
                <li><a href="#gallery">Gallery</a></li>
                <li><a href="#signup">Newsletter</a></li>
                <li><button onclick="toggleDarkMode()">Toggle Dark Mode</button></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="about">
            <h2>Why We Love Cats</h2>
            <p>Cats are more than just pets—they are charming companions that have earned their place in our hearts and homes. Their agility, independence, and playful nature make them endlessly fascinating. Whether they're lounging in the sun or chasing a toy, cats bring joy and comfort to those around them.</p>
            <p>Cats have been domesticated for thousands of years, and their ancient history is rich with stories of reverence and fascination. From ancient Egypt, where they were worshiped as sacred animals, to modern times where they are beloved members of our families, cats have always held a special place in human culture.</p>
            <p>Not only are cats adorable, but they also have unique personalities. Some are fiercely independent, while others are affectionate lap cats. Their varied breeds each have their own traits, making every cat special in its own way.</p>
        </section>

        <section id="gallery">
            <h2>Gallery Access</h2>
            <div class="login-container">
                <h3>Login to Access the Gallery</h3>
                <form id="loginForm">
                    <label for="username">Username:</label>
                    <input type="text" id="username" name="username" required>
                    <label for="password">Password:</label>
                    <input type="password" id="password" name="password" required>
                    <button type="button" onclick="checkLogin()">Login</button>
                    <div id="error-message" class="error-message"></div>
                </form>
            </div>

            <div id="carousel-container" style="display: none;">
                <h2>Cat Gallery</h2>
                <div class="carousel">
                    <div class="carousel-images">
                        <img src="https://cdn.britannica.com/70/234870-050-D4D024BB/Orange-colored-cat-yawns-displaying-teeth.jpg" alt="Cat 1">
                        <img src="https://images.saymedia-content.com/.image/ar_16:9%2Cc_fill%2Ccs_srgb%2Cq_auto:eco%2Cw_1200/MTk2ODc3MzMxMjI1MTI2MzI1/cats-speak.png" alt="Cat 2">
                        <img src="https://www.vetmed.wisc.edu/wp-content/uploads/2022/12/lina-angelov-Ah_QC2v2alE-unsplash-1200x960.jpg" alt="Cat 3">
                        <img src="https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.nationalgeographic.com%2Fadventure%2Farticle%2F140127-cats-pets-animals-nation-dogs-people-science&psig=AOvVaw3TuljMM04hjzH-19-AkxYe&ust=1725986850023000&source=images&cd=vfe&opi=89978449&ved=0CBQQjRxqFwoTCNiOnZuotogDFQAAAAAdAAAAABAZ" alt="Cat 4">
                    </div>
                    <button class="prev" onclick="prevSlide()">&#10094;</button>
                    <button class="next" onclick="nextSlide()">&#10095;</button>
                </div>
            </div>
        </section>

        <section id="quiz">
            <h2>Cat Quiz</h2>
            <div class="quiz-container">
                <form id="quizForm">
                    <div class="question">
                        <p>1. What breed of cat is known for its large size and tufted ears?</p>
                        <ul>
                            <li>
                                <input type="radio" id="q1-option1" name="q1" value="a">
                                <label for="q1-option1">A) Siamese</label>
                            </li>
                            <li>
                                <input type="radio" id="q1-option2" name="q1" value="b">
                                <label for="q1-option2">B) Persian</label>
                            </li>
                            <li>
                                <input type="radio" id="q1-option3" name="q1" value="c">
                                <label for="q1-option3">C) Maine Coon</label>
                            </li>
                            <li>
                                <input type="radio" id="q1-option4" name="q1" value="d">
                                <label for="q1-option4">D) Sphynx</label>
                            </li>
                        </ul>
                    </div>
                    <div class="question">
                        <p>2. Which breed is known for being particularly friendly and sociable?</p>
                        <ul>
                            <li>
                                <input type="radio" id="q2-option1" name="q2" value="a">
                                <label for="q2-option1">A) Maine Coon</label>
                            </li>
                            <li>
                                <input type="radio" id="q2-option2" name="q2" value="b">
                                <label for="q2-option2">B) Ragdoll</label>
                            </li>
                            <li>
                                <input type="radio" id="q2-option3" name="q2" value="c">
                                <label for="q2-option3">C) British Shorthair</label>
                            </li>
                            <li>
                                <input type="radio" id="q2-option4" name="q2" value="d">
                                <label for="q2-option4">D) Sphynx</label>
                            </li>
                        </ul>
                    </div>
                    <!-- Add more questions as needed -->
                    <button type="button" class="quiz-button" onclick="submitQuiz()">Submit</button>
                </form>
                <div id="quiz-result" class="result"></div>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 Cat Peeps. All rights reserved.</p>
    </footer>

    <script>
        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
            document.querySelector('form').classList.toggle('dark-mode');
            document.querySelector('.quiz-container').classList.toggle('dark-mode');
        }

        function checkLogin() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const errorMessage = document.getElementById('error-message');
            const carouselContainer = document.getElementById('carousel-container');

            if (username === 'admin' && password === 'password123') {
                // Show the carousel and hide the login form
                document.querySelector('.login-container').style.display = 'none';
                carouselContainer.style.display = 'block';
            } else {
                errorMessage.textContent = 'Access denied. Please check your username and password.';
            }
        }

        function submitQuiz() {
            const answers = {
                q1: 'c', // Correct answer for question 1
                q2: 'b', // Correct answer for question 2
                // Add more correct answers if needed
            };

            let score = 0;
            const form = document.getElementById('quizForm');
            const resultDiv = document.getElementById('quiz-result');
            resultDiv.innerHTML = ''; // Clear previous results

            for (let [question, correctAnswer] of Object.entries(answers)) {
                const selectedAnswer = form.querySelector(`input[name="${question}"]:checked`);
                if (selectedAnswer && selectedAnswer.value === correctAnswer) {
                    score++;
                }
            }

            resultDiv.innerHTML = `You got ${score} out of ${Object.keys(answers).length} questions right!`;
        }

        // Carousel JavaScript
        let currentIndex = 0;
        const images = document.querySelectorAll('.carousel-images img');
        const totalImages = images.length;

        function showSlide(index) {
            const carouselImages = document.querySelector('.carousel-images');
            if (index >= totalImages) {
                currentIndex = 0;
            } else if (index < 0) {
                currentIndex = totalImages - 1;
            } else {
                currentIndex = index;
            }
            const translateX = -currentIndex * 600; // Width of the image (600px)
            carouselImages.style.transform = `translateX(${translateX}px)`;
        }

        function nextSlide() {
            showSlide(currentIndex + 1);
        }

        function prevSlide() {
            showSlide(currentIndex - 1);
        }

        // Automatic slide
        setInterval(() => {
            nextSlide();
        }, 3000); // Change slide every 3 seconds
    </script>
</body>
</html>