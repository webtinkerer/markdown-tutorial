# Flavored Markdown
Till this moment we were talking only about «vanilla» [Markdown][] that was created by [John Gruber][] and published on his website [Daring Fireball][]. But as long as Markdown became popular and widely used on different platforms, different dialects, so-called «flavored» Markdown, were appeared. It is not a surprise, you always want more and more, only a day ago you had everything that you could dream about for pure writing, and next moment came, and you needed tables, strike-through styling text, or funny icons, etc.

As you probably remember Markdown is used on really different platforms, from social network to blogging. Almost all of them have their «flavored» Markdown with some crossed features.

Let's look briefly at some of these platforms and not standard features that they added to the language:

* [Ghost](#ghost)
* [GitHub](#github)
* [StackOverflow](#stackoverflow)

## Ghost
[Ghost][] blogging platform among full support of standard Markdown also has some nice advanced things, especially for blog posts:

**Strikethrough**
```markdown
\~\~deleted text\~\~
```
      
**Highlight**
```markdown
==das ist fantastisch==
```
      
**Footnotes**
```markdown
Here is an awesome[^1] article[^2]!
      
[^1] Actually, it is amazing!
[^2] It is a book, sorry. 
```

For more details, please, follow the link [Ghost - Ultimate Guide to Markdown](https://blog.ghost.org/markdown/)

## GitHub
[GitHub][] «flavored» Markdown is full of nice things, it is worth to know them all if you widely use the repository on the daily manner. For instance, in GitHub you can create tables using only two key characters - `|` and `-`:
```markdown
| Key  | Name      |
|------|-----------|
|  \   | Backslash |
|  |   | Pipe      |
```

You can also add funny, emotional icons [Emoji] to your comments:
```markdown
Let's smile! :smile:
```

For the detailed list of supported features, please, read [Writing on GitHub](https://help.github.com/categories/writing-on-github/) article.

## Stackoverflow
[Stackoverflow][] has fully supported for standard Markdown markup elements as long as offers few its own. For instance, it has a special syntax to hide a certain piece of text and have it only be visible when a user moves the mouse over it. It is so-called «spoilers». To achieve this use additional exclamation mark `!` after `>`:
```markdown
At the end of episode five, it turns out that
>! he is her father.
```

For the detailed list of all supported features, please, follow the link [Stackoverflow - Markdown Help](http://stackoverflow.com/editing-help).

If you do widely use one of the platforms that support not only «vanilla» Markdown but also has «flavored» Markdown, it is worth to attentively read platform's provided documentation or helping guide and learn all new features. Besides the thing that this move will make you more productive and creative but also bring fun to your daily tasks.

Although, if you don't use any of the mentioned platforms and prefer to write text with Markdown syntax using a text editor, jump to the next post - [Editors With Markdown Support][next].

[Markdown]: https://en.wikipedia.org/wiki/Markdown "Markdown - Wikipedia"
[John Gruber]: https://en.wikipedia.org/wiki/John_Gruber "John Gruber - Wikipedia"
[Daring Fireball]: http://daringfireball.net/projects/markdown/syntax "Markdown Syntax By John Gruber"
[Ghost]: https://ghost.org "Ghost - Blogging Platform"
[StackOverflow]: https://stackoverflow.com "StackOverflow - Q&A Community"
[GitHub]: https://github.com "GitHub - Project Hosting Platform"
[Emoji]: https://en.wikipedia.org/wiki/Emoji "Emoji - Wikipedia"
[next]: 07-Editors-With-Markdown-Support.md "Editors With Markdown Support"
