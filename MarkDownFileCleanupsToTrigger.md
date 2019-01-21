<!-- AuthoredBy:nathan@logdata.tech @NK -->

# MarkDown File Clean-ups to Trigger

## LINE ENDINGS

REPLACE Trailing Single Spaces Followed by NewLine with Just New Line

RegEx " \n" With "\n"

" " Must Stay Stay that is A Line Break

3 Plus Spaces with NewLine Replace with NewLine

If Line is also a Heading so First Character is "#" and Last Character is "?","." then replace that character with ""

---

## Bullet LISTS

Change them to Unordered Lists "-".

---

## START OF LINE

When Start of Line is "\* " So a Bullet List Replace with an Unordered List.

"^\* " Replace with "- "

---

"\*\*" Lines should not start with Bold use a Heading replace with "##" as a default. Note the Trailing "\*\*" will also need to be replace with "" {Null/Empty String}

---

Also Headings should be Marked apart with an horizontal Rule and a Blank Line

RegEx.FIND {with Not the Line Two Prior being equal to exactly "---"}
"\n##"
RegEx.REPLACE
\n---\n\n##

---

## TO Replace Sequential Underlines

RegEx.FIND
"---\n\n---"
RegEx.REPLACE
"---"

---

## Pretty Advanced Examples

[https://superuser.com/questions/1325075/vs-code-find-in-current-file-regular-expressions](https://superuser.com/questions/1325075/vs-code-find-in-current-file-regular-expressions)

```
In VS Code it would look like this:
Find: (##)(\s+)(\[)(\])(\(.*?\))(Heading)
Replace: $1$2$3$6$4$5
INPUT
## [](https://www.website.com/)Heading
OUTPUT
## [Heading](https://www.website.com/)

Let's try something more general:
Find: (##)(\s+)(\[)(\])(\(.*?\))([^^]+)
Replace: $1$2$3$6$4$5
INPUT
## [](https://www.website.com/)Heading
## [](https://www.website2.com/)Heading2
## [](https://www.website3.com/)Heading3
OUTPUT
## [Heading](https://www.website.com/)
## [Heading2](https://www.website2.com/)
## [Heading3](https://www.website3.com/)
```

---
