<div align="center">

# Teaching Aid Skills · zhijiao-skills

**AI lesson planning toolkit for volunteer teachers in ethnic minority regions of China (Xinjiang, Tibet, etc.)**

</div>

<div align="center">

[简体中文](README_CN.md) | **English** | [Français](README_FR.md) | [བོད་སྐད](README_BO.md) | [ئۇيغۇرچە](README_UG.md)

</div>

<div align="center">

![Version](https://img.shields.io/badge/version-1.4.1-orange)
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
If you see a version number, you're ready. If not, see the [Claude Code getting started guide](https://docs.anthropic.com/en/docs/claude-code/getting-started).

---

### Recommended AI tools

| Tool | Rating | Notes |
|---|---|---|
| **Claude Code** (CLI) | ⭐⭐⭐⭐⭐ Best | Native `/skills` system, trigger with one sentence |
| **OpenAI Codex / ChatGPT** | ⭐⭐⭐⭐ Good | Paste `SKILL.md` as System Prompt |
| **Claude.ai web** | ⭐⭐⭐⭐ Good | Upload `SKILL.md` to the conversation |
| **Cursor / Windsurf** | ⭐⭐⭐ Works | Add `SKILL.md` as `.cursorrules` |
| **Local AI (Ollama, etc.)** | ⭐⭐⭐ Works | Quality depends on model capability |

---

### Option 1 — Download and copy (no coding needed)

1. Click the green **Code** button on this page → **Download ZIP**
2. Unzip the downloaded file — you'll get a folder called `zhijiao-skills`
3. Copy this folder to your Claude Code skills directory:
   - **Windows:** `C:\Users\YourName\.claude\skills\`
   - **Mac/Linux:** `~/.claude/skills/`
4. Open a terminal and type `claude`, then `/skills` to verify installation

---

### Option 2 — npm install (recommended for developers)

> Requires [Node.js](https://nodejs.org/) 18+ (npm is included with Node.js).

```bash
# Install Claude Code if you haven't already
npm install -g @anthropic-ai/claude-code

# Navigate to the skills directory
cd ~/.claude/skills          # Mac/Linux
# cd %USERPROFILE%\.claude\skills   # Windows

# Clone this skill pack
git clone https://github.com/LargeMambo/zhijiao-skills.git

# Verify inside Claude Code
claude
/skills
```

> **Compatibility:** Claude Code installs via npm and supports Node.js 18+ on Windows, macOS, and Linux. The skill pack itself is plain text — no `npm install` needed for the skills themselves.

---

### Option 3 — Git clone

```bash
cd ~/.claude/skills   # or %USERPROFILE%\.claude\skills on Windows
git clone https://github.com/LargeMambo/zhijiao-skills.git
```

---

### Option 4 — Universal AI tools

This skill pack works with any AI tool:

| Tool | How to use |
|---|---|
| **Claude.ai web** | Upload `SKILL.md` or paste its content as system prompt |
| **ChatGPT / Codex** | Paste `SKILL.md` content into System Prompt |
| **Cursor / Windsurf** | Add `SKILL.md` as a project rule file (`.cursorrules`) |
| **Local AI (Ollama, etc.)** | Use `SKILL.md` content as system prompt |

> For best results with generic AI tools, also attach the files in `references/`.

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
├── README_CN.md                  ← Simplified Chinese
├── README.md                     ← English (this file)
├── README_FR.md                  ← French
├── README_BO.md                  ← Tibetan
└── README_UG.md                  ← Uyghur
```

---

## FAQ

<details>
<summary><strong>Q: Do I need programming knowledge?</strong></summary>

No. Installation is just copying a folder. Usage is plain natural language conversation.

</details>

<details>
<summary><strong>Q: Does the generated slide need internet?</strong></summary>

The AI needs internet to generate the file, but the finished `.html` file is fully offline — copy it to a USB drive and use it anywhere.

</details>

<details>
<summary><strong>Q: Which browsers work?</strong></summary>

Chrome, Edge, Firefox, Safari — all work. On older school computers, the latest Chrome or Edge is recommended (both free).

</details>

<details>
<summary><strong>Q: Are the minority language translations accurate?</strong></summary>

Generally accurate, but dialects vary. For critical content, please have a local speaker review it.

</details>

<details>
<summary><strong>Q: Can I edit the generated slides?</strong></summary>

Yes. HTML slides are standard web files — open them in any text editor (VS Code, Notepad) to modify.

</details>

<details>
<summary><strong>Q: How do I use this with ChatGPT or Codex?</strong></summary>

Copy the full content of `SKILL.md` and paste it as the System Prompt. For best results, also attach the files in `references/`.

</details>

<details>
<summary><strong>Q: How do I update the skill pack?</strong></summary>

If you used Git: run `git pull` inside the `zhijiao-skills` folder. If you downloaded a ZIP: delete the old folder and re-download.

</details>

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
