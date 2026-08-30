# ✨ Chapter 17: Transitions, Transformations and Animations

![Level](https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-brightgreen)
![Course](https://img.shields.io/badge/Course-BCA-blue)
![Unit](https://img.shields.io/badge/Unit-CSS-purple)
![Language](https://img.shields.io/badge/Language-English%20%2B%20Hinglish-orange)

> [!TIP]
> **Chapter Goal:** CSS se meaningful, smooth aur accessible motion create karna—without page usability aur performance ko harm kiye.

---

## 🎯 17.1 Learning Objectives

After completing this chapter, you will be able to:

1. Define CSS transitions.
2. Configure transition property, duration, timing and delay.
3. Use common timing functions.
4. Apply 2D translate, scale, rotate and skew transforms.
5. Understand transform order and origin.
6. Apply basic 3D transforms and perspective.
7. Define animations using `@keyframes`.
8. Configure animation duration, iteration, direction and fill mode.
9. Pause and combine animations.
10. Improve animation performance.
11. Respect reduced-motion preferences.
12. Build an animated course-card interface.

---

## 🗣️ 17.2 Difficult Words: Pronunciation and Meaning

| 🔤 Word | 🔊 Pronunciation | 💡 Simple Meaning |
|---|---|---|
| Transition | ट्रांजिशन — *tran-zish-un* | One state se another state ka smooth change |
| Transformation | ट्रांसफॉर्मेशन — *trans-for-may-shun* | Element ka visual shape/position change |
| Animation | ऐनिमेशन — *an-i-may-shun* | Time ke saath multiple style changes |
| Duration | ड्यूरेशन — *dyoo-ray-shun* | Effect kitni der chalega |
| Delay | डिले — *di-lay* | Start se pehle wait time |
| Timing Function | टाइमिंग फंक्शन — *tai-ming funk-shun* | Change ki speed curve |
| Interpolation | इन्टरपोलेशन — *in-ter-puh-lay-shun* | Start-end ke beech values calculate karna |
| Translate | ट्रांसलेट — *trans-layt* | Element ko move karna |
| Scale | स्केल — *skayl* | Size visually change karna |
| Rotate | रोटेट — *roh-tayt* | Element ko ghumana |
| Skew | स्क्यू — *skyoo* | Element ko angle par slant karna |
| Perspective | पर्सपेक्टिव — *per-spek-tiv* | 3D depth ka visual effect |
| Keyframe | कीफ्रेम — *kee-frame* | Animation ka defined stage |
| Iteration | इटरेशन — *it-uh-ray-shun* | Repeat count |
| Composite | कम्पॉजिट — *kom-puh-zit* | Visual layers ko combine karna |

---

# 🟦 Part A: CSS Transitions

## 💡 17.3 What Is a Transition?

A CSS transition creates an interpolated change between an element property's old and new values when the property changes.

Without transition:

```css
.button {
    background-color: blue;
}

.button:hover {
    background-color: darkblue;
}
```

With transition:

```css
.button {
    background-color: blue;
    transition: background-color 250ms ease;
}

.button:hover {
    background-color: darkblue;
}
```

### Hinglish Explanation

Normal CSS state instantly change hoti hai. Transition start aur end state ke beech smooth intermediate values create karti hai.

---

## ⚙️ 17.4 Transition Properties

| Property | Purpose |
|---|---|
| `transition-property` | Kaunsi property animate hogi |
| `transition-duration` | Change ka time |
| `transition-timing-function` | Speed curve |
| `transition-delay` | Start delay |
| `transition` | Shorthand |

---

## 🎯 17.5 `transition-property`

```css
.card {
    transition-property: transform;
}
```

Multiple:

```css
.card {
    transition-property: transform, box-shadow;
}
```

All animatable changed properties:

```css
.card {
    transition-property: all;
}
```

> [!WARNING]
> `transition: all` convenient hai but unintended properties animate kar sakta hai. Required properties explicitly list karna generally safer and clearer hai.

---

## ⏱️ 17.6 `transition-duration`

```css
.button {
    transition-duration: 250ms;
}
```

Units:

- `s` — seconds
- `ms` — milliseconds

```text
1s = 1000ms
```

Duration zero ho to visible smooth transition nahi hoti.

---

## 📈 17.7 Timing Functions

```css
.button {
    transition-timing-function: ease;
}
```

Common values:

| Value | Basic Behavior |
|---|---|
| `linear` | Constant rate |
| `ease` | Slow-fast-slow default-like curve |
| `ease-in` | Slow start |
| `ease-out` | Slow end |
| `ease-in-out` | Slow start and end |
| `cubic-bezier()` | Custom curve |
| `steps()` | Discrete steps |

Example:

```css
.card {
    transition-timing-function:
        cubic-bezier(0.2, 0.8, 0.2, 1);
}
```

---

## ⏳ 17.8 Transition Delay

```css
.tooltip {
    transition-delay: 300ms;
}
```

Delay effect start se pehle wait karta hai.

> [!CAUTION]
> Long delays controls ko slow/unresponsive feel kara sakte hain.

---

## 🧩 17.9 Transition Shorthand

```css
.button {
    transition: background-color 200ms ease-out 0ms;
}
```

Common order:

```text
property | duration | timing function | delay
```

Multiple transitions:

```css
.card {
    transition:
        transform 200ms ease-out,
        box-shadow 200ms ease-out,
        border-color 200ms linear;
}
```

---

## 🖱️ 17.10 Transition States

Hover:

```css
.card:hover {
    transform: translateY(-4px);
}
```

Focus:

```css
.card:focus-within {
    border-color: #005fcc;
}
```

Checked:

```css
input:checked + .switch-control {
    background-color: #005fcc;
}
```

Class/state change:

```css
.panel {
    opacity: 0;
}

.panel.is-open {
    opacity: 1;
}
```

Class typically JavaScript se toggle ho sakti hai.

---

## 🚫 17.11 Properties That Do Not Interpolate Smoothly

Every CSS property smoothly interpolate nahi hoti.

Example:

```css
.menu {
    display: none;
}

.menu.open {
    display: block;
}
```

`display` traditionally intermediate visual values nahi banata in simple transition use. Modern discrete-transition features exist, but target support and exact behavior verify karein.

Beginner pattern may animate opacity/transform while visibility and interaction state carefully manage ki jati hai.

> [!IMPORTANT]
> Hidden element keyboard-focusable accidentally na rahe. Visual animation ke saath semantic/interaction state coordinate karein.

---

# 🟩 Part B: 2D Transforms

## 💡 17.12 What Is a Transform?

CSS transform element ko visually translate, rotate, scale or skew karta hai without normal-flow space ko same way recalculate kiye.

```css
.card {
    transform: translateX(20px);
}
```

The element's original layout space generally remains.

---

## ↔️ 17.13 Translate

```css
.box {
    transform: translateX(20px);
}
```

Vertical:

```css
.box {
    transform: translateY(-10px);
}
```

Both:

```css
.box {
    transform: translate(20px, -10px);
}
```

Percentages often element's own reference box par depend karte hain:

```css
.box {
    transform: translateX(50%);
}
```

---

## 🔍 17.14 Scale

```css
.card {
    transform: scale(1.05);
}
```

Horizontal/vertical:

```css
.box {
    transform: scaleX(1.2);
}

.box {
    transform: scaleY(0.8);
}

.box {
    transform: scale(1.2, 0.8);
}
```

> [!CAUTION]
> Large scale nearby content cover kar sakta hai because normal layout space update nahi hota.

---

## 🔄 17.15 Rotate

```css
.icon {
    transform: rotate(45deg);
}
```

Angle units include:

- `deg`
- `rad`
- `turn`
- `grad`

Examples:

```css
transform: rotate(0.25turn);
transform: rotate(90deg);
```

---

## 📐 17.16 Skew

```css
.shape {
    transform: skewX(15deg);
}

.shape {
    transform: skewY(-10deg);
}

.shape {
    transform: skew(15deg, -10deg);
}
```

Text-heavy content ko skew karna readability reduce kar sakta hai.

---

## 🔗 17.17 Combining Transforms

```css
.card {
    transform:
        translateY(-4px)
        scale(1.02)
        rotate(1deg);
}
```

> [!IMPORTANT]
> Transform functions ka order result affect karta hai.

Compare:

```css
.a {
    transform: translateX(100px) rotate(45deg);
}

.b {
    transform: rotate(45deg) translateX(100px);
}
```

Transform operations sequence me apply hoti hain; coordinate system behavior ki wajah se outputs different ho sakte hain.

---

## 🎯 17.18 Transform Origin

Default origin commonly center hota hai.

```css
.door {
    transform-origin: left center;
    transform: rotateY(45deg);
}
```

Values:

- Keywords: `center`, `top`, `left`
- Percentages
- Lengths
- 3D z-offset where applicable

---

## 🧩 17.19 Individual Transform Properties

Modern CSS individual properties provide karti hai:

```css
.card {
    translate: 0 -4px;
    scale: 1.02;
    rotate: 1deg;
}
```

This can make independent state changes easier. Target browser requirements test karein.

---

# 🟨 Part C: 3D Transforms

## 🧊 17.20 3D Translation

```css
.card {
    transform: translateZ(50px);
}
```

Combined:

```css
.card {
    transform: translate3d(20px, 10px, 50px);
}
```

Visible depth typically perspective context require karti hai.

---

## 🔄 17.21 3D Rotation

```css
.card {
    transform: rotateX(20deg);
}

.card {
    transform: rotateY(30deg);
}

.card {
    transform: rotateZ(15deg);
}
```

---

## 👁️ 17.22 Perspective

On parent:

```css
.scene {
    perspective: 800px;
}
```

Child:

```css
.card {
    transform: rotateY(30deg);
}
```

Smaller perspective distance generally stronger depth effect create karta hai.

Transform function:

```css
.card {
    transform: perspective(800px) rotateY(30deg);
}
```

Property and transform-function perspective application context differ kar sakte hain.

---

## 🧱 17.23 Preserve 3D

```css
.card {
    transform-style: preserve-3d;
}
```

Nested children ko shared 3D space me preserve karne ke liye useful.

---

## 🙈 17.24 Backface Visibility

```css
.card-face {
    backface-visibility: hidden;
}
```

Card-flip interfaces me back side hide karne ke liye.

---

## 🃏 17.25 Basic Flip Card Structure

HTML:

```html
<div class="scene">
    <div class="flip-card">
        <div class="card-face card-front">Front</div>
        <div class="card-face card-back">Back</div>
    </div>
</div>
```

CSS:

```css
.scene {
    perspective: 900px;
}

.flip-card {
    position: relative;
    transform-style: preserve-3d;
    transition: transform 500ms ease;
}

.flip-card.is-flipped {
    transform: rotateY(180deg);
}

.card-face {
    position: absolute;
    inset: 0;
    backface-visibility: hidden;
}

.card-back {
    transform: rotateY(180deg);
}
```

> [!WARNING]
> Hover-only flip content keyboard/touch users ke liye inaccessible ho sakta hai. Real button, state and focus management required hai.

---

# 🟪 Part D: CSS Animations

## 💡 17.26 What Is a CSS Animation?

CSS animation keyframes ke through one or more style stages ko time ke saath apply karti hai.

Unlike a simple transition, animation:

- Multiple stages define kar sakti hai.
- Automatically start ho sakti hai.
- Repeat ho sakti hai.
- Alternate direction use kar sakti hai.
- Pause/resume state support karti hai.

---

## 🎞️ 17.27 Defining Keyframes

From/to:

```css
@keyframes fade-in {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

Percentages:

```css
@keyframes move-and-fade {
    0% {
        opacity: 0;
        transform: translateY(20px);
    }

    60% {
        opacity: 1;
    }

    100% {
        transform: translateY(0);
    }
}
```

---

## ▶️ 17.28 Applying an Animation

```css
.card {
    animation-name: fade-in;
    animation-duration: 500ms;
}
```

---

## ⚙️ 17.29 Animation Properties

| Property | Purpose |
|---|---|
| `animation-name` | Keyframes name |
| `animation-duration` | One cycle time |
| `animation-timing-function` | Speed curve |
| `animation-delay` | Start delay |
| `animation-iteration-count` | Repeat count |
| `animation-direction` | Cycle direction |
| `animation-fill-mode` | Before/after keyframe styles |
| `animation-play-state` | Running or paused |
| `animation` | Shorthand |

---

## 🔁 17.30 Iteration Count

```css
.loader {
    animation-iteration-count: infinite;
}
```

Finite:

```css
.notice {
    animation-iteration-count: 3;
}
```

> [!CAUTION]
> Continuous motion distract kar sakti hai. Essential purpose and user control consider karein.

---

## ↔️ 17.31 Animation Direction

```css
.box {
    animation-direction: alternate;
}
```

Values:

- `normal`
- `reverse`
- `alternate`
- `alternate-reverse`

---

## 🎨 17.32 Fill Mode

```css
.card {
    animation-fill-mode: both;
}
```

Values:

| Value | Behavior |
|---|---|
| `none` | Default animation outside styles not retained |
| `forwards` | End-applied values retain according to animation state |
| `backwards` | Delay period me initial keyframe style apply |
| `both` | Both directions |

---

## ⏸️ 17.33 Play State

```css
.animation {
    animation-play-state: paused;
}

.animation.is-running {
    animation-play-state: running;
}
```

Real pause control ke liye accessible button and JavaScript state update needed hai.

---

## 🧩 17.34 Animation Shorthand

```css
.card {
    animation:
        fade-in
        500ms
        ease-out
        100ms
        1
        normal
        both;
}
```

Multiple animations:

```css
.badge {
    animation:
        fade-in 300ms ease-out both,
        pulse 2s ease-in-out 300ms infinite alternate;
}
```

Shorthand order can be tricky; longhand clearer ho sakta hai.

---

## ⏱️ 17.35 Negative Animation Delay

```css
.item {
    animation-delay: -500ms;
}
```

Animation as if already 500ms progress ho chuki ho, aise start ho sakti hai.

---

## 🪜 17.36 Steps Timing

```css
.sprite {
    animation:
        play-sprite
        1s
        steps(8)
        infinite;
}
```

Useful for:

- Sprite sheets
- Typewriter-like visual steps
- Discrete frame animation

---

## 📜 17.37 Scroll-Driven Animations Introduction

Modern CSS scroll/view timelines ke through scroll progress based animation capabilities provide kar sakti hai.

Conceptual example:

```css
.progress {
    animation-name: grow;
    animation-timeline: scroll();
}
```

> [!NOTE]
> Scroll-driven animation features ke current target-browser support and accessibility behavior verify karein. Progressive enhancement use karein.

---

# 🟥 Part E: Practical Motion Patterns

## 🔘 17.38 Button Transition

```css
.button {
    transition:
        background-color 180ms ease-out,
        transform 180ms ease-out;
}

.button:hover {
    background-color: #004a9f;
    transform: translateY(-2px);
}

.button:active {
    transform: translateY(0);
}

.button:focus-visible {
    outline: 3px solid #ffbf47;
    outline-offset: 3px;
}
```

Important state only hover par depend na ho.

---

## 📦 17.39 Card Lift

```css
.card {
    transition:
        transform 200ms ease-out,
        box-shadow 200ms ease-out;
}

.card:hover,
.card:focus-within {
    transform: translateY(-4px);
    box-shadow: 0 12px 30px rgb(15 23 42 / 15%);
}
```

---

## ⏳ 17.40 Loading Spinner

HTML:

```html
<span class="spinner" aria-hidden="true"></span>
<span>Loading course data…</span>
```

CSS:

```css
.spinner {
    display: inline-block;
    width: 1.25rem;
    height: 1.25rem;
    border: 3px solid #cbd5e1;
    border-top-color: #005fcc;
    border-radius: 50%;
    animation: spin 800ms linear infinite;
}

@keyframes spin {
    to {
        transform: rotate(1turn);
    }
}
```

Visible text or accessible status should communicate loading—not spinner alone.

---

## ✨ 17.41 Entrance Animation

```css
@keyframes enter {
    from {
        opacity: 0;
        transform: translateY(1rem);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.course-card {
    animation: enter 450ms ease-out both;
}
```

---

## 🌊 17.42 Pulse Animation

```css
@keyframes pulse {
    50% {
        transform: scale(1.05);
    }
}

.notification {
    animation: pulse 1.5s ease-in-out infinite;
}
```

> [!WARNING]
> Infinite pulse distraction create kar sakta hai. Limited cycles or user control prefer karein.

---

# 🟧 Part F: Performance

## ⚡ 17.43 Rendering Pipeline Basics

Visual updates may involve:

1. Style calculation
2. Layout
3. Paint
4. Compositing

Not every property exact same cost rakhti hai.

Animations using `transform` and `opacity` often layout avoid kar sakti hain and may be compositor-friendly, but performance device and page complexity par depend karti hai.

---

## ✅ 17.44 Prefer Transform and Opacity Where Suitable

Better movement pattern:

```css
.card {
    transform: translateX(100px);
    opacity: 0.5;
}
```

Potentially more layout work:

```css
.card {
    left: 100px;
    width: 500px;
}
```

> [!NOTE]
> Correct property design need ke according choose karein. Performance rule ko semantic/layout correctness par blindly prioritize na karein.

---

## 🧠 17.45 `will-change`

```css
.dragging-element {
    will-change: transform;
}
```

Browser ko upcoming change hint de sakta hai.

> [!CAUTION]
> `will-change` ko many elements par permanently apply na karein. Memory/resource cost ho sakti hai. Only measured, imminent use ke liye.

---

## 🧪 17.46 Performance Testing

Use browser tools:

- Performance panel
- Rendering tools
- FPS meter where available
- Paint flashing
- CPU/network throttling
- Low-end real device testing

Check:

- Frame drops
- Long main-thread tasks
- Layout shifts
- Excessive paint
- Too many simultaneous animations
- Large shadows/filters
- Motion during scroll

---

# 🟫 Part G: Motion Accessibility

## ♿ 17.47 Why Motion Can Be a Problem

Motion may:

- Cause dizziness or nausea
- Distract users
- Make reading difficult
- Trigger vestibular discomfort
- Hide content before animation completes
- Create timing problems
- Consume battery/data/CPU

---

## 🛑 17.48 Reduced Motion

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

This common broad pattern may not suit every project. Better component-specific approach:

```css
.card {
    transition: transform 200ms ease-out;
}

@media (prefers-reduced-motion: reduce) {
    .card {
        transition: none;
    }

    .spinner {
        animation-duration: 1.5s;
    }
}
```

Essential status still communicate hona chahiye.

---

## 🎮 17.49 User Controls

Long, repeating or moving content ke liye:

- Pause
- Stop
- Hide
- Reduce motion
- Disable autoplay

Real buttons and accessible names use karein.

---

## 🚫 17.50 Avoid Harmful Flashing

Rapid flashing content seizures trigger kar sakta hai. Safe design guidelines follow karein and unnecessary flashing avoid karein.

> [!IMPORTANT]
> “Animation” and “flashing” same nahi hain, but high-frequency luminance/color changes especially risky ho sakte hain.

---

## 🧭 17.51 Motion Should Have Purpose

Good uses:

- Show state change
- Explain spatial relationship
- Confirm action
- Guide attention briefly
- Smooth expand/collapse
- Indicate progress

Poor uses:

- Every element constantly moving
- Important content hidden behind long entrance
- Decorative motion blocking task
- Hover-only interaction
- Uncontrolled autoplay
- Motion used as only feedback

---

# 🟪 Part H: Complete Animated Course Interface

## 🧪 17.52 HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Course Cards | BCA Learning Hub</title>
    <link rel="stylesheet" href="css/motion.css">
</head>
<body>
    <a class="skip-link" href="#main-content">
        Skip to main content
    </a>

    <header class="site-header">
        <p class="brand">BCA Learning Hub</p>
        <h1>Continue Your Learning Journey</h1>
        <p>Choose a course and start practicing.</p>
    </header>

    <main id="main-content">
        <section aria-labelledby="courses-heading">
            <div class="section-heading">
                <div>
                    <p class="eyebrow">My Courses</p>
                    <h2 id="courses-heading">Web Development</h2>
                </div>

                <div class="loading-status" role="status">
                    <span class="spinner" aria-hidden="true"></span>
                    <span>Course data updated</span>
                </div>
            </div>

            <div class="course-grid">
                <article class="course-card">
                    <span class="course-badge">Complete</span>
                    <h3>HTML</h3>
                    <p>Build semantic and accessible pages.</p>

                    <div class="progress-track" aria-label="HTML progress: 100%">
                        <span class="progress-value progress-full"></span>
                    </div>

                    <a class="course-link" href="html.html">
                        Review HTML
                    </a>
                </article>

                <article class="course-card current-course">
                    <span class="course-badge">Current</span>
                    <h3>CSS</h3>
                    <p>Create responsive layouts and motion.</p>

                    <div class="progress-track" aria-label="CSS progress: 70%">
                        <span class="progress-value progress-css"></span>
                    </div>

                    <a class="course-link" href="css.html">
                        Continue CSS
                    </a>
                </article>

                <article class="course-card">
                    <span class="course-badge">Next</span>
                    <h3>JavaScript</h3>
                    <p>Add behavior and application logic.</p>

                    <div class="progress-track" aria-label="JavaScript progress: 0%">
                        <span class="progress-value progress-empty"></span>
                    </div>

                    <a class="course-link" href="javascript.html">
                        Preview JavaScript
                    </a>
                </article>
            </div>
        </section>
    </main>

    <footer class="site-footer">
        <p>&copy; 2026 BCA Learning Hub</p>
    </footer>
</body>
</html>
```

---

## 🎨 17.53 CSS

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}

:root {
    --primary: #123a70;
    --primary-dark: #0b274b;
    --accent: #005fcc;
    --focus: #ffbf47;
    --page: #f4f7fb;
    --surface: #ffffff;
    --border: #cbd5e1;
    --text: #1f2937;
}

body {
    margin: 0;
    background-color: var(--page);
    color: var(--text);
    font-family: system-ui, sans-serif;
    line-height: 1.6;
}

.skip-link {
    position: fixed;
    z-index: 100;
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
    padding:
        clamp(3rem, 8vw, 7rem)
        max(1rem, 5vw);
    background:
        linear-gradient(135deg, var(--primary-dark), var(--primary));
    color: #ffffff;
    text-align: center;
}

.brand {
    font-weight: 800;
    letter-spacing: 0.08em;
    text-transform: uppercase;
}

.site-header h1 {
    margin-block: 0.5rem;
    font-size: clamp(2rem, 6vw, 4rem);
    line-height: 1.1;
}

main {
    width: min(90%, 70rem);
    margin-inline: auto;
    padding-block: clamp(3rem, 7vw, 6rem);
}

.section-heading {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem 2rem;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2rem;
}

.eyebrow {
    color: var(--accent);
    font-weight: 800;
    letter-spacing: 0.08em;
    text-transform: uppercase;
}

.loading-status {
    display: flex;
    gap: 0.6rem;
    align-items: center;
}

.spinner {
    width: 1.2rem;
    height: 1.2rem;
    border: 3px solid var(--border);
    border-top-color: var(--accent);
    border-radius: 50%;
    animation: spin 1s linear 2;
}

@keyframes spin {
    to {
        transform: rotate(1turn);
    }
}

.course-grid {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(min(100%, 17rem), 1fr));
    gap: 1.25rem;
}

.course-card {
    position: relative;
    display: flex;
    flex-direction: column;
    padding: 1.5rem;
    border: 1px solid var(--border);
    border-radius: 1rem;
    background-color: var(--surface);
    box-shadow: 0 6px 18px rgb(15 23 42 / 8%);
    animation: card-enter 500ms ease-out both;
    transition:
        transform 200ms ease-out,
        box-shadow 200ms ease-out,
        border-color 200ms linear;
}

.course-card:nth-child(2) {
    animation-delay: 100ms;
}

.course-card:nth-child(3) {
    animation-delay: 200ms;
}

@keyframes card-enter {
    from {
        opacity: 0;
        transform: translateY(1.5rem);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.course-card:hover,
.course-card:focus-within {
    transform: translateY(-0.35rem);
    border-color: var(--accent);
    box-shadow: 0 14px 35px rgb(15 23 42 / 15%);
}

.current-course {
    border-width: 2px;
    border-color: var(--accent);
}

.course-badge {
    align-self: flex-start;
    padding: 0.25rem 0.65rem;
    border-radius: 999px;
    background-color: #e8f0ff;
    color: var(--primary);
    font-size: 0.875rem;
    font-weight: 800;
}

.course-card h3 {
    color: var(--primary);
    font-size: 1.5rem;
}

.progress-track {
    height: 0.75rem;
    margin-block: auto 1.25rem;
    overflow: hidden;
    border-radius: 999px;
    background-color: #e5e7eb;
}

.progress-value {
    display: block;
    height: 100%;
    border-radius: inherit;
    background-color: var(--accent);
    transform-origin: left;
    animation: progress-grow 700ms ease-out 300ms both;
}

.progress-full {
    width: 100%;
}

.progress-css {
    width: 70%;
}

.progress-empty {
    width: 0%;
}

@keyframes progress-grow {
    from {
        transform: scaleX(0);
    }

    to {
        transform: scaleX(1);
    }
}

.course-link {
    display: inline-block;
    align-self: flex-start;
    padding: 0.7rem 1rem;
    border-radius: 0.5rem;
    background-color: var(--accent);
    color: #ffffff;
    font-weight: 750;
    text-decoration: none;
    transition:
        background-color 180ms ease-out,
        transform 180ms ease-out;
}

.course-link:hover {
    background-color: #004a9f;
    transform: translateY(-2px);
}

.course-link:active {
    transform: translateY(0);
}

a:focus-visible {
    outline: 3px solid var(--focus);
    outline-offset: 3px;
}

.site-footer {
    padding: 1.5rem;
    background-color: var(--primary-dark);
    color: #ffffff;
    text-align: center;
}

/* Respect user motion preference */
@media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
        scroll-behavior: auto;
    }

    .course-card,
    .progress-value,
    .spinner {
        animation: none;
    }

    .course-card,
    .course-link {
        transition: none;
    }

    .course-card:hover,
    .course-card:focus-within,
    .course-link:hover,
    .course-link:active {
        transform: none;
    }
}
```

---

## ♿ 17.54 Motion Accessibility Checklist

1. Motion ka purpose clear ho.
2. Essential content animation complete hone par depend na ho.
3. Hover ke saath keyboard state provide ho.
4. Reduced-motion preference respect ho.
5. Infinite motion avoid/limit ho.
6. Pause/stop control where needed.
7. Flashing content avoid ho.
8. Focus location motion se confuse na ho.
9. Screen zoom par transformed content overlap na kare.
10. Hidden state keyboard and accessibility tree ke saath coordinate ho.
11. Loading state visible text se communicate ho.
12. Animations slow devices par test hon.

---

## 🚫 17.55 Common Mistakes

1. `transition: all` everywhere use karna.
2. Duration unit omit karna.
3. Hover-only important interaction.
4. Focus state animate/style na karna.
5. Transform function order ignore karna.
6. Scale se nearby content cover karna.
7. 3D flip ko keyboard/touch inaccessible banana.
8. Animation duration zero rakhkar result expect karna.
9. Keyframe name mismatch.
10. Shorthand values confuse karna.
11. Infinite animation without purpose/control.
12. Width/left/top animate karke performance issue ignore karna.
13. `will-change` every element par lagana.
14. Reduced-motion preference ignore karna.
15. Visual hidden state me controls focusable chhodna.
16. Essential information only generated/animated content me rakhna.

---

## 📌 17.56 Key Points to Remember

- Transition old and new property values ke between smooth change hai.
- Duration and timing function motion feel control karte hain.
- `transform` translate, scale, rotate and skew support karta hai.
- Transform order result change karta hai.
- Transform normal-flow space generally recalculate nahi karta.
- Perspective 3D depth establish kar sakti hai.
- `@keyframes` animation stages define karta hai.
- Animation repeat, direction, fill and play state support karti hai.
- Transform and opacity often efficient motion properties hain.
- `will-change` sparingly use karein.
- Reduced-motion preference respect karein.
- Motion should clarify interface, not distract.

---

## 📝 17.57 Chapter Summary

CSS transitions interpolate changes between old and new property values. Transition configuration includes property, duration, timing function and delay. Transforms visually translate, scale, rotate and skew elements in two or three dimensions; their order and origin affect the result. CSS animations use `@keyframes` to define multiple stages and provide controls for duration, delay, iteration, direction, fill mode and play state. Transform and opacity are often suitable performance-conscious choices, while layout-triggering animations require more care. Motion must remain purposeful, keyboard-compatible and safe. Reduced-motion preferences, pause controls, visible status text and avoidance of harmful flashing improve accessibility.

---

## 🎲 17.58 Multiple-Choice Questions

### 1. Which property sets transition time?

A. `transition-delay`  
B. `transition-duration`  
C. `animation-name`  
D. `transform-time`  

**✅ Answer:** B

### 2. Which timing function has constant rate?

A. `ease`  
B. `linear`  
C. `ease-in`  
D. `steps(2)`  

**✅ Answer:** B

### 3. Which transform moves an element?

A. `translate()`  
B. `scale()`  
C. `skew()`  
D. `opacity()`  

**✅ Answer:** A

### 4. Which transform changes visual size?

A. `rotate()`  
B. `scale()`  
C. `translate()`  
D. `delay()`  

**✅ Answer:** B

### 5. Which rule defines animation stages?

A. `@media`  
B. `@keyframes`  
C. `@import`  
D. `@font-face`  

**✅ Answer:** B

### 6. Which value repeats forever?

A. `always`  
B. `infinite`  
C. `forever`  
D. `loop`  

**✅ Answer:** B

### 7. Which property pauses an animation?

A. `animation-play-state`  
B. `animation-stop`  
C. `transition-state`  
D. `display`  

**✅ Answer:** A

### 8. Which properties are often compositor-friendly?

A. Width and height only  
B. Transform and opacity  
C. Margin and left only  
D. Font family and table layout  

**✅ Answer:** B

### 9. Which query detects reduced-motion preference?

A. `prefers-reduced-motion`  
B. `motion-disabled`  
C. `reduce-animation`  
D. `no-transition`  

**✅ Answer:** A

### 10. Which property sets transformation pivot?

A. `transform-origin`  
B. `perspective-origin-only`  
C. `animation-origin`  
D. `position-origin`  

**✅ Answer:** A

---

## ✍️ 17.59 Fill in the Blanks

1. A transition changes between old and new property __________.
2. `rotate()` commonly accepts an angle such as 45__________.
3. Animation stages are defined with __________.
4. Repeat count is set using animation-iteration-__________.
5. Reduced motion is detected with a media __________.

<details>
<summary><strong>✅ View Answers</strong></summary>

1. values  
2. `deg`  
3. `@keyframes`  
4. count  
5. query

</details>

---

## ✅ 17.60 True or False

1. Every CSS property transitions smoothly.
2. Transform order can change the result.
3. Transform movement normally reserves new layout space.
4. Keyframes can define multiple stages.
5. Infinite animations are always accessible.
6. Opacity and transform often avoid layout work.
7. `will-change` should be placed on every element.
8. Reduced-motion preferences should be respected.
9. Hover interaction always works on touch devices.
10. Animation should support interface understanding.

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

## ❓ 17.61 Short-Answer Questions

1. Define a CSS transition.
2. Explain four transition properties.
3. What is a timing function?
4. What is `cubic-bezier()`?
5. Define CSS transform.
6. Explain translate, scale, rotate and skew.
7. Why does transform order matter?
8. What is transform origin?
9. What is perspective?
10. Define CSS animation.
11. What are keyframes?
12. Explain animation iteration and direction.
13. What is animation fill mode?
14. What is `will-change`?
15. Explain reduced-motion preference.

---

## 📚 17.62 Long-Answer and Exam Questions

1. Explain CSS transitions with syntax and examples.
2. Explain transition timing functions.
3. Discuss all major 2D transforms.
4. Explain transform order and origin.
5. Explain basic 3D transformations.
6. Explain `@keyframes` and animation properties.
7. Explain animation shorthand and multiple animations.
8. Discuss useful motion patterns.
9. Explain animation performance considerations.
10. Discuss motion accessibility and reduced motion.
11. Create and explain a CSS loading indicator.
12. Create and explain an animated course-card interface.

---

## 🧪 17.63 Practical Exercises

1. Add background-color transition to a button.
2. Transition transform and shadow on a card.
3. Compare timing functions.
4. Apply translate, scale, rotate and skew.
5. Change transform order and compare output.
6. Change transform origin.
7. Create a 3D rotate example.
8. Build an accessible flip-card button interaction later with JavaScript.
9. Define a fade-in keyframe.
10. Create a finite pulse animation.
11. Create a loading spinner with status text.
12. Pause an animation using a class.
13. Compare transform with left-position animation.
14. Add reduced-motion rules.
15. Build the complete animated course interface.
16. Test keyboard, zoom and low-end performance.

---

## 🎤 17.64 Viva Questions

1. What is a transition?
2. What is transition duration?
3. Name three timing functions.
4. What does translate do?
5. What does scale do?
6. What does rotate do?
7. Does transform order matter?
8. What is transform origin?
9. What is perspective?
10. What is a keyframe?
11. Which property sets repeat count?
12. What is alternate direction?
13. What does fill mode do?
14. Which properties are often efficient to animate?
15. What is reduced motion?

<details>
<summary><strong>✅ View Short Viva Answers</strong></summary>

1. A smooth change between property states.  
2. Time taken for the change.  
3. Linear, ease and ease-out.  
4. Visually moves an element.  
5. Visually changes its size.  
6. Rotates it around an origin.  
7. Yes.  
8. The transformation pivot.  
9. A 3D depth/viewing effect.  
10. A defined animation stage.  
11. `animation-iteration-count`.  
12. Forward then reverse cycles.  
13. Controls styles before/after active animation.  
14. Transform and opacity.  
15. A preference requesting less motion.

</details>

---

## 🏁 17.65 One-Minute Revision

| Question | Quick Answer |
|---|---|
| Smooth state change? | Transition |
| Transition time? | `transition-duration` |
| Speed curve? | Timing function |
| Move? | `translate()` |
| Resize? | `scale()` |
| Turn? | `rotate()` |
| Slant? | `skew()` |
| Pivot? | `transform-origin` |
| 3D depth? | `perspective` |
| Animation stages? | `@keyframes` |
| Repeat? | `animation-iteration-count` |
| Pause? | `animation-play-state` |
| Efficient motion? | Transform + opacity |
| Performance hint? | `will-change` |
| Less motion? | `prefers-reduced-motion` |

---

## 📚 17.66 Official References

1. [W3C CSS Transitions](https://www.w3.org/TR/css-transitions-2/)
2. [W3C CSS Transforms](https://www.w3.org/TR/css-transforms-2/)
3. [W3C CSS Animations](https://www.w3.org/TR/css-animations-2/)
4. [W3C Media Queries](https://www.w3.org/TR/mediaqueries-5/)

---

[⬅️ Previous Chapter](16-responsive-web-design.md) · [📚 Table of Contents](../SUMMARY.md) · **Next: JavaScript Fundamentals ➡️**
