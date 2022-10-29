# Sorting

Rearranging the items in a collection(e.g. an array)

### [15 Sorting Algorithms in 6 Minutes](https://www.youtube.com/watch?v=kPRA0W1kECg)




## Builtin Javascript Sorting Algorithms

```javascript
const arr = [...otherArray];

arr.sort()
```
```javascript
const arr = [...otherArray];

arr.sort((a, b)=> {
    // logic for sorting
})
```
Examples:
```javascript
const  numberCompare = (num1, num2) => {
  return num1 - num2;
}

[ 6, 4, 15, 10 ].sort(numberCompare);
// [ 4, 6, 10, 15 ]
```

```javascript
const compareByLen = (str1, str2) => {
  return str1.length - str2.length;
}

[ "Jason", "Sarah", "Mohsen", "Ali" ]
  .sort(compareByLen);
```

<hr />
Many sorting algorithms involve some type of swapping functionality (e.g. swapping to numbers to put them in order)

```javascript
// ES5
function swap(arr, idx1, idx2) {
  var temp = arr[idx1];
  arr[idx1] = arr[idx2];
  arr[idx2] = temp;
}

// ES2015
const swap = (arr, idx1, idx2) => {
  [arr[idx1],arr[idx2]] = [arr[idx2],arr[idx1]];
}
```