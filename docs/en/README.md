# vue-core-video-player



## Getting Started

### Install

``` bash
$ npm install --save vue-core-video-player 
```

Anyway, you could use the cdn bundle

``` html
<script src="./dist/vue-core-vide-player.min.js"></script>
```

### Add Video Source

``` vue
<div id="app">
  <vue-core-video-player src="./your_video_source.mp4"></vue-core-video-player>
</div>
```

``` vue
import VueCoreVideoPlayer from 'vue-core-video-player'

export default {
  name: 'app',
  components: {
    VueCoreVideoPlayer
  }
}
```

### Basic Configuration

#### The video source

Use `src` property to set the video source of your player. It must be the only three types below.

+ String; It can be relative path of your video file or some cdn url.

``` html
<vue-core-video-player src="https://media.vued.vanthink.cn/sparkle_your_name_am720p.mp4"></vue-core-video-player>
```
+ Array; It means you set different resolution of the same video source; Our default resolution is `720p`;

And you must set two keys (`resolution`, `src`) of your array item.

``` js
const videoSource = [
  {
    src: 'https://media.vued.vanthink.cn/sparkle_your_name_am360p.mp4',
    resolution: 360,
  }, {
    src: 'https://media.vued.vanthink.cn/sparkle_your_name_am720p.mp4',
    resolution: 720,
  }, {
    src: 'https://media.vued.vanthink.cn/y2mate.com%20-%20sparkle_your_name_amv_K_7To_y9IAM_1080p.mp4',
    resolution: 1080
  }
]
```
If you want to play different file type in different browser. You can add `type` property in an array;

``` bash
const videoSource = [
  {
    src: 'https://media.vued.vanthink.cn/sparkle_your_name_am360p.mp4',
    type: 'video/webm',
  }, {
    src: 'https://media.vued.vanthink.cn/sparkle_your_name_am720p.mp4',
    type: 'video/mp4',
  }
]
```

[caniuse-video-format](https://caniuse.com/#search=video%20format) show which browser supports the specify video file.


### controls

`controls` is set for player bottom dashboard. 

+ String; 

  + 'fixed' means the bottom dashboard is still visible to users. 'auto' means 
  + 'auto' means the bottom dashboard will hide when there is no interaction between user and player.

+ Boolean;
  + `false` means that player will hide the bottom dashboard
  + `true`  means that player will show the bottom dashboard and work like the `'auto'` value above;


### Autoplay

If you set `autoplay`, the player will try to play video. Different browser has different policies to handle auto play action. If player failed, it will show the play button for user to touch.

### Video Playback control

And it keep the same attributes of [HTML Video](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video).

| Props        | Type         | Example  | Description  |
| ------------- |:-------------:|:----- |:--------------|
| volume     | number | `0.5` | the volume of video (0-1) |
| muted     | boolean | `true` | if set `true`, the video will be muted  |
| cover     | string | `'./cover.png'` | it will show the cover of the video  |
| [preload](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)   | string | `'metadata'`  | `'none'` means not preload video source; `'metadata'` indicates that only video metadata (e.g. length) is fetched  |















