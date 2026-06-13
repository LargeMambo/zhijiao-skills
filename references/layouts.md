# 布局骨架参考 — 12 种课堂专用布局

本文件提供 12 种布局的 HTML 骨架，供 ppt-html 子技能按需填充。
所有布局使用同一套 CSS 变量（定义在 template-ethnic.html 的 `:root` 中）。

---

## L01 — 课题封面

```html
<section class="slide slide-cover" data-fx="particles">
  <div class="cover-content">
    <div class="subject-tag">📚 [学科] · [年级]</div>
    <h1 class="cover-title">[课题名称]</h1>
    <div class="cover-meta">
      <span>教材版本：[版本]</span>
      <span>课时：第X课时</span>
    </div>
    <div class="teacher-info">执教：[教师姓名（可选）]</div>
  </div>
</section>
```

---

## L02 — 学习目标

```html
<section class="slide slide-objectives">
  <h2 class="slide-title">🎯 本节课学习目标</h2>
  <ul class="objective-list">
    <li data-anim="fade-in" data-delay="0.2">
      <span class="obj-num">①</span>
      <span class="obj-text">[目标一]</span>
    </li>
    <li data-anim="fade-in" data-delay="0.5">
      <span class="obj-num">②</span>
      <span class="obj-text">[目标二]</span>
    </li>
    <li data-anim="fade-in" data-delay="0.8">
      <span class="obj-num">③</span>
      <span class="obj-text">[目标三]</span>
    </li>
  </ul>
</section>
```

---

## L03 — 新知引入（情境导入）

```html
<section class="slide slide-intro">
  <div class="intro-image-area">
    <!-- 内嵌 SVG 或 Unicode emoji 大图 -->
    <div class="big-emoji" aria-hidden="true">🌄</div>
  </div>
  <div class="intro-question" data-anim="flip-in">
    <span class="question-label">💭 想一想</span>
    <p class="question-text">[情境问题，一句话，≤20字]</p>
  </div>
</section>
```

---

## L04 — 概念讲解（左图右文）

```html
<section class="slide slide-concept">
  <h2 class="slide-title">[概念名称]</h2>
  <div class="concept-layout">
    <div class="concept-visual">
      <!-- 内嵌 SVG 示意图 或 大 emoji -->
      <div class="visual-placeholder">[SVG或emoji]</div>
    </div>
    <div class="concept-text">
      <p class="concept-definition">
        <span class="keyword-highlight">[关键词]</span>
        是指[定义，语言简洁]
      </p>
      <ul class="concept-points">
        <li>[要点1]</li>
        <li>[要点2]</li>
      </ul>
    </div>
  </div>
</section>
```

---

## L05 — 步骤分解（横向流程）

```html
<section class="slide slide-steps">
  <h2 class="slide-title">🔢 [操作/方法名称]的步骤</h2>
  <div class="steps-flow">
    <div class="step-card" data-anim="fade-in" data-delay="0.1">
      <div class="step-num">第①步</div>
      <div class="step-content">[步骤描述]</div>
    </div>
    <div class="step-arrow">→</div>
    <div class="step-card" data-anim="fade-in" data-delay="0.3">
      <div class="step-num">第②步</div>
      <div class="step-content">[步骤描述]</div>
    </div>
    <div class="step-arrow">→</div>
    <div class="step-card" data-anim="fade-in" data-delay="0.5">
      <div class="step-num">第③步</div>
      <div class="step-content">[步骤描述]</div>
    </div>
    <!-- 按需增减 step-card + step-arrow -->
  </div>
</section>
```

---

## L06 — 例题精讲

```html
<section class="slide slide-example">
  <div class="example-header">
    <span class="example-badge">📝 例题</span>
    <span class="example-difficulty">⭐⭐ 提升</span>
  </div>
  <div class="example-question">
    <p>[题目内容，字号 2.4rem，可多行]</p>
  </div>
  <div class="example-solution">
    <div class="solution-step" data-anim="slide-in" data-delay="0.3">
      <span class="step-label">解：</span>
      <span class="step-text">[第一步]</span>
    </div>
    <div class="solution-step" data-anim="slide-in" data-delay="0.6">
      <span class="step-text">[第二步]</span>
    </div>
    <div class="solution-step solution-answer" data-anim="slide-in" data-delay="0.9">
      <span class="step-label">∴</span>
      <span class="step-text answer-text">[答案]</span>
    </div>
  </div>
</section>
```

