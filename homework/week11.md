# week11

> **定理 4.2.8 (二维波动方程的 Poisson 公式)**
> 
> 若 $\varphi\in{C}^{3}\left(\mathbb{R}^{2}\right)$, $\psi\in{C}^{2}\left(\mathbb{R}^{2}\right)$, 则二维波动方程 Cauchy 问题
> $u_{tt}-a^{2}\Delta{u}=0$, $u\left(x,0\right)=\varphi\left(x\right)$, $u_t\left(x,0\right)=\psi\left(x\right)$ 的解为
> $u\left(x,t\right)=\frac{1}{2\pi{a}}\left[\frac{\partial}{\partial{t}}\int_{B_{at}\left(x\right)}\frac{\varphi\left(y\right)\,\mathrm{d}y}{\sqrt{\left(at\right)^{2}-\left|y-x\right|^{2}}}+\int_{B_{at}\left(x\right)}\frac{\psi\left(y\right)\,\mathrm{d}y}{\sqrt{\left(at\right)^{2}-\left|y-x\right|^{2}}}\right]$ (即公式 (4.2.20)); 其中 $B_{at}\left(x\right)=\left\{y:\left|y-x\right|\le{at}\right\}$.

> **公式 (4.2.17) (三维非齐次波动方程 Cauchy 问题的解)**
> 
> $u\left(x,t\right)=\frac{1}{4\pi{a}^{2}}\int_0^{t}\mathrm{d}\tau\int_{S_{a\left(t-\tau\right)}\left(x\right)}\frac{f\left(y,\tau\right)}{t-\tau}\,\mathrm{d}S_y$.

> **公式 (4.2.22) (二维非齐次波动方程 Cauchy 问题的解)**
> 
> $u\left(x,t\right)=\frac{1}{2\pi{a}}\int_0^{t}\mathrm{d}\tau\int_{B_{a\left(t-\tau\right)}\left(x\right)}\frac{f\left(y,\tau\right)\,\mathrm{d}y}{\sqrt{a^{2}\left(t-\tau\right)^{2}-\left|y-x\right|^{2}}}$.

## 习题 4.9 (二维波动方程的 Cauchy 问题)

求解二维波动方程的 Cauchy 问题:

$$
\begin{cases}u_{tt}-2\Delta{u}=0,&x\in\mathbb{R}^{2},t>0,\\u\left(x,0\right)=u_t\left(x,0\right)=2x_1^{2}-x_2^{2},&x\in\mathbb{R}^{2}.\end{cases}
$$

### 解答 4.9

第一步: 确定参数与求解公式. 这里 $a^{2}=2$, 即 $a=\sqrt{2}$; 记 $f\left(x\right)=2x_1^{2}-x_2^{2}$, 则 $\varphi=\psi=f$. 由**定理 4.2.8 (二维波动方程的 Poisson 公式)**,

$$
u\left(x,t\right)=\frac{1}{2\pi{a}}\left[\frac{\partial}{\partial{t}}I\left(t\right)+I\left(t\right)\right],\qquad{I}\left(t\right)=\int_{B_{at}\left(x\right)}\frac{f\left(y\right)\,\mathrm{d}y}{\sqrt{\left(at\right)^{2}-\left|y-x\right|^{2}}}.\tag{A}
$$

第二步: 把二重积分化为径向积分. 记 $r=at$. 在极坐标 $y=x+\rho{n}$ ($n$ 为单位向量) 下 $\mathrm{d}y=\rho\,\mathrm{d}\rho\,\mathrm{d}\theta$, 故

$$
I\left(t\right)=\int_0^{r}\frac{\rho\,\mathrm{d}\rho}{\sqrt{r^{2}-\rho^{2}}}\int_0^{2\pi}f\left(x+\rho{n}\right)\,\mathrm{d}\theta.\tag{B}
$$

第三步: 算内层的角向平均. 由 $f\left(x\right)=2x_1^{2}-x_2^{2}$,

$$
f\left(x+\rho{n}\right)=2\left(x_1+\rho\cos\theta\right)^{2}-\left(x_2+\rho\sin\theta\right)^{2}.\tag{C}
$$

由 $\int_0^{2\pi}\cos\theta\,\mathrm{d}\theta=\int_0^{2\pi}\sin\theta\,\mathrm{d}\theta=\int_0^{2\pi}\cos\theta\sin\theta\,\mathrm{d}\theta=0$, $\int_0^{2\pi}\cos^{2}\theta\,\mathrm{d}\theta=\int_0^{2\pi}\sin^{2}\theta\,\mathrm{d}\theta=\pi$,

