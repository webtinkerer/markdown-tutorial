# Styling Text

In the [previous][] post we have learned the considerations why Markdown was created. Now let's dive into the real code and learn how to apply basic text formatting to your document.

## Text
[Markdown][] allows you to differently emphasize a word, a phrase or even the whole sentence. To emphasize a little bit enclose your text in the single asterisks (`*`text`*`): 
```markdown
This *word* is emphasized a little bit. 
It will look like *italic* text.
```
Output:
```html
<p>This <em>word</em> is emphasized a little bit. 
It will look like <em>italic</em> text.</p>
```

If you need to emphasize text more - enclose it in the double asterisks with no spaces between them (`**`text`**`):
```markdown
This **word** is more emphasized. 
It will look like **bold** text.
```
Output:
```html
<p>This <strong>word</strong> is more emphasized. 
It will look like <strong>bold</strong> text.</p>
```

There is also a third level of emphasizing - if you wish to put your text in the spotlight, enclose it in the triple asterisks with no spaces between them (`***`text`***`):
```markdown
This ***word*** is spotlight. 
It will look like **bold** and *italic* text at the same time.
```
Output:
```html
<p>This <strong><em>word</em></strong> is spotlight. 
It will look like <strong>bold</strong>and <em>italic</em> text at the same time.</p>
```
As you can see in pure HTML it just applies two styles at once - `em` and `strong`.

You can also achieve the same result by using underscores (`_`) instead of asterisks (`*`), they are interchangeable with one restriction - the same character must be used to open and close an emphasis span:
```markdown
Here we emphasize __word__ by underscore _characters_.
```
Output:
```html
<p>Here we emphasize <strong>word</strong> by underscore <em>characters</em>.</p>
```

<div class="note">It is a good practice to choose one set of characters for all levels of emphasizing - either <code>*</code> or <code>_</code> - and use it across all your documents.</div>

## Paragraphs
Paragraphs are just one or more lines of consecutive text followed by one or more blank lines. A blank line is an any empty line, with no other characters except one or more spaces or tabs. Here is a simple example:
```markdown
This is a paragraph 1.
    
This is a paragraph 2.
```
Output:
```html
<p>This is a paragraph 1.</p>
<p>This is a paragraph 2.</p>
```

If you don't have the intent to start a new paragraph but wish to start next sentence with a new line - you need to add a so-called «soft break». In HTML this can be done by `<br>` tag. To achieve the same behavior in Markdown, just add two extra spaces to the previous line and start next sentence from the beginning of the next line. You don't need to add any blank lines, just two extra spaces. Be accurate; space is not so evident in the text in comparison with the blank lines:
```markdown
This is a paragraph with a soft break.  This sentence is in the same paragraph, is only started with a new line. 
```
Output:
```html
<p>This is a paragraph with the soft break. <br>
This sentence is in the same paragraph, is only started with a new line. </p>
```

## Headings
Now let's take a look at headings. They are frequently used on websites, blog posts, and other notices. They act like titles or subtitles. 

As you probably know HTML supports 6 levels of headings like `h1`, `h2` or `h6`, where `h1` is the largest heading and `h6` is the smallest heading. Here they are:
```html
<h1>Header 1</h1>
<h2>Header 2</h2>
<h3>Header 3</h3>
<h4>Header 4</h4>
<h5>Header 5</h5>
<h6>Header 6</h6>
```

To create such headings using Markdown, add one or more hash marks `#` before your heading text. The number of `#` will determine the level of your heading:
```markdown
# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6
``` 

<div class="note"><p>You can safely omit a space between a sequence of <code>#</code> and a heading text. But keep in mind that Markdown considers all characters after <code>#</code> and until the end of the line as a header text, with one excuse - trailing <code>#</code> characters are skipped. It is made for the cosmetic purpose of somehow «close» header. The «closing» <code>#</code> don't even need to match the number of <code>#</code> used to open the header.</p></div>

