# 解題紀錄 LeetCode 11

## 題目：Container With Most Water

## 📙 題目描述

You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).
Find two lines that together with the x-axis form a container, such that the container contains the most water.
Return the maximum amount of water a container can store.
Notice that you may not slant the container.

- 求兩個高度間圍起來的最大容量

**範例1：**

![ ](https://raw.githubusercontent.com/tim941008/note/main/resource/Container_With_Most_Water.png)


```txt
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.

```

**範例2：**

```txt
Input: height = [1,1]
Output: 1
```

---

## ✒️ 解題思路

1.使用**雙指針**解法

- 每次移動高度較小的指針

## 💻 C++解法

```cpp
class Solution {
public:
    int maxArea(vector<int>& height) {
        int l = 0;
        int r = height.size() - 1;
        int max = 0, cur = 0;
        while (l < r) {
            cur = (r - l) * min(height[l], height[r]);
            if (max < cur) {
                max = cur;
            }
            if (height[l] > height[r]) {
                r--;
            } else {
                l++;
            }
        }
        return max;
    }
};
```

---

## 🕛時間複雜度分析

- **O(n)**（迴圈遍歷）

---