$$
\int_0^{2\pi}f\left(x+\rho{n}\right)\,\mathrm{d}\theta=2\pi\left(2x_1^{2}-x_2^{2}\right)+\rho^{2}\left(2\pi-\pi\right)=2\pi\left(f\left(x\right)+\frac{\rho^{2}}{2}\right).\tag{D}
$$

第四步: 算出 $I\left(t\right)$. 把 (D) 代入 (B),

$$
I\left(t\right)=2\pi\int_0^{r}\frac{\rho\left(f\left(x\right)+\frac{\rho^{2}}{2}\right)}{\sqrt{r^{2}-\rho^{2}}}\,\mathrm{d}\rho=2\pi\left[f\left(x\right)\int_0^{r}\frac{\rho\,\mathrm{d}\rho}{\sqrt{r^{2}-\rho^{2}}}+\frac{1}{2}\int_0^{r}\frac{\rho^{3}\,\mathrm{d}\rho}{\sqrt{r^{2}-\rho^{2}}}\right].\tag{E}
$$

第五步: 算两个标准积分. 作替换 $\rho=r\sin\varphi$,

$$
\int_0^{r}\frac{\rho\,\mathrm{d}\rho}{\sqrt{r^{2}-\rho^{2}}}=r,\qquad\int_0^{r}\frac{\rho^{3}\,\mathrm{d}\rho}{\sqrt{r^{2}-\rho^{2}}}=r^{3}\int_0^{\frac{\pi}{2}}\sin^{3}\varphi\,\mathrm{d}\varphi=\frac{2}{3}r^{3},\tag{F}
$$

其中用到 $\int_0^{\frac{\pi}{2}}\sin^{3}\varphi\,\mathrm{d}\varphi=\frac{2}{3}$.

第六步: 代入得 $I$ 的显式. 由 (E)(F) 与 $r=at$,

$$
I\left(t\right)=2\pi\left[f\left(x\right)at+\frac{1}{2}\cdot\frac{2}{3}a^{3}t^{3}\right]=2\pi\left(f\left(x\right)at+\frac{a^{3}t^{3}}{3}\right).\tag{G}
$$

第七步: 求导并合并. 由 (G), $\frac{\partial}{\partial{t}}I\left(t\right)=2\pi\left(f\left(x\right)a+a^{3}t^{2}\right)$. 代入 (A),

$$
u\left(x,t\right)=\frac{1}{2\pi{a}}\cdot2\pi\left[a\left(1+t\right)f\left(x\right)+a^{3}t^{2}+\frac{a^{3}t^{3}}{3}\right]=\left(1+t\right)f\left(x\right)+a^{2}t^{2}+\frac{a^{2}t^{3}}{3}.\tag{H}
$$

第八步: 代入 $a^{2}=2$ 得结论,

$$
u\left(x,t\right)=\left(1+t\right)\left(2x_1^{2}-x_2^{2}\right)+2t^{2}+\frac{2}{3}t^{3}.\tag{I}
$$

第九步: 直接验证. 由 (I), $u\left(x,0\right)=f\left(x\right)$, $u_t\left(x,t\right)=f\left(x\right)+4t+2t^{2}$, 故 $u_t\left(x,0\right)=f\left(x\right)$; 又 $\partial_t^{2}u=4+4t$, 而 $\Delta{u}=\Delta\left[\left(1+t\right)f\right]=\left(1+t\right)\left(4-2\right)=2\left(1+t\right)$, 故 $a^{2}\Delta{u}=2\cdot2\left(1+t\right)=4+4t=\partial_t^{2}u$, 方程成立.

## 习题 4.10 (二维非齐次方程求解公式的证明)

模仿求解公式 (4.2.17) 的推导过程, 利用齐次化原理, 证明 (4.2.22) 式成立.

### 解答 4.10

第一步: 写出齐次化原理的表述. 对二维非齐次方程 Cauchy 问题

$$
\begin{cases}u_{tt}-a^{2}\Delta{u}=f\left(x,t\right),&x\in\mathbb{R}^{2},t>0,\\u\left(x,0\right)=u_t\left(x,0\right)=0,&x\in\mathbb{R}^{2}\end{cases}\tag{A}
$$

由齐次化原理, 其解可表示为

$$
u\left(x,t\right)=\int_0^{t}w\left(x,t;\tau\right)\,\mathrm{d}\tau,\tag{B}
$$

