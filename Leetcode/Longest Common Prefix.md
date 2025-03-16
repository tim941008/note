# 解題紀錄 LeetCode 14

## 題目：Longest Common Prefix

## 📙 題目描述

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string ``""``.

- 找出共同前綴子字串
**範例1：**

```txt
Input: strs = ["flower","flow","flight"]
Output: "fl"
```

**範例2：**

```txt
Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```

---

## ✒️ 解題思路

先找出這些字串中最短長度，再逐一跟第一個字串做比較。

``len``變數會隨著搜尋共同的子字串變化。

---

## 💻 C++解法

```cpp
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        if (strs.size() == 0)
            return "";
        int len{200};
        for (auto &s : strs) {
            if (s.length() < len) {
                len = s.length();
            }
        }
        for (auto &s : strs) {
            int cnt{0};
            while (cnt < len && s[cnt] == strs[0][cnt]) {
                cnt++;
            }
            len = cnt;
            if(len == 0) break;
        }
        return strs[0].substr(0, len);
    }
};
```

---
