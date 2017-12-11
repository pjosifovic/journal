### Second week at CodeFellows

* We survived first week, got the sleeping schedule synced with school and studying. This week we're going to dive in servers and building our own TCP and HTTP servers. At the end of the week we will touch on RESTful API and implementing databases to our project. Last Friday we're learnign about Big 0 and data structures and this Friday we will expand that knowledge and dig into doubly linked lists as well as stacks and queues.

## Winston

* At the first encounter I was really happy that we started using Winston because we could store our logs at one file but later, especially during HTTP server lab - I was having issues debugging and logging. It's a great tool, I'm sure when you implement log reading system it will be really useful.

## Promises

* Mid week we got introduced with Promises - industry's way of solving callback hell. At least till ES7 comes out and async and await take their spot. Promises give us a way to handle asynchronous processing in a more synchronous fashion. They represent a value that we can handle at some point in the future. Unlike callbacks, they are objects.

This is how we create new Promise.

  ``` JavaScript
  var p = new Promise(function(resolve, reject) {  
     if (/* condition */) {
        resolve(/* value */);  // fulfilled successfully
     }
     else {
        reject(/* reason */);  // error, rejected
     }
  });
  ```
To consume the Promise - meaning we want to process the Promises value once fulfilled - we attach a handler to the Promise using it's `.then()` method. This method takes a function that will be passed the resolved value of the Promise once it is fulfilled. `.then()` can be chained.

Promise `.catch()`, which takes a single handler to be called when a promise is rejected. You should use `.catch()` for handling errors, rather than `.then(null, fn)`. Using `.catch()` is more explicit and idiomatic; and when chaining you can have a single `.catch()` at the end of the chain to handle any rejection or thrown exceptions from either the original promise or any of it's handlers.

## Thursday storage

* Thursday was the first day this week where I finally got some time to catch up lab assignments and readings. I feel like first three days labs were not necessarily hard but retyping all lectures code was time consuming. Definitely, i was pulling some long hours and finishing my labs around midnight. I've really enjoyed Thursday's lab as we're getting closer to **express** and **mongodb**.

## Friday data structures

* This week we learned about doubly linked list. Which is a lot like single linked list but in addition dll have a property that point to previous node in the list. Talked about binary-search and how use can implement them in our algorithms. We used binary search to look for an item through our presorted list. Finding first, last and middle index for the array and simply eliminating items based on their position and relation with entered id parameter.

Then we touched on different data structures that will serve as a collection of elements. Talked about stacks and queues. Best analogy for stack data structure is to think about stack of plates. Last plate that was put on a stack will be the first one to be use - this is LIFO(last in, first out). Analogy for queues would be a waiting line for a show. The person that came the earliest to wait in line will be the first person to go in - this is FIFO (first in, first out).

Simple dLL constructor would look like this:

```JavaScript
class DoublyLinkedList {

  constructor(value){
    this.value = value;
    this.next = null;
    this.previous = null;
  }

  append(node){
    if(!(node instanceof DoublyLinkedList))
      throw new TypeError('<node> should be an instance of DoublyLinkedList');

    if(!this.next){
      this.next = node;
      node.previous = this;
    }
    else
      this.next.append(node);

    return this;
  }
}
```

Binary search from labs:


```JavaScript
let binarySearch = (sortedArray, id) => {
  if(typeof id !== 'number'){
    throw new TypeError('id has to be a number');
  }

  let lowIndex = 0;
  let highIndex = sortedArray.length - 1;

  let steps = 0;

  while(lowIndex <= highIndex){
    steps++;
    console.log(`Number of steps so far: ${steps}`);

    let middleIndex = Math.floor((lowIndex + highIndex) / 2);
    let elementFound = sortedArray[middleIndex];
    let elementFoundId = sortedArray[middleIndex].id;

    if(elementFoundId < id){
      lowIndex = middleIndex + 1;
    } else if (elementFoundId > id) {
      highIndex = middleIndex - 1;
    } else{
      return elementFound;
    }
  }
  return -1;
};
```
