### V-Bind explained


A basic Vue setup consists of a Vue instance and that we can access it from the ```<div id="app">``` tag with {{ }} or the v-bind directive.

What is the v-bind directive in more detail? 

The v-bind directive lets us bind an HTML attribute to data in the Vue instance. This makes it easy to change the attribute value dynamically.

```js
<div v-bind:[attribute]="[Vue data]"></div>
```
Example

The src attribute value of an <img> tag is taken from the Vue instance data property 'url':
```
<img v-bind:src="url">
```

**CSS Binding**
We can use the v-bind directive to do in-line styling and modify classes dynamically. We will show you briefly how to do that in this section, and later in this tutorial, on the CSS Binding page, we will explain this in more detail.

Bind style<br>
In-line styling with Vue is done by binding the style attribute to Vue with v-bind.

As a value to the v-bind directive, we can write a JavaScript object with the CSS property and value:

Example<br>
The font size depends on the Vue data property 'size'.

```js
<div v-bind:style="{ fontSize: size }">
  Text example
</div>
```

&nbsp;<br>
We can also separate the font size number value from the font size unit if we want to, like this:

Example<br>
The font size number value is stored the Vue data property 'size'.

```js
<div v-bind:style="{ fontSize: size + 'px' }">
  Text example
</div>
```

&nbsp;<br>
We could also write the CSS property name with CSS syntax (kebab-case) in hyphens, but it is not recommended:

Example<br>
The CSS property fontSize is referred to as 'font-size'.

```js
<div v-bind:style="{ 'font-size': size + 'px' }">
  Text example
</div>
```

Example<br>
The background color depends on the 'bgVal' data property value inside the Vue instance.


```js
<div v-bind:style="{ backgroundColor: 'hsl('+bgVal+',80%,80%)' }">
  Notice the background color on this div tag.
</div>
```


/
/
/
/
/
/


**Shorthand for v-bind**
The shorthand for 'v-bind:' is simply ```':'``` (colon).

Example<br>
Here, we just write ':' instead of 'v-bind:':

```
<div :class="{ impClass: isImportant }">
  The class is set conditionally to change the background color
</div>
```