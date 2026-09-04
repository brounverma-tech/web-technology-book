# Practical 03: Links and Buttons

## Goal

Is practical mein tum clickable links banana aur link aur button ka difference samjhoge.

## Related Theory

Read: [Chapter 8 — Text, Links, Images and Lists](../../../chapters/08-text-links-images-and-lists.md)

## Step 1: Folder Banao

```text
frontend-practice/
└── practical-03/
    └── index.html
```

## Step 2: Example Type Karo

[index.html](index.html) ka code apni local file mein khud type karo. Save karke browser mein kholo.

## Link Syntax

```html
<a href="https://example.com">Visible Link Text</a>
```

- `a` means anchor element.
- `href` mein destination address hota hai.
- Start aur end tags ke beech clickable text hota hai.

## New Tab Link

```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer">
    Open Example
</a>
```

- `target="_blank"` link ko new tab mein kholta hai.
- `rel="noopener noreferrer"` new-tab external links ke liye safety information deta hai.

## Link vs Button

| Element | Main Use |
|---|---|
| `<a>` | Dusre page ya location par jana |
| `<button>` | Koi action karna |

Normal button bina JavaScript ya form ke click par koi action nahi karega. Ye error nahi hai.

## Your Tasks

1. Google link open karke test karo.
2. GitHub profile link new tab mein open karke test karo.
3. Ek naya link banao:
   - Address: `https://developer.mozilla.org/`
   - Text: **Learn HTML on MDN**
4. Button text ko **Start Learning** mein change karo.
5. Link aur button ke beech difference apne words mein ek paragraph mein likho.

## Self-Check

- [ ] Folder ka naam `practical-03` hai.
- [ ] Links click karne par correct websites open hoti hain.
- [ ] Complete URL `https://` se start hota hai.
- [ ] GitHub link new tab mein khulta hai.
- [ ] MDN link khud add kiya hai.
- [ ] Button ke andar `type="button"` hai.
- [ ] Button click par abhi kuch na hona samajh aa gaya hai.

Save karo, browser refresh karo aur screenshot share karo.
