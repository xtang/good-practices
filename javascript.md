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
  // prepare code: borrowed from [jsperf](http://jsperf.com/reverse-foreach-vs-reversal-iteration)
  Array.prototype.each = function(callback, from, to) {
    var length = this.length;
    if(callback instanceof Function === false ||
       length === 0) return this;

    if(from === undefined)
       from  = 0;
    if(to === undefined)
       to  = from < 0 && -from < length?0:length - 1;

    if(from < 0)
      from = -from >= length?0:length + from;
    else if(from > length - 1)
      from = length - 1;

    if(to < 0)
       to = -to >= length?(from > 0?0:length - 1):length + to;
    else if(to > length - 1)
      to = length - 1;

    if(from > to) do {
      if(callback.call(this, this[from], from) === false) return false;
    } while(from-- !== to) else if(from < to) do {
      if(callback.call(this, this[from], from) === false) return false;
    } while(from++ !== to) else if(callback.call(this, this[from], from) === false)
    return false; return this;
  };

  // fastest
  pole.each(function(pole) {}, pole.length - 1, 0);

  // slow
  pole.reverse().forEach(function(pole) {});
  ```
