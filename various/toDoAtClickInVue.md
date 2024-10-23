<h3>@ Sign usage in Vue</h3>

In Vue 3 (and beyond), the `@` symbol is widely used as a shorthand in templates and project configuration. Here are the primary usages of `@` in Vue:

### 1. **Shorthand for Event Binding (`v-on`) in Templates**
The most common use of `@` in Vue is as a shorthand for the `v-on` directive, which is used to listen for DOM events.

In Vue templates, instead of writing:

```vue
<button v-on:click="handleClick">Click me</button>
```

You can use the shorthand syntax with `@`:

```vue
<button @click="handleClick">Click me</button>
```

This shorthand applies to any DOM event, such as `click`, `input`, `change`, `keyup`, etc.

For example:
```vue
<input @input="handleInput" />
<button @mouseover="hoverEffect">Hover over me</button>
```

The `@` syntax makes the template code more concise and easier to read.

### 2. **Alias for Import Paths (Webpack or Vite)**
In Vue project configurations (usually when using Webpack or Vite), `@` is often used as an alias for the `src` directory in the project. This allows for simpler and more maintainable imports, avoiding long relative paths like `../../../` when importing components, assets, or other files.

For example, instead of writing a relative path like this:

```javascript
import MyComponent from '../../../components/MyComponent.vue';
```

You can use the `@` alias to import from the `src` folder directly:

```javascript
import MyComponent from '@/components/MyComponent.vue';
```

In the project configuration (like `vite.config.js` or `webpack.config.js`), the alias is defined as:

#### Vite Configuration (vite.config.ts):
```js
import { defineConfig } from 'vite';
import vue from '@vitejs/plugin-vue';
import path from 'path';

export default defineConfig({
  resolve: {
    alias: {
      '@': path.resolve(__dirname, 'src'),
    },
  },
  plugins: [vue()],
});
```

#### Webpack Configuration (webpack.config.js):
```js
const path = require('path');

module.exports = {
  resolve: {
    alias: {
      '@': path.resolve(__dirname, 'src'),
    },
  },
};
```

This simplifies the import paths throughout your project, making it cleaner and more maintainable.

### 3. **Event Modifiers with `@`**
Vue provides event modifiers that are used to modify the behavior of events. These modifiers are appended after the event name using a dot (`.`). For example:

- **@click.prevent**: Prevent the default behavior of an event.
- **@click.stop**: Stop the event from propagating (bubbling up the DOM tree).
- **@submit.prevent**: Prevent the default form submission.

Example usage:
```vue
<button @click.prevent="submitForm">Submit</button>
```

Here’s a breakdown of some common event modifiers:
- **`.prevent`**: Calls `event.preventDefault()` on the event.
- **`.stop`**: Calls `event.stopPropagation()` on the event.
- **`.capture`**: Adds the event listener in the capture mode (triggers before the target).
- **`.self`**: Only triggers the event if the event target is the element itself.
- **`.once`**: Ensures the event listener is only invoked once.

Example:

```vue
<form @submit.prevent="handleSubmit">
  <button @click.stop="handleClick">Click me</button>
</form>
```

### 4. **Modifiers for `@` in Vue 3**
Vue 3 introduces some new modifiers for handling events more effectively:
- **`.passive`**: Improves performance by marking the listener as passive. It prevents `event.preventDefault()` for certain types of events (like scrolling).
  
  Example:
  ```vue
  <div @scroll.passive="handleScroll">Scroll me</div>
  ```

- **`.exact`**: Ensures that the event is triggered only when the exact combination of key modifiers is pressed (used in keyboard events).

  Example:
  ```vue
  <button @click.exact="handleExactClick">Click me</button>
  ```

### 5. **Shorthand in Nuxt.js for Vue Router**
In frameworks like **Nuxt.js** (which is built on top of Vue), the `@` symbol is also used in combination with the router-link for better file organization. Since Nuxt.js uses the `@/` shorthand to resolve paths from the `src` or `pages` directory, it’s common to see `@/` in component paths or Nuxt-specific configurations.

### Summary of `@` Usage in Vue 3:
- **Event Binding Shorthand**: `@` is shorthand for `v-on`, simplifying event listener binding.
  ```vue
  @click="doSomething" // Instead of v-on:click
  ```

- **Path Aliasing**: `@` is used as an alias for the `src` directory in import statements (configured in Webpack or Vite).
  ```javascript
  import MyComponent from '@/components/MyComponent.vue';
  ```

- **Event Modifiers**: Modifiers can be used with `@` to modify event behavior (`@click.stop`, `@submit.prevent`, etc.).

In summary, the `@` symbol in Vue 3 and beyond serves two main purposes: it's used as a shorthand for `v-on` in templates for event handling and as an alias for the `src` directory in import paths. Both usages help improve code readability and maintainability.