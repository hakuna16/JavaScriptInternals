#### Objects inJavaScript.

Each data property (object property that store data) has not only the name-value pair, but also 3 attributes (the three attributes are set to true by default):

- Configurable Attribute: Specifies whether the property can be deleted or changed.
- Enumerable: Specifies whether the property can be returned in a for/in loop.
- Writable: Specifies whether the property can be changed.

##### Creating Objects

These are the two common ways to create objects:

1. Object Literals

   ```javascript
   var mango = {
     color: "yellow",
     shape: "round",
     sweetness: 8,
     howSweetAmI: function() {
       console.log("Hmm Hmm Good");
     }
   };
   ```

2. Object Constructor

   ```javascript
   var mango = new Object();
   mango.color = "yellow";
   mango.shape = "round";
   mango.sweetness = 8;

   mango.howSweetAmI = function() {
     console.log("Hmm Hmm Good");
   };
   ```

   The second most common way to create objects is with Object constructor.
   A constructor is a function used for initializing new objects, and you use the new keyword to call the constructor.

The problem here is for each type object(of same type) we have to add the same method again and again.
Also the modification which is needed will be repeated.

So for solving this we have came with the two approach:

1. Constructor Pattern for Creating Objects

```javascript
function Fruit(theColor, theSweetness, theFruitName, theNativeToLand) {
  this.color = theColor;
  this.sweetness = theSweetness;
  this.fruitName = theFruitName;

  this.showName = function() {
    console.log("This is a " + this.fruitName);
  };
}
```

This is a kind of `Factory Design Pattern technique` used.

2. Prototype Pattern for Creating Objects

```javascript
function Fruit() {}
Fruit.prototype.color = "Yellow";
Fruit.prototype.sweetness = 7;
Fruit.prototype.fruitName = "Generic Fruit";

Fruit.prototype.showName = function() {
  console.log("This is a " + this.fruitName);
};
```

- And this is how we call the Fruit () constructor in this prototype pattern:

```javascript
var mangoFruit = new Fruit();
mangoFruit.showName();
```

Internally what happens is

- When we use `Object.prototype` it will create a prototype chain, which will be pointing to `__protp__` of the Object.
- So when we create a new Object it wont create a copy of that, it will only just point to the same `Object.__proto__`.

Example

```
P1
  - x
  - y
  - __proto__
```

Which will pointing to the Object.prototype.
if we use prototype pattern ,so while we create a different object we can see the common method in the same `__proto__`

Example

```
P2
  - x
  - y
  - __proto__  (Object)
    - show()
```

#### So why this is useful?

If we use the prototype pattern, we can make use of the things like.

    - sharing the function or variables across all the common object.
    - You can modify with your custom code on top of some liabrary.
    - This way we can achive inheritance and polymorphism in javascript

#### what is **proto** ?

So this is a reffrence to property of a `prototype` up the prototype chain, which points to `Object.prototype`


