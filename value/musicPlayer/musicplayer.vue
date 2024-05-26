<template>
  <div id="app">
    <header>
      <h1>Vue 3 Music Player</h1>
      <input type="file" @change="handleFiles" multiple webkitdirectory directory />
    </header>
    <main>
      <ul>
        <li v-for="(file, index) in audioFiles" :key="index" @click="playAudio(file)">
          {{ file.name }}
        </li>
      </ul>
      <audio ref="audioPlayer" controls></audio>
    </main>
</template>


<script>
import { ref } from 'vue';
  
export default {
  setup() {   // Setup the composition API
    const audioFiles = ref([]);
    const audioPlayer = ref(null);
    const currentTrack = ref(null); // Display the current track being played.

      const handleFiles = (event) => {
      const files = Array.from(event.target.files).filter((file) =>
        ['audio/mp3', 'audio/mp4', 'audio/wav'].includes(file.type)
      );
      audioFiles.value = files;
    };

     const playAudio = (file) => {
      const audioURL = URL.createObjectURL(file);
      audioPlayer.value.src = audioURL;
      audioPlayer.value.play();
      currentTrack.value = file;
    };

      return {
      audioFiles,
      audioPlayer,
      currentTrack,
      handleFiles,
      playAudio,
    };
    
  },
};

</script>

<style scoped>
  #app {
  text-align: center;
}
header {
  margin: 20px;
}
main {
  margin: 20px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  cursor: pointer;
  margin: 5px 0;
}
</style>
