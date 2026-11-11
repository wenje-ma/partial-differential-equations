# week8

> **定理 3.2.1 (弱极值原理)**
> 
> 设函数 $u\in{C}^{2,1}\left(Q_T\right)\cap{C}^{0}\left(\overline{Q}_T\right)$ 满足 $u_t-a^{2}\Delta{u}\le0$ (或 $\ge0$) 于 $Q_T$, 则 $u$ 在 $\overline{Q}_T$ 上的最大 (小) 值必在其抛物边界 $\partial_pQ_T$ 上达到.

> **定理 3.2.3 (初边值问题的最大模估计)**
> 
> 设 $f\in{C}^{0}\left(\overline{Q}_T\right)$, $\varphi\in{C}^{0}\left(\partial_pQ_T\right)$. 若 $u\in{C}^{2,1}\left(Q_T\right)\cap{C}^{0}\left(\overline{Q}_T\right)$ 是 $u_t-a^{2}\Delta{u}=f$ ($\left(x,t\right)\in{Q}_T$), $u=\varphi$ 于 $\partial_pQ_T$ 的解, 则 $\max_{\overline{Q}_T}\left|u\right|\le{T}\max_{\overline{Q}_T}\left|f\right|+\max_{\partial_pQ_T}\left|\varphi\right|$.

> **定义 3.4.3 (Fourier 变换)**
> 
> 设 $f$ 在 $\left(-\infty,+\infty\right)$ 上绝对可积, 定义 $f$ 的 Fourier 变换为 $\mathcal{F}\left[f\right]\left(y\right)=\int_{-\infty}^{+\infty}f\left(x\right)\mathrm{e}^{-\mathrm{i}xy}\,\mathrm{d}x$, 并定义 $g$ 的 Fourier 逆变换为 $\mathcal{F}^{-1}\left[g\right]\left(x\right)=\frac{1}{2\pi}\int_{-\infty}^{+\infty}g\left(y\right)\mathrm{e}^{\mathrm{i}xy}\,\mathrm{d}y$.

## 习题 3.7 (时间导数的最大模估计)

设 $f\in{C}^{1}\left(\overline{Q}_T\right)$, $\varphi\in{C}^{2}\left(\overline{\Omega}\right)$. 若 $u\in{C}^{2,1}\left(Q_T\right)$, $u_t\in{C}^{2,1}\left(Q_T\right)$, 并且 $u$ 满足

$$
\begin{cases}u_t-a^{2}\Delta{u}=f\left(x,t\right),&\left(x,t\right)\in{Q}_T,\\u\left(x,0\right)=\varphi\left(x\right),&x\in\overline{\Omega},\\u\left(x,t\right)=0,&x\in{S}_T,\end{cases}
$$

证明:

$$
\max_{\overline{Q}_T}\left|u_t\right|\le{C}\left(\left\|f\right\|_{C^{1}\left(\overline{Q}_T\right)}+\left\|D^{2}\varphi\right\|_{C^{0}\left(\overline{\Omega}\right)}\right),
$$

其中 $C$ 是仅依赖于 $T$ 的常数.

### 解答 3.7

第一步: 令 $v=u_t$. 由题设 $v\in{C}^{2,1}\left(Q_T\right)$. 把原方程关于 $t$ 求导 (由 $u_t\in{C}^{2,1}$ 可交换求导次序),

$$
v_t-a^{2}\Delta{v}=f_t\left(x,t\right),\qquad\left(x,t\right)\in{Q}_T.\tag{A}
$$

第二步: 定出 $v$ 的初值. 在原方程中令 $t=0$, 由 $u\left(x,0\right)=\varphi\left(x\right)$,

$$
u_t\left(x,0\right)-a^{2}\Delta{u}\left(x,0\right)=f\left(x,0\right),\qquad\text{即}\;v\left(x,0\right)=a^{2}\Delta\varphi\left(x\right)+f\left(x,0\right),\quad{x}\in\overline{\Omega}.\tag{B}
$$

第三步: 定出 $v$ 的边值. 由 $u\left(x,t\right)=0$ 对一切 $x\in\partial\Omega$, $0\le{t}\le{T}$ 成立, 关于 $t$ 求导得

$$
v\left(x,t\right)=0,\qquad{x}\in\partial\Omega,\quad0\le{t}\le{T}.\tag{C}
$$

