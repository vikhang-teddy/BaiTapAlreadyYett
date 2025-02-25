<html>
<head>
    <title>Already vs Yet Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }
        .question {
            margin: 20px 0;
            font-size: 18px;
        }
        .options button {
            display: block;
            margin: 5px auto;
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            cursor: pointer;
        }
        .correct {
            background-color: lightgreen;
        }
        .incorrect {
            background-color: lightcoral;
        }
        #submitBtn {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
            background-color: dodgerblue;
            color: white;
            border: none;
        }
    </style>
</head>
<body>
    <h2>Already vs Yet Quiz</h2>
    <div id="quiz"></div>
    <button id="submitBtn">Xác nhận</button>
    <p id="result"></p>
    
    <script>
        const questions = [
            { question: "I haven't finished my homework ___.", options: ["already", "yet"], answer: "yet" },
            { question: "She has ___ arrived at the airport.", options: ["already", "yet"], answer: "already" },
            { question: "Have you eaten lunch ___?", options: ["already", "yet"], answer: "yet" },
            { question: "He's ___ gone home, so you can't meet him now.", options: ["already", "yet"], answer: "already" },
            { question: "They haven’t called us ___.", options: ["already", "yet"], answer: "yet" },
            { question: "We have ___ seen that movie.", options: ["already", "yet"], answer: "already" },
            { question: "Has the package arrived ___?", options: ["already", "yet"], answer: "yet" },
            { question: "I've ___ finished my book.", options: ["already", "yet"], answer: "already" },
            { question: "She hasn’t decided what to wear ___.", options: ["already", "yet"], answer: "yet" },
            { question: "They have ___ left for the airport.", options: ["already", "yet"], answer: "already" },
            { question: "Has he done his homework ___?", options: ["already", "yet"], answer: "yet" },
            { question: "The guests have ___ arrived.", options: ["already", "yet"], answer: "already" },
            { question: "We haven’t eaten breakfast ___.", options: ["already", "yet"], answer: "yet" },
            { question: "She has ___ bought the tickets.", options: ["already", "yet"], answer: "already" },
            { question: "Have you finished your assignment ___?", options: ["already", "yet"], answer: "yet" },
            { question: "The train has ___ left the station.", options: ["already", "yet"], answer: "already" },
            { question: "They haven’t paid the bill ___.", options: ["already", "yet"], answer: "yet" },
            { question: "He has ___ cleaned his room.", options: ["already", "yet"], answer: "already" },
            { question: "Has she called you ___?", options: ["already", "yet"], answer: "yet" },
            { question: "I've ___ sent the email.", options: ["already", "yet"], answer: "already" },
            { question: "She hasn’t packed her suitcase ___.", options: ["already", "yet"], answer: "yet" },
            { question: "We have ___ completed the project.", options: ["already", "yet"], answer: "already" },
            { question: "Has he left for work ___?", options: ["already", "yet"], answer: "yet" },
            { question: "They have ___ started the meeting.", options: ["already", "yet"], answer: "already" },
            { question: "She hasn’t told me the news ___.", options: ["already", "yet"], answer: "yet" },
            { question: "The store has ___ opened.", options: ["already", "yet"], answer: "already" },
            { question: "Have they arrived at the hotel ___?", options: ["already", "yet"], answer: "yet" },
            { question: "He has ___ called his friend.", options: ["already", "yet"], answer: "already" },
            { question: "I haven't checked my email ___.", options: ["already", "yet"], answer: "yet" }
        ];

        const quizDiv = document.getElementById("quiz");
        let userAnswers = [];

        questions.forEach((q, index) => {
            const questionDiv = document.createElement("div");
            questionDiv.classList.add("question");
            questionDiv.innerHTML = `<p>${q.question}</p>`;
            
            const optionsDiv = document.createElement("div");
            optionsDiv.classList.add("options");

            q.options.forEach(option => {
                const btn = document.createElement("button");
                btn.innerText = option;
                btn.onclick = () => {
                    userAnswers[index] = option;
                    if (option === q.answer) {
                        btn.classList.add("correct");
                    } else {
                        btn.classList.add("incorrect");
                    }
                };
                optionsDiv.appendChild(btn);
            });
            
            questionDiv.appendChild(optionsDiv);
            quizDiv.appendChild(questionDiv);
        });

        document.getElementById("submitBtn").onclick = () => {
            let correctCount = userAnswers.filter((ans, i) => ans === questions[i].answer).length;
            document.getElementById("result").innerText = `Bạn trả lời đúng ${correctCount} / ${questions.length} câu!`;
        };
    </script>
</body>
</html>
