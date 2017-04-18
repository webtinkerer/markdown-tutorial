# Advanced Formatting
By this time we have already learned major blocks of Markdown - basic [text formatting], how to define different [lists], add [links] and [images]. It is a lot if you think about this. Your toolbox is filled by very powerful syntax. But as you will see it is not the end of the story. [Markdown][] is not limited by this set of elements, you can do even more:

* [Inline Code](#inline-code)
* [Block Code](#block-code)
* [Embedded HTML](#embedded-html)
* [Escape Characters](#escape-characters)
* [Horizontal Rules](#horizontal-rules)
* [Automatic Links](#automatic-links)

## Inline Code
As you probably noticed I'm using the inline code a lot across this tutorial, you know, it is difficult to write about syntax without code snippets, even tiny ones. How is it done? To format text as code span, wrap it with the backtick quotes (`` ` ``text`` ` ``):
```markdown
The most popular tag in HTML is `div`. Do you know why?
```
Output:
```html
<p>The most popular tag in HTML is <code>div</code>. Do you know why?</p>
```

## Block Code
You can also specify an entire block of preformatted code, just indent every line of the block by at least four spaces or one tab:
```markdown
    console.log('Hello world!');
```
Output:
```html
<pre>
  <code>console.log('Hello world');</code>
</pre>
```

A code block continues until it reaches a line that is not indented (or the end of the document):
```markdown
    console.log('Hello world!');
    console.log('How are you?');
This is a paragraph.
```
Output:
```html
<pre>
    <code>
        console.log('Hello world!');
        console.log('How are you?');
    </code>
</pre>
<p>This is a paragraph.</p>
```

Also, regular Markdown syntax won't be processed within either inline code or code blocks (this means it is also very easy to use Markdown to write about Markdown syntax):
```markdown
    Here is the example of *text* formatting by **Markdown**.
```
Output:
```html
<pre>
    <code>Here is example of *text* formatting by **Markdown**.</code>
</pre>
```

Keep in mind that any ampersands `&` and angle brackets `<` `>` will be automatically escaped to be further translated safely into HTML elements.
```markdown
    Here is an example of escaping & and < characters.
```
Output:
```html
<pre>
    <code>Here is an example of escaping &amp; and &lt; characters.</code>
</pre>
```

## Embedded HTML
You can safely include arbitrary HTML markup in any Markdown document; it will be parsed as is during converting key elements to HTML tags. The only restriction about HTML syntax Markdown has is related to the block-level HTML elements - `<div>`, `<table>`, `<pre>`, etc. You should separate them from the surrounding content by blank lines, and the start and the end tags of the HTML block should not be indented with extra spaces or tabs. Let's see example:
```markdown
This is a paragraph.

<div>
    <span>Some HTML markup.</span>
</div>

This is another paragraph.
```
Output:
```html
<p>This is a paragraph.</p>
<div>
    <span>Some HTML markup.</span>
</div>
<p>This is another paragraph.</p>
```

Keep in mind that Markdown formatting syntax is not processed within block-level HTML elements. It will be rendered as is:
```markdown
<div>
    Here *is* used some **Markdown** syntax.
</div>
```
Output:
```html
<div>
    Here *is* used some **Markdown** syntax.
</div>
```

The same is true for encoding `&` and `<` characters within HTML block-level elements - unfortunately, they won't be escaped, so be accurate:
```markdown
<div> Here we have & and <. They are not escaped, unfortunately.</div>
```
Output:
```html
<div> Here we have & and <. They are not escaped, unfortunately.</div>
```

Span-level HTML elements from the other side can be used anywhere in Markdown - [paragraphs], [list items], [headers], [blockquotes]. You can also use Markdown [text formatting] syntax within span-level elements, it will be processed correctly and converted to the corresponding HTML tags. Here is an example:
```markdown
This is a paragraph with <span>*HTML* **span-level**</span> element.
```
Output:
```html
<p>This is a paragraph with <span><em>HTML</em> <strong>span-level</strong></span> element.</p>
```

Even `&` and `<` characters within HTML span-level elements will be correctly escaped:
```markdown
This is a paragraph with <span>& and <</span> that will be escaped.
```
Output:
```html
<p>This is a paragraph with <span>&amp; and &lt;</span> that will be escaped.</p>
```

## Escape Characters
Sometimes you need to display Markdown key character as the literal character without any conversion. To achieve it just precede such character with a backslash `\`:
```markdown
Render one asterisk (\*) followed by another asterisk (\*) as is. 
```
Output:
```html
<p>Render one asterisk (*) followed by another asterisk (*) as is.</p>
```

If you remove `\` character, you probably won't be satisfied with the result:
```markdown
Render one asterisk (*) followed by another asterisk (*) as is. 
```
Output:
```html
<p>Render one asterisk (<em>) followed by another asterisk (</em>) as is.</p>
```

You can escape by `\` any of the following key characters: `\`, `` ` ``, `*`, `_`, `{}`, `[]`, `()`, `#`, `+`, `-`, `.`, `!`. But to escape `` ` `` within code spans you should use multiple backticks as the open and close key elements:
```markdown
Here is ``code span with (`)``.
```
Output:
```html
<p>Here is <code>code span with (`)</code>.</p>
```

## Horizontal Rules
You can produce a horizontal rule tag `<hr>` by placing three or more hyphens `-`, asterisks `*`, or underscores `_` on a line by themselves. If you wish, you may use spaces between the hyphens or asterisks. Each of the following lines will produce a horizontal rule:
```markdown
* * *

---

_______
```
Output:
```html
<hr>
<hr>
<hr>
```

Keep in mind that if will you use hyphens `-` to create a horizontal line, you will need to leave one blank line above them. Otherwise, Markdown will consider your hyphens `-` as a part of the [header level 2](01-Styling-Text.md#headings) syntax.

## Automatic Links
Markdown also supports a shortcut style for creating «automatic» links for URL - simply surround the URL with angle brackets `<` `>`. It will mean that you wish to show the actual text of an URL or email address and also have it be a clickable link, here is an example:
```markdown
<http://google.com>
```
Output:
```html
<a href="http://google.com">http://google.com</a>
```

Well, by this moment we are done with so-called «vanilla» Markdown syntax, next time we look at so-called [flavored Markdown][next], different Markdown dialects.

[Markdown]: https://en.wikipedia.org/wiki/Markdown "Markdown - Wikipedia"
[previous]: 04-Adding-Images.md "Adding Images in Markdown"
[next]: 06-Flavored-Markdown.md "Flavored Markdown"
[text formatting]: 01-Styling-Text.md "Styling Text in Markdown"
[lists]: 02-Adding-Lists.md "Adding Lists in Markdown"
[links]: 03-Working-With-Links.md "Working With Links in Markdown"
[images]: 04-Adding-Images.md "Adding Images in Markdown"
[paragraphs]: 01-Styling-Text.md#paragraphs "Styling Text in Markdown"
[list items]: 02-Adding-Lists.md "Adding Lists in Markdown"
[headers]: 01-Styling-Text.md#headings "Styling Text in Markdown"
[header level 2]: 01-Styling-Text.md#headings "Styling Text in Markdown"
[blockquotes]: 01-Styling-Text.md#quotes "Styling Text in Markdown"
