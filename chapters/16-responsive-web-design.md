# 📱 Chapter 16: Responsive Web Design

![Level](https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-brightgreen)
![Course](https://img.shields.io/badge/Course-BCA-blue)
![Unit](https://img.shields.io/badge/Unit-CSS-purple)
![Language](https://img.shields.io/badge/Language-English%20%2B%20Hinglish-orange)

> [!TIP]
> **Chapter Goal:** Aisi website banana jo mobile, tablet, laptop, large screen, zoom aur different user preferences par readable aur usable rahe.

---

## 🎯 16.1 Learning Objectives

After completing this chapter, you will be able to:

1. Define Responsive Web Design.
2. Explain responsive, adaptive and fixed layouts.
3. Apply the mobile-first approach.
4. Configure viewport metadata.
5. Create fluid layouts with relative units.
6. Write media queries and choose content-based breakpoints.
7. Use Flexbox and Grid responsively.
8. Create responsive images using `srcset`, `sizes` and `picture`.
9. Apply fluid typography with `clamp()`.
10. Understand container queries.
11. Respect orientation, contrast and motion preferences.
12. Test a page across screen sizes and input modes.
13. Build a complete responsive landing page.

---

## 🗣️ 16.2 Difficult Words: Pronunciation and Meaning

| 🔤 Word | 🔊 Pronunciation | 💡 Simple Meaning |
|---|---|---|
| Responsive | रिस्पॉन्सिव — *ri-spon-siv* | Available space ke according adapt karna |
| Adaptive | अडैप्टिव — *uh-dap-tiv* | Selected layouts/sizes par switch karna |
| Viewport | व्यूपोर्ट — *vyoo-port* | Browser ka visible page area |
| Breakpoint | ब्रेकपॉइंट — *brayk-point* | Jahan layout change hota hai |
| Fluid | फ्लूइड — *floo-id* | Flexible size wala |
| Media Query | मीडिया क्वेरी — *mee-dee-uh kwe-ree* | Device/user condition based CSS rule |
| Orientation | ओरिएन्टेशन — *or-ee-en-tay-shun* | Portrait ya landscape direction |
| Intrinsic | इन्ट्रिन्सिक — *in-trin-zik* | Content ki natural size se related |
| Container | कन्टेनर — *kun-tay-ner* | Content ko hold karne wala box |
| Art Direction | आर्ट डायरेक्शन — *art dai-rek-shun* | Different layout ke liye different image crop/content |
| Resolution | रेजोल्यूशन — *rez-uh-loo-shun* | Image/display detail |
| Density | डेन्सिटी — *den-si-tee* | Device pixel concentration |
| Reflow | रीफ्लो — *ree-flow* | Content ka available space me rearrange hona |
| Progressive | प्रोग्रेसिव — *pro-gres-iv* | Basic se enhanced experience |
| Preference | प्रेफरेन्स — *pref-er-ens* | User ki chosen setting |

---

# 🟦 Part A: Responsive Design Fundamentals

## 💡 16.3 What Is Responsive Web Design?

### English Explanation

Responsive Web Design is an approach in which page structure, layout, media and typography adapt to the available viewport, container, device capabilities and user preferences.

### Hinglish Explanation

Responsive website screen ke size aur available space ke according apna layout adjust karti hai. Mobile par content readable stack ho sakta hai, aur wide screen par multiple columns me show ho sakta hai.

### Main Building Blocks

1. Flexible layouts
2. Flexible media
3. Media queries
4. Responsive typography
5. Content-based breakpoints
6. Accessible interaction
7. Performance-conscious delivery

---

## ⚖️ 16.4 Fixed, Fluid, Adaptive and Responsive Layouts

| Layout | Meaning |
|---|---|
| Fixed | Mainly fixed dimensions |
| Fluid | Relative dimensions with flexible space |
| Adaptive | Selected predefined layouts at ranges |
| Responsive | Fluid behavior plus conditional layout changes |

Modern websites often combine fluid and adaptive techniques under responsive design.

---

## 🌍 16.5 Why Responsive Design Matters

1. Mobile and desktop support
2. Better readability
3. Easier navigation
4. Less horizontal scrolling
5. Improved accessibility
6. One content system across devices
7. Better maintenance
8. Search and sharing consistency
9. Different input support
10. Future screen-size flexibility

> [!IMPORTANT]
> Responsive design ka meaning sirf “mobile site” nahi hai. Zoom, language, text length, orientation, input type and user preferences bhi matter karte hain.

---

# 🟩 Part B: Mobile-First Design

## 📱 16.6 What Is Mobile First?

Mobile-first CSS starts with a simple small-space layout. Wider-layout enhancements are added using minimum-width media queries.

Base:

```css
.course-grid {
    display: grid;
    gap: 1rem;
}
```

Enhancement:

```css
@media (min-width: 48rem) {
    .course-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

Larger:

```css
@media (min-width: 75rem) {
    .course-grid {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

---

## ✅ 16.7 Benefits of Mobile First

1. Essential content first
2. Simpler base styles
3. Progressive enhancement
4. Small-screen constraints considered early
5. Less overriding in many cases
6. Performance awareness
7. Touch and narrow-layout planning

> [!NOTE]
> Mobile-first is useful approach, but design should be tested across full range—not mobile only.

---

## 🧠 16.8 Content First

Ask:

1. Page ka primary task kya hai?
2. Which content essential hai?
3. Navigation narrow space me kaise work karegi?
4. Long headings wrap kaise karenge?
5. Forms one-column me usable hain?
6. Images useful or decorative?
7. Large tables ka fallback kya hai?
8. Slow network par page usable hai?

---

# 🟨 Part C: Viewport and Fluid Layouts

## 🖥️ 16.9 Viewport Metadata

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- `width=device-width` layout viewport ko device width ke according set karta hai.
- `initial-scale=1.0` initial zoom scale specify karta hai.

> [!WARNING]
> User zoom disable karne wale restrictive viewport values avoid karein.

---

## 📏 16.10 Fluid Width

```css
.container {
    width: min(90%, 70rem);
    margin-inline: auto;
}
```

This combines:

- Fluid percentage
- Maximum readable width
- Centering

---

## 📦 16.11 Responsive Box Sizing

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

Padding and border ko declared width me include karke overflow calculations easier hoti hain.

---

## 🖼️ 16.12 Flexible Images

```css
img,
svg,
video {
    display: block;
    max-width: 100%;
    height: auto;
}
```

Media container se wider hone se bachta hai while aspect ratio preserve kar sakta hai.

> [!NOTE]
> Embedded iframe ke liye aspect-ratio wrapper or direct sizing separately handle karni ho sakti hai.

---

## 📐 16.13 Aspect Ratio

```css
.video-wrapper {
    aspect-ratio: 16 / 9;
}

.video-wrapper iframe {
    width: 100%;
    height: 100%;
    border: 0;
}
```

---

## ↔️ 16.14 Logical Properties

```css
.card {
    margin-block: 1rem;
    padding-inline: 1.5rem;
}
```

Logical properties writing directions and internationalization me helpful hain.

---

# 🟪 Part D: Media Queries

## 💡 16.15 What Is a Media Query?

Media query CSS rules ko media conditions ke according apply karti hai.

Syntax:

```css
@media (condition) {
    /* Conditional CSS */
}
```

Example:

```css
@media (min-width: 48rem) {
    .layout {
        display: grid;
        grid-template-columns: 16rem 1fr;
    }
}
```

---

## 📺 16.16 Media Types

Common media types:

- `all`
- `screen`
- `print`
- `speech`

Example:

```css
@media print {
    nav,
    .video-player {
        display: none;
    }
}
```

Often media type omit karke feature query sufficient hai.

---

## 📐 16.17 Width Queries

Minimum width:

```css
@media (min-width: 48rem) {
    /* Wider layout */
}
```

Maximum width:

```css
@media (max-width: 47.999rem) {
    /* Narrow layout */
}
```

Range syntax:

```css
@media (30rem <= width < 60rem) {
    /* Middle range */
}
```

Target browser support check karein when using newer syntax.

---

## 🔗 16.18 Combining Conditions

AND:

```css
@media (min-width: 48rem) and (orientation: landscape) {
    /* Both conditions */
}
```

Comma means OR between queries:

```css
@media (max-width: 30rem), (orientation: portrait) {
    /* Either query */
}
```

NOT:

```css
@media not print {
    /* Not print media */
}
```

---

## 🧭 16.19 Orientation

```css
@media (orientation: landscape) {
    .gallery {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

> [!CAUTION]
> Orientation ko device type na samjhein. Window resize se orientation condition change ho sakti hai.

---

## 🖱️ 16.20 Pointer and Hover Features

```css
@media (hover: hover) and (pointer: fine) {
    .card:hover {
        transform: translateY(-4px);
    }
}
```

Possible values:

- `hover: hover`
- `hover: none`
- `pointer: fine`
- `pointer: coarse`
- `pointer: none`

> [!IMPORTANT]
> Important functionality hover-only na banayein. Touch and keyboard alternatives provide karein.

---

## 🌓 16.21 Color-Scheme Preference

```css
:root {
    color-scheme: light dark;
}

@media (prefers-color-scheme: dark) {
    body {
        background-color: #111827;
        color: #f9fafb;
    }
}
```

Ensure both schemes me contrast and component states test hon.

---

## 🌀 16.22 Reduced Motion Preference

```css
@media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
        scroll-behavior: auto;
        animation-duration: 0.01ms;
        animation-iteration-count: 1;
        transition-duration: 0.01ms;
    }
}
```

This is one strategy, but project-specific essential motion and behavior carefully review karein.

---

## 🎨 16.23 Contrast Preference

```css
@media (prefers-contrast: more) {
    .card {
        border-width: 2px;
    }
}
```

Support and exact behavior target browsers me test karein. Base design already readable hona chahiye.

---

## 🖨️ 16.24 Print Styles

```css
@media print {
    body {
        background: white;
        color: black;
        font-size: 12pt;
    }

    nav,
    button,
    .video-player {
        display: none;
    }

    a[href]::after {
        content: " (" attr(href) ")";
    }
}
```

Consider:

- Navigation remove
- Black text
- Page-break behavior
- Link destinations
- Unnecessary backgrounds
- Forms and interactive-only elements

---

# 🟥 Part E: Breakpoints

## 🎯 16.25 What Is a Breakpoint?

Breakpoint wo condition/range hai jahan layout ko meaningful change chahiye.

Bad approach:

```text
“Every phone at 480px, every tablet at 768px”
```

Better approach:

1. Start narrow.
2. Slowly viewport widen karein.
3. Jahan content awkward lage, breakpoint add karein.
4. Real content and long translations test karein.
5. Device brand ke instead content need follow karein.

---

## 📏 16.26 Breakpoint Units

`rem`-based breakpoints flexible design practice me commonly use hote hain:

```css
@media (min-width: 48rem) {
    /* Layout change */
}
```

Media-query `rem` evaluation behavior root styling se different standardized reference follow kar sakta hai; practical target browsers me test karein.

---

## 🚫 16.27 Too Many Breakpoints

Problems:

- Maintenance difficult
- Conflicting rules
- Device-specific hacks
- Inconsistent design

Use fewer meaningful breakpoints and fluid layout between them.

---

# 🟧 Part F: Responsive Flexbox and Grid

## 🧵 16.28 Responsive Flexbox

```css
.navigation {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

@media (min-width: 40rem) {
    .navigation {
        flex-direction: row;
        align-items: center;
    }
}
```

Sometimes query not needed:

```css
.navigation {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem 1rem;
}
```

---

## 🧱 16.29 Query-Free Responsive Grid

```css
.card-grid {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(min(100%, 16rem), 1fr));
    gap: 1rem;
}
```

Available space ke according columns automatically change hoti hain.

---

## 🗺️ 16.30 Grid Areas Across Breakpoints

Base:

```css
.page {
    display: grid;
    grid-template-areas:
        "header"
        "main"
        "sidebar"
        "footer";
}
```

Wide:

```css
@media (min-width: 60rem) {
    .page {
        grid-template-areas:
            "header header"
            "main sidebar"
            "footer footer";
        grid-template-columns: minmax(0, 1fr) 20rem;
    }
}
```

DOM order meaningful rehna chahiye even if visual areas change.

---

# 🟫 Part G: Responsive Images

## 🖼️ 16.31 Why Responsive Images?

One large image every device ko dene se:

- Data waste
- Slow loading
- Memory use
- Poor mobile experience

One small image large display par blurry ho sakti hai.

Responsive images suitable candidate choose karne me browser ko information deti hain.

---

## 📏 16.32 Width-Descriptor `srcset`

```html
<img
    src="images/campus-800.jpg"
    srcset="
        images/campus-400.jpg 400w,
        images/campus-800.jpg 800w,
        images/campus-1200.jpg 1200w"
    sizes="
        (max-width: 40rem) 100vw,
        (max-width: 70rem) 50vw,
        40rem"
    alt="Students walking outside the college building"
    width="1200"
    height="800">
```

- `srcset` candidates and intrinsic widths
- `sizes` expected rendered slot width
- Browser selects candidate based on layout and device conditions

> [!WARNING]
> `sizes` actual CSS layout ke close hona chahiye. Wrong sizes browser ko unnecessarily large/small candidate select karwa sakta hai.

---

## 🖥️ 16.33 Density Descriptor

```html
<img
    src="images/logo.png"
    srcset="
        images/logo.png 1x,
        images/logo@2x.png 2x"
    alt="ABC College"
    width="200"
    height="80">
```

Useful when rendered CSS dimensions fixed and density variants available.

Do not mix width and density descriptors in one `srcset`.

---

## 🎭 16.34 Art Direction with `picture`

Different crop/content at different conditions:

```html
<picture>
    <source
        media="(min-width: 60rem)"
        srcset="images/course-wide.jpg">

    <source
        media="(min-width: 35rem)"
        srcset="images/course-medium.jpg">

    <img
        src="images/course-portrait.jpg"
        alt="Student learning web development"
        width="800"
        height="1000">
</picture>
```

`img` is required fallback and carries alt text.

---

## 📦 16.35 Format Selection with `picture`

```html
<picture>
    <source
        type="image/avif"
        srcset="images/course.avif">
    <source
        type="image/webp"
        srcset="images/course.webp">
    <img
        src="images/course.jpg"
        alt="Laptop displaying HTML and CSS code"
        width="1200"
        height="800">
</picture>
```

Browser first supported suitable source choose kar sakta hai.

---

## 🐢 16.36 Image Loading

Off-screen image:

```html
<img
    src="images/gallery.jpg"
    alt="Students presenting a web project"
    width="1200"
    height="800"
    loading="lazy">
```

Important hero/LCP image ko blindly lazy load na karein.

Dimensions provide karna layout shift reduce kar sakta hai.

---

# 🟦 Part H: Fluid Typography and Spacing

## 🔤 16.37 Fluid Font Size

```css
h1 {
    font-size: clamp(2rem, 5vw, 4rem);
}
```

- Minimum: `2rem`
- Fluid preferred: `5vw`
- Maximum: `4rem`

---

## 📏 16.38 Fluid Spacing

```css
.section {
    padding-block: clamp(2rem, 6vw, 6rem);
    padding-inline: clamp(1rem, 4vw, 3rem);
}
```

Too many breakpoint overrides reduce ho sakte hain.

---

## 📖 16.39 Readable Text Width

```css
.article {
    width: min(90%, 70ch);
    margin-inline: auto;
}
```

Text column extremely wide na ho.

---

# 🟩 Part I: Container Queries

## 📦 16.40 Why Container Queries?

Media queries viewport conditions use karti hain. Reusable component kabhi sidebar me narrow aur main content me wide ho sakta hai.

Container query component ko its containing size ke according adapt karne deti hai.

---

## 🧱 16.41 Creating a Query Container

```css
.course-wrapper {
    container-type: inline-size;
    container-name: course-card;
}
```

Shorthand:

```css
.course-wrapper {
    container: course-card / inline-size;
}
```

---

## 🔍 16.42 Writing a Container Query

```css
.course-card {
    display: grid;
    gap: 1rem;
}

@container course-card (min-width: 32rem) {
    .course-card {
        grid-template-columns: 10rem 1fr;
        align-items: center;
    }
}
```

Component viewport ke instead its query container width par react karta hai.

---

## 📐 16.43 Container Query Units

```css
.course-title {
    font-size: clamp(1.25rem, 6cqi, 2rem);
}
```

`cqi` query container inline size ka 1%.

More:

- `cqw`
- `cqh`
- `cqb`
- `cqmin`
- `cqmax`

---

## ⚖️ 16.44 Media vs Container Queries

| Media Query | Container Query |
|---|---|
| Viewport/device/user media conditions | Ancestor query-container conditions |
| Page-level layout | Component-level adaptation |
| Dark mode, motion, print | Card/sidebar component sizing |
| Global responsive rules | Reusable component rules |

Both together use kiye ja sakte hain.

---

# 🟪 Part J: Responsive Navigation and Tables

## 🧭 16.45 Navigation

Simple wrapping navigation:

```css
.main-nav {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem 1rem;
}
```

Collapsible menu needs JavaScript and correct accessibility behavior:

- Real button
- `aria-expanded` state
- `aria-controls`
- Keyboard support
- Focus management
- Works without hover

Detailed scripting later.

---

## 📊 16.46 Responsive Tables

Wrapper:

```html
<div class="table-wrapper" tabindex="0">
    <table>
        ...
    </table>
</div>
```

```css
.table-wrapper {
    overflow-x: auto;
}
```

Caution:

- Scroll region keyboard accessible/check
- Caption and headers preserve
- Critical columns hide na karein
- Alternative summary consider karein
- `tabindex` only if needed and accessible-name/instructions considered

---

## 📝 16.47 Responsive Forms

```css
.form-grid {
    display: grid;
    gap: 1rem;
}

@media (min-width: 48rem) {
    .form-grid {
        grid-template-columns: repeat(2, 1fr);
    }

    .form-field.full-width {
        grid-column: 1 / -1;
    }
}
```

Form control basics:

```css
input,
select,
textarea,
button {
    max-width: 100%;
    font: inherit;
}
```

---

# 🟥 Part K: Testing

## 🧪 16.48 Responsive Testing Checklist

Test:

1. Narrow mobile width
2. Wide mobile landscape
3. Tablet-like width
4. Laptop
5. Large monitor
6. Browser zoom
7. Increased text size
8. Long translated text
9. Keyboard only
10. Touch/coarse pointer
11. Dark mode
12. Reduced motion
13. Slow network
14. Images disabled/failing
15. Print preview

---

## 🧰 16.49 Browser Developer Tools

Use responsive/device mode to:

- Resize viewport continuously
- Inspect breakpoints
- Simulate orientation
- Check overflow
- Test DPR/device scale approximately
- Throttle network
- Inspect image selection
- Emulate media preferences where supported

> [!IMPORTANT]
> Device emulation useful hai, but real devices and real users testing ka replacement nahi hai.

---

## 🔎 16.50 Finding Horizontal Overflow

Temporary debug style:

```css
* {
    outline: 1px solid red;
}
```

Inspect common causes:

- Fixed width
- Long unbroken text
- Image without max-width
- Grid track minimum too large
- Negative margins
- Positioned element
- `100vw` plus scrollbar/padding
- Large preformatted code

Remove debug rule after testing.

---

# 🟧 Part L: Complete Responsive Landing Page

## 🧪 16.51 HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web Technology Course | BCA Learning Hub</title>
    <link rel="stylesheet" href="css/responsive.css">
</head>
<body>
    <a class="skip-link" href="#main-content">
        Skip to main content
    </a>

    <header class="site-header">
        <a class="brand" href="index.html">
            BCA Learning Hub
        </a>

        <nav class="main-nav" aria-label="Main navigation">
            <a href="#features">Features</a>
            <a href="#chapters">Chapters</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <main id="main-content">
        <section class="hero">
            <div class="hero-content">
                <p class="eyebrow">Beginner to Advanced</p>
                <h1>Learn Web Technology Step by Step</h1>
                <p>
                    Master HTML, CSS, JavaScript, PHP and MySQL
                    through bilingual explanations and practical projects.
                </p>

                <div class="hero-actions">
                    <a class="button primary" href="#chapters">
                        Start Learning
                    </a>
                    <a class="button secondary" href="syllabus.html">
                        View Syllabus
                    </a>
                </div>
            </div>

            <picture class="hero-media">
                <source
                    media="(min-width: 60rem)"
                    srcset="images/course-wide.webp">
                <img
                    src="images/course-mobile.webp"
                    alt="Student learning web development on a laptop"
                    width="800"
                    height="900">
            </picture>
        </section>

        <section id="features" class="section">
            <div class="section-heading">
                <p class="eyebrow">Course Benefits</p>
                <h2>Designed for BCA Beginners</h2>
            </div>

            <div class="feature-grid">
                <article class="feature-card">
                    <h3>Simple Language</h3>
                    <p>English and Hinglish explanations.</p>
                </article>

                <article class="feature-card">
                    <h3>Practical Code</h3>
                    <p>Complete working examples and exercises.</p>
                </article>

                <article class="feature-card">
                    <h3>Exam Preparation</h3>
                    <p>MCQs, viva and long-answer questions.</p>
                </article>
            </div>
        </section>

        <section id="chapters" class="section chapter-section">
            <div class="section-heading">
                <p class="eyebrow">Learning Path</p>
                <h2>Course Chapters</h2>
            </div>

            <div class="chapter-grid">
                <article class="chapter-card">
                    <span>Unit 1</span>
                    <h3>Web Foundations</h3>
                    <p>Internet, servers, URLs and HTTP.</p>
                    <a href="unit-1.html">Open Unit 1</a>
                </article>

                <article class="chapter-card">
                    <span>Unit 2</span>
                    <h3>HTML</h3>
                    <p>Semantic and accessible page structure.</p>
                    <a href="unit-2.html">Open Unit 2</a>
                </article>

                <article class="chapter-card">
                    <span>Unit 3</span>
                    <h3>CSS</h3>
                    <p>Responsive visual design and layout.</p>
                    <a href="unit-3.html">Open Unit 3</a>
                </article>
            </div>
        </section>

        <section id="contact" class="section contact-section">
            <div>
                <h2>Ready to Start?</h2>
                <p>Begin your complete Web Technology journey.</p>
            </div>
            <a class="button primary" href="chapter-1.html">
                Read Chapter 1
            </a>
        </section>
    </main>

    <footer class="site-footer">
        <p>&copy; 2026 BCA Learning Hub</p>
    </footer>
</body>
</html>
```

---

## 🎨 16.52 CSS

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}

:root {
    color-scheme: light;
    --primary: #123a70;
    --primary-dark: #0b274b;
    --accent: #005fcc;
    --page: #f4f7fb;
    --surface: #ffffff;
    --text: #1f2937;
    --muted: #4b5563;
    --border: #cbd5e1;
    --focus: #ffbf47;
}

html {
    scroll-behavior: smooth;
}

body {
    margin: 0;
    background-color: var(--page);
    color: var(--text);
    font-family: system-ui, sans-serif;
    line-height: 1.6;
}

img,
picture {
    display: block;
    max-width: 100%;
}

img {
    height: auto;
}

.skip-link {
    position: fixed;
    z-index: 1000;
    top: -5rem;
    left: 1rem;
    padding: 0.75rem 1rem;
    background-color: #ffffff;
    color: #000000;
}

.skip-link:focus {
    top: 1rem;
}

.site-header {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    padding: 1rem max(1rem, 5vw);
    background-color: var(--primary-dark);
    color: #ffffff;
}

.brand {
    color: #ffffff;
    font-size: 1.25rem;
    font-weight: 800;
    text-decoration: none;
}

.main-nav {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem 1rem;
}

.main-nav a {
    padding: 0.4rem;
    color: #ffffff;
}

.hero {
    display: grid;
    gap: 2rem;
    align-items: center;
    padding:
        clamp(2rem, 8vw, 6rem)
        max(1rem, 5vw);
    background-color: #e8f0ff;
}

.hero-content {
    max-width: 42rem;
}

.eyebrow {
    color: var(--accent);
    font-weight: 800;
    letter-spacing: 0.08em;
    text-transform: uppercase;
}

h1 {
    margin-block: 0.5rem;
    color: var(--primary);
    font-size: clamp(2.25rem, 8vw, 5rem);
    line-height: 1.05;
}

h2 {
    color: var(--primary);
    font-size: clamp(1.75rem, 4vw, 3rem);
    line-height: 1.15;
}

.hero-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    margin-top: 1.5rem;
}

.button {
    display: inline-block;
    padding: 0.8rem 1.1rem;
    border: 2px solid var(--accent);
    border-radius: 0.5rem;
    font-weight: 750;
    text-decoration: none;
}

.button.primary {
    background-color: var(--accent);
    color: #ffffff;
}

.button.secondary {
    background-color: transparent;
    color: var(--accent);
}

.hero-media img {
    width: 100%;
    max-height: 32rem;
    border-radius: 1rem;
    object-fit: cover;
}

.section {
    padding:
        clamp(3rem, 8vw, 7rem)
        max(1rem, 5vw);
}

.section-heading {
    max-width: 48rem;
    margin-bottom: 2rem;
}

.feature-grid,
.chapter-grid {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(min(100%, 16rem), 1fr));
    gap: 1rem;
}

