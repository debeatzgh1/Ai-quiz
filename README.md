# 🎓 AI True/False Quiz — GitHub Pages Version

Welcome to the **AI True/False Quiz**, a fully interactive, timed, modern educational quiz designed using **HTML, CSS, and JavaScript**. This project is optimized for **GitHub Pages**, **Blogger embeds**, and **mobile responsiveness**.

This quiz automatically scales for Blogger, includes a floating widget launcher, smart iframe modal preview, and adaptive height communication between parent/child pages to prevent scroll clipping.

---

## 🚀 Live Demo

**GitHub Pages Live:**
👉 [https://debeatzgh1.github.io/Ai-quiz/](https://debeatzgh1.github.io/Ai-quiz/)

**Blogger Embedded Live Preview:**
👉 [https://beatzde4.blogspot.com/p/ai-social-carousel-grid-debeatzgh-root.html](https://beatzde4.blogspot.com/p/ai-social-carousel-grid-debeatzgh-root.html)

---

## 📌 Features

* 20 AI knowledge True/False questions
* 5‑second auto-timer per question
* Automatic question advance
* Responsive UI
* Full score summary + detailed corrections
* Retake quiz option
* Blogger auto-height adjustment
* Floating widget button with iframe modal

---

## 📁 Project Structure

```
Ai-quiz/
 ├── index.html
 ├── assets/
 │     └── styles.css (optional external stylesheet)
 └── README.md
```

---

## 🧠 How It Works

### 1. Timer Logic

Each question has **5 seconds**. If the user doesn’t answer, it moves automatically.

### 2. Score Calculation

Each correct answer = **5 marks** → Total = **100 marks**.

### 3. Summary Output

At the end, users see:

* Total score
* Every question
* Correct answers vs their picked answers

### 4. Retake & Finish Flow

Users can retake the quiz or finish with a closing message.

---

## 🖼 Floating Widget Button (Included)

This floating button opens your widgets in an iframe modal.

```html
<!-- Floating Widget Button -->
<style>
  #widget-launcher {
    position: fixed;
    top: 20px;
    right: 20px;
    background: #2563eb;
    padding: 10px 16px;
    color: #fff;
    border-radius: 10px;
    font-weight: 700;
    cursor: pointer;
    z-index: 99999;
    box-shadow: 0 4px 10px rgba(0,0,0,0.25);
  }
  #iframe-modal {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.6);
    backdrop-filter: blur(4px);
    z-index: 99998;
  }
  #iframe-box {
    width: 90%;
    height: 90%;
    background: white;
    margin: 3% auto;
    border-radius: 14px;
    overflow: hidden;
    position: relative;
  }
  #close-modal {
    position: absolute;
    top: 10px;
    right: 20px;
    font-size: 28px;
    cursor: pointer;
  }
</style>

<div id="widget-launcher">Widget</div>

<div id="iframe-modal">
  <div id="iframe-box">
    <span id="close-modal">&times;</span>
    <iframe id="widget-frame" style="width:100%;height:100%;border:none;"></iframe>
  </div>
</div>

<script>
  document.getElementById("widget-launcher").onclick = () => {
    document.getElementById("widget-frame").src = "https://debeatzgh1.github.io/curly-chainsaw/";
    document.getElementById("iframe-modal").style.display = "block";
  };

  document.getElementById("close-modal").onclick = () => {
    document.getElementById("iframe-modal").style.display = "none";
    document.getElementById("widget-frame").src = "";
  };
</script>
```

---

## 📦 Full Quiz HTML Script (Included)

Your full upgraded quiz HTML script is embedded in the repository—ready to deploy on GitHub Pages.

It includes:

* Layout scaling for Blogger
* JS quiz logic
* Auto-height messaging
* Modern UI design

---

## 🧩 How to Embed in Blogger

Use this snippet:

```html
<iframe src="https://debeatzgh1.github.io/Ai-quiz/" width="100%" height="900" style="border:none;overflow:hidden;"></iframe>
```

Matches automatically using `postMessage()` resizing.

---

## 🔧 How to Customize

You can change:

* Questions (in the JS array)
* Colors (CSS section)
* Timer duration
* Floating button launch URL
* Widget launcher styles

Need help? Tell me and I’ll edit the code.

---

## 🎨 Branding & UI Enhancement

Add your logo, brand colors, gradients, animations—or I can design a full UI theme for you.
Just say **“Upgrade UI”**.

---

## 📣 Credits

Developed for **Debeatzgh** — AI Tools & Widgets for Web Creators.

If you want:

* More widgets
* A full dashboard
* A multi-quiz engine
* A leaderboard system

Just let me know!

## Live Demo

Click below to launch the interactive quiz:

👉 **Live Demo:** [https://debeatzgh1.github.io/Ai-quiz/](https://debeatzgh1.github.io/Ai-quiz/)

> *GitHub READMEs cannot embed iframes, so the quiz opens in a new tab.*

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>AI True/False Quiz - Upgraded</title>
<style>
  body, html {
    width: 100%;
    max-width: 100%;
    overflow-x: hidden;
    font-family: Arial, sans-serif;
    background: #f3f4f6;
  }

  /* Universal scale-up for Blogger */
  .quiz-root {
    transform: scale(1.25);
    transform-origin: top center;
    width: 80%;
    margin: auto;
  }
  @media (max-width: 600px) {
    .quiz-root {
      transform: scale(1.05);
      width: 100%;
    }
  }

  .quiz-container {
    background: #ffffff;
    width: 100%;
    max-width: 850px;
    margin: 40px auto;
    padding: 30px;
    border-radius: 16px;
    box-shadow: 0 8px 28px rgba(0,0,0,0.15);
    text-align: center;
  }

  .quiz-title {
    font-size: 2rem;
    font-weight: 700;
    color: #111827;
    margin-bottom: 20px;
  }

  .quiz-question {
    font-size: 1.4rem;
    font-weight: 600;
    margin: 20px 0;
    color: #1f2937;
  }

  .timer {
    font-size: 1.2rem;
    font-weight: bold;
    color: #2563eb;
    margin-bottom: 20px;
  }

  .options {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 20px;
  }

  .quiz-option {
    background: #2563eb;
    color: white;
    padding: 12px 24px;
    border-radius: 10px;
    cursor: pointer;
    font-size: 1.2rem;
    font-weight: 600;
    transition: 0.2s;
  }
  .quiz-option:hover { background: #1e40af; }

  .summary {
    display: none;
    text-align: center;
    padding: 20px;
  }

  .quiz-score {
    font-size: 1.6rem;
    font-weight: bold;
    margin-bottom: 25px;
  }

  .retake-btn, .finish-btn {
    padding: 12px 22px;
    background: #16a34a;
    color: #fff;
    font-size: 1.2rem;
    border-radius: 10px;
    cursor: pointer;
    display: inline-block;
    margin-top: 20px;
    transition: 0.2s;
  }
  .retake-btn:hover, .finish-btn:hover { background: #0f7c36; }
</style>
</head>
<body>
<div class="quiz-root">
  <div class="quiz-container" id="quiz-box">
    <div class="quiz-title">AI True/False Challenge (20 Questions)</div>
    <div class="timer">Time Left: <span id="timer">5</span>s</div>
    <div class="quiz-question" id="question-text">Loading question...</div>
    <div class="options">
      <div class="quiz-option" onclick="submitAnswer(true)">TRUE</div>
      <div class="quiz-option" onclick="submitAnswer(false)">FALSE</div>
    </div>
  </div>

  <div class="summary" id="summary-box">
    <div class="quiz-title">Quiz Completed 🎉</div>
    <div class="quiz-score" id="score-text"></div>
    <div id="corrections"></div>
    <div class="retake-btn" onclick="restartQuiz()">Retake Quiz</div>
    <div class="finish-btn" onclick="endQuiz()">Finish</div>
  </div>
</div>

<script>
const questions = [
  { q: "AI can learn patterns from data.", a: true },
  { q: "AI never makes mistakes.", a: false },
  { q: "Machine learning is a subset of AI.", a: true },
  { q: "AI works exactly like the human brain.", a: false },
  { q: "Neural networks are inspired by biological neurons.", a: true },
  { q: "AI does not need data to function.", a: false },
  { q: "Robots and AI are the same thing.", a: false },
  { q: "AI can analyze images.", a: true },
  { q: "Chatbots use AI to understand messages.", a: true },
  { q: "AI cannot recognize speech.", a: false },
  { q: "AI can generate new images and text.", a: true },
  { q: "AI can replace all human jobs today.", a: false },
  { q: "Deep learning uses multiple layers of processing.", a: true },
  { q: "AI is 100% accurate all the time.", a: false },
  { q: "AI is used in self-driving cars.", a: true },
  { q: "AI cannot translate languages.", a: false },
  { q: "AI can detect spam emails.", a: true },
  { q: "All AI systems think independently.", a: false },
  { q: "AI can help doctors detect diseases.", a: true },
  { q: "AI models improve with more data.", a: true }
];

let index = 0;
let score = 0;
let timer = 5;
let countdown;
let userAnswers = [];

function loadQuestion() {
  if (index >= questions.length) return showSummary();

  document.getElementById("question-text").innerText = questions[index].q;
  timer = 5;
  document.getElementById("timer").innerText = timer;

  clearInterval(countdown);
  countdown = setInterval(() => {
    timer--;
    document.getElementById("timer").innerText = timer;
    if (timer <= 0) {
      submitAnswer(null);
    }
  }, 1000);
}

function submitAnswer(choice) {
  clearInterval(countdown);

  const correct = questions[index].a;
  userAnswers.push({
    question: questions[index].q,
    correct,
    picked: choice
  });

  if (choice === correct) score += 5;

  index++;
  loadQuestion();
}

function showSummary() {
  document.getElementById("quiz-box").style.display = "none";
  const sum = document.getElementById("summary-box");
  sum.style.display = "block";

  document.getElementById("score-text").innerText =
    `Your Score: ${score} / 100`;

  let html = "";
  userAnswers.forEach((u, i) => {
    html += `<p><strong>Q${i+1}:</strong> ${u.question}<br>Correct: ${u.correct ? "TRUE" : "FALSE"} | You: ${u.picked === null ? "No Answer" : u.picked}</p>`;
  });
  document.getElementById("corrections").innerHTML = html;
}

function restartQuiz() {
  index = 0;
  score = 0;
  userAnswers = [];
  document.getElementById("summary-box").style.display = "none";
  document.getElementById("quiz-box").style.display = "block";
  loadQuestion();
}

function endQuiz() {
  alert("Thank you for participating in the AI Quiz!");
}

loadQuestion();

/* Blogger Auto Height */
setInterval(() => {
  parent.postMessage(
    { quizHeight: document.body.scrollHeight + 50 },
    "*"
  );
}, 500);
</script>
</body>
</html>