其中对每个参数 $\tau\in\left[0,t\right]$, $w\left(\cdot,\cdot;\tau\right)$ 是齐次方程的 Cauchy 问题

$$
\begin{cases}w_{tt}-a^{2}\Delta{w}=0,&x\in\mathbb{R}^{2},t>\tau,\\w\left(x,\tau;\tau\right)=0,\quad{w}_t\left(x,\tau;\tau\right)=f\left(x,\tau\right),&x\in\mathbb{R}^{2}\end{cases}\tag{C}
$$

的解.

第二步: 作时间平移把 (C) 化为标准形式. 令 $s=t-\tau$, $\tilde{w}\left(x,s\right)=w\left(x,\tau+s;\tau\right)$, 则 (C) 等价于

$$
\begin{cases}\tilde{w}_{ss}-a^{2}\Delta\tilde{w}=0,&x\in\mathbb{R}^{2},s>0,\\\tilde{w}\left(x,0\right)=0,\quad\tilde{w}_s\left(x,0\right)=f\left(x,\tau\right),&x\in\mathbb{R}^{2}.\end{cases}\tag{D}
$$

第三步: 对 (D) 用二维 Poisson 公式. 由**定理 4.2.8 (二维波动方程的 Poisson 公式)**, 取 $\varphi=0$, $\psi=f\left(\cdot,\tau\right)$,

$$
\tilde{w}\left(x,s\right)=\frac{1}{2\pi{a}}\int_{B_{as}\left(x\right)}\frac{f\left(y,\tau\right)\,\mathrm{d}y}{\sqrt{\left(as\right)^{2}-\left|y-x\right|^{2}}}.\tag{E}
$$

第四步: 回到 $w$. 把 $s=t-\tau$ 代回,

$$
w\left(x,t;\tau\right)=\frac{1}{2\pi{a}}\int_{B_{a\left(t-\tau\right)}\left(x\right)}\frac{f\left(y,\tau\right)\,\mathrm{d}y}{\sqrt{a^{2}\left(t-\tau\right)^{2}-\left|y-x\right|^{2}}}.\tag{F}
$$

第五步: 代入 (B) 得 (4.2.22). 把 (F) 代入 (B),

$$
u\left(x,t\right)=\frac{1}{2\pi{a}}\int_0^{t}\mathrm{d}\tau\int_{B_{a\left(t-\tau\right)}\left(x\right)}\frac{f\left(y,\tau\right)\,\mathrm{d}y}{\sqrt{a^{2}\left(t-\tau\right)^{2}-\left|y-x\right|^{2}}},\tag{G}
$$

这正是**公式 (4.2.22) (二维非齐次波动方程 Cauchy 问题的解)**, 即所要证明的式子.

第六步: 说明与 (4.2.17) 推导的平行性. 三维情形里用的是三维 Poisson 公式与球面积分 (得到**公式 (4.2.17)**); 二维情形里只要把球面 $S_{a\left(t-\tau\right)}$ 换成圆盘 $B_{a\left(t-\tau\right)}$, 把面积分换成带权 $\frac{1}{\sqrt{a^{2}\left(t-\tau\right)^{2}-\left|y-x\right|^{2}}}$ 的重积分, 其余步骤 (齐次化原理, 时间平移, 累加) 完全相同.

## 习题 4.11 (分离变量法求解弦振动初边值问题)

用分离变量法求解弦振动方程初边值问题

$$
\begin{cases}u_{tt}-a^{2}u_{xx}=0,&0<{}x<{}l,t>0,\\u\left(x,0\right)=A\sin\frac{m\pi{x}}{l},\quad{u}_t\left(x,0\right)=u_0,&0\le{x}\le{l},\\u\left(0,t\right)=u\left(l,t\right)=0,&t\ge0,\end{cases}
$$

其中 $m$ 是正整数, $A,u_0$ 为常数.

### 解答 4.11

第一步: 分离变量. 设 $u\left(x,t\right)=X\left(x\right)T\left(t\right)$, 代入方程得 $\frac{T''}{a^{2}T}=\frac{X''}{X}=-\lambda$, 即

$$
X''+\lambda{X}=0,\quad{X}\left(0\right)=X\left(l\right)=0;\qquad{T}''+a^{2}\lambda{T}=0.\tag{A}
$$

第二步: 解特征值问题. (A) 中空间问题的特征值为 $\lambda_n=\left(\frac{n\pi}{l}\right)^{2}$, 特征函数