第四步: 对 (A)(B)(C) 用**定理 3.2.3 (初边值问题的最大模估计)**, 取 $f$ 为 $f_t$, $\varphi$ 为 $a^{2}\Delta\varphi\left(\cdot\right)+f\left(\cdot,0\right)$,

$$
\max_{\overline{Q}_T}\left|v\right|\le{T}\max_{\overline{Q}_T}\left|f_t\right|+\max_{\overline{\Omega}}\left|a^{2}\Delta\varphi+f\left(\cdot,0\right)\right|.\tag{D}
$$

第五步: 估计右端. 由 $\Delta\varphi=\sum_{i}\partial_{x_ix_i}\varphi$ 与 $a^{2}>0$,

$$
\max_{\overline{\Omega}}\left|a^{2}\Delta\varphi+f\left(\cdot,0\right)\right|\le{a}^{2}\max_{\overline{\Omega}}\left|\Delta\varphi\right|+\max_{\overline{\Omega}}\left|f\left(\cdot,0\right)\right|\le{a}^{2}\left\|D^{2}\varphi\right\|_{C^{0}\left(\overline{\Omega}\right)}+\left\|f\right\|_{C^{0}\left(\overline{Q}_T\right)}.\tag{E}
$$

又 $\max_{\overline{Q}_T}\left|f_t\right|\le\left\|f\right\|_{C^{1}\left(\overline{Q}_T\right)}$.

第六步: 合并. 取 $C=1+a^{2}+T$, 由 (D)(E) 与第一步 $v=u_t$,

$$
\max_{\overline{Q}_T}\left|u_t\right|\le{T}\left\|f\right\|_{C^{1}\left(\overline{Q}_T\right)}+a^{2}\left\|D^{2}\varphi\right\|_{C^{0}\left(\overline{\Omega}\right)}+\left\|f\right\|_{C^{0}\left(\overline{Q}_T\right)}\le{C}\left(\left\|f\right\|_{C^{1}\left(\overline{Q}_T\right)}+\left\|D^{2}\varphi\right\|_{C^{0}\left(\overline{\Omega}\right)}\right),
$$

其中 $C$ 只依赖于 $T$ (与 $a$, 即与方程本身无关的部分已并入常数).

## 习题 3.8 (含梯度模项算子的比较原理)

设 $Lu=u_t-\Delta{u}+\left|\nabla{u}\right|$. 证明: 对于算子 $L$ 比较原理成立: 若 $u,v\in{C}^{2,1}\left(Q_T\right)\cap{C}^{0}\left(\overline{Q}_T\right)$ 满足

$$
\begin{cases}Lu\le{Lv},&\left(x,t\right)\in{Q}_T,\\u\le{v},&\left(x,t\right)\in\partial_pQ_T,\end{cases}
$$

则在 $\overline{Q}_T$ 上 $u\le{v}$.

### 解答 3.8

第一步: 化归为单个函数的不等式. 令 $w=v-u$. 由 $Lu\le{Lv}$,

$$
\left(v_t-\Delta{v}+\left|\nabla{v}\right|\right)-\left(u_t-\Delta{u}+\left|\nabla{u}\right|\right)\ge0,
$$

即

$$
w_t-\Delta{w}+\left|\nabla{v}\right|-\left|\nabla{u}\right|\ge0,\qquad\left(x,t\right)\in{Q}_T.\tag{A}
$$

第二步: 用三角不等式控制梯度项. 由 $\nabla{v}=\nabla{u}+\nabla{w}$ 与 $\left|\nabla{v}\right|\le\left|\nabla{u}\right|+\left|\nabla{w}\right|$,

$$
\left|\nabla{v}\right|-\left|\nabla{u}\right|\le\left|\nabla{w}\right|,
$$

代回 (A) 得

$$
w_t-\Delta{w}+\left|\nabla{w}\right|\ge\left(\left|\nabla{v}\right|-\left|\nabla{u}\right|\right)+\left|\nabla{w}\right|\ge0,\qquad\left(x,t\right)\in{Q}_T.\tag{B}
$$

第三步: 边界条件. 由 $u\le{v}$ 于 $\partial_pQ_T$,

$$
w\ge0\quad\text{于}\;\partial_pQ_T.\tag{C}
$$

第四步: 证 $w\ge0$. 反设 $w$ 在 $Q_T$ 内部取到负值. 对任意 $\varepsilon>0$ 令

$$
z\left(x,t\right)=w\left(x,t\right)+\varepsilon{t}.\tag{D}
$$

第五步: 由 (B), $z$ 满足

