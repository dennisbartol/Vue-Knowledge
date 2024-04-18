<h4>VueX</h4>

Vuex is a state management pattern and library for Vue.js applications. It serves as a centralized store for all the components in an application, allowing them to access and modify the application's state in a predictable and consistent way.

Here's an overview of Vuex and its key concepts:

<b>1. State:</b> Vuex manages the state of a Vue.js application. The state is typically represented as a JavaScript object that contains data shared among multiple components.
  
<b>2. Getters:</b> Getters are functions in Vuex that allow components to retrieve and compute derived state from the Vuex store. They are useful for accessing specific pieces of state or performing computations on the state.

<b>3. Mutations:</b> Mutations are synchronous functions that are responsible for modifying the state in the Vuex store. They are the only way to change the state in a Vuex store, ensuring that state changes are explicit and predictable.

<b>4. Actions:</b> Actions are asynchronous functions that are used to perform side effects, such as making API calls or asynchronous operations, and then committing mutations to modify the state. Actions are typically called from components and are responsible for handling complex logic before committing mutations.
  
<b>5. Modules:</b> Vuex allows developers to organize their store into modules, each of which can have its own state, getters, mutations, actions, and even nested modules. This helps manage large-scale applications by dividing the store into smaller, manageable pieces.

Vuex is commonly used in Vue.js applications, especially those with complex state management needs, such as applications with multiple components that need to share and synchronize state. By centralizing the state management logic in a Vuex store, developers can maintain a clear and predictable data flow throughout their applications.


<b>=> Vuex v.5 has been renamed into Pinia</b>
See - https://vuex.vuejs.org/
