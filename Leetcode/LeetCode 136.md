# 解題紀錄 LeetCode 136

## 題目：Single Number

## 📙 題目描述

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

- 找出沒有重複出現過的數字
**Example 1:**

```txt
Input: nums = [2,2,1]

Output: 1
```

**Example 2：**

```txt
Input: nums = [4,1,2,1,2]

Output: 4
```

**Example 3：**

```txt
Input: nums = [1]

Output: 1
```

---

## ✒️ 解題思路

- 利用**XOR**的性質，當兩個一樣的數字做^運算，其結果為0。  
- 遍歷陣列結束，結果為不重複數字。

---

## 💻 C++解法

```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int result = 0;
        for(int num : nums){
            result ^= num; 
        }
        return result;
    }
};
```

---
