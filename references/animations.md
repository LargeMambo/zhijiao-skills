# 动效参考 — 仅在重点页面使用

**原则：动效是工具，不是装饰。** 滥用动效会分散学生注意力。
本文件规定哪些场景可以使用动效，以及具体的 HTML attribute 写法。

---

## 使用场景与动效对应表

| 布局 | 场景 | 动效 | 实现方式 |
|---|---|---|---|
| L01 封面 | 课题引入，营造氛围 | 粒子星空背景 | `data-fx="particles"` on `<section>` |
| L02 学习目标 | 目标逐条出现，引导聚焦 | 列表项依次淡入 | `data-anim="fade-in"` + `data-delay` |
| L03 新知引入 | 抛出问题，制造期待 | 问题卡片3D翻转 | `data-anim="flip-in"` on `.intro-question` |
| L05 步骤分解 | 步骤依次展示，节奏控制 | 步骤卡片依次淡入 | `data-anim="fade-in"` + `data-delay` 递增 |
| L06 例题精讲 | 解题步骤逐步揭示 | 解析行逐行滑入 | `data-anim="slide-in"` + `data-delay` |
| L08 互动问答 | 举手动作引起注意 | 举手 emoji 弹跳 | `data-anim="bounce"` on `.raise-hand-emoji` |
| L11 记忆强化 | 关键词视觉冲击 | 关键词弹跳高亮 | `data-anim="bounce-highlight"` |
| L12 课堂收尾 | 鼓励、奖励感 | Canvas 彩纸雨 | `data-fx="confetti"` on `<section>` |
| 其他所有页面 | 默认进场 | 简单淡入 | `data-anim="fade-in"` on `<section>` |

---

## 动效 attribute 详解

### `data-anim` — CSS/JS 动画（元素级）

作用在 **元素** 上，控制该元素的入场动画。

| 值 | 效果 | 适用元素 |
|---|---|---|
| `fade-in` | 透明度 0→1，轻柔淡入 | 所有元素，默认动效 |
| `flip-in` | 绕 Y 轴3D翻转入场 | 卡片、问题框 |
| `slide-in` | 从左侧滑入 | 解题步骤、列表项 |
| `bounce` | 弹跳出现 | emoji、强调元素 |
| `bounce-highlight` | 弹跳 + 背景色闪烁 | 关键词、记忆点 |
| `zoom-in` | 从中心缩放出现 | 标题、重要数字 |

配合 `data-delay="0.3"` 设置延迟（单位：秒），实现逐项出现效果。

**示例：**
```html
<li data-anim="slide-in" data-delay="0.2">第一条要点</li>
<li data-anim="slide-in" data-delay="0.5">第二条要点</li>
<li data-anim="slide-in" data-delay="0.8">第三条要点</li>
```

### `data-fx` — Canvas 特效（页面级）

作用在 **`<section>`** 上，为整个页面添加画布背景特效。
**仅用于 L01 封面和 L12 收尾**，其他页面不使用。

| 值 | 效果 |
|---|---|
| `particles` | 漂浮粒子星空（夜空感，适合封面） |
| `confetti` | 彩纸从天而降（庆祝感，适合收尾） |

**示例：**
```html
<section class="slide slide-cover" data-fx="particles">
  ...
</section>
```

---

## 禁止使用的动效场景

以下情况 **不得** 使用动效，以保证课堂专注度：

- 每一页都有 `data-fx` 全屏特效（除封面和收尾外）
- 同一页面有超过 3 个不同的 `data-anim` 类型
- 纯文字说明页、步骤密集的计算页
- 知识小结页（L10）——学生需要专注记笔记
