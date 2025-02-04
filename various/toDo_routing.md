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
  <button @click="activeComponent = 'animal-collection'">Animals</button>
  <button @click="activeComponent = 'food-items'">Food</button><br>
  <div>
    <component :is="activeComponent"></component>
  </div>
</template>

<script>
export default {
  data() {
      return {
        activeComponent: ''
      }
    }
}
</script>

<style scoped>
  button {
    padding: 4px;
    margin: 11px;
  }
  div {
    border: dotted dodgerblue 1px;
    padding: 18px;
    margin: 10px;
    display: inline-block;
  }
</style>
```


&nbsp;<br>
**From Dynamic Component to Routing**<br>
We build SPAs (Single Page Applications) with Vue, which means that our application only contains one *.html file. And that means we cannot direct people to other *.html files to show them different content on our page.

In the example above, we can navigate between different content on the page, but we cannot give someone else an address to the page so that they come directly to the part about food, but with routing we can do that.

With routing set up appropriately, if you open the Vue application with an extension to the URL address, like "/food-items" for example, you will come directly to the part with the food content.


&nbsp;<br>
**Install The Vue Router Library**<br>
To use routing in Vue on your machine, install the Vue Router library in your project folder using the terminal:

``` js
npm install vue-router@4
```

**Updating main.js**
To use routing we must create a router, and we do that in the main.js file.


``` js
main.js:

import { createApp } from 'vue'
import { createRouter, createWebHistory } from 'vue-router'

import App from './App.vue'
import FoodItems from './components/FoodItems.vue'
import AnimalCollection from './components/AnimalCollection.vue'

const router = createRouter({
    history: createWebHistory(),
    routes: [
        { path: '/animals', component: AnimalCollection },
        { path: '/food', component: FoodItems },
    ]
});

const app = createApp(App)

app.use(router);
app.component('food-items', FoodItems);
app.component('animal-collection', AnimalCollection);

app.mount('#app')


```