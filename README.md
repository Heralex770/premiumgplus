<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PremiumQPlus</title>
  <script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
  <style>
    body {
      background-color: white;
      font-family: Arial, sans-serif;
      text-align: center;
    }
    .premiumqplus {
      position: fixed;
      top: 20px;
      right: 20px;
      font-size: 24px;
      font-weight: bold;
      color: red;
      text-shadow: 0 0 5px red;
      animation: blink 1s infinite alternate;
    }
    @keyframes blink {
      0% { opacity: 1; }
      100% { opacity: 0; }
    }
    video {
      width: 80%;
      height: 500px;
      margin-top: 20px;
      background: black;
    }
    .channel-bar {
      position: fixed;
      bottom: 10px;
      left: 0;
      width: 100%;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
      font-size: 18px;
      font-weight: bold;
      text-transform: uppercase;
      animation: colorChange 5s infinite alternate;
    }
    .channel-bar span {
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
    }
    @keyframes colorChange {
      0% { color: red; }
      25% { color: blue; }
      50% { color: green; }
      75% { color: orange; }
      100% { color: purple; }
    }
  </style>
</head>
<body>
  <div class="premiumqplus">PremiumQPlus</div>
  <h1>Canlı Yayınlar</h1>
  <video id="videoPlayer" controls autoplay></video>
  <div class="channel-bar">
    <!-- BeIN Sports yayınları -->
    <span onclick="playStream('http://germanyqdnsx11.com:8080/live/pxNy8YcJ1h/Iwdd5ox4cm/89006.m3u8')">BeIN Sports</span>
    <span onclick="playStream('http://germanyqdnsx11.com:8080/live/riza0956/deneri0956/89004.m3u8')">BeIN Sports</span>
    <span onclick="playStream('http://germanyqdnsx11.com:8080/live/celalcakir/705d2y01e/105874.m3u8')">BeIN Sports</span>
    <span onclick="playStream('http://germanyqdnsx11.com:8080/live/arslan46/46arslan/89004.m3u8')">BeIN Sports</span>
    <span onclick="playStream('http://germanyqdnsx11.com:8080/live/arslan54/54arslan/89006.m3u8')">BeIN Sports</span>
    <span onclick="playStream('http://germanyqdnsx11.com:8080/live/ferhat123/ferhat321/89004.m3u8')">BeIN Sports</span>
    <span onclick="playStream('http://germanyqdnsx11.com:8080/live/tuncay/tuncay14/89006.m3u8')">BeIN Sports</span>
    
    <!-- Tabii Spor yayınları -->
    <span onclick="playStream('https://beert7sqimrk0bfdupfgn6qew.medya.trt.com.tr/master_1080p.m3u8')">Tabii Spor</span>
    <span onclick="playStream('https://iaqzu4szhtzeqd0edpsayinle.medya.trt.com.tr/master_1080p.m3u8')">Tabii Spor</span>
    <span onclick="playStream('https://klublsslubcgyiz7zqt5bz8il.medya.trt.com.tr/master_1080p.m3u8')">Tabii Spor</span>
    <span onclick="playStream('https://ujnf69op16x2fiiywxcnx41q8.medya.trt.com.tr/master_1080p.m3u8')">Tabii Spor</span>
    <span onclick="playStream('https://bfxy3jgeydpbphtk8qfqwm3hr.medya.trt.com.tr/master_1080p.m3u8')">Tabii Spor</span>
    <span onclick="playStream('https://z3mmimwz148csv0vaxtphqspf.medya.trt.com.tr/master_1080p.m3u8')">Tabii Spor</span>
    <span onclick="playStream('https://vbtob9hyq58eiophct5qctxr2.medya.trt.com.tr/master_1080p.m3u8')">Tabii Spor</span>
    
    <!-- Diğer kanallar -->
    <span onclick="playStream('https://tv-trt1.medya.trt.com.tr/master_1080.m3u8')">TRT 1</span>
    <span onclick="playStream('https://tv-trtspor1.medya.trt.com.tr/master_1080.m3u8')">TRT SPOR</span>
    <span onclick="playStream('https://tv8-live.daioncdn.net/tv8/tv8_1080p.m3u8')">TV8</span>
    <span onclick="playStream('https://tv8-live.daioncdn.net/tv8bucuk/tv8bucuk_1080p.m3u8')">TV8.5</span>
    <span onclick="playStream('https://canli.tgrthaber.com/tgrt.m3u8')">TGRT HABER</span>
  </div>
  <script>
    function playStream(url) {
      var video = document.getElementById('videoPlayer');
      if (Hls.isSupported()) {
        var hls = new Hls();
        hls.loadSource(url);
        hls.attachMedia(video);
        hls.on(Hls.Events.MANIFEST_PARSED, function() {
          video.play();
        });
      } else if (video.canPlayType('application/vnd.apple.mpegurl')) {
        video.src = url;
        video.play();
      } else {
        alert('Tarayıcınız bu yayını desteklemiyor.');
      }
    }
  </script>
</body>
</html>
