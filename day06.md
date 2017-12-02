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
