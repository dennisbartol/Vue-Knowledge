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


export default {
  setup() {


  }
}


<style scoped>

</style>
