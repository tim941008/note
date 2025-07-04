---
title: Chapter 30

---

# Chapter 30  

## Homework

---

### **Problem 1**

A 25-turn circular coil of wire has diameter 1.00 m. It is placed with its axis along the direction of the Earth’s magnetic field of 50.0 μT, and then in 0.200 s it is flipped 180°. An average emf of what magnitude is generated in the coil?  

**Question Translation:**  

求感應電勢  

**Solution:**  

$\Delta\cos\theta=1(\cos180^\circ - \cos0^\circ)=-2$  
$\epsilon = \frac{NBA}{0.2} = \frac{2\times25\times50\mu\times0.25\pi}{0.2} =9.82\times10^{-3}V$

---

### **Problem 2**
(a) A loop of wire in the shape of a rectangle of width w and length L and a long, straight wire carrying a current I lie on a tabletop as shown in Figure P30.1.  
(a) Determine the magnetic flux through the loop due to the current I.  
(b) Suppose the current is changing with time according to I = a + bt, where a and b are constants. Determine the emf that is induced in the loop if b = 10.0 A/s, h = 1.00 cm, w = 10.0 cm, and L = 100 cm. What is the direction of the induced current in the rectangle?  
![ ](https://hackmd.io/_uploads/rJUXIOZMlg.png)

**Question Translation:**  
**(a)**  
桌面上有一個矩形線圈，其寬度為 \\( w \\)，長度為 \\( L \\)，旁邊有一條長直導線通過電流 \\( I \\)，如圖 P30.1 所示。  
請求出由電流 \\( I \\) 所產生的穿過線圈的磁通量。

**(b)**  
假設電流隨時間變化為 \\( I = a + bt \\)，其中 \\( a \\) 和 \\( b \\) 為常數。  
若 \\( b = 10.0\\,\text{A/s} \\)、\\( h = 1.00\\,\text{cm} \\)、\\( w = 10.0\\,\text{cm} \\)、\\( L = 100\\,\text{cm} \\)，  
請求出矩形線圈中感應出的電動勢為多少？並判斷感應電流的方向。

**Solution:**  
(a)  
$$
\Phi_B = \int_{h}^{h+w} \frac{\mu_0 I L}{2\pi r} \, dr = \frac{\mu_0 I L}{2\pi} \ln\left(\frac{h + w}{h}\right)
$$
(b)
$$
\mathcal{E} = -\frac{d\Phi_B}{dt}
$$

$$
\mathcal{E} = -\frac{d}{dt} \left( \frac{\mu_0 L}{2\pi} I \ln\left(\frac{h + w}{h}\right) \right) = -\frac{\mu_0 L}{2\pi} \frac{dI}{dt} \ln\left(\frac{h + w}{h}\right)
$$

$$
\frac{dI}{dt} = b
$$

$$
\mathcal{E} = -\frac{\mu_0 L b}{2\pi} \ln\left(\frac{h + w}{h}\right)
$$
$$
\mathcal{E} = -\frac{(4\pi \times 10^{-7}) \cdot 1.00 \cdot 10.0}{2\pi} \ln\left(\frac{0.010 + 0.10}{0.010}\right)
= -2 \times 10^{-6} \ln(11) \approx -4.80 \times 10^{-6}\, \text{V}
$$

  
---
### **Problem 3**

Figure P30.2 shows a top view of a bar that can slide without friction. The resistor is 6.00 Ω and a 2.50-T magnetic field is directed perpendicularly downward, into the paper. Let ℓ = 1.20 m.  
(a) Calculate the applied force required to move the bar to the right at a constant speed of 2.00 m/s.  
(b) At what rate is energy delivered to the resistor?  
![ ](https://hackmd.io/_uploads/B1KG5O-fgl.png)


**Question Translation:**  
(a)求力的大小  

**Solution:**  
(a)  
$$
\mathcal{E} = B \ell v
$$

$$
I = \frac{\mathcal{E}}{R} = \frac{B \ell v}{R}
$$

$$
F = I \ell B = \frac{B^2 \ell^2 v}{R}
$$
$$
F = \frac{(2.50)^2 \cdot (1.20)^2 \cdot 2.00}{6.00} = 3.00\, \text{N}
$$
(b)  
$$
P = I^2 R = \left(\frac{B \ell v}{R}\right)^2 R = \frac{B^2 \ell^2 v^2}{R}
$$

$$
P = \frac{(2.50)^2 \cdot (1.20)^2 \cdot (2.00)^2}{6.00} = 6.00\, \text{W}
$$



---

### **Problem 4**

Two parallel rails with negligible resistance are 10.0 cm apart and are connected by a 5.00-Ω resistor. The circuit also contains two metal rods having resistances of 10.0 Ω and 15.0 Ω sliding along the rails (Fig. P30.3). The rods are pulled away from the resistor at constant speeds of 4.00 m/s and 2.00 m/s, respectively. A uniform magnetic field of magnitude 0.010 0 T is applied perpendicular to the plane of the rails. Determine the current in the 5.00-Ω resistor.  

![ ](https://hackmd.io/_uploads/S1fFadWMge.png)
[解](https://www.doubtnut.com/qna/31091121)

**Question Translation:**  
求 $5.00\Omega$ 電阻中的電流大小與方向。  

**Solution:**  

$\text{棒 1 (10Ω)}: \mathcal{E}_1 = B \ell v_1 = 0.01 \cdot 0.10 \cdot 4.00 = 4.00 \times 10^{-3}\, \text{V}$

$\text{棒 2 (15Ω)}: \mathcal{E}_2 = B \ell v_2 = 0.01 \cdot 0.10 \cdot 2.00 = 2.00 \times 10^{-3}\, \text{V}$

$I=0.15mA\,up$

 

---

### **Problem 5**

A magnetic field directed into the page changes with time according to$B = (0.030 0t^2 + 1.40)T$, where t is in seconds. The field has a circular cross section of radius R = 2.50 cm (Fig. P30.4). What are the magnitude and direction of the electric field at point P1 when t = 3.00 s and r1 = 0.020 0 m?  
[解題影片](https://youtu.be/mRJlU2G37iI)  
![ ](https://hackmd.io/_uploads/rJXY7Fbzee.png)  
**Question Translation:**  
磁場為半徑 $R = 2.50,\text{cm}$ 的圓形區域。
求在 $t = 3.00,\text{s}$ 時，半徑 $r_1 = 2.00,\text{cm}$ 處的電場大小與方向。

**Solution:**  
$$
\oint \vec{E} \cdot d\vec{s} = -\frac{d\Phi_B}{dt}
$$

$$
E \cdot 2\pi r = -\frac{d}{dt} (B \cdot \pi r^2) = -\pi r^2 \cdot \frac{dB}{dt}
$$

$$
E = -\frac{r}{2} \cdot \frac{dB}{dt}
$$
$$
\frac{dB}{dt} = \frac{d}{dt}(0.0300 t^2 + 1.40) = 0.0600 t = 0.0600 \cdot 3.00 = 0.180\,\text{T/s}
$$

$$
E = -\frac{0.0200}{2} \cdot 0.180 = -1.80 \times 10^{-3}\,\text{V/m}
$$
方向：磁場增強，電場逆向產生，順時針。

---

### **Problem 6**

A conducting rectangular loop of mass M, resistance R, and dimensions w by ℓ falls from rest into a magnetic field B as shown in Figure P30.5. During the time interval before the top edge of the loop reaches the field, the loop approaches a terminal speed vT.  
(a) Show that $v_T=\frac{MgR}{B^2w^2}$  
(b) Why is vT proportional to R?  
(c) Why is it inversely proportional to B2?   
 
![ ](https://hackmd.io/_uploads/HJyyDYZMge.png)

[解題影片](https://youtu.be/97ewgbB86JQ)  
**Question Translation:**  
(a) 推導其終端速度 $v_T=\frac{MgR}{B^2w^2}$  

(b) 為何 $v_T$ 與 $R$ 成正比？  

(c) 為何 $v_T$ 與 $B^2$ 成反比？  

**Solution:**  
$$
\mathcal{E} = B w v
$$

$$
I = \frac{\mathcal{E}}{R} = \frac{B w v}{R}
$$

$$
F_B = I w B = \frac{B^2 w^2 v}{R}
$$

$\text{達到終端速度時：} F_B = Mg$

$$
\frac{B^2 w^2 v_T}{R} = Mg \Rightarrow v_T = \frac{MgR}{B^2 w^2}
$$
(b) $v_T \propto R$：電阻大 → 電流小 → 磁阻力小 → 須更大速度產生足夠磁阻力。  
(c) $v_T \propto \frac{1}{B^2}$：磁場強 → 同樣速度產生更大磁阻力 → 須更小速度即可平衡重力。


---

### **Problem 7**

An electron moves through a uniform electric field E = (2.50  i+ 5.00j ) V/m and a uniform magnetic field B = (0.400k )T. Determine the acceleration of the electron when it has a velocity v = 10.0  m/s. 


**Question Translation:**  
一電子在電場 $\vec{E} = (2.50\hat{i} + 5.00\hat{j}),\text{V/m}$ 與磁場 $\vec{B} = (0.400\hat{k}),\text{T}$ 中，具有速度 $\vec{v} = 10.0\hat{i},\text{m/s}$。求其加速度。  

**Solution:**  
$$
\vec{F} = q(\vec{E} + \vec{v} \times \vec{B})
$$

$$
\vec{v} \times \vec{B} = (10.0\hat{i}) \times (0.400\hat{k}) = -4.00\hat{j}
$$

$$
\vec{F} = q[(2.50\hat{i} + 5.00\hat{j}) - 4.00\hat{j}] = q(2.50\hat{i} + 1.00\hat{j})
$$
$$
\vec{a} = \frac{\vec{F}}{m_e} = \frac{-e}{m_e} (2.50\hat{i} + 1.00\hat{j})
$$

$$
a_x = -\frac{1.60 \times 10^{-19} \cdot 2.50}{9.11 \times 10^{-31}} \approx -4.39 \times 10^{11}\,\text{m/s}^2
$$
$$
a_y = -\frac{1.60 \times 10^{-19} \cdot 1.00}{9.11 \times 10^{-31}} \approx -1.76 \times 10^{11}\,\text{m/s}^2
$$


---


