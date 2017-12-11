### Day 06 - Finishing bitmap lab

* It's first Saturday and day without school. Finally was able to get more than couple hours of sleep. We had a lot of progress on Friday with bitmap assignment. We got it to read, transform and create new bmp. We divvied up weekend task between Jeff, Cameron and myself. I got task with transform test. They were not really complex. Callbacks, modules are finally getting so much clearer now. Still lots to learn.



### Scope and good analogy to it

* Today's reading found this nice analogy about scopes. You may think of Scopes as a series of doors decreasing in size (from biggest to smallest). A short person that fits through the smallest door — **innermost scope** — also fits through any bigger doors — **outer scopes**.
A tall person that gets stuck on the third door, for example, will have access to all previous doors — **outer scopes** — but not any further doors — **inner scopes**.

  * **Example: Scoping**
  ``` JavaScript
  outer = () => {
    let a = 1;
    inner = () => {
      let b = 2;
      innermost = () => {
        let c = 3;
        console.log(a, b, c); // 1, 2, 3
      }
      innermost();
      console.log(a, b); // 1, 2 - "c" is NOT defined
    }
    inner();
    console.log(a); // 1- "b" and "c" is NOT defined
  }
  outer();
  // 1 2 3
  // 1 2
  // 1
  ```

### `this` binding

  * **Example: Hard binding**
  ``` JavaScript
  function foo(something) {
  	console.log( this.a, something );
  	return this.a + something;
  }

  var obj = {
	   a: 2
  };

  var bar = foo.bind( obj );

  var b = bar( 3 ); // 2 3
  console.log( b ); // 5
  ```
  * bind(..) returns a new function that is hard-coded to call the original function with the this context set as you specified.

  Note: As of ES6, the hard-bound function produced by `bind(..)` has a `.name` property that derives from the original target function. For example: `bar = foo.bind(..)` should have a `bar.name` value of `"bound foo"`, which is the function call name that should show up in a stack trace.

  * YDKJS `this` chapter explains as rules how the call-site determines where `this` will point during the execution of a function. Finding call site and inspecting which of these rules applies will point you to `this`.

    * Default
    * Implicit
    * Explicit
    * `new` binding


      1. Is the function called with `new` (`new` binding)? If so, this is the newly constructed object.

        `var bar = new foo()`

      2. Is the function called with `call` or `apply` (explicit binding), even hidden inside a bind hard binding? If so, this is the explicitly specified object.

        `var bar = foo.call( obj2 )`

      3. Is the function called with a context (implicit binding), otherwise known as an owning or containing object? If so, this is that context object.

        `var bar = obj1.foo()`

      4. Otherwise, default the this (default binding). If in strict mode, pick undefined, otherwise pick the global object.

        `var bar = foo()`


**The lexical binding of an arrow-function cannot be overridden (even with new!).**
