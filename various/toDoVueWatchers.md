### Vue Watchers

- A watcher is a method that watches a data property with the same name.
- A watcher runs every time the data property value changes.
- Use a watcher if a certain data property value requires an action.

**The Watcher Concept**
Watchers are the fourth configuration option in the Vue instance. The other three configuration options (we have already looked at) are 'data', 'methods' and 'computed'.

As with 'data', 'methods' and 'computed' watchers also has a reserved name in the Vue instance: **'watch'.**

Example:</br>
``` js
const app = Vue.createApp({
  data() {
    ...
  },
  watch: {
    ...
  },
  computed: {
    ...
  },
  methods: {
    ...
  }
})
```