$$
z_t-\Delta{z}+\left|\nabla{z}\right|=w_t+\varepsilon-\Delta{w}+\left|\nabla{w}\right|\ge\varepsilon>0,\qquad\left(x,t\right)\in{Q}_T.\tag{E}
$$

又由 (C), $z\ge\varepsilon{t}\ge0$ 于 $\partial_pQ_T$.

第六步: 反设 $z$ 在 $Q_T$ 内部某点 $\left(x_0,t_0\right)$ 取到负的最小值. 由 $z\in{C}^{2,1}$, 在该点 $z_t=0$, $\nabla{z}=0$, 且 $\Delta{z}\ge0$ (空间 Hessian 半正定). 于是

$$
z_t-\Delta{z}+\left|\nabla{z}\right|=-\Delta{z}\le0,
$$

与 (E) 矛盾.

第七步: 故 $z$ 在 $\overline{Q}_T$ 上的最小值在 $\partial_pQ_T$ 上达到, 从而 $z\ge0$ 于 $\overline{Q}_T$. 由 (D),

$$
w\left(x,t\right)\ge-\varepsilon{t}\ge-\varepsilon{T},\qquad\left(x,t\right)\in\overline{Q}_T.
$$

令 $\varepsilon\to0$ 得 $w\ge0$, 即 $u\le{v}$ 于 $\overline{Q}_T$.

## 习题 3.9 (初值为方波的热方程解的极限)

设 $h>0$, $u\left(x,t;h\right)$ 是 Cauchy 问题

$$
\begin{cases}u_t-a^{2}u_{xx}=0,&-\infty<{}x<+\infty,t>0,\\u\left(x,0\right)=\begin{cases}\frac{1}{h},&\left|x\right|\le{h},\\0,&\left|x\right|>{}h\end{cases}\end{cases}
$$

由 Poisson 公式给出的形式解. 证明:

$$
\lim_{h\to0^{+}}u\left(x,t;h\right)=\frac{1}{a\sqrt{\pi{t}}}\mathrm{e}^{-\frac{x^{2}}{4a^{2}t}},\qquad-\infty<{}x<+\infty,t>0.
$$

### 解答 3.9

第一步: 写出 Poisson 公式. 对上述初值, 一维热传导方程 Cauchy 问题的解为

$$
u\left(x,t;h\right)=\frac{1}{2a\sqrt{\pi{t}}}\int_{\left|y\right|\le{h}}\frac{1}{h}\mathrm{e}^{-\frac{\left(x-y\right)^{2}}{4a^{2}t}}\,\mathrm{d}y.\tag{A}
$$

第二步: 记 $F\left(y\right)=\mathrm{e}^{-\frac{\left(x-y\right)^{2}}{4a^{2}t}}$, 它在 $\mathbb{R}$ 上连续. 由积分中值定理, 存在 $\xi_h\in\left[-h,h\right]$ 使

$$
\int_{\left|y\right|\le{h}}F\left(y\right)\,\mathrm{d}y=2hF\left(\xi_h\right).\tag{B}
$$

第三步: 代入 (A),

$$
u\left(x,t;h\right)=\frac{1}{2a\sqrt{\pi{t}}}\cdot\frac{1}{h}\cdot2hF\left(\xi_h\right)=\frac{1}{a\sqrt{\pi{t}}}F\left(\xi_h\right).\tag{C}
$$

第四步: 令 $h\to0^{+}$. 此时 $\xi_h\in\left[-h,h\right]$ 迫使 $\xi_h\to0$, 而 $F$ 连续, 故 $F\left(\xi_h\right)\to{F}\left(0\right)=\mathrm{e}^{-\frac{x^{2}}{4a^{2}t}}$. 由 (C),

$$
\lim_{h\to0^{+}}u\left(x,t;h\right)=\frac{1}{a\sqrt{\pi{t}}}\mathrm{e}^{-\frac{x^{2}}{4a^{2}t}}.
$$

第五步: 说明该极限的物理意义: 初值在 $h\to0^{+}$ 时趋于强度为 $2$ 的点源, 其解趋于热核 $\frac{1}{a\sqrt{\pi{t}}}\mathrm{e}^{-\frac{x^{2}}{4a^{2}t}}$.

## 习题 3.10 (用 Poisson 公式证明 Weierstrass 逼近定理)

利用热传导方程 Cauchy 问题解的 Poisson 公式证明 Weierstrass 逼近定理: 对于 $f\in{C}^{0}\left[a,b\right]$, 存在一个多项式列 $\left\{P_n\left(x\right)\right\}$, 使得 $\left\{P_n\left(x\right)\right\}$ 在 $\left[a,b\right]$ 上一致收敛到 $f\left(x\right)$.

