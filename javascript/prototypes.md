### Prototypes

*Taken from Eloquent Javascript*

A prototype is another object that is used as a **fallback** source of properties. The great ancestral prototype is `Object.prototype`, it provides a few methods that show up in all objects, such as `toString`. 

```javascript
console.log(Object.getPrototypeOf({}) ==
            Object.prototype);
// → true
console.log(Object.getPrototypeOf(Object.prototype));
// → null
```

Many objects don't directlly have `Object.prototype` as their prototype, but instead have another object: Functions derive from `Functions.prototype` and arrays derive from `Array.prototype`, if you want to know the prototype of an object, you can call `Object.getPrototypeOf`.

You can also use `Object.create` to create an object with a specific prototype: 

```javascript
var protoRabbit = {
  speak: function(line) {
    console.log("The " + this.type + " rabbit says '" +
                line + "'");
  }
};
var killerRabbit = Object.create(protoRabbit);
killerRabbit.type = "killer";
killerRabbit.speak("SKREEEE!");
```

In the former example the proto rabbit acts as a container for the properties that are shared by all rabbits :D 
