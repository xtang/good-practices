- Empty Array(see [here](http://stackoverflow.com/questions/1232040/how-to-empty-an-array-in-javascript))
  ```javascript
  // better
  A.length = 0;

  // good
  A = [];

  // bad
  A.splice(0, A.length);
  ```

- Convert string to boolean(see [here](http://stackoverflow.com/questions/263965/how-can-i-convert-a-string-to-boolean-in-javascript))
  ```javascript
  // Right
  A = (myValue === 'true');

  // Wrong
  A = Boolean('false'); // return true
  A = !!'false'; // also return true

- reverse().forEach() vs. reversal iteration(see [here](http://jsperf.com/reverse-foreach-vs-reversal-iteration))
  ```javascript
  // fastest
  pole.each(function(pole) {}, pole.length - 1, 0);

  // slow
  pole.reverse().forEach(function(pole) {});
  ```
