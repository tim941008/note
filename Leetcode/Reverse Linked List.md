# 解題紀錄 LeetCode 206

## 題目：Reverse Linked List

## 📙 題目描述

Given the head of a singly linked list, reverse the list, and return the reversed list.

**範例1：**

![image](https://hackmd.io/_uploads/rkBiBfOokg.png)
```txt
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]
```

**範例2：**
![image](https://hackmd.io/_uploads/BkkfIM_i1e.png)

```txt
Input: head = [1,2]
Output: [2,1]
```

**範例3：**

```txt
Input: head = []
Output: []
```

---

## ✒️ 解題思路

可以參考[Reverse SLL](https://hackmd.io/g693lvEYTzO0cUriiC4LtA?view#36-%E5%8F%8D%E8%BD%89%E4%B8%B2%E5%88%97)

## 💻 C 語言解法

```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */
struct ListNode* reverseList(struct ListNode* head) {
    struct ListNode* pre = NULL;
    struct ListNode* cur = head;
    struct ListNode* next;
    while(cur != NULL){
        next = cur->next;
        cur->next = pre;
        pre = cur;
        cur = next;
    }
    return pre;
}

```

---

## 🕛時間複雜度分析

- **O(n)**（依串列長度）

---
