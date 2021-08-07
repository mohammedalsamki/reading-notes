# Video and Audio APIs

## HTML5 video and audio

The <video> and <audio> elements allow us to embed video and audio into web pages. As we showed in Video and audio content, a typical implementation looks like this:

<video controls>
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
</video>
  
  
  
  ## The HTMLMediaElement API
Part of the HTML5 spec, the HTMLMediaElement API provides features to allow you to control video and audio players programmatically — 
  for example HTMLMediaElement.play(), HTMLMediaElement.pause(), etc. This interface is available to both <audio> and <video> elements,
  as the features you'll want to implement are nearly identical. Let's go through an example, adding features as we go.
  
 ## Exploring the HTML
Open the HTML index file. You'll see a number of features; the HTML is dominated by the video player and its controls:

<div class="player">
  <video controls>
    <source src="video/sintel-short.mp4" type="video/mp4">
    <source src="video/sintel-short.webm" type="video/webm">
    <!-- fallback content here -->
  </video>
  <div class="controls">
    <button class="play" data-icon="P" aria-label="play pause toggle"></button>
    <button class="stop" data-icon="S" aria-label="stop"></button>
    <div class="timer">
      <div></div>
      <span aria-label="timer">00:00</span>
    </div>
    <button class="rwd" data-icon="B" aria-label="rewind"></button>
    <button class="fwd" data-icon="F" aria-label="fast forward"></button>
  </div>
</div>
