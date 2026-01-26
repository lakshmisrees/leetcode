# Two Sum

**Difficulty:** Easy  
**Topic:** Arrays, Brute Force  

---

## 🧠 Problem Statement

Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to `target`.

- Each input has exactly one solution
- You may not use the same element twice
- The order of indices does not matter

---

## 💡 Approach (Brute Force)

I solved this problem using a brute force approach.

### Idea:
- Check every possible pair of elements
- If their sum equals the target, return their indices

This works because the problem guarantees exactly one solution.

---

## 🧪 Example

Input: nums = [2,7,11,15], target = 9
Output: [0,1]

---

## Brute Force

```js
var twoSum = function(nums, target) {
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] === target) {
                return [i, j];
            }
        }
    }
};