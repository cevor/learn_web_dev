# Native Audio

## Play native audio

Add the audio element, with the src attribute referencing the location of your audio file and fallback content for older browsers.

    <audio src="audio.ogg" controls>
        Download <a href="audio.ogg">episode 42 of Learning to Love HTML5</a>
    </audio>

## Audio codecs

.aac

Lossy compression scheme developed as an improvement over MP3, with similar bit rates but better sound quality

.mp3

Patented yet popular format that uses lossy compression to achieve file sizes one-tenth of noncompressed

.ogg

Open source alternative to .mp3 that also uses a lossy compression format

.wav

Proprietary format for audio that does not utilize any compression

.webm

Google’s open, royalty-free media format, which relies on the Vorbis audio codec for compression

## Integrating multiple sources

When using the source element in audio , the src attribute is dropped.

    <audio controls>
        <source src="audio.ogg">
        <source src="audio.mp3">
        Download <a href="audio.ogg">episode 42 of Learning to Love HTML5</a>
    </audio>

## Preloading the audio

The preload attribute allows you to hint to the browser when it should begin buffering the audio.

    <audio controls preload>

You can simply specify preload and leave it to the browser to decide the appropriate action, or you can choose from three defined preload values.

preload="auto"

Is the same as a Boolean preload , and suggests that the browser should begin downloading the file but leaves the ultimate action up to the browser. So, if it is a mobile situation or a slow connection, the browser can decide not to preload in order to save bandwidth.

preload="metadata"

Hints that the browser shouldn’t buffer the audio itself until the user activates the controls, but that metadata like duration and tracks should be preloaded.

preload="none"

Suggests that the audio shouldn’t be downloaded until the user activates the controls.

## audio attributes

autoplay

Tells the browser to start playing the audio as soon as the page loads.

loop

Another self-descriptive attribute, loop tells the browser to loop the audio when playing forward.

    <audio controls loop>
