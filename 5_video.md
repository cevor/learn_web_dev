# Native Video

Similar in nature to audio , the video element shares many of the same attributes, has a similar syntax, and can be styled and manipulated with CSS and JavaScript.

## Play native video

    <video src="video.ogv"></video>
    <video src="video.ogv" controls></video>

Native player controls look different in different browsers. Style your own controls with JavaScript and CSS.

## Preloading

The preload attribute allows you to suggest to the browser whether and how it should download the video.

    <video src="video.ogv" controls preload></controls>

You can skip the attribute and let the browser decide, or give browsers a “hint” with specific values (refer back to Recipe 4.1, for details)

* preload="auto" or, simply, preload
* preload="metadata"
* preload="none"

## Fallback content

    <video src="video.ogv" controls>
        Your device does not support HTML5 video. <a href="video.ogg">Download the Learning to Love HTML5 introductory video</a>.
    </video>

Fallback content is content that displays on browsers that don’t support video . It does two things: informs the user that her browser doesn’t support HTML5 video and provides a link to download the video.

## Video codecs

.mp4

The container format for the proprietary H.264 codec that encodes video for a full range of devices, including high definition.

.ogv

The free, open source container format for the open source Theora codec. Results in lower quality than H.264.

.webm

Another open source container format, which is used by the new, royalty-free VP8 codec from Google.

## Multi-Browser Video Support

Use the source child element of video to specify each of your video formats

    <video controls>
        <source src="video.mp4" />
        <source src="video.ogv" />
        Your device does not support HTML5 video.
    </video>

## MIME type for video

Beyond specifying the video files themselves, it is good practice to also specify the MIME type for your video files.

    <source src="video.mp4" type="video/mp4" />
    <source src="video.ogv" type="video/ogg" />

Since file formats are simply containers for different codecs, you should also specify the compression used.

    <source src="video.ogv" type="video/ogg; codecs='theora'">

examples of MIME types with codecs.

    type="video/ogg; codecs='theora, vorbis'"
    type="video/mp4; codecs='avc1.42E01E'"
    type="video/webm; codecs='vp8, vorbis'"

Unfortunately, even if you declare your MIME types with the proper codec in your HTML, there can also be challenges related to the MIME types supported by your server. If your server isn’t configured to support the MIME types your video uses, there will be playback issues.

## Video Dimensions

Add the width and height attributes, and their corresponding values, to video.

    <video controls width="640" height="360">
        <source src="video.mp4" type="video/mp4" />
        <source src="video.ogv" type="video/ogg" />
        Your device does not support HTML5 video.
    </video>

## Placeholder Image Before Video Plays

Add the poster attribute with the placeholder image file path as the value.

    <video controls width="640" height="360" poster="video_still.png">
        <source src="video.mp4" type="video/mp4" />
        <source src="video.ogv" type="video/ogg" />
        Your device does not support HTML5 video.
    </video>

## Video Loop

Add the loop Boolean attribute to video.

    <video controls width="640" height="360" loop>
        <source src="video.mp4" type="video/mp4" />
        <source src="video.ogv" type="video/ogg" />
        Your device does not support HTML5 video.
    </video>

## Video Autoplay

autoplay starts playing the video as soon as the page loads.
