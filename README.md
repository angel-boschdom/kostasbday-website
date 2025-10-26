# 🥳 Kostas' 32nd Birthday — Party Web App  
**Website:** https://kostasbday.online  
**Event:** Thessaloniki, Greece — 2025  
**Guests:** ~70 people, all in their 30s  
**Theme:** Fun • Interactive • Slightly Drunk • Very Greek 🇬🇷  

---

## 🎯 Overview

Welcome to **Kostas' 32nd Birthday Bash**, a web app built purely with **HTML, CSS, and JavaScript** — **no backend, no database, no local storage**.  
Everything runs client-side and resets on refresh. Host it statically on Vercel, Netlify, or GitHub Pages.

**Games included:**
1. **🧠 Kosta-Quiz** — Hardcoded trivia about Kostas. Final score shown at the end (e.g., `7/10`).  
2. **🎰 Kosta-Roulette** — A roulette of dares and party challenges.  
3. **🍸 Kosta-Shots** — Dual name spinners with a center **Spin!** button to randomly match two people for a shot.

---

## 🌈 Design Goals

| Aspect | Description |
|--------|--------------|
| **Mood** | Nightclub + humor + mischief |
| **Color palette** | Dark background (black/deep navy) with neon accents (pink, purple, lime, cyan) |
| **Font** | Bold sans-serif (Poppins / Montserrat / Bebas Neue) |
| **Style** | Minimal UI, glowing buttons, confetti, smooth animations |
| **Tone** | Playful, cheeky, inclusive |
| **Device** | Optimized for mobile browsers |
| **Storage** | None (no cookies, no localStorage, no DB) |

---

## 🏠 Pages & Structure

### `/index.html` — Home Page
**Purpose:** Entry hub for the three games.

**Sections:**
- Title: `Kostas' 32nd Birthday Bash 🎉`  
- Subtitle: `Play. Drink. Survive.`  
- Three glowing buttons:
  - 🧠 **Kosta-Quiz**
  - 🎰 **Kosta-Roulette**
  - 🍸 **Kosta-Shots**
- Optional animated background (lights/confetti).
- Footer: `Made with ❤️ for Kostas & Friends — Thessaloniki 2025`

---

### `/quiz.html` — 🧠 Kosta-Quiz
**Goal:** See how well guests know Kostas.

**Gameplay:**
- 10 multiple-choice questions hardcoded in JavaScript.
- Users answer sequentially.
- At the end, show result as `X/10` with playful feedback.
- No leaderboard or persistence.

**Example questions:**
- `What’s Kostas’ go-to drink?`
- `Which dance move is officially banned at his parties?`
- `What city did Kostas once get lost in for 6 hours?`
- `What’s his most used phrase after 2 AM?`

**Implementation notes:**
- Represent questions as an array of objects and compute the final score.

    const questions = [
      { q: "What’s Kostas’ favorite drink?", choices: ["Whiskey", "Gin Tonic", "Ouzo", "Beer"], answer: 2 },
      // ...
    ];

- Sample feedback bands:
  - `0–3: Do you even know Kostas? 😅`
  - `4–7: You’re part of the crew 🍻`
  - `8–10: You’re basically his twin 🔥`

---

### `/roulette.html` — 🎰 Kosta-Roulette
**Goal:** Spin the wheel of party dares.

**Gameplay:**
- Colorful roulette wheel with 8–12 slices.
- Each slice holds a challenge from a predefined list.
- On spin, the wheel animates (≈3 seconds) and lands randomly.
- Display the winning challenge in large type with emoji and confetti.

**Example challenges:**
- `Take a shot with someone new 🍸`
- `Give a toast to Kostas 🥂`
- `Sing a line from a love song 🎤`
- `Teach someone a Greek phrase 🇬🇷`
- `Do your best DJ drop 📀`

**Implementation notes:**
- Use CSS rotation or a `<canvas>` wheel.
- Fairness: pick a random index and animate to it.
- Controls: `SPIN 🎡` and `Reset 🔁`.

---

### `/shots.html` — 🍸 Kosta-Shots
**Goal:** Randomly pair two guests to take a shot together.

**Layout (important):**
- **Left column:** A **name spinner** (vertical or slot-style), cycling through the hardcoded guest list.
- **Center:** A large **`Spin!`** button.
- **Right column:** Another **name spinner** identical to the left one.

**Interaction & Behavior:**
- When the **`Spin!`** button is pressed:
  - **Both** name spinners start rapidly cycling names, slot-machine style.
  - After 3–5 seconds, they decelerate and **settle** on two **distinct** random names.
  - Show a celebratory message centered below, like:
    - `🎉 Take a shot! 🥃`
    - `Alex & Maria — Time for a shot!`
  - Trigger confetti and an optional “win” sound, like a slot machine jackpot.

**Implementation notes:**
- Names are hardcoded in a JS array; keep everything in memory.

    const guests = [
      "Kostas", "Maria", "Alex", "Nikos", "Eleni", "Giannis",
      "Christina", "George", "Dimitra", "Sofia"
      // ...add up to ~70
    ];

- Ensure **distinct** picks for the two spinners (re-roll if identical).
- Use requestAnimationFrame or CSS animations for smooth slot motion.
- Provide a `Spin Again` button or reuse the center **`Spin!`** to re-run.

---

## 🧩 Tech Stack

| Layer | Tool | Purpose |
|--------|------|----------|
| **Frontend** | HTML5, CSS3, Vanilla JavaScript | Entire app |
| **Frameworks** | None (optional Tailwind via CDN) | Styling convenience |
| **Storage/Backend** | None | Static-only |
| **Hosting** | Vercel / Netlify / GitHub Pages | Zero-config |
| **Assets** | Lightweight SVGs, emojis, optional sounds | Party vibes |
| **Animations** | CSS keyframes + JS timers/RAF | Smooth mobile UX |

---

## ⚙️ Folder Structure

    /kostasbday.online
    │
    ├── index.html
    ├── quiz.html
    ├── roulette.html
    ├── shots.html
    │
    ├── /assets
    │   ├── /images
    │   ├── /icons
    │   └── /sounds
    │
    ├── /js
    │   ├── quiz.js
    │   ├── roulette.js
    │   └── shots.js
    │
    ├── /css
    │   ├── style.css
    │   └── animations.css
    │
    └── README.md

---

## 🧃 UX Enhancements (Optional)

- Glow hover effects on buttons ✨  
- Confetti bursts on quiz finish, roulette win, and shots match 🎉  
- Optional background DJ loop (muted by default) 🎧  
- Easter egg hidden in the footer  
- Motion-reduced mode (respect `prefers-reduced-motion`)

---

## 🚀 Deployment

1. No build step required: static HTML/CSS/JS.  
2. Deploy to Netlify, Vercel, or GitHub Pages (drag & drop or CLI).  
3. Point `kostasbday.online` to your host via DNS (CNAME).  
4. Done — everything runs in the browser. 🍾

---

## 🔐 Privacy & Simplicity

- No tracking, cookies, or saved data.  
- No logins or forms.  
- Refresh to reset — pure fun.

---

## 🍹 Credits

- **For:** Kostas’ 32nd Birthday, Thessaloniki 2025  
- **Concept & Direction:** Angel + Friends  
- **Tech:** HTML, CSS, Vanilla JS  
- **Spirit:** Ouzo, laughter, and 70 Greek legends  

---

> “Spin, quiz, and drink responsibly. Kostas is watching.” 👀