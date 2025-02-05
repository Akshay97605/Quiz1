<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GK Quiz</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; margin: 20px; }
        .container { width: 60%; margin: auto; text-align: left; }
        .question { margin-bottom: 10px; font-weight: bold; }
        .options { margin-bottom: 20px; }
        button { padding: 10px 20px; font-size: 16px; cursor: pointer; }
        .result { font-size: 20px; font-weight: bold; margin-top: 20px; }
    </style>
</head>
<body>

    <h1>General Knowledge Quiz</h1>
    <form id="quizForm">
        <div class="container">
            <div class="question">1. What is the capital of France?</div>
            <div class="options">
                <input type="radio" name="q1" value="A"> A. London<br>
                <input type="radio" name="q1" value="B"> B. Paris<br>
                <input type="radio" name="q1" value="C"> C. Berlin<br>
                <input type="radio" name="q1" value="D"> D. Madrid<br>
            </div>

            <div class="question">2. Who wrote 'Hamlet'?</div>
            <div class="options">
                <input type="radio" name="q2" value="A"> A. Charles Dickens<br>
                <input type="radio" name="q2" value="B"> B. William Shakespeare<br>
                <input type="radio" name="q2" value="C"> C. Mark Twain<br>
                <input type="radio" name="q2" value="D"> D. Jane Austen<br>
            </div>

            <div class="question">3. What is the largest planet in our solar system?</div>
            <div class="options">
                <input type="radio" name="q3" value="A"> A. Earth<br>
                <input type="radio" name="q3" value="B"> B. Mars<br>
                <input type="radio" name="q3" value="C"> C. Jupiter<br>
                <input type="radio" name="q3" value="D"> D. Saturn<br>
            </div>

            <div class="question">4. Which ocean is the largest?</div>
            <div class="options">
                <input type="radio" name="q4" value="A"> A. Atlantic Ocean<br>
                <input type="radio" name="q4" value="B"> B. Indian Ocean<br>
                <input type="radio" name="q4" value="C"> C. Arctic Ocean<br>
                <input type="radio" name="q4" value="D"> D. Pacific Ocean<br>
            </div>

            <div class="question">5. What is the square root of 64?</div>
            <div class="options">
                <input type="radio" name="q5" value="A"> A. 6<br>
                <input type="radio" name="q5" value="B"> B. 7<br>
                <input type="radio" name="q5" value="C"> C. 8<br>
                <input type="radio" name="q5" value="D"> D. 9<br>
            </div>

            <button type="button" onclick="calculateScore()">Submit</button>
        </div>
    </form>

    <div id="result" class="result"></div>

    <script>
        function calculateScore() {
            let answers = { q1: "B", q2: "B", q3: "C", q4: "D", q5: "C" };
            let score = 0;

            for (let key in answers) {
                let selected = document.querySelector(`input[name="${key}"]:checked`);
                if (selected && selected.value === answers[key]) {
                    score++;
                }
            }

            let resultDiv = document.getElementById("result");
            resultDiv.innerHTML = `Your Score: ${score} / 5`;

            // Redirect to result page after 2 seconds
            setTimeout(() => {
                window.location.href = `result.html?score=${score}`;
            }, 2000);
        }
    </script>

</body>
</html>
