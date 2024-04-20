<h4>Computed functions in Vue</h4>

A computed function in Vue.js is a special type of property that is derived from one or more reactive properties and is updated automatically whenever its dependencies change. Computed properties are used to perform calculations or transformations on reactive data in a Vue component.

Here's a breakdown of how computed properties work:

<b>1. Automatic Dependency Tracking:</b> Vue.js automatically tracks the reactive dependencies used inside a computed property. This means that if any of the reactive properties that the computed property depends on change, Vue will know to re-evaluate the computed property.

<b>2. Caching:</b> Computed properties are cached based on their reactive dependencies. If the reactive dependencies have not changed since the last evaluation of the computed property, Vue will return the cached result instead of re-evaluating the computed property.

<b>3. Lazy Evaluation:</b> Computed properties are lazy by default, meaning they won't be evaluated until they are accessed in the template or within the component's JavaScript code.

<b>4. Getter and Setter:</b> Computed properties have both a getter and a setter function. The getter function calculates the value of the computed property based on its dependencies, while the setter function allows you to define custom behavior when trying to assign a value to the computed property.

Here's a simple example of a computed property in Vue.js:



![Knipsel_computed](https://github.com/dennisbartol/Vue-Knowledge/assets/85198215/e134b747-bd25-483e-bf38-7e413692ed56)

In this example, the `area` computed property depends on the width and height reactive properties. Whenever width or height changes, Vue will automatically recalculate the area and update any bindings in the template that reference it.
