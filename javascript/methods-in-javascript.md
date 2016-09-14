### Methods in Javascript

*This was taken from Eloquent Javascript*

Javascript has a wide variety of ways to handle objects, some of them are directly related to classical object-oriented techniques, like methods. Watch the following code:


```javascript
unction speak(line) {
  console.log("The " + this.type + " rabbit says '" + line + "'");
}
var whiteRabbit = {type: "white", speak: speak};
var fatRabbit = {type: "fat", speak: speak};

whiteRabbit.speak("Oh my ears and whiskers, " + "how late it's getting!");
// → The white rabbit says 'Oh my ears and whiskers, how late it's getting!'
fatRabbit.speak("I could sure use a carrot right now.");
// → The fat rabbit says 'I could sure use a carrot right now.'
```

Method `speak` needs to do something with the object it was called on, special variable `this` in its body will point to the object that it was called on. The former can also be written using `call` function

```javascript
speak.apply(fatRabbit, ["Burp!"]);
// → The fat rabbit says 'Burp!'
speak.call({type: "old"}, "Oh my.");
// → The old rabbit says 'Oh my.'
```

The first argument for `call` is used to give a value to `this` (to simulate method calls). Awesome!
