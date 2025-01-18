### Data 


**Definition and Usage**</br>
The data option is a function that <ins>returns an object with all the data properties inside</ins>.

The object returned by the data function can be accessed with <code>this.$data</code>, and a specific data property 'count' can be accessed with this.$data.count, or simply this.count.

Data properties with a name that starts with $ or _ must be accessed through the <code>this.$data</code> object, they cannot be accessed otherwise.

It is possible to add new data properties after the application has started running, by using this.$data, but it is not recommended.
