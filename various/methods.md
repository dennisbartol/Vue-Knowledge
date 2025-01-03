#### Vue (JS) methods. 


In Vue 3, the :methods property under export default in a Vue component is used to define the methods that can be used within that component. These methods typically include custom functions that perform actions, handle events, or manipulate data associated with the component.

Purpose of methods in Vue 3

**1. Event Handlers:** Methods are commonly used as event handlers for user interactions like clicks, key presses, or form submissions.

``` js
<template>
  <button @click="handleClick">Click me</button>
</template>

<script>
export default {
  methods: {
    handleClick() {
      console.log('Button clicked!');
    }
  }
}
</script>
```

**2. Data Manipulation:** Methods allow you to create reusable functions to modify or process the component's data.

``` js
<template>
  <div>
    <p>{{ message }}</p>
    <button @click="reverseMessage">Reverse Message</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'Hello Vue!'
    };
  },
  methods: {
    reverseMessage() {
      this.message = this.message.split('').reverse().join('');
    }
  }
}
</script>
```

**3. Code Organization:** They help separate logic from the template, making the codebase cleaner and more maintainable.


**4. Reusability:** Methods can be reused multiple times within the template or other parts of the component.


**5. Accessibility from Lifecycle Hooks:** You can call methods within lifecycle hooks, such as mounted, to perform operations when the component is initialized or updated.



Key Characteristics of methods in Vue 3

Context Binding: Methods in Vue automatically bind this to the Vue instance, so you can access reactive data, computed properties, and other methods using this.

Not Reactive: Unlike computed properties, methods do not cache their return values. They are executed every time they are called.

Separation from setup: In Vue 3's Composition API, you may not use the methods option directly; instead, you define functions inside the setup function. However, methods remains part of the Options API, providing backward compatibility and ease of use for developers familiar with Vue 2.


By using methods, you can implement interactive functionality within Vue components effectively.

