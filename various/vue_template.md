#### Template

A template in Vue is what we call the HTML part of our Vue application.

The <template> tag will later be used in *.vue files to structure our code in a better way.

It is possible to use template as a configuration option in the Vue instance, and put the HTML code inside.


```js
<div id="app"></div>

<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
<script>
  const app = Vue.createApp({
    template:
      `<h1>{{ message }}</h1>
      <p>This is a second line of HTML code, inside back tick quotes</p>`,
    data() {
      return {
        message: "Hello World!"
      }
    }
  })
app.mount('#app')
</script>

```


#### Single File Components (SFCs)


As you can see in the code example above, also the HTML part of our Vue application can be gathered inside the Vue instance, but this does not make it easier to get an overview in the HTML file.

To get a better overview, to make it easier to handle larger projects, and to get a better development environment, we will now switch to write our Vue code in SFCs, or *.vue files.

All *.vue files only consist of three parts:

- <template> where the HTML content is.

- <script> for our Vue code.

- <style> where we write the CSS styling.



