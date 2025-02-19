


#### Vue has a set of built-in attributes.

These are: 
| Attribute |	Description |
| ------ | ------ |
| is	| Refers to the current active dynamic component | 
| key	| Gives a unique value to elements created with v-for | 
| ref | 	Gives a reference to an element in the template so that the element can be manipulated later in the script. | 


#### Is Attribute
The is attribute can be used for three things:

1. Dynamic components: The is attribute is set on the built-in <component> element to create a dynamic component, where the is attribute defines which component should be the active one.

In more detail, the is attribute is bound to a property with v-bind, and the property holds the name of which component that should be the active one. (See the Example above)

2. Replace a native element with a Vue component: is="vue:my-component" is placed on a native HTML element to replace it with a Vue component. (See Example 1)

If we do not use the vue: prefix, it will be interpreted as a customized built-in element, as explained right below here, and the Vue component will not be inserted.

3. Customized built-in element: Customized built-in elements can be written in JavaScript, and the is attribute can be used on an HTML tag to define it as such a customized built-in element. This is not a Vue feature.
