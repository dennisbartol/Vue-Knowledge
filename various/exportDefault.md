<h4>Export Default in Vue</h4>


In Vue.js, `export default` is a feature of JavaScript's module system, not specifically tied to Vue itself, although it's commonly used in Vue components.

Here's what it does:

<b>1. Exporting:</b> <ins>It exports a single value or object as the default export from a module. This means that when another module imports from this module, it will receive whatever is exported as the default</ins>.

<b>2. Default Import:</b> When importing from a module that has a default export, you can import it without curly braces {}. For example:
<code>
// Exporting module
export default {
  data() {
    return {
      message: 'Hello'
    }
  }
}
</code>
Javascript:</br>
<code>
// Importing module
import MyComponent from './MyComponent.vue'

// Now MyComponent refers to the default export of MyComponent.vue
</code>

In Vue.js, 'export default' commonly <ins>used to export Vue components, allowing other parts of the application to import and use them easily</ins>. This is a convention in Vue.js projects, though you're not required to use it - you could use named exports and imports instead if you prefer.

<h4>Other objects and methods</h4>

In addition, in Vue.js components, besides the data() method, there are several other objects or methods that you commonly use to define the component's behavior and structure. <ins>Here are some of the key ones</ins>:

<b>1. Props:</b> This object allows a parent component to pass data down to a child component. It's an array or an object containing props that the component accepts.

<b>2. Computed:</b> Computed properties are cached based on their reactive dependencies. They are useful for deriving values based on other data in the component.

<b>3. Methods:</b> This object contains methods that the component can use. These methods can be called from within the component's template or from other methods.

<b>4. Watch:</b> This object allows you to perform side effects in response to changes in reactive data. You can watch individual properties or an expression and execute a callback when the value changes.

<b>5. Components:</b> This object is used to register child components within a parent component. It's particularly useful in single-file components where you define multiple components in the same file.

<b>6. Mounted:</b> This is a lifecycle hook that is called after the component has been mounted to the DOM. It's often used for performing initial setup that requires access to the DOM.

<b>7. Created:</b> This is a lifecycle hook that is called synchronously after the instance has been initialized, before data observation and computed properties are set up.



