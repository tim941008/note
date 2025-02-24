# 解題紀錄

## 題目：字串轉整數（atoi）

## 📙 題目描述

Implement the myAtoi(string s) function, which converts a string to a 32-bit signed integer.

The algorithm for myAtoi(string s) is as follows:

1.Whitespace: Ignore any leading whitespace (" ").
2.Signedness: Determine the sign by checking if the next character is '-' or '+', assuming positivity if neither present.
3.Conversion: Read the integer by skipping leading zeros until a non-digit character is encountered or the end of the string is reached. If no digits were read, then the result is 0.
4.Rounding: If the integer is out of the 32-bit signed integer range [-231, 231 - 1], then round the integer to remain in the range. Specifically, integers less than -231 should be rounded to -231, and integers greater than 231 - 1 should be rounded to 231 - 1.
Return the integer as the final result.

1.略過空格
2.檢查 $\pm$ 號
3.沒有讀到數字回傳 ``0``
4.超過範圍則用 $2^31-1$ 或是 $-2^31$

其實這題蠻有趣
在C語言``stdlib.h``其實有 ``atoi``這個函式🤣

**Example 1:**

```txt
Input: s = "42"

Output: 42

Explanation:

The underlined characters are what is read in and the caret is the current reader position.
Step 1: "42" (no characters read because there is no leading whitespace)
         ^
Step 2: "42" (no characters read because there is neither a '-' nor '+')
         ^
Step 3: "42" ("42" is read in)
           ^
```

**Example 2:**

```txt
Input: s = " -042"

Output: -42

Explanation:

Step 1: "   -042" (leading whitespace is read and ignored)
            ^
Step 2: "   -042" ('-' is read, so the result should be negative)
             ^
Step 3: "   -042" ("042" is read in, leading zeros ignored in the result)
               ^
Example 3:
```

**Example 3:**

```txt
Input: s = "1337c0d3"

Output: 1337

Explanation:

Step 1: "1337c0d3" (no characters read because there is no leading whitespace)
         ^
Step 2: "1337c0d3" (no characters read because there is neither a '-' nor '+')
         ^
Step 3: "1337c0d3" ("1337" is read in; reading stops because the next character is a non-digit)
             ^
```

**Example 4:**

```txt
Input: s = "0-1"

Output: 0

Explanation:

Step 1: "0-1" (no characters read because there is no leading whitespace)
         ^
Step 2: "0-1" (no characters read because there is neither a '-' nor '+')
         ^
Step 3: "0-1" ("0" is read in; reading stops because the next character is a non-digit)
          ^
```

**Example 5:**

```txt
Input: s = "0-1"

Output: 0

Explanation:

Input: s = "words and 987"

Output: 0

Explanation:

Reading stops at the first non-digit character 'w'.

```

---

## ✒️ 解題思路

1. **宣告變數**
    - 變數``i``代表**當前字串索引**
    - 變數``sum`` 儲存**數字轉換結果**，因為有可能會溢位，所以宣告型態為``long long``  
2. **跳過空白**
    - 先用``While``迴圈跳過前面空白
3. **判斷正負**
4. **轉換數字**
    - 在轉換的同時**判斷是否有溢位**

---

## 💻 C 語言解法

```c
int myAtoi(char* s) {
    int i = -1, sign = 1;
    long long sum = 0; 
    while (s[++i] == ' '); //跳過空格
    if (s[i] == '-' || s[i] == '+') { //正負號處理
        if (s[i] == '-') {
            sign = -1;
        }
        i++;
    }
    while (s[i] >= '0' && s[i] <= '9') { //數字轉換
        sum = sum * 10 + (s[i] - '0'); 
        if (sign == 1 && sum > INT_MAX) return INT_MAX;//檢查是否溢位
        if (sign == -1 && -sum < INT_MIN) return INT_MIN; // INT_MIN 及 INT_MAX 定義在limits.h
        i++;
    }
    return (int)(sign * sum); //強制轉成int
}
```

---

## 🕛時間複雜度分析

- **O(n)**（迴圈遍歷）
  - 最多遍歷一次**

---
