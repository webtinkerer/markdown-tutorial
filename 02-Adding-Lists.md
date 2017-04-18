# Adding Lists
From ancient times there are two well-known types of lists - bullet points and list with numbers, in other words - [unordered](#unordered-lists) and [ordered](#ordered-lists) lists.

<h2 id="unordered-lists">Unordered Lists</h2>
You can make an unordered list by preceding list items with the asterisk character `*`:
```markdown
* Item 1
* Item 2
```
Output:
```html
<ul>
   <li>Item 1</li>
   <li>Item 2</li>
</ul>
```

You can also achieve the same result by using either dash `-` or plus sign `+`:
```markdown
+ Item 1
+ Item 2
```
Output:
```html
<ul>
   <li>Item 1</li>
   <li>Item 2</li>
</ul>
```

You can even mix key characters in one list (although it is not a good practice):
```markdown
+ Item 1
* Item 2
- Item 3
```
Output:
```html
<ul>
   <li>Item 1</li>
   <li>Item 2</li>
   <li>Item 3</li>
</ul>
```

<div class="note">Keep in mind that you cannot omit space between key character and list item text, it is required by Markdown syntax.</div>

<h2 id="ordered-lists">Ordered Lists</h2>
To make an ordered list start with a number followed by a period `.` and space (all characters are mandatory):
```markdown
1. Item 1
2. Item 2
```
Output:
```html
<ol>
   <li>Item 1</li>
   <li>Item 2</li>
   <li>Item 3</li>
</ol>
```

If you omit one of the characters (number, period `.` or space), you won't see an ordered list, but rather a new paragraph:
```markdown
1.Item 1
2 Item 2
```
Output:
```html
<p>1.Item 1
2 Item 2</p>
```

Note that the number value itself is irrelevant, [Markdown][] uses just simple HTML syntax for ordered list without any additional configuration or attributes. There is no way to change this logic, unfortunately.
```markdown
2. Item 1
4. Item 2
1. Item 3
```
Output:
```html
<ol>
   <li>Item 1</li>
   <li>Item 2</li>
   <li>Item 3</li>
</ol>
```
That is why you can simplify ordered list creation by specifying just `1` for a number for all list items. In this case, you don't need to track ordered numbers and can easily apply any changes, either adding a new item or removing an old one from the middle. 
```markdown
1. Item 1
1. Item 2
1. Item 3
```
Output:
```html
<ol>
   <li>Item 1</li>
   <li>Item 2</li>
   <li>Item 3</li>
</ol>
```

Keep in mind that sometimes you can accidentally trigger an ordered list by writing something like this:
```markdown
1985. The great year.
```
Output:
```html
<ol>
   <li>The great year.</li>
</ol>
```

So whenever there is a possibility to have a number-period-space sequence at the beginning of a line, escaped by backslash `\` the period `.`:
```markdown
1985\. The great year.
```
Output:
```html
<p>1985. The great year.</p>
```

## How does Markdown analyze list syntax 
Markdown only considers a start of the unordered list if the following requirements are met:

 * list item key character `*` (`-` or `+`) stays at the beginning of the line;
 * there is a blank line before this key character.

Then all further text will be considered as a part of the current list item until another list item key character will be met at the beginning of the line. Markdown will end list as soon as meets next blank line.
```markdown
This is paragraph before the list. 

* number, 
* period `.` 
* space.

This is a paragraph after list.
```
Output:
```html
<p>This is paragraph before list. </p>
<ul>
   <li>number,</li>
   <li>period <code>.</code> and </li>
   <li>space.</li>
</ul>
<p>This is a paragraph after list.</p>
```
This works the same way for the ordered lists too.

## Using text format elements within lists
You can also specify any text formatting within list item text as you might expect:
```language-markdown
* This item contains **bold** text.
* And this item contains *italic* text.
```
Output:
```html
<ul>
   <li>This item contains <strong>bold</strong> text.</li>
   <li>And this item contains <em>italic</em> text.</li>
</ul>
```

To have a paragraph as a list item text, you need to put a blank line between list items:
```markdown
1. number,
 
2. period `.` and
 
3. space.
```
Output:
```html
<ol>
   <li><p>number,</p></li>
   <li><p>period <code>.</code> and</p></li>
   <li><p>space.</p></li>
</ol>
``` 

You can create multi-paragraph list items by indenting paragraphs from the second by four spaces or one tab and leave blank lines between list items and paragraphs too:
```markdown
1. First paragraph.

    Second Paragraph

2. First paragraph.

    Second Paragraph
```
Output:
```html
<ol>
   <li>
      <p>First paragraph.</p>
      <p>Second Paragraph</p></li>
   <li>
      <p>First paragraph.</p>
      <p>Second Paragraph</p></li>
</ol>
``` 

Here are general rules for nesting formatted text elements within lists:

* to have a paragraph within the list item, it must be indented by either four spaces or one tab;
* to have a blockquote within a list item, it must be indented by at least one space;
* to have a code block within a list item, it must be indented by either eight spaces or two tabs.

## Nested lists
Markdown also allows nesting one list within another one; the syntax will just be the same as for ordinary lists, only add four extra spaces before list item key character for the next depth:
```markdown
* Item 1
    * Item 1.1
        * Item 1.1.1
* Item 2
```
Output:
```html
<ul>
   <li>Item 1
      <ul>
         <li>Item 1.1
            <ul>
               <li>Item 1.1.1</li>
            </ul>
         </li>
      </ul>
   </li>
   <li>Item 2</li>
</ul>
```

You can even mix two types of the lists:
```markdown
* Item 1
    1. Item 1.1
        * Item 1.1.1
    2. Item 1.2 
* Item 2
```
Output:
```html
<ul>
   <li>Item 1
      <ol>
         <li>Item 1.1
            <ul>
               <li>Item 1.1.1</li>
            </ul>
         </li>
         <li>Item 1.2 </li>
      </ol>
   </li>
   <li>Item 2</li>
</ul>
```

This is all for the lists, to learn more about Markdown, especially how to add links to your document, jump to the next post - [Working with Links in Markdown][next].

[Markdown]: https://en.wikipedia.org/wiki/Markdown "Markdown - Wikipedia"
[next]: 03-Working-With-Links.md "Working with Links in Markdown"
