#### Mouse hover, video playback. 


&nbsp;</br>
To convert this code to Vue 3, we’ll need to create a Vue component that sets up the video elements and manages the mouseenter and mouseleave events for play and pause functionality. Here’s how this code would look rewritten as a Vue 3 single-file component:

```js
<template>
  <div class="container">
    <div
      v-for="(videoSrc, index) in videos"
      :key="index"
      class="box"
      @mouseenter="playVideo(index)"
      @mouseleave="pauseVideo(index)"
    >
      <video :src="videoSrc" type="video/mp4" loop ref="videoRefs" class="clip"></video>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';

export default {
  setup() {
    const videos = [
      'vidTirol.mp4',
      'vidStarryNight.mp4',
      'vidYosemiteCapitan.mp4',
      'vidLosAngeles.mp4'
    ];

    const videoRefs = ref([]);

    const playVideo = (index) => {
      videoRefs.value[index].play();
    };

    const pauseVideo = (index) => {
      videoRefs.value[index].pause();
    };

    onMounted(() => {
      videoRefs.value = videoRefs.value.slice(0, videos.length);
    });

    return {
      videos,
      videoRefs,
      playVideo,
      pauseVideo
    };
  }
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #333333;
}

.container {
  display: flex;
  flex-wrap: wrap;
  min-height: 100vh;
  width: 100%;
}

.container .box {
  position: relative;
  width: 50%;
  height: 50vh;
  filter: grayscale(1);
  border: 2px solid #222;
}

.container .box:hover {
  filter: grayscale(0);
}

.container .box video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

@media (max-width: 800px) {
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    min-height: 100vh;
  }
}
</style>
```

Explanation of Changes

1. Template:

Use v-for to iterate over the videos array, creating a div for each video source. This dynamically generates each video element and associates its index with mouse events.

Bind @mouseenter and @mouseleave events to trigger the playVideo and pauseVideo methods respectively, passing the current index.



2. Script:

We define videos, which is an array of video file paths.

videoRefs is a reference array to store direct DOM references to the video elements.

playVideo and pauseVideo functions are defined to control video playback based on index.

In onMounted, we adjust videoRefs to match the number of videos in the array.



3. Scoped Styling:

CSS is included in the <style scoped> block to ensure styles apply only to this component.




This Vue 3 component mirrors the original functionality but leverages Vue's reactivity and scoped component structure.

