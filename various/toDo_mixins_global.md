#### Global Mixins

A global mixin in Vue 3 is a feature provided by the Vue framework (which is not a standard part of JavaScript) that allows you to define functionality (like methods, data, or lifecycle hooks) that is automatically available in every component in your application. It helps to avoid repetitive code when multiple components need the same behavior or utility functions.

**What Is a Mixin?**</br>
<ins>A mixin is a reusable piece of logic that can be shared across Vue components</ins>. Mixins are merged into the component they are used in. For example, if you have a set of utility methods for playing audio, you can write those once in a mixin and include the mixin in any component that needs it.

**What Is a Global Mixin?**</br>
A global mixin applies a mixin to every single Vue component in your application. Once registered, it becomes part of all components automatically.

\
**Example of a Global Mixin**
- Define the Mixin</br>
- Create a mixin file (e.g., src/mixins/audioMixin.js):</br>

```javascript
export default {
  methods: {
    playSound(audioElement) {
      if (audioElement) {
        audioElement.play();
      }
    },
    stopSound(audioElement) {
      if (audioElement) {
        audioElement.pause();
        audioElement.currentTime = 0; // Reset to the beginning
      }
    },
  },
};
```

Register It Globally
In your main.js file, import the mixin and register it globally:

```javascript
import { createApp } from "vue";
import App from "./App.vue";
import audioMixin from "@/mixins/audioMixin";

const app = createApp(App);

app.mixin(audioMixin); // Registers the mixin globally

app.mount("#app");
```

**Use the Mixin in Any Component**<br>
After registering the global mixin, the playSound and stopSound methods are available in every Vue component without explicitly importing them:

```vue
<template>
  <div>
    <a @click.prevent="playSound($refs.audioRef)">Play</a>
    <a @click.prevent="stopSound($refs.audioRef)">Stop</a>
    <audio ref="audioRef" :src="audioSrc" loop autoplay></audio>
  </div>
</template>

<script>
export default {
  data() {
    return {
      audioSrc: "./mp3/koordinaten.mp3",
    };
  },
};
</script>
```



#### Pros and Cons of Global Mixins<br>

**Pros:**
1. Convenience: Automatically makes reusable logic available in all components.
2. DRY Code: Reduces the need to import utility functions in multiple components.

**Cons:**
1. Global Scope Pollution: It adds properties or methods to all components, <ins>which might lead to unintended conflicts</ins>.
2. Reduced Clarity: It's <ins>harder to track where a method or property is coming from</ins> because it's not explicitly imported into the component.

