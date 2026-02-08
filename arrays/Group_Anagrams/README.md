# Group Anagrams

**Difficulty:** Medium  
**Topic:** Arrays, Hashing, Strings  

---

## 🧠 Problem Statement

Given an array of strings `strs`, group the anagrams together.

You can return the answer in any order.

Two strings are anagrams if they contain the same characters with the same frequencies, but possibly in a different order.

---

## 💡 Approach (Hash Map + Sorting)

I solved this problem using a **Hash Map**.

### Idea:
- Anagrams become identical when their characters are sorted
- Use the sorted string as a **key** in a hash map
- Group all original strings that share the same sorted key

This ensures all anagrams are placed in the same group.

---

## 🧪 Example

Input:  
`strs = ["eat","tea","tan","ate","nat","bat"]`

Output:  
`[["eat","tea","ate"],["tan","nat"],["bat"]]`

Explanation:  
- "eat", "tea", and "ate" are anagrams  
- "tan" and "nat" are anagrams  
- "bat" has no anagram pair  

---

## 🧩 JavaScript Solution

```js
var groupAnagrams = function(strs) {
    const map = {};

    for (let s of strs) {
        const key = s.split("").sort().join("");

        if (!map[key]) {
            map[key] = [];
        }
        map[key].push(s);
    }

    return Object.values(map);
};
