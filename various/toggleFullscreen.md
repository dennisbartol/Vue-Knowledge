<h4>Toggle Fullscreen</h4>

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
