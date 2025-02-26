# 解題紀錄 LeetCode 9

## 題目：回文數（Palindrome Number）

## 📙 題目描述

Given an integer ``x``, return true if ``x`` is a *palindrome*, and false otherwise.

給定一個整數x，如果x是回文則傳回true，否則false

**範例1：**

```txt
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

**範例2：**

```txt
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

**範例3：**

```txt
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```

---

## ✒️ 解題思路

1. **判斷條件**
    - ``x`` > 0
    - ``x``的最低位數及最高位數不為0 **x可以是0**
2. **回文數是對稱**
    - 迴圈至中間即可
    - 若數字是**奇數長度**必須將``cur`` $/10$ 與x做比較

## 💻 C++ 解法

```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        if (x < 0 || x % 10 == 0 && x != 0 )
            return false;
        int cur{0}; //當前紀錄數字
        while (x > cur) {
            cur = cur * 10 + x % 10;//反轉數字-->121 ->x = 1 cur = 12
            x /= 10;
        }
        return ( x == cur  ||  x == (cur / 10));
    }
};

```

---

## 🕛時間複雜度分析

- **O(n)**（迴圈遍歷）

---
