<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine ❤️</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #ffe6f2;
            color: #d63384;
            padding: 20px;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            display: inline-block;
            max-width: 400px;
        }
        button {
            background-color: #ff4d94;
            color: white;
            border: none;
            padding: 10px 20px;
            margin: 10px;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #e60073;
        }
    </style>
</head>
<body>
    <div class="container" id="question-container">
        <h2>Hey my love ❤️</h2>
        <p>I just want to say that I love you and cherish every moment with you. Now, I have a few sweet questions for you... 💕</p>
        <button onclick="nextQuestion(1)">Start 💌</button>
    </div>

    <script>
        let answers = {};

        function nextQuestion(step) {
            let container = document.getElementById('question-container');
            if (step === 1) {
                container.innerHTML = `<h2>Would you be my Valentine? ❤️</h2>
                <button onclick="saveAnswer('valentine', 'Yes'); nextQuestion(2)">Yes 💖</button>
                <button onclick="saveAnswer('valentine', 'No'); nextQuestion(99)">No 💔</button>`;
            } else if (step === 2) {
                container.innerHTML = `<h2>What would you prefer to do? 🎬</h2>
                <button onclick="saveAnswer('activity', 'Watch Movie'); nextQuestion(3)">Watch Movie 🍿</button>
                <button onclick="saveAnswer('activity', 'Talk'); nextQuestion(5)">Just Talk 🥰</button>`;
            } else if (step === 3) {
                container.innerHTML = `<h2>What type of movie shall we watch? 🔮</h2>
                <button onclick="saveAnswer('movieType', 'Romantic'); nextQuestion(5)">Romantic Love Story ❤️</button>
                <button onclick="saveAnswer('movieType', 'Mystery'); nextQuestion(5)">Mystery Thriller 🕵️‍♀️</button>`;
            } else if (step === 5) {
                container.innerHTML = `<h2>What would you like to have for dinner tomorrow night? 🍽️</h2>
                <button onclick="saveAnswer('food', 'Donut'); nextQuestion(6)">Donut 🍩</button>
                <button onclick="saveAnswer('food', 'Pizza'); nextQuestion(6)">Pizza 🍕</button>
                <button onclick="saveAnswer('food', 'Pasta'); nextQuestion(6)">Pasta 🍝</button>`;
            } else if (step === 6) {
                container.innerHTML = `<h2>Yay! I can’t wait for tomorrow! ❤️</h2>
                <p>Here’s what you chose:</p>
                <p>💖 Valentine: ${answers.valentine}</p>
                <p>🎬 Activity: ${answers.activity || 'None'}</p>
                <p>🍿 Movie Type: ${answers.movieType || 'None'}</p>
                <p>🍽️ Food: ${answers.food}</p>
                <p>I’m so excited! Love you! 😘</p>`;
            } else if (step === 99) {
                container.innerHTML = `<h2>Oh no! 💔</h2><p>Well, I still love you anyway! 😘</p>`;
            }
        }

        function saveAnswer(question, answer) {
            answers[question] = answer;
        }
    </script>
</body>
</html>
