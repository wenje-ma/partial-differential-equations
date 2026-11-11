# week7

> **定理 3.2.1 (弱极值原理)**
> 
> 设函数 $u\in{C}^{2,1}\left(Q_T\right)\cap{C}^{0}\left(\overline{Q}_T\right)$ 满足 $u_t-a^{2}\Delta{u}\le0$ (或 $\ge0$) 于 $Q_T$, 则 $u$ 在 $\overline{Q}_T$ 上的最大 (小) 值必在其抛物边界 $\partial_pQ_T$ 上达到.

> **定理 3.2.3 (初边值问题的最大模估计)**
> 
> 设 $f\in{C}^{0}\left(\overline{Q}_T\right)$, $\varphi\in{C}^{0}\left(\partial_pQ_T\right)$. 若 $u\in{C}^{2,1}\left(Q_T\right)\cap{C}^{0}\left(\overline{Q}_T\right)$ 是 $u_t-a^{2}\Delta{u}=f$, $u=\varphi$ 于 $\partial_pQ_T$ 的解, 则 $\max_{\overline{Q}_T}\left|u\right|\le{T}\max_{\overline{Q}_T}\left|f\right|+\max_{\partial_pQ_T}\left|\varphi\right|$.

> **定理 3.2.5 (Cauchy 问题的最大模估计)**
> 
> 设 $f\in{L}^{\infty}\left(\mathbb{R}_T\right)$, $\varphi\in{L}^{\infty}\left(\mathbb{R}^{n}\right)$. 若 $u\in{C}^{2,1}\left(\mathbb{R}_T\right)\cap{C}^{0}\left(\overline{\mathbb{R}}_T\right)$ 是 $u_t-a^{2}\Delta{u}=f$, $u\left(x,0\right)=\varphi\left(x\right)$ 的有界解, 则 $\sup_{\mathbb{R}_T}\left|u\right|\le{T}\sup_{\mathbb{R}_T}\left|f\right|+\sup_{\mathbb{R}^{n}}\left|\varphi\right|$.

> **定理 3.2.6 (Cauchy 问题的唯一性和稳定性)**
> 
> 问题 $u_t-a^{2}\Delta{u}=f$ ($\left(x,t\right)\in\mathbb{R}_T$), $u\left(x,0\right)=\varphi\left(x\right)$ ($x\in\mathbb{R}^{n}$) 在 $\mathbb{R}_T$ 上的有界函数类中是唯一的, 并且在最大模意义下关于 $f\in{L}^{\infty}\left(\mathbb{R}_T\right)$ 和 $\varphi\in{L}^{\infty}\left(\mathbb{R}^{n}\right)$ 是稳定的.

> **定理 3.3.1 (Duhamel 原理)**
> 
> 对任意 $\tau>0$, 设 $w\left(x,t;\tau\right)$ 满足 $w_t-a^{2}w_{xx}=0$ ($t>\tau$), $w\left(x,\tau;\tau\right)=\bar{f}\left(x,\tau\right)$, 齐次边界条件, 则原非齐次问题的解可表示为 $\bar{u}_2\left(x,t\right)=\int_0^tw\left(x,t;\tau\right)\,\mathrm{d}\tau$.

> **定义 3.4.3 (Fourier 变换)**
> 
> 设 $f$ 在 $\left(-\infty,+\infty\right)$ 上绝对可积, 定义 $f$ 的 Fourier 变换为 $\mathcal{F}\left[f\right]\left(y\right)=\int_{-\infty}^{+\infty}f\left(x\right)\mathrm{e}^{-\mathrm{i}xy}\,\mathrm{d}x$, 并定义 $g$ 的 Fourier 逆变换为 $\mathcal{F}^{-1}\left[g\right]\left(x\right)=\frac{1}{2\pi}\int_{-\infty}^{+\infty}g\left(y\right)\mathrm{e}^{\mathrm{i}xy}\,\mathrm{d}y$.