---

## L07 — 跟练题组（3题一组）

```html
<section class="slide slide-practice">
  <h2 class="slide-title">✏️ 跟练一下</h2>
  <div class="practice-list">
    <div class="practice-item">
      <span class="practice-num">1.</span>
      <span class="practice-q">[题目] <span class="diff-tag">⭐</span></span>
      <details class="practice-answer">
        <summary>查看答案</summary>
        <span class="answer-text">[答案及简析]</span>
      </details>
    </div>
    <div class="practice-item">
      <span class="practice-num">2.</span>
      <span class="practice-q">[题目] <span class="diff-tag">⭐⭐</span></span>
      <details class="practice-answer">
        <summary>查看答案</summary>
        <span class="answer-text">[答案及简析]</span>
      </details>
    </div>
    <div class="practice-item">
      <span class="practice-num">3.</span>
      <span class="practice-q">[题目] <span class="diff-tag">⭐⭐⭐</span></span>
      <details class="practice-answer">
        <summary>查看答案</summary>
        <span class="answer-text">[答案及简析]</span>
      </details>
    </div>
  </div>
</section>
```

---

## L08 — 互动问答

```html
<section class="slide slide-interaction">
  <div class="interaction-center">
    <div class="raise-hand-emoji" data-anim="bounce">🙋</div>
    <p class="interaction-prompt">[问题，面向全体，开放性]</p>
    <p class="interaction-hint">💡 提示：[思考方向提示]</p>
  </div>
  <div class="think-time">
    <span>思考时间：</span>
    <span class="timer-placeholder">⏱ [X] 秒</span>
  </div>
</section>
```

---

## L09 — 小组活动

```html
<section class="slide slide-group">
  <h2 class="slide-title">👥 小组活动</h2>
  <div class="activity-card">
    <div class="activity-task">
      <p class="task-title">🎯 任务：</p>
      <p class="task-desc">[活动要求，语言简洁]</p>
    </div>
    <div class="activity-rules">
      <p>⏱ 时间：[X] 分钟</p>
      <p>👨‍👩‍👦 每组：[X] 人</p>
      <p>📋 完成后：[汇报方式]</p>
    </div>
  </div>
</section>
```

---

## L10 — 知识小结（思维导图式）

```html
<section class="slide slide-summary">
  <h2 class="slide-title">📖 本节课小结</h2>
  <div class="mind-map">
    <div class="mind-center">[课题]</div>
    <div class="mind-branches">
      <div class="mind-branch" data-anim="fade-in" data-delay="0.2">
        <span class="branch-label">[要点1]</span>
      </div>
      <div class="mind-branch" data-anim="fade-in" data-delay="0.4">
        <span class="branch-label">[要点2]</span>
      </div>
      <div class="mind-branch" data-anim="fade-in" data-delay="0.6">
        <span class="branch-label">[要点3]</span>
      </div>
    </div>
  </div>
</section>
```

---

## L11 — 记忆强化（关键词爆闪）

```html
<section class="slide slide-memory">
  <h2 class="slide-title">⭐ 记住这一点！</h2>
  <div class="memory-center">
    <div class="memory-keyword" data-anim="bounce-highlight">
      [核心关键词/公式/规律]
    </div>
    <p class="memory-sentence">[一句话记忆口诀或规律总结]</p>
  </div>
</section>
```

---

## L12 — 课堂收尾

```html
<section class="slide slide-ending" data-fx="confetti">
  <div class="ending-content">
    <div class="praise-emoji">🎉</div>
    <h2 class="ending-title">今天学得很棒！</h2>
    <div class="homework-box">
      <p class="homework-title">📝 今日作业</p>
      <p class="homework-content">[作业内容，分层说明]</p>
    </div>
    <p class="ending-quote">[鼓励语，贴近学生文化]</p>
  </div>
</section>
```
