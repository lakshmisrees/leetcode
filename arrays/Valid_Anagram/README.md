# Valid Anagram

**Difficulty:** Easy  
**Topic:** Strings, Hashing  

---

## 🧠 Problem Statement

Given two strings `s` and `t`, return `true` if `t` is an **anagram** of `s`, and `false` otherwise.

An **anagram** is formed by rearranging the letters of another string using **all original characters exactly once**.

---

## 💡 Approach (Hash Map / Frequency Count)

I solved this problem using a **frequency count (hash map)** approach.

### Idea:
- If the lengths of both strings are different, they cannot be anagrams
- Count the frequency of each character in string `s`
- Reduce the count using characters from string `t`
- If any character count becomes invalid, return `false`
- If all checks pass, return `true`

---

## 🧪 Example

### Example 1  
Input:  
`s = "anagram", t = "nagaram"`

Output:  
`true`

---

### Example 2  
Input:  
`s = "rat", t = "car"`

Output:  
`false`

---

## Hashing Solution

```js
var isAnagram = function(s, t) {
    if (s.length !== t.length) return false;

    let count = {};

    for (let char of s) {
        count[char] = (count[char] || 0) + 1;
    }

    for (let char of t) {
        if (!count[char]) return false;
        count[char]--;
    }

    return true;
};
