## Sample-polymer

An experiment with polymer elements. The goal is to have a `audio-pad` element
with much of the same functionality from my [simple-sampler](https://github.com/meandavejustice/simple-sampler) project.

## Usage
To use the `audio-pad` element you will need to `bower install --save sampler-polymer platform` and include it in your html page.
```html
    <script type="text/javascript" src="../bower_components/platform/platform.js"></script>
    <link rel="import" href="bower_components/sample-polymer/audio-pad.html" />
</head>
<body>
    <div class="container">
        <audio-pad></audio-pad>
    </div>
```

Then you will need to pass the element an [audio context](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext) and a url for the sample. It's a good
idea to listen for the `polymer-ready` event before trying to apply these attributes.

``` javascript
window.addEventListener('polymer-ready', function(evt) {
  var pad = document.querySelector('audio-pad');
  var audioContext = generateAudioContext();
  pad.audioContext = audioContext;
  pad.url = 'path/to/your/sample.wav';
  // play the sound
  pad.play();
}

```
An event listener is already bound to click for each `<audio-pad>` element.

## Contributing
Take a look at the [issues](https://github.com/meandavejustice/sample-polymer/issues)
to run locally:
* `bower install`
* `python -m SimpleHTTPServer`
* visit [http://localhost:8000/example/index.html](http://localhost:8180/example/index.html)