### 解答 3.10

第一步: 把 $f$ 延拓为 $\mathbb{R}$ 上具紧支集的连续函数. 先取 $a-1<{}b+1$ 内的分段线性延拓, 使延拓后的函数在 $\left[a-1,b+1\right]$ 上连续, 在 $\left[a-1,b+1\right]$ 外为 $0$; 记延拓后的函数仍为 $f$. 则 $f$ 在 $\mathbb{R}$ 上连续, $\operatorname{supp}f\subset\left[a-1,b+1\right]$, 且 $f$ 在 $\mathbb{R}$ 上一致连续, 记 $\max\left|f\right|=\left\|f\right\|_{\infty}$.

第二步: 引入 Poisson 公式. 取 $a=1$ (即热传导方程取 $u_t=u_{xx}$), 对任意 $t>0$ 定义

$$
u\left(x,t\right)=\frac{1}{2\sqrt{\pi{t}}}\int_{-\infty}^{+\infty}\mathrm{e}^{-\frac{\left(x-y\right)^{2}}{4t}}f\left(y\right)\,\mathrm{d}y.\tag{A}
$$

由 Poisson 公式, $u$ 在 $t>0$ 内满足 $u_t=u_{xx}$, 且当 $t\to0^{+}$ 时 $u\left(\cdot,t\right)$ 是 $f$ 的磨光 (见第三步).

第三步: 证 $u\left(\cdot,t\right)$ 当 $t\to0^{+}$ 时一致收敛到 $f$. 记 $G_t\left(z\right)=\frac{1}{2\sqrt{\pi{t}}}\mathrm{e}^{-\frac{z^{2}}{4t}}$, 则 $\int_{\mathbb{R}}G_t\left(z\right)\,\mathrm{d}z=1$, 且

$$
u\left(x,t\right)-f\left(x\right)=\int_{-\infty}^{+\infty}G_t\left(x-y\right)\left(f\left(y\right)-f\left(x\right)\right)\mathrm{d}y.\tag{B}
$$

由 $f$ 在 $\mathbb{R}$ 上一致连续, 对 $\varepsilon>0$ 存在 $\delta>0$, 使 $\left|y-x\right|<\delta$ 时 $\left|f\left(y\right)-f\left(x\right)\right|<\varepsilon$. 把 (B) 拆成两部分.

第四步: 近处的估计. 由 $G_t\ge0$ 与归一化,

$$
\left|\int_{\left|y-x\right|<\delta}G_t\left(x-y\right)\left(f\left(y\right)-f\left(x\right)\right)\mathrm{d}y\right|\le\varepsilon\int_{\mathbb{R}}G_t\,\mathrm{d}z=\varepsilon.\tag{C}
$$

第五步: 远处的估计. 对 $\left|y-x\right|\ge\delta$,

$$
G_t\left(x-y\right)\le\frac{1}{2\sqrt{\pi{t}}}\mathrm{e}^{-\frac{\delta^{2}}{4t}},
$$

且 $\left|f\left(y\right)-f\left(x\right)\right|\le2\left\|f\right\|_{\infty}$, 故

$$
\left|\int_{\left|y-x\right|\ge\delta}G_t\left(f\left(y\right)-f\left(x\right)\right)\mathrm{d}y\right|\le\frac{2\left\|f\right\|_{\infty}}{2\sqrt{\pi{t}}}\mathrm{e}^{-\frac{\delta^{2}}{4t}}\int_{\mathbb{R}}\mathrm{d}y,\tag{D}
$$

这里积分只在 $\operatorname{supp}f$ 上有效, 其长度不超过 $b-a+2$. 当 $t\to0^{+}$ 时, $\mathrm{e}^{-\frac{\delta^{2}}{4t}}/\sqrt{t}\to0$, 故 (D) 的右端当 $t$ 充分小时小于 $\varepsilon$.

第六步: 合并 (C)(D) 得: 当 $t$ 充分小时, 对一切 $x\in\mathbb{R}$

$$
\left|u\left(x,t\right)-f\left(x\right)\right|<2\varepsilon.\tag{E}
$$

