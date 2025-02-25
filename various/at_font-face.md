### Font-Face

In Vue 3 (or any web project using CSS), @font-face is a CSS rule used to define custom fonts that can be loaded and used in your application. It allows you to specify a font file (e.g., .ttf, .woff, .woff2, etc.) 
and use it anywhere in your Vue components.

**Usage in Vue 3**
You can define @font-face in a global CSS or SCSS file (e.g., styles.css or styles.scss), or inside a Vue single-file component's <style> section.

**Example: Using @font-face in a Global CSS File**

Create or update your global style.css file:

``` js
@font-face {
  font-family: 'CustomFont';
  src: url('@/assets/fonts/CustomFont.woff2') format('woff2'),
       url('@/assets/fonts/CustomFont.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}

body {
  font-family: 'CustomFont', sans-serif;
}
```


**Example: Using @font-face Inside a Vue Component**

If you want to define the font only in a specific component:

``` js
<template>
  <div class="custom-text">Custom font, in Vue 3!</div>
</template>

<style scoped>
@font-face {
  font-family: 'CustomizedFont';
  src: url('@/assets/fonts/CustomFont.woff2') format('woff2');
}

.custom-text {
  font-family: 'CustomizedFont', sans-serif;
}
</style>



```