## 习题 3.1 (含零阶项热方程的最大模估计)

设 $\varphi\in{C}^{0}\left(\partial_pQ_T\right)$, $c>0$ 是一个常数. 若 $u\in{C}^{2,1}\left(Q_T\right)\cap{C}^{0}\left(\overline{Q}_T\right)$ 是问题

$$
\begin{cases}u_t-\Delta{u}-cu=0,&\left(x,t\right)\in{Q}_T,\\u=\varphi\left(x,t\right),&\left(x,t\right)\in\partial_pQ_T\end{cases}
$$

的解, 证明: 在 $\overline{Q}_T$ 上 $\left|u\left(x,t\right)\right|\le\mathrm{e}^{ct}\max_{\partial_pQ_T}\left|\varphi\right|$.

### 解答 3.1

第一步: 消去零阶项. 令

$$
v\left(x,t\right)=\mathrm{e}^{-ct}u\left(x,t\right),\qquad\left(x,t\right)\in\overline{Q}_T.
$$

第二步: 验证 $v$ 满足齐次热方程. 直接求导,

$$
v_t=\mathrm{e}^{-ct}u_t-c\mathrm{e}^{-ct}u,\qquad\Delta{v}=\mathrm{e}^{-ct}\Delta{u},
$$

故

$$
v_t-\Delta{v}=\mathrm{e}^{-ct}\left(u_t-\Delta{u}-cu\right)=0,\qquad\left(x,t\right)\in{Q}_T.\tag{A}
$$

第三步: 验证 $v$ 的抛物边界条件. 由 $u=\varphi$ 于 $\partial_pQ_T$,

$$
v=\mathrm{e}^{-ct}\varphi,\qquad\left(x,t\right)\in\partial_pQ_T,\qquad\max_{\partial_pQ_T}\left|v\right|\le\max_{\partial_pQ_T}\left|\varphi\right|.\tag{B}
$$

第四步: 对 $v$ 用**定理 3.2.3 (初边值问题的最大模估计)**, 取 $f=0$, 得

$$
\max_{\overline{Q}_T}\left|v\right|\le\max_{\partial_pQ_T}\left|v\right|\le\max_{\partial_pQ_T}\left|\varphi\right|.\tag{C}
$$

第五步: 回到 $u$. 由 $u=\mathrm{e}^{ct}v$ 与 $0<\mathrm{e}^{ct}\le\mathrm{e}^{cT}$ 于 $\overline{Q}_T$,

$$
\left|u\left(x,t\right)\right|=\mathrm{e}^{ct}\left|v\left(x,t\right)\right|\le\mathrm{e}^{ct}\max_{\partial_pQ_T}\left|\varphi\right|\le\mathrm{e}^{cT}\max_{\partial_pQ_T}\left|\varphi\right|.
$$

这就是所要的估计.

## 习题 3.2 (Robin 边界下解的上界与下界)

设 $l,T,b,u_0$ 是正常数. 若 $u\in{C}^{2,1}\left(\left(0,l\right)\times\left(0,T\right)\right)$, $u_x\in{C}^{0}\left(\left[0,l\right]\times\left[0,T\right]\right)$, $u$ 是问题

$$
\begin{cases}u_t-u_{xx}=0,&0<{}x<{}l,0<{}t\le{T},\\u\left(x,0\right)=0,&0\le{x}\le{l},\\u_x\left(0,t\right)+b\left(u_0-u\left(0,t\right)\right)=0,\quad{u}\left(l,t\right)=0,&0\le{t}\le{T}\end{cases}
$$

的解, 证明: 在 $\left[0,l\right]\times\left[0,T\right]$ 上 $0\le{u}\left(x,t\right)\le{u}_0$.

### 解答 3.2

一, 上界 $u\le{u}_0$.

