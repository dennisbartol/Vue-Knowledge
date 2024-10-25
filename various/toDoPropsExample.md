<h4>Property usage in Vue 3.</h4>




In Vue 3, **props** are still a core concept for passing data from parent components to child components. Props allow you to pass data into child components, enabling reusability and flexibility. With the Composition API, you can define and use props more flexibly, but the basic functionality remains the same as in Vue 2.

### Example of Props Usage in Vue 3

#### 1. **Parent Component**: Passing data to a child component
In the parent component, you define the child component and pass data using **props**.

#### 2. **Child Component**: Receiving the props
The child component declares the props it expects, and it can use them inside its template or script.

---

### Step-by-Step Example:

Let's say you want to pass a `message` and a `count` prop to a child component.

#### Parent Component (e.g., `App.vue`)

```vue
<template>
  <div>
    <h1>Parent Component</h1>
    <!-- Passing props 'message' and 'count' to the ChildComponent -->
    <ChildComponent message="Hello from parent" :count="5" />
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue'; // Import the child component

export default {
  components: {
    ChildComponent, // Register the child component
  },
};
</script>
```

In the above example:
- The `message` prop is passed as a string (`"Hello from parent"`).
- The `count` prop is passed dynamically with a number (`5`) using `v-bind` (`:` shorthand).

#### Child Component (e.g., `ChildComponent.vue`)

```vue
<template>
  <div>
    <h2>Child Component</h2>
    <p>Message from parent: {{ message }}</p>
    <p>Count from parent: {{ count }}</p>
  </div>
</template>

<script>
export default {
  props: {
    // Declare the props this component expects
    message: {
      type: String,  // Specify the prop type
      required: true // Mark it as required
    },
    count: {
      type: Number,  // Type checking
      required: true // Mark it as required
    }
  },
};
</script>
```

In the child component:
- **Props declaration**: The `props` object defines the `message` and `count` props. Each prop has:
  - **type**: This is used to validate the prop (e.g., `String` or `Number`).
  - **required**: Marks the prop as mandatory.
- The child component can access and use these props via the template using `{{ message }}` and `{{ count }}`.

### Output:
When you render the parent component, it will pass the `message` and `count` props to the child component, which will display:

```
Parent Component
Child Component
Message from parent: Hello from parent
Count from parent: 5
```

### Vue 3 Composition API Usage for Props
If you're using the **Composition API**, the syntax to define props changes slightly, but the concept is the same.

```vue
<template>
  <div>
    <h2>Child Component (Composition API)</h2>
    <p>Message from parent: {{ message }}</p>
    <p>Count from parent: {{ count }}</p>
  </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    message: {
      type: String,
      required: true,
    },
    count: {
      type: Number,
      required: true,
    },
  },
  setup(props) {
    // 'props' is passed as an argument to the setup function
    return { ...props };
  },
});
</script>
```

In this Composition API example:
- `props` are passed as an argument to the `setup()` function.
- The `setup()` function returns the `props`, which makes them available in the template.

### Summary of Props in Vue 3:
- **Props** allow you to pass data from a parent component to a child component.
- In **Options API**, props are declared in the `props` option.
- In **Composition API**, props are accessed within the `setup()` function.
- Props are typed (e.g., `String`, `Number`) and can be required or optional.
  
This pattern provides flexibility and reusability when working with Vue components!