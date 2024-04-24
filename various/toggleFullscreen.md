<h4>Toggle Fullscreen</h4>

To create a video player in Vue 3 with fullscreen enter/exit options, you can follow these steps:

1. Setup Vue Project: Set up a new Vue project or use an existing one.
2. Install Dependencies: You'll need to install the vue-video-player package to handle video playback. You can do this via npm or yarn:</br>
<code>
npm install vue-video-player video.js
</code>
<code>
yarn add vue-video-player video.js
</code>

3. Import Video Player Component: In your Vue component where you want to use the video player, import the necessary components:
<code>
import { VueVideoPlayer } from 'vue-video-player';
import 'video.js/dist/video-js.css';
</code>


4. Create Vue Component: Define your Vue component with the video player and fullscreen functionality:
<code>
&lt;template>
  &lt;div>
    &lt;video-player ref="videoPlayer" class="video-js vjs-default-skin"></video-player>
    &lt;button @click="toggleFullscreen">Toggle Fullscreen</button>
  &lt;/div>
&lt;/template>
</code>
<code>
&lt;script>
import { VueVideoPlayer } from 'vue-video-player';
import 'video.js/dist/video-js.css';
</code>
<code>
export default {
  components: {
    videoPlayer: VueVideoPlayer
  },
  methods: {
    toggleFullscreen() {
      const videoPlayer = this.$refs.videoPlayer.$refs.videoPlayer;
      if (videoPlayer.requestFullscreen) {
        videoPlayer.requestFullscreen();
      } else if (videoPlayer.mozRequestFullScreen) {
        videoPlayer.mozRequestFullScreen();
      } else if (videoPlayer.webkitRequestFullscreen) {
        videoPlayer.webkitRequestFullscreen();
      } else if (videoPlayer.msRequestFullscreen) {
        videoPlayer.msRequestFullscreen();
      }
    }
  }
};
&lt;/script>
</code>
<code>
&lt;style scoped>
/* Add your custom styles here */
&lt;/style>
</code>

<h4>How to toggle the videoplayer only (Like YT)</h4>
To set the video player element to fullscreen mode like YouTube's video player, you can use the `requestFullscreen()` API and CSS to achieve this. Here's how you can modify the previous example to make the video player element fullscreen:

<code>
&lt;template>
  &lt;div ref="videoContainer" class="video-container">
    &lt;video ref="videoPlayer" class="video-js vjs-default-skin"></video>
    &lt;button @click="toggleFullscreen">Toggle Fullscreen</button>
  &lt;/div>
&lt;/template>
</code>
<code>
&lt;script>
import { VueVideoPlayer } from 'vue-video-player';
import 'video.js/dist/video-js.css';
</code>
<code>
export default {
  components: {
    videoPlayer: VueVideoPlayer
  },
  methods: {
    toggleFullscreen() {
      const videoContainer = this.$refs.videoContainer;
      if (!document.fullscreenElement) {
        videoContainer.requestFullscreen();
      } else {
        if (document.exitFullscreen) {
          document.exitFullscreen();
        }
      }
    }
  }
};
&lt;/script>
</code>
<code>
&lt;style scoped>
.video-container {
  position: relative;
  width: 100%;
  height: 0;
  padding-top: 56.25%; /* 16:9 aspect ratio */
}
</code>
<code>
.video-container video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</code>
<code>
/* Add your custom styles here */
&lt;/style>
</code>

</code>

In this version:
&nbsp;</br>
1. The video element is wrapped inside a div with a class video-container.
2. CSS is used to maintain the aspect ratio of the video player.
3. The toggleFullscreen method toggles fullscreen mode for the video-container instead of just the video element.
4. When entering fullscreen, requestFullscreen() is called on the video-container.
5. When exiting fullscreen, document.exitFullscreen() is called.

This will make the entire video player container fullscreen, similar to the behavior seen on YouTube's video player. Adjust the styles and layout as needed to fit your design requirements.

</p>