第一步: 令 $z=u-u_0$. 则 $z_t-z_{xx}=0$ 且 $z_x\left(0,t\right)=u_x\left(0,t\right)=b\left(u\left(0,t\right)-u_0\right)=bz\left(0,t\right)$. 又 $z\left(x,0\right)=-u_0<0$, $z\left(l,t\right)=-u_0<0$.

第二步: 由**定理 3.2.1 (弱极值原理)**, $z$ 在 $\overline{Q}_T$ 上的最大值在 $\partial_pQ_T$ 上达到. 若最大值点在 $\left\{t=0\right\}$ 或 $\left\{x=l\right\}$ 上, 则该值等于 $-u_0<0$. 若最大值点在某 $\left(0,t_0\right)$, $0<{}t_0\le{T}$ 处取到, 则对一切 $x\in\left[0,l\right]$

$$
z\left(x,t_0\right)\le{z}\left(0,t_0\right),
$$

即固定 $t_0$ 时 $x\mapsto{z}\left(x,t_0\right)$ 在 $x=0$ 处取最大, 而 $z_x\left(0,t_0\right)$ 存在 (由题设 $u_x$ 在闭区域上连续), 故

$$
z_x\left(0,t_0\right)\le0.\tag{A}
$$

第三步: 由边界条件 $z_x\left(0,t_0\right)=bz\left(0,t_0\right)$ 与 $b>0$, 由 (A) 得 $z\left(0,t_0\right)\le0$. 于是无论如何

$$
\max_{\overline{Q}_T}z\le0,\qquad\text{即}\;u\le{u}_0\;\text{于}\;\left[0,l\right]\times\left[0,T\right].
$$

二, 下界 $u\ge0$.

第四步: 若 $u$ 在 $\overline{Q}_T$ 上取到负值, 记其最小值 $m<0$, 由**定理 3.2.1 (弱极值原理)** (对 $u$) 最小值在 $\partial_pQ_T$ 上达到. 在 $\left\{t=0\right\}$ 与 $\left\{x=l\right\}$ 上 $u=0$, 故最小值只能在某点 $\left(0,t_0\right)$, $0<{}t_0\le{T}$ 处取到.

第五步: 此时对一切 $x\in\left[0,l\right]$ 有 $u\left(x,t_0\right)\ge{u}\left(0,t_0\right)$, 故 $x\mapsto{u}\left(x,t_0\right)$ 在 $x=0$ 处取最小, $u_x\left(0,t_0\right)\ge0$. 但边界条件给出

$$
u_x\left(0,t_0\right)=b\left(u\left(0,t_0\right)-u_0\right).
$$

由 $u\left(0,t_0\right)=m<0$ 与 $u_0>0$ 得 $u\left(0,t_0\right)-u_0<-u_0<0$, 故 $u_x\left(0,t_0\right)<0$, 这与 $u_x\left(0,t_0\right)\ge0$ 矛盾.

第六步: 故 $u$ 在 $\overline{Q}_T$ 上不取负值, $u\ge0$. 结合第三步即得 $0\le{u}\left(x,t\right)\le{u}_0$.

## 习题 3.3 (Cauchy 问题解的唯一性与稳定性)

详细叙述并证明定理 3.2.6.

### 解答 3.3

第一步: 叙述. 设 $a>0$, $T>0$, $\mathbb{R}_T=\mathbb{R}^{n}\times\left(0,T\right]$. 考虑 Cauchy 问题

$$
\begin{cases}u_t-a^{2}\Delta{u}=f\left(x,t\right),&\left(x,t\right)\in\mathbb{R}_T,\\u\left(x,0\right)=\varphi\left(x\right),&x\in\mathbb{R}^{n}.\end{cases}\tag{A}
$$

定理 3.2.6 的内容是下列两条:

