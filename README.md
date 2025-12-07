              <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>AI True/False Quiz</title>
<style>
  body { font-family: Arial, sans-serif; background:#f5f5f5; margin:0; padding:20px; }
  .quiz-container { background:#fff; max-width:700px; margin:auto; padding:20px; border-radius:12px; box-shadow:0 4px 12px rgba(0,0,0,0.1); }
  .question { font-size:1.3rem; margin-bottom:20px; }
  .btn { display:block; width:100%; padding:15px; margin:10px 0; cursor:pointer; font-size:1.1rem; border:none; border-radius:8px; background:#007bff; color:#fff; }
  .btn:hover { background:#005fcc; }
  .timer { font-size:1.2rem; margin-bottom:10px; color:#e53935; font-weight:bold; }
  .summary { text-align:center; }
  .hidden { display:none; }
</style>
</head>
<body>
<div class="quiz-container">
  <div id="quizBox">
    <div class="timer">Time Left: <span id="time">5</span>s</div>
    <div class="question" id="questionText"></div>
    <button class="btn" onclick="answer(true)">True</button>
    <button class="btn" onclick="answer(false)">False</button>
  </div>

  <div id="summaryBox" class="summary hidden">
    <h2>Quiz Summary</h2>
    <p id="scoreText"></p>
    <button class="btn" onclick="retake(true)">Retake Quiz</button>
    <button class="btn" onclick="retake(false)" style="background:#444;">Finish</button>
  </div>
</div>

<script>
const questions = [
  { q: "AI can learn patterns from data.", a: true },
  { q: "AI and robots are the same thing.", a: false },
  { q: "Machine learning is a subset of AI.", a: true },
  { q: "AI cannot recognize images.", a: false },
  { q: "Neural networks mimic the human brain.", a: true },
  { q: "AI can work without electricity.", a: false },
  { q: "Chatbots are examples of AI.", a: true },
  { q: "AI is always accurate.", a: false },
  { q: "AI helps detect fraud in banking.", a: true },
  { q: "AI cannot translate languages.", a: false },
  { q: "Deep learning is based on neural networks.", a: true },
  { q: "AI cannot drive cars.", a: false },
  { q: "AI can predict weather patterns.", a: true },
  { q: "AI is purely random guesswork.", a: false },
  { q: "AI helps medical diagnosis.", a: true },
  { q: "AI cannot play games like chess.", a: false },
  { q: "AI models improve with more data.", a: true },
  { q: "AI can replace all humans.", a: false },
  { q: "Voice assistants use AI.", a: true },
  { q: "AI cannot analyze large datasets.", a: false }
];

let index = 0;
let score = 0;
let timer;
let timeLeft = 5;

function loadQuestion() {
  if (index >= questions.length) return showSummary();
  document.getElementById("questionText").innerText = questions[index].q;
  resetTimer();
}

function resetTimer() {
  timeLeft = 5;
  document.getElementById("time").innerText = timeLeft;
  clearInterval(timer);
  timer = setInterval(() => {
    timeLeft--;
    document.getElementById("time").innerText = timeLeft;
    if (timeLeft <= 0) {
      clearInterval(timer);
      index++;
      loadQuestion();
    }
  }, 1000);
}

function answer(choice) {
  if (questions[index].a === choice) score += 5;
  index++;
  loadQuestion();
}

function showSummary() {
  document.getElementById("quizBox").classList.add("hidden");
  document.getElementById("summaryBox").classList.remove("hidden");
  document.getElementById("scoreText").innerText = `You scored ${score} out of 100`;
}

function retake(choice) {
  if (!choice) {
    alert("Thank you for participating!");
    return;
  }
  index = 0;
  score = 0;
  document.getElementById("summaryBox").classList.add("hidden");
  document.getElementById("quizBox").classList.remove("hidden");
  loadQuestion();
}

window.onload = loadQuestion;

// Auto-resize for Blogger
setInterval(() => {
  parent.postMessage({ quizHeight: document.body.scrollHeight }, "*");
}, 500);
</script>
</body>
</html>
                                                                                                                                                                                           | Project                                                                                                                                                      | Description                                                                                                         | Action                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| ![Custom Blogger Theme](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/generateamobile-firstresponsivebloggertemplatewithcustomizablecolorsfontsandsections1576324612066211977.jpg)                                                            | **[Custom Blogger Theme with Dynamic Post Loading and Logo](https://debeatzgh1.github.io/Custom-Blogger-Theme-for-with-Dynamic-Post-Loading-and-Logo-/)**    | A responsive, mobile-first Blogger theme with customizable sections, dynamic post loading, and custom logo support. | [🔗 View Demo](https://debeatzgh1.github.io/Custom-Blogger-Theme-for-with-Dynamic-Post-Loading-and-Logo-/)       |
| ![Popup Generator](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createatoolthatgeneratesiframeorcard-styleembedsforindividualbloggerpostscompletewiththumbnailtitleandreadmorebuttonforcross-blogpromotion754077096311972631.jpg)            | **[Popup HTML Page Generator](https://debeatzgh1.github.io/popup-html-page-generator-blogger/)**                                                             | Easily generate iframe or card-style embeds for individual Blogger posts with thumbnails and read-more buttons.     | [🔗 View Demo](https://debeatzgh1.github.io/popup-html-page-generator-blogger/)                                  |
| ![Newsletter Widget](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/amodernflat-styleillustrationofanotificationbellwithglowinghighlightssurroundedbyabstractshapespaperenvelopesanddigitalicons28emailmessageupdate293314991682681990671.jpg) | **[Sliding Newsletter Signup Widget](https://debeatzgh1.github.io/Sliding-Newsletter-Signup-Widget-with-Pulse-Animation/)**                                  | A modern newsletter signup widget with sliding animation and pulsing notification highlights.                       | [🔗 View Demo](https://debeatzgh1.github.io/Sliding-Newsletter-Signup-Widget-with-Pulse-Animation/)              |
| ![Product Carousel](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designacleanmodernthumbnailforabloggerproductscarouseltool1711994558720457535.jpg)                                                                                          | **[Blogger Product Carousel with WhatsApp Floating Button](https://debeatzgh1.github.io/Blogger-Product-Carousel-with-WhatsApp-Floating-Button/)**           | Showcase Blogger products in a responsive carousel with a built-in WhatsApp floating button for instant contact.    | [🔗 View Demo](https://debeatzgh1.github.io/Blogger-Product-Carousel-with-WhatsApp-Floating-Button/)             |
| ![Floating Dock](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/amodernminimallayoutwithafloatingdockofcolorfulroundicons28patreonbloggergithub29ontherightsideofacleanwebpagemockup6676994054500999142.jpg)                                   | **[Floating Dock Smart Iframe Modal](https://debeatzgh1.github.io/-Floating-Dock-Smart-Iframe-Modal/)**                                                      | A modern floating dock with colorful round icons and iframe modal integration.                                      | [🔗 View Demo](https://debeatzgh1.github.io/-Floating-Dock-Smart-Iframe-Modal/)                                  |
| ![Tailwind Homepage](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createamodernandcleanthumbnailforawebdevelopmentproducttitledmodernhomepagestylingtemplatewithtailwindcss3420170625469385526.jpg)                                          | **[Modern Homepage Styling with TailwindCSS](https://debeatzgh1.github.io/Modern-homepage-styling-with-TailwindCSS-/)**                                      | A clean and modern homepage layout template styled with TailwindCSS.                                                | [🔗 View Demo](https://debeatzgh1.github.io/Modern-homepage-styling-with-TailwindCSS-/)                          |
| ![TechAdapt Solutions](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/wp-17550417188267308669484942620808.jpg)                                                                                                                                 | **[TechAdapt Solutions – Strategies for Modern Startups](https://debeatzgh1.github.io/TechAdapt-Solutions-Strategies-for-Modern-Startups-and-Individuals/)** | Practical strategies, resources, and tools for startups and individuals adapting to the modern digital world.       | [🔗 View Demo](https://debeatzgh1.github.io/TechAdapt-Solutions-Strategies-for-Modern-Startups-and-Individuals/) |

---

## 🛠️ Features

* ✅ Fully responsive designs
* ✅ Blogger-friendly & easy to embed
* ✅ Lightweight, no heavy dependencies
* ✅ Includes floating buttons, modals, and animations
* ✅ Perfect for enhancing engagement & monetization

---

## 📌 Explore More Scripts

👉 Check out the full curated collection here:
[**Firebase Curated Front-End Components**](https://github.com/debeatzgh1/firebase-front-end-components)

---

## 💡 Contribution

Want to suggest improvements or add your own scripts?

* Open an **issue**
* Submit a **pull request**
* Share your ideas in the discussions

---

## 📜 License

This project is released under the **MIT License** – free to use, modify, and share with attribution.

---

✨ Designed for creators, bloggers, and developers who want to level up their Blogger sites with modern UI components.

---


# 🌐 Personal Portfolio Website

A simple and responsive personal portfolio website built with **HTML, CSS, and JavaScript**.  
This project is perfect for showcasing your skills, projects, and contact information.  

Live Demo 👉 [View Portfolio](https://debeatzgh.github.io/portfolio-site/)

---

## ✨ Features
- Responsive design (works on mobile & desktop)  
- Navigation bar with smooth scrolling  
- Hero section with intro & call-to-action button  
- About section with bio details  
- Projects section with cards  
- Contact section with email & social links  
- **Dark mode toggle** 🌙☀️  

---

## 🛠️ Technologies Used
- **HTML5** – Structure  
- **CSS3** – Styling & Responsive design  
- **JavaScript (Vanilla)** – Interactivity (dark mode toggle)  
- **GitHub Pages** – Free hosting & deployment  

---

## 🚀 Getting Started
To run this project locally:  

1. Clone the repository:
   ```bash
   git clone https://github.com/debeatzgh1/portfolio-site.git

# 🚀 DeBeatzGH – AI Tools & Side Hustle Hub  

![DeBeatzGH Thumbnail](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designamodernminimalisticdesignfeaturinganai-themedicon28likeabraincircuitorrobot29overlaidwithdebeatzghoraitoolshustles6089986211026037047.jpg)  

## 🌟 About  
Welcome to **[DeBeatzGH](https://debeatzgh.wordpress.com/)** — your go-to hub for **AI tools, side hustle strategies, blogging resources, and digital growth guides**.  

Our platform is built to help **students, creators, startups, and professionals** unlock the power of AI, monetize their skills, and thrive in today’s digital economy.  

### ✨ What You’ll Find  
- 💡 Explore **AI prompts, tools, and hacks**  
- 📈 Discover **side hustle strategies & online income ideas**  
- ✍️ Access **blogging & digital business guides**  
- 🚀 Stay ahead with **regular updates and fresh insights**  

---

## 👉 Get Started  
🔥 **Start your journey today → [Visit DeBeatzGH]([https://debeatzgh.wordpress.com/](https://www.patreon.com/debeatzgh/collections))**  

---


<!-- README: DebeatzGH Digital Store (HTML-friendly for GitHub) -->
<div align="center">
  <a href="https://www.socialcreator.com/debeatzgh" target="_blank" rel="noopener">
    <img
      src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg"
      alt="DebeatzGH Digital Store"
      style="max-width:100%; border-radius:16px;"
    />
  </a>

  <h1 style="margin-top: 14px;">DebeatzGH Digital Store</h1>
  <p style="max-width:780px;">
    Your hub for AI insights, tech tutorials, side-hustle playbooks, and productivity tools.
    Learn, build, and launch digital projects faster.
  </p>

  <!-- CTAs -->
  <p>
    <a href="https://www.socialcreator.com/debeatzgh" target="_blank" rel="noopener"
       style="display:inline-block; padding:10px 16px; margin:4px; border-radius:999px; text-decoration:none; font-weight:600; border:1px solid #2563eb;">
      🚀 View Live App
    </a>
    <a href="https://github.com/debeatzgh1/Personal-Portfolio-site-" target="_blank" rel="noopener"
       style="display:inline-block; padding:10px 16px; margin:4px; border-radius:999px; text-decoration:none; font-weight:600; border:1px solid #111827;">
      ⭐ Star this Repo
    </a>
  </p>
</div>

<hr/>

<h2>Overview</h2>
<p>
  <strong>DebeatzGH</strong> helps beginners and creators build profitable digital assets:
  blogs, affiliate funnels, AI-assisted content, and more. Explore tutorials, tools, and
  ready-to-use components to speed up your workflow.
</p>

<h2>Features</h2>
<ul>
  <li><strong>AI & Tech Learning:</strong> Bite-sized guides for modern tools and workflows.</li>
  <li><strong>Side-Hustle Playbooks:</strong> Practical steps to validate and launch ideas.</li>
  <li><strong>Productivity Toolkit:</strong> Reusable widgets, templates, and scripts.</li>
  <li><strong>Beginner-Friendly:</strong> Clear explanations, curated resources, and examples.</li>
</ul>

<h2>Quick Start</h2>
<ol>
  <li>Clone:
    <pre><code>git clone https://github.com/debeatzgh1/Personal-Portfolio-site-</code></pre>
  </li>
  <li>Enter folder:
    <pre><code>cd debeatzgh</code></pre>
  </li>
  <li>Install deps (adjust to your stack):
    <pre><code># Node
npm install
npm run dev

# or Python
pip install -r requirements.txt
python app.py</code></pre>
  </li>
  <li>Open in browser:
    <pre><code>http://localhost:3000</code></pre>
  </li>
</ol>

<h2>Project Links</h2>
<ul>
  <li>🌐 Live App: <a href="https://www.socialcreator.com/debeatzgh" target="_blank" rel="noopener">socialcreator.com/debeatzgh</a></li>
  <li>🖼️ Thumbnail: <a href="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg" target="_blank" rel="noopener">View image</a></li>
</ul>

<h2>Contributing</h2>
<p>
  Contributions are welcome! Open an issue for bugs or ideas. For changes, fork the repo,
  create a feature branch, and submit a pull request.
</p>

<h2>License</h2>
<p>
  Released under the <a href="./LICENSE">MIT License</a>.
</p>

<hr/>

<div align="center">
  <p><em>If this project helps you, consider giving it a star. It really helps! ⭐</em></p>
  <p>
    <a href="https://www.socialcreator.com/debeatzgh/?s=314768" target="_blank" rel="noopener"
       style="display:inline-block; padding:10px 16px; margin-top:6px; border-radius:10px; text-decoration:none; font-weight:600; border:1px solid #2563eb;">
      PRODUCTS →
    </a>
  </p>
</div>
