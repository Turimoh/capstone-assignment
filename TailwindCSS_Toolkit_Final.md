# Getting Started with TailwindCSS — A Beginner's Guide

**Moringa School | GenAI Capstone | Week 1**

---

## 1. Title & Objective

**Technology chosen:** TailwindCSS

**Why I chose it:** TailwindCSS is one of the most widely used CSS frameworks in modern web development. Unlike traditional CSS or Bootstrap, it takes a "utility-first" approach — meaning you style elements directly in HTML using small, single-purpose classes. This makes it fast to build with and easy to understand visually.

**End goal:** Render a styled, interactive UI card component (Hello World) in the browser using only TailwindCSS utility classes — no custom CSS written.

---

## 2. Quick Summary of TailwindCSS

**What is it?**
TailwindCSS is a utility-first CSS framework. Instead of writing classes like `.card { padding: 16px; background: white; }`, you write `class="p-4 bg-white"` directly in your HTML. Every class does one thing.

**Where is it used?**
It's used in frontend development across the web — from personal portfolios to large-scale production apps. It works with plain HTML, React, Vue, Next.js, and more.

**Real-world example:**
Vercel (the platform that hosts millions of web apps) uses TailwindCSS for its entire dashboard UI.

---

## 3. System Requirements

| Requirement | Details |
|-------------|---------|
| OS | Windows, macOS, or Linux |
| Browser | Any modern browser (Chrome, Firefox, Edge) |
| Code Editor | VS Code (recommended) |
| Node.js | Optional — only needed for the CLI/build approach |
| Internet | Required for CDN approach |

> ✅ **For this Hello World, no installation is required** — we use the TailwindCSS CDN.

---

## 4. Installation & Setup Instructions

### Option A — CDN (Beginner-friendly ✅ used in this project)

Just add one `<script>` tag to your HTML `<head>`:

```html
<script src="https://cdn.tailwindcss.com"></script>
```

That's it. You can now use all Tailwind utility classes in your HTML file.

### Option B — Via npm (for production projects)

```bash
# Step 1: Initialize a Node project
npm init -y

# Step 2: Install Tailwind
npm install -D tailwindcss

# Step 3: Create Tailwind config
npx tailwindcss init

# Step 4: Add to tailwind.config.js — tell Tailwind where your HTML files are
# content: ["./src/**/*.{html,js}"]

# Step 5: Create input CSS file (input.css)
# @tailwind base;
# @tailwind components;
# @tailwind utilities;

# Step 6: Build your CSS
npx tailwindcss -i ./input.css -o ./output.css --watch
```

Then link `output.css` in your HTML:

```html
<link href="./output.css" rel="stylesheet">
```

---

## 5. Minimal Working Example

**What it does:**
Renders a styled card on a gradient background. The card contains a heading, a description, feature pills, and a button. When the button is clicked, it changes color and text to confirm interactivity.

**File:** `tailwind-hello-world/index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Hello TailwindCSS</title>
  <!-- TailwindCSS via CDN — no install needed -->
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="min-h-screen bg-gradient-to-br from-indigo-50 to-purple-100
             flex items-center justify-center">

  <!-- Card container -->
  <div class="bg-white rounded-2xl shadow-xl p-10 max-w-md w-full text-center">

    <!-- Badge -->
    <span class="inline-block bg-indigo-100 text-indigo-700 text-xs
                 font-semibold px-3 py-1 rounded-full mb-4 uppercase">
      Capstone Project
    </span>

    <!-- Heading -->
    <h1 class="text-4xl font-extrabold text-gray-800 mb-3">
      Hello, TailwindCSS! 👋
    </h1>

    <!-- Description -->
    <p class="text-gray-500 text-base leading-relaxed mb-6">
      Styled using only utility classes — no custom CSS written.
    </p>

    <!-- Interactive button: swaps color class on click -->
    <button
      onclick="this.textContent='🎉 It works!';
               this.classList.replace('bg-indigo-600','bg-green-500')"
      class="bg-indigo-600 hover:bg-indigo-700 text-white font-semibold
             py-3 px-8 rounded-xl transition-colors duration-200">
      Click Me
    </button>

  </div>
</body>
</html>
```

**Expected output:**
A centered white card on a purple-indigo gradient page. Clicking the button changes it to green and shows "🎉 It works!"

**Key Tailwind classes explained:**

| Class | What it does |
|-------|-------------|
| `bg-gradient-to-br` | Background gradient going bottom-right |
| `from-indigo-50 to-purple-100` | Gradient colour stops |
| `flex items-center justify-center` | Centers content on both axes |
| `rounded-2xl` | Large rounded corners |
| `shadow-xl` | Large box shadow |
| `text-4xl font-extrabold` | Large, heavy heading text |
| `hover:bg-indigo-700` | Darker background on mouse hover |
| `transition-colors duration-200` | Smooth colour animation |