(1) 唯一性: 若 $f\in{L}^{\infty}\left(\mathbb{R}_T\right)$, $\varphi\in{L}^{\infty}\left(\mathbb{R}^{n}\right)$, 则 (A) 在 $\mathbb{R}_T$ 上的有界函数类 (即 $u\in{C}^{2,1}\left(\mathbb{R}_T\right)\cap{C}^{0}\left(\overline{\mathbb{R}}_T\right)$ 且 $\sup_{\mathbb{R}_T}\left|u\right|<+\infty$) 中至多有一个解.

(2) 稳定性: 对任意 $\varepsilon>0$, 存在仅依赖于 $\varepsilon$ 与 $T$ 的 $\delta>0$, 使得当

$$
\sup_{\mathbb{R}_T}\left|f_1-f_2\right|<\delta,\qquad\sup_{\mathbb{R}^{n}}\left|\varphi_1-\varphi_2\right|<\delta
$$

时, 以 $\left(f_1,\varphi_1\right)$, $\left(f_2,\varphi_2\right)$ 为数据的两个有界解 $u_1,u_2$ 满足

$$
\sup_{\mathbb{R}_T}\left|u_1-u_2\right|<\varepsilon;
$$

即解在最大模意义下连续依赖于 $f$ 与 $\varphi$.

第二步: 证唯一性. 设 $u_1,u_2$ 是 (A) 的两个有界解 ($f,\varphi$ 相同), 记 $w=u_1-u_2$. 由方程的线性, $w$ 有界, 且

$$
w_t-a^{2}\Delta{w}=0\;\text{于}\;\mathbb{R}_T,\qquad{w}\left(x,0\right)=0\;\text{于}\;\mathbb{R}^{n}.\tag{B}
$$

第三步: 对 (B) 用**定理 3.2.5 (Cauchy 问题的最大模估计)**, 取 $f=0$, $\varphi=0$,

$$
\sup_{\mathbb{R}_T}\left|w\right|\le{T}\sup_{\mathbb{R}_T}\left|0\right|+\sup_{\mathbb{R}^{n}}\left|0\right|=0,
$$

故 $w\equiv0$, 即 $u_1=u_2$. 唯一性得证.

第四步: 证稳定性. 设 $u_i$ 是数据 $\left(f_i,\varphi_i\right)$ 的有界解, $i=1,2$, 记 $w=u_1-u_2$. 由线性, $w$ 有界且

$$
w_t-a^{2}\Delta{w}=f_1-f_2\;\text{于}\;\mathbb{R}_T,\qquad{w}\left(x,0\right)=\varphi_1-\varphi_2\;\text{于}\;\mathbb{R}^{n}.
$$

第五步: 对 $w$ 用**定理 3.2.5 (Cauchy 问题的最大模估计)**,

$$
\sup_{\mathbb{R}_T}\left|w\right|\le{T}\sup_{\mathbb{R}_T}\left|f_1-f_2\right|+\sup_{\mathbb{R}^{n}}\left|\varphi_1-\varphi_2\right|.\tag{C}
$$

第六步: 取 $\delta=\frac{\varepsilon}{2\left(T+1\right)}$. 当两个数据的扰动小于 $\delta$ 时, 由 (C)

$$
\sup_{\mathbb{R}_T}\left|w\right|<{}T\delta+\delta=\left(T+1\right)\frac{\varepsilon}{2\left(T+1\right)}=\frac{\varepsilon}{2}<\varepsilon,
$$

且该 $\delta$ 只依赖于 $\varepsilon$ 与 $T$. 稳定性得证.

## 习题 3.4 (一阶方程的齐次化原理)

叙述并证明一阶方程 Cauchy 问题

$$
\begin{cases}u_t+u_x=f\left(x,t\right),&-\infty<{}x<+\infty,t>0,\\u\left(x,0\right)=0,&-\infty<{}x<+\infty\end{cases}
$$

的齐次化原理.

### 解答 3.4

第一步: 叙述 (齐次化原理, 即 Duhamel 原理). 对任意 $\tau\ge0$, 设 $W\left(x,t;\tau\right)$ 是齐次问题

