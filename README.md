# JWPlayer-Chapters-API

Note: This is a early experiment after an hour of coding. It's really hacky and has only been tested in Safari and Chrome.

Currently the only way to add chapter markers to the JW Player is via a WebVTT file.
https://support.jwplayer.com/customer/portal/articles/1407454-adding-chapter-markers

This JS Method allows you to add chapter markers via JavaScript without the need of a WebVTT file.
It uses BlobURL to create a WEBVTT file which is then used by the JW Player.

##Usage

- Include the jwchapters.js file or contents of file into your page.
- Call chaptersBlob() with an array containing the start of the chapters expressed in seconds.


##Example

```javascript
<script type="text/javascript" src="jwchapters.js">
<script type="text/javascript">

var playerInstance = jwplayer("player");
var qs = window.location.search;
playerInstance.setup({
    file: 'mymovie.mp4',
	tracks: [{
	    file:chaptersBlob([10,300,667,800]),
	    kind:'chapters'
	  }]
});


</script>
```

