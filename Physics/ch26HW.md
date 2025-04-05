# Chapter 26  

## Homework

---

### **Problem 1**

A teapot(茶壺) with a surface area of  $700 cm^2$ is to be silver plated. It is attached to the negative [electrode](https://dictionary.cambridge.org/zht/%E8%A9%9E%E5%85%B8/%E8%8B%B1%E8%AA%9E-%E6%BC%A2%E8%AA%9E-%E7%B9%81%E9%AB%94/electrode) of an electrolytic cell containing silver nitrate(硝酸鹽) (Ag+ NO3–). If the cell is powered by a $12.0V$ battery and has a resistance of $1.80 Ω$ , how long does it take for a 0.133-mm layer of silver to build up on the teapot? (The density of silver is   $10.5 × 10^3 kg/m^3$ .)  

**Question Translation:**  

一個表面積為 700 cm² 的茶壺要鍍上銀。它接在含有硝酸銀 (Ag⁺ NO₃⁻) 的電解槽的負極。若電解槽由 12.0 V 的電池供電，電阻為 1.80 Ω，鍍上一層厚度為 0.133 mm 的銀需要多久？（銀的密度為 10.5 × 10³ kg/m³。） 

**Solution:**  

先求體積:  

- $V =  A \cdot d = 700 \times 10^{-4} \times 0.133 \times 10^{-6} = 9.31 \times 10^{-2}m^3$  

求重量:

- $M = \rho V = 10.5 \times 10^3 \times 9.31 \times = 9.78\times 10^{-2}kg$

求原子數:

- $N = 9.78\times 10^{-2} \div 107.9\times 10^3 \times 6.02\times 10^{23}=  5.45 \times 10^{23}$

得出 $Q = Ne = 5.45\times 10^{23} \times 1.6 \times 10^{-19} = 87200C$  

$It = \frac{V}{R} \cdot t = Q$  
$t = \frac{Q\cdot R}{V} = 87200\times 1.8 \div 12 = 13080sec = 3.64h$

**Answer:**

$3.64h$

---

### **Problem 2**

The quantity of charge q (in coulombs) that has passed through a surface of area $2.00 cm^2$ varies with time according to the equation $q = 4t^3 + 5t + 6$ , where t is in seconds.  
(a) What is the [instantaneous(瞬間)](https://dictionary.cambridge.org/dictionary/english/instantaneous#google_vignette) current through the surface at t = 1.00 s?  
(b) What is the value of the current density?  

**Question Translation:**  
一個面積為 2.00 cm² 的表面，其通過的電荷量 q（單位：庫倫）隨時間變化  
$q = 4t^3 + 5t + 6$  
(a) 求 $t = 1.00$ 秒時的**瞬時電流**是多少？  
(b) 此時的**電流密度**是多少？

**Solution:**  
(a)  
$I \equiv \frac{dq}{dt} = 12t^2 + 5$  
$I = 17A$
(b)  
$J = \frac{I}{A} = 17\div(2\times10^{-4}) = 8.5 \times 10^4 A/m^2$  

---

### **Problem 3**

A [Van de Graaff generator](https://zh.wikipedia.org/zh-tw/%E8%8C%83%E5%BE%B7%E6%A0%BC%E6%8B%89%E5%A4%AB%E8%B5%B7%E7%94%B5%E6%9C%BA) produces a beam of 2.00-MeV deuterons, which are heavy hydrogen nuclei containing a proton and a neutron.  
(a) If the beam current is 10.0 μA, how far apart are the deuterons?  
(b) Is the electric force of repulsion among them a significant factor in beam stability? Explain.  
**Question Translation:**  
一台 Van de Graaff 產生器產生了一束能量為 $2.00 MeV$ 的 **重氫原子核（deuterons）** 粒子束。  
每個 deuteron 含有一個質子與一個中子。  
(a) 若該粒子束電流為 $10.0 μA$，請問這些 deuterons 的間距是多少？  
(b) 在這樣的情況下，deuterons 之間的**靜電排斥力**是否會成為影響粒子束穩定性的顯著因素？請解釋。
**Solution:**  

(a)
根據能量守恆  

- $2MeV = 2 \times 10^{6} \times 1.6 \times 10^{-19} = 0.5mv^2 = 0.5(2\times 1.67\times 10^{-27}) v^2$
- 求出 $v = 1.38\times 10^7$
- $I = \frac{q}{t} = 10\times10^{-6}A$
    - $t = \frac{1.6\times 10^{-19}}{10^{-5}} = 1.6 \times 10^{-14}$

- $\Delta x = vt = 1.38\times 10^7 \times 1.6\times 10^{-14} = 2.21\times 10^{-7}m$

(b)  
$V = \frac{KQ}{r} = \frac{8.99\times 10^9 \times 1.6\times 10^{-19}}{2.21\times 10^{-7}} = 6.44\times 10^{-3}$  
比 $2MV$ 小很多  

---

### **Problem 4**

An [aluminum](https://dictionary.cambridge.org/zht/%E8%A9%9E%E5%85%B8/%E8%8B%B1%E8%AA%9E-%E6%BC%A2%E8%AA%9E-%E7%B9%81%E9%AB%94/aluminium#google_vignette) wire having a cross-sectional area of $4.00 × 10^{–6} m^2$ carries a current of $5.00 A$ . Find the drift speed of the electrons in the wire. The density of aluminum is $2.70 g/cm^3$. Assume that one conduction electron is supplied by each atom.  

**Question Translation:**  

一條截面積為 $4.00 × 10⁻⁶ m²$ 的鋁線中通有 $5.00 A$ 的電流。  

請問這條線中的電子漂移速度（drift speed）是多少？

**Solution:**   

求 $n$ :

材料密度乘上亞佛加爵常數 $\div$ 莫爾質量

$\frac{2700 \times 6.02\times 10^{23}}{27\times 10^-3}=6.02 \times 10^{28}$

$v_d = \frac{I}{nqA}$

**Answer:**  
$1.3\times 10^{-4}m/s$

---

### **Problem 5**

A conductor of uniform radius 1.20 cm carries a current of 3.00 A produced by an electric field of 120 V/m. What is the resistivity of the material? 

**Question Translation:**  

一條半徑為 $1.20 cm$ 的導體，其內部由電場 $120 V/m$ 所產生電流 $3.00 A$。

請問：這種材料的 **電阻率（resistivity）** 是多少？  

**Solution:**  

$I = \sigma EA = \sigma 120 \times 1.44 \times 10^{-4} \pi= 3$
$\rho = \frac{1}{\sigma} = 0.0181 \Omega \cdot m$


---

### **Problem 6**

Gold is the most [ductile](https://dictionary.cambridge.org/zht/%E8%A9%9E%E5%85%B8/%E8%8B%B1%E8%AA%9E-%E6%BC%A2%E8%AA%9E-%E7%B9%81%E9%AB%94/ductile) of all metals. For example, one gram of gold can be drawn into a wire 2.40 km long. What is the resistance of such a wire at 20°C? You can find the necessary reference information in this textbook.

**Question Translation:**  

金是所有金屬中延展性最好的。例如，一公克的金可以拉成長達 $2.40 km$ 的金線。

請問：這樣的一條金線在 $20°C$ 時的 **電阻** 是多少？
**Solution:**  

求體積
 $V = \frac{M}{\rho}  = \frac{10^{-3}}{1.93\times10^4} = 5.18\times 10^{-8} = A(2.4 \times 10^{3})$
求面積
 $A = \frac{5.18\times 10^{-8}}{2.4\times 10^3} = 2.16\times 10^{-11}m^2$


$R = \frac{\rho l}{A} = \frac{2.44\times 10^{-8}\times 2.4\times 10^3}{2.16\times 10^{-11}}=2.71\times 10^6 \Omega$


---

### **Problem 7**

The rod in below figure is made of two materials. The figure is not drawn to scale. Each conductor has a square cross section 3.00 mm on a side. The first material has a resistivity of $4.00 × 10^{–3} Ω$ · m and is 25.0 cm long, while the second material has a resistivity of $6.00 × 10^{–3} Ω$ · m and is 40.0 cm long. What is the resistance between the ends of the rod?
![ ](https://raw.githubusercontent.com/tim941008/note/main/resource/ch26.png)

**Question Translation:**  
下圖所示的導棒由兩種不同材料組成（圖未按比例繪製）。  
每段導體的橫截面積都是 **3.00 mm × 3.00 mm** 的正方形。

- 第一段長度為 $25.0 cm$，其電阻率為 $4.00 × 10⁻³ Ω·m$  
- 第二段長度為 $40.0 cm$，其電阻率為 $6.00 × 10⁻³ Ω·m$  

**Solution:**

$R_{total} = \frac{4 \times 10^{-3}\times 0.25 +6\times10^{-3}\times 0.4 }{9 \times 10^{-6}} = 378 \Omega $ 

---

### **Problem 8**

Use data from Example 26.1 to calculate the collision mean free path of electrons in copper. Assume the average thermal speed of conduction electrons is $8.60 × 10^5 m/s$.
**Question Translation:**  

使用26.1 的資料，計算 **銅中傳導電子的碰撞平均自由長度**（mean free path）。

**Solution:**  

$\tau = \frac{l_{avg}}{v_{avg}}$
$l = v_{avg}\tau$
$\tau = \frac{m_e}{nq^2\rho} = \frac{9.11\times 10^{-31}}{8.49\times10^{28}\times (1.6\times10^{-19})^2\times1.7 \times 10^{-8}} = 2.47\times 10^{-14}s$

$l = 8.6\times 10^5 \times 2.47 \times 10^{-14} = 2.12 \times 10^{-8}$

---

### **Problem 9**

Review problem. An aluminum rod has a resistance of 1.234 Ω at 20.0°C. Calculate the resistance of the rod at 120°C by accounting for the changes in both the resistivity and the dimensions of the rod.
**Question Translation:**  

求鋁棒在120°C時的電阻

**Solution:**  

$R = R_0(1 + \alpha \Delta T)$
$1.234(1 +0.0039\times100) = 1.71 \Omega$

---

### **Problem 10**

A 10.0-V battery is connected to a 120-Ω resistor. Ignoring the internal resistance of the battery, calculate the power delivered to the resistor.
**Question Translation:**  

求消耗能量

**Solution:**  

$P = \frac{V^2}{R} =100 \div 120 = 0.833W$

---