Also, Markdown supports special syntax for headings of level `1` and level `2`. Here it is: 
```markdown
Header 1
=
Put one or more '=' characters at the beginning of the next line 
after header text for level `1` heading

Header 2
-
Put one or more '-' characters at the beginning of the next line 
after header text for level `2` heading
```
Output:
```html
<h1>Header 1</h1>
<p>Put one or more '=' characters at the beginning of the next line 
after header text for level <сode>1</code> heading</p>
<h2>Header 2</h2>
<p>Put one or more '-' characters at the beginning of the next line 
after header text for level <сode>2</code> heading</p>
```

### Quotes
To add a quote to your document just add trailing `>` at the beginning of the line:
```markdown
> This a simple blockquote.
```
Output:
```html
<blockquote>
    <p>This a simple blockquote.</p>
</blockquote>
```

<div class="note">You don't need to put extra space between <code>></code> and the first letter of the quote, without that space, you will still get a correctly rendered block quote. It is used only for better readability, the same situation as with <code>#</code> marks in headings.</div>

To create a multi-line quote just put `>` on each line of your quote text:
```markdown
> This a multi-line blockquote.
> Each line is started with `>` character.
```
Output:
```html
<blockquote>
    <p>This a multi-line blockquote.
    Each line is started with <сode>&gt;</code> character.</p>
</blockquote>
```

The syntax above is so called «classic style», you can also create quotes with «lazy style». For this purpose put `>` only at the beginning of the first line of your quote:
```markdown
> This a multi-line blockquote in lazy style.
Only first line is started with `>` character
```
Output:
```html
<blockquote>
  <p>This a multi-line blockquote in lazy style.
  Only first line is started with <сode>&gt;</code> character</p>
</blockquote>
```

Keep in mind that you need to use «lazy style» very carefully with the quotes contained blank lines:
```markdown
> Quote with the blank line.
Next line will be a blank line and a sign for Markdown to complete quote, unfortunately.

This text will be out of the quote, at the newly created paragraph.
```
Output:
```html
<blockquote>
    <p>Quote with the blank line.
    Next line will a blank line and a sign for Markdown to complete quote, unfortunately.</p>
</blockquote>
<p>This text will be out of quote, at the newly created paragraph.</p>
```

As you can see we got the result not that we wanted. To include a blank line to the quote block, you need either switch to the «classic style» or put additional `>` at the beginning of the blank line:
```markdown
> Quote with the blank line.
Next line will be a blank line.
>
This text will be within a quote.
```
Now we have the correct output:
```html
<blockquote>
    <p>Quote with the blank line.
    Next line will be a blank line.</p>

    <p>This text will be within quote.</p>
</blockquote>
```

You can also nest one quote within another one by adding additional levels of `>`:
```markdown
> This is level `1` quote.
>> And this is level `2` quote.
```
Output:
```html
<blockquote>
    <p>This is level <сode>1</code> quote.</p>
    <blockquote>
        <p>And this is level <сode>2</code> quote.</p>
    </blockquote>
</blockquote>
```

### Real Example
Now let's see how can we combine different elements that we have learned by current moment in one document:
```markdown
### Header level 3
Here is a first paragraph with only **differently** *emphasized* ***words***. 
To create the second paragraph leave one blank line.

Here is a second paragraph followed by a single line quote.
> It is a single line quote.
To complete quote and start another paragraph add another blank line.

Here is a third paragraph.
``` 
Output:
```html
<h3>Header level 3</h3>
<p>Here is a first paragraph with only 
<strong>differently</strong> <em>emphasized</em> <strong><em>words</em></strong>. 
To create second paragraph leave one blank line.</p>
<p>Here is a second paragraph followed by a single line quote.</p>
<blockquote>
    <p>It is a single line quote.
    To complete quote and start another paragraph add another blank line.</p>
</blockquote>
<p>Here is a third paragraph.</p>
```

Next time we will look how to add different lists to our document - [Adding Lists in Markdown][next].

[Markdown]: https://en.wikipedia.org/wiki/Markdown "Markdown - Wikipedia"
[previous]: /ultimate-guide-markdown-introduction "Introduction to Markdown"
[next]: /ultimate-guide-markdown-adding-lists "Adding Lists in Markdown"
