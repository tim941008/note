# 解題紀錄 LeetCode 6

## 題目：鋸齒形轉換（Zigzag Conversion）

## 📙 題目描述

給定一個字串 `s` 和一個整數 `numRows`，要求將 `s` 以 "Z字形" 排列，然後按行讀取，輸出新的字串。

### **範例**

#### **輸入**

```txt
s = "PAYPALISHIRING"
numRows = 3
```

#### **Z字形排列**

```txt
P   A   H   N
A P L S I I G
Y   I   R
```

#### **輸出**

```txt
"PAHNAPLSIIGYIR"
```

---

## ✒️ 解題思路

1. **觀察 Z 字形規律**

   - 每個完整的 Zigzag 週期長度為 `cycle = (numRows - 1) * 2`。
   - 每行的元素索引按照週期性出現。
   - 除了第一行與最後一行，每行會有 **兩個** 元素：
     - 第一個索引：`j = i`，間隔 `cycle`。
     - 第二個索引：`j + cycle - 2 * i`，用來補充對角線部分。

2. **遍歷每一行，按規律取字元**

   - 從 `i = 0` 到 `i = numRows-1` 遍歷每行。
   - 取 `j = i, j += cycle` 的元素。
   - 若 `i` 不是首行或末行，額外取 `j + cycle - 2 * i` $\textcolor{red}{垂直元素及斜邊元素}$ 。

---

## **程式碼實現（C 語言）**

```c
char* convert(char* s, int numRows) {
    int len = strlen(s);
    if (numRows == 1 || numRows == 1) return s; //特殊情況
    char *result = (char *)malloc(len + 1);
    int index = 0;
    int cycle = (numRows - 1) * 2;
    for (int i = 0; i < numRows; i++) {
        for (int j = i; j < len; j += cycle) {
            result[index++] = s[j];
            int secondIdx = j + cycle - 2 * i;//將週期內元素放入字串
            if (i > 0 && i < numRows - 1 && secondIdx < len) {
                result[index++] = s[secondIdx];
            }
        }
    }
    result[index] = '\0'; // 確保字串結束
    return result;
}

```

---

## **時間與空間複雜度分析**

- **時間複雜度：**
  - 每個字元最多被存取一次，因此時間複雜度為 `O(n)`。

---
