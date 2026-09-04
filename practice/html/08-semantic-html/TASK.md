# Practical 08: Semantic HTML

## Goal

Is practical mein tum webpage ko meaningful sections mein divide karna seekhoge.

## Related Theory

Read: [Chapter 10 — Semantic HTML and Multimedia](../../../chapters/10-semantic-html-and-multimedia.md)

## Step 1: Folder Banao

```text
frontend-practice/
└── practical-08/
    └── index.html
```

## Step 2: Example Type Karo

[index.html](index.html) ka code apni local file mein khud type karo.

## Semantic Elements

| Element | Use |
|---|---|
| `<header>` | Page ya section ka introductory top part |
| `<nav>` | Navigation links |
| `<main>` | Page ka unique main content |
| `<section>` | Related content ka section |
| `<article>` | Independent/self-contained content |
| `<aside>` | Main content se related extra information |
| `<footer>` | Bottom information, author ya copyright |

Semantic elements browser ko content ka meaning batate hain. Ye automatically beautiful design nahi banate; design CSS se aayega.

## Navigation Kaise Kaam Karti Hai?

```html
<a href="#about">About</a>

<section id="about">
    <h2>About Me</h2>
</section>
```

Link ka `#about` section ke `id="about"` se connect hota hai.

## Your Tasks

Example chalne ke baad:

1. Navigation mein **Skills** link add karo using `href="#skills"`.
2. `main` ke andar `id="skills"` wala naya `section` banao.
3. Skills section mein `ul` list se HTML, CSS aur JavaScript likho.
4. Learning section ke andar ek aur `article` banao:
   - Heading: **My Next Goal**
   - Paragraph: apna next learning goal
5. Footer mein apna naam rakho.

## Common Mistakes

- Page par multiple unrelated `main` elements banana
- Navigation ka `href="#name"` aur section ka `id="name"` different rakhna
- Har normal line ke liye `section` banana
- Semantic elements ko sirf design ke liye use karna
- Closing tags bhoolna

## Self-Check

- [ ] `practical-08/index.html` correct location par hai.
- [ ] Header aur navigation dikh rahe hain.
- [ ] Navigation links correct sections tak ja rahe hain.
- [ ] Page par one main element hai.
- [ ] Section, article aur aside use hue hain.
- [ ] Skills link aur section khud add kiya hai.
- [ ] Footer bottom mein hai.

Save karo, browser refresh karo aur screenshot share karo.
