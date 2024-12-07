<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive README</title>
    <style>
        body { font-family: Arial, sans-serif; }
        .question { margin: 20px 0; }
        .feedback { font-weight: bold; margin-top: 10px; }
        button { margin-top: 10px; padding: 10px; }
    </style>
</head>
<body>
    <h1>Interactive README with MCQs</h1>
    <form id="quizForm">
        <div class="question">
            <p>1. What does HTML stand for?</p>
            <label><input type="radio" name="q1" value="wrong"> Hyper Text Markdown Language</label><br>
            <label><input type="radio" name="q1" value="correct"> Hyper Text Markup Language</label><br>
            <label><input type="radio" name="q1" value="wrong"> High Text Machine Language</label>
        </div>
        <div class="question">
            <p>2. What is the purpose of CSS?</p>
            <label><input type="radio" name="q2" value="correct"> Styling web pages</label><br>
            <label><input type="radio" name="q2" value="wrong"> Programming logic</label><br>
            <label><input type="radio" name="q2" value="wrong"> Storing data</label>
        </div>
        <button type="button" onclick="checkAnswers()">Submit</button>
    </form>
    <div id="feedback"></div>
    <script>
        function checkAnswers() {
            const form = document.getElementById('quizForm');
            const feedback = document.getElementById('feedback');
            const answers = new FormData(form);
            let score = 0;
            let total = 2; // Number of questions

            if (answers.get("q1") === "correct") score++;
            if (answers.get("q2") === "correct") score++;

            feedback.innerHTML = `<p>You scored ${score} out of ${total}.</p>`;
        }
    </script>
</body>
</html>
