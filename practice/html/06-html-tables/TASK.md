# Practical 06: HTML Tables

## Goal

Is practical mein tum rows aur columns mein data dikhana seekhoge.

## Related Theory

Read: [Chapter 9 — Tables, Forms and Input Elements](../../../chapters/09-tables-forms-and-input-elements.md)

## Step 1: Folder Banao

```text
frontend-practice/
└── practical-06/
    └── index.html
```

## Step 2: Example Type Karo

[index.html](index.html) ka code apni local file mein khud type karo.

## Table Structure

```html
<table border="1">
    <tr>
        <th>Topic</th>
        <th>Status</th>
    </tr>

    <tr>
        <td>HTML</td>
        <td>Completed</td>
    </tr>
</table>
```

## Tag Meaning

| Tag | Meaning |
|---|---|
| `<table>` | Puri table ka container |
| `<tr>` | Table row — ek horizontal line |
| `<th>` | Heading cell |
| `<td>` | Normal data cell |

Easy formula:

```text
table → rows → cells
<table> → <tr> → <th> or <td>
```

`border="1"` abhi grid lines clearly dekhne ke liye use kar rahe hain. CSS seekhne ke baad border ko CSS se banayenge.

## Your Tasks

Example chalne ke baad table mein ye three rows khud add karo:

| Topic | Status | Practice |
|---|---|---|
| Images | Completed | 04 |
| Lists | Completed | 05 |
| Tables | Learning | 06 |

Phir ek naya column **Remark** add karo:

- Completed rows ka remark: **Good**
- Tables row ka remark: **In Progress**

Yaad rakho: heading row aur har data row mein cells ki sankhya same honi chahiye.

## Common Mistakes

- `td` ko `tr` ke bahar likhna
- Kisi row mein extra ya missing cell rakhna
- Closing `</tr>` bhoolna
- Heading ke liye `td` use karna instead of `th`

## Self-Check

- [ ] `practical-06/index.html` correct location par hai.
- [ ] Table mein borders dikh rahe hain.
- [ ] First row mein headings hain.
- [ ] Har data item `td` ke andar hai.
- [ ] Images, Lists aur Tables ki rows add ki hain.
- [ ] Remark column add kiya hai.
- [ ] Har row mein four cells hain.

Save karo, browser refresh karo aur screenshot share karo.
