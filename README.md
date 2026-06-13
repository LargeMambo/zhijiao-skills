<div align="center">

# Teaching Aid Skills · zhijiao-skills

**AI lesson planning toolkit for volunteer teachers in ethnic minority regions of China (Xinjiang, Tibet, etc.)**

</div>

<div align="center">

[中文](README_CN.md) | **English** | [Français](README_FR.md)

</div>

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-orange)
![Compatible](https://img.shields.io/badge/compatible-Claude%20Code%20%7C%20Universal%20AI-blue)
![License](https://img.shields.io/badge/license-MIT-green)

</div>

---

## What is this?

**zhijiao-skills** is an AI prompt skill pack that helps volunteer teachers create complete lesson materials with a single sentence:

- 📊 **HTML interactive slides** — one file, works offline on any device
- 📑 **PPTX slides** — compatible with whiteboards and old projectors
- 📝 **Lesson plans** (教案) — Markdown format, print-ready
- 📋 **Tiered exercise banks** — in-class quizzes, homework, and unit tests

**Designed specifically for ethnic minority classrooms:**
- ✅ Larger fonts, cleaner layout
- ✅ Slower teaching pace — one core concept per page
- ✅ Animated highlights for key knowledge points (3D flip, bounce, confetti)
- ✅ Generated slides are fully offline — no internet, no software needed
- ✅ Optional minority language annotations (Uyghur, Tibetan, Kazakh, etc.)
- ✅ Three-tier difficulty exercises with a simplified version for struggling students

---

## Installation

### Prerequisites

You need **Claude Code** or another AI tool that supports skill packs.

**Check if Claude Code is installed:**
```bash
claude --version
```
If you see a version number, you're ready.

---

### Option 1 — Download and copy (no coding needed)

1. Click the green **Code** button on this page → **Download ZIP**
2. Unzip the downloaded file — you'll get a folder called `zhijiao-skills`
3. Copy this folder to your Claude Code skills directory:
   - **Windows:** `C:\Users\YourName\.claude\skills\`
   - **Mac/Linux:** `~/.claude/skills/`
4. Open a terminal and type `claude`, then `/skills` to verify installation

---

### Option 2 — Git clone

```bash
cd ~/.claude/skills   # or %USERPROFILE%\.claude\skills on Windows
git clone https://github.com/your-username/zhijiao-skills.git
```

---

### Option 3 — Universal AI tools

This skill pack works with any AI tool:

| Tool | How to use |
|---|---|
| **Claude.ai web** | Upload `SKILL.md` or paste its content as system prompt |
| **ChatGPT / GPT-4** | Paste `SKILL.md` content into System Prompt |
| **Cursor / Windsurf** | Add `SKILL.md` as a project rule file |
| **Local AI (Ollama, etc.)** | Use `SKILL.md` content as system prompt |

---

## Usage

Just describe what you need in natural language — no commands to memorize.

### Examples

**Make an HTML slide deck:**
```
Make a lesson on "Fractions" for 3rd grade math, PEP textbook
```

**Write a lesson plan:**
```
I'm teaching Newton's First Law, 8th grade physics,
my class has mostly Uyghur students — please write a detailed lesson plan
```

**Generate exercises:**
```
Create a homework exercise set for "Addition within 100",
2nd grade math, with basic, intermediate, and advanced levels
```

**Full lesson package:**
```
Next week I'm teaching "The Water Cycle", 4th grade science —
please make a complete package: lesson plan + HTML slides
```

**With minority language annotations:**
```
Make slides for "Telling Time", 2nd grade math,
add small Uyghur annotations next to key vocabulary
```

---

## Features

### HTML Slides

| Feature | Details |
|---|---|
| Fully offline | Single HTML file, copy to USB and use anywhere |
| Keyboard navigation | ← → arrow keys, ESC for slide overview |
| Touch support | Swipe on phones and tablets |
| Keyword highlights | Red background + white text for core concepts |
| Animations | Particle cover, step-by-step example reveals, confetti ending |
| Answer reveal | Click "Show Answer" in practice slides |

### Color Themes

| Theme | Best for |
|---|---|
| 🟠 Warm Orange (default) | Math, elementary school |
| 🔵 Sky Blue | Chinese, English, middle school |
| 🟢 Grass Green | Science, biology, geography |
| ⬛ High Contrast B&W | Old projectors, bright classrooms |

### Minority Language Annotations

| Language | Code | Region |
|---|---|---|
| Uyghur | ug | Xinjiang |
| Tibetan | bo | Tibet, Qinghai |
| Kazakh | kk | Xinjiang |
| Mongolian | mn | Inner Mongolia |
| Kyrgyz | ky | Xinjiang |

Specify in your prompt: `add Uyghur annotations next to key terms`

---

## File Structure

```
zhijiao-skills/
├── SKILL.md                      ← Main skill entry (AI reads this)
├── sub-skills/
│   ├── ppt-html/SKILL.md         ← HTML slide generation
│   ├── ppt-pptx/SKILL.md         ← PPTX slide generation
│   ├── lesson-plan/SKILL.md      ← Lesson plan generation
│   └── quiz-bank/SKILL.md        ← Exercise bank generation
├── assets/
│   ├── template-ethnic.html      ← HTML slide base template
│   └── emoji-vectors/            ← Pre-loaded SVG icons (offline)
├── references/
│   ├── layouts.md                ← 12 classroom layout skeletons
│   ├── themes.md                 ← 4 color themes
│   ├── animations.md             ← Animation usage guidelines
│   ├── minority-languages.md     ← Minority language vocabulary
│   ├── svg-embed-guide.md        ← SVG embedding reference
│   └── checklist.md              ← Output quality checklist
└── README_CN.md / README.md / README_FR.md
```

---

## FAQ

**Q: Do I need programming knowledge?**
A: No. Installation is just copying a folder. Usage is plain natural language conversation.

**Q: Does the generated slide need internet?**
A: The AI needs internet to generate the file, but the finished `.html` file is fully offline.

**Q: Which browsers work?**
A: Chrome, Edge, Firefox, Safari — all work. On older school computers, the latest Chrome or Edge is recommended.

**Q: Are the minority language translations accurate?**
A: Generally accurate, but dialects vary. For critical content, please have a local speaker review it.

---

## Contributing

Issues and pull requests are welcome. Minority language vocabulary contributions are especially appreciated.

---

## License

MIT License .

---

<div align="center">

Built with ❤️ for volunteer teachers · May every lesson light up a child's eyes

</div>
