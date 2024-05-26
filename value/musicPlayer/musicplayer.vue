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
    const audioFiles = ref([]); // This line creates a reactive reference to an empty array. audioFiles will hold the list of audio files selected by the user.
   // Since audioFiles is a reactive reference, any changes to its value will cause the component to re-render where this reference is used.
    
    const audioPlayer = ref(null); // This line creates a reactive reference to null.
    // audioPlayer will be used to reference the <audio> element in the template.
    //By initializing it with null, you set up a placeholder that will later be assigned the actual DOM element when it is mounted.
    
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
