# 解題紀錄 LeetCode 848

## 題目：Shifting Letters(移動字母)

## 📙 題目描述

You are given a string ``s`` of lowercase English letters and an integer array ``shifts`` of the same length.

Call the ``shift()`` of a letter, the next letter in the alphabet, (wrapping around so that ``'z'`` becomes ``'a'``).

For example, ``shift('a') = 'b'`` , ``shift('t') = 'u'``, and ``shift('z') = 'a'``.
Now for each ``shifts[i] = x``, we want to shift the first ``i + 1`` letters of ``s``, ``x`` times.

Return the final string after all such shifts to ``s`` are applied.

給定一個小寫字母的字串 `s` 和一個整數陣列 `shifts`，其中 `shifts[i]` 代表 `s[0]` 到 `s[i]` 需要被右移的總次數。我們需要計算移動後的新字串，並返回該結果。
後面字母移動，前面字母也需移動。

---

**Example 1:**

```txt
Input: s = "abc", shifts = [3,5,9]
Output: "rpl"
Explanation: We start with "abc".
After shifting the first 1 letters of s by 3, we have "dbc".
After shifting the first 2 letters of s by 5, we have "igc".
After shifting the first 3 letters of s by 9, we have "rpl", the answer.
```

**Example 2:**

```txt
Input: s = "aaa", shifts = [1,2,3]
Output: "gfd"

```

## ✒️ 解題思路

本題的核心是 **後綴和 (Suffix Sum)**  

前面字母會受到後面字母移動次數影響。
可以從陣列最後一個元素至陣列首元素移動
每次迴圈更新``shift_sum``讓陣列前一個元素可以正確移動

令 $\text{shiftsum}[i] \text{表示} \text{shifts}[i] \text{到} \text{shifts}[n-1]$ 的總和

可以得出 :

$\text{shiftsum}[i] = (\text{shiftsum}[i+1] + \text{shifts}[i]) \mod 26$

---

## 💻 C 語言解法

```c
char* shiftingLetters(char* s, int* shifts, int shiftsSize) {
    int shift_sum = 0;  // 記錄累積的 shift 值
    for (int i = shiftsSize - 1; i >= 0; i--) {
        shift_sum = (shift_sum + shifts[i]) % 26; 
        s[i] = 'a' + (s[i] - 'a' + shift_sum) % 26;  // 確保字元範圍在 'a'~'z'
    }
    return s;
}
```

---

## 🕛時間複雜度分析

- **時間複雜度：** `O(n)`
  - 從陣列最後元素至首

---
