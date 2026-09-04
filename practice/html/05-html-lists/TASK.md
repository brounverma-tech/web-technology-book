# Practical 05: Ordered and Unordered Lists

## Goal

Is practical mein tum bullet list aur numbered list banana seekhoge.

## Related Theory

Read: [Chapter 8 — Text, Links, Images and Lists](../../../chapters/08-text-links-images-and-lists.md)

## Step 1: Folder Banao

```text
frontend-practice/
└── practical-05/
    └── index.html
```

## Step 2: Example Type Karo

[index.html](index.html) ka code apni local file mein khud type karo.

## Unordered List

Jab items ka fixed order important na ho, `ul` use karo:

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

Browser bullets dikhata hai.

## Ordered List

Jab steps ka order important ho, `ol` use karo:

```html
<ol>
    <li>Open VS Code</li>
    <li>Write HTML</li>
</ol>
```

Browser numbers dikhata hai.

## Tag Meaning

| Tag | Meaning |
|---|---|
| `<ul>` | Unordered list — bullets |
| `<ol>` | Ordered list — numbers |
| `<li>` | List ka ek item |

`li` elements ko `ul` ya `ol` ke andar rakho.

## Your Tasks

Example chalne ke baad:

1. Skills list mein **Responsive Design** add karo.
2. Daily steps ke end mein **Share my screenshot** add karo.
3. Nayi heading **My Favorite Games** banao.
4. Uske neeche `ul` use karke apne 3 favorite games likho.

## Common Mistakes

### Wrong

```html
<ul>
    HTML
    CSS
</ul>
```

### Correct

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

Har item ke liye separate `li` use hota hai.

## Self-Check

- [ ] `practical-05/index.html` correct location par hai.
- [ ] Skills bullets mein dikh rahi hain.
- [ ] Daily steps numbers mein dikh rahe hain.
- [ ] Har item `li` ke andar hai.
- [ ] Responsive Design add kiya hai.
- [ ] Share my screenshot add kiya hai.
- [ ] Favorite games ki nayi bullet list banayi hai.

Save karo, browser refresh karo aur screenshot share karo.
