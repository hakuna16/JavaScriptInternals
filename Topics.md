### List of JavaScript Internal Topics

1.  #### Functions in JavaScript

    ```javascript
    function test() {                                   function Test() {

           }                                                         }
    ```

#### What is the difference between these two code.

        *  Being a java guy i can say that first one is a normal method, And the second one is constructor.
           which is also true in case of JS.

While working in a javaScript community no one will read Test() as a function, they will be calling it as a
function constructor or constructor functions.
These functions are apply using new binding. And this will return `this`

- Whenever we write code as

    ```javascript
    function test() {

    }
    ```

- This will get complied as

    ````javascript
    var test = new Function();
    ````

    The above syntax is called function object declaration syntax.

    This is less efficient than declaring a function with a function expression or function statement and calling it within your code because such functions are parsed with the rest of the code. which means, the body and the arguments will not be passed if we declare like this.

    The global Function object has no methods or properties of its own. However, since it is a function itself, it does inherit some methods and properties through the prototype chain from Function.prototype.

#### We say that Everything in JavaScript is an Object. So why?

An object in JS is simply a hashmap with key-value pairs. (In Memory)

                 ___________________
                | key     |  value  |
                | String  |   (any) |
                |___________________|


A key is always a string, and a value can be anything including strings, integers, booleans, functions, other     objects etc.
    
All have a function of creation (its constructor).
    
All INHERIT the members of the prototype-object of its constructor and this is its prototype.

- Example:

        `var obj = {}; // this is not the only way to create an object in JS and add new key-value pairs into it`

        `obj['message'] = 'Hello'; // you can always attach new properties to an object externally`
        `obj.message = 'Hello';`

#### Prototypes

    The Object.prototype is a property of the Object constructor.
