#### Directives 

Directives are a core feature in Vue 3 that <ins>provide a declarative way to interact with the DOM</ins>. They simplify tasks like binding data, managing events, and conditionally rendering content while keeping templates clean and readable. Whether you're using built-in directives or creating custom ones, they are essential for building dynamic, interactive applications with Vue.

<p>The following directives are available:</p>

| Directive	| Description |
| --- | --------|
| v-bind |	Binds an attribute to a data property |
| v-cloak |	Hides an un-compiled template until it is ready |
| v-for |	Renders a list of elements |
| v-html |	Outputs HTML code in the template |
| v-if |	Renders an element conditionally |
| v-else-if |	Renders an element conditionally when the first part of the if-statement is false |
| v-else |	Renders an element when the first part of the if-statement is false |
| v-memo |	Holds back rendering of an element until a change is detected in one or more specified properties |
| v-model	| Creates a two-way binding between an input element and the corresponding data property |
| v-on |	Connects an event to an action |
| v-once |	Renders an element only once |
| v-pre |	Skips compilation of an element and its content |
| v-show	 | Toggles an element's visibility conditionally |
| v-slot |	Directs content to a named slot |
| v-text |	Updates an element's text content |


&nbsp;
&nbsp;

### Purpose of Directives in Vue 3

**1. Dynamic DOM Manipulation:**
Directives help modify the DOM (e.g., show/hide elements, apply styles, set attributes) based on the state of your application.


**2. Simplify Common Tasks:**
Tasks like binding data to attributes, conditionally rendering content, or attaching event listeners become more concise and declarative with directives.


**3. Enhance Readability:**
Using directives makes your template logic easy to understand at a glance because they express intent clearly in the HTML.


**4. Reactivity Integration:**
Directives are tightly integrated with Vue's reactivity system, automatically updating the DOM when data changes.




&nbsp;<br>
&nbsp;<br>

#### Common Directives with basic code examples 

1. v-bind:
Dynamically binds attributes or properties to an element.
Example:

``` js
<img :src="imageUrl" :alt="imageDescription" />
```


2. v-if, v-else-if, v-else:
Conditionally renders elements based on an expression.
Example:

``` js
<p v-if="isLoggedIn">Welcome back!</p>
<p v-else>Login to continue.</p>
```

3. v-for:
Renders a list of items by iterating over an array or object.
Example:

```js
<ul>
  <li v-for="item in items" :key="item.id">{{ item.name }}</li>
</ul>
```

4. v-on:
Attaches event listeners to elements.
Example:

``` js
<button @click="handleClick">Click Me</button>
```

5. v-model:
Two-way binds a form input or component to a variable.
Example:

```js
<input v-model="username" placeholder="Enter your name" />
```

6. v-show:
Toggles the visibility of an element using CSS display.
Example:

``` js
<div v-show="isVisible">This is visible</div>
```


7. v-slot:
Defines a slot for passing content into a child component.
Example:

```js
<MyComponent>
  <template v-slot:default>
    <p>Default Slot Content</p>
  </template>
</MyComponent>
```


8. v-html:
Dynamically renders raw HTML inside an element.
Example:

``` js
<div v-html="htmlContent"></div>
```

Warning: Be cautious with v-html as it can introduce XSS vulnerabilities if used with untrusted content.


&nbsp;

**Custom Directives in Vue 3**

Vue also allows you to define your own directives for custom behavior. These are useful when the built-in directives don't meet your requirements.

Example: Custom Directive to Autofocus an Input

```js
<template>
  <input v-autofocus />
</template>

<script>
export default {
  directives: {
    autofocus: {
      mounted(el) {
        el.focus();
      },
    },
  },
};
</script>
```


&nbsp;<br>

**Built-In vs Custom Directives**

Built-In Directives: Provided by Vue and cover most common use cases (e.g., v-if, v-for, v-bind).

Custom Directives: Allow you to implement unique behaviors that are specific to your application.



&nbsp;<br>

**Advantages of Using Directives**

1. Declarative Syntax: Makes templates expressive and easier to read.


2. Seamless Integration with Reactivity: Automatically updates the DOM when data changes.


3. Encapsulation: Custom directives encapsulate behavior, keeping templates clean.


4. Reusability: Custom directives can be reused across components.



&nbsp;<br>
&nbsp;<br>

**Summary**

Directives are a core feature in Vue 3 that provide a declarative way to interact with the DOM. They simplify tasks like binding data, managing events, and conditionally rendering content while keeping templates clean and readable. Whether you're using built-in directives or creating custom ones, they are essential for building dynamic, interactive applications with Vue.

