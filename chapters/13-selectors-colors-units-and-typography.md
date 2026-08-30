# 🖌️ Chapter 13: Selectors, Colors, Units and Typography

![Level](https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-brightgreen)
![Course](https://img.shields.io/badge/Course-BCA-blue)
![Unit](https://img.shields.io/badge/Unit-CSS-purple)
![Language](https://img.shields.io/badge/Language-English%20%2B%20Hinglish-orange)

> [!TIP]
> **Chapter Goal:** HTML elements ko accurately select karna, accessible colors choose karna, suitable CSS units use karna aur readable responsive typography create karna.

---

## 🎯 13.1 Learning Objectives

After completing this chapter, you will be able to:

1. Use type, class, ID, universal and grouping selectors.
2. Apply descendant, child and sibling combinators.
3. Use attribute selectors.
4. Understand pseudo-classes and pseudo-elements.
5. Use modern functional selectors such as `:is()`, `:where()` and `:not()`.
6. Write colors using different CSS formats.
7. Choose absolute and relative units.
8. Use responsive viewport and container-related units carefully.
9. Apply font and text properties.
10. Create readable, accessible typography.
11. Build a styled article page using chapter concepts.

---

## 🗣️ 13.2 Difficult Words: Pronunciation and Meaning

| 🔤 Word | 🔊 Pronunciation | 💡 Simple Meaning |
|---|---|---|
| Selector | सिलेक्टर — *si-lek-ter* | Elements choose karne ka pattern |
| Combinator | कॉम्बिनेटर — *kom-bi-nay-ter* | Selectors ka relationship operator |
| Attribute | एट्रिब्यूट — *uh-trib-yoot* | Element ki extra information |
| Pseudo-class | सूडो क्लास — *soo-doh class* | Element state/condition selector |
| Pseudo-element | सूडो एलिमेंट — *soo-doh el-uh-ment* | Element ke conceptual part ko select karta hai |
| Specificity | स्पेसिफिसिटी — *spes-uh-fis-uh-tee* | Selector comparison weight |
| Opacity | ओपैसिटी — *oh-pas-uh-tee* | Transparency level |
| Hue | ह्यू — *hyoo* | Basic color angle/type |
| Saturation | सैचुरेशन — *sat-yuh-ray-shun* | Color intensity |
| Typography | टाइपोग्राफी — *tai-pog-ruh-fee* | Text presentation ka system |
| Typeface | टाइपफेस — *type-face* | Letter design family |
| Font | फॉन्ट — *font* | Typeface ka specific digital resource/style |
| Relative | रिलेटिव — *rel-uh-tiv* | Kisi reference par dependent |
| Viewport | व्यूपोर्ट — *vyoo-port* | Browser ka visible area |
| Legibility | लेजिबिलिटी — *lej-uh-bil-uh-tee* | Letters ko easily identify karna |
| Readability | रीडबिलिटी — *ree-duh-bil-uh-tee* | Text ko comfortably read/samajhna |

---

# 🟦 Part A: CSS Selectors

## 💡 13.3 What Is a Selector?

A CSS selector is a pattern used to match elements that should receive a set of declarations.

```css
selector {
    property: value;
}
```

Example:

```css
p {
    color: #1f2937;
}
```

Here, `p` is the selector.

---

## 🌐 13.4 Universal Selector

```css
* {
    box-sizing: border-box;
}
```

It selects all elements in the relevant scope.

Namespace/type combinations and pseudo-elements can affect exact matching, but beginner use me `*` “all elements” ke roop me samjhein.

---

## 🏷️ 13.5 Type Selector

```css
h1 {
    color: #123a70;
}
```

All `h1` elements match honge.

Multiple types:

```css
h1,
h2,
h3 {
    font-family: Georgia, serif;
}
```

---

## 🧩 13.6 Class Selector

HTML:

```html
<p class="notice">Exam starts at 10 AM.</p>
```

CSS:

```css
.notice {
    padding: 1rem;
    background-color: #fff4cc;
}
```

One element multiple classes use kar sakta hai:

```html
<p class="notice urgent">Submit today.</p>
```

Select element containing both classes:

```css
.notice.urgent {
    border-left: 4px solid #b42318;
}
```

---

## 🆔 13.7 ID Selector

HTML:

```html
<h1 id="main-title">Web Technology</h1>
```

CSS:

```css
#main-title {
    color: #123a70;
}
```

ID document me unique hona chahiye. Reusable styling ke liye classes generally more flexible hain.

---

## 👥 13.8 Selector List

```css
h1,
h2,
h3,
.course-title {
    color: #123a70;
}
```

All listed selectors same declaration block share karte hain.

> [!WARNING]
> Traditional selector list me one invalid selector complete list ko invalidate kar sakta hai depending on syntax/context. Supported selectors use karein or forgiving functional lists such as `:is()` consider karein.

---

# 🟩 Part B: Combinators

## 🌳 13.9 Descendant Combinator

Space means any matching descendant:

```css
article p {
    line-height: 1.7;
}
```

Article ke andar any nesting level par `p` match ho sakta hai.

---

## 👶 13.10 Child Combinator

Greater-than sign `>` only direct children select karta hai.

```css
nav > ul {
    list-style: none;
}
```

`ul` must be direct child of `nav`.

---

## ➕ 13.11 Next-Sibling Combinator

Plus `+` immediately following sibling select karta hai.

```css
h2 + p {
    font-size: 1.1rem;
}
```

Only first matching `p` immediately after `h2`.

---

## 🌊 13.12 Subsequent-Sibling Combinator

Tilde `~` later matching siblings select karta hai.

```css
h2 ~ p {
    color: #374151;
}
```

Same parent ke under `h2` ke baad aane wale matching paragraphs.

---

## ⚖️ 13.13 Combinator Comparison

| Pattern | Meaning |
|---|---|
| `A B` | B anywhere inside A |
| `A > B` | B direct child of A |
| `A + B` | B immediately after A |
| `A ~ B` | B later sibling after A |

---

# 🟨 Part C: Attribute Selectors

## 🧾 13.14 Attribute Presence

```css
input[required] {
    border-left: 4px solid #b42318;
}
```

Matches inputs containing `required`.

---

## 🎯 13.15 Exact Attribute Value

```css
input[type="email"] {
    background-color: #f8fafc;
}
```

---

## 📝 13.16 Common Attribute Operators

| Selector | Meaning |
|---|---|
| `[attr]` | Attribute exists |
| `[attr="value"]` | Exact value |
| `[attr~="word"]` | Space-separated list contains word |
| `[attr|="value"]` | Exact or value followed by hyphen |
| `[attr^="value"]` | Starts with value |
| `[attr$="value"]` | Ends with value |
| `[attr*="value"]` | Contains substring |

Examples:

```css
a[href^="https://"] {
    color: #005fcc;
}

a[href$=".pdf"] {
    font-weight: bold;
}

a[href*="github.com"] {
    text-decoration-style: dotted;
}
```

> [!CAUTION]
> File extension or URL substring styling content type/security ka reliable proof nahi hai. Selector only attribute text inspect karta hai.

---

## 🔤 13.17 Case-Sensitivity Flags

```css
a[href$=".PDF" i] {
    font-weight: bold;
}
```

`i` matching ko ASCII case-insensitive banata hai in supported selector syntax.

---

# 🟪 Part D: Pseudo-Classes

## 💡 13.18 What Is a Pseudo-Class?

Pseudo-class element ki state, position ya condition ke according match karti hai.

Syntax:

```css
selector:pseudo-class {
    property: value;
}
```

---

## 🔗 13.19 Link Pseudo-Classes

```css
a:link {
    color: #005fcc;
}

a:visited {
    color: #6b2d8f;
}

a:hover {
    color: #003f88;
}

a:active {
    color: #b42318;
}
```

Browsers privacy reasons se `:visited` styling capabilities limit karte hain.

---

## ⌨️ 13.20 Focus Pseudo-Classes

```css
input:focus {
    border-color: #005fcc;
}

button:focus-visible {
    outline: 3px solid #ffbf47;
    outline-offset: 3px;
}

.form-group:focus-within {
    background-color: #f0f7ff;
}
```

| Pseudo-class | Meaning |
|---|---|
| `:focus` | Element has focus |
| `:focus-visible` | Focus indicator helpful/expected according to UA heuristics |
| `:focus-within` | Element or descendant has focus |

> [!IMPORTANT]
> Visible keyboard focus remove na karein.

---

## 📝 13.21 Form-State Pseudo-Classes

```css
input:required {
    border-left: 4px solid #b42318;
}

input:disabled {
    opacity: 0.6;
}

input:checked {
    accent-color: #005fcc;
}

input:valid {
    border-color: #2e7d32;
}

input:invalid {
    border-color: #b42318;
}
```

Useful states:

- `:enabled`
- `:disabled`
- `:checked`
- `:required`
- `:optional`
- `:valid`
- `:invalid`
- `:in-range`
- `:out-of-range`
- `:placeholder-shown`
- `:read-only`
- `:read-write`

> [!CAUTION]
> Error only red/green color se show na karein. Text message and accessible association bhi provide karein.

---

## 🔢 13.22 Structural Pseudo-Classes

```css
li:first-child {
    font-weight: bold;
}

li:last-child {
    border-bottom: 0;
}

li:nth-child(odd) {
    background-color: #f8fafc;
}

li:nth-child(even) {
    background-color: #eef2f7;
}
```

More:

- `:only-child`
- `:first-of-type`
- `:last-of-type`
- `:only-of-type`
- `:nth-of-type()`
- `:empty`

---

## 🎯 13.23 Target Pseudo-Class

Fragment target select karta hai:

HTML:

```html
<section id="admission">...</section>
```

CSS:

```css
section:target {
    outline: 3px solid #ffbf47;
}
```

URL ending `#admission` par section highlight ho sakta hai.

---

## 🚫 13.24 `:not()`

Specified selector match na karne wale elements:

```css
button:not(.secondary) {
    background-color: #005fcc;
    color: white;
}
```

---

## 👥 13.25 `:is()`

Selector alternatives ko compact banata hai:

```css
:is(article, section, aside) h2 {
    color: #123a70;
}
```

Equivalent repeated selectors reduce hote hain.

---

## 🪶 13.26 `:where()`

`:where()` alternatives group karta hai but function itself and arguments contribute zero specificity.

```css
:where(article, section, aside) h2 {
    margin-top: 0;
}
```

Low-specificity base styles ke liye useful.

---

## 🔍 13.27 `:has()` Introduction

Relational pseudo-class parent/subject ko relative condition ke according match kar sakti hai.

```css
.card:has(img) {
    padding-top: 0;
}

.form-group:has(input:invalid) {
    border-left: 4px solid #b42318;
}
```

> [!NOTE]
> Modern feature use karte waqt project ke target browsers and fallback requirements test karein.

---

# 🟥 Part E: Pseudo-Elements

## 💡 13.28 What Is a Pseudo-Element?

Pseudo-element element ke conceptual part ko style karta hai.

Common syntax double colon:

```css
selector::pseudo-element {
    property: value;
}
```

---

## ✍️ 13.29 `::first-letter` and `::first-line`

```css
.article-intro::first-letter {
    font-size: 3rem;
    font-weight: bold;
}

.article-intro::first-line {
    color: #123a70;
}
```

---

## ➕ 13.30 `::before` and `::after`

```css
.external-link::after {
    content: " ↗";
}

.note::before {
    content: "Note: ";
    font-weight: bold;
}
```

> [!WARNING]
> Essential information only generated content me na rakhein. Accessibility and copy behavior contexts me generated content inconsistent ho sakta hai.

---

## 🎨 13.31 Other Useful Pseudo-Elements

```css
::selection {
    background-color: #ffdf70;
    color: #111827;
}

input::placeholder {
    color: #667085;
}

li::marker {
    color: #005fcc;
}
```

---

# 🟧 Part F: CSS Colors

## 🎨 13.32 Named Colors

```css
h1 {
    color: navy;
}
```

Easy but limited design precision.

---

## #️⃣ 13.33 Hexadecimal Colors

```css
h1 {
    color: #123a70;
}

.card {
    background-color: #ffffff;
}
```

Formats:

- `#RGB`
- `#RGBA`
- `#RRGGBB`
- `#RRGGBBAA`

Alpha example:

```css
.overlay {
    background-color: #00000080;
}
```

---

## 🔴 13.34 RGB and RGBA

```css
p {
    color: rgb(31 41 55);
}

.overlay {
    background-color: rgb(0 0 0 / 50%);
}
```

Channels describe red, green and blue; optional alpha controls transparency.

Legacy comma syntax bhi existing code me mil sakti hai:

```css
color: rgba(0, 0, 0, 0.5);
```

---

## 🌈 13.35 HSL

```css
h1 {
    color: hsl(214 72% 25%);
}
```

| Component | Meaning |
|---|---|
| Hue | Color angle/type |
| Saturation | Color intensity |
| Lightness | Light-dark level |
| Alpha | Optional transparency |

```css
background-color: hsl(214 72% 25% / 90%);
```

---

## 🧪 13.36 Modern Color Functions Introduction

Modern CSS also includes formats/functions such as:

- `hwb()`
- `lab()`
- `lch()`
- `oklab()`
- `oklch()`
- `color()`

Example:

```css
.accent {
    color: oklch(55% 0.18 250);
}
```

> [!NOTE]
> Advanced color spaces wider and perceptually useful choices support kar sakte hain. Target browser support, tooling and fallback strategy check karein.

---

## 👻 13.37 Transparency and Opacity

Element-level opacity:

```css
.disabled-card {
    opacity: 0.6;
}
```

Color-only alpha:

```css
.card {
    background-color: rgb(255 255 255 / 85%);
}
```

Difference:

- `opacity` entire element including children affect karta hai.
- Alpha color only that color value affect karta hai.

---

## 🧾 13.38 Current Color

`currentColor` element ki computed `color` value use karta hai.

```css
.button {
    color: #005fcc;
    border: 2px solid currentColor;
}
```

---

## ♿ 13.39 Color Accessibility

Common WCAG contrast targets:

- Normal text: at least 4.5:1
- Large text: at least 3:1
- Many meaningful UI boundaries/graphics: at least 3:1

Do not rely only on color:

Bad:

```html
<p>Red fields are required.</p>
```

Better:

```html
<p>Required fields are marked “Required”.</p>
```

> [!TIP]
> Contrast calculator use karein. Monitor dekhkar guess na karein.

---

# 🟫 Part G: CSS Units

## 📏 13.40 Absolute Length Units

| Unit | Meaning |
|---|---|
| `px` | CSS pixel |
| `in` | Inch |
| `cm` | Centimeter |
| `mm` | Millimeter |
| `pt` | Point |
| `pc` | Pica |

Screen design me `px` common hai. Physical units ka actual physical-size relationship output/device context par depend kar sakta hai.

---

## 🔄 13.41 Relative Units

| Unit | Relative To |
|---|---|
| `%` | Property-specific reference |
| `em` | Current element's relevant font size/context |
| `rem` | Root element font size |
| `ch` | “0” glyph advance approximation |
| `ex` | Font x-height approximation |
| `lh` | Element line height |
| `rlh` | Root line height |

---

## 🔤 13.42 `em` vs `rem`

### `em`

```css
.card {
    font-size: 20px;
    padding: 1em;
}
```

Padding becomes relative to card's font size.

Nested font-size with `em` can compound:

```css
.parent {
    font-size: 1.2em;
}

.child {
    font-size: 1.2em;
}
```

### `rem`

```css
h1 {
    font-size: 2rem;
}
```

`rem` root font size par based hota hai, creating more predictable sizing.

> [!TIP]
> User font preferences respect karne ke liye root font size ko unnecessarily fixed/overridden na karein.

---

## 📐 13.43 Percentages

```css
main {
    width: 90%;
}
```

Percentage reference property ke according differ hoti hai. Example width often containing block se relate hoti hai.

---

## 🖥️ 13.44 Viewport Units

| Unit | Meaning |
|---|---|
| `vw` | 1% viewport width |
| `vh` | 1% viewport height |
| `vmin` | Smaller viewport dimension ka 1% |
| `vmax` | Larger viewport dimension ka 1% |

Modern viewport variants:

- `svh` — small viewport height
- `lvh` — large viewport height
- `dvh` — dynamic viewport height

Example:

```css
.hero {
    min-height: 100dvh;
}
```

Mobile browser controls ki wajah se viewport-height behavior change ho sakta hai. Test carefully.

---

## 📦 13.45 Container Query Units Introduction

| Unit | Meaning |
|---|---|
| `cqw` | Query container width ka 1% |
| `cqh` | Query container height ka 1% |
| `cqi` | Query container inline size ka 1% |
| `cqb` | Query container block size ka 1% |
| `cqmin` | Smaller query-container dimension |
| `cqmax` | Larger query-container dimension |

Example:

```css
.card-title {
    font-size: clamp(1.25rem, 5cqi, 2rem);
}
```

Container queries detail responsive-design chapter me.

---

## 🧮 13.46 CSS Math Functions

### `calc()`

```css
main {
    width: calc(100% - 2rem);
}
```

### `min()`

```css
.card {
    width: min(100%, 40rem);
}
```

### `max()`

```css
section {
    padding-inline: max(1rem, 4vw);
}
```

### `clamp()`

```css
h1 {
    font-size: clamp(2rem, 5vw, 4rem);
}
```

`clamp(minimum, preferred, maximum)` responsive value ko range me limit karta hai.

---

## 🧭 13.47 Choosing Units

General guidance:

- Font size: `rem`, sometimes `em`/`clamp()`
- Component spacing: `rem` or `em`
- Fluid width: `%`
- Max reading width: `rem` or `ch`
- Borders: `px` often practical
- Viewport sections: viewport units carefully
- Component-relative design: container units where appropriate

No single unit every situation ke liye best nahi hai.

---

# 🟦 Part H: Typography

## 📖 13.48 Typography Basics

Typography includes:

- Typeface
- Font family
- Size
- Weight
- Style
- Line height
- Letter spacing
- Word spacing
- Alignment
- Line length
- Hierarchy
- Contrast

Goal: text readable, legible and visually organized ho.

---

## 🔤 13.49 Font Family

```css
body {
    font-family: Arial, Helvetica, sans-serif;
}
```

Browser first available font use karta hai.

### Generic Families

- `serif`
- `sans-serif`
- `monospace`
- `cursive`
- `fantasy`
- `system-ui`

System stack example:

```css
body {
    font-family:
        system-ui,
        -apple-system,
        "Segoe UI",
        sans-serif;
}
```

Font name spaces contain kare to quote karein:

```css
font-family: "Times New Roman", serif;
```

---

## 📐 13.50 Font Size

```css
body {
    font-size: 1rem;
}

h1 {
    font-size: 2.25rem;
}
```

Responsive heading:

```css
h1 {
    font-size: clamp(2rem, 5vw, 4rem);
}
```

> [!WARNING]
> Text ko extremely small na karein. Users ko zoom and text resize karne dein.

---

## 💪 13.51 Font Weight

```css
h1 {
    font-weight: 700;
}

p {
    font-weight: 400;
}
```

Common keywords:

- `normal`
- `bold`
- `lighter`
- `bolder`

Available weights selected font par depend karti hain.

---

## ✒️ 13.52 Font Style

```css
em {
    font-style: italic;
}
```

Values include:

- `normal`
- `italic`
- `oblique`

Semantic emphasis HTML `em` se define karein; CSS appearance control kare.

---

## 📏 13.53 Line Height

```css
body {
    line-height: 1.6;
}
```

Unitless line height often useful hai because descendants proportional value inherit karte hain.

Readable body text ke liye adequate line spacing important hai.

---

## ↔️ 13.54 Letter and Word Spacing

```css
.page-title {
    letter-spacing: 0.02em;
}

.summary {
    word-spacing: 0.08em;
}
```

Excessive spacing readability reduce kar sakti hai. All-caps me moderate letter spacing sometimes helpful ho sakti hai.

---

## 📍 13.55 Text Alignment

```css
h1 {
    text-align: center;
}

article {
    text-align: start;
}
```

Values:

- `start`
- `end`
- `left`
- `right`
- `center`
- `justify`

Long text ko full justify karna uneven spacing create kar sakta hai. Test readability.

---

## 🔗 13.56 Text Decoration

```css
a {
    text-decoration-line: underline;
    text-decoration-thickness: 0.12em;
    text-underline-offset: 0.18em;
}
```

Avoid removing link underline without another clear non-color indicator.

---

## 🔠 13.57 Text Transform

```css
.label {
    text-transform: uppercase;
}
```

Values:

- `uppercase`
- `lowercase`
- `capitalize`
- `none`

Screen/search meaning and actual source text considerations ke liye important content ko correct natural case me write karein.

---

## 📚 13.58 Readable Line Length

`ch` use karke paragraph width limit:

```css
.article-content {
    max-width: 68ch;
}
```

Very long lines reading difficult bana sakti hain. Exact ideal context, font, language and audience par depend karta hai.

---

## 🌐 13.59 Web Fonts with `@font-face`

```css
@font-face {
    font-family: "Course Sans";
    src:
        url("../fonts/course-sans.woff2") format("woff2");
    font-style: normal;
    font-weight: 400;
    font-display: swap;
}

body {
    font-family: "Course Sans", Arial, sans-serif;
}
```

Consider:

1. Valid font license
2. WOFF2 format where suitable
3. Only needed weights/styles
4. File size
5. Fallback fonts
6. Font-display behavior
7. Language glyph support
8. Layout shift

---

## 🧾 13.60 Font Shorthand

```css
p {
    font: italic 600 1rem/1.6 Arial, sans-serif;
}
```

Shorthand can reset omitted sub-properties. Beginners may prefer longhand for clarity.

---

# 🟩 Part I: Complete Practical

## 🧪 13.61 Styled Article Page

### HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Why Learn Web Technology?</title>
    <link rel="stylesheet" href="css/article.css">
</head>
<body>
    <a class="skip-link" href="#article-content">
        Skip to article
    </a>

    <header class="site-header">
        <p class="site-name">BCA Learning Hub</p>

        <nav aria-label="Main navigation">
            <a href="index.html">Home</a>
            <a href="articles.html" aria-current="page">Articles</a>
            <a href="contact.html">Contact</a>
        </nav>
    </header>

    <main>
        <article id="article-content" class="article">
            <header class="article-header">
                <p class="category">Web Development</p>
                <h1>Why Learn Web Technology?</h1>
                <p class="article-meta">
                    Published on
                    <time datetime="2026-08-30">30 August 2026</time>
                </p>
            </header>

            <p class="article-intro">
                Web Technology helps students understand how
                websites and web applications are created.
            </p>

            <h2>Core Technologies</h2>

            <ul class="technology-list">
                <li data-level="beginner">HTML</li>
                <li data-level="beginner">CSS</li>
                <li data-level="intermediate">JavaScript</li>
            </ul>

            <aside class="note">
                Practice every concept by creating a small project.
            </aside>

            <h2>Next Step</h2>

            <p>
                Continue with
                <a class="external-link" href="https://www.w3.org/Style/CSS/">
                    official CSS resources
                </a>.
            </p>
        </article>
    </main>

    <footer class="site-footer">
        <p>&copy; 2026 BCA Learning Hub</p>
    </footer>
</body>
</html>
```

### CSS

```css
* {
    box-sizing: border-box;
}

:root {
    color-scheme: light;
    font-family:
        system-ui,
        -apple-system,
        "Segoe UI",
        sans-serif;
}

body {
    margin: 0;
    background-color: #f5f7fb;
    color: #1f2937;
    font-size: 1rem;
    line-height: 1.7;
}

.skip-link {
    position: absolute;
    inset-inline-start: 1rem;
    top: -5rem;
    padding: 0.75rem 1rem;
    background: #ffffff;
    color: #111827;
}

.skip-link:focus {
    top: 1rem;
}

.site-header {
    padding: 1rem max(1rem, 5vw);
    background-color: #0b274b;
    color: #ffffff;
}

.site-name {
    font-size: 1.25rem;
    font-weight: 700;
}

.site-header a {
    margin-inline-end: 1rem;
    color: #ffffff;
    text-underline-offset: 0.2em;
}

.site-header a[aria-current="page"] {
    font-weight: 700;
    text-decoration-thickness: 0.18em;
}

.article {
    width: min(90%, 68rem);
    margin: 2rem auto;
    padding: clamp(1.25rem, 4vw, 3rem);
    border: 1px solid #d8dee8;
    border-radius: 1rem;
    background-color: #ffffff;
    box-shadow: 0 8px 24px rgb(15 23 42 / 10%);
}

.article-header {
    border-bottom: 1px solid #d8dee8;
}

.category {
    color: #005fcc;
    font-size: 0.9rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
}

h1 {
    margin-block: 0.25rem 0.5rem;
    color: #123a70;
    font-family: Georgia, serif;
    font-size: clamp(2rem, 6vw, 4rem);
    line-height: 1.1;
}

h2 {
    margin-top: 2rem;
    color: #123a70;
    font-family: Georgia, serif;
    line-height: 1.25;
}

.article-meta {
    color: #4b5563;
}

.article-intro {
    max-width: 62ch;
    font-size: 1.2rem;
}

.article-intro::first-letter {
    color: #123a70;
    font-family: Georgia, serif;
    font-size: 3rem;
    font-weight: 700;
}

.technology-list {
    padding-inline-start: 1.5rem;
}

.technology-list li::marker {
    color: #005fcc;
}

.technology-list li[data-level="intermediate"] {
    font-weight: 700;
}

.note {
    margin-block: 2rem;
    padding: 1rem;
    border-inline-start: 0.35rem solid #d97706;
    background-color: #fff7e6;
}

.external-link::after {
    content: " ↗";
}

a {
    color: #005fcc;
    text-decoration-thickness: 0.1em;
    text-underline-offset: 0.18em;
}

a:hover {
    color: #003f88;
}

a:focus-visible {
    outline: 3px solid #ffbf47;
    outline-offset: 3px;
}

.site-footer {
    padding: 1.5rem;
    background-color: #0b274b;
    color: #ffffff;
    text-align: center;
}
```

---

## ♿ 13.62 Accessibility Checklist

1. Text contrast verify karein.
2. Links ko only color par depend na karayein.
3. Focus visible rakhein.
4. User zoom block na karein.
5. Body text readable size me ho.
6. Line height adequate ho.
7. Long lines limit karein.
8. Actual HTML semantics preserve karein.
9. Pseudo-element content me essential info na rakhein.
10. Form invalid state text message ke saath show karein.
11. Relative units and reflow test karein.
12. Custom font fallback provide karein.

---

## 🚫 13.63 Common Mistakes

1. Class selector me dot omit karna.
2. ID selector me hash omit karna.
3. Child and descendant selectors confuse karna.
4. `:hover` add karke focus state omit karna.
5. Excessive ID specificity.
6. `!important` se every conflict solve karna.
7. Essential text `::before`/`::after` me rakhna.
8. Low-contrast color use karna.
9. Opacity parent par lagakar children accidentally fade karna.
10. Fixed pixel font size se resizing restrict karna.
11. Nested `em` sizing compounding ignore karna.
12. `100vh` mobile behavior test na karna.
13. One font only without fallback.
14. Too many font files load karna.
15. Long paragraphs ko unlimited width dena.
16. Full justification se spacing problems ignore karna.

---

## 📌 13.64 Key Points to Remember

- Selector elements match karta hai.
- Class dot and ID hash use karta hai.
- Combinators element relationships select karte hain.
- Attribute selectors attribute text/value inspect karte hain.
- Pseudo-class state/condition match karti hai.
- Pseudo-element conceptual part style karta hai.
- `:where()` zero specificity contribution provide karta hai.
- CSS multiple color formats support karti hai.
- Alpha color and element opacity different hain.
- Relative units flexible designs me useful hain.
- `rem` root font size par depend karta hai.
- `clamp()` responsive bounded values create karta hai.
- Typography readability, hierarchy and spacing cover karti hai.
- Contrast and focus accessibility ke liye essential hain.

---

## 📝 13.65 Chapter Summary

CSS selectors target elements by type, class, ID, attributes, relationships, state and conceptual parts. Combinators distinguish descendants, children and siblings. Pseudo-classes represent conditions such as hover, focus, validity and structural position, while pseudo-elements style parts such as the first letter or marker. CSS colors can be expressed with names, hexadecimal, RGB, HSL and modern color functions. Units may be absolute or relative to fonts, containers and viewports. Typography properties control font family, size, weight, line height, spacing, alignment and decoration. Effective design uses maintainable selectors, responsive units, readable line lengths, suitable fallbacks, strong contrast and visible focus.

---

## 🎲 13.66 Multiple-Choice Questions

### 1. Which symbol starts a class selector?

A. `#`  
B. `.`  
C. `:`  
D. `@`  

**✅ Answer:** B

### 2. Which combinator selects direct children?

A. Space  
B. `>`  
C. `+`  
D. `~`  

**✅ Answer:** B

### 3. Which selector matches focused elements when focus should be visibly indicated?

A. `:hover`  
B. `:focus-visible`  
C. `::before`  
D. `:visited`  

**✅ Answer:** B

### 4. Which pseudo-element styles list markers?

A. `:marker`  
B. `::marker`  
C. `:list`  
D. `::bullet`  

**✅ Answer:** B

### 5. Which color model uses hue, saturation and lightness?

A. RGB  
B. HSL  
C. HEX only  
D. CMYK  

**✅ Answer:** B

### 6. Which unit is relative to root font size?

A. `em`  
B. `rem`  
C. `px`  
D. `vw`  

**✅ Answer:** B

### 7. Which function provides minimum, preferred and maximum values?

A. `calc()`  
B. `clamp()`  
C. `rgb()`  
D. `var()`  

**✅ Answer:** B

### 8. Which property controls line spacing?

A. `font-space`  
B. `line-height`  
C. `text-gap`  
D. `letter-spacing`  

**✅ Answer:** B

### 9. Which selector function has zero specificity contribution?

A. `:is()`  
B. `:where()`  
C. `:not()`  
D. `:has()`  

**✅ Answer:** B

### 10. Which property changes entire element transparency?

A. `alpha`  
B. `opacity`  
C. `visibility-color`  
D. `transparent-level`  

**✅ Answer:** B

---

## ✍️ 13.67 Fill in the Blanks

1. A type selector uses the element __________.
2. The `+` combinator selects the next __________.
3. A state selector is called a pseudo-__________.
4. `rem` is relative to the __________ element font size.
5. The property controlling font thickness is __________.

<details>
<summary><strong>✅ View Answers</strong></summary>

1. name  
2. sibling  
3. class  
4. root  
5. `font-weight`

</details>

---

## ✅ 13.68 True or False

1. IDs should generally be unique.
2. Descendant and child selectors are identical.
3. `:hover` replaces keyboard focus styling.
4. `::before` is a pseudo-element.
5. `opacity` affects an element's children visually.
6. `rem` is relative to the root font size.
7. `vw` is relative to viewport width.
8. Every website should use only pixels.
9. Line height affects readability.
10. Link underlines should always be removed.

<details>
<summary><strong>✅ View Answers</strong></summary>

1. True  
2. False  
3. False  
4. True  
5. True  
6. True  
7. True  
8. False  
9. True  
10. False

</details>

---

## ❓ 13.69 Short-Answer Questions

1. Define a CSS selector.
2. Differentiate between class and ID selectors.
3. Explain four combinators.
4. What is an attribute selector?
5. Define pseudo-class.
6. Define pseudo-element.
7. Explain `:is()` and `:where()`.
8. What is `:has()`?
9. Explain HEX, RGB and HSL colors.
10. Differentiate between alpha color and opacity.
11. Differentiate between absolute and relative units.
12. Differentiate between `em` and `rem`.
13. Explain viewport units.
14. What is `clamp()`?
15. Define typography.

---

## 📚 13.70 Long-Answer and Exam Questions

1. Explain basic and combinator selectors with examples.
2. Explain attribute selectors and operators.
3. Discuss common pseudo-classes.
4. Explain pseudo-elements with examples.
5. Explain modern functional selectors.
6. Compare CSS color formats.
7. Explain color accessibility.
8. Explain absolute, relative, viewport and container units.
9. Discuss CSS math functions.
10. Explain important font and text properties.
11. Discuss accessible responsive typography.
12. Create and explain a fully styled article page.

---

## 🧪 13.71 Practical Exercises

1. Create type, class and ID selectors.
2. Test all four combinators.
3. Style required and email inputs with attribute selectors.
4. Add hover and focus-visible link styles.
5. Create alternating list colors with `:nth-child()`.
6. Use `:not()` and `:is()`.
7. Add marker styling with `::marker`.
8. Compare HEX, RGB and HSL colors.
9. Create alpha backgrounds and opacity examples.
10. Compare `em` and `rem` in nested elements.
11. Create fluid heading size with `clamp()`.
12. Limit article width using `ch`.
13. Add a system font stack.
14. Build the complete article project.
15. Test contrast, zoom and keyboard focus.

---

## 🎤 13.72 Viva Questions

1. What is a selector?
2. How do class and ID selectors start?
3. What does the child combinator do?
4. What does `+` select?
5. What is an attribute selector?
6. What is a pseudo-class?
7. What is a pseudo-element?
8. What does `:focus-visible` do?
9. What does `:nth-child()` do?
10. Name three color formats.
11. What is opacity?
12. What is `rem` relative to?
13. What is `vw`?
14. What does `clamp()` return?
15. What is line height?

<details>
<summary><strong>✅ View Short Viva Answers</strong></summary>

1. A pattern matching elements.  
2. Dot and hash.  
3. Selects direct children.  
4. The immediately following sibling.  
5. A selector based on attributes.  
6. A state or condition selector.  
7. A selector for a conceptual part.  
8. Styles focus when a visible indicator is appropriate.  
9. Matches elements by sibling position pattern.  
10. HEX, RGB and HSL.  
11. Whole-element transparency level.  
12. Root font size.  
13. One percent of viewport width.  
14. A value bounded by minimum and maximum.  
15. Space/height allocated to text lines.

</details>

---

## 🏁 13.73 One-Minute Revision

| Question | Quick Answer |
|---|---|
| Class selector? | `.class` |
| ID selector? | `#id` |
| Direct child? | `A > B` |
| Next sibling? | `A + B` |
| State selector? | Pseudo-class |
| Conceptual part? | Pseudo-element |
| Focus style? | `:focus-visible` |
| Marker? | `::marker` |
| Root unit? | `rem` |
| Viewport width? | `vw` |
| Bounded fluid value? | `clamp()` |
| Text family? | `font-family` |
| Text thickness? | `font-weight` |
| Line spacing? | `line-height` |
| Reading width unit? | `ch` |

---

## 📚 13.74 Official References

1. [W3C Selectors Level 4](https://www.w3.org/TR/selectors-4/)
2. [W3C CSS Color](https://www.w3.org/TR/css-color-4/)
3. [W3C CSS Values and Units](https://www.w3.org/TR/css-values-4/)
4. [W3C CSS Fonts](https://www.w3.org/TR/css-fonts-4/)
5. [W3C CSS Text](https://www.w3.org/TR/css-text-4/)

---

[⬅️ Previous Chapter](12-css-fundamentals.md) · [📚 Table of Contents](../SUMMARY.md) · **Next: Box Model, Display and Positioning ➡️**