$$
X_n\left(x\right)=\sin\frac{n\pi{x}}{l},\qquad{n}=1,2,\dots\tag{B}
$$

第三步: 写出通解形式. 对每个 $n$, 时间方程为 $T_n''+\omega_n^{2}T_n=0$, $\omega_n=\frac{n\pi{a}}{l}$, 故

$$
u\left(x,t\right)=\sum_{n=1}^{\infty}\left(C_n\cos\omega_nt+D_n\sin\omega_nt\right)\sin\frac{n\pi{x}}{l}.\tag{C}
$$

第四步: 用第一个初值定 $C_n$. 由 $u\left(x,0\right)=A\sin\frac{m\pi{x}}{l}$,

$$
\sum_{n=1}^{\infty}C_n\sin\frac{n\pi{x}}{l}=A\sin\frac{m\pi{x}}{l}.\tag{D}
$$

由正弦系 $\left\{\sin\frac{n\pi{x}}{l}\right\}$ 在 $\left[0,l\right]$ 上的正交性 (即把右端按此系展开), 得

$$
C_m=A,\qquad{C}_n=0\,\left(n\ne{m}\right).\tag{E}
$$

第五步: 用第二个初值定 $D_n$. 对 (C) 关于 $t$ 求导并令 $t=0$,

$$
\sum_{n=1}^{\infty}\omega_nD_n\sin\frac{n\pi{x}}{l}=u_0.\tag{F}
$$

把常数 $u_0$ 在 $\left[0,l\right]$ 上按正弦系展开, $\omega_nD_n=\frac{2}{l}\int_0^{l}u_0\sin\frac{n\pi{x}}{l}\,\mathrm{d}x$, 而

$$
\int_0^{l}\sin\frac{n\pi{x}}{l}\,\mathrm{d}x=\frac{l}{n\pi}\left(1-\cos{n}\pi\right)=\frac{l}{n\pi}\left(1-\left(-1\right)^{n}\right).\tag{G}
$$

第六步: 解出 $D_n$. 由 (F)(G),

$$
D_n=\frac{2u_0}{n\pi\omega_n}\left(1-\left(-1\right)^{n}\right)=\frac{2u_0l}{n^{2}\pi^{2}a}\left(1-\left(-1\right)^{n}\right),\tag{H}
$$

即 $n$ 为偶数时 $D_n=0$, $n=2k+1$ 时 $D_{2k+1}=\frac{4u_0l}{\left(2k+1\right)^{2}\pi^{2}a}$.

第七步: 写出解. 把 (E)(H) 代入 (C),

$$
u\left(x,t\right)=A\cos\frac{m\pi{a}t}{l}\sin\frac{m\pi{x}}{l}+\sum_{k=0}^{\infty}\frac{4u_0l}{\left(2k+1\right)^{2}\pi^{2}a}\sin\frac{\left(2k+1\right)\pi{a}t}{l}\sin\frac{\left(2k+1\right)\pi{x}}{l}.\tag{I}
$$

第八步: 核对初值与边界条件. (I) 中每一项都含因子 $\sin\frac{n\pi{x}}{l}$, 故 $u\left(0,t\right)=u\left(l,t\right)=0$; 又当 $t=0$ 时 (I) 化为 $A\sin\frac{m\pi{x}}{l}$ (第二项含 $\sin0=0$), 而关于 $t$ 求导后令 $t=0$ 得 $\sum_{k\ge0}\frac{4u_0}{\left(2k+1\right)\pi}\times$ $\sin\frac{\left(2k+1\right)\pi{x}}{l}$, 这正是常数 $u_0$ 在 $\left(0,l\right)$ 上的正弦级数展开 (其和为 $u_0$, $0<{}x<{}l$). 故 (I) 是所求的解.

## 习题 4.12 (带非齐次项的弦振动初边值问题)

用分离变量法求解弦振动方程初边值问题

$$
\begin{cases}u_{tt}-a^{2}u_{xx}=b\sinh{x},&0<{}x<{}l,t>0,\\u\left(x,0\right)=u_t\left(x,0\right)=0,&0\le{x}\le{l},\\u\left(0,t\right)=u\left(l,t\right)=0,&t\ge0,\end{cases}
$$

其中 $b$ 是正常数.

### 解答 4.12

第一步: 把非齐次项按特征函数展开. 设

