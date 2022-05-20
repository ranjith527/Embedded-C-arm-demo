# Jump To

- Block Elements
  - Paragraphs and New Lines
  - Headers
  - Blockquotes
  - Lists
  - Code Blocks
  - Horizontal Rule
- Span Elements
  - Links
  - Emphasis
  - Inline Code
  - Images
- Misc.
  - Escaping
  - Automatic Linking
  - Linking Emails
  
As we all Know, HTML has been around a *long* time and is used to build every website on the internet, but it's really not that easy to write. Sure, for many developers it might be easy, but it definitely isn't convenient thanks to the verbose syntax. If you're a blogger, there really isn't any reason to have to write HTML as you probably only need simple formatting like emphasis and links.

This is where [Markdown](https://en.wikipedia.org/wiki/Markdown) comes in to play. In this article I'll explain what it is, and more importantly, I'll show you some Markdown examples that you can use on your own.

## What is Markdown

Markdown is a very lightweight markup language that lets you create rich text (meaning text that has emphasis, headers,etc) in any plain text editor. Makrdown, like HTML, allows you to specify text formatting, but it is far less expressive than HTML, which is perfectly fine since it is only meant to format text and not create full web pages.

The resulting Markdown you write is then fed in to a converter that replaces the Markdown syntax with HTML, which can then be displayed on a web page. In addition to the Markdown syntax, you can also write plain HTML as well, so if you have some more complicated structure you want to add in-line with your text, you'll still have the ability to do so.

[John Gruber](https://daringfireball.net/) created the Markdown syntax with Aaron Swartx in 2004 as a way "to write using an easy-to-read, easy-to-write plain text format, and optionally convert it to structurally valid XHTML (or HTML)".

He Seems to have achieved his goal, but there have been problems with [standardization](https://en.wikipedia.org/wiki/Markdown#Standardization) since there isn't a clearly defined standard other than the initial documentation by Gruber. Because of this, there has been some fragmentation issues with converters, although many of them agree on the majority of the syntax, there are still quite a few [different flavors](https://github.com/commonmark/commonmark-spec/wiki/Markdown-Flavors)  out there. Throughout this article we'll stick as closely to the original implementation as possible, and note when I'm describing a feature not fully supported.

## Markdown Syntax examples

The examples will be broken up in to two different sections, block elements and span elements. Block elements are those that take up their own line, like paragraphs, code, or headers.

The span elements can be used inline, meaning they can be used within a paragraph and don't need to be on a line of their own.

## Block elements

### Paragraphs and New Lines

Creating paragraphs and new lines (or line breaks) are similar, but have subtle differences. A new paragraph element, ```<p>...</p>```is created any time there is a blank line between two lines of text. Like this:

**Markdown:**

``` text
Hello, this is a paragraph.
This is a new Paragraph!
```

**HTML:**

``` bash
<p>Hello, this is a paragraph. </p>
<p>This is a new paragraph! </p>
```

On the other hand, a line break, ``` <br /> ``` is inserted when there is a new line and no blank line separating the text, like this:

**Markdown:**

``` text
The paragraph starts here...
...and doesn't end until here.
```

**HTML:**

``` bash
<p>The paragraph starts here...<br/>
...and doesn't end until here.</p>
```

## **Headers**

There are two ways to create headers, [Setext](https://en.wikipedia.org/wiki/Setext) and [atx](https://en.wikipedia.org/wiki/Aaron_Swartz#atx). The method you choose will be based on personal preference and the size of header you need.

For declaring H1 or H2 headers in the Setext format, you can use an underlines:

``` text
An H1 Header
============

An H2 Header
------------
```

Keep in mind that the number of "=" or "-" you use doesn't matter. Even placing just one of these characters under the text will tell Markdown to create the header.

As for the atx method, all you need to do is place pound signs (```#```) before the text. The number of pound signs you use determines the header tag used (up to ```h6```).

``` text
# An H1 Header
## An H2 Header
### An H3 Header
#### An H4 Header
```

You can optionally add the pound sign after the header text, but it would be purely for aesthetic reasons. You don't even need to match the number of symbols in the prefix:

``` text
# An H1 Header #
## n H2 Header ##
### n H3 Header ###
```

## **Blockquotes**

A blockquote is a an element used for showing quotes. Adding these blockquotes in Markdown is similar to how you do it in many email clients. Like many other elements, there are a few options for how to create them.

The first option is to prefix each line of the quote with a greater-than (```>```) character.

**Markdown:**

> Of all the things I've Lost
> I miss my mind the most. - *Mark Tawin*

**HTML:**

``` html
<blockquote>
    <p>Of all the things I've lost I miss my mind the most. - Mark Twain
</blockquote>
```

This can get a bit tedious for long blocks of continuous text, so instead you can just use a single > before the first line of each paragraph, and the rest will follow:

**Markdown:**
> Measuring programming progress by lines of code is like measuring aircraft building progress by weight. — Bill Gates

Other Markdown elements can be placed in blockquotes as well, so if the quote requires formatting, like emphasis, you can add it. Just make sure the line starts with the ```>``` symbol to get this to work.

## **Lists**

Both types of HTML lists are supported in Markdown - unordered lists (```<ul>```) and ordered lists (```<ol>```).

For unordered lists, there are a couple different characters that can be used to declare a list item. Here are a few examples, all of which produce the same unordered list output:

**Markdown:**

``` bash
* Item 1
* Item 2
* Item 3

+ Item 1
+ Item 2
+ Item 3

- Item 1
- Item 2
- Item 3
```

**HTML:**

``` bash
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

You can even declare nested lists just by indenting the item.

**Markdown:**

``` bash
- Item 
    - Sub-item 1
    - Sub-item 2
- Item 2
    - Sub-item 1
```

**HTML:**

``` bash
<ul>
  <li>Item 1
    <ul>
      <li>Sub-item 1</li>
      <li>Sub-item 2</li>
    </ul>
  </li>
  <li>Item 2
    <ul>
      <li>Sub-item 1</li>
    </ul>
  </li>
</ul>
```

As for ordered lists, you declare them in a similar fashion, with the biggest difference being that you use numbers instead of the ```*```, ```+```, or ```-``` characters.

**Markdown:**

``` bash
1. Item 1
2. Item 2
3. Item 3
```

With ordered lists, it doesn't even matter what numbers are prefixing the items. Even if you had random numbers like this:

**Markdown:**

``` bash
45. Item 1
0. Item 2
910. Item 3
```

**HTML:**

``` bash
<ol>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>
```

The same rules also apply to ordered lists for adding sub-items. All you have to do is indent the item and a sub-list will be started.

The same rules also apply to ordered lists for adding sub-items. All you have to do is indent the item and a sub-list will be started.

``` bash
* Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean fringilla velit sit amet lectus tincidunt, quis suscipit tortor maximus. Vestibulum facilisis sit amet tortor sed vestibulum.

  Sed nec egestas leo. Nam tristique tincidunt venenatis. Vestibulum vel justo tincidunt, aliquet sapien vitae, vestibulum ex.

  Donec commodo, nunc in posuere condimentum, diam est gravida ex, quis varius nisi neque et nunc.
* Nulla facilisi. Mauris eleifend felis a purus pretium egestas
```

**HTML:**

``` bash
<ul>
  <li><p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean fringilla velit sit amet lectus tincidunt, quis suscipit tortor maximus. Vestibulum facilisis sit amet tortor sed vestibulum.</p>

  <p>Sed nec egestas leo. Nam tristique tincidunt venenatis. Vestibulum vel justo tincidunt, aliquet sapien vitae, vestibulum ex.</p>

  <p>Donec commodo, nunc in posuere condimentum, diam est gravida ex, quis varius nisi neque et nunc.</p>
  <li><p>Nulla facilisi. Mauris eleifend felis a purus pretium egestas</p>
</ul>
```

## **Code Blocks**

To show code within your content you'd usually use the ```pre``` and ```code``` HTML tags. In Markdown, to add a code block you just need to indent each line by either 4 spaces or a single tab. However, this isn't like a paragraph where you only need to indent the first line and the rest will follow. With code blocks you actually need to indent each line to get it to be included in the block. If there are any non-indented lines between code, then they'll break it up in to separate blocks.

``` bash
Check out this code:

    def fibonacci(number):
        if number <= 1:
            return number
        else:
            return fibonacci(number - 1) + fibonacci(number - 2)

And use the function like this:

    fib_number = fibonacci(8)
    print 'The 8th Fibonacci number is:', fib_number

Wow, that was amazing...
```

In some Markdown converters, you can alternatively use three backticks (`) to create code blocks. Personally, I prefer this method more than indenting since it's easier to read and write. Additionally, if you have a syntax highlighter you can declare which language your code is in so it knows how to highlight the code.

```python
name = 'Scoot'
print 'Hi my name is' + name
```

You don't need to include 'python' in there, but it helps the syntax highlighter be more accurate. It does this by adding the declared language as a class. So the above would result in the following:

**HTML:**

``` bash
<pre><code class="language-python">
name = 'Scott'
print 'Hi my name is ' + name
</code></pre>
```

## Horizontal Rule

To break up sections in your text, you can add horizontal rules (```<hr />```), which are just long lines spanning the length of the block that it's in. To add one with Markdown, just add three or more ```*``` or ```-```.

``` text
***

or

---
```

You can also place spaces between the characters if you want:

``` bash
* * * * * * *

- - - - - - - - - - 
```

## Span Elements

### Links

There are quite a few different ways to create links, each of which depends on the meta-data you need, organization, and personal preference. The first and simplest way to create a link is with this format: ```[ANCHOR-TEXT](LINK)```. An example might be:

**Markdown:**

``` text
 [Stack Abuse](http://stackabuse.com)
```

**HTML:**

``` bash
<a href="http://stackabuse.com">Stack Abuse</a>
```

You can also add an optional title attribute to your links:

``` bash
[Stack Abuse](http://stackabuse.com "Stack Abuse Title")
```

If you prefer, instead you can use reference-style linking where the actual link is separate from where it is referenced. This reference can be anywhere in the text, as long as it is on a line of its own.

``` bash
Here's a link to [Stack Abuse][SA], you guys.

[SA]: https://stackabuse.com "Stack Abuse Link Title"
```

The anchor text is optional as well, in which case the ID would be used as the anchor text instead. The ID portion can be a number or text, even with spaces.

### Emphasis 

One of the most used elements in HTML is emphasis on text, like bold or italics. Either of these elements can be created with an underscore (```_```), or asterisk (```*```).

To add ```<em>``` tags, use a single _ or * on each side of the text. And for ```<strong>``` tags, use two of those characters on each side. Here area few examples:

**Markdown:**

``` text
_This is emphasized text!_

__This is strong text!__

*This is emphasized text!*

**This is strong text!**
```

**HTML:**

``` html
HTML:

<em>This is emphasized text!</em>

<strong>This is strong text!</strong>

<em>This is emphasized text!</em>

<strong>This is strong text!</strong>
```

### Inline Code

Inline code can be added via backticks ``` ` ``` within a paragraph, so it doesn't need to be on its own line. This will just add ``` code ``` tags around the text.

**Markdown:**

``` text
In JavaScript, use `console.log()` to print to the console.
```

**HTML:**

``` html
<p>In JavaScript, use <code>console.log()</code> to print to the console.</p>
```

If you ever need to use literal backticks within your span of code, you should use two backticks on both the opening and closing delimiters. This way you an do things like this:

**Markdown:**

``` TEXT
A backtick `` ` `` is used for code blocks.
```

**HTML:**

``` HTML
<p>A backtick <code>`</code> is used for code blocks.</p>
```

### Images

Linking to images is a lot like adding URL links. The small difference is that you have to prefix it with an exclamation mark (``` ! ```).

**Markdown:**

``` Markdown
![My Alt Text](/path/to/my/pic.jpg "My Optional Title Text")
```

**HTML:**

``` html
<img alt="My Alt Text" title="My Optional Title Text" src="/path/to/my/pic.jpg">
```

And same with URL links, you can also use references.

``` markdown
![My Alt Text][id]

[id]: /path/to/my/pic.jpg "My Optional Title Text"
```

## Misc.

### Escaping

If you ever need to use reserved characters like ```*```, ```#```, or ```-```, you'll need to escape it with a backslash. Although,you only need to escape if the reserved character being used is in the format of Markdown syntax.

**Markdown:**

``` markdown
OMG \_this\_ has better not have emphasis...
```

**HTML:**

``` html
<p>OMG _this_ had better not have emphasis...</p>
```

The following characters can be escaped with a backslash:

- \\ (backslash)
- \` (backtick)
- \* (asterisk)
- \_ (underscore)
- \{} (curly brackets)
- \[] (square brackets)
- \() (parentheses)
- \# (hash marks)
- \+ (plus signs)
- \- (hyphens)
- \. (dot)
- \! (exclamation marks)

### Automatic linking

There is a shortened form of linking available to you, but at the cost of anchor text. If you want to add a link and just have the URL as the anchor text then you can use this:

**Markdown:**

``` markdown
<https://stackabuse.com>
```

**HTML:**

``` html
<a href="http://stackabuse.com">http://stackabuse.com</a>
```

### Linking Emails

*Note:* Although it is declared in the Markdown specification, this feature is not supported by all converters.

You can also use the short-hand linking style to link to email addresses with 'mailto'. As a convenience, the converter will perform a hex entity-encoding on the email address, which still shows up as ASCII characters to the reader. This will help prevent many email harvesting bots from reading the email, but not all.

**Markdown:**

``` markdown
<address@example.com>
```

**HTML:**

``` html
<a href="&#x6D;&#x61;i&#x6C;&#x74;&#x6F;:&#x61;&#x64;&#x64;&#x72;&#x65;&#115;&#115;&#64;&#101;&#120;&#x61;&#109;&#x70;&#x6C;e&#x2E;&#99;&#111;&#109;">&#x61;&#x64;&#x64;&#x72;&#x65;&#115;&#115;&#64;&#101;&#120;&#x61;&#109;&#x70;&#x6C;e&#x2E;&#99;&#111;&#109;</a>
```

## Conclusion

Don't forget, Markdown also allows you to insert plain HTML as well. So if the syntax doesn't allow you to specify the attributes you want, like ```height``` and ```width``` On an image, then you can just use HTML instead. This is where a lot of the power comes from - in the form of flexibility.

Note that this is not a definitive guide to the Markdown syntax. If you want a more complete and through resource, you should either consult the specific converter you're using or John Gruber's guide at [Daring Fireball](https://daringfireball.net/projects/markdown/syntax).
