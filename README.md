Web Audio boilerplate
========================

A couple of helpers necessary for cross-browser web audio projects :

1. Testing audio format support
2. Unmuting `AudioContext` on iOS

**note** : in addition of this library, I recommend using @cwilso's [AudioContext-MonkeyPatch](https://github.com/cwilso/AudioContext-MonkeyPatch) for normalizing Web Audio API across browsers (prefix and method names). For convenience, it is already bound with the built version of the library.


Download
----------

- From npm : `npm install --save web-audio-boilerplate`
- Built version (bundled with **AudioContext-MonkeyPatch**) : [here](https://github.com/sebpiq/web-audio-boilerplate/tree/master/dist/)


API
----

### webAudioBoilerplate.getSupportedFormats(audioContext, done)

Test what audio formats are supported in the current browser. Calls `done(err, results)` where `result` is an object :

```javascript
{wav: <trueOrFalse>, ogg: <trueOrFalse>, mp3: <trueOrFalse>}
```

### webAudioBoilerplate.getAudioContextOnClick(elem, handler)

[iOS](https://developer.apple.com/library/content/documentation/AudioVideo/Conceptual/Using_HTML5_Audio_Video/PlayingandSynthesizingSounds/PlayingandSynthesizingSounds.html) requires a user action in order for your `AudioContext` to make any sound. When the HTML `elem` is clicked or tapped, `handler(err, audioContext)` is called with `audioContext` an unmuted instance of `AudioContext`. This function is only really necessary on iOS, but you can use it safely in all browsers.


Demo
-----

There is a simple demo [here](https://github.com/sebpiq/web-audio-boilerplate/tree/master/demo.html). You can see the demo in action [here](sebpiq.github.io/web-audio-boilerplate/demo.html). 
