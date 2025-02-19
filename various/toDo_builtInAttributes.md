


#### Vue has a set of built-in attributes.

These are: 
| Attribute |	Description |
| ------ | ------ |
| is	| Refers to the current active dynamic component | 
| key	| Gives a unique value to elements created with v-for | 
| ref | 	Gives a reference to an element in the template so that the element can be manipulated later in the script. | 

&nbsp;</br>
#### Is Attribute
The is attribute can be used for three things:

**1. Dynamic components:** The is attribute is set on the built-in <component> element to create a dynamic component, where the is attribute defines which component should be the active one.

In more detail, the is attribute is bound to a property with v-bind, and the property holds the name of which component that should be the active one. (See the Example above)

**2. Replace a native element with a Vue component:** `is="vue:my-component"` is placed on a native HTML element to replace it with a Vue component. (See Example 1)

If we do not use the vue: prefix, it will be interpreted as a customized built-in element, as explained right below here, and the Vue component will not be inserted.

**3. Customized built-in element:** Customized built-in elements can be written in JavaScript, and the is attribute can be used on an HTML tag to define it as such a customized built-in element. This is not a Vue feature.


&nbsp;<br>
#### Key Attribute 

The key attribute is used with the v-for directive so that Vue can tell the elements apart properly.

Vue optimizes performance by reusing elements. So when elements are created from an array with v-for, if the key attribute is NOT used, element properties can be mixed when the array gets modified.


&nbsp;<br>
#### Ref Attribute 

The ref attribute is used to mark elements in `<template>`, so that they can be accessed from the `$refs` object inside `<script>`.

We can use the ref attribute and the `$refs` object in Vue as an alternative to methods in plain JavaScript like getElementById() or querySelector().

If HTML elements created with v-for have the ref attribute, the resulting DOM elements will be added to the $refs object as an array, like demonstrated in this example:


