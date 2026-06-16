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
- 配色主题（见下方主题列表，默认"暖橙"）
- 视觉风格（默认"标准"，可选"极简"/"插画风"/"高对比"）
- 预计幻灯片数量（默认根据课时推算：40分钟课 ≈ 15-20 页）

### Step 2 — 规划页面结构

按以下顺序规划每张幻灯片，根据课程复杂度灵活增减：

1. 课题封面（L01）— 必须
2. 学习目标（L02）— 必须
3. 情境导入/新知引入（L03，1-2页）
4. 新知讲解（L04/L05，按知识点数量决定页数）
5. 例题精讲（L06，每道例题单独一页，含逐步推导）
6. 跟练题组（L07，每组3题，含答案折叠区）
7. 互动问答（L08，穿插）
8. 对比分析（L09，可选，适合"易混淆概念"类课程）
9. 知识小结（L10）— 必须
10. 记忆强化（L11，关键知识点）
11. 课堂收尾（L12）— 必须

规划完成后，输出一张**页面结构清单**给教师确认，格式：
```
第1页：课题封面 [L01]
第2页：学习目标 [L02]
第3页：情境导入 [L03] — "用买馕引入分数概念"
...
```

### Step 3 — 选择布局骨架

每页从以下布局中选择最合适的骨架（参见 `references/layouts.md`）：

| 代号 | 布局名 | 适用场景 |
|---|---|---|
| L01 | 全屏封面 | 课题封面，大标题居中 |
| L02 | 目标清单 | 学习目标，项目符号列表 |
| L03 | 左图右文 | 情境导入，图文并排 |
| L04 | 大标题+正文 | 概念讲解，一个知识点 |
| L05 | 分栏对比 | 两列对比（如正方形vs长方形） |
| L06 | 例题步骤 | 例题，逐行显示推导过程 |
| L07 | 题组练习 | 3道练习题+隐藏答案 |
| L08 | 问答交互 | 提问页，空白等待区 |
| L09 | 卡片对比 | 3-4个知识点横排卡片 |
| L10 | 思维导图 | 用CSS+Flexbox绘制的知识树 |
| L11 | 关键词强化 | 核心词放大+弹跳动效 |
| L12 | 收尾感谢 | 结束页，加油语句 |

### Step 4 — 注入动效

动效只在以下具体场景使用，其余页面一律用简单淡入（`data-anim="fade-in"`）：

**封面动效（L01）：**
根据学科选择 Canvas 背景效果：
- **理科/数学**：WebGL 粒子流（蓝色/橙色粒子漂浮）
- **语文/人文**：CSS 渐变动态背景（缓慢色移）
- **科学/地理**：Canvas 星空/天象背景

```html
<!-- WebGL粒子封面示例 -->
<canvas id="bg-canvas" style="position:absolute;top:0;left:0;width:100%;height:100%;z-index:0"></canvas>
<script>
// 内联WebGL粒子着色器
const vs = `attribute vec2 a_pos; void main(){gl_PointSize=3.0;gl_Position=vec4(a_pos,0,1);}`;
const fs = `precision mediump float; uniform vec4 u_color; void main(){float d=distance(gl_PointCoord,vec2(.5));if(d>.5)discard;gl_FragColor=u_color*(1.-d*2.);}`;
// ... 粒子逻辑内联
</script>
```

**新知引入（L03）：** 卡片3D翻转揭示
```css
.card-flip { transform-style: preserve-3d; transition: transform 0.6s; }
.card-flip.flipped { transform: rotateY(180deg); }
```

**例题推导（L06）：** 逐行滑入显示
```js
// 点击/按键时逐步显示下一步
steps.forEach((el, i) => { el.style.opacity = i===0 ? 1 : 0; });
```

**关键词强化（L11）：** 弹跳高亮 + 计数器
```css
@keyframes bounce { 0%,100%{transform:scale(1)} 50%{transform:scale(1.15)} }
.keyword-bounce { animation: bounce 0.6s ease infinite; }
```

**课堂收尾（L12）：** Canvas confetti 庆祝
```js
// 内联 confetti 粒子系统，约30行JS
function launchConfetti(canvas){ /* ... */ }
```

### Step 5 — 主题与配色

从以下主题中选择一个，替换 `:root` CSS 变量：

| 主题 | 主色 | 辅色 | 背景 | 适用 |
|---|---|---|---|---|
| 🟠 暖橙（默认） | `#e07b39` | `#f5c842` | `#fffdf8` | 数学、小学 |
| 🔵 天蓝 | `#3b82f6` | `#60b5e8` | `#f0f7ff` | 语文、初中 |
| 🟢 草绿 | `#22c55e` | `#86efac` | `#f0fdf4` | 科学、生物 |
| 🟣 民族紫 | `#7c3aed` | `#c084fc` | `#faf5ff` | 历史、人文 |
| ⬛ 高对比黑白 | `#111827` | `#374151` | `#ffffff` | 老旧投影仪 |

```css
:root {
  --color-primary: /* 主色 */;
  --color-secondary: /* 辅色 */;
  --color-bg: /* 背景 */;
  --color-text: #1a1a1a;
  --color-keyword-bg: #e53e3e;
  --color-keyword-text: #fff;
}
```

### Step 6 — 内嵌所有资源

**强制执行，不得使用外链：**

