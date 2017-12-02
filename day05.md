### Class 04 - Bitmap and buffers

* Today in lecture we were introduced into terms like `encoding` and `decoding`. We use encoding to turn string, integers into "ones and zeros" and decoding to turn it back into human readable form.

  * we can use different types of encoding like decimal(base10), binary(base2) or hex(base16).

* We had our first whiteboard challenge that we did on paper. Task was to pull min, max and avg from array without using array methods. I re-stated the problem but I didn't focus on egde cases like what if array has only one item etc. Definitely whiteboarding is one task that I'll have to focus more as well as codewars. Just solving simple tasks; find min, max, avg, looping thru array etc to build those solving muscles. Practice makes perfect. 



### Class 05 - Big O

* Introducing the concept of `class` in ES6. Used for constructor functions. No more need to add prototype.

  * **Example:**
  ``` JavaScript
  class Person {
    constructor(name, dob){
      this.name = name;
      this._year = year;
    }
    get make(){
      return this.name;
    }
    get year(){
      return this._year;
    }
    toString(){
      return `${this.name}${this.dob}`
    }
  }
  let person = new Person('chuck bundy', 2011);

  console.log(person.name); // chuck bundy
  console.log(person.toString()) // chuck bundy 2011
  ```

  * **Example: Whiteboard challange class04**
  ``` JavaScript
  let biggestSecond = (array) => {
    if(!Array.isArray(array))
      return console.error('Array is not an array');

    if(array.lenght === 0)
      return null;

    if(array.lenght < 2)
      return null;

    let biggest = Math.max(array[0], array[1]);
    let second = Math.min(array[0], array[1]);

    for(int i = 2; i < array.length; i++) {
      if(array[i] >= biggest) {
        second = biggest;
        biggest = array[i];
      } else if(array[i] > second) {
          second = array[i];
      }
    }
    return {'biggest': biggest,'second': second};
  }


  ```
