# Practical 07: Forms and Input Elements

## Goal

Is practical mein tum user se information lene ke liye basic HTML form banana seekhoge.

## Related Theory

Read: [Chapter 9 — Tables, Forms and Input Elements](../../../chapters/09-tables-forms-and-input-elements.md)

## Step 1: Folder Banao

```text
frontend-practice/
└── practical-07/
    └── index.html
```

## Step 2: Example Type Karo

[index.html](index.html) ka code apni local file mein khud type karo.

## Main Elements

| Element | Use |
|---|---|
| `<form>` | Pura form container |
| `<label>` | Input ka readable naam |
| `<input>` | Short information enter karna |
| `<select>` | Options mein se choose karna |
| `<option>` | Select ka ek option |
| `<textarea>` | Long message enter karna |
| `<button>` | Form submit ya reset karna |

## Important Attribute Connections

```html
<label for="full-name">Full Name:</label>
<input type="text" id="full-name" name="full_name">
```

- Label ka `for` aur input ka `id` same hona chahiye.
- `name` submitted data ka field name hota hai.
- `required` field ko compulsory banata hai.
- `type="email"` browser se email format check karwata hai.

## Your Tasks

Example chalne ke baad:

1. Name input mein `placeholder="Enter your name"` add karo.
2. Email input mein `placeholder="name@example.com"` add karo.
3. Phone field add karo using `type="tel"`.
4. Course options mein **JavaScript** add karo.
5. Submit button se pehle agreement checkbox add karo:

```html
<input type="checkbox" id="agree" name="agree" required>
<label for="agree">I agree to the practice rules.</label>
```

6. Dummy information fill karke Submit click karo.
7. Clear button test karo.

> Practice ke liye dummy information use karo. Real password ya private information mat enter karo.

## Submit Par Kya Hoga?

Abhi form kisi backend/server se connected nahi hai. Valid form submit karne par page refresh ho sakta hai. Ye error nahi hai. Data save karna backend ke time par seekhenge.

## Common Mistakes

- Label ka `for` aur input ka `id` different rakhna
- Input mein `name` bhoolna
- `input` ke liye `</input>` likhna
- `option` ko `select` ke bahar likhna
- Real personal information se practice karna

## Self-Check

- [ ] `practical-07/index.html` correct location par hai.
- [ ] Name, email aur age fields dikh rahe hain.
- [ ] Course dropdown kaam kar raha hai.
- [ ] Message box dikh raha hai.
- [ ] Phone field add kiya hai.
- [ ] JavaScript option add kiya hai.
- [ ] Required agreement checkbox add kiya hai.
- [ ] Submit aur Clear buttons test kiye hain.

Save karo, browser refresh karo aur screenshot share karo.
