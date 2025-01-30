### Vue CSS binding 


You can use Vue to modify CSS by using v-bind on style and class attributes. Here is explained in more detail how CSS can be changed dynamically with Vue. But first lets look at two examples with in-line styling with v-bind:style and assigning a class with v-bind:class.

&nbsp;</br>
**Inline Styling**</br>
We use v-bind:style to do in-line styling in Vue.

Example</br>
An `<input type="range">` element is used to change the opacity of a `<div>` element with the use of in-line styling.

``` js
<input type="range" v-model="opacityVal">
<div v-bind:style="{ backgroundColor: 'rgba(155,20,20,'+opacityVal+')' }">
  Drag the range input above to change opacity here.
</div>
```

**Assign a Class**</br>
We use v-bind:class to assign a class to an HTML tag in Vue.

Example</br>
Select images of food. Selected food is highlighted with the use of v-bind:class to show what you have selected.

```
<div v-for="(img, index) in images">
  <img v-bind:src="img.url"
       v-on:click="select(index)"
       v-bind:class="{ selClass: img.sel }">
</div>
```

**Other Ways to Assign Classes and Style**<br>
Here are different aspects regarding the use of v-bind:class and v-bind:style that we have not seen before in this tutorial:

- When CSS classes are assigned to an HTML tag with both `class=""` and `v-bind:class=""` Vue merges the classes.
- An object containing one or more classes is assigned with v-bind:class="{}". Inside the object one or more classes might be toggled on or off.
- With in-line styling (v-bind:style) camelCase is preferred when defining a CSS property, but 'kebab-case' can also be used if it is written inside quotes.
- CSS classes can be assigned with arrays / with array notation / syntax

The four points are explained in more detail below.

**1. Vue Merges 'class' And 'v-bind:class'**<br>
In cases when an HTML tag belongs to a class assigned with class="", and is also assigned to a class with v-bind:class="", Vue merges the classes for us.

Example</br>
A `<div>` element belongs to two classes: 'impClass' and 'yelClass'. The 'important' class is set the normal way with the class attribute, and 'yellow' class is set with v-bind:class.

``` js
<div class="impClass" v-bind:class="{yelClass: isYellow}">
  This div belongs to both 'impClass' and 'yelClass'.
</div>
```

**2. Assign More Than One Class With 'v-bind:class'**<br>
When assigning an HTML element to a class with v-bind:class="{}", we can simply use comma to separate and assign multiple classes.

Example</br>
A `<div>` element can belong to both 'impClass' and 'yelClass' classes, depending on the boolean Vue data properties 'isYellow' and 'isImportant'.

``` js
<div v-bind:class="{yelClass: isYellow, impClass: isImportant}">
  This tag can belong to both the 'impClass' and 'yelClass' classes.
</div>
```

**3. Camel case vs kebab case notation with 'v-bind:style'**<br>
When modifying CSS in Vue with in-line styling (v-bind:style), it is recommended to use camel Case notation for the CSS property, but 'kebab-case' can also be used if the CSS property is inside quotes.

&nbsp;<br>
Example</br>
Here, we set CSS properties background-color and font-weight for a `<div>` element in two different ways: the recommended way with camel Case backgroundColor, and the not recommended way with 'kebab-case' in quotes 'font-weight'. Both alternatives work.

``` js
<div v-bind:style="{ backgroundColor: 'lightpink', 'font-weight': 'bolder' }">
  This div tag has pink background and bold text.
</div>
```

&nbsp;<br>
**4. Array Syntax with 'v-bind:class'**<br>
We can use array syntax with v-bind:class to add multiple classes. With array syntax we can use both classes that depend on a Vue property and classes that do not depend on a Vue property.

Example<br>
Here, we set CSS classes 'impClass' and 'yelClass' with array syntax. The class 'impClass' depends on a Vue property isImportant and the class 'yelClass' is always attached to the `<div>` element.

``` js
<div v-bind:class="[{ impClass: isImportant }, 'yelClass' ]">
  This div tag belongs to one or two classes depending on the isImportant property.
</div>
```