第七步: 用多项式逼近 $u\left(\cdot,t\right)$ ($t$ 固定). 由 (A), $u\left(x,t\right)$ 是 $\mathrm{e}^{-\frac{\left(x-y\right)^{2}}{4t}}$ 与 $f$ 的积分. 取 $t=t_0$ 充分小 (满足 (E)). 在紧集 $\left\{\left(x,y\right):x\in\left[a,b\right],y\in\operatorname{supp}f\right\}$ 上, 核 $\mathrm{e}^{-\frac{\left(x-y\right)^{2}}{4t_0}}$ 关于 $x$ 实解析, 它的关于 $x$ 的 Taylor 级数在该紧集上一致收敛于自身 (Taylor 余项被与 $y$ 无关的几何型常数控制). 于是把 Taylor 级数代入 (A) 并逐项积分, 得

$$
u\left(x,t_0\right)=\sum_{k=0}^{\infty}c_kx^{k},\qquad{x}\in\left[a,b\right],
$$

其中 $c_k$ 是常数, 且该级数在 $\left[a,b\right]$ 上一致收敛. 取 $P_n\left(x\right)=\sum_{k=0}^{n}c_kx^{k}$, 则

$$
\max_{x\in\left[a,b\right]}\left|P_n\left(x\right)-u\left(x,t_0\right)\right|\to0,\qquad{n}\to\infty.\tag{F}
$$

第八步: 结论. 取 $n$ 充分大使得 (F) 中的偏差小于 $\varepsilon$; 则由 (E)(F) 的三角不等式

$$
\max_{x\in\left[a,b\right]}\left|P_n\left(x\right)-f\left(x\right)\right|<3\varepsilon.
$$

故多项式列 $\left\{P_n\right\}$ 在 $\left[a,b\right]$ 上一致收敛到 $f$, Weierstrass 定理得证.

## 习题 3.11 ($\cos\left(ax^{2}\right)$ 的 Fourier 变换)

求函数 $f\left(x\right)=\cos{ax^{2}}$ 的 Fourier 变换, 其中 $a$ 是非零常数. 并比较 Fourier 变换前后的图像.

### 解答 3.11

第一步: 用 Euler 公式把余弦写成指数形式. 由 $\cos{ax^{2}}=\operatorname{Re}\left(\mathrm{e}^{\mathrm{i}ax^{2}}\right)$ 与 $\mathcal{F}\left[f\right]=\int_{\mathbb{R}}f\left(x\right)\mathrm{e}^{-\mathrm{i}x\xi}\mathrm{d}x$,

$$
\mathcal{F}\left[\cos{ax^{2}}\right]\left(\xi\right)=\operatorname{Re}\int_{-\infty}^{+\infty}\mathrm{e}^{\mathrm{i}ax^{2}-\mathrm{i}x\xi}\,\mathrm{d}x.\tag{A}
$$

第二步: 配方. 设 $a>0$. 把指数写成 $a\left(x-\frac{\xi}{2a}\right)^{2}-\frac{\xi^{2}}{4a}$,

$$
\mathrm{i}ax^{2}-\mathrm{i}x\xi=\mathrm{i}a\left(x-\frac{\xi}{2a}\right)^{2}-\mathrm{i}\frac{\xi^{2}}{4a}.\tag{B}
$$

第三步: 用 Gauss 积分. 令 $z=x-\frac{\xi}{2a}$, 由 $\int_{\mathbb{R}}\mathrm{e}^{\mathrm{i}az^{2}}\mathrm{d}z=\sqrt{\frac{\pi}{a}}\mathrm{e}^{\mathrm{i}\frac{\pi}{4}}$ (Fresnel 积分, 即 $\int_{\mathbb{R}}\mathrm{e}^{-\left(-\mathrm{i}a\right)z^{2}}\mathrm{d}z$ 取 $\sqrt{\frac{\pi}{\lambda}}$ 在 $\lambda=-\mathrm{i}a$ 的解析延拓),

$$
\int_{-\infty}^{+\infty}\mathrm{e}^{\mathrm{i}ax^{2}-\mathrm{i}x\xi}\,\mathrm{d}x=\sqrt{\frac{\pi}{a}}\mathrm{e}^{\mathrm{i}\frac{\pi}{4}}\mathrm{e}^{-\mathrm{i}\frac{\xi^{2}}{4a}}.\tag{C}
$$

第四步: 取实部. 由 (A)(C),

$$
\mathcal{F}\left[\cos{ax^{2}}\right]\left(\xi\right)=\sqrt{\frac{\pi}{a}}\cos\left(\frac{\pi}{4}-\frac{\xi^{2}}{4a}\right)=\sqrt{\frac{\pi}{2a}}\left(\cos\frac{\xi^{2}}{4a}+\sin\frac{\xi^{2}}{4a}\right),\qquad{a}>0.\tag{D}
$$

