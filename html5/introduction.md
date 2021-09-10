# Introduction to HTML 5 

## Create an HTML5 page

    <!DOCTYPE html>
    <html>
      <head>
        <title>HTML5</title>
      </head>
      <body>
      </body>
    </html>

## Character encoding
In your document head , add a meta declaration for the character set

    <meta charset="UTF-8" />

## Specify the primary language of your web page
Add the lang attribute and appropriate value to your opening html element

    <html lang="en">

## Add JS and CSS in web page

    <link rel="stylesheet" href="styles.css" />
    <script src="scripts.js"></script>

## Document Structure

### header
Is used to contain the headline(s) for a page and/or section . It can also contain supplemental information such as logos and navigational aids.

### footer
Contains information about a page and/or section , such as who wrote it, links to related information, and copyright statements.

### nav
Contains the major navigation links for a page and, while not a requirement, is often contained by header.

### aside
Contains information that is related to the surrounding content but also exists independently, such as a sidebar or pull-quotes.

### section
Is the most generic of the new structural elements, containing content that can be grouped thematically or is related.

### article
Is used for self-contained content that could be consumed independently of the page as a whole, such as a blog entry.

### Tips
- Do not use section simply as a styling hook. Use div s and span s instead.
- Do not use section if header , footer , aside , or article is more semantically appropriate for your content.
- Do not use section unless the content has a natural heading.
- h6 as the primary heading of section
- h1 as the primary heading of article

## hgroup
hgroup hides all headings except the highest ranked from the document outline.

    <hgroup>
      <h1>HTML5, for Fun &amp; Profit</h1>
      <h2>Tips, Tricks and Resources</h2>
    </hgroup>

output will be:

`HTML5, for Fun & Profit`

## Emphasizing Text
    <p>My name is <em>Jane</em>, not John.</p>

Tip
- Browsers render both the `<i>` and `<em>` elements in italics

## Importance Tex
Browsers render both the `<b>` and `<strong>` elements in bold

## Reference Text
    <p>Your search for <mark>awesomesauce</mark> resulted in 923 entries:</p>

Browsers render the `<mark>` element with a yellow background by default

## Small Print
    <p><small>Copyright &copy; 2011 Awesomest Blog. All rights reserved.</small></p>

## Acronyms and Abbreviations

    <abbr title="Accessible Rich Internet Applications">ARIA</abbr>


## Adding Links to Block-Level Content
    <a href="http://html5funprofit.com">
      <h1>HTML5, for Fun &amp; Profit</h1>
      <img src="logo.png" alt="HTML5 for Fun and Profit" />
    </a>

## Figures and Captions
    <figure>
      <img src="chart.png" alt="Chart of increasing awesomeness" />
      <figcaption>
        The increasing amount of awesome that this blog demonstrates.
      </figcaption>
    </figure>

figure can be used to specify code examples, photos, charts, audio, and data tables, to name just a few of the options.

figcaption is optional and can reside anywhere within figure , whether before or after the figure content.

## Dates and Times

    <p>Published: <time datetime="2011-01-15">January 15, 2011</time></p>
    <p>The class starts at <time datetime="08:00">8:00 am</time>.</p>

## Publication dates
    <p>Published: <time datetime="2011-01-09" pubdate>January 9, 2011</time></p>

## Details element

Contain the full content with the details element and indicate the content area that is “focusable” with summary


    <details>
      <summary>Upcoming Topics</summary>
      <p>For the new year, we have a great line up of articles!</p>
      <ul>
        <li>Understanding the Outline Algorithm</li>
        <li>When to Use <code>hgroup</code></li>
        <li>Machine Semantics with Microdata</li>
      </ul>
    </details>


## Numbering of Your Lists

Specify one of the semantic control attributes on the `ol` or `li`. For instance, to start a numbered list at 3, include the start attribute in your `ol` and specify 3 as the value

    <ol start="3">
      <li>Apples</li>
      <li>Oranges</li>
      <li>Bananas</li>
    </ol>

## Value Attribute

    <ol>
      <li value="1">Bananas</li>
      <li value="1">Oranges</li>
      <li value="2">Apples</li>
    </ol>

## Hiding Content

    <p hidden>As a special deal for members, use discount code AWESOMESAUCE and save
    10% off all purchases from these vendors.</p>

Do not use hidden for presentational purposes and don’t rely on browsers to actually hide the content. Use it only for semantic
purposes and use CSS to control presentation.

## Making Portions of a Page Editable

Add the contenteditable attribute to the element containing the content to be edited.

    <article contenteditable>
      <h2>Stop <code>section</code> Abuse!</h2>
      <p>As the most generic of the HTML5 structural elements, <code>section</code>
      is often incorrectly used as a styling container, when <code>div</code> is
      more appropriate.</p>
    </article>

## Native Drag-and-Drop

Add the draggable attribute to the element that should be draggable

    <h2 draggable>Block-Level Links</h2>

draggable simply allows you to specify the elements that
can be dragged.

To achieve the desired drag-and-drop functionality, you need JavaScript.

