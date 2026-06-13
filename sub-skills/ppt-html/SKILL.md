---
name: zhijiao-ppt-html
description: >
  生成适合少数民族地区课堂的 HTML 课件（单文件，完全离线，开箱即用）。
  专为疆藏等地区设计：大字体、节奏慢、关键知识点动效突出、可选双语注释。
  由父技能 zhijiao-skills 路由调用，也可直接触发。
---

# HTML 课件生成子技能

## 工作流

### Step 1 — 确认参数

从父技能获取或重新询问：
- 学科、年级、课题、教材版本
- 是否需要少数民族语注释（及语种）
- 配色主题（默认"暖橙"，可选"天蓝"/"草绿"/"高对比黑白"）
- 预计幻灯片数量（默认根据课时推算：40分钟课 ≈ 15-20 页）

### Step 2 — 规划页面结构

按以下顺序规划每张幻灯片：
1. 课题封面（L01）
2. 学习目标（L02）
3. 情境导入/新知引入（L03，1-2页）
4. 新知讲解（L04/L05，按知识点数量决定页数）
5. 例题精讲（L06，每道例题单独一页）
6. 跟练题组（L07，每组3题）
7. 互动问答（L08，穿插）
8. 知识小结（L10）
9. 记忆强化（L11，关键知识点）
10. 课堂收尾（L12）

规划完成后，输出一张**页面结构清单**给教师确认，格式：
```
第1页：课题封面 [L01]
第2页：学习目标 [L02]
第3页：情境导入 [L03] — "用买馕引入分数概念"
...
```

### Step 3 — 复制模板并生成课件

1. 将 `assets/template-ethnic.html` 内容作为基础结构
2. 根据选择的主题，替换 `:root` 中的 CSS 变量（参见 `references/themes.md`）
3. 按页面结构清单，逐页使用 `references/layouts.md` 中的骨架填充内容
4. 动效仅在以下场景注入（参见 `references/animations.md`）：
   - L01 封面：WebGL 粒子背景
   - L03 新知引入：卡片3D翻转
   - L06 例题揭晓：逐行滑入
   - L11 记忆强化：弹跳高亮
   - L12 收尾：Canvas confetti
5. 其余页面使用简单淡入（`data-anim="fade-in"`）

### Step 4 — 内嵌所有资源

**强制执行，不得使用外链：**

- **SVG 矢量图**：从 `assets/emoji-vectors/` 读取对应 SVG 文件，将 `<svg>` 标签直接 inline 到 HTML 中。若需要课件中没有的 emoji，使用 Unicode 字符代替（如 📚 ✏️ 🌟 ⭐ ✅ ❌ 🎉）
- **字体**：使用 `system-ui, "Microsoft YaHei", sans-serif` 作为字体栈（系统字体，零依赖），无需 @font-face 内嵌
- **JS 动画库**：将 Motion One 代码内联到 `<script>` 标签（从 `assets/motion.min.js` 读取）
- **WebGL 着色器**：`<script type="x-shader/x-vertex">` 内联

### Step 5 — 双语注释（如需）

若教师指定了少数民族语种，在每页底部添加 `<div class="bilingual-bar">`。
参见 `references/minority-languages.md` 中各语种的关键词词库和 HTML 模板。

维吾尔语注意事项：RTL 文本，需添加 `dir="rtl"` 属性。

### Step 6 — 质检并输出

按 `references/checklist.md` 逐项核查，确保：
- [ ] 所有字体大小符合规格
- [ ] 没有外链资源（img src、script src、link href 均为 inline 或 data URI）
- [ ] 每页信息聚焦，核心知识点清晰
- [ ] 动效仅在规定场景出现
- [ ] HTML 文件可在浏览器离线打开并完整显示

输出路径：`[课题名称]-课件.html`

### Step 7 — 询问是否转换为 PPTX

课件生成完毕后，主动询问：
> "课件已生成。如果您的教室设备（如白板一体机、老式投影仪）只支持 PowerPoint 格式，
> 我可以将其转换为 PPTX 文件，但部分 3D 动效会转为静态图片。需要转换吗？"

如需转换，路由到 `sub-skills/ppt-pptx/SKILL.md` 并传入已生成的 HTML 内容。

## 技术规格速查

| 参数 | 值 |
|---|---|
| 幻灯片尺寸 | 1280×720px（16:9） |
| 标题字号 | `3.2rem`（约 51px） |
| 正文字号 | `1.8rem`（约 29px），可读性优先 |
| 题目/关键词字号 | `2.4-3rem` |
| 关键词标注 | `background: #e53e3e; color: #fff; padding: 0.2em 0.5em; border-radius: 4px` |
| 导航 | 键盘左右箭头 / 点击底部圆点 / 触摸滑动 |
| 概览 | 按 `ESC` 键打开缩略图概览 |
