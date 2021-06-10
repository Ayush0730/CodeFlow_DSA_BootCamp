## Mentor's LinkedIn - https://www.linkedin.com/in/vivekgiitkgp/

## Topic - Searching and Sorting Algorithms

Website to visualize sorting Algorithms [Visulago](https://visualgo.net/en/sorting)

### Sorting Algorithms

* Bubble
* Selection 
* Insertion
* Merge
* Quick
* Counting
* Radix
* Heap
* Bucket

### Searching Algorithms

* Linear Search - O(n)
* Binary Search - O(log(n))
* Ternary Search

#### Questions

1. Search an element X in the array
    - Use basic binary search

2. [Find index of first 1 in an array containing only zeros](https://www.geeksforgeeks.org/find-index-first-1-sorted-array-0s-1s/)

- Arr = [0,0,0,1,1,1,1,1,1,1]
- Ans -> 3 

```
int lo = 0, hi = n-1, ans = n;
while(lo <= hi){
    int mid = (lo + hi)/2;
    if(arr[mid] == 1){
        ans = mid;
        hi = mid - 1;
    }else{
        lo = mid + 1;
    }
}
```


## Monotone Space

#### Converting to monotone space:

- lower_bound(arr, x) => return smallest element greater than or equal to x
- if x = 11 and arr = [2, 3, 5, 7, 8, 9, 12, 16]
- It will return index of 12 (6)
- Monotone function will convert input to 0s and 1s [0, 0, 0, 0, 1, 1, 1, 1] (Similar to this)
- to convert our given array to monotone space, we will use monotone function, i.e
- f(x){ return(arr[i] >= x? 1:0) }

3. Rotated Array (Find the number of times, the array is rotated)

- Arr = [5, 6, 10, 11] => 0 times rotated
- Arr = [10, 11, 1, 5, 8]] => 3 times rotated
// Cannot be solved using binary search if array can contain duplicate elements

4. DIY - [Search in rotated sorted array](https://leetcode.com/problems/search-in-rotated-sorted-array/)