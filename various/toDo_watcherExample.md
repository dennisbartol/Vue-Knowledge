<h4>Watchers in Vue (3)</h4>

**Watchers** are still relevant and useful in Vue 3, but their usage has evolved somewhat with the introduction of the Composition API. Vue 3 maintains compatibility with watchers, and they continue to provide value when you need to respond to changes in reactive data, whether you're using the Options API or the new Composition API.

How Watchers Operate in Vue 3:
Watchers in Options API (similar to Vue 2): If you're using the Options API (the traditional way of writing Vue components), watchers work the same way they did in Vue 2. You define a watch property in your component and specify the data property or computed property you want to observe.

Example:

```javascript

export default {
  data() {
    return {
      count: 0,
    };
  },
  watch: {
    count(newValue, oldValue) {
      console.log(`Count changed from ${oldValue} to ${newValue}`);
    },
  },
};
```

Watchers in Composition API (New in Vue 3): With the Composition API, Vue introduces a more flexible way to define watchers using the watch function. This function can observe reactive variables, computed properties, or even specific functions returning reactive values. It's more powerful and easier to manage in larger components because it avoids polluting the component's options space.

Here's how it works:

javascript
Code kopiëren
import { ref, watch } from 'vue';

export default {
  setup() {
    const count = ref(0);

    // Watcher to track changes in 'count'
    watch(count, (newValue, oldValue) => {
      console.log(`Count changed from ${oldValue} to ${newValue}`);
    });

    return {
      count,
    };
  },
};
The watch function takes two arguments: the reactive reference (or computed function) and a callback to run when the value changes.
The first argument can also be a getter function if you want to watch multiple reactive properties at once or to observe deep changes.
Key Differences in Vue 3:
More Control over Dependencies: In the Composition API, you have more fine-grained control over what you're watching, and you can directly watch computed properties, refs, or complex functions that return reactive values.

Watching Multiple Sources: With the Composition API, you can watch multiple reactive sources simultaneously by passing an array to the first argument of watch.

Example:

javascript
Code kopiëren
watch([count, anotherReactive], ([newCount, newAnotherValue], [oldCount, oldAnotherValue]) => {
  console.log(`Count changed from ${oldCount} to ${newCount}`);
  console.log(`Another value changed from ${oldAnotherValue} to ${newAnotherValue}`);
});
Deep Watching: If you need to deeply watch an object or array, you can pass an additional deep: true option to the watch function. This works similarly to how deep watchers work in Vue 2.

Example:

```javascript

const state = reactive({ nested: { value: 0 } });

watch(
  () => state.nested,
  (newVal, oldVal) => {
    console.log("Nested value changed");
  },
  { deep: true }
);
```

Immediate Invocation: Watchers in Vue 3 also support the immediate option, which can be used to run the watcher function immediately upon setup, rather than waiting for the first change.

```javascript
watch(count, (newValue, oldValue) => {
  console.log(`Initial value or changes: ${newValue}`);
}, { immediate: true });
```

**When to Use Watchers in Vue 3:**</br>
When you need side effects based on data changes: Watchers are useful when you need to run some logic (like an API call, logging, or complex state management) in response to changes in reactive data.
More explicit control than computed properties: Computed properties are typically better suited for deriving values, while watchers are better when you need to trigger side effects or handle more complex logic.
In summary, watchers are still an integral part of Vue 3, and they remain useful when you need to run side effects in response to changes in reactive data. However, with the Composition API, you get more flexibility and control over your watchers, which can make them easier to use and scale in more complex applications.