.feature-card,
.chapter-card {
    padding: clamp(1.25rem, 4vw, 2rem);
    border: 1px solid var(--border);
    border-radius: 1rem;
    background-color: var(--surface);
    box-shadow: 0 6px 18px rgb(15 23 42 / 8%);
}

.chapter-section {
    background-color: #e8f0ff;
}

.chapter-card {
    display: flex;
    flex-direction: column;
}

.chapter-card a {
    margin-top: auto;
    color: var(--accent);
    font-weight: 700;
}

.contact-section {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    align-items: flex-start;
    justify-content: space-between;
}

.site-footer {
    padding: 1.5rem max(1rem, 5vw);
    background-color: var(--primary-dark);
    color: #ffffff;
    text-align: center;
}

a:focus-visible {
    outline: 3px solid var(--focus);
    outline-offset: 3px;
}

/* Wider layout enhancements */
@media (min-width: 48rem) {
    .site-header {
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }

    .contact-section {
        flex-direction: row;
        align-items: center;
    }
}

@media (min-width: 60rem) {
    .hero {
        grid-template-columns: minmax(0, 1.1fr) minmax(20rem, 0.9fr);
    }
}

/* User preference */
@media (prefers-reduced-motion: reduce) {
    html {
        scroll-behavior: auto;
    }
}

