# 陣列 (Array) 

---

## 1. 陣列的定義

陣列 (Array) 是一種 **線性資料結構**，用於儲存 **相同類型** 的多個數值，並且這些數值會依序存放在記憶體中。
同時是一排連續可數的記憶體，透過**索引**能取得陣列存放的資料。

## 2. 陣列的特性

    - **優點**
        - **索引 (Index)**：陣列中的每個元素都有一個唯一的索引，從 **0** 開始。
        - **快速存取**：可以透過索引直接存取陣列中的元素，時間複雜度為 **O(1)**。
    - **缺點**  
        - **記憶體浪費**： 宣告大小必須先決定好

## 3. 陣列的使用方式 (C 語言範例)

### 3.1 宣告與初始化

```c
    #include <stdio.h>
    #include <stdio.h>
    int main() {
    int arr_1[5];//不指定初始值
    int arr_2[5] = {0};//指定初始值為0
    int arr_3[5] = {1, 2, 3, 4, 5}; //指定初始值
    int arr_4[] = {1, 2, 3, 4, 5};//不指定長度，自動計算長度
    int arr_5[5] = {1, 2, 3, 4, 5, 6};//指定長度為5，但是給了6個初始值(編譯器會警告)
    int arr_6[5] = {1, 2, 3};//指定長度為5，但是只給了3個初始值，剩下的兩個會被初始化為0
    return 0;
}
```

### 3.2 陣列迴圈操作

```c
#include <stdio.h>
int main() {
    int arr[5] = {1, 2, 3, 4, 5};
    for (int i = 0; i < 5; i++) {
        printf("%d\n", arr[i]);//輸出元素
    }
    return 0;
}
```

## 4. 陣列與記憶體

陣列的元素是 **連續存放** 在記憶體中的，因此可以透過指標進行操作。

```c
#include <stdio.h>
int main() {
    int arr[3] = {10, 20, 30};
    int *ptr = arr + 1; //指標是存放位址的資料型態
    printf("%d",*ptr);  //輸出20
    return 0;
}
```

## 5. 二維陣列 與 元素位置

**以`r`為列數，`c` 為行數，`d`為元素大小**

- **以列為主(Row - major)**
    $$
    \cdot{Loc}(a_{ij}) = \text{起始位置} + c \cdot(i - 1) \cdot d +  (j - 1) \cdot d
    $$

- **以行為主(column - major)**
    $$
    \cdot{Loc}(a_{ij}) = \text{起始位置} + (i - 1) \cdot d + r \cdot (j - 1) \cdot d
    $$

以下是C語言以Row - major 實作
```c
#include <stdio.h>
int main() {
    int arr[3][3];//宣告3 * 3大小
    for(int i = 0;i < 3;i++) {
        for(int j = 0;j < 3;j++) {
            arr[i][j] = (i + 1) * 3 + (j + 1);
        }
    }
    printf("初始位置%d\n",&arr[0][0]);//陣列初始位置
    printf("arr[0][1]以row - major 位置%d\n",&arr[0][1]);//加了1的位置
    printf("arr[1][0]以row - major 位置%d\n", &arr[1][0]);//加了3的位置
}
```
![圖片](/note/resource/image.png)

## 5.1 二維陣列實作

👇以下是簡單的轉置矩陣實作

```c
#include <stdio.h>
#define MAX 10  // 最大矩陣大小
// 輸入矩陣
void inputMatrix(int matrix[MAX][MAX], int row, int col) {
    printf("請輸入 %d x %d 矩陣的元素：\n", row, col);
    for (int i = 0; i < row; i++) {
        for (int j = 0; j < col; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
}
// 轉置矩陣
void transposeMatrix(int matrix[MAX][MAX], int transposed[MAX][MAX], int row, int col) {
    for (int i = 0; i < row; i++) {
        for (int j = 0; j < col; j++) {
            transposed[j][i] = matrix[i][j];  // 行列互換
        }
    }
}
// 輸出矩陣
void printMatrix(int matrix[MAX][MAX], int row, int col) {
    printf("矩陣結果：\n");
    for (int i = 0; i < row; i++) {
        for (int j = 0; j < col; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
}
int main() {
    int matrix[MAX][MAX], transposed[MAX][MAX];
    int row, col;
    // 讀取使用者輸入的矩陣大小
    printf("請輸入矩陣的行數與列數：");
    scanf("%d %d", &row, &col);
    // 讀取矩陣
    inputMatrix(matrix, row, col);
    // 計算轉置矩陣
    transposeMatrix(matrix, transposed, row, col);
    // 輸出轉置後的矩陣
    printf("轉置矩陣：\n");
    printMatrix(transposed, col, row);  // 行列互換輸出
    return 0;
}

```

## 6. 陣列的應用

陣列的應用十分廣泛，例如：

- **排序演算法** (如氣泡排序、快速排序)
- **搜尋演算法** (如線性搜尋、二分搜尋)
- **矩陣運算**
- **圖像處理** (OpenCV 及 numpy)

### 6.1 更多維陣列討論

標準C語言能多達**12維陣列**，因此會有其他多維的應用。以下是討論多維陣列的記憶體存放方式。

- 以前面二維陣列的存放方式我們可以得知
我們以$u_1,u_2,u_3...$視作以1開始的索引($A(1:d_1,1:d_2,\cdots)$)
$S$為單位大小
  - **Row-major**
    - 當陣列宣告為
           $a[d_1][d_2][d_3] \dots [d_n]$
        則:

        $\text{位址} = \text{起始位置} +
        \left( (u_1 - 1) \times d_2 d_3 \cdots d_n + u_2 \times d_3 d_4  
        \cdots d_n + \dots + (u_{n-1} -1)\times d_n + u_n - 1 \right) \times S$

  - **Column-major**
    - 當陣列宣告為
        $a[d_1][d_2][d_3] \dots [d_n]$
    則:
        $\text{位址} = \text{起始位置} + \left( (u_n-1) \times d_2 d_3 \cdots d_n + (u_{n-1}-1) \times d_3 d_4   \cdots d_n + \dots + (u_2-1) \times d_n + (u_1-1) \right) \times S$

    #### Row and Column 想法

    從C語言**2D-Array**實作中得知以Row-major為主的語言，左邊的數字跳動的元素較多  
    而**Column-major**則反之
    因此可以將以 **Row-major** $A[u_1][u_2][u_3]$記憶體位置看成 **Column-major** $A[u_3][u_2][u_1]$

## 7. 結論

陣列是一種基礎但強大的資料結構，適用於 **大量資料的存儲與操作**。透過陣列，我們可以更有效地管理和處理數據，但在使用時需要注意 **邊界存取** 和 **記憶體管理**。

未來補充稀疏矩陣以及降維😉