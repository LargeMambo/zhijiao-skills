# SVG 内嵌规范

本文件说明如何将矢量图内嵌到 HTML 课件中，确保离线完整性。

---

## 原则

**所有图像必须内嵌，不得使用外链。** 课件 HTML 文件需要在没有网络的教室设备上完整运行。

---

## 方法一：使用 assets/emoji-vectors/ 中的预置 SVG（推荐）

`assets/emoji-vectors/` 目录中存有常用教学场景的矢量图。

使用方式：读取对应 `.svg` 文件内容，将 `<svg>...</svg>` 标签直接粘贴到 HTML 中。

```html
<!-- 示例：嵌入一个苹果图标 -->
<div class="visual-icon">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64" width="120" height="120">
    <!-- svg 内容 -->
  </svg>
</div>
```

**重要：** 嵌入时设置合适的 `width` 和 `height` 属性，确保在不同屏幕尺寸下正常显示。

---

## 方法二：Unicode Emoji（最简单，零依赖）

当 `assets/emoji-vectors/` 中没有需要的图案时，直接使用 Unicode emoji 字符。
在现代操作系统（Windows 10+、macOS、iOS、Android）上均可正常显示。

```html
<!-- 直接用 emoji 字符，无任何依赖 -->
<div class="big-emoji" role="img" aria-label="书本">📚</div>
<div class="big-emoji" role="img" aria-label="铅笔">✏️</div>
```

**推荐常用教学 emoji：**

| 场景 | Emoji | Unicode |
|---|---|---|
| 学习/课本 | 📚 | U+1F4DA |
| 铅笔/写字 | ✏️ | U+270F |
| 思考 | 💭 | U+1F4AD |
| 举手 | 🙋 | U+1F64B |
| 目标 | 🎯 | U+1F3AF |
| 重点/注意 | ⭐ | U+2B50 |
| 正确 | ✅ | U+2705 |
| 错误 | ❌ | U+274C |
| 问题/疑问 | ❓ | U+2753 |
| 提示/灯泡 | 💡 | U+1F4A1 |
| 作业 | 📝 | U+1F4DD |
| 庆祝 | 🎉 | U+1F389 |
| 时间/计时 | ⏱ | U+23F1 |
| 地图/地理 | 🗺️ | U+1F5FA |
| 实验/科学 | 🔬 | U+1F52C |
| 植物/生物 | 🌿 | U+1F33F |
| 数字/计算 | 🔢 | U+1F522 |
| 音乐 | 🎵 | U+1F3B5 |
| 运动/体育 | ⚽ | U+26BD |
| 美术 | 🎨 | U+1F3A8 |

---

## 方法三：base64 内嵌（适合 PNG/JPEG 图片）

如果教师提供了图片文件，使用 base64 编码内嵌：

```html
<img src="data:image/png;base64,[BASE64编码字符串]" alt="图片描述" width="300">
```

**注意：** base64 图片会显著增大 HTML 文件体积。建议：
- 图片分辨率不超过 800×600px
- JPEG 图片压缩至质量 70-80%
- 单个 HTML 文件建议不超过 5MB

---

## assets/emoji-vectors/ 目录说明

预置 SVG 文件按主题分类：

```
assets/emoji-vectors/
├── education/        教育场景（书本、黑板、铅笔、地球仪…）
├── nature/           自然场景（植物、动物、天气、地貌…）
├── people/           人物（学生、教师、举手、小组…）
├── objects/          常用物品（时钟、放大镜、星星、灯泡…）
├── symbols/          符号（箭头、对勾、叉号、数字…）
└── culture/          文化场景（民族服饰、建筑、食物…）
```

每个 SVG 文件命名规范：`[描述]-[颜色].svg`，例如：
- `book-blue.svg`
- `star-gold.svg`
- `checkmark-green.svg`
- `arrow-right-orange.svg`
