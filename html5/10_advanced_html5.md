# Advanced HTML5 JavaScript

## Local Storage

HTML5 introduced two new APIs for in-browser persistent data storage:

- sessionStor age which stores data only for the lifetime of the browser instance/session.

- local Storage which stores data persistently “forever” (which in this case means, “until either the code or the user clears it out”).

Both interfaces have the same API. The difference between the two is basically how long the browser persists the data.

The APIs for sessionStorage and localStorage are as follows.

getItem(key)

- Returns an item of data from the storage container, referenced by its key

setItem(key, item)

- Adds an item of data to the storage container, referenced by its key

key(index)

- Returns the key for an item of data at the numerical index specified

removeItem(key)

- Removes an item from the storage container, referenced by its key

clear()

- Clears out all data in the current storage container

length

- Identifies how many items of data are in the storage container

## Caching

HTML5 defines a special application cache, commonly called the appcache , that allows you to instruct the browser to cache certain resources—images, CSS, JS, etc.

In a way that makes them available to the application even if the user’s browser is offline and not connected to the public Internet.

To utilize appcache in your application, first you need to create a manifest file listing the resources you want in the appcache.

This file might look like:

    CACHE MANIFEST

    CACHE:
    index.html
    help.html
    style/default.css
    images/logo.png
    images/backgound.png

Once you have the manifest file—in this example we’ve named it cache.manifest—tell the browser about the file by adding a property to the html element in your markup,like so.

    <html manifest="cache.manifest">

The cache manifest file must be served with the MIME type text/cache-manifest.

## Web Workers

Web Workers create a special environment for JavaScript code to run in that occurs in a separate thread from the main UI of your page.

This means that your page’s UI won’t be locked up if you have particularly long-running JavaScript code.

## Web Sockets

Most browsers now have the native ability to establish a bidirectional socket connection between themselves and the server, using the WebSocket API.

This means that both sides (browser and server) can send and receive data.

The server URL in our example uses the “ws://” protocol, as opposed to the more common “http://” you’re familiar with.

This signals the special protocol that Web Sockets use between client and server.

The WebSocket object instance has, similar to XHR, a readyState property that lets you examine the state of the connection.

It can have the following constant values.

{worker}.CONNECTING (numeric value 0)

- Connection has not yet been established

{worker}.OPEN (numeric value 1)

- Connection is open and communication is possible

{worker}.CLOSING (numeric value 2)

- Connection is being closed

{worker}.CLOSED (numeric value 3)

- Connection is closed (or was never opened successfully)

The events that a WebSocket object instance fires are:

open

- Called when the connection has been opened

message

- Called when a message has been received from the server

error

- Called when an error occurs with the socket (sending or receiving)

close

- Called when the connection is closed

## History

HTML5 brings us several important enhancements to the browser’s window.history object, commonly referred to as the History API.

## Local Files

HTML5 gives us the FileReader API, which lets us take a reference to a local file and read its contents directly into the web page.
