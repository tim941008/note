# Homework Chapter 22

## 1. Number of Electrons and Net Charge Calculation

(a) Calculate the number of electrons in a small, electrically neutral silver pin that has a mass of 10.0 g. Silver has 47 electrons per atom, and its molar mass is 107.87 g/mol. (b) Electrons are added to the pin until the net negative charge is 1.00 mC. How many electrons are added for every $10^9$ electrons already present?

### 1.中文翻譯

(a) 計算一根 10.0 g 的電中性銀針()中的電子數。銀每個原子有 47 個電子，其莫耳質量為 107.87 g/mol。

(b) 向銀針中添加電子，使其淨電荷達到 1.00 mC。對於每 $10^9$ 個原來的電子，新增多少電子？

### 1.Solution

a. 計算銀針中的電子總數：

- $1 mol = 6.02 \times 10^{23} $ 個原子
- 一個原子有47個電子
   $ {個數} = \frac{10.0 g}{107.87 g/mol} \times (6.022 \times 10^{23}) = 5.59 \times 10^{22} \times 47 = (5.59 \times 10^{22}) \times 47 = 2.63 \times 10^{24} {個電子}$

b. 計算新增電子數：

   $n = \frac{1.00 \times 10^{-3} C}{1.6 \times 10^{-19} C} = 6.25 \times 10^{15}$
   $\frac{6.25 \times 10^{15}}{2.63 \times 10^{24}} \times 10^9 = 2.38$
題目要求是以每 $10^9$ 個電子所新增的所以要乘上 $10^9$ 這題看了好久也是不懂😥
**答案：每 $10^9$ 個原電子新增 2.38 個電子。**

---

## 2. Electric Force Between Protons

Two protons(質子) in an atomic nucleus(核) are typically separated by a distance of $2 × 10^{15}$ m. The electric repulsion force(排斥力) between the protons is huge, but the attractive nuclear force is even stronger and keeps the nucleus from bursting apart(炸開). What is the magnitude of the electric force between two protons separated by $2.00 × 10^{15}$ m?

### 2.中文翻譯

兩個質子在原子核中通常相距 \(2.00 \times 10^{-15}\) m。求它們之間的電力大小。

### 2.Solution

1.使用庫侖定律計算庫倫靜電力：

- $F = k \frac{q_1 q_2}{r^2}$

2.代入已知值：

- 質子電荷 $ q_1 = q_2 = 1.6 \times 10^{-19} C $
- 距離 $ r = 2.00 \times 10^{-15} m $
- 庫侖常數 $ k = 8.988 \times 10^9 N\cdot m^2/C^2 $

3.計算：

- $F = \frac{(8.988 \times 10^9) (1.6 \times 10^{-19})^2}{(2.00 \times 10^{-15})^2} = 57.52 N$

**答案：質子間的電力為 $ 57.52 N $。**

---

## 3. Electrostatic Force on Earth

 Suppose that $1.00 g$ of hydrogen is separated into electrons and protons. Suppose also that the protons are placed at the Earth’s north pole and the electrons are placed at the south pole. What is the resulting compressional(壓縮) force on the Earth?

### 3.中文翻譯

假設 1.00 g 的氫被分離為電子和質子，並且質子放置在地球的北極，電子放置在南極。求作用在地球上的壓縮力。

### Solution

1.計算電荷總量：

   $Q = N e = (6.02 \times 10^{23}) (1.602 \times 10^{-19}) $

2.使用庫侖定律計算作用在地球上的力。
   **設地球半徑$6400km$**
   帶入公式:

- $F = \frac{(8.988 \times 10^9) (6.02 \times 1.6 \times 10^{4})^2}{(2 \times 6400 \times 10^{3})^2} = 5.08 \times 10^{3} N$

---

## 4. Equilibrium of a Charged Bead

Two small beads(珠) having positive charges 3q and q are fixed at the opposite ends of a horizontal, insulating rod, extending from the origin to the point x = d. As shown in figure below, a third small charged bead is free to slide on the rod. At what position is the third bead in equilibrium? Can it be in stable [equilibrium](https://dictionary.cambridge.org/zht/%E8%A9%9E%E5%85%B8/%E8%8B%B1%E8%AA%9E-%E6%BC%A2%E8%AA%9E-%E7%B9%81%E9%AB%94/equilibrium) ?(平衡)

[圖片](/resource/ch22hw_p1.png)

### 4.中文翻譯

兩個帶有正電荷 $3q$ 和 $q$ 的小珠分別固定在絕緣棒的兩端，該棒從原點延伸至 $x = d$。另一顆帶電珠可以在棒上自由滑動。求該珠處於平衡的位置，並判斷其是否為穩定平衡。

### 4.Solution

1.**建立方程式**

- $\frac{k(3qQ)}{x^2} = \frac{k(qQ)}{(d-x)^2}$
可以得知在 $x = \frac{3 \pm \sqrt{3}}{2} \cdot {d}$ 時有解

---

## 5. Mass of Floating Object in Electric Field

An object having a net charge of $24.0 μC$ is placed in a uniform electric field of $610 N/C$ directed vertically. What is the mass of this object if it “floats’’ in the field?

### 5.中文翻譯

一個帶有 24.0 μC 電荷的物體被放置在 610 N/C 的均勻電場中，電場方向為垂直向上。如果該物體在電場中「漂浮」，求其質量。

### 5.Solution

因為$F = ma = mg = qE $  
我們所求 $m = \frac {q \cdot E}{g} = \frac {24.0 \times 10^{-6} \times 610}{9.8} = 1.49 \times 10^{-3} g$

---

## 6. Electric Field on an Airplane in a Thundercloud

An airplane is flying through a thundercloud at a height of 2 000 m. (This is a very dangerous thing to do because of updrafts, turbulence, and the possibility of electric discharge.) If acharge concentration of +40.0 C is above the plane at a height of 3 000 m within the cloud and a charge concentration of –40.0 C is at height 1 000 m, what is the electric field at the aircraft?

### 6.中文翻譯

一架飛機正在高度 $2000 m$ 的雷暴雲中飛行。在飛機上方 $3000 m$ 處有一個電荷分布 $+40.0$ C，在飛機下方 1000 m 處有一個電荷分布 $-40.0$ C。求飛機處的電場。

### 6.Solution

這題把飛機當成**Test charge** 對於不同**Source charge**求出**向量加總**
1.**討論正電荷所施的電場方向**
   在 $3000m$ 處的 $+40C$ 所施加的電場方向為
   $  \frac{8.988 \times 10^9\times 40}{(10^{3})^2} $
   方向為下
2.**討論負電荷所施的電場方向**
   在 $1000m$ 處的 $-40C$ 所施加的電場方向為
   $ \frac{8.988 \times 10^9\times 40}{(10^{3})^2} $ 方向為下

3.**求出總和**
   **兩大小相同且方向相同**可以直接計算
   $ \frac{2 \times 8.988 \times 10^9\times 40}{(10^{3})^2}  = 718400\frac{N}{C}$