$$
\begin{cases}W_t+W_x=0,&t>\tau,-\infty<{}x<+\infty,\\W\left(x,\tau;\tau\right)=f\left(x,\tau\right),&-\infty<{}x<+\infty\end{cases}\tag{A}
$$

的解. 则原非齐次问题的解可表为

$$
u\left(x,t\right)=\int_0^{t}W\left(x,t;\tau\right)\,\mathrm{d}\tau.\tag{B}
$$

第二步: 先写出 $W$ 的显式. 问题 (A) 是一阶齐次方程, 沿特征线 $x+t=$ 常数 取值不变: 特征线过点 $\left(x,t\right)$ 时与直线 $t=\tau$ 交于 $x-\left(t-\tau\right)$, 故

$$
W\left(x,t;\tau\right)=f\left(x-\left(t-\tau\right),\tau\right).\tag{C}
$$

第三步: 验证 (B) 满足初始条件. 由 (B),

$$
u\left(x,0\right)=\int_0^{0}W\,\mathrm{d}\tau=0.\tag{D}
$$

第四步: 验证 (B) 满足方程. 由 (C), $W$ 关于 $\left(x,t\right)$ 光滑 (设 $f$ 光滑), 故可用含参量积分的求导公式. 注意积分上限 $t$ 出现于上限与被积函数的第二个自变量中,

$$
u_t\left(x,t\right)=W\left(x,t;t\right)+\int_0^{t}\frac{\partial{W}}{\partial{t}}\left(x,t;\tau\right)\,\mathrm{d}\tau,\qquad{u}_x\left(x,t\right)=\int_0^{t}\frac{\partial{W}}{\partial{x}}\left(x,t;\tau\right)\,\mathrm{d}\tau.
$$

第五步: 相加. 由 (C), $W\left(x,t;t\right)=f\left(x,t\right)$; 又 $W$ 是 (A) 的解, 故 $W_t+W_x=0$ 对 $t>\tau$ 成立. 于是

$$
u_t+u_x=f\left(x,t\right)+\int_0^{t}\left(W_t+W_x\right)\left(x,t;\tau\right)\,\mathrm{d}\tau=f\left(x,t\right).
$$

结合 (D), (B) 确为原问题的解, 齐次化原理得证.

第六步: 把 (C) 代入 (B), 得解的显式

$$
u\left(x,t\right)=\int_0^{t}f\left(x-t+\tau,\tau\right)\mathrm{d}\tau.
$$

## 习题 3.5 (Fourier 变换求带低阶项热方程的形式解)

应用 Fourier 变换求出 Cauchy 问题

$$
\begin{cases}u_t-a^{2}u_{xx}-bu_x-cu=f\left(x,t\right),&-\infty<{}x<+\infty,t>0,\\u\left(x,0\right)=\varphi\left(x\right),&-\infty<{}x<+\infty\end{cases}
$$

的形式解, 其中 $a,b,c$ 是常数.

### 解答 3.5

第一步: 对空间变量取 Fourier 变换. 由**定义 3.4.3 (Fourier 变换)**, 记

$$
\hat{u}\left(\xi,t\right)=\mathcal{F}\left[u\left(\cdot,t\right)\right]\left(\xi\right)=\int_{-\infty}^{+\infty}u\left(x,t\right)\mathrm{e}^{-\mathrm{i}x\xi}\,\mathrm{d}x,\tag{A}
$$

同样记 $\hat{f},\hat{\varphi}$. 设 $u$ 及其导数在 $x\to\pm\infty$ 时衰减, 由分部积分

$$
\mathcal{F}\left[u_x\right]=-\int_{-\infty}^{+\infty}u\left(x,t\right)\left(-\mathrm{i}\xi\right)\mathrm{e}^{-\mathrm{i}x\xi}\,\mathrm{d}x=\mathrm{i}\xi\hat{u},\qquad\mathcal{F}\left[u_{xx}\right]=\mathrm{i}\xi\cdot\mathrm{i}\xi\hat{u}=-\xi^{2}\hat{u}.\tag{B}
$$