第五步: $a<0$ 的情形. 令 $b=-a>0$, $\cos{ax^{2}}=\cos{bx^{2}}$, 与第四步同法可得

$$
\mathcal{F}\left[\cos{ax^{2}}\right]\left(\xi\right)=\sqrt{\frac{\pi}{2\left|a\right|}}\left(\cos\frac{\xi^{2}}{4\left|a\right|}-\sin\frac{\xi^{2}}{4\left|a\right|}\right),\qquad{a}<0.\tag{E}
$$

第六步: 比较图像. 变换前 $f\left(x\right)=\cos{ax^{2}}$ 是"调频"振荡: 零点间隔随 $\left|x\right|$ 增大而减小, 频率在 $\left|x\right|$ 大处越来越密. 变换后 (D) 表明 $\mathcal{F}\left[f\right]\left(\xi\right)$ 仍是同类型的调频振荡, 只是把自变量换成 $\xi$, 把参数 $a$ 换成 $\frac{1}{4a}$: 在 $\xi$ 大处振荡也越来越密. 这就是调频信号的"自对偶"性质 (Fourier 变换把 chirp 仍映为 chirp); 同时振幅 $\sqrt{\frac{\pi}{2\left|a\right|}}$ 与频率参数成反比, 与测不准关系的直观一致.

## 习题 3.12 ($\mathrm{e}^{-b\left|y\right|}$ 的 Fourier 逆变换)

求函数 $g\left(y\right)=\mathrm{e}^{-b\left|y\right|}$ 的 Fourier 逆变换, 其中 $b$ 是正常数.

### 解答 3.12

第一步: 写出逆变换的定义. 由**定义 3.4.3 (Fourier 变换)**,

$$
\mathcal{F}^{-1}\left[g\right]\left(x\right)=\frac{1}{2\pi}\int_{-\infty}^{+\infty}\mathrm{e}^{-b\left|y\right|}\mathrm{e}^{\mathrm{i}xy}\,\mathrm{d}y.\tag{A}
$$

第二步: 把积分按 $y$ 的正负拆开. 由 $\left|y\right|=y$ ($y>0$) 与 $\left|y\right|=-y$ ($y<0$),

$$
\int_{-\infty}^{+\infty}\mathrm{e}^{-b\left|y\right|}\mathrm{e}^{\mathrm{i}xy}\,\mathrm{d}y=\int_0^{+\infty}\mathrm{e}^{-\left(b-\mathrm{i}x\right)y}\,\mathrm{d}y+\int_{-\infty}^{0}\mathrm{e}^{\left(b+\mathrm{i}x\right)y}\,\mathrm{d}y.\tag{B}
$$

第三步: 算出两个积分. 由 $b>0$, 两个指数衰减,

$$
\int_0^{+\infty}\mathrm{e}^{-\left(b-\mathrm{i}x\right)y}\,\mathrm{d}y=\frac{1}{b-\mathrm{i}x},\qquad\int_{-\infty}^{0}\mathrm{e}^{\left(b+\mathrm{i}x\right)y}\,\mathrm{d}y=\frac{1}{b+\mathrm{i}x}.\tag{C}
$$

第四步: 相加并通分. 把 (C) 代入 (B),

$$
\frac{1}{b-\mathrm{i}x}+\frac{1}{b+\mathrm{i}x}=\frac{\left(b+\mathrm{i}x\right)+\left(b-\mathrm{i}x\right)}{b^{2}+x^{2}}=\frac{2b}{b^{2}+x^{2}}.\tag{D}
$$

第五步: 结论. 把 (D) 代入 (A),

$$
\mathcal{F}^{-1}\left[\mathrm{e}^{-b\left|y\right|}\right]\left(x\right)=\frac{1}{2\pi}\cdot\frac{2b}{b^{2}+x^{2}}=\frac{b}{\pi\left(b^{2}+x^{2}\right)}.
$$

第六步: 说明该结果的对称性: 上式正是 Cauchy 分布的密度 (差一个归一化常数), 由此也可看出 $\mathcal{F}\left[\frac{b}{\pi\left(b^{2}+x^{2}\right)}\right]\left(y\right)=\mathrm{e}^{-b\left|y\right|}$, 即该函数对是 Fourier 变换意义下的自对偶对.
