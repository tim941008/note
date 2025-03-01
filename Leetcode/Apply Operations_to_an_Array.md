# 解題紀錄 LeetCode 2460

## 題目：Apply Operations to an Array

## 📙 題目描述

You are given a ``0-indexed`` array nums of size n consisting of non-negative integers.

You need to apply ``n - 1`` operations to this array where, in the ith operation (``0-indexed``), you will apply the following on the ith element of nums:

If ``nums[i] == nums[i + 1]``, then multiply ``nums[i]`` by 2 and set nums[i + 1] to 0. Otherwise, you skip this operation.
After performing all the operations, shift all the 0's to the end of the array.

- For example, the array ``[1,0,2,0,0,1]``after shifting all its 0's to the end, is ``[1,2,1,0,0,0]``.
Return the resulting array.

Note that the operations are applied sequentially, not all at once.

- 若兩個相鄰數字相等，則將前一個數字翻倍，並將後一個數字設為 0。
- 將所有非零數字移動到新陣列的前面，保持原有順序。

**範例1：**

```txt
Input: nums = [1,2,2,1,1,0]
Output: [1,4,2,0,0,0]

```

**範例2：**

```txt
Input: nums = [0,1]
Output: [1,0]
```

---

## ✒️ 解題思路

1.**calloc**確保陣列元素為0

2.將非零元素加入到新陣列

## 💻 C 語言解法

```c
int* applyOperations(int* nums, int numsSize, int* returnSize) {
    int* result = calloc(numsSize,sizeof(int));
    int nonzero = 0;
    for(int i = 0;i < numsSize ;i++){ //邊界檢查及檢查相鄰元素
        if(i != numsSize-1 && nums[i] == nums[i + 1]){
            nums[i]  <<= 1;
            nums[i + 1] = 0; 
        }
        if(nums[i] != 0){
            result[nonzero++] = nums[i];
        }
    }
    *returnSize = numsSize;
    return result;
}

```

---

## 🕛時間複雜度分析

- **O(n)**（迴圈遍歷）

---
