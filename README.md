# The Ultimate Guide to Markdown
Have you ever heard about [Markdown][]? What is this?. A little bit?. Then you are definitely in the right place. This tutorial contains everything that you need to get started with Markdown, get familiar with it, learn it and fall in love with it at the end. You have some doubts, don't you? But the truth is that it's fantastic markup language, very simple and very powerful at the same moment.

> «Markdown is intended to be as easy-to-read and easy-to-write as is feasible. Readability, however, is emphasized above all else. A Markdown-formatted document should be publishable as-is, as plain text, without looking like it’s been marked up with tags or formatting instructions.» 

With all this said keep in mind that Markdown is not a replacement for HTML, its goal is different:

> «The overriding design goal for Markdown’s formatting syntax is to make it as readable as possible.»

Markdown is the language for writers and bloggers, who wish and need to write well-structured text without pain and headache, it's for all who are in love in typing text, sentences, words, lots of words. Each and every day. Every minute. Every second!

So, let's get started!

## License
Copyright (c) 2017 Quteron  
Licensed under the [MIT license][].

---

## Table of Content

* [Introduction](00-Introduction.md)
* [Styling Text](01-Styling-Text.md)
* [Adding Lists](02-Adding-Lists.md)
* [Working with Links](03-Working-With-Links.md)
* [Adding Images](04-Adding-Images.md)
* [Advanced Formatting](05-Advanced-Formatting.md)
* [Flavored Markdown](06-Flavored-Markdown.md)
* [Editor with Markdown Support](07-Editors-With-Markdown-Support.md)
* [Summary](08-Summary.md)

---

## Quick Syntax Reference
Here is a quick reference for Markdown syntax that is described in this tutorial:

### Styling Text
| Style                | Syntax                                    | Example                         | Output                      |
|-------------------|:-----------------------------------------:|:----------------------------:|:---------------------------:|
| [Bold]            | `**` `text` `**`                          | \*\*bold text\*\*            | **bold text**               |
| [Italic]          | `*` `text` `*`                            | \*italic text\*              | *italic text*               |
| [Bold and Italic] | `***` `text` `***`                        | \*\*\*super text\*\*\*       | ***super text***            |
| [Inline Code]     | `` ` `` `code` `` ` ``                    | \`code\`                     | `code`                      |
| [Link]            | `[` `title` `]` `(` `url` `)`             | \[title\]\(http://\)         | [Google](http://google.com) |
| [Automatic Link]  | `<` `url` `>`                             | \<http://\>                  | <http://google.com>         |

### Headings
| Style                | Syntax                                    | Example                         | 
|-------------------|-------------------------------------------|------------------------------|
| [H1]              | `#` `text`                                | \# Level 1                   |
| [H2]              | `##` `text`                               | \#\# Level 2                 |
| [H3]              | `###` `text`                              | \#\#\# Level 3               |
| [H4]              | `####` `text`                             | \#\#\#\# Level 4             |
| [H5]              | `#####` `text`                            | \#\#\#\#\# Level 5           |
| [H6]              | `######` `text`                           | \#\#\#\#\#\# Level 6         |

*Output*:
# Level 1
## Level 2
### Level 3
#### Level 4
##### Level 5
###### Level 6

### Quotes
| Style                | Syntax                                    | Example                         | 
|-------------------|:-----------------------------------------:|:----------------------------:|
| [Quote]           | `>` `quote`                               | \> quote                     |

*Output*:
> This is quote!

### Images
| Style                | Syntax                                    | Example                         | 
|-------------------|:-----------------------------------------:|:----------------------------:|
| [Image]           | `!` `[` `alt` `]` `(` `url` `"title"` `)` | \!\[alt\]\(http:// "title"\) |

*Output*:

![Google](https://www.google.com/images/srpr/logo11w.png)

### Lists
| Style                | Syntax                                    | Example                         | 
|-------------------|:-----------------------------------------:|:----------------------------:|
| [Unordered]       | `*` `item `                               | * item                       |
| [Ordered]         | `1` `.` `item `                           | 1. item                      |

### Horizontal Rule
| Style                  | Syntax                                    | Example                         | 
|---------------------|:-----------------------------------------:|:----------------------------:|
| [Horizontal Rule][] | `---`                                     | \-\-\-                       |

*Output*:

---

[Markdown]: https://en.wikipedia.org/wiki/Markdown "Markdown - Wikipedia"
[Bold]: 01-Styling-Text.md#text
[Italic]: 01-Styling-Text.md#text
[Bold and Italic]: 01-Styling-Text.md#text
[H1]: 01-Styling-Text.md#headings
[H2]: 01-Styling-Text.md#headings
[H3]: 01-Styling-Text.md#headings
[H4]: 01-Styling-Text.md#headings
[H5]: 01-Styling-Text.md#headings
[H6]: 01-Styling-Text.md#headings
[Quote]: 01-Styling-Text.md#quotes
[Unordered]: 02-Adding-Lists.md#unordered-lists
[Ordered]: 02-Adding-Lists.md#ordered-lists
[Inline Code]: 05-Advanced-Formatting.md#inline-code
[Link]: 03-Working-With-Links.md
[Automatic Link]: 05-Advanced-Formatting.md#automatic-links
[Image]: 04-Adding-Images.md
[Horizontal Rule]: 05-Advanced-Formatting.md#horizontal-rules
[MIT license]: https://en.wikipedia.org/wiki/MIT_License "MIT License - Wikipedia"
