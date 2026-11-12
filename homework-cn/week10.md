# week10

> **定理 4.2.2 (d'Alembert 公式)**
> 
> 若 $\varphi\in{C}^{2}\left(\left(-\infty,+\infty\right)\right)$, $\psi\in{C}^{1}\left(\left(-\infty,+\infty\right)\right)$, 则由
> $u\left(x,t\right)=\frac{1}{2}\left(\varphi\left(x+at\right)+\varphi\left(x-at\right)\right)+\frac{1}{2a}\int_{x-at}^{x+at}\psi\left(s\right)\,\mathrm{d}s$ (即公式 (4.2.9))
> 给出的 $u\in{C}^{2}\left(\left(-\infty,+\infty\right)\times\left[0,+\infty\right)\right)$ 是无界弦自由振动 Cauchy 问题 $u_{tt}-a^{2}u_{xx}=0$, $u\left(x,0\right)=\varphi\left(x\right)$, $u_t\left(x,0\right)=\psi\left(x\right)$ 的解.

> **定义 4.2.4 (球面平均函数)**
> 
> 设 $w\in{C}^{0}\left(\mathbb{R}^{3}\right)$, 定义其球面平均函数 $w_B\left(x,r\right)=\frac{1}{4\pi{r}^{2}}\int_{S_r\left(x\right)}w\left(y\right)\,\mathrm{d}S_y=\frac{1}{4\pi}\int_{\left|n\right|=1}w\left(x+rn\right)\,\mathrm{d}S_n$.

> **定理 4.2.6 (三维波动方程的 Poisson 公式)**
> 
> 设 $\varphi\in{C}^{3}\left(\mathbb{R}^{3}\right)$, $\psi\in{C}^{2}\left(\mathbb{R}^{3}\right)$, 则三维波动方程 Cauchy 问题的解为
> $u\left(x,t\right)=\frac{\partial}{\partial{t}}\left(t\varphi_B\left(x,at\right)\right)+t\psi_B\left(x,at\right)$, 即公式 (4.2.15)
> $u\left(x,t\right)=\frac{1}{4\pi{a}^{2}}\left[\frac{\partial}{\partial{t}}\left(\frac{1}{t}\int_{S_{at}\left(x\right)}\varphi\left(y\right)\,\mathrm{d}S_y\right)+\frac{1}{t}\int_{S_{at}\left(x\right)}\psi\left(y\right)\,\mathrm{d}S_y\right]$.

> **公式 (4.2.17) (三维非齐次波动方程 Cauchy 问题的解)**
> 
> $u\left(x,t\right)=\frac{1}{4\pi{a}^{2}}\int_0^{t}\mathrm{d}\tau\int_{S_{a\left(t-\tau\right)}\left(x\right)}\frac{f\left(y,\tau\right)}{t-\tau}\,\mathrm{d}S_y$.

## 习题 4.5 (非齐次弦振动方程的 Cauchy 问题)

求解非齐次弦振动方程的 Cauchy 问题

$$
\begin{cases}u_{tt}-a^{2}u_{xx}=\frac{xt}{\left(1+x^{2}\right)^{2}},&-\infty<{}x<+\infty,t>0,\\u\left(x,0\right)=0,\quad{u}_t\left(x,0\right)=\frac{1}{1+x^{2}},&-\infty<{}x<+\infty.\end{cases}
$$

### 解答 4.5

第一步: 用叠加原理分解问题. 令 $u=u_1+u_2$, 其中 $u_1$ 是齐次方程的 Cauchy 问题

$$
\begin{cases}\left(u_1\right)_{tt}-a^{2}\left(u_1\right)_{xx}=0,\\u_1\left(x,0\right)=0,\quad\left(u_1\right)_t\left(x,0\right)=\frac{1}{1+x^{2}}\end{cases}\tag{A}
$$

的解, $u_2$ 是非齐次方程带零初值的 Cauchy 问题

$$
\begin{cases}\left(u_2\right)_{tt}-a^{2}\left(u_2\right)_{xx}=\frac{xt}{\left(1+x^{2}\right)^{2}},\\u_2\left(x,0\right)=\left(u_2\right)_t\left(x,0\right)=0\end{cases}\tag{B}
$$

的解. 由线性, $u_1+u_2$ 就是原问题的解.

第二步: 用**定理 4.2.2 (d'Alembert 公式)** 求 $u_1$. 此时 $\varphi=0$, $\psi\left(s\right)=\frac{1}{1+s^{2}}$,

$$
u_1\left(x,t\right)=\frac{1}{2a}\int_{x-at}^{x+at}\frac{\mathrm{d}s}{1+s^{2}}=\frac{1}{2a}\left(\arctan\left(x+at\right)-\arctan\left(x-at\right)\right).\tag{C}
$$

第三步: 对 (B) 用齐次化原理. 齐次化原理给出

$$
u_2\left(x,t\right)=\frac{1}{2a}\int_0^{t}\mathrm{d}\tau\int_{x-a\left(t-\tau\right)}^{x+a\left(t-\tau\right)}\frac{s\tau}{\left(1+s^{2}\right)^{2}}\,\mathrm{d}s.\tag{D}
$$

第四步: 算内层积分. 由 $\frac{\mathrm{d}}{\mathrm{d}s}\left(-\frac{1}{2\left(1+s^{2}\right)}\right)=\frac{s}{\left(1+s^{2}\right)^{2}}$,

$$
\int_{x-a\left(t-\tau\right)}^{x+a\left(t-\tau\right)}\frac{s\,\mathrm{d}s}{\left(1+s^{2}\right)^{2}}=-\frac{1}{2\left(1+\left(x+a\left(t-\tau\right)\right)^{2}\right)}+\frac{1}{2\left(1+\left(x-a\left(t-\tau\right)\right)^{2}\right)}.\tag{E}
$$

第五步: 代入 (D). 记 $g\left(s\right)=\frac{1}{1+s^{2}}$, 把 (E) 代入 (D),

$$
u_2\left(x,t\right)=\frac{1}{4a}\int_0^{t}\tau\left[g\left(x-a\left(t-\tau\right)\right)-g\left(x+a\left(t-\tau\right)\right)\right]\mathrm{d}\tau.\tag{F}
$$

第六步: 算两个基本积分. 令 $r=t-\tau$, 则 $\tau=t-r$, $\mathrm{d}\tau=-\mathrm{d}r$, 于是

$$
\int_0^{t}\tau\,g\left(x\pm{a}\left(t-\tau\right)\right)\mathrm{d}\tau=\int_0^{t}\left(t-r\right)g\left(x\pm{a}r\right)\,\mathrm{d}r.\tag{G}
$$

对第一类积分作变量替换 $u=x+ar$,

$$
\int_0^{t}\left(t-r\right)\frac{\mathrm{d}r}{1+\left(x+ar\right)^{2}}=\frac{1}{a}\int_{x}^{x+at}\left(t+\frac{x}{a}-\frac{u}{a}\right)\frac{\mathrm{d}u}{1+u^{2}},\tag{H}
$$

于是用 $\int\frac{\mathrm{d}u}{1+u^{2}}=\arctan{u}$ 与 $\int\frac{u\,\mathrm{d}u}{1+u^{2}}=\frac{1}{2}\ln\left(1+u^{2}\right)$,

$$
\int_0^{t}\left(t-r\right)g\left(x+ar\right)\,\mathrm{d}r=\frac{1}{a}\left(t+\frac{x}{a}\right)\left(\arctan\left(x+at\right)-\arctan{x}\right)-\frac{1}{2a^{2}}\ln\frac{1+\left(x+at\right)^{2}}{1+x^{2}}.\tag{I}
$$

第七步: 同样算出 $x-ar$ 那一项. 作 $u=x-ar$,

$$
\int_0^{t}\left(t-r\right)\frac{\mathrm{d}r}{1+\left(x-ar\right)^{2}}=\frac{1}{a}\int_{x-at}^{x}\left(t-\frac{x}{a}+\frac{u}{a}\right)\frac{\mathrm{d}u}{1+u^{2}},\tag{J}
$$

$$
\int_0^{t}\left(t-r\right)g\left(x-ar\right)\,\mathrm{d}r=\frac{1}{a}\left(t-\frac{x}{a}\right)\left(\arctan{x}-\arctan\left(x-at\right)\right)+\frac{1}{2a^{2}}\ln\frac{1+x^{2}}{1+\left(x-at\right)^{2}}.\tag{K}
$$

第八步: 代入 (F) 并整理. 记

$$
D=\arctan\left(x+at\right)-\arctan\left(x-at\right),\qquad{P}=2\arctan{x}-\arctan\left(x+at\right)-\arctan\left(x-at\right),\tag{L}
$$

则 $\left(\arctan\left(x+at\right)-\arctan{x}\right)+\left(\arctan{x}-\arctan\left(x-at\right)\right)=D$,
$\left(\arctan{x}-\arctan\left(x-at\right)\right)-\left(\arctan\left(x+at\right)-\arctan{x}\right)=P$, 且 (I)(K) 中的两个对数项相加后为 $\ln\frac{1+\left(x+at\right)^{2}}{1+\left(x-at\right)^{2}}$. 于是

$$
u_2\left(x,t\right)=\frac{1}{4a}\left[\frac{tP-\frac{x}{a}D}{a}+\frac{1}{2a}\ln\frac{1+\left(x+at\right)^{2}}{1+\left(x-at\right)^{2}}\right].\tag{M}
$$

第九步: 合并得解. 由 (C)(M),

$$
u\left(x,t\right)=\frac{D}{2a}+\frac{tP}{4a^{2}}-\frac{xD}{4a^{3}}+\frac{1}{8a^{3}}\ln\frac{1+\left(x+at\right)^{2}}{1+\left(x-at\right)^{2}},\tag{N}
$$

其中 $D,P$ 由 (L) 给出.

第十步: 验证初值. 在 $t=0$ 时 $D=0$, $P=0$, 对数项为零, 故 $u\left(x,0\right)=0$. 关于 $t$ 求导后令 $t=0$: 由 (C), $u_1$ 的贡献为 $\frac{1}{2a}\left(a\frac{1}{1+x^{2}}+a\frac{1}{1+x^{2}}\right)=\frac{1}{1+x^{2}}$; 由 (M), $P$ 与 $D$ 在 $t=0$ 处为零而 $P_t$, $D_t$ 项自动消失, 对数项的贡献为

$$
\frac{1}{8a^{3}}\left.\left(\frac{2a\left(x+at\right)}{1+\left(x+at\right)^{2}}+\frac{2a\left(x-at\right)}{1+\left(x-at\right)^{2}}\right)\right|_{t=0}=\frac{x}{2a^{2}\left(1+x^{2}\right)},
$$

而 $-\frac{xD}{4a^{3}}$ 的导数在 $t=0$ 处为 $-\frac{x}{4a^{3}}\cdot{2a}\cdot\frac{1}{1+x^{2}}=-\frac{x}{2a^{2}\left(1+x^{2}\right)}$, 两项相消. 故 $u_t\left(x,0\right)=\frac{1}{1+x^{2}}$, 与题设相符.

## 习题 4.6 (球面波问题解的验证)

证明: 球面波问题

$$
\begin{cases}u_{tt}-a^{2}\Delta{u}=0,&x\in\mathbb{R}^{3},t>0,\\u\left(x,0\right)=\varphi\left(r\right),\quad{u}_t\left(x,0\right)=\psi\left(r\right),&x\in\mathbb{R}^{3}\end{cases}
$$

的解为

$$
u\left(r,t\right)=\begin{cases}\frac{1}{2r}\left(\left(r+at\right)\varphi\left(r+at\right)+\left(r-at\right)\varphi\left(r-at\right)\right)+\frac{1}{2ar}\int_{r-at}^{r+at}\rho\psi\left(\rho\right)\,\mathrm{d}\rho,&r>at,\\\frac{1}{2r}\left(\left(r+at\right)\varphi\left(r+at\right)-\left(at-r\right)\varphi\left(at-r\right)\right)+\frac{1}{2ar}\int_{at-r}^{at+r}\rho\psi\left(\rho\right)\,\mathrm{d}\rho,&r<{}at,\end{cases}
$$

其中 $r=\left|x\right|$.

### 解答 4.6

第一步: 把三维径向问题化为一维问题. 记 $r=\left|x\right|$, 设 $u=u\left(r,t\right)$. 由径向对称, $\nabla{u}=u_r\frac{x}{r}$, 于是

$$
\Delta{u}=u_{rr}+\frac{2}{r}u_r=\frac{1}{r}\left(\partial_r^{2}\left(ru\right)\right).\tag{A}
$$

第二步: 引入 $v=ru$. 由 (A),

$$
\left(ru\right)_{tt}=r{u}_{tt}=a^{2}r\Delta{u}=a^{2}\partial_r^{2}\left(ru\right),\qquad\text{即}\;\;v_{tt}-a^{2}v_{rr}=0.\tag{B}
$$

第三步: 写出 $v$ 的初值. 由 $u\left(x,0\right)=\varphi\left(r\right)$, $u_t\left(x,0\right)=\psi\left(r\right)$,

$$
v\left(r,0\right)=r\varphi\left(r\right),\qquad{v}_t\left(r,0\right)=r\psi\left(r\right),\qquad{r}>0.\tag{C}
$$

第四步: 把初值奇延拓到 $r<0$. 定义

$$
\Phi\left(r\right)=\begin{cases}r\varphi\left(r\right),&r>0,\\r\varphi\left(-r\right),&r<0,\end{cases}\qquad\Psi\left(r\right)=\begin{cases}r\psi\left(r\right),&r>0,\\r\psi\left(-r\right),&r<0.\end{cases}\tag{D}
$$

注意 $r<0$ 时 $r\varphi\left(-r\right)=-\left(-r\right)\varphi\left(-r\right)$, 故 $\Phi,\Psi$ 是奇函数: $\Phi\left(-r\right)=-\Phi\left(r\right)$, $\Psi\left(-r\right)=-\Psi\left(r\right)$, 且由 $\varphi,\psi$ 的光滑性它们在全轴 $C^{2}$, $C^{1}$.

第五步: 对全轴的 $v$ 用 d'Alembert 公式. 把 (B)(C) 的解按 (D) 延拓为全轴问题, 由**定理 4.2.2 (d'Alembert 公式)**,

$$
v\left(r,t\right)=\frac{1}{2}\left(\Phi\left(r+at\right)+\Phi\left(r-at\right)\right)+\frac{1}{2a}\int_{r-at}^{r+at}\Psi\left(\rho\right)\,\mathrm{d}\rho,\qquad{r}\ge0.\tag{E}
$$

第六步: 情形 $r>at$. 此时 $r\pm{a}t>0$, 由 (D),

$$
\Phi\left(r+at\right)=\left(r+at\right)\varphi\left(r+at\right),\qquad\Phi\left(r-at\right)=\left(r-at\right)\varphi\left(r-at\right);
$$

又积分区间 $\left[r-at,r+at\right]\subset\left(0,+\infty\right)$, 故 $\Psi\left(\rho\right)=\rho\psi\left(\rho\right)$. 代入 (E) 并除以 $r$,

$$
u\left(r,t\right)=\frac{v\left(r,t\right)}{r}=\frac{1}{2r}\left(\left(r+at\right)\varphi\left(r+at\right)+\left(r-at\right)\varphi\left(r-at\right)\right)+\frac{1}{2ar}\int_{r-at}^{r+at}\rho\psi\left(\rho\right)\,\mathrm{d}\rho.\tag{F}
$$

第七步: 情形 $r<{}at$. 此时 $r-at<0$, $r+at>0$, 故

$$
\Phi\left(r+at\right)=\left(r+at\right)\varphi\left(r+at\right),\qquad\Phi\left(r-at\right)=r\varphi\left(at-r\right)=-\left(at-r\right)\varphi\left(at-r\right).\tag{G}
$$

第八步: 算这一情形的积分项. 由 $r<{}at$,

$$
\int_{r-at}^{r+at}\Psi\left(\rho\right)\,\mathrm{d}\rho=\int_{r-at}^{0}\Psi\,\mathrm{d}\rho+\int_0^{r+at}\Psi\,\mathrm{d}\rho.\tag{H}
$$

在第一段作替换 $\rho=-s$ ($s$ 从 $at-r$ 到 $0$), 用 $\Psi\left(-s\right)=-\Psi\left(s\right)=-s\psi\left(s\right)$,

$$
\int_{r-at}^{0}\Psi\left(\rho\right)\,\mathrm{d}\rho=\int_{at-r}^{0}\left(-\Psi\left(s\right)\right)\left(-\mathrm{d}s\right)=-\int_0^{at-r}s\psi\left(s\right)\,\mathrm{d}s.\tag{I}
$$

又第二段为 $\int_0^{r+at}\rho\psi\left(\rho\right)\mathrm{d}\rho$. 故 (H) 等于

$$
\int_{at-r}^{r+at}\rho\psi\left(\rho\right)\,\mathrm{d}\rho=\int_{at-r}^{at+r}\rho\psi\left(\rho\right)\,\mathrm{d}\rho.\tag{J}
$$

第九步: 合并. 把 (G)(J) 代入 (E) 并除以 $r$,

$$
u\left(r,t\right)=\frac{1}{2r}\left(\left(r+at\right)\varphi\left(r+at\right)-\left(at-r\right)\varphi\left(at-r\right)\right)+\frac{1}{2ar}\int_{at-r}^{at+r}\rho\psi\left(\rho\right)\,\mathrm{d}\rho,\qquad{r}<{}at.\tag{K}
$$

第十步: 结论. (F) 与 (K) 正是题目给出的分段表达式, 故球面波问题的解确如题所述.

## 习题 4.7 (三维波动方程的 Cauchy 问题)

求解下述三维波动方程的 Cauchy 问题

$$
\begin{cases}u_{tt}-a^{2}\Delta{u}=0,&x\in\mathbb{R}^{3},t>0,\\u\left(x,0\right)=x_1^{2}+x_2^{2}x_3,\quad{u}_t\left(x,0\right)=0,&x\in\mathbb{R}^{3}.\end{cases}
$$

### 解答 4.7

第一步: 写出求解公式. 由**定理 4.2.6 (三维波动方程的 Poisson 公式)**, 取 $\varphi=x_1^{2}+x_2^{2}x_3$, $\psi=0$,

$$
u\left(x,t\right)=\frac{\partial}{\partial{t}}\left(t\varphi_B\left(x,at\right)\right),\tag{A}
$$

其中 $\varphi_B$ 是由**定义 4.2.4 (球面平均函数)** 给出的球面平均.

第二步: 准备三条球面积分公式. 记 $S_r\left(x\right)=\left\{y:\left|y-x\right|=r\right\}$. 由球面的旋转对称性, 对 $i,j,k\in\left\{1,2,3\right\}$,

$$
\int_{S_r\left(x\right)}\left(y_i-x_i\right)\mathrm{d}S=0,\qquad\int_{S_r\left(x\right)}\left(y_i-x_i\right)\left(y_j-x_j\right)\mathrm{d}S=\frac{4\pi{r}^{4}}{3}\delta_{ij},\tag{B}
$$

$$
\int_{S_r\left(x\right)}\left(y_i-x_i\right)\left(y_j-x_j\right)\left(y_k-x_k\right)\mathrm{d}S=0.\tag{C}
$$

(B) 的第二式来自: 三个二阶矩由对称性相等, 而其和等于 $\int_{S_r}\left|y-x\right|^{2}\mathrm{d}S=r^{2}\cdot4\pi{r}^{2}=4\pi{r}^{4}$; (C) 来自关于 $y_k-x_k$ 的奇对称.

第三步: 算 $\varphi$ 的球面平均. 令 $y=x+n$, $\left|n\right|=r$, 则

$$
\varphi\left(y\right)=y_1^{2}+y_2^{2}y_3=\left(x_1+n_1\right)^{2}+\left(x_2+n_2\right)^{2}\left(x_3+n_3\right).\tag{D}
$$

第四步: 逐项展开并对球面积分. 由 (B)(C),

$$
\int_{S_r}\left(x_1+n_1\right)^{2}\mathrm{d}S=4\pi{r}^{2}x_1^{2}+\int_{S_r}n_1^{2}\mathrm{d}S=4\pi{r}^{2}x_1^{2}+\frac{4\pi{r}^{4}}{3},\tag{E}
$$

$$
\int_{S_r}\left(x_2+n_2\right)^{2}\left(x_3+n_3\right)\mathrm{d}S=4\pi{r}^{2}x_2^{2}x_3+x_3\int_{S_r}n_2^{2}\mathrm{d}S=4\pi{r}^{2}x_2^{2}x_3+\frac{4\pi{r}^{4}}{3}x_3,\tag{F}
$$

这里其余项含 $n_i$ 的一次或三次因子, 由 (B)(C) 积分为零 (如 $2x_2x_3\int{n}_2\mathrm{d}S=0$, $\int{n}_2^{2}n_3\mathrm{d}S=0$, $2x_2\int{n}_2n_3\mathrm{d}S=0$).

第五步: 写出 $\varphi_B$. 由 (E)(F) 与 $\varphi_B=\frac{1}{4\pi{r}^{2}}\int_{S_r}\varphi\,\mathrm{d}S$,

$$
\varphi_B\left(x,r\right)=x_1^{2}+x_2^{2}x_3+\frac{r^{2}}{3}\left(1+x_3\right)=\varphi\left(x\right)+\frac{r^{2}}{3}\left(1+x_3\right).\tag{G}
$$

第六步: 代入 (A). 把 $r=at$ 代入,

$$
t\varphi_B\left(x,at\right)=t\left(\varphi\left(x\right)+\frac{a^{2}t^{2}}{3}\left(1+x_3\right)\right).\tag{H}
$$

第七步: 求导得解. 由 (A)(H),

$$
u\left(x,t\right)=\frac{\partial}{\partial{t}}\left[t\varphi\left(x\right)+\frac{a^{2}t^{3}}{3}\left(1+x_3\right)\right]=\varphi\left(x\right)+a^{2}t^{2}\left(1+x_3\right),
$$

即

$$
u\left(x,t\right)=x_1^{2}+x_2^{2}x_3+a^{2}t^{2}\left(1+x_3\right).\tag{I}
$$

第八步: 直接验证. $\partial_t^{2}u=2a^{2}\left(1+x_3\right)$; 又 $\Delta\left(x_1^{2}+x_2^{2}x_3\right)=2+2x_3$ 且 $\Delta\left(a^{2}t^{2}x_3\right)=0$, 故 $a^{2}\Delta{u}=2a^{2}\left(1+x_3\right)=\partial_t^{2}u$, 方程成立; $u\left(x,0\right)=\varphi\left(x\right)$, $u_t\left(x,0\right)=0$ 也成立.

## 习题 4.8 (三维非齐次波动方程的 Cauchy 问题)

求解下述三维非齐次波动方程的 Cauchy 问题

$$
\begin{cases}u_{tt}-a^{2}\Delta{u}=\left|x\right|^{2}\mathrm{e}^{t},&x\in\mathbb{R}^{3},t>0,\\u\left(x,0\right)=u_t\left(x,0\right)=0,&x\in\mathbb{R}^{3}.\end{cases}
$$

### 解答 4.8

第一步: 写出求解公式. 取 $f\left(x,t\right)=\left|x\right|^{2}\mathrm{e}^{t}$, 由**公式 (4.2.17) (三维非齐次波动方程 Cauchy 问题的解)**,

$$
u\left(x,t\right)=\frac{1}{4\pi{a}^{2}}\int_0^{t}\mathrm{d}\tau\int_{S_{a\left(t-\tau\right)}\left(x\right)}\frac{\left|y\right|^{2}\mathrm{e}^{\tau}}{t-\tau}\,\mathrm{d}S_y.\tag{A}
$$

第二步: 算被积函数在球面上的积分. 记 $r=a\left(t-\tau\right)$, 令 $y=x+n$, $\left|n\right|=r$. 由

$$
\left|y\right|^{2}=\left|x\right|^{2}+2x\cdot{n}+\left|n\right|^{2},\qquad\int_{S_r}n\,\mathrm{d}S=0,\qquad\int_{S_r}\mathrm{d}S=4\pi{r}^{2},\tag{B}
$$

得

$$
\int_{S_r\left(x\right)}\left|y\right|^{2}\,\mathrm{d}S=4\pi{r}^{2}\left(\left|x\right|^{2}+r^{2}\right).\tag{C}
$$

第三步: 代入 (A) 并化简. 由 (B)(C),

$$
\frac{1}{4\pi{a}^{2}}\int_{S_{a\left(t-\tau\right)}\left(x\right)}\frac{\left|y\right|^{2}\mathrm{e}^{\tau}}{t-\tau}\,\mathrm{d}S_y=\frac{4\pi{a}^{2}\left(t-\tau\right)^{2}\left(\left|x\right|^{2}+a^{2}\left(t-\tau\right)^{2}\right)\mathrm{e}^{\tau}}{4\pi{a}^{2}\left(t-\tau\right)}=\left(t-\tau\right)\left(\left|x\right|^{2}+a^{2}\left(t-\tau\right)^{2}\right)\mathrm{e}^{\tau}.\tag{D}
$$

故

$$
u\left(x,t\right)=\int_0^{t}\left(t-\tau\right)\left(\left|x\right|^{2}+a^{2}\left(t-\tau\right)^{2}\right)\mathrm{e}^{\tau}\,\mathrm{d}\tau.\tag{E}
$$

第四步: 换元. 令 $s=t-\tau$, 则 $\tau=t-s$, $\mathrm{d}\tau=-\mathrm{d}s$,

$$
u\left(x,t\right)=\mathrm{e}^{t}\int_0^{t}s\left(\left|x\right|^{2}+a^{2}s^{2}\right)\mathrm{e}^{-s}\,\mathrm{d}s=\mathrm{e}^{t}\left[\left|x\right|^{2}\int_0^{t}s\mathrm{e}^{-s}\,\mathrm{d}s+a^{2}\int_0^{t}s^{3}\mathrm{e}^{-s}\,\mathrm{d}s\right].\tag{F}
$$

第五步: 算两个积分. 由分部积分,

$$
\int_0^{t}s\mathrm{e}^{-s}\,\mathrm{d}s=1-\left(1+t\right)\mathrm{e}^{-t},\tag{G}
$$

$$
\int_0^{t}s^{3}\mathrm{e}^{-s}\,\mathrm{d}s=6-\left(t^{3}+3t^{2}+6t+6\right)\mathrm{e}^{-t},\tag{H}
$$

其中 (H) 由三次分部积分得到: $\int_0^{t}s^{3}\mathrm{e}^{-s}\mathrm{d}s=\left[-s^{3}\mathrm{e}^{-s}\right]_0^{t}+3\int_0^{t}s^{2}\mathrm{e}^{-s}\mathrm{d}s$, 逐次降幂并代入 $\int_0^{t}\mathrm{e}^{-s}\mathrm{d}s=1-\mathrm{e}^{-t}$.

第六步: 合并得解. 把 (G)(H) 代入 (F),

$$
u\left(x,t\right)=\left|x\right|^{2}\left(\mathrm{e}^{t}-1-t\right)+a^{2}\left(6\mathrm{e}^{t}-t^{3}-3t^{2}-6t-6\right).\tag{I}
$$

第七步: 直接验证. 由 (I),

$$
\partial_t^{2}u=\left|x\right|^{2}\mathrm{e}^{t}+a^{2}\left(6\mathrm{e}^{t}-6t-6\right),\qquad{a}^{2}\Delta{u}=a^{2}\left(\mathrm{e}^{t}-1-t\right)\Delta\left|x\right|^{2}=6a^{2}\left(\mathrm{e}^{t}-1-t\right),
$$

故

$$
\partial_t^{2}u-a^{2}\Delta{u}=\left|x\right|^{2}\mathrm{e}^{t}+a^{2}\left(6\mathrm{e}^{t}-6t-6-6\mathrm{e}^{t}+6+6t\right)=\left|x\right|^{2}\mathrm{e}^{t},
$$

方程成立. 又 $u\left(x,0\right)=\left|x\right|^{2}\left(1-1\right)+a^{2}\left(6-6\right)=0$, $u_t\left(x,0\right)=\left|x\right|^{2}\left(1-1\right)+a^{2}\left(6-6\right)=0$, 初值条件也成立.
