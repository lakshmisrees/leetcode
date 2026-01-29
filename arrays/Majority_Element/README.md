Majority Element

Difficulty: Easy  
Topic: Arrays, Greedy  

---

Problem Statement

Given an array nums of size n, return the majority element.

The majority element is the element that appears more than floor(n / 2) times.  
You may assume that the majority element always exists in the array.

---

Approach (Boyer-Moore Voting Algorithm)

I solved this problem using a greedy approach.

Idea:
- Maintain a candidate element and a count
- If count becomes 0, assign the current element as the new candidate
- If the current element matches the candidate, increment count
- Otherwise, decrement count

The element remaining as the candidate at the end is the majority element.

---

Example

Input:  
nums = [2, 2, 1, 1, 1, 2, 2]

Output:  
2

Explanation:  
The number 2 appears more than floor(n / 2) times.

---

Greedy Solution

```js
var majorityElement = function(nums) {
    let candidate = null;
    let count = 0;

    for (let num of nums) {
        if (count === 0) {
            candidate = num;
        }

        if (num === candidate) {
            count++;
        } else {
            count--;
        }
    }

    return candidate;
};
```
