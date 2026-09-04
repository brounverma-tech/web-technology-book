# Practical 09: Audio and Video

## Goal

Is practical mein tum local audio aur video files ko HTML page par play karna seekhoge.

## Related Theory

Read: [Chapter 10 — Semantic HTML and Multimedia](../../../chapters/10-semantic-html-and-multimedia.md)

## Step 1: Folder Structure Banao

```text
frontend-practice/
└── practical-09/
    ├── index.html
    └── media/
        ├── sample-audio.mp3
        └── sample-video.mp4
```

1. `practical-09` folder banao.
2. Uske andar `index.html` file banao.
3. Uske andar `media` folder banao.
4. Koi short MP3 file ko `sample-audio.mp3` naam se rakho.
5. Koi short MP4 file ko `sample-video.mp4` naam se rakho.

> Local practice ke liye apni short recording use kar sakte ho. Private ya copyrighted media ko public GitHub repository mein upload mat karo.

## Step 2: Example Type Karo

[index.html](index.html) ka code apni local file mein khud type karo.

## Main Elements and Attributes

| Code | Use |
|---|---|
| `<audio>` | Audio player |
| `<video>` | Video player |
| `<source>` | Media file ka path aur type |
| `controls` | Play, pause aur volume controls |
| `width` | Video ki displayed width |
| `type="audio/mpeg"` | MP3 file ka media type |
| `type="video/mp4"` | MP4 file ka media type |

`source` void element hai, isliye iska closing `</source>` tag nahi hota.

## Your Tasks

1. Audio ko play aur pause karke test karo.
2. Video ko play, pause aur volume change karke test karo.
3. Video width ko pehle `300`, phir `500` karke difference dekho.
4. Final width `400` rakho.
5. Audio aur video ke neeche ek-ek paragraph mein batao ki media kis baare mein hai.

## Important

`autoplay` abhi use mat karo. Browsers ise block kar sakte hain aur unexpected sound user experience ko kharab karta hai.

## Media Na Chale To Check Karo

- File sach mein `media` folder mein hai?
- Filename aur extension exact match karte hain?
- MP3 ke liye `audio/mpeg` hai?
- MP4 ke liye `video/mp4` hai?
- File save aur browser refresh kiya?
- Media file browser-supported format mein hai?

## Self-Check

- [ ] `practical-09/index.html` correct location par hai.
- [ ] `media` folder correct location par hai.
- [ ] Audio controls dikh rahe hain.
- [ ] Audio play ho raha hai.
- [ ] Video controls dikh rahe hain.
- [ ] Video play ho raha hai.
- [ ] Video width 400 hai.
- [ ] Media descriptions khud add ki hain.

Save karo, browser refresh karo aur screenshot share karo.
