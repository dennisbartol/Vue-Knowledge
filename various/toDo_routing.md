### Routing

Routing in Vue is used to navigate the Vue application, and it happens on the client side (in the browser) without full page reload, which results in a faster user experience.

Routing is a way to navigate, similar to how we have used dynamic components earlier.

With routing we can use the URL address to direct someone to a specific place in our Vue application.


**Navigate Using a Dynamic Component**
To understand routing in Vue, let's first look at an application that uses a dynamic component to switch between two components.

We can switch between the components using buttons:

Example


``` js
App.vue

<template>
  <p>Choose what part of this page you want to see:</p>
  <button @click="activeComp = 'animal-collection'">Animals</button>
  <button @click="activeComp = 'food-items'">Food</button><br>
  <div>
    <component :is="activeComp"></component>
  </div>
</template>

<script>
export default {
  data() {
      return {
        activeComp: ''
      }
    }
}
</script>

<style scoped>
  button {
    padding: 5px;
    margin: 10px;
  }
  div {
    border: dashed black 1px;
    padding: 20px;
    margin: 10px;
    display: inline-block;
  }
</style>
```
