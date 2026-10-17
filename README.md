<div align="center">

# 🎤 Unprepared

**Spin a topic. Start the timer. Speak.**

A tiny speaking-practice app for thinking on your feet, with two modes, ten dark themes and zero dependencies.

![HTML5](https://img.shields.io/badge/HTML5-single_file-e34f26?style=flat-square&logo=html5&logoColor=white)
![No build](https://img.shields.io/badge/build-none-7fc4f0?style=flat-square)
![Dependencies](https://img.shields.io/badge/dependencies-0-success?style=flat-square)
![Theme](https://img.shields.io/badge/theme-dark-0c1218?style=flat-square)

</div>

---

## ✨ Features

- 🧠 **Spontaneous mode:** a short, random topic from the category you choose, plus a quick speaking timer. Minimal prep.
- 🔍 **Scholarly mode:** a deeper concept (for example *The compromise effect*), a research timer, then a separate speech timer.
- 🎰 **Slot-machine spin:** topics flash past and slow down, then land on one after exactly 5 seconds.
- 🗂️ **9 categories:** General, Personal finance, Entrepreneurship, Startups, Tech / AI, Fitness, Nutrition, Productivity and History.
- ⏱️ **Custom timers:** set your own spontaneous, research and speech durations. A soft beep marks the end.
- 🎨 **10 dark themes:** Arctic (default), Ember, Midnight, Plum, Ocean, Graphite, Crimson, Forest, Sunset and Lavender.
- 💾 **Remembers your settings** (timers and theme) in your browser.
- 📱 **Responsive**, with safe-area support for phones.

---

## 🧭 How it works

```mermaid
flowchart TD
    A([Open the app]) --> B{Pick a mode}
    B -->|Spontaneous| C[Choose a category]
    B -->|Scholarly| D[Concept pool]
    C --> E[Press Spin]
    D --> E
    E --> F[Topics cycle and slow down for 5 seconds]
    F --> G[Final topic lands]
    G --> H{Mode?}
    H -->|Spontaneous| I[Start the speaking timer]
    H -->|Scholarly| J[Start the research timer]
    J --> K[Start the speech timer]
    I --> L([Beep: time is up])
    K --> L
    L --> E
```

### ⏲️ Timer states

```mermaid
stateDiagram-v2
    [*] --> Ready
    Ready --> Spinning: Press Spin
    Spinning --> Ready: Topic lands after 5s
    Ready --> Speaking: Start timer (Spontaneous)
    Ready --> Researching: Start research (Scholarly)
    Researching --> TimesUp: Research ends
    TimesUp --> Speaking: Start speech timer
    Speaking --> Done: Time ends
    Researching --> Ready: Stop
    Speaking --> Ready: Stop
    Done --> Ready: Spin again
```

---

## 🚀 Quick start

No install and no build step. The whole app is one file.

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/unprepared.git
cd unprepared

# 2. Open it in your browser
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

> 💡 If your file is called `unprepared.html`, rename it to `index.html` so hosting platforms serve it automatically.

---

## 🌐 Deploy for free

Because it is a static site, it works on any static host.

```mermaid
flowchart LR
    R[(GitHub repo)] --> P1[GitHub Pages]
    R --> P2[Cloudflare Pages]
    R --> P3[Netlify]
    R --> P4[Vercel]
    P1 --> W((Live site))
    P2 --> W
    P3 --> W
    P4 --> W
```

**GitHub Pages:** go to *Settings → Pages*, choose the `main` branch and the `/ (root)` folder, then save.
**Cloudflare Pages, Netlify or Vercel:** import the repo and leave the build command empty. The output directory is the repo root.

---

## 🛠️ Customize

Everything lives in `index.html`.

| What | Where to look |
|---|---|
| ✏️ Spontaneous topics | the `CATS` object in the script |
| 🎓 Scholarly concepts | the `SCHOL` array in the script |
| 🎨 Theme colours | the `:root[data-theme=...]` blocks in the CSS |
| 🧊 Default theme | the first `:root{...}` block |
| 🎰 Spin duration | `DUR=5000` (milliseconds) in the Spin handler |
| 🔗 Handle and link | search for `thvividx` |

### Add a new category

```js
"Travel": ["✈️", ["Lost Luggage", "Window Seat", "Street Maps", "Jet Lag"]],
```

### Add a new theme

```css
:root[data-theme=mint]{--bg:#0b1512;--glow1:#14402f;--glow2:#12303a;--accent:#6ee7b7;--ink:#04201a;--text:#e6f8f0;--muted:#8fb3a6;--panel:#101c18}
```

Then add `["mint","#6ee7b7","#12303a","Mint"]` to the `THEMES` array so it shows up in settings.

---

## 🗂️ Project structure

```mermaid
flowchart TB
    root["📁 unprepared"] --> idx["📄 index.html (HTML, CSS and JS)"]
    root --> rd["📄 README.md"]
    root --> gi["📄 .gitignore"]
```

---

## 🧰 Built with

- Vanilla HTML, CSS and JavaScript
- [Fraunces](https://fonts.google.com/specimen/Fraunces) and [Outfit](https://fonts.google.com/specimen/Outfit) from Google Fonts
- Web Audio API for the end-of-timer beep
- `localStorage` for saved settings

---

## 👤 Author

Made by [@thvividx](https://instagram.com/thvividx)

---

## 📄 License

Add a license of your choice, for example [MIT](https://choosealicense.com/licenses/mit/).
