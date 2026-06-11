 > สืบเนื่องจาก [[precalculus]]  
 ---
 
### ทำไมต้องเรียนลิมิต
สมมุติเราอยากหาพื้นที่ใต้กราฟเราก็จะแบ่งพื้นที่ใต้กราฟเป็นแท่งสี่เหลี่ยมเล็กๆเล็กมากๆจน x เข้าใกล้ 0 แต่ไม่เป็น 0 เรา call that $\lim_{ x \to 0 }$ แล้วคำนวณหาพื้นที่

#### 1. An intuitive approach
#### _Ex_ let $f(x)=\frac{x^{2}-2x}{x-2}$ what's value of $f(x)$ when $x$ approaches $2$?
คือถ้าเราแทน 2 ลงไปตรงๆมันก็จะเป็น 0 มันก็จะหาค่าไม่ได้
แต่เขาบอกว่า "approches $2$" คือมันจะเป็นแบบ 1.9999... หรือ 2.0000...1
แล้ว $f(x)$ โดย $x$ เป็น $1.9999...$ หรือ $2.0000...1$

ถ้า $x$ approches $2$ ทางซ้าย ($\lim_{ x \to 2^- }$) 
$$
\begin{array}{c|c}
\text{x} & f(x) \\ \hline
\ 1.9 & 1.9  \\
\ 1.99 & 1.99 \\
\ 1.999 & 1.999 \\
\ 1.9999 & 1.9999 \\
\end{array}
$$
$x\to{2^-}$
$\therefore f(x)\to{2}$ 

ถ้า $x$ approches $2$ ทางขวา ($\lim_{ x \to 2^+ }$) 
$$
\begin{array}{c|c}
\text{x} & f(x) \\ \hline
\ 2.1 & 2.1  \\
\ 2.01 & 2.01 \\
\ 2.001 & 2.001 \\
\ 2.0001 & 2.0001 \\
\end{array}
$$
$x\to{2^+}$
$\therefore f(x)\to{2}$ 
ฉะนั้นเราเลยสรุปได้ว่า $\lim_{ x \to 2 }f(x)=2$ 

---
#### _Ex_  draw the graph of $f(x)=\frac{x^{2}-2x}{x-2}$ 
$$
f(x)=\frac{x^{2}-2x}{x-2}=\frac{x(x-2)}{x-2}=x\tag{$x \neq 2$}
$$
$$
\therefore f(2)=2
$$
มันคือกราฟเส้นตรงหน้าตาแบบนี้
![[desmos-graph.png|208]]
แต่อย่าลืมว่า จุดที่ $x=2$ จะได้ $y=undefine$ ที่ 2 เลยต้องเป็นจุดโปร่ง

---
#### _Ex_ let $f(x)=\frac{\sin x}{x}$ find $\lim_{ x \to 0 } f(x)$
$$
\begin{array}{c|c}
\text{x} & f(x) \\ \hline
\ -0.1 & 0.998334  \\
\ -0.01 & 0.999983 \\
\ -0.001 & 0.999989 \\
\ -0.0001 & 0.999999 \\
\end{array}
$$
$x\to{0^-}$
$\therefore f(x)\to{1}$
$$
\begin{array}{c|c}
\text{x} & f(x) \\ \hline
\ 0.1 & 0.998334  \\
\ 0.01 & 0.999983 \\
\ 0.001 & 0.999989 \\
\ 0.0001 & 0.999999 \\
\end{array}
$$
$x\to{0^+}$
$\therefore f(x)\to{1}$
เราจะได้ $\lim_{ x \to 0} f(x)=1$

---
#### 2. computing limits
**some basic limits
1. $\lim_{ x \to a }k = k$
2. $\lim_{ x \to a }x=a$
3. $\lim_{ x \to a }c_{n}x^n+c_{n-1}x^{n-1}+\dots+c_{1}x^1+c_{0}=c_{n}a^n+c_{n-1}x^{n-1}+\dots+c_{1}x^1+c_{0}$ 
   > $\lim_{ x \to 2 }5x^{2}+3x+1=5(2)^{2}+3(2)+1=27$
4. $\lim_{ x \to 0^+ }\frac{1}{x}=\infty$
5. $\lim_{ x \to 0^- }\frac{1}{x}=-\infty$

**some properties
let a, k be a real number, and suppose that $\lim_{ x \to a }f(x)$
1. $\lim_{ x \to a }[kf(x)]=k\lim_{ x \to a }f(x)$
2. $\lim_{ x \to a }[f(x)+g(x)]=\lim_{ x \to a }f(x)+\lim_{ x \to a }g(x)$
3. $\lim_{ x \to a }[f(x)-g(x)]=\lim_{ x \to a }f(x)-\lim_{ x \to a }g(x)$
4. $\lim_{ x \to a }[f(x) \cdot g(x)]=\lim_{ x \to a }f(x) \cdot \lim_{ x \to a }g(x)$
5. $\lim_{ x \to a }[f(x) / g(x)]=\lim_{ x \to a }f(x) / \lim_{ x \to a }g(x)$
6. $\lim_{ x \to a }[f(x)]^n=[\lim_{ x \to a }f(x)]^n$ 
7. $\lim_{ x \to a } \sqrt[n]{f(x)}= \sqrt[n]{ \lim_{ x \to a }f(x) }$_if x is an odd number_
8. $\lim_{ x \to a } \sqrt[n]{f(x)}= \sqrt[n]{ \lim_{ x \to a }f(x) }$ _if x is an even number and $\lim_{ x \to a }f(x)>0$ **beware_
9. $\lim_{ x \to a }f(x)^{g(x)}=\lim_{ x \to a }f(x)^{\lim_{ x \to a }g(x)}$

Note: limit $\to$ กระจายได้ $+,-,\times,\div,$ยกกำลังเลข,ยกกำลังฟังก์ชัน,รูท
**but รากคู่ ในรากห้ามติดลบ**

---
#### indeterminate forms
$$\frac{0}{0}, \frac{\infty}{\infty}, 0 \times \infty, \infty - \infty, 0^0, 1^\infty, \infty^0$$
เจอแบบนี้ก็ต้องจัดรูป ทำมาแล้วใน [[precalculus]]
$$
\begin{aligned}
\lim_{ h \to 0 }\frac{\sqrt{3+h}-\sqrt{ 3 }}{h} &= \lim_{ h \to 0 }\frac{(3+h)^{1/2}-\sqrt{ 3 }}{h} \\
\ &= \lim_{ h \to 0 } \frac{1}{2}(3+h)^{-\frac{1}{2}} \\
\ &= \frac{1}{2}(3+0)^{-\frac{1}{2}} \\
\ &= \frac{1}{2} \times \frac{1}{3^{1/2}} \\
\ \therefore lim_{ h \to 0 }\frac{\sqrt{3+h}-\sqrt{ 3 }}{h}&= \frac{1}{2\sqrt{ 3 }}
\end{aligned}
$$
อันนี้ลองแก้แบบใช้ lhopital

---
****_Ex_Find $\lim_{ x \to 0^+ }x^{1/x}$
$$
\begin{aligned}
\text{let } y &= x^{1/x} \\
\ln y &= \frac{1}{x} \ln x \\
\lim_{x \to 0^+} \ln y &= \lim_{x \to 0^+} \left( \frac{1}{x} \cdot \ln x \right) \\
&= (\infty) \cdot (-\infty) \\
&= -\infty \\
\therefore \lim_{x \to 0^+} y &= e^{-\infty} = 0
\end{aligned}
$$
