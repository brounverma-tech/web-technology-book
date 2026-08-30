# 📝 Chapter 8: Text, Links, Images and Lists

![Level](https://img.shields.io/badge/Level-Beginner-brightgreen)
![Course](https://img.shields.io/badge/Course-BCA-blue)
![Unit](https://img.shields.io/badge/Unit-HTML-purple)
![Language](https://img.shields.io/badge/Language-English%20%2B%20Hinglish-orange)

> [!TIP]
> **Chapter Goal:** HTML me readable text, meaningful formatting, navigation links, accessible images aur properly structured lists banana.

---

## 🎯 8.1 Learning Objectives

After completing this chapter, you will be able to:

1. Use HTML elements for text-level meaning.
2. Differentiate semantic elements from visual styling.
3. Create internal, external, email and telephone links.
4. Use absolute, relative and fragment URLs.
5. Add accessible images using meaningful alternative text.
6. Understand basic image formats and dimensions.
7. Create ordered, unordered and description lists.
8. Build nested lists correctly.
9. Organize files and use correct relative paths.
10. Create a complete profile page using text, links, images and lists.

---

## 🗣️ 8.2 Difficult Words: Pronunciation and Meaning

| 🔤 Word | 🔊 Pronunciation | 💡 Simple Meaning |
|---|---|---|
| Emphasis | एम्फसिस — *em-fuh-sis* | Kisi text par stress dena |
| Semantic | सिमैन्टिक — *si-man-tik* | Meaning clearly batane wala |
| Hyperlink | हाइपरलिंक — *hai-per-link* | Clickable connection |
| Anchor | एंकर — *ang-ker* | Link banane wala HTML element |
| Destination | डेस्टिनेशन — *des-ti-nay-shun* | Link ki target location |
| Relative | रिलेटिव — *rel-uh-tiv* | Current location par dependent |
| Absolute | एब्सोल्यूट — *ab-suh-loot* | Complete address |
| Fragment | फ्रैगमेंट — *frag-ment* | Page ke specific section ka reference |
| Alternative | ऑल्टरनेटिव — *awl-tur-nuh-tiv* | Replacement option |
| Accessible | एक्सेसिबल — *ak-ses-uh-bul* | Different users ke liye usable |
| Decorative | डेकोरेटिव — *dek-uh-ray-tiv* | Sirf decoration ke liye |
| Resolution | रेजोल्यूशन — *rez-uh-loo-shun* | Image detail/dimensions ka measure |
| Compression | कम्प्रेशन — *kum-presh-un* | File size reduce karna |
| Caption | कैप्शन — *kap-shun* | Image ka visible description/title |
| Nested | नेस्टेड — *nes-tid* | Ek structure ke andar dusra structure |

---

# 🟦 Part A: Text Elements

## 💡 8.3 Text Content in HTML

HTML text ko sirf visible banane ke liye nahi, balki uska meaning describe karne ke liye elements provide karti hai.

Example:

```html
<p>HTML gives structure and meaning to web content.</p>
```

> [!IMPORTANT]
> Text ka appearance—color, font aur size—mainly CSS se control karein. HTML element content ke meaning ke according choose karein.

---

## 📰 8.4 Headings and Paragraphs

### 8.4.1 Headings

```html
<h1>Web Technology</h1>
<h2>HTML</h2>
<h3>Text Elements</h3>
```

- `h1` highest-level heading hai.
- `h6` lowest-level heading hai.
- Levels logical hierarchy represent karte hain.

### 8.4.2 Paragraph

```html
<p>HTML is used to structure web content.</p>
```

A paragraph ko visual spacing ke liye empty `p` elements se separate na karein. CSS use karein.

---

## 💪 8.5 Strong Importance and Emphasis

### 8.5.1 `strong` Element

`strong` strong importance, seriousness or urgency represent karta hai.

```html
<p><strong>Warning:</strong> Do not share your password.</p>
```

Browsers usually bold render karte hain, lekin iska main purpose meaning hai.

### 8.5.2 `em` Element

`em` stress emphasis represent karta hai.

```html
<p>You must submit the form <em>today</em>.</p>
```

Browsers usually italic render karte hain.

### Difference

| Element | Meaning | Typical Default Look |
|---|---|---|
| `strong` | Strong importance | Bold |
| `em` | Stress emphasis | Italic |

---

## 🔤 8.6 `b` and `i` Elements

### `b`

`b` text ko attention ke liye stylistically offset karta hai without strong importance.

```html
<p>Product code: <b>WT-101</b></p>
```

### `i`

`i` alternate voice, technical term, idiomatic phrase or similar text represent kar sakta hai.

```html
<p>The term <i>responsive design</i> is widely used.</p>
```

> [!NOTE]
> Sirf bold/italic appearance ke liye CSS better choice ho sakti hai. `strong` aur `em` ko unke semantic meaning ke liye use karein.

---

## 🖍️ 8.7 Highlighted and Small Text

### `mark`

Relevant highlighted text:

```html
<p>Search result: Learn <mark>HTML</mark> today.</p>
```

### `small`

Side comments or small print:

```html
<p><small>Terms and conditions apply.</small></p>
```

---

## ➕ 8.8 Inserted and Deleted Text

### Deleted Text

```html
<p>Old fee: <del>₹5,000</del></p>
```

### Inserted Text

```html
<p>New fee: <ins>₹4,500</ins></p>
```

These elements can represent document edits.

---

## 🔢 8.9 Subscript and Superscript

### Subscript

```html
<p>Water formula is H<sub>2</sub>O.</p>
```

### Superscript

```html
<p>2<sup>3</sup> = 8</p>
```

Use these elements where typographical position carries meaning, not merely for smaller text.

---

## 💻 8.10 Computer and Preformatted Text

### 8.10.1 `code`

Represents a short piece of computer code.

```html
<p>Use the <code>&lt;h1&gt;</code> element for a main heading.</p>
```

### 8.10.2 `pre`

Preserves source whitespace and line breaks.

```html
<pre>
Name: Broun
Course: BCA
Subject: Web Technology
</pre>
```

### Code Block

```html
<pre><code>&lt;h1&gt;Hello HTML&lt;/h1&gt;</code></pre>
```

### Other Computer-Related Elements

| Element | Meaning |
|---|---|
| `kbd` | User input, often keyboard |
| `samp` | Program output |
| `var` | Variable name |

```html
<p>Press <kbd>Ctrl</kbd> + <kbd>S</kbd> to save.</p>
<p>Output: <samp>File saved</samp></p>
<p>The variable <var>x</var> stores a value.</p>
```

---

## 💬 8.11 Quotations and Citations

### Inline Quotation

```html
<p>The teacher said, <q>Practice HTML every day.</q></p>
```

### Block Quotation

```html
<blockquote cite="https://example.com/source">
    <p>Learning improves through regular practice.</p>
</blockquote>
```

### Citation

```html
<p><cite>Web Technology Handbook</cite> is a study resource.</p>
```

> [!NOTE]
> `cite` element work ke title ko represent karta hai, normal person's name ko mark karne ke liye generally nahi.

---

## 🏷️ 8.12 Abbreviation and Definition

### Abbreviation

```html
<p><abbr title="HyperText Markup Language">HTML</abbr> structures web pages.</p>
```

### Defining a Term

```html
<p><dfn>Browser</dfn> is software used to access web content.</p>
```

---

## 🕒 8.13 Date and Time

`time` machine-readable date/time provide kar sakta hai.

```html
<p>Exam date: <time datetime="2026-09-15">15 September 2026</time></p>
```

---

## 📍 8.14 Contact Information

`address` nearest article or page author/organization ki contact information represent karta hai.

```html
<address>
    Contact: <a href="mailto:help@example.com">help@example.com</a>
</address>
```

> [!WARNING]
> `address` ko arbitrary postal address ya general indentation ke liye use na karein unless it represents relevant contact information.

---

# 🟩 Part B: Hyperlinks

## 🔗 8.15 What Is a Hyperlink?

A hyperlink connects one resource or location to another.

HTML me anchor element `a` link banata hai.

```html
<a href="https://example.com">Visit Example</a>
```

- `a` = anchor element
- `href` = destination
- Visible text = link text

---

## 🌍 8.16 External Link

```html
<a href="https://www.wikipedia.org/">Visit Wikipedia</a>
```

Complete absolute URL use hota hai.

### Good Link Text

Recommended:

```html
<a href="syllabus.pdf">Download the BCA syllabus</a>
```

Less clear:

```html
<a href="syllabus.pdf">Click here</a>
```

Meaningful link text users aur assistive technologies ko destination samajhne me help karta hai.

---

## 🏠 8.17 Internal Website Link

```html
<a href="about.html">About Us</a>
```

Relative URL current website/project ke resource ko point karti hai.

### Folder Example

```text
website/
├── index.html
├── about.html
├── courses/
│   └── bca.html
└── images/
    └── logo.png
```

From `index.html`:

```html
<a href="about.html">About</a>
<a href="courses/bca.html">BCA Course</a>
```

From `courses/bca.html` back to home:

```html
<a href="../index.html">Home</a>
```

---

## 🎯 8.18 Link to a Page Section

First assign an ID:

```html
<h2 id="admission">Admission Process</h2>
```

Then create a fragment link:

```html
<a href="#admission">Go to Admission Process</a>
```

Link to a section on another page:

```html
<a href="courses.html#bca">View BCA Details</a>
```

> [!IMPORTANT]
> Fragment target ka `id` unique hona chahiye.

---

## 📧 8.19 Email Link

```html
<a href="mailto:help@example.com">Email Support</a>
```

Optional subject:

```html
<a href="mailto:help@example.com?subject=Course%20Enquiry">
    Send Course Enquiry
</a>
```

> [!CAUTION]
> Email address public page par rakhne se automated collection/spam ho sakta hai. Project needs ke according contact form consider karein.

---

## 📞 8.20 Telephone Link

```html
<a href="tel:+911234567890">Call Us</a>
```

Supported device par phone application open ho sakti hai.

---

## 📥 8.21 Download Link

```html
<a href="notes.pdf" download>Download Notes</a>
```

`download` browser ko resource download karne ka hint deta hai. Actual behavior resource origin, headers aur browser policy par depend kar sakta hai.

---

## 🪟 8.22 Opening a Link in a New Tab

```html
<a href="https://example.com" target="_blank" rel="noopener">
    Open Example
</a>
```

### Important Attributes

| Attribute | Purpose |
|---|---|
| `target="_blank"` | New browsing context/tab request |
| `rel="noopener"` | Opened page ko opener reference se isolate karta hai |
| `rel="noreferrer"` | Referrer information omit karta hai and implies opener protection in modern behavior |

> [!TIP]
> New tab tabhi use karein jab user experience me genuinely useful ho. Unexpected new tabs users ko confuse kar sakte hain.

---

## 🧭 8.23 Basic Navigation Menu

```html
<nav aria-label="Main navigation">
    <a href="index.html">Home</a>
    <a href="about.html">About</a>
    <a href="courses.html">Courses</a>
    <a href="contact.html">Contact</a>
</nav>
```

Later chapter me semantic page structure aur accessibility detail se cover hogi.

---

## 🚫 8.24 Placeholder and Empty Links

Avoid:

```html
<a href="#">Read More</a>
<a href="">Profile</a>
```

Agar action ready nahi hai to proper button, text or disabled design use karein. Dummy link navigation aur accessibility problems create kar sakta hai.

---

# 🟨 Part C: Images

## 🖼️ 8.25 The `img` Element

`img` embeds an image.

```html
<img src="images/college.jpg" alt="Front view of ABC College">
```

### Main Attributes

| Attribute | Purpose |
|---|---|
| `src` | Image resource URL |
| `alt` | Text alternative |
| `width` | Intrinsic/display width hint in CSS pixels |
| `height` | Intrinsic/display height hint |
| `loading` | Loading behavior hint |
| `srcset` | Multiple image candidates |
| `sizes` | Layout-size hints with `srcset` |

---

## 📁 8.26 Image Paths

### Same Folder

```html
<img src="logo.png" alt="Company logo">
```

### Images Subfolder

```html
<img src="images/logo.png" alt="Company logo">
```

### Parent Folder

```html
<img src="../images/logo.png" alt="Company logo">
```

### External URL

```html
<img src="https://example.com/images/logo.png" alt="Example logo">
```

> [!WARNING]
> Random external image ko directly embed na karein. Permission, copyright, privacy, reliability aur performance consider karein.

---

## ♿ 8.27 Alternative Text

`alt` image ka text alternative provide karta hai.

### Informative Image

```html
<img src="library.jpg" alt="Students studying in the college library">
```

### Functional Image Link

```html
<a href="index.html">
    <img src="logo.png" alt="ABC College home">
</a>
```

### Decorative Image

```html
<img src="decorative-line.png" alt="">
```

### Alt-Text Rules

1. Image ka purpose describe karein.
2. Context ke according concise rakhein.
3. “Image of” unnecessarily repeat na karein.
4. Image me important text ho to relevant text include karein.
5. Decorative image ke liye empty `alt=""` use karein.
6. `alt` omit na karein.

> [!IMPORTANT]
> Good alt text file ka look hi nahi, page me image ka purpose batata hai.

---

## 📐 8.28 Width and Height

```html
<img
    src="student.jpg"
    alt="BCA student working on a laptop"
    width="600"
    height="400">
```

Width aur height browser ko aspect ratio reserve karne me help kar sakte hain, reducing layout movement.

Responsive visual sizing later CSS me:

```css
img {
    max-width: 100%;
    height: auto;
}
```

> [!NOTE]
> HTML attributes me correct intrinsic ratio dein. CSS rendered size control kar sakti hai.

---

## 🐢 8.29 Lazy Loading

```html
<img
    src="campus.jpg"
    alt="College campus"
    width="800"
    height="500"
    loading="lazy">
```

`loading="lazy"` off-screen image loading defer karne ka browser hint hai.

Above-the-fold important image par blindly lazy loading apply na karein.

---

## 🗃️ 8.30 Common Image Formats

| Format | Suitable Use | Key Point |
|---|---|---|
| JPEG/JPG | Photographs | Lossy compression, no normal transparency |
| PNG | Graphics and transparency | Lossless, often larger |
| GIF | Simple animation | Limited colors |
| SVG | Logos, icons, diagrams | Scalable vector |
| WebP | Web photos/graphics | Modern compression and transparency support |
| AVIF | Highly compressed modern images | Strong compression, workflow support check karein |

### Selection Tips

- Photo: JPEG, WebP or AVIF
- Logo/icon: SVG where suitable
- Transparency: PNG, WebP, AVIF or SVG
- Simple animation: GIF or suitable modern format

---

## 🖼️ 8.31 Figure and Caption

```html
<figure>
    <img
        src="network-diagram.png"
        alt="Client connected to a web server"
        width="700"
        height="400">
    <figcaption>Figure 8.1: Basic client-server connection</figcaption>
</figure>
```

`figure` self-contained content represent karta hai, while `figcaption` visible caption provide karta hai.

---

## 🔗 8.32 Image as a Link

```html
<a href="gallery.html">
    <img
        src="gallery-thumbnail.jpg"
        alt="Open the college photo gallery"
        width="300"
        height="200">
</a>
```

Alt text ko link ka purpose batana chahiye.

---

## 📱 8.33 Responsive Image Introduction

`srcset` browser ko multiple image candidates deta hai.

```html
<img
    src="campus-800.jpg"
    srcset="campus-400.jpg 400w,
            campus-800.jpg 800w,
            campus-1200.jpg 1200w"
    sizes="(max-width: 600px) 100vw, 800px"
    alt="Main building of ABC College"
    width="1200"
    height="800">
```

Browser viewport, layout and device characteristics ke according candidate choose kar sakta hai.

> [!NOTE]
> Responsive images advanced topic hai. Beginning me correct `src`, `alt`, dimensions aur optimized file sabse important hain.

---

# 🟥 Part D: Lists

## 📋 8.34 Unordered List

`ul` unordered list create karta hai. Each item `li` me hota hai.

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

Use when item order essential nahi hai.

---

## 🔢 8.35 Ordered List

`ol` ordered list create karta hai.

```html
<ol>
    <li>Open the editor.</li>
    <li>Create index.html.</li>
    <li>Write HTML code.</li>
    <li>Open the file in a browser.</li>
</ol>
```

Use when sequence or rank matters.

### Useful Attributes

#### Start Number

```html
<ol start="5">
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

#### Reversed Order

```html
<ol reversed>
    <li>Third position</li>
    <li>Second position</li>
    <li>First position</li>
</ol>
```

#### Specific Item Value

```html
<ol>
    <li>Introduction</li>
    <li value="5">HTML</li>
    <li>CSS</li>
</ol>
```

---

## 📖 8.36 Description List

`dl` description list container hai.

- `dt` = term/name
- `dd` = description/value

```html
<dl>
    <dt>HTML</dt>
    <dd>Structures web content.</dd>

    <dt>CSS</dt>
    <dd>Controls presentation and layout.</dd>

    <dt>JavaScript</dt>
    <dd>Adds behavior and interaction.</dd>
</dl>
```

Suitable for:

- Glossaries
- Metadata
- Question-answer pairs in suitable contexts
- Terms and definitions

---

## 🪆 8.37 Nested Lists

A nested list should be placed inside the relevant `li`.

### Correct

```html
<ul>
    <li>
        Front-End
        <ul>
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
        </ul>
    </li>
    <li>
        Back-End
        <ul>
            <li>PHP</li>
            <li>Node.js</li>
        </ul>
    </li>
</ul>
```

### Incorrect Structure

```html
<ul>
    <li>Front-End</li>
    <ul>
        <li>HTML</li>
    </ul>
</ul>
```

---

## 🧭 8.38 Navigation List

```html
<nav aria-label="Main navigation">
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="courses.html">Courses</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

CSS later list markers aur layout change kar sakti hai.

---

## ✅ 8.39 List Best Practices

1. Related items ko list me group karein.
2. Sequence important ho to `ol` use karein.
3. Order unimportant ho to `ul` use karein.
4. Terms and descriptions ke liye `dl` use karein.
5. Nested list relevant `li` ke andar rakhein.
6. Visual bullets manually type karne ke bajay semantic lists use karein.
7. List items concise aur parallel style me likhein.

---

# 🟧 Part E: Combined Practical

## 🧪 8.40 Student Profile Page

### Project Structure

```text
student-profile/
├── index.html
├── about.html
└── images/
    └── student.jpg
```

### `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Broun Verma | BCA Student Profile</title>
</head>
<body>
    <header>
        <h1>Broun Verma</h1>
        <p><strong>BCA Student</strong> and Web Technology Learner</p>

        <nav aria-label="Main navigation">
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="about.html">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="mailto:contact@example.com">Email</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <figure>
            <img
                src="images/student.jpg"
                alt="Broun working on a laptop"
                width="400"
                height="400">
            <figcaption>Learning web development</figcaption>
        </figure>

        <section>
            <h2>Introduction</h2>
            <p>
                I am learning <strong>Web Technology</strong>.
                My current focus is <mark>HTML fundamentals</mark>.
            </p>
        </section>

        <section id="skills">
            <h2>Skills I Am Learning</h2>
            <ol>
                <li>HTML</li>
                <li>CSS</li>
                <li>JavaScript</li>
            </ol>
        </section>

        <section>
            <h2>Study Topics</h2>
            <dl>
                <dt>HTML</dt>
                <dd>Structure and meaning of web content.</dd>

                <dt>CSS</dt>
                <dd>Design and responsive layout.</dd>
            </dl>
        </section>
    </main>

    <footer>
        <p><small>&copy; 2026 Broun Verma</small></p>
    </footer>
</body>
</html>
```

---

## ♿ 8.41 Accessibility Checklist

### Text

- Meaningful heading order use karein.
- Important meaning sirf bold/color par depend na kare.
- Clear language use karein.

### Links

- Link text destination explain kare.
- “Click here” alone avoid karein.
- Keyboard users ke liye real anchor use karein.
- New-tab behavior unnecessarily force na karein.

### Images

- Every `img` ko suitable `alt` dein.
- Decorative image ke liye `alt=""`.
- Text ko unnecessarily image me embed na karein.
- Correct dimensions and optimized files use karein.

### Lists

- Real list ke liye `ul`, `ol` ya `dl` use karein.
- Manual hyphens ko semantic list ka replacement na banayein.
- Correct nesting rakhein.

---

## 🚫 8.42 Common Mistakes

1. `strong` aur `b` ko exactly same samajhna.
2. Heading ko only font size ke liye use karna.
3. Link text me sirf “click here” likhna.
4. Broken relative path use karna.
5. `target="_blank"` use karke opener safety ignore karna.
6. Image ka `alt` omit karna.
7. File name ko alt text bana dena.
8. Decorative image ko long description dena.
9. Huge image ko HTML width se sirf visually small karna.
10. List items ko `li` ke bina likhna.
11. Nested list ko parent `li` ke outside rakhna.
12. Visual bullets manually type karna.
13. Copyrighted external image bina permission use karna.
14. File and folder names me inconsistent letter case use karna.

---

## 📌 8.43 Key Points to Remember

- Semantic text elements meaning describe karte hain.
- `strong` importance aur `em` stress emphasis represent karta hai.
- Anchor element `a` links create karta hai.
- `href` link destination specify karta hai.
- Relative paths current document location par depend karte hain.
- Fragment link `id` target use karta hai.
- `img` is a void element.
- `src` image location aur `alt` text alternative deta hai.
- Correct width/height layout stability improve kar sakte hain.
- `ul` unordered, `ol` ordered aur `dl` description list hai.
- Nested list relevant `li` ke andar honi chahiye.
- HTML meaning ke liye, CSS presentation ke liye use karein.

---

## 📝 8.44 Chapter Summary

HTML provides meaningful text elements for importance, emphasis, quotations, code, abbreviations, dates and other content. The anchor element creates links to external resources, internal pages, page sections, email addresses and phone numbers. Clear link text improves usability. Images are embedded with the `img` element; `src` identifies the resource and `alt` provides a context-sensitive text alternative. Dimensions and optimized formats improve page stability and performance. Unordered, ordered and description lists organize related information semantically. Correct paths, nesting and accessibility practices make pages more reliable.

---

## 🎲 8.45 Multiple-Choice Questions

### 1. Which element represents strong importance?

A. `b`  
B. `strong`  
C. `big`  
D. `font`  

**✅ Answer:** B

### 2. Which attribute contains a link destination?

A. `src`  
B. `href`  
C. `alt`  
D. `class`  

**✅ Answer:** B

### 3. Which syntax links to a section with ID `skills`?

A. `href="skills"`  
B. `href=".skills"`  
C. `href="#skills"`  
D. `src="#skills"`  

**✅ Answer:** C

### 4. Which attribute provides image alternative text?

A. `title`  
B. `alt`  
C. `href`  
D. `target`  

**✅ Answer:** B

### 5. Which element creates an ordered list?

A. `ul`  
B. `ol`  
C. `dl`  
D. `li` only  

**✅ Answer:** B

### 6. Which element represents a list item?

A. `item`  
B. `list`  
C. `li`  
D. `dt`  

**✅ Answer:** C

### 7. Which element preserves whitespace?

A. `pre`  
B. `p`  
C. `span`  
D. `small`  

**✅ Answer:** A

### 8. Decorative image should commonly use:

A. Missing alt attribute  
B. `alt=""`  
C. `alt="decorative image"` always  
D. `href=""`  

**✅ Answer:** B

### 9. Which list suits terms and definitions?

A. `ol`  
B. `ul`  
C. `dl`  
D. `nav`  

**✅ Answer:** C

### 10. Which path moves to the parent folder?

A. `./`  
B. `../`  
C. `#`  
D. `//`  

**✅ Answer:** B

---

## ✍️ 8.46 Fill in the Blanks

1. The __________ element creates a hyperlink.
2. Link destination is stored in the __________ attribute.
3. Image location is stored in the __________ attribute.
4. An unordered list uses the __________ element.
5. A description term uses the __________ element.

<details>
<summary><strong>✅ View Answers</strong></summary>

1. `a`  
2. `href`  
3. `src`  
4. `ul`  
5. `dt`

</details>

---

## ✅ 8.47 True or False

1. `strong` represents strong importance.
2. `alt` is optional for every image.
3. Relative paths depend on the current location.
4. `ol` represents an ordered list.
5. A nested list should be placed inside its related `li`.
6. HTML comments are suitable for passwords.
7. Meaningful link text improves accessibility.
8. `img` requires a closing `</img>` tag.

<details>
<summary><strong>✅ View Answers</strong></summary>

1. True  
2. False  
3. True  
4. True  
5. True  
6. False  
7. True  
8. False

</details>

---

## ❓ 8.48 Short-Answer Questions

1. Differentiate between `strong` and `b`.
2. Differentiate between `em` and `i`.
3. What is the purpose of `pre`?
4. Define a hyperlink.
5. What is the `href` attribute?
6. Differentiate between absolute and relative links.
7. What is a fragment link?
8. What is the use of `mailto`?
9. Define alternative text.
10. How should decorative images be handled?
11. What is lazy loading?
12. Name four image formats.
13. Differentiate between `ul` and `ol`.
14. What is a description list?
15. Explain nested lists.

---

## 📚 8.49 Long-Answer and Exam Questions

1. Explain important HTML text-formatting and semantic elements.
2. Explain the anchor element and its attributes with examples.
3. Discuss internal, external, email, telephone and fragment links.
4. Explain absolute and relative paths with a project structure.
5. Explain the `img` element and its important attributes.
6. Discuss image accessibility and good alt-text practices.
7. Compare common web image formats.
8. Explain ordered, unordered and description lists.
9. Explain nested lists with correct and incorrect examples.
10. Create a complete student-profile page using all chapter concepts.

---

## 🧪 8.50 Practical Exercises

1. Create paragraphs using `strong`, `em`, `mark` and `small`.
2. Display H₂O and x² using HTML.
3. Display HTML code safely using `pre` and `code`.
4. Create internal and external links.
5. Create a page-section fragment link.
6. Add email and telephone links.
7. Create an image with meaningful alt text.
8. Add a figure and caption.
9. Create an ordered list of web-development steps.
10. Create an unordered list of skills.
11. Create a glossary using `dl`.
12. Create a nested course-subject list.
13. Build the complete student-profile project.
14. Validate every HTML page.

---

## 🎤 8.51 Viva Questions

1. What does `strong` represent?
2. What does `em` represent?
3. What is the anchor element?
4. Which attribute defines a link destination?
5. What is an absolute URL?
6. What is a relative URL?
7. How do you link to a page section?
8. Is `img` a void element?
9. What is the purpose of `alt`?
10. What alt value is used for a decorative image?
11. What does `figure` represent?
12. What does `figcaption` provide?
13. Which element creates an unordered list?
14. Which element creates an ordered list?
15. What are `dt` and `dd`?

<details>
<summary><strong>✅ View Short Viva Answers</strong></summary>

1. Strong importance or urgency.  
2. Stress emphasis.  
3. The `a` element used to create links.  
4. `href`.  
5. A complete resource address.  
6. A path dependent on a base/current location.  
7. Use `href="#id"` and a matching unique `id`.  
8. Yes.  
9. It provides a text alternative.  
10. `alt=""`.  
11. Self-contained referenced content.  
12. A visible caption.  
13. `ul`.  
14. `ol`.  
15. Description term and description details.

</details>

---

## 🏁 8.52 One-Minute Revision

| Question | Quick Answer |
|---|---|
| Strong importance? | `strong` |
| Stress emphasis? | `em` |
| Code element? | `code` |
| Hyperlink element? | `a` |
| Destination attribute? | `href` |
| Section link? | `#id` |
| Image element? | `img` |
| Image source? | `src` |
| Text alternative? | `alt` |
| Caption? | `figcaption` |
| Unordered list? | `ul` |
| Ordered list? | `ol` |
| Description list? | `dl` |
| List item? | `li` |

---

## 📚 8.53 Official Reference

- [WHATWG HTML Living Standard](https://html.spec.whatwg.org/)

---

[⬅️ Previous Chapter](07-html-fundamentals.md) · [📚 Table of Contents](../SUMMARY.md) · **Next: Tables, Forms and Input Elements ➡️**
