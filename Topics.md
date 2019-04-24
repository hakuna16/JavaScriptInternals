### List of JavaScript Internal Topics

1. Functions in JavaScript

    ````javascript
    function test(){                     function Test(){

    }                                               }
    ````
    What is the difference between these two code.

        *  Being a java guy i can say that first one is a normal method, And the second one is constructor.
           which is also true in case of JS.
    While working in a javaScript community no one will read Test() as a function, they will be calling it as a 
    function constructor.

    We say that Everything in JavaScript is an Object. So why?
    
        *  An object in JS is simply a hashmap with key-value pairs. 
                 ___________________
                | key     |  value  |
                | String  |   (any) |
                |___________________|

        * A key is always a string, and a value can be anything including strings, integers, booleans, functions, other     objects etc.
        * All have a function of creation (its constructor).
        * All INHERIT the members of the prototype-object of its constructor and this is its prototype.

    Example:

        `var obj = {}; // this is not the only way to create an object in JS and add new key-value pairs into it`

        `obj['message'] = 'Hello'; // you can always attach new properties to an object externally`
        `obj.message = 'Hello';`


     