# 🎙️ Unprepared

A lightweight, single-file web app for spontaneous speaking practice and impromptu drills.

## 🚀 Quick Deploy

You can host this static file for free in seconds:

* **[GitHub Pages](https://pages.github.com/):** Go to your repo **Settings** ➔ **Pages**, select the `main` branch and `/ (root)` folder, and click **Save**.
* **Cloudflare Pages / Netlify / Vercel:** Import your repository, leave the build command blank, and deploy from the root directory.

> **Important:** Make sure your main app file is named `index.html` in the root of your repository so web servers recognize it as the homepage.

---

## 🛠️ Quick Customization

Everything lives inside `index.html`. Open it up to customize:

| What to change | Where to look |
|---|---|
| ✏️ **Spontaneous Topics** | The `CATS` object in the script |
| 🎓 **Scholarly Concepts** | The `SCHOL` array in the script |
| 🎨 **Theme Colors** | The `:root[data-theme=...]` blocks in the CSS |
| 🎰 **Spin Duration** | `DUR=5000` (milliseconds) in the spin handler |

---

## 📄 License

Distributed under the MIT License.
