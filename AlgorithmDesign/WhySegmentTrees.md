# Why Segment Trees

## Scenario 
Computing the 1) sum of range query & 2) update query

**Example**
```text
nums = [1,3,5,8,9]
```

### Solution
Considering there are 'n' elements & 'k' sum range query

1. Brute Force Approach: 
   1. Compute the sum for every query

   2. Time Complexity for range sum query: O(nk)

2. Efficient Approach: 
   1. Compute prefix sum array

   2. Time Complexity for range sum query: O(k)

    ```text
    nums = [1,3,5,8,9]

    prefixSum = [1,4,9,17,26]
    ```

***When to use Segment Tree***

Whenever the given array is updated, the prefix sum array also needs to be updated, so in efficient prefix sum array approach it takes O(n) time to compute prefix sum array for single update query request.
So, for say 'k' range sum and 'q' update queries

When the **prefix sum approach** approach is used,

```text
Time complexity for range sum query = O(1)
Time Complexity for update query = O(n)
For total queries= O(qn) + O(k)
```
When the **brute force** approach is used,
```text
Time complexity for range sum query = O(n)
Time Complexity for update query = O(1)
For total queries= O(k) + O(qn)
```
When the **segment tree** approach is used,
```text
Time complexity for range sum query = O(logn)
Time Complexity for update query = O(logn)
For total queries= O(klogn) + O(qlogn)
```
Considering the above senario when there is a greater number of update query requests, _segment trees_ are used.
