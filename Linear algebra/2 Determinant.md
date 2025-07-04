---
title: 2 Determinant

---

# 2 Determinant


## The Determinant of a Matrix

行列式
det($A$)可用來檢查一個$n\times n$ 矩陣是否是nonsingular 或是反矩陣是否存在

- 定義 $1 \times 1$ 矩陣 det($\mathbf{A}$) $= a$
- 若A 是 ==nonsingular== 則det($A$) $\ne 0$  


---

### 二階行列式（2x2 Determinant）

對於一個二階矩陣：

$$
A = \begin{bmatrix}
  a_{11} & a_{12} \\
  a_{21} & a_{22}
\end{bmatrix}
$$

其行列式的計算公式為：

$$
\text{det}(A) = a_{11}a_{22} - a_{12}a_{21}
$$



---

### 三階行列式（3x3 Determinant）

對於一個三階矩陣：

$$
A = \begin{bmatrix}
  a_{11} & a_{12} & a_{13} \\
  a_{21} & a_{22} & a_{23} \\
  a_{31} & a_{32} & a_{33}
\end{bmatrix}
$$

其行列式的計算公式可使用展開式 **(cofactor expansion )**（如依第一列展開）：

$$
\text{det}(A) = a_{11}(a_{22}a_{33} - a_{23}a_{32}) - a_{12}(a_{21}a_{33} - a_{23}a_{31}) + a_{13}(a_{21}a_{32} - a_{22}a_{31})
$$


- 若行列式為 0，表示該矩陣**不可逆**。




:::success
令  
$M_{ij} =\text{det}(A)$ 為第(i,j)個子行列式 **(Minor)**  
$C_{ij} = (-1)^{i+j}M_{ij}$餘因子 **(cofactor)**

:::

:::info
$n \times n$ matrix $n \geq 2$
可以用任何列或是行 ==cofactor expansion==   

(i,j)為被刪去的列及行  
$$
\det(A) = \sum_{j=1}^{n} (-1)^{i+j} a_{ij} \cdot \det(M_{ij})
$$
$$
\det(A) = \sum_{i=1}^{n} (-1)^{i+j} a_{ij} \cdot \det(M_{ij})
$$

:::


- 上三角矩陣之行列式為對角線元素乘積
- 對角矩陣之行列式為對角線元素乘積  
- 若有一行或列全為0則行列式則為0  
- 若兩行或兩列相同行列式則為0  
- $\text{det}(A)= \text{det}(A^T)$  
- $\text{det}(EA) = \text{det}(E)\text{det}(A)$
- 第一基本矩陣行列式為$-1$  
- 第二基本矩陣行列式為$\alpha \;(\alpha \ne 0)$ 
- 第三基本矩陣行列式為$1$  
- 若$U = E_{k}E_{k-1}...E_1A$
    - $\text{det}(U) = 0$則$\text{det}(A)= 0$
- $\text{det}(AB) = \text{det}(A)\text{det}(B)$

## Properties of Determinants Lemma 2.2.1  
對某列或某行元素乘上對應*cofactor*再取總和等於行列式值
若乘上不同對應的行列則為$0$  
(因為兩列或兩行相同為0)  
![image](https://hackmd.io/_uploads/SJsM5jRT1g.png)

---

## The Adjoint of a Matrix 


$\text{adj}(A) = \begin{bmatrix}
C_{11} &C_{12} &\cdots &C_{1n} \\
C_{21} &C_{22} &\cdots &C_{2n} \\
\vdots  &\vdots &\vdots &\vdots \\
C_{n1}  &\cdots &\cdots&C_{nn}
\end{bmatrix}^T$  

- $A \cdot \text{adj}(A) = \text{det}(A)I_n$
     - 因為$\text{adj}(A)$是轉置過後的cofactor矩陣對照前面性質(i,j)要相同因此只有主對角線元素不為0且是行列式值  

- 若 $A$ is nonsingular 則 $A^{-1} = \frac{\text{adj}(A)}{\text{det}(A)}$  

---

### Cramer's Rule

若$x$ 是唯一解

$\mathbf{x} = A^{-1}\mathbf{b}$  

$x_i = \frac{b_1A_{1i} +b_2A_{2i}... }{\text{det}(A)} = \frac{\text{det}(A_i) }{\text{det}(A)}$  
  
  
  

