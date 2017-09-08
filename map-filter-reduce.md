
# Map Filter Reduce
## Map

Looping through an array and add a number to each item in the numbers array.

```javascript
// => numbers: [1,2,3,4,5,6,7,8,9,10,11]
var addOne = numbers.map((n) => n+1);  

// => addOne: [2,3,4,5,6,7,8,9,10,11,12]

```

## Filter

like map(), filter() returns a new array with copies of the items that match the filter.

```javascript
// => addOne: [2,3,4,5,6,7,8,9,10,11,12]

var oddOneOut = addOne.filter((n) => n % 3 === 0);  
// => oddOneOut: [3,6,9,12]

````

## Reduce

use Reduce to aggregate data in a list

```javascript
// => oddOneOut: [3,6,9,12]

var reduceOutput = oddOneOut.reduce((grp,num) => {
  let key = num / 6 == 0 ? 'By Mark Six' : 'None';
  grp[key].push(num);
  return grp;
},{});

// =>Reduce Output : {'By Mark Six':[6,12], 'None': [3,9]}

````

