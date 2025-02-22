# 二元搜尋法（Binary Search）

---
## 思路

二元搜尋法適用於**已排序**的數列，透過每次將搜尋範圍縮小一半來快速定位目標值。

- **迭代版本**：使用 `while` 迴圈，每次比較中間值與目標值，並根據結果縮小搜尋範圍。
- **遞迴版本**：透過遞迴函式，每次遞迴呼叫時縮小搜尋範圍，直到找到目標值或範圍無效。

## 演算過程

1. 設定 `left` 為 0，`right` 為陣列大小減 1。
2. 計算中間索引 `mid = (left + right) / 2`。
3. 比較 `arr[mid]` 與 `target`：
   - 若相等，返回 `mid`。
   - 若 `arr[mid] < target`，更新 `left  = mid + 1`。
   - 若 `arr[mid] > target`，更新 `right = mid - 1`。
4. 重複以上步驟直到找到 `target` 或 `left > right`（搜尋失敗）。

## 迭代版本(c語言)

```c
int binary_search(int* arr, int target, int left, int right) {
    while (left <= right) {
        int mid = (right + left) / 2;
        if (arr[mid] == target)  
            return mid;
        else if (arr[mid] < target) 
            left = mid + 1;
        else 
            right = mid - 1;
    }
    return -1;
}
```

## 遞迴版本(c語言)

```c
int binary_search(int* arr, int target, int left, int right) {
    if (left > right) 
        return -1;
    int mid = (right + left) / 2;
    if (arr[mid] == target) 
        return mid;
    else if (arr[mid] < target) 
        return binary_search(arr, target, mid + 1, right);
    else 
        return binary_search(arr, target, left, mid - 1);
}
```

---

## 時間與空間複雜度分析

### **時間複雜度**

二元搜尋法每次查找都將搜尋範圍縮小為原來的一半，因此其時間複雜度為 **O(log n)**。

- 假設初始陣列長度為 `n`，每次搜尋後，範圍變為 `n/2`、`n/4`、`n/8`....
  直到 `n/2^k = 1`，解得 `k = log_2(n)`，也就是 **O(log n)**。

| 數據大小 `n` | 最大查找次數 `log_2(n)` |
|-------------|------------------|
| 10         | ≈ 3              |
| 100        | ≈ 7              |
| 1,000      | ≈ 10             |
| 1,000,000  | ≈ 20             |

可以看到，即使 `n` 非常大，二元搜尋仍然能夠很快地找到目標。

### **空間複雜度**

- **迭代版本**：僅使用變數 `left`、`right`、`mid`，**空間複雜度為 O(1)**。
- **遞迴版本**：每次遞迴都會建立新的堆疊幀，最多呼叫 `log n` 次，  
  所以遞迴版本的 **空間複雜度為 O(log n)**。

### **優勢與劣勢**

| 方法 | 優勢 | 劣勢 |
|------|------|------|
| **迭代版本** | 使用 O(1) 空間，效能較高 | 需要額外的 `while` 迴圈 |
| **遞迴版本** | 代碼簡潔，直觀 | 佔用 O(log n) 的遞迴堆疊 |

### **適用場景**

- 適用於 **已排序** 的陣列。
- 若資料集較大且查詢頻繁，**二元搜尋法比線性搜尋（O(n)）更高效**。
