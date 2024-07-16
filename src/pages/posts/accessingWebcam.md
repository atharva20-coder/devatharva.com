---
title: Integrate Webcam 🤳 using JavaScript
slug: integrate-webcam-using-javaScript
date: 2021-7-21
author: Atharva Joshi
read_time: 4
tags: [HTML, CSS]
order: 3
hero: https://atharvacodes.netlify.app/static/a41843444900a315c63641d3b2e09d20/00d43/js.png
draft: false
emoji: "🤳"
---

**Hello Geeks 👋,** In this blog we will learn JavaScript to easily integrate your webcam into a web page.

### Integrate Webcam using JavaScript step by step

First, we need to create two files **index.html** and **style.css** then we need to do code for it.

First, we need to create an **HTML DOM** structure using the following code snippet.

- To integrate webcam into webpage we will use HTML `<video>` tag.

```html
<video id="video" width="100%" height="100%" autoplay></video>
```

# Step:1 Integrate Webcam

**Add below code inside index.html**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>How to Integrate Webcam using JavaScript</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" href="style.css" />
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
      href="https://fonts.googleapis.com/css2?family=Oswald&display=swap"
      rel="stylesheet"
    />
  </head>

  <body>
    <div class="webcam">
      <div class="video-outer">
        <video id="video" height="100%" width="100%" autoplay></video>
      </div>

      <div class="webcam-start-stop">
        <a href="#!" class="btn-start" onclick="start()">Start</a>
        <a href="#!" class="btn-stop" onclick="StopWebCam()">Stop</a>
      </div>
    </div>

    <script>
      var StopWebCam = function () {
        var stream = video.srcObject;
        var tracks = stream.getTracks();

        for (var i = 0; i < tracks.length; i++) {
          var track = tracks[i];
          track.stop();
        }
        video.srcObject = null;
      };

      var start = function () {
        var video = document.getElementById("video"),
          vendorURL = window.URL || window.webkitURL;

        if (navigator.mediaDevices.getUserMedia) {
          navigator.mediaDevices
            .getUserMedia({ video: true })
            .then(function (stream) {
              video.srcObject = stream;
            })
            .catch(function (error) {
              console.log("Something went wrong");
            });
        }
      };
      $(function () {
        start();
      });
    </script>
  </body>
</html>
```

# Step:2 Integrate Webcam

Then we need to add code for **style.css** which code I provide in the below screen.

```css
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Oswald", sans-serif;
}
body {
  height: 100vh;
  width: 100vw;
  background: #f2f4f6;
  overflow: hidden;
}
.webcam-start-stop {
  position: fixed;
  left: 0;
  bottom: 0;
  right: 0;
  padding: 5px 0;
  background: #000;
  display: flex;
  align-items: center;
  justify-content: space-around;
}
.webcam-start-stop > a {
  text-decoration: unset;
  color: #000;
  background: #fff;
  padding: 10px 20px;
}
```

<iframe height="651" style="width: 100%;" scrolling="no" title="" src="https://codepen.io/Codextracter/embed/ExmGMJb?default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/Codextracter/pen/ExmGMJb">
  </a> by Atharva (<a href="https://codepen.io/Codextracter">@Codextracter</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

## Congratulations!🎉 you just integrated webcam 👏👏

## Thank you for reading!😀 I hope you enjoyed it and please share if you enjoyed it.

<br><br><br>