/* Print */
@media print {
    .site-header,
    .hero-actions,
    .site-footer {
        display: none;
    }

    body {
        background: white;
        color: black;
    }

    .section,
    .hero {
        padding: 1rem 0;
        background: white;
    }
}
```

---

## ♿ 16.53 Accessibility and Performance Checklist

1. Mobile-first content order meaningful ho.
2. Zoom and text resize work kare.
3. Horizontal scrolling avoid ho except data regions.
4. Focus visible ho.
5. Touch targets usable hon.
6. Hover-only functionality na ho.
7. Images have correct alt and dimensions.
8. Hero image unnecessarily huge na ho.
9. Reduced-motion preference respect ho.
10. Dark scheme applicable ho to contrast test ho.
11. Breakpoints content-driven hon.
12. DOM order visual order se logical rahe.
13. Forms stack and labels visible rahen.
14. Slow network par essential content available ho.
15. Print output important content preserve kare.

---

## 🚫 16.54 Common Mistakes

1. Viewport meta omit karna.
2. User zoom disable karna.
3. Only device-name breakpoints use karna.
4. Fixed desktop width on mobile.
5. Images ko max-width na dena.
6. Every change ke liye breakpoint add karna.
7. Mobile-first bolkar desktop test na karna.
8. `100vh` mobile controls issue ignore karna.
9. Navigation hover-only banana.
10. `sizes` attribute actual layout se mismatch.
11. Hero image lazy load karna without testing.
12. Visual CSS reorder se DOM order confuse karna.
13. Container query without container define karna.
14. Long words and translations test na karna.
15. Emulator ko real-device testing ka complete replacement samajhna.

---

## 📌 16.55 Key Points to Remember

- Responsive design available space and preferences ke according adapt karta hai.
- Viewport metadata mobile layout ke liye important hai.
- Mobile-first base styles narrow screens se start hoti hain.
- Fluid widths relative units use karti hain.
- Media queries conditional CSS apply karti hain.
- Breakpoints content ke according choose karein.
- Flexbox and Grid responsive layouts support karte hain.
- `auto-fit` and `minmax()` query-free grids create kar sakte hain.
- `srcset` and `sizes` responsive image candidates guide karte hain.
- `picture` art direction and format selection support karta hai.
- `clamp()` bounded fluid size create karta hai.
- Container queries component size par react karti hain.
- Real responsiveness includes zoom, keyboard, motion and network.

---

## 📝 16.56 Chapter Summary

Responsive Web Design creates pages that adapt to available space, device capabilities and user preferences. A mobile-first approach establishes a simple narrow layout and progressively enhances it. Viewport metadata, flexible dimensions, responsive media and box sizing form the foundation. Media queries apply conditional rules based on width, orientation, pointer, color scheme, motion and other features. Content-based breakpoints are more durable than device-specific assumptions. Flexbox, Grid, relative units and CSS math functions create fluid layouts. Responsive images use `srcset`, `sizes` and `picture` to deliver suitable resources. Container queries allow reusable components to respond to their own available space. Effective testing includes continuous resizing, zoom, keyboard, preferences, slow networks and real devices.

---

## 🎲 16.57 Multiple-Choice Questions

### 1. Which approach starts with narrow-screen base styles?

A. Desktop-only  
B. Mobile-first  
C. Print-only  
D. Fixed-only  

**✅ Answer:** B

### 2. Which metadata configures the layout viewport?

A. Charset  
B. Viewport meta  
C. Description only  
D. Author meta  

**✅ Answer:** B

### 3. Which at-rule creates a media query?

A. `@screen`  
B. `@media`  
C. `@responsive`  
D. `@device`  

**✅ Answer:** B

### 4. Breakpoints should primarily follow:

A. Device brand names  
B. Content and layout needs  
C. Random numbers  
D. Browser color  

**✅ Answer:** B

### 5. Which property prevents an image from exceeding its container?

A. `min-width: 100%`  
B. `max-width: 100%`  
C. `height: 100vw`  
D. `position: fixed`  

**✅ Answer:** B

### 6. Which function creates bounded fluid values?

A. `repeat()`  
B. `clamp()`  
C. `rgb()`  
D. `url()`  

**✅ Answer:** B

### 7. Which image attribute lists width candidates?

A. `alt`  
B. `srcset`  
C. `class`  
D. `loading` only  

**✅ Answer:** B

### 8. Which element supports art direction?

A. `picture`  
B. `figure` only  
C. `canvas`  
D. `table`  

**✅ Answer:** A

### 9. Container queries respond mainly to:

A. A query container  
B. Database size  
C. File name  
D. DNS record  

**✅ Answer:** A

### 10. Which query respects reduced-motion preference?

A. `prefers-reduced-motion`  
B. `motion-off`  
C. `no-animation`  
D. `slow-device`  

**✅ Answer:** A

---

## ✍️ 16.58 Fill in the Blanks

1. The browser's visible area is called the __________.
2. A layout-change condition is a __________.
3. Responsive image candidates are listed in __________.
4. `clamp()` accepts minimum, preferred and __________ values.
5. Component-size queries are called __________ queries.

<details>
<summary><strong>✅ View Answers</strong></summary>

1. viewport  
2. breakpoint  
3. `srcset`  
4. maximum  
5. container

</details>

---

## ✅ 16.59 True or False

1. Responsive design only means mobile support.
2. User zoom should be disabled.
3. Breakpoints can be based on content needs.
4. Media queries can detect print.
5. Hover is available on every device.
6. `srcset` can provide multiple image candidates.
7. `picture` requires an `img` fallback.
8. Container queries always use viewport width.
9. Real-device testing remains useful.
10. CSS Grid can be responsive without media queries.

<details>
<summary><strong>✅ View Answers</strong></summary>

1. False  
2. False  
3. True  
4. True  
5. False  
6. True  
7. True  
8. False  
9. True  
10. True

</details>

---

## ❓ 16.60 Short-Answer Questions

1. Define Responsive Web Design.
2. Differentiate fixed, fluid and responsive layouts.
3. What is mobile-first design?
4. Explain viewport metadata.
5. What is a media query?
6. Define a breakpoint.
7. Why should breakpoints be content-driven?
8. Explain pointer and hover queries.
9. What is reduced-motion preference?
10. Explain responsive Grid.
11. What are `srcset` and `sizes`?
12. What is art direction?
13. Explain `picture`.
14. What is fluid typography?
15. Define a container query.

---

## 📚 16.61 Long-Answer and Exam Questions

1. Define Responsive Web Design and explain its importance.
2. Explain the mobile-first approach.
3. Explain viewport metadata and fluid layout techniques.
4. Describe media-query syntax and features.
5. Explain how to select breakpoints.
6. Discuss responsive Flexbox and Grid patterns.
7. Explain responsive images using `srcset` and `sizes`.
8. Explain the `picture` element for art direction and formats.
9. Explain fluid typography and spacing.
10. Define container queries and compare them with media queries.
11. Discuss responsive accessibility and performance.
12. Create and explain a complete responsive landing page.

---

## 🧪 16.62 Practical Exercises

1. Add viewport metadata.
2. Create a fluid centered container.
3. Make all images flexible.
4. Write mobile-first navigation.
5. Add two content-based breakpoints.
6. Create responsive Flexbox cards.
7. Create auto-fit Grid cards.
8. Build responsive named Grid areas.
9. Use clamp for heading and spacing.
10. Create `srcset` with three image sizes.
11. Create art direction with `picture`.
12. Add dark-mode preference.
13. Add reduced-motion preference.
14. Create a container-query card.
15. Build the complete landing page.
16. Test zoom, keyboard, slow network and print.

---

## 🎤 16.63 Viva Questions

1. What is Responsive Web Design?
2. What is mobile first?
3. What is a viewport?
4. Why is viewport meta required?
5. What is a breakpoint?
6. What is a media query?
7. How is a min-width query written?
8. What does auto-fit do?
9. What does `srcset` contain?
10. What does `sizes` describe?
11. What is `picture` used for?
12. What does `clamp()` do?
13. What is a container query?
14. What is reduced motion?
15. Is emulator testing sufficient alone?

<details>
<summary><strong>✅ View Short Viva Answers</strong></summary>

1. An approach that adapts layout and content presentation.  
2. Starting with narrow-layout base styles.  
3. The browser's visible page area.  
4. To configure mobile layout viewport behavior.  
5. A condition where layout changes.  
6. Conditional CSS based on media features.  
7. `@media (min-width: value)`.  
8. Creates/fits repeated tracks and collapses unused ones.  
9. Image candidates and descriptors.  
10. Expected rendered image slot size.  
11. Art direction or format selection.  
12. Bounds a preferred value between min and max.  
13. CSS based on a query container's conditions.  
14. A user preference requesting less motion.  
15. No.

</details>

---

## 🏁 16.64 One-Minute Revision

| Question | Quick Answer |
|---|---|
| Responsive design? | Layout adapts |
| Narrow-first? | Mobile first |
| Visible browser area? | Viewport |
| Conditional CSS? | Media query |
| Change point? | Breakpoint |
| Flexible width? | %, min(), max-width |
| Responsive cards? | auto-fit + minmax |
| Image candidates? | `srcset` |
| Image slot hint? | `sizes` |
| Art direction? | `picture` |
| Fluid bounded size? | `clamp()` |
| Component responsive? | Container query |
| Motion preference? | `prefers-reduced-motion` |
| Theme preference? | `prefers-color-scheme` |
| Complete testing? | Emulation + real devices/users |

---

## 📚 16.65 Official References

1. [W3C Media Queries](https://www.w3.org/TR/mediaqueries-5/)
2. [W3C CSS Containment](https://www.w3.org/TR/css-contain-3/)
3. [W3C CSS Images](https://www.w3.org/TR/css-images-4/)
4. [WHATWG Responsive Images](https://html.spec.whatwg.org/multipage/images.html)
5. [W3C CSS Values and Units](https://www.w3.org/TR/css-values-4/)

---

[⬅️ Previous Chapter](15-flexbox-and-css-grid.md) · [📚 Table of Contents](../SUMMARY.md) · **Next: Transitions, Transformations and Animations ➡️**
