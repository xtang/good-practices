- Empty Array(see [here](http://stackoverflow.com/questions/1232040/how-to-empty-an-array-in-javascript))
```javascript
// better
A.length = 0

// good
A = []

// bad
A.splice(0, A.length)
```
