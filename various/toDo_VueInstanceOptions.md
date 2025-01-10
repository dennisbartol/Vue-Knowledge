### Vue Instance Options

=> ! Add a table 

Options in Vue are the different options available to us on the Vue instance when using the Options API.


|Option	 | Description|
| ----| ----------------- |
|data	 | contains the data properties we set up and their initial values|

| ----| ----------------- |
| methods | 	
contains the methods we write | 

| computed | 
contains the computed properties we make, that are used as data properties, but are written like functions with a return and no arguments, and gets called whenever a dependency is changed. | 

| watch	| 
contains the watchers we make, which are like functions that get called whenever a data property with the same name is changed. | 

| props	| contains the props of a component, that are used as custom attributes by the parent component | 

| emits | contains the emits of a component, the custom events a component emits to its parent component |  

| expose | contains a list of public properties. Properties that are not exposed, are kept private to the component | 






#################################

|Option	 | Description|
|data	 |
contains the data properties we set up and their initial values|

methods	
contains the methods we write

computed
	contains the computed properties we make, that are used as data properties, but are written like functions with a return and no arguments, and gets called whenever a dependency is changed

watch	
contains the watchers we make, which are like functions that get called whenever a data property with the same name is changed

props	contains the props of a component, that are used as custom attributes by the parent component

emits	contains the emits of a component, the custom events a component emits to its parent component

expose	contains a list of public properties. Properties that are not exposed, are kept private to the component
