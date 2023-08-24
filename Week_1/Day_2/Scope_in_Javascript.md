### Tips

Global vs Local Scopes
Let's classify two basic levels of scope: global and local.

A globally-scoped variable is available everywhere in the code, whereas a locally-scoped variable would only be available within the function in which it's defined.

To illustrate this, please examine the following code carefully:

```javascript
let myGlobalVar = "global";

const printMyVars = function() {
  let myLocalVar = "local";
  console.log("-- Inside printMyVars --");
  console.log("myLocalVar is:", myLocalVar);
  console.log("myGlobalVar is:", myGlobalVar);
}

printMyVars();

console.log('-- Outside of printMyVars now --');
console.log(myLocalVar);
```

### Scoping Can Overwrite Variables

When a local variable and a global variable have the same name, the local variable takes precedence within its scope. So, within myFunction, myVar is "local". Outside of myFunction, myVar is "global".

```javascript
let myVar = "global";

const myFunction = function() {
  let myVar = "local";

  console.log("inside myFunction, myVar is:", myVar); 
}

myFunction();

console.log("outside myFunction, myVar is:", myVar);  
```

The local variable myVar takes precedence inside myFunction. It would evaluate to "local"
However outside the function the variable myVar behaves as a global variable. It would evaluate to "global"