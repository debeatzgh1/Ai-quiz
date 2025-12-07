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
