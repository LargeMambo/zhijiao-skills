# 少数民族语言注释模板

本文件提供各语种的关键词注释格式和常用词汇，供 ppt-html 子技能在教师指定语种时使用。

**使用前提：** 只有教师在提示词中明确指定语种时才添加双语注释。

---

## 通用 HTML 模板

将以下代码添加到每个 `<section>` 底部，替换对应语种：

```html
<div class="bilingual-bar">
  <span class="bi-label">💬</span>
  <span class="bi-zh">【汉语关键词】</span>
  <span class="bi-sep">→</span>
  <span class="bi-minority" lang="[语言代码]" dir="[方向]">【少数民族语对应词】</span>
</div>
```

**lang 属性代码：**
- 维吾尔语：`ug`
- 藏语：`bo`
- 哈萨克语：`kk`
- 蒙古语：`mn`
- 柯尔克孜语：`ky`

**dir 属性：**
- 维吾尔语、哈萨克语、柯尔克孜语：`dir="rtl"`（从右向左）
- 藏语、蒙古语：`dir="ltr"`（从左向右）

---

## CSS 样式（添加到模板 `<style>` 中）

```css
.bilingual-bar {
  position: absolute;
  bottom: 1.2rem;
  left: 0;
  right: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.8rem;
  padding: 0.5rem 2rem;
  background: rgba(0,0,0,0.08);
  border-top: 1px solid var(--color-border);
  font-size: 1.1rem;
  color: var(--color-text-light);
}
.bi-minority {
  font-size: 1.2rem;
  color: var(--color-primary);
  font-weight: 500;
}
/* 维语/哈萨克语等 RTL 文字需要特殊字体支持 */
[lang="ug"], [lang="kk"], [lang="ky"] {
  font-family: "Noto Nastaliq Urdu", "Scheherazade New", serif;
}
[lang="bo"] {
  font-family: "Tibetan Machine Uni", "Noto Serif Tibetan", serif;
}
[lang="mn"] {
  font-family: "Noto Sans Mongolian", serif;
}
```

> **注意**：少数民族语言字体在多数设备上未预装，建议字体仅作为美化增强，
> 系统无对应字体时会回退到通用 serif 字体，文字依然可读。

---

## 各语种常用教学词汇

### 维吾尔语（ug）

| 汉语 | 维吾尔语 | 发音参考 |
|---|---|---|
| 数学 | ماتېماتىكا | matematika |
| 语文 | ئانا تىلى | ana tili |
| 课题 | مەۋزۇ | mewzu |
| 例题 | مىسال | misal |
| 答案 | جاۋاب | jawab |
| 重点 | ئاساسلىق نۇقتا | asasliq nuqta |
| 注意 | دىققەت | diqqet |
| 同学们 | ئوقۇغۇچىلار | oqughuchïlar |
| 回答 | جاۋاب بەر | jawab ber |
| 正确 | توغرا | toghra |
| 错误 | خاتا | khata |
| 思考 | ئويلاش | oylash |
| 分数 | كەسىر | kesir |
| 等于 | گە باراۋەر | ge barawer |
| 面积 | يۈزلۈك | yüzlük |

### 藏语（bo）

| 汉语 | 藏语 | 注音（拉丁转写） |
|---|---|---|
| 数学 | རྩིས་རིག | tsi-rik |
| 语文 | བོད་ཡིག | bö-yik |
| 例题 | དཔེར་བརྗོད། | per-jö |
| 答案 | ལན། | len |
| 重点 | གལ་གནད། | kel-né |
| 注意 | ཞིབ་འཇུག | zhib-juk |
| 同学们 | མཐུན་རོགས། | thün-rok |
| 正确 | ཡང་དག | yang-dak |
| 错误 | ནོར་འཁྲུལ། | nor-trül |

### 哈萨克语（kk）

| 汉语 | 哈萨克语 | 发音参考 |
|---|---|---|
| 数学 | математика | matematika |
| 语文 | қазақ тілі | qazaq tili |
| 例题 | мысал | mïsal |
| 答案 | жауап | jawap |
| 注意 | назар аудар | nazar audar |
| 正确 | дұрыс | durïs |
| 错误 | қате | qate |
| 思考 | ойлан | oylan |

### 蒙古语（mn）

| 汉语 | 蒙古语（西里尔） | 发音参考 |
|---|---|---|
| 数学 | математик | matematik |
| 语文 | монгол хэл | mongol khel |
| 例题 | жишээ бодлого | jishee bodlogo |
| 答案 | хариулт | khariult |
| 注意 | анхаар | ankhaar |
| 正确 | зөв | zöv |
| 错误 | буруу | buruu |

---

## 使用建议

1. **不要逐字翻译整页内容**，只注释本页的 1-2 个核心关键词
2. 注释栏字号保持在 `1.1-1.2rem`，不要比正文更大
3. 题目和例题页不需要双语注释（以免分散注意力）
4. 文化适应举例（如数学应用题的情境）用汉语即可，无需翻译
