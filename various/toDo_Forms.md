### Vue Forms


Routing in Vue is used to navigate the Vue application, and it happens on the client side (in the browser) without a full page reload, which results in a faster user experience.

Routing is a way to navigate, similar to how we have used dynamic components earlier.

With routing we can use the URL address to direct someone to a specific place in our Vue application.

///
Example



```vue
Aircraft.vue

<template>
    <h1>Aircraft</h1>
    <p>There are a lot of aircraft types.</p>
</template>
```



```vue
Helicopters.vue
<template>
    <h1>Helicopters</h1>
    <p>I want to learn about at least one new helicopter type, every year.</p>
</template>
```

```vue

App.vue
<template>
  <p>Choose what part of this page you want to see:</p>
  <button @click="activeComp = 'animal-collection'">Aircraft</button>
  <button @click="activeComp = 'food-items'">Helicopters</button><br>
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
    padding: 6px;
    margin: 10px;
  }
  div {
    border: dotted #333 1px;
    padding: 18px;
    margin: 10px;
    display: inline-block;
  }
</style>
```

**From Dynamic Component to Routing**

We build SPAs (Single Page Applications) with Vue, which means that our application only contains one *.html file. And that means we cannot direct people to other *.html files to show them different content on our page.

In the example above, we can navigate between different content on the page, but we cannot give someone else an address to the page so that they come directly to the part about food, but with routing we can do that.

With routing set up appropriately, if you open the Vue application with an extension to the URL address, like "/food-items" for example, you will come directly to the part with the food content.

**Install The Vue Router Library**<br>
To use routing in Vue on your machine, install the Vue Router library in your project folder using the terminal:

```
npm install vue-router@
```


&nbsp;<br>
**Update main.js**
To use routing we must create a router, and we do that in the main.js file.
