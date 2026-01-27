# Maximum Subarray

**Difficulty:** Easy  
**Topic:** Arrays, Greedy Algorithm  

---

## 🧠 Problem Statement

Given an integer array `nums`, find the **contiguous subarray** (containing at least one number) which has the **largest sum**, and return that sum.

A subarray must be continuous.

---

## 💡 Approach (Greedy – Kadane’s Algorithm)

I solved this problem using a greedy approach known as **Kadane’s Algorithm**.

### Idea:
- Keep track of the current subarray sum
- At each element, decide whether to:
  - start a new subarray
  - or continue the existing subarray
- Keep updating the maximum sum found so far

This approach works efficiently in a single pass.

---

## 🧪 Example

Input:  
`nums = [-2,1,-3,4,-1,2,1,-5,4]`

Output:  
`6`

Explanation:  
The subarray `[4, -1, 2, 1]` has the largest sum → `6`

---

## Greedy Solution (Kadane’s Algorithm)

```js
var maxSubArray = function(nums) {
    let currentSum = nums[0];
    let maxSum = nums[0];

    for (let i = 1; i < nums.length; i++) {
        currentSum = Math.max(nums[i], currentSum + nums[i]);
        maxSum = Math.max(maxSum, currentSum);
    }

    return maxSum;
};
