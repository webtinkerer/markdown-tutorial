# Adding Images
When you know how to [add hyperlinks][previous] to your document, it won't be too difficult to add images, especially in case syntax is pretty the same with some tiny differences. 

## Images
Here we also have two styles: [inline links](#inline-links) and [reference links](#reference-links). Let's look at both.

<h3 id="inline-links">Inline Links</h3>
To add a new image to the document you will need to start with exclamation mark `!` followed by a pair of square brackets `[]` for `alt` text and pair of parenthesis `()` for image URL (can be either full or relative) and then by an optional title for the image enclosed in quotes:
```language-markdown
![This is an alt text](https://www.google.com/images/srpr/logo11w.png) "Here is a title for the image"
```

Output:
```language-markup
<img src="https://www.google.com/images/srpr/logo11w.png" 
alt="This is an alt text" title="Here is a title for the image" />
```

<div class="note>Keep in mind that <code>alt</code> text is optional, but you will still need to enter <code>[]</code>. Just leave them empty if you don't want to specify <code>alt</code> text.</div>

Unfortunately, [Markdown][] has one limitation - there is no syntax for specifying the dimensions of the image.
 
<h3 id="reference-links">Reference Links</h3>
Reference link solves the same [issue](/ultimate-guide-markdown-working-links#reference-links) as with hyperlinks - prevents image URL duplication across one document and provides easy way to update such URL. Here is an example:
```language-markdown
![This is an alt text][key]
[key]: https://www.google.com/images/srpr/logo11w.png "Here is a title for the image"
```
Output:
```language-markup
<img src="https://www.google.com/images/srpr/logo11w.png" 
alt="This is an alt text" title="Here is a title for the image" />
```

### Image as a hyperlink
You can also specify the whole image as a hyperlink. It is very useful when you don't want to add the large image to your document. In this case, you can add the same image of a small size and mark it as a hyperlink to the full-sized image.
```language-markdown
[![][small]][large]
[small]: https://www.google.com/images/srpr/logo1w.png 
[large]: https://www.google.com/images/srpr/logo11w.png
```
Output:
```language-markup
<a href="https://www.google.com/images/srpr/logo11w.png">
<img src="https://www.google.com/images/srpr/logo1w.png" alt="" />
</a>
```
And this is how it will look like in the browser:
<a style="border: none;" href="https://www.google.com/images/srpr/logo11w.png">
<img src="https://www.google.com/images/srpr/logo1w.png" alt="" />
</a>

At the current moment, we have learned all major elements of Markdown, your toolbox is filled with the knowledge of all necessary elements for your day-to-day documents. If you still feel that need more power, some advanced techniques, jump to the next post - [Advanced Formatting with Markdown][next].

[Markdown]: https://en.wikipedia.org/wiki/Markdown "Markdown - Wikipedia"
[previous]: 03-Working-With-Links.md "Working With Links in Markdown"
[next]: 05-Advanced-Formatting.md "Advanced Formatting"
