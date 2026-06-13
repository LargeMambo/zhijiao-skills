# 配色主题参考

共 4 套主题，全部高对比度（符合 WCAG AA 标准）。
在 `template-ethnic.html` 的 `:root {}` 中替换对应变量即可切换主题。

---

## 主题 A — 暖橙（默认，推荐小学）

温暖活泼，适合低年级和数学/科学课。

```css
:root {
  --bg-primary: #fffbf5;
  --bg-slide: #ffffff;
  --bg-accent: #fff3e0;
  --color-primary: #e65100;
  --color-secondary: #f57c00;
  --color-keyword: #ffffff;
  --bg-keyword: #e53e3e;
  --color-text: #1a1a1a;
  --color-text-light: #555555;
  --color-border: #ffcc80;
  --step-num-bg: #ff6d00;
  --step-num-color: #ffffff;
  --nav-dot: #e65100;
}
```

---

## 主题 B — 天蓝（推荐初中/英语/语文）

清爽专注，适合需要大量文字阅读的课堂。

```css
:root {
  --bg-primary: #f0f7ff;
  --bg-slide: #ffffff;
  --bg-accent: #e3f2fd;
  --color-primary: #0d47a1;
  --color-secondary: #1976d2;
  --color-keyword: #ffffff;
  --bg-keyword: #d32f2f;
  --color-text: #1a1a1a;
  --color-text-light: #455a64;
  --color-border: #90caf9;
  --step-num-bg: #1565c0;
  --step-num-color: #ffffff;
  --nav-dot: #1976d2;
}
```

---

## 主题 C — 草绿（推荐自然/生物/地理）

自然舒适，适合生命科学类课程，也贴近牧区自然场景。

```css
:root {
  --bg-primary: #f1f8f1;
  --bg-slide: #ffffff;
  --bg-accent: #e8f5e9;
  --color-primary: #1b5e20;
  --color-secondary: #388e3c;
  --color-keyword: #ffffff;
  --bg-keyword: #c62828;
  --color-text: #1a1a1a;
  --color-text-light: #4e5d4f;
  --color-border: #a5d6a7;
  --step-num-bg: #2e7d32;
  --step-num-color: #ffffff;
  --nav-dot: #388e3c;
}
```

---

## 主题 D — 高对比黑白（视力障碍/老旧投影仪）

极高对比度，适用于投影仪画质差、教室光线强或有视力障碍学生的情况。

```css
:root {
  --bg-primary: #000000;
  --bg-slide: #111111;
  --bg-accent: #222222;
  --color-primary: #ffffff;
  --color-secondary: #ffff00;
  --color-keyword: #000000;
  --bg-keyword: #ffff00;
  --color-text: #ffffff;
  --color-text-light: #cccccc;
  --color-border: #666666;
  --step-num-bg: #ffff00;
  --step-num-color: #000000;
  --nav-dot: #ffffff;
}
```

---

## 主题选择建议

| 学科 | 推荐主题 |
|---|---|
| 数学 | A 暖橙 |
| 语文 | B 天蓝 |
| 英语 | B 天蓝 |
| 科学/物理/化学 | A 暖橙 或 C 草绿 |
| 生物/地理 | C 草绿 |
| 历史/道德与法治 | B 天蓝 |
| 老旧设备/投影仪 | D 高对比 |