第二步: 化为常微分方程. 对题中方程两端取 Fourier 变换, 用 (B),

$$
\hat{u}_t+a^{2}\xi^{2}\hat{u}-\mathrm{i}b\xi\hat{u}-c\hat{u}=\hat{f}\left(\xi,t\right),\qquad\hat{u}\left(\xi,0\right)=\hat{\varphi}\left(\xi\right),
$$

即

$$
\hat{u}_t=\left(c-a^{2}\xi^{2}+\mathrm{i}b\xi\right)\hat{u}+\hat{f}\left(\xi,t\right),\qquad\hat{u}\left(\xi,0\right)=\hat{\varphi}\left(\xi\right).\tag{C}
$$

第三步: 解 (C). 这是一阶线性常微分方程, 用积分因子 $\exp\left(-\left(c-a^{2}\xi^{2}+\mathrm{i}b\xi\right)t\right)$,

$$
\hat{u}\left(\xi,t\right)=\mathrm{e}^{\left(c-a^{2}\xi^{2}+\mathrm{i}b\xi\right)t}\hat{\varphi}\left(\xi\right)+\int_0^{t}\mathrm{e}^{\left(c-a^{2}\xi^{2}+\mathrm{i}b\xi\right)\left(t-\tau\right)}\hat{f}\left(\xi,\tau\right)\,\mathrm{d}\tau.\tag{D}
$$

第四步: 准备反演所需的两条事实. (i) 由 Gauss 积分 $\int_{-\infty}^{+\infty}\mathrm{e}^{-A\xi^{2}}\mathrm{e}^{\mathrm{i}\xi{z}}\,\mathrm{d}\xi=\sqrt{\frac{\pi}{A}}\mathrm{e}^{-\frac{z^{2}}{4A}}$ ($A>0$),

$$
\mathcal{F}^{-1}\left[\mathrm{e}^{-a^{2}\xi^{2}t}\right]\left(x\right)=\frac{1}{2\pi}\int_{-\infty}^{+\infty}\mathrm{e}^{-a^{2}t\xi^{2}}\mathrm{e}^{\mathrm{i}x\xi}\,\mathrm{d}\xi=\frac{1}{2a\sqrt{\pi{t}}}\mathrm{e}^{-\frac{x^{2}}{4a^{2}t}}=:G\left(x,t\right).\tag{E}
$$

(ii) 由**定义 3.4.3** 作变量替换 $x+bt=y$,

$$
\mathcal{F}\left[g\left(\cdot+bt\right)\right]\left(\xi\right)=\int_{-\infty}^{+\infty}g\left(x+bt\right)\mathrm{e}^{-\mathrm{i}x\xi}\,\mathrm{d}x=\mathrm{e}^{\mathrm{i}b\xi{t}}\hat{g}\left(\xi\right),\tag{F}
$$

即乘因子 $\mathrm{e}^{\mathrm{i}b\xi{t}}$ 相当于把自变量平移 $bt$. 于是

$$
\mathcal{F}^{-1}\left[\mathrm{e}^{-a^{2}\xi^{2}t+\mathrm{i}b\xi{t}}\hat{\varphi}\right]\left(x\right)=\int_{-\infty}^{+\infty}G\left(x+bt-y,t\right)\varphi\left(y\right)\,\mathrm{d}y,\tag{G}
$$

这里用了 (E) 与卷积形式 $\mathcal{F}^{-1}\left[\hat{G}\hat{\varphi}\right]\left(x\right)=\int{G}\left(x-y,t\right)\varphi\left(y\right)\mathrm{d}y$ 以及 (F).

第五步: 反演初值部分的项. 由 (D)(G),

