# Progressive Markup and Techniques

## Mark up content correctly

Apply markup in a semantic manner.

Semantic markup is markup that describes the content it contains, rather than what the content should look like. This means coding paragraphs with the p element, titles with heading elements, and so on.

The point is to use the element that best describes the content.

## Syntax coding style to use

Best practices include the following suggestions:

- Code your tag names in lowercase.
- Enclose all attribute values in quotes.
- Close all elements with content.

## Browser supports a feature of HTML5

use <http://caniuse.com>

## HTML5 for non supported browser

Declare the HTML5 element that we’ve used on the page .i.e header as DOM elements.

    <script>
        document.createElement("header");
    </script>

To make the elements behave as block level elements, set the new
HTML5 elements to display:block in your style sheet.

## Detects which features are supported

use <http://www.modernizr.com>
