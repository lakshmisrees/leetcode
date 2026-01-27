# Contains Duplicate

**Difficulty:** Easy  
**Topic:** Arrays, Hashing  

---

## 🧠 Problem Statement

Given an integer array `nums`, return `true` if **any value appears at least twice** in the array, and return `false` if **every element is distinct**.

---

## 💡 Approach (Using Set)

I solved this problem using a **Set**.

### Idea:
- A Set stores only **unique values**
- Traverse the array and check:
  - If the value already exists in the Set → duplicate found
  - Otherwise, add the value to the Set

If a duplicate is found, return `true`.  
If the loop ends, return `false`.

---

## 🧪 Example

Input:  
`nums = [1,2,3,1]`

Output:  
`true`

Explanation:  
The number `1` appears more than once.

---

## Hashing Solution

```js
var containsDuplicate = function(nums) {
    let seen = new Set();

    for (let num of nums) {
        if (seen.has(num)) {
            return true;
        }
        seen.add(num);
    }

    return false;
};
