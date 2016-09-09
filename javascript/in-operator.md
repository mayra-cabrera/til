### In Operator

The binary `in` operator, when applied to a string and an object, returns a Boolean value that indicates whether that object has that property. 

```javascript
var anObject = {left: 1, right: 2};
console.log(anObject.left);
// → 1
delete anObject.left;
console.log(anObject.left);
// → undefined
console.log("left" in anObject);
// → false
console.log("right" in anObject);
// → true
```

What would happen if we set a property to undefined:

```javascript
var anObject = {left: 1, right: undefined};
console.log(anObject.right);
// → undefined
console.log("right" in anObject);
// → true

```
Basically the diference between setting a property to `undefined` and actually deleting is that, in the first case, the object still **has** the property (it just doesn'¡t have an `undefined` value), whereas in the second case the property is no longer present.
