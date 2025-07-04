---
title: Chapter 27

---

# Chapter 27  

## Homework

---

### **Problem 1**

An automobile battery has an emf of $12.6 V$ and an internal resistance of $0.080 0 Ω$ . The headlights together present equivalent resistance $5.00 Ω$ (assumed constant). What is the potential difference across the headlight bulbs(車頭燈)  
(a) when they are the only load on the battery and  
(b) when the starter motor is operated, taking an additional $35.0 A$ from the battery?  

**Question Translation:**  
(a) 只有車頭燈的時的負載電壓  
(b) 當電池多輸出 $35A$的負載電壓  

**Solution:**  
(a)  
  $V_{load} =12.6\times \frac{5}{5+0.08} = 12.40V$  
(b)  
根據**KVL**設過燈的電流為**I**得到迴路方程
$12.6 - 0.08 \times (35+I) - 5I = 0$  
$I = 1.93A$  
$V_{load} = 1.93 \times 5 = 9.65V$

---

### **Problem 2**

(a)Find the equivalent resistance between points a and b in below figure.  
(b) A potential difference of $34.0 V$ is applied between points a and b. Calculate the current in each resistor.  
![ ](https://raw.githubusercontent.com/tim941008/note/main/resource/ch27_1.png)  

**Question Translation:**  
(a) 求等效電阻$R_{ab}$  
(b) 有 $34V$ 電壓在a b兩端求每個電阻流過的電流

**Solution:**  
(a)  
  $4 +(7//10) + 9 = 17.12 \Omega$  
(b)  
  $I_{total} = 34 \div 17.12 = 1.99A$  
  $I_{4\Omega}= 1.99A$  
  $I_{9\Omega} = 1.99A$  
  $I_{7\Omega} = 1.98 \times \frac{10}{17} = 1.17A$  
  $I_{10\Omega} = 1.98 \times \frac{7}{17} = 0.82A$  
  
---
### **Problem 3**

For the purpose of measuring the electric resistance of shoes through the body of the wearer to a metal ground plate, the American National Standards Institute (ANSI) specifies the circuit shown in right figure. The potential difference $ΔV$ across the $1.00-MΩ$ resistor is measured with a high-resistance voltmeter.  
(a) Show that the resistance of the footwear is given by
![image](https://hackmd.io/_uploads/rJ9NmXfJll.png)  
(b) In a medical test, a current through the human body should not exceed $150 μA$. Can the current delivered by the ANSI-specified circuit [exceed(超過)](https://dictionary.cambridge.org/zht/%E8%A9%9E%E5%85%B8/%E8%8B%B1%E8%AA%9E/exceed) $150 μA?$ To decide, consider a person standing barefoot on the ground plate. 
![ ](https://hackmd.io/_uploads/Sk9JVXfyeg.png)


**Question Translation:**  
(a) 推導式子  
(b) 赤腳站在上面是否會超過 $150\mu A$  

**Solution:**  
(a)已知在電阻上面的電位差為 $\Delta V$  
 $\Delta V = 50V \times \frac{1M}{1M + R_{shoes}}$  
 $R_{shoes} = 1M\times\frac{50V - \Delta V}{\Delta V}$  
(b)  
最大電流 $I = \frac{50}{10^6} = 50 \mu A$

---

### **Problem 4**

The current in a circuit is tripled by connecting a $500Ω$ resistor in parallel with the resistance of the circuit. Determine the resistance of the circuit in the absence of the $500Ω$ resistor.  

**Question Translation:**  
在一個電路中，若將一個 500 Ω 的電阻與原有電阻並聯，電路中的電流會變為原來的三倍。請求出在未連接 500 Ω 電阻前，原本電路的電阻為多少？  

**Solution:**  

利用電導$G$解題

$$
V \times (\frac{1}{R} + \frac{1}{500}) = V \times \frac{1}{R}\times 3
$$
$R = 1000 \Omega$

---

### **Problem 5**

Taking $R = 1.00 kΩ$ and $ε = 250 V$ in below figure, determine the direction and magnitude of the current in the horizontal wire between a and e  
![123](https://hackmd.io/_uploads/HJEF5mMyll.png)  
**Question Translation:**  
求電流$I_{ae}$ 

**Solution:**  
簡化電路  
![image](https://hackmd.io/_uploads/ByvIhmzylx.png)  
大小為$50mA$  
方向為$a -> e$

---

### **Problem 6**

For the network shown in below figure, show that the resistance Rab = $(27/17) Ω$ .  
  
![ ](https://hackmd.io/_uploads/Bk6G6mMylx.png)

**Question Translation:**  
求電阻$R_{ab}$ 

**Solution:**  
不偷懶了...  
設a b間有一電壓$V$  
有三個loop三個未知電流求解 求總電流$I_1$

$$
\begin{cases}
2I_1 - I_2 -I_3 = V \\
-I_1 + 5I_2 -I_3 = 0 \\  
-I_1 - I_2 +7I_3 = 0
\end{cases}  
$$

得出 $I_1 = \frac{17}{27}V$  
$R_{ab} = \frac{27}{17}Ω$  
:::info
$Y - \Delta$ 轉換比較快  
:::

---

### **Problem 7**

For the circuit shown in below figure, calculate  
(a) the current in the 2.00-Ω resistor and  
(b) the potential difference between points a and b  
  
![ ](https://hackmd.io/_uploads/SkNqySGyge.png)


**Question Translation:**  
(a)通過$2\Omega$的電流  
(b) 求$V_{ab}$  

**Solution:**  
設b點為0電位
求a點電位

根據**KCL**

$\frac{V+8}{6} + \frac{V}{2} + \frac{V-12}{4} = 0$  
$V_{ba} = -1.82V$  
$I_{2 \Omega} = 1.82 \div 2 = 0.91A$

---

### **Problem 8**

A capacitor in an RC circuit is charged to $60.0%$ of its maximum value in $0.900 s$ . What is the time constant of the circuit?  
  


**Question Translation:**  
求時間常數 $\tau$   

**Solution:**  

$e^{-\frac{0.9}{\tau}} = 0.4$  
$\tau = -\frac{0.9}{\ln 0.4} = 0.982s$  


---

### **Problem 9**

The circuit in below figure has been connected for a long time.  
(a) What is the voltage across the capacitor?  
(b) If the battery is disconnected, how long does it take the capacitor to discharge to one tenth of its initial voltage?  
  

![ ](https://hackmd.io/_uploads/HyE0mHGkgl.png)

**Question Translation:**  
(a)求電容穩態電壓  
(b)多久時間到 $\frac{1}{10}V$

**Solution:**  

用[戴維寧](https://zh.wikipedia.org/zh-tw/%E6%88%B4%E7%BB%B4%E5%8D%97%E5%AE%9A%E7%90%86)  
(a) $6V$  
(b) $e^{-\frac{t}{3.6\mu}} = 0.1$  
$t =  -3.6\ln0.1 \times 10^{-6} = 8.29\times 10^{-6}s$

---

### **Problem 10**

Design a multirange ammeter(多檔電流計) capable of full-scale [deflection(偏轉)](https://dictionary.cambridge.org/zht/%E8%A9%9E%E5%85%B8/%E8%8B%B1%E8%AA%9E-%E6%BC%A2%E8%AA%9E-%E7%B9%81%E9%AB%94/deflection) for $25.0 mA$, $50.0 mA$, and $100 mA$. Assume the meter movement is a [galvanometer 檢流計](https://tw.dictionary.search.yahoo.com/search?p=galvanometer) that has a resistance of $25.0 Ω$ and gives a full-scale deflection for $1.00 mA$. 

**Question Translation:**  
我們要設計一個 多檔電流計（multirange ammeter），可以量測 25.0 mA、50.0 mA 和 100 mA 

**Solution:**  

求分流電阻  


![ ](https://hackmd.io/_uploads/rkbJ691bge.png)



---