$$
u\left(x,t\right)=\sum_{n=1}^{\infty}T_n\left(t\right)\sin\frac{n\pi{x}}{l},\qquad{b}\sinh{x}=\sum_{n=1}^{\infty}b_n\sin\frac{n\pi{x}}{l},\tag{A}
$$

其中 (由正弦系的正交性)

$$
b_n=\frac{2}{l}\int_0^{l}b\sinh{x}\sin\frac{n\pi{x}}{l}\,\mathrm{d}x.\tag{B}
$$

第二步: 定 $b_n$. 记 $k=\frac{n\pi}{l}$, 由分部积分

$$
\int\sinh{x}\sin{kx}\,\mathrm{d}x=\frac{\cosh{x}\sin{kx}-k\sinh{x}\cos{kx}}{1+k^{2}}.\tag{C}
$$

第三步: 代入上下限. 由 $\sin0=\sin{n}\pi=0$, $\cos0=1$, $\cos{n}\pi=\left(-1\right)^{n}$, $\sinh0=0$,

$$
\int_0^{l}\sinh{x}\sin\frac{n\pi{x}}{l}\,\mathrm{d}x=0-\frac{k\sinh{l}\cdot\left(-1\right)^{n}}{1+k^{2}}-0=\frac{k\sinh{l}\left(-1\right)^{n+1}}{1+k^{2}}.\tag{D}
$$

第四步: 写出 $b_n$ 的显式. 由 (B)(D),

$$
b_n=\frac{2b}{l}\cdot\frac{\frac{n\pi}{l}\sinh{l}\left(-1\right)^{n+1}}{1+\left(\frac{n\pi}{l}\right)^{2}}=\frac{2bn\pi\sinh{l}\left(-1\right)^{n+1}}{l^{2}+n^{2}\pi^{2}}.\tag{E}
$$

第五步: 得到 $T_n$ 的方程. 把 (A) 代入方程并用正弦系逐项比较,

$$
T_n''+\omega_n^{2}T_n=b_n,\qquad\omega_n=\frac{n\pi{a}}{l};\tag{F}
$$

由初值条件 $u\left(x,0\right)=u_t\left(x,0\right)=0$ 得 $T_n\left(0\right)=T_n'\left(0\right)=0$.

第六步: 解常微分方程 (F). 常微分方程的一个特解是 $T_n=\frac{b_n}{\omega_n^{2}}$ (因右端为常数), 通解为

$$
T_n\left(t\right)=\frac{b_n}{\omega_n^{2}}+P_n\cos\omega_nt+Q_n\sin\omega_nt.\tag{G}
$$

第七步: 定常数. 由 $T_n\left(0\right)=0$ 得 $P_n=-\frac{b_n}{\omega_n^{2}}$; 由 $T_n'\left(0\right)=0$ 得 $Q_n=0$. 故

$$
T_n\left(t\right)=\frac{b_n}{\omega_n^{2}}\left(1-\cos\omega_nt\right).\tag{H}
$$

第八步: 代入数据化简. 由 (E)(H) 与 $\omega_n^{2}=\frac{n^{2}\pi^{2}a^{2}}{l^{2}}$,

$$
\frac{b_n}{\omega_n^{2}}=\frac{2bn\pi\sinh{l}\left(-1\right)^{n+1}}{l^{2}+n^{2}\pi^{2}}\cdot\frac{l^{2}}{n^{2}\pi^{2}a^{2}}=\frac{2bl^{2}\sinh{l}\left(-1\right)^{n+1}}{n\pi\left(l^{2}+n^{2}\pi^{2}\right)a^{2}}.\tag{I}
$$

第九步: 写出解. 把 (I) 代入 (A),

$$
u\left(x,t\right)=\sum_{n=1}^{\infty}\frac{2bl^{2}\sinh{l}\left(-1\right)^{n+1}}{n\pi\left(l^{2}+n^{2}\pi^{2}\right)a^{2}}\left(1-\cos\frac{n\pi{a}t}{l}\right)\sin\frac{n\pi{x}}{l}.\tag{J}
$$

第十步: 核对条件. 每一项都含 $\sin\frac{n\pi{x}}{l}$, 故 $u\left(0,t\right)=u\left(l,t\right)=0$; 又 $1-\cos\omega_nt$ 在 $t=0$ 处及其导数的零点均为零, 故 $u\left(x,0\right)=u_t\left(x,0\right)=0$; 而逐项代入方程时 $T_n$ 满足 (F), 故方程成立. 于是 (J) 是所求的解.