---

## 6. AI Prompt Journal

### Prompt 1

**Prompt used:**
> "Give me a step-by-step guide to use TailwindCSS in a plain HTML file for beginners. No build tools."

**Link:** [ai.moringaschool.com](http://ai.moringaschool.com)

**AI response summary:**
The AI explained the CDN approach clearly — just add a script tag and start using classes. It listed the most common utility classes for layout, spacing, and typography with examples.

**Evaluation:** Very helpful. It removed the intimidation of setup and let me focus on learning the classes themselves. Saved at least 30 minutes of reading docs.

---

### Prompt 2

**Prompt used:**
> "What are the most important TailwindCSS utility classes a beginner should know? Group them by category."

**Link:** [ai.moringaschool.com](http://ai.moringaschool.com)

**AI response summary:**
The AI grouped classes into Layout (`flex`, `grid`), Spacing (`p-`, `m-`), Typography (`text-`, `font-`), Colours (`bg-`, `text-`), and Effects (`shadow-`, `rounded-`). This gave me a mental map of how Tailwind is organised.

**Evaluation:** Extremely useful as a reference. I used this to pick classes for the Hello World card without guessing.

---

### Prompt 3

**Prompt used:**
> "Write a Hello World card component using TailwindCSS with a button that changes colour when clicked. Use only HTML and the CDN."

**Link:** [ai.moringaschool.com](http://ai.moringaschool.com)

**AI response summary:**
The AI produced a working HTML file with a styled card and an `onclick` handler using `classList.replace()` to swap Tailwind colour classes dynamically.

**Evaluation:** The code worked on first try. The use of `classList.replace()` was something I hadn't thought of — a neat Tailwind-specific trick for dynamic styling without writing extra JavaScript.

---

### Prompt 4

**Prompt used:**
> "I'm getting an error where my Tailwind hover classes don't work. What could be wrong?"

**Link:** [ai.moringaschool.com](http://ai.moringaschool.com)

**AI response summary:**
The AI explained that when using the CDN, hover variants work automatically. For the npm build approach, you need to ensure the `content` field in `tailwind.config.js` correctly points to your HTML/JS files, or Tailwind's purge will remove unused classes including hover states.

**Evaluation:** Helped me understand a common gotcha that would have been confusing to debug alone. Prevented a lot of wasted time.

---

## 7. Common Issues & Fixes

### Issue 1: Classes not applying

**Problem:** Added Tailwind classes to HTML but nothing changed.

**Cause:** Forgot to include the CDN script tag.

**Fix:**
```html
<!-- Add this inside <head> -->
<script src="https://cdn.tailwindcss.com"></script>
```

---

### Issue 2: Hover/Focus classes not working (npm build)

**Problem:** `hover:bg-blue-500` has no effect after npm build.

**Cause:** Tailwind's purge removes classes it doesn't see referenced in the `content` paths.

**Fix:** Update `tailwind.config.js`:

```javascript
module.exports = {
  content: ["./src/**/*.{html,js}"], // ← make sure this matches your file paths
  theme: { extend: {} },
  plugins: [],
}
```

**Reference:** [StackOverflow – Tailwind hover not working](https://stackoverflow.com)

---

### Issue 3: `npx tailwindcss` command not found

**Problem:** Running `npx tailwindcss init` throws "command not found."

**Cause:** Node.js not installed, or npm not available.

**Fix:** Install Node.js from [nodejs.org](https://nodejs.org), then re-run.

---

### Issue 4: Dynamic classes added via JavaScript don't style

**Problem:** Adding a class like `text-red-500` via `element.classList.add()` doesn't work in production build.

**Cause:** Tailwind doesn't scan JS strings for class names during purge.

**Fix:** Use `classList.replace('old-class', 'new-class')` where both classes already exist in your HTML — or safelist them in config:

```javascript
safelist: ['bg-green-500', 'bg-red-500']
```

---

### Peer Testing Notes

Tested with a classmate who followed the guide from scratch on a Windows machine using VS Code. They successfully rendered the Hello World card using the CDN approach with no issues. Feedback received: the class explanation table was especially helpful for understanding what each utility does at a glance.

---

## 8. References

| Resource | Link |
|----------|------|
| Official TailwindCSS Docs | https://tailwindcss.com/docs |
| Tailwind CDN Setup | https://tailwindcss.com/docs/installation/play-cdn |
| Tailwind Cheat Sheet | https://nerdcave.com/tailwind-cheat-sheet |
| Tailwind YouTube Crash Course (Traversy Media) | https://www.youtube.com/watch?v=dFgzHOX84xQ |
| Tailwind Components Library | https://tailwindui.com/components |
| Node.js Download | https://nodejs.org |

---

*Document prepared as part of Moringa School GenAI Capstone — Week 1.*
