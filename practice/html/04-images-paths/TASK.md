# Practical 04: Images and File Paths

## Goal

Is practical mein tum local image ko HTML page par show karoge aur relative file path samjhoge.

## Related Theory

Read: [Chapter 8 — Text, Links, Images and Lists](../../../chapters/08-text-links-images-and-lists.md)

## Step 1: Folder Structure Banao

```text
frontend-practice/
└── practical-04/
    ├── index.html
    └── images/
        └── my-photo.jpg
```

1. `practical-04` folder banao.
2. Uske andar `index.html` file banao.
3. Uske andar `images` folder banao.
4. Computer se koi photo copy karke `images` folder mein rakho.
5. Photo ka naam `my-photo.jpg` rakho.

> Agar photo PNG format mein hai, filename `my-photo.png` rakho aur HTML ke `src` mein bhi `.png` use karo.

## Step 2: Code Type Karo

[index.html](index.html) ka code apni local file mein khud type karo.

## Image Syntax

```html
<img src="images/my-photo.jpg" alt="Broun learning HTML" width="250">
```

| Part | Meaning |
|---|---|
| `img` | Image element |
| `src` | Image ka address/path |
| `images/` | Current folder ke andar images folder |
| `my-photo.jpg` | Exact image filename |
| `alt` | Image na khule to description; accessibility mein bhi useful |
| `width="250"` | Image ki displayed width |

`img` void element hai. Isliye `</img>` closing tag nahi hota, lekin end ka `>` zaroor hona chahiye.

## Relative Paths

| Image Location | Path Example |
|---|---|
| HTML ke same folder mein | `photo.jpg` |
| `images` subfolder mein | `images/photo.jpg` |
| Parent folder mein | `../photo.jpg` |

## Your Tasks

1. Apni image browser mein show karo.
2. `width` ko pehle `150`, phir `300` karke difference dekho.
3. Final width apni pasand se set karo.
4. Image ke neeche apne words mein ek paragraph likho.
5. Meaningful `alt` text likho.

## Image Na Dikhe To Check Karo

- `src` path correct hai?
- Filename aur extension exact same hain?
- `.jpg`, `.jpeg` ya `.png` match kar raha hai?
- Image sach mein `images` folder ke andar hai?
- `img` tag ke end mein `>` hai?
- File save aur browser refresh kiya?

## Self-Check

- [ ] `practical-04/index.html` correct location par hai.
- [ ] `images` folder correct location par hai.
- [ ] Image browser mein visible hai.
- [ ] `alt` meaningful hai.
- [ ] Width set hai.
- [ ] `</img>` nahi likha hai.

Save karo, browser refresh karo aur screenshot share karo.
