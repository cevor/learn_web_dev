# Microdata and Custom Data

HTML5 introduces microdata, which gives us a new syntax for marking up these additional structured semantics.

In addition, HTML5 allows for custom data attributes, which further give web professionals a standards-compliant way for embedding additional data in their markup.

The markup aspects of these features work in browsers today, but the associated DOM APIs to interact with them are not yet (microdata) or widely (custom data) supported by user agents. Still, given that it is possible to write JavaScript to interact with the additional data, there’s little reason not to use them.

## When to Use Microdata Versus Custom Data

Similar to microformats and RDFa, microdata is used to mark up structured data. It introduces new attributes that can be applied to any element in order to identify scoped name/value pairs. As with microformats, shared vocabularies are emerging to standardize how data is marked up, so microdata can be used to share data across websites and applications.

Custom data attributes are just that: custom. You, the programmer, create attributes using the data- prefix and assign them values.

The name/value pairs are related to the displayed content, but are not themselves displayed.

Because you define the attributes according to the needs of your website or application, these are not to be used to exchange data with another site, nor do public search engines consume them.

Google, Microsoft, and Yahoo!, meanwhile, are promoting microdata and have teamed up to create Schema.org, a shared vocabulary of data structures that allows their search engines to extract more meaning from your data.

## Adding Microdata to Markup

Use the itemscope and itemprop attributes, along with descriptive property names, to label your content.

    <p itemscope>
        <span itemprop="inventor">Tim Berners-Lee</span> created the
        <span itemprop="invention">World Wide Web</span>.
    </p>

The itemscope attribute is used to identify the scope of the microdata item, an item being a set of name/value pairs.

The itemprop attribute values define the property names and their associated values.

## Using Microdata and Schema.org

In addition to using the itemscope and itemprop attributes, specify an itemtype and apply the appropriate property names from the Schema.org vocabulary.

    <section itemscope itemtype="http://schema.org/Person">
        <h1 itemprop="name">Tim Berners-Lee</h1>
        <img itemprop="image" src="http://www.w3.org/Press/Stock/Berners-Lee/2001-europaeum-eighth.jpg">
        <p>
            <span itemprop="jobTitle">Director</span>,
            <span itemprop="affiliation" itemscope itemtype="http://schema.org/Organization" itemprop="name">World Wide Web Consortium</span>
        </p>
        <p itemprop="address" itemscope itemtype="http://schema.org/PostalAddress">
            <span itemprop="addressLocality">Cambridge</span>,
            <span itemprop="addressRegion">MA</span>
        </p>
        <a itemprop="url" href="http://www.w3.org/People/Berners-Lee/">Website at W3C</a>
    </section>

## Adding Custom Data to Markup

Define your own data- attributes to name and store the information.

    <h1>My Volkswagens</h1>
    <ul>
        <li data-year="1996"
        <li data-year="1993"
        <li data-year="2008"
        <li data-year="2003"
    </ul>

If your custom data attributes have additional hyphens in the name, you need to convert them to camel case names when using the dataset API—
for example, data-foo-bar would be referred to as dataset.fooBar .

But if you’re using getAttribute() or setAttribute() , you will still reference it as data-foo-bar.

You can access custom data via javascript and execute some logic based on the data.
