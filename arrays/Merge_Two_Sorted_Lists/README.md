Merge Two Sorted Lists

Difficulty: Easy  
Topic: Linked List, Two Pointers  

---

Problem Statement

You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists into one sorted list.  
The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.

---

Approach (Two Pointers)

I solved this problem using a two-pointer approach.

Idea:
- Compare the current nodes of both linked lists
- Attach the node with the smaller value to the merged list
- Move forward in the list from which the node was taken
- Repeat until one list becomes empty
- Attach the remaining nodes of the other list

A dummy node is used to simplify handling the head of the merged list.

---

Example

Input:  
list1 = 1 → 2 → 4  
list2 = 1 → 3 → 4  

Output:  
1 → 1 → 2 → 3 → 4 → 4  

Explanation:  
Nodes are merged in sorted order by comparing values from both lists.

---

Linked List Solution

```js
var mergeTwoLists = function(list1, list2) {
    let dummy = new ListNode(-1);
    let current = dummy;

    while (list1 !== null && list2 !== null) {
        if (list1.val <= list2.val) {
            current.next = list1;
            list1 = list1.next;
        } else {
            current.next = list2;
            list2 = list2.next;
        }
        current = current.next;
    }

    if (list1 !== null) {
        current.next = list1;
    } else {
        current.next = list2;
    }

    return dummy.next;
};
```
