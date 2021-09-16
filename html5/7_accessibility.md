# Accessibility

“Disability” is a broad term. Major categories of disabilities that affect use of the Web include visual, hearing, cognitive, speech (especially on mobile devices), and motor disabilities.

A single category of disability may manifest in many forms. For example, visual disability includes, but is not limited to, red-green color blindness.

About 7 to 10% of all men have trouble differentiating between red and green colors.

## The Purpose of Accessibility

Web accessibility is about removing barriers that prevent people from using the Web.

In fact, one could say accessibility is at the heart of the Web in that its goal is to break down barriers of communication.

## POUR

WCAG 2.0 uses the acronym POUR to summarize the four principles of web accessibility.

POUR stands for Perceivable, Operable, Understandable, and Robust:

### Perceivable

Means that the content is available to the senses, usually sight or hearing.

That means you’ve done things like provide text alternatives for images, provide captions for audio and video, and include sufficient contrast between the text and the background.

### Operable

Ensures that people can use or interact with the website, including navigation, content, forms, and dynamic controls.

### Understandable

Means that the text is legible and the site behaves in consistent, predictable ways.

### Robust

Defines the page’s markup and coding as working in a variety of user agents and assistive technologies.

## ARIA

The W3C WAI also authored WAI-ARIA 1.0 (Accessible Rich Internet Applications).

ARIA provides a way to add semantic meaning to Ajax-like, dynamic web content and custom widgets by defining a set of roles and the states and properties of those roles.

In other words, ARIA allows you to programmatically communicate to assistive technologies what is displayed to sighted users as the page changes in response to user actions, rather than just what is present in the original page markup.

The work of ARIA specification is still being done, and while support is fairly robust and always improving, there are bugs and incomplete support in user agents to contend with.

The good thing is that implementing ARIA doesn’t have to be hard.

It’s definitely not harder than building cross-browser, custom JavaScript widgets.

## Text alternative for an image

If an image deserves a text alternative that can be summed up in one to two sentences (or about 75 words or less), set that text as the value of the alt attribute.

    <img src="next_button.jpg" alt="Go to the next page.">

## ARIA aria-labelledby

If you need to reference multiple text alternative sources for an image to make sense and all of that content is on the same web page, use the ARIA aria-labelledby or aria-describedby attributes to reference the text alternatives, as these ARIA attributes can accept multiple references.

    <h1 id="johnny1">Johnny throwing cake at his Mom while Dad ducks behind her</h1>
    <p id="johnny2">Johnny's poor Mom is smeared with cake. Well, that shirt is ruined!</p>
    <img src="johnny_1st_bd.jpg" aria-describedby="johnny1 johnny2" alt="Johnny's first birthday party">

Until user agents and assistive technologies better support figure and figcaption elements, use the aria-labelledby attribute to associate an image enclosed in the figure element with its caption.

Add the aria-labelledby attribute to the img element and add its associated value to an id attribute of the figcaption element.

    <figure>
        <img src="ceremony_photo.jpg" aria-labelledby="figcaption123">
        <figcaption id="figcaption123">
            Opening ceremony for the new library building at the state university.
        </figcaption>
    </figure>

Apply these best practices when writing the text alternatives for images:

- Include all content (text) that appears in the image.
- Consider the context of the image to help determine what is important about it.
- If it is relevant, convey the purpose or function of the image.
- Avoid including information that is available as text near the image.
- Avoid including phrases such as “image of” or “picture of.”
- Be concise.

## Null alt attribute

A null alt attribute is an alt attribute whose value contains no spaces or content.

It is not the same as omitting the alt attribute

    <img src="border_decoration.jpg" alt="">

Adding a null or empty alt attribute to an image is appropriate in the following situations:

- The image is purely decorative.
- A text alternative is available immediately adjacent to the image. However, this is not a valid suggestion if the image is also a link.
- The image is one of a group of images that form a larger picture, and one of the other images already has the text alternative for the entire picture.
- The image is not meant to be seen by users (e.g., a 1-pixel image that counts page views).

Alternative text is also not necessary when you use background-image CSS properties to add a purely decorative image to the web page instead
of using an img element.

However, if you omit the alt attribute altogether from the img element, the same assistive technologies announce that an image exists on the page and do their best to provide information about it, even if that information is only the filename.

Keep in mind when considering whether to use a null alt attribute or omit the alt attribute that there is a difference in how some assistive technologies handle them.

## Using figcaption

In HTML5, an image may be enclosed in a figure element and the figcaption element may either provide the entire text alternative or supplement the text alternative provided in the image’s alt attribute.

    <figure>
        <img src="ceremony_photo.jpg">
        <figcaption>
            Opening ceremony for the new library building at the state university.
        </figcaption>
    </figure>

## Using abbr

Use the abbr element to programmatically associate the full expansion with the abbreviation.

The abbr element is an inline element that can be used within block elements or other inline elements.

    <p>
        <abbr title="Web Content Accessibility Guidelines">WCAG</abbr> 2.0 was released as a 
        <abbr title="World Wide Web Consortium">W3C</abbr> recommendation in December 2008.
    </p>

## ARIA roles

Use banner role only once per document or web application.

    <header role="banner">

Add the complementary role to the aside element.

    <aside role="complementary">

Add the navigation role to each nav element.

    <nav role="navigation">

Add the form role to any form element, unless the form contains search functionality.

    <form role="form">

Add the search role to a site’s search form.

    <form role="search">

The contentinfo role identifies information about the page content, such as copyright  and privacy terms.

    <footer role="contentinfo">
        <p>Copyright 2011</p>
    </footer>

## Roles for web apps

Some ARIA landmark roles, such as application and main , are unique and do not map directly to specific HTML5 elements.

Add the application role to an HTML element that contains a web application instead of normal web content.

    <div role="application">
    ...
    </div>

Add the main role to an HTML element that contains the primary content of the document, such as article s, div s, etc.

    <div role="main">

## Creating More Accessible Navigation Links

    <nav role="navigation">
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Blog</a></li>
            <li><a href="#">Portfolio</a></li>
        </ul>
    </nav>

Next, add a “skip navigation” link:

    <div id="offscreen"><a href="#maincontent">Skip to the main content</a></div>
    ...
    <nav role="navigation">
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Blog</a></li>
            <li><a href="#">Portfolio</a></li>
        </ul>
    </nav>
    ...
    <article id="maincontent" role="main">
    ...

“skip navigation” link purpose is to provide keyboard and assistive technology users a way to go directly to the main content on the page.

Avoid using display:none for hiding skip links as screen readers might ignore the links altogether.

Instead of hiding the skip link, consider using CSS to stylize the link to match your design. Or, better yet, have your skip link become visible with keyboard focus.
