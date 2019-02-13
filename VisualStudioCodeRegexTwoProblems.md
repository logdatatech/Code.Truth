
# Regular Expressions Working in VS Code

## Find NewLine+StartOfLine+ExtendedDash

```java
Find: {New Line}{Start of Line}{Extended Dash}  
\n^―
Replace:
―
```

> This will bring the line up.

---

## Basically Looking for Years

```java
Find:
^(\d)(\d)(\d)(\d)
Replace:
\n## $1$2$3$4
```

So we Finding StartOfLine Plus Four Uninterrupted Digits

Replace them with Some MarkDown code and their original group match values
.
> Essentially Replace any number between 1000-9999 with itself and some extra Markup.

---
