+++
date = '2025-01-23T02:19:09+01:00'
draft = false
title = 'Bind() vs Call() vs Apply()'
categories = ['js']
+++

[https://stackoverflow.com/questions/15455009/javascript-call-apply-vs-bind](https://stackoverflow.com/questions/15455009/javascript-call-apply-vs-bind)



They all attach **this** into function (or object) and the difference is in the function invocation (see below).

**call** attaches **this** into function and executes the function immediately:

```
var person = {  
  name: "James Smith",
  hello: function(thing) {
    console.log(this.name + " says hello " + thing);
  }
}

person.hello("world");  // output: "James Smith says hello world"
person.hello.call({ name: "Jim Smith" }, "world"); // output: "Jim Smith says hello world"
```

**bind** attaches this into function and it needs to be invoked separately like this:

```
var person = {  
  name: "James Smith",
  hello: function(thing) {
    console.log(this.name + " says hello " + thing);
  }
}

person.hello("world");  // output: "James Smith says hello world"
var helloFunc = person.hello.bind({ name: "Jim Smith" });
helloFunc("world");  // output: Jim Smith says hello world"
```

or like this:

```
...    
var helloFunc = person.hello.bind({ name: "Jim Smith" }, "world");
helloFunc();  // output: Jim Smith says hello world"
```

**apply** is similar to call except that it takes an array-like object instead of listing the arguments out one at a time:

```
function personContainer() {
  var person = {  
     name: "James Smith",
     hello: function() {
       console.log(this.name + " says hello " + arguments[1]);
     }
  }
  person.hello.apply(person, arguments);
}
personContainer("world", "mars"); // output: "James Smith says hello mars", note: arguments[0] = "world" , arguments[1] = "mars"
```