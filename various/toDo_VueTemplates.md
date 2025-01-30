### Vue Templates

A template in Vue is what we call the HTML part of our Vue application. 
The `<template>` tag will later be used in *.vue files to structure our code in a better way.
It is possible to use template as a configuration option in the Vue instance, and put the HTML code inside.


In Vue 3, <template> is a special HTML-like element used to define the structure of a Vue component's UI. It acts as a container for the component’s markup and is essential in Vue’s Single File Components (SFCs) or inside inline component definitions.

Key Points About <template> in Vue 3:</br>

**1. Encapsulation of Markup:**
The <template> section contains the HTML structure of the component.
It is not rendered as an actual DOM element in the output.

**2. Reactivity & Binding:**
It can contain Vue directives like `v-bind, v-for, v-if`, etc.
It can dynamically render data using `{{ }} (interpolation)`.

**3. Scoped to the Component:**
Unlike regular HTML, elements inside <template> are reactive and belong only to the component they are defined in.

**4. Multiple Root Elements (Vue 3 Feature):**
Vue 3 allows multiple root elements inside <template>, unlike Vue 2 which required a single root element.


&nbsp;</br>
Example of a <template> in a Vue 3 Component:

``` js
<template>
  <div>
    <h1>{{ title }}</h1>
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Hey, my component is in Vue 3",
      description: "Vue 3 allows multiple root elements!"
    };
  }
};
</script>

<style scoped>
h1 {
  color: blue;
}
</style>
```