- **SVG 矢量图**：从 `assets/emoji-vectors/` 读取对应 SVG，将 `<svg>` 标签直接 inline 到 HTML 中。若 emoji 不在预置库中，使用 Unicode 字符（📚 ✏️ 🌟 ⭐ ✅ ❌ 🎉 🔢 🧪 🌍）
- **字体**：`system-ui, "Microsoft YaHei", "PingFang SC", sans-serif`（系统字体栈，零依赖）
- **JS 动画**：所有动画逻辑内联到 `<script>` 标签，不引用外部 CDN
- **WebGL 着色器**：`<script type="x-shader/x-vertex">` 内联
- **图片**：如需插图，使用内联 SVG 绘制简单图形（勿用 `<img src="...">`）

### Step 7 — 双语注释（如需）

若教师指定了少数民族语种，在每页底部添加 `<div class="bilingual-bar">`。
参见 `references/minority-languages.md` 中各语种的关键词词库和 HTML 模板。

| 语种 | RTL | 字体 | 注意 |
|---|---|---|---|
| 维吾尔语 ug | 是 | `"Noto Nastaliq Urdu", serif` | 需 `dir="rtl"` |
| 藏语 bo | 否 | `"Noto Serif Tibetan", serif` | 需后备系统字体 |
| 哈萨克语 kk | 是（哈萨克阿拉伯文） | 同维吾尔语 | 需 `dir="rtl"` |
| 蒙古语 mn | 否（传统蒙古文竖排） | `"Noto Sans Mongolian"` | 需 `writing-mode: vertical-lr` |
| 柯尔克孜语 ky | 否（拉丁/西里尔） | 系统字体 | — |

```html
<!-- 双语注释条示例 -->
<div class="bilingual-bar">
  <span class="zh-term">分数</span>
  <span class="minority-term" dir="rtl" lang="ug">كەسر</span>
</div>
```

### Step 8 — 质检并输出

按 `references/checklist.md` 逐项核查，确保：
- [ ] 所有字体大小符合规格（标题 ≥ 3.2rem，正文 ≥ 1.8rem）
- [ ] 没有外链资源（所有 img src / script src / link href 均为 inline 或 data URI）
- [ ] 每页信息聚焦，单页不超过 1 个核心知识点
- [ ] 动效只在规定场景（L01/L03/L06/L11/L12）出现，其余页淡入
- [ ] 键盘导航（← →）/ 触摸滑动 / 圆点点击三种方式均可用
- [ ] ESC 打开幻灯片缩略图总览
- [ ] HTML 文件可在浏览器离线打开并完整显示（Chrome / Edge / Firefox / Safari）
- [ ] 文件大小 < 2MB（理科复杂课件允许 < 5MB）

输出路径：`[课题名称]-课件.html`

### Step 9 — 询问后续

课件生成完毕后，主动询问：
> "课件已生成。需要以下任何一项吗？
> 1. 转换为 PPTX 格式（适合白板一体机/老旧投影仪，部分 3D 动效会转为静态图片）
> 2. 配套教案（Markdown 格式，可打印）
> 3. 配套题库（分层练习题）
> 请告诉我需要哪项，或直接说"都需要"。"

---

## 技术规格速查

| 参数 | 值 |
|---|---|
| 幻灯片尺寸 | 1280×720px（16:9） |
| 标题字号 | `3.2rem`（约 51px，超大字） |
| 副标题字号 | `2.4rem` |
| 正文字号 | `1.8rem`（约 29px），可读性优先 |
| 关键词/题目字号 | `2.4-3rem` |
| 行高 | `1.7`（宽松，便于理解） |
| 关键词标注 | `background: #e53e3e; color: #fff; padding: 0.2em 0.5em; border-radius: 4px` |
| 导航 | 键盘左右箭头 / 点击底部圆点 / 触摸滑动 |
| 总览 | 按 `ESC` 打开缩略图概览（CSS Grid 排列） |
| 答案折叠 | `<details>` 标签，点击展开 |
| 页码显示 | 右下角 `当前页 / 总页数` |

## 布局骨架 HTML 片段

每种布局的最小实现（生成时填充内容）：

### L06 — 例题步骤（逐步揭示）

```html
<section data-layout="L06" data-anim="steps">
  <h2 class="slide-title">例题：<span class="keyword">分数加减</span></h2>
  <div class="steps-container">
    <div class="step" data-step="1">
      <span class="step-num">第①步</span>
      <p>通分，找公分母...</p>
    </div>
    <div class="step hidden" data-step="2">
      <span class="step-num">第②步</span>
      <p>分子相加...</p>
    </div>
    <div class="step hidden" data-step="3">
      <span class="step-num">第③步</span>
      <p>化简结果...</p>
    </div>
  </div>
  <button class="next-step-btn" onclick="revealNextStep(this)">下一步 ▶</button>
</section>
```

### L07 — 跟练题组（答案折叠）

```html
<section data-layout="L07">
  <h2 class="slide-title">随堂跟练</h2>
  <div class="quiz-list">
    <div class="quiz-item">
      <p class="question">1. 1/2 + 1/3 = ?</p>
      <details class="answer-box">
        <summary>查看答案</summary>
        <p>5/6（通分后：3/6 + 2/6 = 5/6）</p>
      </details>
    </div>
    <!-- 重复3题 -->
  </div>
</section>
```

### L10 — 知识小结（思维导图）

```html
<section data-layout="L10">
  <h2 class="slide-title">本课小结</h2>
  <div class="mind-map">
    <div class="mind-center">分数</div>
    <div class="mind-branches">
      <div class="branch">概念：部分与整体</div>
      <div class="branch">读法：分之</div>
      <div class="branch">计算：通分加减</div>
      <div class="branch">应用：生活中的分数</div>
    </div>
  </div>
</section>
```
