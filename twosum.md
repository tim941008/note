# 解題紀錄

## 題目：兩數之和（Two Sum）

## 📙 題目描述
給定一個整數陣列 `nums` 和一個目標值 `target`，請找出兩個數字，使其和等於 `target`，並回傳這兩個數字的索引值。

**範例：**
```txt
輸入: nums = [2, 7, 11, 15], target = 9
輸出: [0, 1]
```

---

## ✒️ 解題思路
1. **雙迴圈暴力解法**
   - 遍歷陣列，檢查兩個數字的和是否等於 `target`
   - 雙層迴圈找出是否有相加等於目標的整數
   - 若沒找到則釋放記憶體並回傳 `NULL`
   
---

## 💻 C 語言解法

```c
#include <stdio.h>
#include <stdlib.h>

int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    *returnSize = 2;
    int* ans = malloc(sizeof(int) * 2);
    for(int i = 0;i < numsSize;i++){
        for(int j = i + 1;j < numsSize;j++){
            if(nums[i] + nums[j] == target){
                ans[0] = i;
                ans[1] = j;
                return ans;
            }
        }
    }
    free(ans);
    return NULL;
}
```

---

##  🕛時間複雜度分析
- **暴力解法：O(n²)**（雙迴圈遍歷）
- **我會努力研究 hash table的**
---


