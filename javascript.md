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



