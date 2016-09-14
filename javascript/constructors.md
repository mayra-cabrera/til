### Constructors

*Taken from Eloquent Javascript book* 

Another convenient way to create objects in javascript are through _constructors_

```javascript
function Rabbit(type) {
  this.type = type;
}

var killerRabbit = new Rabbit("killer");
var blackRabbit = new Rabbit("black");
console.log(blackRabbit.type);
// → black
```

Calling a function with `new` keyword in front of it causes it to be treated as a cosntructor, an object created with `new` is said to be an instance of its constructor. Also check is a convention to capitalize names of constructors 

We can take advantage of prototypes, so if we want a function to be available to rabbits created with `Rabbit` constructor, we can simply do this:

```javascript
Rabbit.prototype.speak = function(line) {
  console.log("The " + this.type + " rabbit says '" + line + "'");
};
blackRabbit.speak("Doom...");
// → The black rabbit says 'Doom...'
```
