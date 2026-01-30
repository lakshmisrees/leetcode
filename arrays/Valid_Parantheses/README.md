Valid Parentheses

Difficulty: Easy  
Topic: Stack, Strings  

---

Problem Statement

Given a string s containing just the characters
(, ), {, }, [ and ], determine if the input string is valid.

An input string is valid if:
- Open brackets must be closed by the same type of brackets
- Open brackets must be closed in the correct order
- Every closing bracket has a corresponding opening bracket

---

Approach (Using Stack)

I solved this problem using a stack.

Idea:
- Traverse the string one character at a time
- If the character is an opening bracket, push it into the stack
- If the character is a closing bracket:
  - If the stack is empty, return false
  - Pop the top element from the stack
  - If it does not match the closing bracket, return false
- At the end, if the stack is empty, the string is valid

---

Example

Input:
s = "()[]{}"

Output:
true

Explanation:
Each opening bracket is closed correctly and in the right order.

---

Example

Input:
s = "(]"

Output:
false

Explanation:
The closing bracket does not match the opening bracket.

---

Stack Solution

```js
var isValid = function(s) {
    let stack = [];
    let map = {
        ')': '(',
        '}': '{',
        ']': '['
    };

    for (let char of s) {
        if (char === '(' || char === '{' || char === '[') {
            stack.push(char);
        } else {
            if (stack.length === 0) {
                return false;
            }

            let top = stack.pop();
            if (top !== map[char]) {
                return false;
            }
        }
    }

    return stack.length === 0;
};
