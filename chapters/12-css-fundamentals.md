# 🎨 Chapter 12: CSS Fundamentals

![Level](https://img.shields.io/badge/Level-Absolute%20Beginner-brightgreen)
![Course](https://img.shields.io/badge/Course-BCA-blue)
![Unit](https://img.shields.io/badge/Unit-CSS-purple)
![Language](https://img.shields.io/badge/Language-English%20%2B%20Hinglish-orange)

> [!TIP]
> **Chapter Goal:** CSS ko zero level se samajhna, HTML ke saath connect karna aur cascade, inheritance aur specificity ke basic rules use karke first styled webpage banana.

---

## 🎯 12.1 Learning Objectives

After completing this chapter, you will be able to:

1. Define CSS and explain its purpose.
2. Write a valid CSS rule.
3. Identify selectors, properties, values and declarations.
4. Add CSS using inline, internal and external methods.
5. Use basic element, class and ID selectors.
6. Apply common colors, spacing, borders and fonts.
7. Explain the cascade at a beginner level.
8. Understand inheritance and specificity.
9. Use browser Developer Tools to inspect styles.
10. Create a complete styled student-profile page.

---

## 🗣️ 12.2 Difficult Words: Pronunciation and Meaning

| 🔤 Word | 🔊 Pronunciation | 💡 Simple Meaning |
|---|---|---|
| CSS | सी-एस-एस — *see-es-es* | Web-page presentation language |
| Cascading | कैस्केडिंग — *kas-kay-ding* | Competing style rules ka ordered selection |
| Style Sheet | स्टाइल शीट — *style sheet* | CSS rules ka collection |
| Selector | सिलेक्टर — *si-lek-ter* | Target elements choose karta hai |
| Property | प्रॉपर्टी — *prop-er-tee* | Style ka feature |
| Value | वैल्यू — *val-yoo* | Property ki setting |
| Declaration | डेक्लेरेशन — *dek-luh-ray-shun* | Property-value pair |
| Specificity | स्पेसिफिसिटी — *spes-uh-fis-uh-tee* | Selector priority ka comparison weight |
| Inheritance | इनहेरिटेन्स — *in-hair-i-tuns* | Parent se child ko value milna |
| Origin | ओरिजिन — *or-i-jin* | Style rule ka source |
| Precedence | प्रेसीडन्स — *pres-i-duns* | Kaunsa rule priority me aage hai |
| External | एक्सटर्नल — *eks-tur-nul* | Separate file me |
| Internal | इंटरनल — *in-tur-nul* | Same HTML document me |
| Inline | इनलाइन — *in-line* | Element ke style attribute me |
| Debugging | डीबगिंग — *dee-bug-ing* | Error find aur fix karna |

---

# 🟦 Part A: Introduction to CSS

## 💡 12.3 What Is CSS?

**CSS** stands for **Cascading Style Sheets**.

### 12.3.1 English Explanation

CSS is a language used to describe the presentation and rendering of structured documents such as HTML. It controls colors, fonts, spacing, borders, sizing, positioning, layout, responsiveness and visual effects.

### 12.3.2 Hinglish Explanation

HTML page ka structure banati hai aur CSS uska appearance control karti hai. CSS se hum text color, background, font, spacing, border aur layout change kar sakte hain.

### Simple Example

HTML:

```html
<h1>Web Technology</h1>
```

CSS:

```css
h1 {
    color: blue;
}
```

Result: Heading browser me blue display hogi.

---

## 🧍 12.4 HTML, CSS and JavaScript

| Technology | Main Work | Example |
|---|---|---|
| HTML | Structure and meaning | Heading, paragraph, form |
| CSS | Presentation and layout | Color, spacing, responsive design |
| JavaScript | Behavior and logic | Click action, validation, dynamic update |

> [!IMPORTANT]
> CSS content ka semantic meaning create nahi karti. Correct HTML structure pehle banayein, phir CSS se style karein.

---

## ✅ 12.5 Advantages of CSS

1. Presentation aur content separate hote hain.
2. One stylesheet many pages style kar sakti hai.
3. Consistent design maintain hota hai.
4. Repeated styling code reduce hota hai.
5. Maintenance easier hoti hai.
6. Responsive layouts create ho sakte hain.
7. Different devices/media ke liye styles apply ho sakti hain.
8. Accessibility preferences support ki ja sakti hain.
9. Browser caching external CSS loading improve kar sakti hai.
10. HTML source cleaner rehta hai.

---

## 🕰️ 12.6 CSS Is Modular

CSS ko ek single fixed “CSS3 language version” ke roop me develop nahi kiya jata. Modern CSS multiple modules and specifications ka collection hai, such as:

- Color
- Selectors
- Backgrounds and Borders
- Flexbox
- Grid
- Transforms
- Animations
- Media Queries

> [!NOTE]
> “CSS3” term commonly use hota hai, but modern CSS features individual modules me evolve hote hain.

---

# 🟩 Part B: CSS Syntax

## 🧱 12.7 CSS Rule Structure

```css
p {
    color: navy;
    font-size: 18px;
}
```

### Parts

| Part | Example | Meaning |
|---|---|---|
| Selector | `p` | Target element(s) |
| Declaration block | `{ ... }` | Declarations ka group |
| Property | `color` | Style feature |
| Value | `navy` | Chosen setting |
| Declaration | `color: navy;` | Property-value pair |

### Visual Breakdown

```text
p {
│   color: navy;
│   └─┬─┘  └─┬─┘
│ property  value
└ selector
}
```

---

## ✍️ 12.8 Declaration Syntax

```css
property: value;
```

Example:

```css
background-color: lightblue;
```

Rules:

1. Property and value colon `:` se separate hote hain.
2. Declaration generally semicolon `;` se end hoti hai.
3. Declaration block braces `{ }` me hota hai.
4. Property names lowercase style me likhein.
5. Each declaration new line par readability improve karti hai.

---

## 💬 12.9 CSS Comments

```css
/* Main page heading */
h1 {
    color: darkblue;
}
```

CSS comments:

- `/*` se start
- `*/` se end
- Explanation or organization ke liye

> [!WARNING]
> Secret keys, passwords ya private information CSS comments me mat likhein. Stylesheet users download aur inspect kar sakte hain.

---

## 🚫 12.10 Invalid CSS

Incorrect:

```css
p {
    color = blue
    font-size 18px;
}
```

Correct:

```css
p {
    color: blue;
    font-size: 18px;
}
```

Browser invalid declaration ignore kar sakta hai while remaining valid CSS apply ho sakti hai.

---

# 🟨 Part C: Adding CSS to HTML

## 12.11 Inline CSS

CSS directly element ke `style` attribute me:

```html
<p style="color: blue; font-size: 18px;">
    Welcome to CSS.
</p>
```

### Advantages

- Quick testing
- One specific element

### Limitations

- HTML cluttered
- Reuse difficult
- Maintenance hard
- Style separation weak
- Cascade management confusing

> [!CAUTION]
> Regular project styling ke liye inline CSS avoid/prefer less karein.

---

## 12.12 Internal CSS

CSS same HTML document ke `head` me `style` element ke andar:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Internal CSS</title>

    <style>
        body {
            background-color: #f5f7fb;
        }

        h1 {
            color: #123a70;
        }
    </style>
</head>
<body>
    <h1>Internal CSS Example</h1>
</body>
</html>
```

### Suitable For

- Single-page demo
- Small prototype
- Self-contained example

### Limitation

Multiple pages ke across reuse difficult.

---

## 12.13 External CSS

CSS separate `.css` file me stored hoti hai.

### HTML: `index.html`

```html
<head>
    <meta charset="UTF-8">
    <title>External CSS</title>
    <link rel="stylesheet" href="css/styles.css">
</head>
```

### CSS: `css/styles.css`

```css
body {
    background-color: #f5f7fb;
    color: #1f2937;
}

h1 {
    color: #123a70;
}
```

### Advantages

1. Multiple pages reuse
2. Cleaner HTML
3. Easy maintenance
4. Consistent design
5. Browser caching opportunity
6. Better project organization

> [!IMPORTANT]
> Most multi-page projects ke liye external stylesheet preferred method hai.

---

## 12.14 External CSS File Structure

```text
my-website/
├── index.html
├── about.html
└── css/
    └── styles.css
```

From `index.html`:

```html
<link rel="stylesheet" href="css/styles.css">
```

Agar path wrong hai, CSS load nahi hogi.

---

## 12.15 `@import` Introduction

CSS file ke andar another stylesheet import ki ja sakti hai:

```css
@import url("typography.css");

body {
    background-color: white;
}
```

`@import` statements applicable ordering rules follow karti hain. Performance and architecture reasons ke liye standard HTML `link` often preferred hota hai for main stylesheets.

---

## ⚖️ 12.16 Inline vs Internal vs External

| Method | Location | Reuse | Best Use |
|---|---|---:|---|
| Inline | Element `style` | Very low | Small exceptional/test case |
| Internal | Document `style` | One document | Demo/single page |
| External | Separate `.css` file | High | Normal multi-page project |

---

# 🟪 Part D: Basic Selectors

## 🎯 12.17 Universal Selector

```css
* {
    box-sizing: border-box;
}
```

All elements select karta hai. Carefully use karein.

---

## 🏷️ 12.18 Type Selector

Element name ke through select karta hai:

```css
p {
    color: #333333;
}
```

All `p` elements affected.

---

## 🧩 12.19 Class Selector

Class selector dot `.` use karta hai:

HTML:

```html
<p class="important">Exam starts at 10 AM.</p>
```

CSS:

```css
.important {
    color: #a40000;
    font-weight: bold;
}
```

One class multiple elements par use ho sakti hai.

---

## 🆔 12.20 ID Selector

ID selector hash `#` use karta hai:

HTML:

```html
<h1 id="page-title">BCA Web Technology</h1>
```

CSS:

```css
#page-title {
    color: #123a70;
}
```

ID document me unique hona chahiye.

> [!TIP]
> Reusable styling ke liye class selectors usually more flexible hote hain.

---

## 👥 12.21 Selector List

Same declarations multiple selectors par:

```css
h1,
h2,
h3 {
    font-family: Arial, sans-serif;
    color: #123a70;
}
```

---

## 🌳 12.22 Descendant Selector

Element inside another element:

```css
article p {
    line-height: 1.7;
}
```

All paragraphs that are descendants of `article` select honge.

Detailed selectors Chapter 13 me cover honge.

---

# 🟥 Part E: Basic Properties

## 🎨 12.23 Text and Background Colors

```css
body {
    color: #1f2937;
    background-color: #f8fafc;
}
```

- `color` text foreground color
- `background-color` background color

Ensure readable contrast.

---

## 🔤 12.24 Basic Font Properties

```css
body {
    font-family: Arial, sans-serif;
    font-size: 16px;
    line-height: 1.6;
}
```

| Property | Work |
|---|---|
| `font-family` | Typeface stack |
| `font-size` | Text size |
| `font-weight` | Thickness |
| `font-style` | Normal/italic style |
| `line-height` | Lines ke beech distance |

Detailed typography Chapter 13 me.

---

## 📏 12.25 Width and Maximum Width

```css
main {
    width: 90%;
    max-width: 900px;
    margin: 0 auto;
}
```

- `width` preferred/current width set kar sakta hai.
- `max-width` maximum limit.
- `margin: 0 auto` fixed/limited block ko horizontally center kar sakta hai where leftover inline space exists.

---

## 📦 12.26 Margin and Padding

```css
.card {
    margin: 20px;
    padding: 20px;
}
```

| Property | Space |
|---|---|
| `padding` | Content aur border ke between |
| `margin` | Element ke outside |

Box model detail Chapter 14 me.

---

## 🖼️ 12.27 Border

```css
.card {
    border: 1px solid #cbd5e1;
    border-radius: 12px;
}
```

Shorthand parts:

```text
border-width border-style border-color
```

---

## 🌫️ 12.28 Box Shadow

```css
.card {
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.12);
}
```

Shadows carefully use karein. Important boundaries only shadow par depend na karein.

---

## 📐 12.29 Text Alignment

```css
.page-title {
    text-align: center;
}
```

Common values:

- `left`
- `right`
- `center`
- `start`
- `end`
- `justify`

Logical `start` and `end` writing direction ke saath adapt kar sakte hain.

---

## 🔗 12.30 Styling Links

```css
a {
    color: #005fcc;
}

a:hover {
    color: #003f88;
}

a:focus-visible {
    outline: 3px solid #ffbf47;
    outline-offset: 3px;
}
```

> [!IMPORTANT]
> Link ko only color se identify karna insufficient ho sakta hai. Underline or another non-color cue preserve karein where appropriate.

---

## 🖱️ 12.31 Styling Buttons

```css
.button {
    display: inline-block;
    padding: 0.75rem 1rem;
    border: 0;
    border-radius: 0.5rem;
    background-color: #005fcc;
    color: white;
    font: inherit;
    cursor: pointer;
}

.button:hover {
    background-color: #004a9f;
}

.button:focus-visible {
    outline: 3px solid #ffbf47;
    outline-offset: 3px;
}
```

Use actual `button` for actions, even if a class gives visual style.

---

# 🟧 Part F: The Cascade

## 🌊 12.32 Why “Cascading”?

Multiple rules same element/property ko target kar sakti hain. Cascade determines which declared value wins after considering factors such as:

- Origin and importance
- Context/layers
- Specificity
- Scope/proximity rules where applicable
- Source order

Beginner level par remember:

1. Applicable rules find hote hain.
2. Higher-priority declarations win.
3. Same priority me specificity compare ho sakti hai.
4. Same specificity me later declaration can win.

---

## 🔁 12.33 Source Order

```css
p {
    color: blue;
}

p {
    color: green;
}
```

Both selectors equal specificity rakhte hain, so later rule usually wins: green.

---

## 🧮 12.34 Specificity Basics

General beginner order:

```text
ID selector > Class/attribute/pseudo-class > Type selector
```

Example:

```css
p {
    color: blue;
}

.note {
    color: green;
}

#special-note {
    color: red;
}
```

HTML:

```html
<p id="special-note" class="note">Important text</p>
```

ID rule higher specificity ki wajah se red may win, assuming same origin/importance and no higher cascade factor.

> [!NOTE]
> Specificity sirf cascade ka one part hai. `!important`, origins, layers and other factors result affect kar sakte hain.

---

## 🧬 12.35 Inheritance

Some property values parent se child elements ko inherit hoti hain.

```css
body {
    color: #1f2937;
    font-family: Arial, sans-serif;
}
```

Body ke descendants often these text-related values inherit karenge unless overridden.

Commonly inherited examples:

- `color`
- `font-family`
- `font-size`
- `line-height`

Commonly not inherited by default:

- `margin`
- `padding`
- `border`
- `background-color`
- `width`

---

## 🔧 12.36 CSS-Wide Keywords

| Keyword | Basic Meaning |
|---|---|
| `inherit` | Parent ka computed value use karo |
| `initial` | Property ka initial value |
| `unset` | Inherited property → inherit; otherwise initial |
| `revert` | Lower-priority origin/layer result ki taraf revert |

Example:

```css
button {
    font-family: inherit;
}
```

---

## ❗ 12.37 `!important`

```css
.warning {
    color: red !important;
}
```

`!important` changes cascade importance and can make overrides difficult.

> [!WARNING]
> Routine specificity problems solve karne ke liye `!important` habitually use na karein. Clean selectors and organized CSS prefer karein.

---

## 🗂️ 12.38 Cascade Layers Introduction

Cascade layers author styles ko controlled priority groups me organize kar sakti hain.

```css
@layer reset, base, components, utilities;

@layer base {
    body {
        font-family: Arial, sans-serif;
    }
}

@layer components {
    .button {
        background-color: blue;
    }
}
```

This is an advanced feature. Beginner projects me simple organized stylesheet enough hai.

---

# 🟫 Part G: Developer Tools

## 🧰 12.39 Inspecting CSS

1. Web page open karein.
2. `F12` press karein.
3. Elements/Inspector panel select karein.
4. Element click karein.
5. Applied styles dekhein.
6. Crossed-out declarations notice karein.
7. Computed panel inspect karein.
8. Temporary value edit karein.

Developer Tools can show:

- Matched rules
- Source file and line
- Overridden declarations
- Computed values
- Box model
- Inherited styles
- Pseudo-class states

> [!NOTE]
> DevTools edits temporary hoti hain. Permanent change ke liye source CSS file update karein.

---

## 🐞 12.40 CSS Not Working? Checklist

1. CSS file path correct?
2. `link` head me correct?
3. File saved?
4. Browser reload/cache?
5. Selector target match karta hai?
6. Property spelling correct?
7. Colon and semicolon correct?
8. Braces balanced?
9. Another rule override kar raha hai?
10. Value valid and supported?
11. Comment accidentally unclosed?
12. DevTools console/network me error?

---

# 🟪 Part H: Complete Practical

## 📁 12.41 Project Structure

```text
styled-profile/
├── index.html
└── css/
    └── styles.css
```

---

## 🧱 12.42 HTML File

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Broun Verma | Student Profile</title>
    <link rel="stylesheet" href="css/styles.css">
</head>
<body>
    <a class="skip-link" href="#main-content">
        Skip to main content
    </a>

    <header class="site-header">
        <h1>Broun Verma</h1>
        <p>BCA Student and Web Technology Learner</p>
    </header>

    <nav class="main-navigation" aria-label="Main navigation">
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#contact">Contact</a>
    </nav>

    <main id="main-content" class="page-content">
        <section id="about" class="card">
            <h2>About Me</h2>
            <p>
                I am learning HTML, CSS and JavaScript
                from beginner to advanced level.
            </p>
        </section>

        <section id="skills" class="card">
            <h2>Current Skills</h2>
            <ul>
                <li>Semantic HTML</li>
                <li>Accessible Forms</li>
                <li>CSS Fundamentals</li>
            </ul>
        </section>

        <section id="contact" class="card">
            <h2>Contact</h2>
            <a class="button" href="mailto:contact@example.com">
                Send Email
            </a>
        </section>
    </main>

    <footer class="site-footer">
        <p>&copy; 2026 Broun Verma</p>
    </footer>
</body>
</html>
```

---

## 🎨 12.43 External CSS File

```css
/* Basic reset */
* {
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    margin: 0;
    background-color: #f4f7fb;
    color: #1f2937;
    font-family: Arial, sans-serif;
    font-size: 16px;
    line-height: 1.6;
}

/* Keyboard skip link */
.skip-link {
    position: absolute;
    left: 1rem;
    top: -4rem;
    padding: 0.75rem 1rem;
    background-color: #ffffff;
    color: #000000;
}

.skip-link:focus {
    top: 1rem;
}

/* Header */
.site-header {
    padding: 3rem 1rem;
    background-color: #123a70;
    color: #ffffff;
    text-align: center;
}

.site-header h1 {
    margin: 0;
    font-size: 2.25rem;
}

/* Navigation */
.main-navigation {
    padding: 1rem;
    background-color: #0b274b;
    text-align: center;
}

.main-navigation a {
    margin: 0 0.75rem;
    color: #ffffff;
    font-weight: bold;
}

/* Main content */
.page-content {
    width: 90%;
    max-width: 800px;
    margin: 2rem auto;
}

.card {
    margin-bottom: 1.5rem;
    padding: 1.5rem;
    border: 1px solid #cbd5e1;
    border-radius: 0.75rem;
    background-color: #ffffff;
    box-shadow: 0 4px 12px rgba(15, 23, 42, 0.08);
}

.card h2 {
    margin-top: 0;
    color: #123a70;
}

/* Button-style link */
.button {
    display: inline-block;
    padding: 0.75rem 1rem;
    border-radius: 0.5rem;
    background-color: #005fcc;
    color: #ffffff;
    font-weight: bold;
    text-decoration: none;
}

.button:hover {
    background-color: #004a9f;
}

/* Visible keyboard focus */
a:focus-visible {
    outline: 3px solid #ffbf47;
    outline-offset: 3px;
}

/* Footer */
.site-footer {
    padding: 1.5rem;
    background-color: #0b274b;
    color: #ffffff;
    text-align: center;
}
```

---

## 🧪 12.44 Practice Changes

Try these changes:

1. Header background color change karein.
2. Card border radius increase karein.
3. Font family stack change karein.
4. Button color change karein.
5. Page maximum width modify karein.
6. Navigation link spacing change karein.
7. One new class create karein.
8. DevTools me overridden rule identify karein.
9. Internal CSS version banayein.
10. CSS file temporarily disconnect karke compare karein.

---

## ♿ 12.45 Accessibility and CSS

1. Text-background contrast readable rakhein.
2. Focus outline remove na karein.
3. Content ko only color se identify na karein.
4. Text resize/zoom allow karein.
5. Fixed heights se text cut na ho.
6. Link appearance identifiable ho.
7. Hover ke saath focus state bhi style karein.
8. Motion later user preferences respect kare.
9. DOM order logical rakhein; visual reordering carefully.
10. CSS disabled/failed ho to HTML meaningful rahe.

---

## 🚫 12.46 Common Mistakes

1. CSS property me equals sign use karna.
2. Colon or semicolon omit karna.
3. Closing brace miss karna.
4. `class` selector me dot forget karna.
5. ID selector me hash forget karna.
6. Wrong external CSS path.
7. HTML file me CSS syntax outside `style` likhna.
8. CSS file me `<style>` tags add karna.
9. Every style inline likhna.
10. Excessive `!important` use karna.
11. IDs se all reusable styling karna.
12. Focus outline remove karna.
13. Low-contrast colors choose karna.
14. DevTools change ko permanent samajhna.
15. HTML structure problem ko only CSS se hide karna.

---

## 📌 12.47 Key Points to Remember

- CSS stands for Cascading Style Sheets.
- CSS structured documents ki presentation describe karti hai.
- Rule contains selector and declaration block.
- Declaration contains property and value.
- CSS can be inline, internal or external.
- External CSS normal multi-page projects ke liye preferred hai.
- Class selectors reusable hote hain.
- Cascade competing declarations ka result decide karta hai.
- Specificity cascade ka one factor hai.
- Some properties inherit hoti hain.
- `!important` carefully use karna chahiye.
- Browser DevTools CSS debugging me useful hain.
- Accessible design me contrast and focus important hain.

---

## 📝 12.48 Chapter Summary

CSS is the language used to control the visual presentation of HTML documents. A CSS rule contains a selector and a declaration block, while each declaration contains a property and value. CSS can be added inline, internally or through an external stylesheet; external CSS provides the best reuse for multi-page projects. Basic selectors target elements, classes and IDs. Common properties control colors, typography, spacing, borders and size. When multiple declarations apply, the cascade determines the result using priority factors including origin, importance, specificity and source order. Some values inherit from parent elements. Clean external styles, meaningful classes, visible focus and readable contrast produce more maintainable and accessible pages.

---

## 🎲 12.49 Multiple-Choice Questions

### 1. CSS stands for:

A. Creative Style System  
B. Cascading Style Sheets  
C. Computer Sheet Syntax  
D. Color Style Source  

**✅ Answer:** B

### 2. Which symbol starts a class selector?

A. `#`  
B. `.`  
C. `*`  
D. `:`  

**✅ Answer:** B

### 3. Which symbol starts an ID selector?

A. `#`  
B. `.`  
C. `@`  
D. `&`  

**✅ Answer:** A

### 4. Which method uses a separate CSS file?

A. Inline  
B. Internal  
C. External  
D. Embedded image  

**✅ Answer:** C

### 5. Which property controls text color?

A. `background`  
B. `color`  
C. `font-color`  
D. `text-paint`  

**✅ Answer:** B

### 6. Which property creates inner spacing?

A. `margin`  
B. `padding`  
C. `border`  
D. `width`  

**✅ Answer:** B

### 7. If equal-specificity rules conflict, which may win?

A. Earlier declaration always  
B. Later declaration  
C. HTML title  
D. File name  

**✅ Answer:** B

### 8. Which is commonly inherited?

A. `color`  
B. `margin`  
C. `border`  
D. `width`  

**✅ Answer:** A

### 9. Which tool helps inspect applied CSS?

A. Calculator  
B. Browser Developer Tools  
C. DNS server  
D. Email client  

**✅ Answer:** B

### 10. Which should not be removed without replacement?

A. Focus indicator  
B. Comments  
C. File extension  
D. Heading text  

**✅ Answer:** A

---

## ✍️ 12.50 Fill in the Blanks

1. A CSS rule begins with a __________.
2. A property and value form a __________.
3. External CSS files commonly use the __________ extension.
4. A class selector begins with __________.
5. Parent-to-child value propagation is called __________.

<details>
<summary><strong>✅ View Answers</strong></summary>

1. selector  
2. declaration  
3. `.css`  
4. dot (`.`)  
5. inheritance

</details>

---

## ✅ 12.51 True or False

1. CSS creates semantic HTML structure.
2. External CSS can style multiple pages.
3. Class names must be unique.
4. ID values should be unique.
5. All CSS properties inherit by default.
6. Specificity is one cascade factor.
7. Inline CSS is best for every project.
8. DevTools edits are normally temporary.
9. Focus outline should always be removed.
10. Invalid declarations may be ignored.

<details>
<summary><strong>✅ View Answers</strong></summary>

1. False  
2. True  
3. False  
4. True  
5. False  
6. True  
7. False  
8. True  
9. False  
10. True

</details>

---

## ❓ 12.52 Short-Answer Questions

1. Define CSS.
2. Explain the full form of CSS.
3. What is a CSS rule?
4. Define selector, property and value.
5. What is a declaration?
6. What is inline CSS?
7. What is internal CSS?
8. What is external CSS?
9. Define class selector.
10. Define ID selector.
11. What is the cascade?
12. Define specificity.
13. What is inheritance?
14. What is `!important`?
15. How do Developer Tools help?

---

## 📚 12.53 Long-Answer and Exam Questions

1. Define CSS and explain its advantages.
2. Explain CSS rule syntax with a diagram.
3. Compare inline, internal and external CSS.
4. Explain basic CSS selectors with examples.
5. Discuss common CSS properties.
6. Explain cascade and source order.
7. Explain specificity with examples.
8. Explain inheritance and CSS-wide keywords.
9. Discuss CSS coding and accessibility practices.
10. Create a complete styled profile page using external CSS.

---

## 🧪 12.54 Practical Exercises

1. Create an external stylesheet.
2. Link it to an HTML page.
3. Style the body background and text.
4. Style headings using type selectors.
5. Create a reusable card class.
6. Create and use an ID selector.
7. Style a link and its hover state.
8. Add visible focus styling.
9. Apply margin, padding and border.
10. Create two conflicting rules and observe source order.
11. Compare class and ID specificity.
12. Inspect computed styles in DevTools.
13. Build the complete styled-profile project.
14. Validate HTML and check CSS syntax.

---

## 🎤 12.55 Viva Questions

1. What is CSS?
2. Why is CSS called cascading?
3. What is a selector?
4. What is a declaration?
5. How do you write a CSS comment?
6. Where is internal CSS written?
7. How is external CSS linked?
8. Which selector starts with a dot?
9. Which selector starts with a hash?
10. What does `color` control?
11. What is the difference between margin and padding?
12. What is source order?
13. What is specificity?
14. What is inheritance?
15. Are DevTools changes permanent?

<details>
<summary><strong>✅ View Short Viva Answers</strong></summary>

1. A language for document presentation.  
2. Competing declarations are resolved through an ordered cascade.  
3. It targets elements.  
4. A property-value pair.  
5. `/* comment */`.  
6. In a `style` element, usually in `head`.  
7. With `link rel="stylesheet" href="...">`.  
8. Class selector.  
9. ID selector.  
10. Text foreground color.  
11. Outside space vs inner space.  
12. Later equal-priority declaration may win.  
13. Selector comparison weight in the cascade.  
14. Parent-to-child property-value propagation.  
15. No, normally temporary.

</details>

---

## 🏁 12.56 One-Minute Revision

| Question | Quick Answer |
|---|---|
| CSS full form? | Cascading Style Sheets |
| Rule parts? | Selector + declaration block |
| Declaration? | Property + value |
| Class selector? | `.class` |
| ID selector? | `#id` |
| External file? | `styles.css` |
| Link CSS? | `link rel="stylesheet"` |
| Text color? | `color` |
| Background? | `background-color` |
| Inner spacing? | `padding` |
| Outer spacing? | `margin` |
| Competing rules? | Cascade |
| Selector weight? | Specificity |
| Parent value? | Inheritance |
| Inspect styles? | DevTools |

---

## 📚 12.57 Official References

1. [W3C CSS Snapshot 2026](https://www.w3.org/TR/css-2026/)
2. [W3C CSS Cascading and Inheritance](https://www.w3.org/TR/css-cascade-6/)
3. [W3C Starting with HTML + CSS Tutorial](https://www.w3.org/Style/Examples/011/firstcss.en.html)

---

[⬅️ Previous Chapter](11-html-best-practices-and-accessibility.md) · [📚 Table of Contents](../SUMMARY.md) · **Next: Selectors, Colors, Units and Typography ➡️**
