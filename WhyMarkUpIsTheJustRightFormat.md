# Why MarkUp is the Just Right Format

<!-- Author nathan@logdata.tech -->

## Markdown has Won

[wikipedia.org/wiki/Markdown](https://en.wikipedia.org/wiki/Markdown)

> Not to heavy, not to light = Just Right. [wikipedia.org/wiki/Lightweight_markup_language](https://en.wikipedia.org/wiki/Lightweight_markup_language)

Markdown allows you to write using an easy-to-read, easy-to-write plain text format, that can then be converted into structurally valid HTML. So, to be entirely precise, Markdown is really two things:

> A plain text formatting syntax

and

> A software tool (the first version of which was written in Perl) that converts the plain text formatting into HTML.

Markdown incorporates a handful of simple, fairly intuitive, and easy-to-use syntax conventions. Especially for you as a software engineer – who is not put off by needing to learn and use these basic syntax conventions – Markdown can indeed be the path of least resistance between what you want to write and getting it written.

[stackoverflow.com/questions/659227/compare-and-contrast-the-lightweight-markup-languages](https://stackoverflow.com/questions/659227/compare-and-contrast-the-lightweight-markup-languages)

---

## In Good Company who Else decided on MarkDown

* [http://github.com](http://github.com) an enhanced version called GFM github flavoured markup
* [https://docs.microsoft.com/](https://docs.microsoft.com/) Very high number of articles.
* [https://blog.ghost.org/markdown/](https://blog.ghost.org/markdown/) Ghost Blogging Tool

---

## Editors that do a Very Good Job With Markdown

* Visual Studio Code {hard to beat it's Free runs on Windows,MacOS,Linux} Lots of Extensions to assist.

---

## Syntactically Correct - AutoPilot for Structure

Markdown has Linters that can automatically apply several dozen powerful rule sets to a Markdown file.

Rules like

> MD012/no-multiple-blanks: Multiple consecutive blank lines [Expected: 1; Actual: 2]

```python
MD024 - Multiple headings with the same content
Tags: headings, headers

Aliases: no-duplicate-heading, no-duplicate-header

Parameters: siblings_only, allow_different_nesting (boolean; default false)

This rule is triggered if there are multiple headings in the document that have the same text:

# Some text

## Some text
```

When processed with automation and a little bit of rigour you essentially have a continuous integration for Documentation quality no need to multiple human review something that they do poorly.

---

## More Reading on MarkDown

[toptal.com/web/markdown-the-writing-tool-for-software-developers/](https://www.toptal.com/web/markdown-the-writing-tool-for-software-developers/)

<!-- TODO: Make the RegEx for Finding a Bare-URL and replacing with [$BARE-URL$]($BARE-URL$) -->

---

## A Brief History of MarkUp Languages

[wikipedia.org/wiki/Markup_language](https://en.wikipedia.org/wiki/Markup_language)

In computer text processing, a markup language is a system for annotating a document in a way that is syntactically distinguishable from the text. The idea and terminology evolved from the "marking up" of paper manuscripts, i.e., the revision instructions by editors, traditionally written with a blue pencil on authors' manuscripts. In digital media, this "blue pencil instruction text" was replaced by tags, that is, instructions are expressed directly by tags or "instruction text encapsulated by tags." However the whole idea of a mark up language is to avoid the formatting work for the text, as the tags in the mark up language serve the purpose to format the appropriate text (like a header or the beginning of a paragraph etc.). Every tag used in a Markup language has a property to format the text we write.

Examples include typesetting instructions such as those found in LaTeX, or structural markers such as XML tags. Markup instructs software that renders the text to carry out appropriate actions, but is omitted from the version of the text that users see.

### SGML

Patient Zero but so strict almost never used.

### XML

XML does not have pre-defined presentation semantics—meaning that their specification prescribes how to present the structured data.
and is general purpose.

### HTML 1.0 -> 2.0 -> 3.0 -> 4.0 -> 5.0

The Main Problem with HTML now for Portability is it's crazy rich feature set.

* CSS
* JavaScript
* HTML 5 Native Specials

HTML has pre-defined presentation semantics—meaning that their specification prescribes how to present the structured data.

HyperText Markup Language (HTML), one of the document formats of the World Wide Web, is an instance of Standard Generalized Markup Language or SGML, and follows many of the markup conventions used in the publishing industry in the communication of printed work between authors, editors, and printers.
