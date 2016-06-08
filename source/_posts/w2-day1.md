---
title: Day 6 is the beginning of second week
tags: 
- during-bootcamp
- modules
comments: true
date: 2016-06-06
---

Never fully understood the importance of Sunday until now... After an incredibly busy and intense week, Sunday came like a pouring rain after years of drought. Feeling refreshed and ready for the rest of the week! 

Scopes, Closures, Modules Intro
-----------------------
* `var` creates a local variable; no `var` --> changes variables
* `module`: is used to return an interface with hidden data
*  return a function, so we can return multiple objects that represent API, advantage: we can keep local variables, without polluting global namespace. 
* The module pattern is when you enclose a set of data and functionality in an outer scope that returns a "public API" for using the internal stuff.
* Modules are all about encapsulating (aka hiding) details and behavior inside a scope, and exposing a more limited set of functionality as an "API" (in this case, just a collection of methods).
* Encapsulation: the idea of the least privileged. Make things private and expose them if they need to be public
* Modules as a code organization pattern reduce the chances of naming collisions. 
* Modules: 1) an outer wrapping function that gets executed. It doesn't need to be an IIFE, but it has to be an outer function 2) must be one or more functions returned from that outer function call so the inner function(s) that have a closure over inner private scope. In other words, it returns at least one inner function with closure over the inner details


* Class module pattern: 
```
// revealing module pattern (Class module pattern)
// stack 'class' 

var stack = function(){
	var storage = [];
	return {
		push: function
		pop: function
	}
}

//maintain the integrity of stack, keeping variables private 
stack.push(10);
stack.pop();
stack.storage // undefined
```

* Modified Module pattern

```
var foo = (function(){
	var publicAPI = {
		bar: function(){
			publicAPI.baz();
		},
		baz: function() {
			console.log('baz');
		}
	};
	return publicAPI;
})();
foo.bar();

```

* Browsify --> get rid of global scope. In-browser JS has a global scope; in Node.js, every file has its own scope. 


Lexical Scope, Nested Scope, Block Scope:
---------------
Below is my study notes, read more at <a href="https://github.com/getify/You-Dont-Know-JS" target="_blank">You Don't Know JS</a>.

* Lexical scope is set when the function is created
* Lexical scope rules are determined statically at compile-time. Anything that happens after compilation, during execution, is dynamic at run-time. This distinction is important because it helps us understand the difference between normal variables, which behave lexically, and the this binding, which behaves dynamically.
* Declarations come in two forms: variable declarations and function declarations. The compiler will look for any of these declarations, and wherever it finds them, it will register them into the appropriate scopes.
* A commonly used term "hoisting" refers to the process of finding declarations and assigning them to their owning scopes. Hoisting isn't real, it's just a metaphor for understanding the compiler and scopes. Hoisting describes moving (aka "hoisting") all declarations to the top of their respective scopes. 
* The compiler handles all declarations before our code is executed. Hoisting is done in the compilation phase
* `var a = 2;`: Compiler declares a variable (if not previously declared in the current scope), and second, when executing, Engine looks up the variable in Scope and assigns to it, if found.
*  LHS and RHS meaning "left/right-hand side of an assignment" doesn't necessarily literally mean "left/right side of the = assignment operator". There are several other ways that assignments happen, and so it's better to conceptually think about it as: "who's the target of the assignment (LHS)" and "who's the source of the assignment (RHS)".
* Unfulfilled RHS references result in ReferenceErrors being thrown. Unfulfilled LHS references result in an automatic, implicitly-created global of that name (if not in "Strict Mode" [^note-strictmode]), or a ReferenceError (if in "Strict Mode" [^note-strictmode]).

```
function foo(a) {
    var b = a;
    return a + b;
}

var c = foo( 2 );

// Identify all the LHS look-ups (there are 3!).
// c = .., a = 2 (implicit param assignment) and b = ..
// Identify all the RHS look-ups (there are 4!).
// foo(2.., = a;, a + .. and .. + b
// https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20&%20closures/ch1.md#understanding-scope
```

*  The first traditional phase of a standard language compiler is called lexing (aka, tokenizing).
*  Scope look-up stops once it finds the first match. The same identifier name can be specified at multiple layers of nested scope, which is called "shadowing" (the inner identifier "shadows" the outer identifier). Regardless of shadowing, scope look-up always starts at the innermost scope being executed at the time, and works its way outward/upward until the first match, and stops.
* Leakage of global variable: 

```
function baz(foo) {
	bam = 'create bam for me in global scope';
}
// LHR of bam cannot be found on the global scope, so global scope will create it (trying to be helpful?)
```

* Compilation phase: register all variables in their own scopes 
* In non-strict mode, `reference error` results in unfulfilled or undeclared `RHS` reference 

IIFE
-------------
* IIFEs are functions that are not declared but instead appear as expressions, and then are immediately invoked. This is a convenient way to create some scope inside another scope. ES6 lets us do similar things with { .. } blocks and let.

Let
-------------
* The let keyword attaches the variable declaration to the scope of whatever block (commonly a { .. } pair) it's contained in.

```
var foo = true;

if (foo) {
    { // <-- explicit block
        let bar = foo * 2;
        bar = something( bar );
        console.log( bar );
    }
}

console.log( bar ); // ReferenceError

```
* We can create an arbitrary block for let to bind to by simply including a { .. } pair anywhere a statement is valid grammar. 

```
{
   console.log( bar ); // ReferenceError!
   let bar = 2;
}
```

* declarations made with let will not hoist to the entire scope of the block they appear in. Such declarations will not observably "exist" in the block until the declaration statement.


Closure
---------
* Closure is how a function remembers and retains access to any outer lexical variables even when that function is executed in a different scope.
* In other words: Closure is when a function remembers its lexical scope even when the outside function has finished executed and returned.

```
function setupEvents(elems) {
   var appName = "Cool Stuff";

   for (var i=0; i<elems.length; i++) {
      (function(i){  // <-- new `i` for each iteration
         elems[i].addEventListener( "click", function(){
            console.log( appName + ": " + i );
         } );
      })(i);  // <-- assigns current `i` value to per-iteration `i`
   }
}
// We want a scope for each iteration

```

```
// more complex
function setupEvents(elems) {
   var appName = "Cool Stuff";

   for (var i=0; i<elems.length; i++) {
      let j = i;  // <-- new `j` for each iteration with current `i` value
      elems[i].addEventListener( "click", function(){
         console.log( appName + ": " + j );
      } );
   }
}
```
```
// simpler
function setupEvents(elems) {
   var appName = "Cool Stuff";

   for (let i=0; i<elems.length; i++) {  // <-- new `i` for each iteration
      elems[i].addEventListener( "click", function(){
         console.log( appName + ": " + i );
      } );
   }
}

```
```
var fn;

for (var i = 0; i < 5; i++) {
   let j = i * 2;
   if (j < 7) {
      fn = function() {
         console.log( i, j );
      };
   }
}

fn();
// output: 5 6
```
* Question: is it a closure?

```
var foo = (function(){
  var o = {bar:'bar'}
  return {obj:o};
})();
console.log(foo.obj.bar);

```
Answer: no, by definition, this is object reference, but there is no function keeping a reference to its scope


this
______

* If strict mode is in effect, the global object is not eligible for the default binding, so the this is instead set to undefined.

```
function foo() {
    "use strict";

    console.log( this.a );
}

var a = 2;

foo(); // TypeError: `this` is `undefined`
```

