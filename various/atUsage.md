###  @ Usage in Vue3.

In Vue 3, the @ character is used as a shorthand for various directives and features. Here are all the ways it is commonly used:

Event Binding (v-on)

@click="handleClick" → shorthand for v-on:click="handleClick"

@mouseover="handleMouseover" → shorthand for v-on:mouseover="handleMouseover"

Supports event modifiers like @click.stop, @keydown.enter, etc.


Dynamic Event Binding

@[eventName]="handleEvent" → dynamically binds an event using a variable.


Custom Event Emission ($emit)

@custom-event="handleCustomEvent" → listens for custom events emitted by a child component.


Modifiers for Event Handling

@submit.prevent="handleSubmit" → prevents default behavior.

@click.stop="handleClick" → stops event propagation.

@keyup.enter="handleEnterKey" → listens for Enter key presses.

@click.once="handleClickOnce" → ensures the event fires only once.


Inline Event Handling

@click="count++" → executes inline expressions.

