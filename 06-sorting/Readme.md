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

## Bubble sort

A sorting algorithm where the largest values bubble up to the top

[https://visualgo.net/en/sorting](https://visualgo.net/en/sorting)

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

<hr />

```javascript
// UNOPTIMIZED VERSION OF BUBBLE SORT
const swap = (arr, idx1, idx2) => {
    [arr[idx1], arr[idx2]] = [arr[idx2], arr[idx1]];
};

function bubbleSort(arr) {

    for (let i = arr.length; i > 0; i--) {
        for (let j = 0; j < i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr, j, j + 1);
            }
    }
}
  return arr;
}

bubbleSort([8,1,2,3,4,5,6,7]);
```


```javascript

// Optimized BubbleSort with noSwaps
const swap = (arr, idx1, idx2) => {
    [arr[idx1], arr[idx2]] = [arr[idx2], arr[idx1]];
};


function bubbleSort(arr){
    var noSwaps;
    for(var i = arr.length; i > 0; i--){
        noSwaps = true;
        for(var j = 0; j < i - 1; j++){
            if(arr[j] > arr[j+1]){
                swap(arr, j, j + 1);
                noSwaps = false;
            }
        }
        if(noSwaps) break;
    }
    return arr;
}

bubbleSort([8,1,2,3,4,5,6,7]);
```

O(n^2)

<hr />