Valid Palindrome

Difficulty: Easy  
Topic: Strings, Two Pointers  

---

Problem Statement

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward.

Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

---

Approach (Two Pointers)

I solved this problem using the two-pointer technique.

Idea:
- Convert the string to lowercase
- Remove all non-alphanumeric characters
- Use two pointers:
  - One starting from the beginning
  - One starting from the end
- Compare characters while moving pointers inward

If all characters match, the string is a palindrome.

---

Example

Input:  
s = "A man, a plan, a canal: Panama"

Output:  
true

Explanation:  
After cleaning the string → "amanaplanacanalpanama", which reads the same forward and backward.

---

Two Pointer Solution

```js
var isPalindrome = function(s) {
    let cleaned = s.toLowerCase().replace(/[^a-z0-9]/g, "");
    let left = 0;
    let right = cleaned.length - 1;

    while (left < right) {
        if (cleaned[left] !== cleaned[right]) {
            return false;
        }
        left++;
        right--;
    }

    return true;
};
```
