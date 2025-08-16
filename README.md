# 🧼 Remove Nth Node From End of List

🔗 [LeetCode Problem](https://leetcode.com/problems/remove-nth-node-from-end-of-list/submissions/1736907432/)

---

## 🧩 Problem Statement

Given the head of a linked list, remove the `n`th node from the end of the list and return its head.

---

## 🧠 Approach: Two-Pointer Technique

We use a dummy node and two pointers (`fast` and `slow`) to traverse the list in one pass.

---

## 🧪 Example Test Cases
 Input:  head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]

Input:  head = [1], n = 1
Output: []

Input:  head = [1,2], n = 1
Output: [1]

## 📊 Complexity Analysis
Time Complexity: O(L)  # L = length of the linked list
Space Complexity: O(1) # Only pointers used



## ✅ Python Code

```python
class Solution(object):
    def removeNthFromEnd(self, head, n):
        dummy = ListNode(0)
        dummy.next = head
        fast = slow = dummy

        for _ in range(n + 1):
            fast = fast.next

        while fast:
            fast = fast.next
            slow = slow.next

        slow.next = slow.next.next
        return dummy.next
