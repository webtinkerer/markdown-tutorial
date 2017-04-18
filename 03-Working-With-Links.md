# Working With Links
Last time we have learned how to create different [lists][previous] in Markdown and combine them with other elements - [headings][], [paragraphs][], etc. Now it is time to take a look at hyperlinks.

## Links
As you probably know tag `<a>` allows to create a hyperlink to another website within your document. [Markdown][] supports not only this capability too, but also provides three different styles to add such hyperlinks:

* [inline links](#inline-links)
* [reference links](#reference-links)
* [implicit links](#implicit-links)

Let's exam all of them.

<h3 id="inline-links">Inline Links</h3>
To create an inline link, wrap the link text in the square brackets `[]` and the link URL (can be either full or relative) in the parenthesis `()` and enter all this together consecutively:
```markdown
[Google](google.com)
```
Output:
```html
<a href="google.com">Google</a>
```

You can also specify `title` for your link by adding the quoted text within parenthesis `()` after the link itself separated by a space:
```markdown
[Google](google.com "Link to Google website")
```
Output:
```html
<a href="google.com" title="Link to Google website">Google</a>
```

You can add any supported text formatting syntax to the link text. There is no restriction for this, just add extra key elements within the square brackets `[]`:
```markdown
[G**oo**gle](google.com "Link to Google website")
```
Output:
```html
<a href="google.com" title="Link to Google website">G<strong>oo</strong>gle</a>
```

You can specify links not only within the different paragraphs but also add it to a heading element or even make the entire header be a link to another website:
```markdown
#### [Google](google.com "Link to Google website")
###### Add here is a link to [Amazon](amazon.com)
```
Output:
```html
<h4>
  <a href="google.com" title="Link to Google website">Google</a>
</h4>
<h6>Add here is a link to <a href="amazon.com">Amazon</a></h6>
```

But sometimes you need to reference the same website several times in one document. By using inline links, you will need to specify referenced website URL in each of such hyperlinks. If there are only 1-3 duplicated links, it is probably not a big deal. But let's consider that you have 10-20 same links, it will be a lot of duplication in the same document. Or consider another scenario - URL for the specified website is changed from time to time, and you need to update it very often, without tedious text search. In all such cases, usage of inline link won't be the best practice. And here reference link comes to the stage.

<h3 id="reference-links">Reference Links</h3>
This style allows you to associate the link text with some name that is enclosed in the square brackets `[]` and used in place of link URL. To make it works you also need to define this name somewhere in the document, earlier or later (generally in the footer of the document). 

Here are the rules to define a reference link:

- the same name used previously within square brackets `[]`;
- followed by a colon `:`;
- followed by at least one space;
- followed by the URL for the link.

Here is a simple example:
```markdown
[Google][link]

Some other text.

[link]: www.google.com
```
Output:
```html
<p><a href="www.google.com">Google</a></p>
<p>Some other text.</p>
```

<div class="note">Names themselves may consist of letters, numbers, spaces, or even punctuation marks. They are not case sensitive.</div>

Using reference link style you can also specify `title` for the link, but this time put it within name definition, just after website URL separated by a space:
```markdown
[Google][link]
[link]: www.google.com "Link to Google"
```
Output:
```html
<a href="www.google.com" title="Link to Google">Google</a>
```

<h3 id="implicit-links">Implicit Links</h3>
Implicit links are similar to reference links, with one exception - they just allow you to omit the name of the link. In this case, the link text itself is used as the name of the link. To create an implicit link, just use an empty set of square brackets for link name:
```markdown
[Google][]
[Google]: http://google.com/
```
Output:
```html
<a href="http://google.com/">Google</a>
```

That is it for today. Next time we will learn how to [add images to the document][next].

[Markdown]: https://en.wikipedia.org/wiki/Markdown "Markdown - Wikipedia"
[previous]: 02-Adding-Lists.md "Adding Lists"
[next]: 04-Adding-Images.md "Adding Images"
[headings]: 01-Styling-Text.md#headings "Adding Headings"
[paragraphs]: 01-Styling-Text.md#paragraphs "Adding Paragraphs"