$$
u_{1}\left(x,t\right)=\mathrm{e}^{ct}\int_{-\infty}^{+\infty}\frac{1}{2a\sqrt{\pi{t}}}\mathrm{e}^{-\frac{\left(x+bt-y\right)^{2}}{4a^{2}t}}\varphi\left(y\right)\,\mathrm{d}y.\tag{H}
$$

第六步: 反演源项部分的项. 对 (D) 中积分里的每一项, 把 $\tau$ 视为参数, 用 (G) 并把 $\mathrm{e}^{c\left(t-\tau\right)}$ 提出,

$$
u_{2}\left(x,t\right)=\int_0^{t}\mathrm{e}^{c\left(t-\tau\right)}\int_{-\infty}^{+\infty}\frac{1}{2a\sqrt{\pi\left(t-\tau\right)}}\mathrm{e}^{-\frac{\left(x+b\left(t-\tau\right)-y\right)^{2}}{4a^{2}\left(t-\tau\right)}}f\left(y,\tau\right)\,\mathrm{d}y\,\mathrm{d}\tau.\tag{I}
$$

第七步: 相加即得形式解

$$
u\left(x,t\right)=\mathrm{e}^{ct}\int_{\mathbb{R}}G\left(x+bt-y,t\right)\varphi\left(y\right)\,\mathrm{d}y+\int_0^{t}\mathrm{e}^{c\left(t-\tau\right)}\int_{\mathbb{R}}G\left(x+b\left(t-\tau\right)-y,t-\tau\right)f\left(y,\tau\right)\,\mathrm{d}y\,\mathrm{d}\tau,
$$

其中 $G$ 由 (E) 给出. 这就是所求的形式解.

## 习题 3.6 (热方程 Cauchy 问题的求解)

求解 Cauchy 问题

$$
\begin{cases}u_t-u_{xx}=0,&-\infty<{}x<+\infty,t>0,\\u\left(x,0\right)=\sin{x},&-\infty<{}x<+\infty.\end{cases}
$$

### 解答 3.6

第一步: 试取分离变量形式 $u\left(x,t\right)=T\left(t\right)\sin{x}$ (初始数据含 $\sin{x}$, 而 $\sin{x}$ 是 $-\partial_x^{2}$ 的特征函数). 代入方程,

$$
T'\sin{x}+T\sin{x}=\left(T'+T\right)\sin{x}=0,\qquad\text{故}\;T'+T=0.
$$

第二步: 解常微分方程得 $T\left(t\right)=A\mathrm{e}^{-t}$, 由初值 $u\left(x,0\right)=\sin{x}$ 定出 $A=1$. 于是

$$
u\left(x,t\right)=\mathrm{e}^{-t}\sin{x}.\tag{A}
$$

第三步: 直接验证. $\partial_tu=-\mathrm{e}^{-t}\sin{x}$, $\partial_x^{2}u=-\mathrm{e}^{-t}\sin{x}$, 故 $\partial_tu-\partial_x^{2}u=0$; 且 $u\left(x,0\right)=\sin{x}$. 所以 (A) 是解.

第四步: 说明解的唯一性. 由 $\left|u\left(x,t\right)\right|\le\mathrm{e}^{-t}\le1$, (A) 属于 $\mathbb{R}_T$ 上的有界函数类, 故由**定理 3.2.6 (Cauchy 问题的唯一性和稳定性)**, 它是有界函数类中唯一的解.

第五步: 结论: $u\left(x,t\right)=\mathrm{e}^{-t}\sin{x}$ 就是所求的解. 这与 Poisson 公式给出的结果一致: 由 Poisson 公式,
$\frac{1}{2\sqrt{\pi{t}}}\int_{\mathbb{R}}\mathrm{e}^{-\frac{\left(x-y\right)^{2}}{4t}}\sin{y}\,\mathrm{d}y=\mathrm{e}^{-t}\sin{x}$.
