# week4

> **定理 2.3.1 (弱极值原理)**
> 
> 设 $u\in{C}^{2}\left(\Omega\right)\cap{C}^{0}\left(\overline{\Omega}\right)$ 在 $\Omega$ 内满足 $\Delta{u}\ge0$ (或 $\Delta{u}\le0$), 则 $u$ 在 $\overline{\Omega}$ 上的最大值 (最小值) 在 $\partial\Omega$ 上达到.

> **定义 2.4.1 (基本解)**
> 
> $\Gamma\left(x\right)=\frac{1}{2\pi}\ln\frac{1}{\left|x\right|}$ ($n=2$), $\Gamma\left(x\right)=\frac{1}{\left(n-2\right)\omega_n}\left|x\right|^{2-n}$ ($n\ge3$); 且 $\partial_{x_i}\Gamma\left(x\right)=-\frac{x_i}{\omega_n\left|x\right|^{n}}$.

> **定理 2.5.1 (Green 表示公式)**
> 
> 设 $\Omega$ 是 $\mathbb{R}^{n}$ 中的有界区域, $u\in{C}^{1}\left(\overline{\Omega}\right)\cap{C}^{2}\left(\Omega\right)$. 则对任意固定点 $a\in\Omega$, $u\left(a\right)=\int_{\partial\Omega}\left(\Gamma\left(a,x\right)\frac{\partial{u}}{\partial\nu}\left(x\right)-u\left(x\right)\frac{\partial\Gamma}{\partial\nu}\left(a,x\right)\right)\mathrm{d}S-\int_{\Omega}\Gamma\left(a,x\right)\Delta{u}\left(x\right)\,\mathrm{d}x$, 其中 $\nu$ 是 $\partial\Omega$ 的单位外法向.

> **定义 2.5.3 (Green 函数)**
> 
> 设 $\Phi\left(x,\cdot\right)\in{C}^{1}\left(\overline{\Omega}\right)\cap{C}^{2}\left(\Omega\right)$ 是 $\Delta_y\Phi\left(x,y\right)=0$ ($y\in\Omega$), $\Phi\left(x,y\right)=-\Gamma\left(x,y\right)$ ($y\in\partial\Omega$) 的解, 则 $G\left(x,y\right):=\Gamma\left(x,y\right)+\Phi\left(x,y\right)$ 称为区域 $\Omega$ 上的 Green 函数, 且 $u\left(x\right)=\int_{\Omega}G\left(x,y\right)f\left(y\right)\,\mathrm{d}y+\int_{\partial\Omega}\varphi\left(y\right)\frac{\partial{G}}{\partial\nu}\left(x,y\right)\,\mathrm{d}S$ 是 Poisson 方程 Dirichlet 问题的解.

> **定义 2.5.4 (上半空间 Poisson 核)**
> 
> $P\left(x,y\right)=\frac{2x_n}{\omega_n\left|x-y\right|^{n}}$, $x\in\mathbb{R}^{n}_{+}$, $y\in\partial\mathbb{R}^{n}_{+}$, 称为上半空间 $\mathbb{R}^{n}_{+}$ 上的 Poisson 核.

> **定义 2.5.6 (球上的 Poisson 核)**
> 
> $K\left(x,y\right):=\frac{\partial{G}}{\partial\nu}\left(x,y\right)=\frac{1}{\omega_nR}\frac{R^{2}-\left|x\right|^{2}}{\left|x-y\right|^{n}}$, $x\in{B}_R\left(0\right)$, $y\in\partial{B}_R\left(0\right)$.

> **定理 2.5.7 (Poisson 积分公式)**
> 
> 设 $\varphi\in{C}^{0}\left(\partial{B}_R\left(0\right)\right)$, 则由 (2.5.10) 定义的 $u$ 属于 $C\left(\overline{\Omega}\right)\cap{C}^{\infty}\left(\Omega\right)$, 且是 $\Delta{u}=0$ (于 $B_R\left(0\right)$), $u=\varphi$ (于 $\partial{B}_R\left(0\right)$) 的解; 且 $\int_{\partial{B}_R\left(0\right)}K\left(x,y\right)\,\mathrm{d}S=1$.

> **公式 2.5.9 (上半空间的 Poisson 公式)**
> 
> 对 $\varphi\in{C}^{0}\left(\mathbb{R}^{n-1}\right)$, $u\left(x\right)=\frac{2x_n}{\omega_n}\int_{\mathbb{R}^{n-1}}\frac{\varphi\left(y'\right)}{\left(\left|x'-y'\right|^{2}+x_n^{2}\right)^{\frac{n}{2}}}\,\mathrm{d}y'$.

## 习题 2.8 (调和函数在球心处的梯度估计)

设 $u\in{C}^{1}\left(\overline{B}_R\right)$ 且在 $B_R$ 中满足 $\Delta{u}=0$, 试证: $\left|\partial_{x_i}u\left(0\right)\right|\le\frac{n}{R}\max_{\overline{B}_R}\left|u\right|$, $i=1,2,\dots,n$.

### 解答 2.8

第一步: 由**定理 2.5.7 (Poisson 积分公式)** 与**定义 2.5.6 (球上的 Poisson 核)**, 对 $\left|x\right|<{}R$,

$$
u\left(x\right)=\frac{1}{\omega_nR}\int_{\partial{B}_R}\frac{R^{2}-\left|x\right|^{2}}{\left|x-y\right|^{n}}u\left(y\right)\,\mathrm{d}S.\tag{A}
$$

第二步: 对 (A) 关于 $x_i$ 求导. 被积函数对 $x$ 光滑, $\partial{B}_R$ 是紧集, 故可在积分号下求导. 用 $\partial_{x_i}\left|x-y\right|^{-n}=-n\frac{x_i-y_i}{\left|x-y\right|^{n+2}}$,

$$
\partial_{x_i}u\left(x\right)=\frac{1}{\omega_nR}\left[-2x_i\int_{\partial{B}_R}\frac{u\left(y\right)}{\left|x-y\right|^{n}}\,\mathrm{d}S-n\int_{\partial{B}_R}\frac{\left(x_i-y_i\right)u\left(y\right)}{\left|x-y\right|^{n+2}}\,\mathrm{d}S\right].\tag{B}
$$

其中第一项的系数由 $\partial_{x_i}\left(R^{2}-\left|x\right|^{2}\right)=-2x_i$ 得来.

第三步: 在 (B) 中令 $x=0$. 第一项含因子 $x_i$ 而消失; 第二项中 $\left|x-y\right|=\left|y\right|=R$ 且 $x_i-y_i=-y_i$,

$$
\partial_{x_i}u\left(0\right)=\frac{n}{\omega_nR}\int_{\partial{B}_R}\frac{u\left(y\right)y_i}{R^{n+2}}\,\mathrm{d}S=\frac{n}{\omega_nR^{n+1}}\int_{\partial{B}_R}u\left(y\right)y_i\,\mathrm{d}S.\tag{C}
$$

第四步: 估计 (C). 由 $\left|u\left(y\right)\right|\le\max_{\overline{B}_R}\left|u\right|$ 与 $\left|y_i\right|\le\left|y\right|=R$,

$$
\left|\int_{\partial{B}_R}u\left(y\right)y_i\,\mathrm{d}S\right|\le\max_{\overline{B}_R}\left|u\right|\cdot{R}\cdot\omega_nR^{n-1}=\max_{\overline{B}_R}\left|u\right|\,\omega_nR^{n}.
$$

第五步: 代回 (C),

$$
\left|\partial_{x_i}u\left(0\right)\right|\le\frac{n}{\omega_nR^{n+1}}\cdot\max_{\overline{B}_R}\left|u\right|\,\omega_nR^{n}=\frac{n}{R}\max_{\overline{B}_R}\left|u\right|.
$$

## 习题 2.9 (上半空间 Poisson 积分的性质)

试证: 若 $\varphi\in{C}^{0}\left(\mathbb{R}^{n-1}\right)\cap{L}^{\infty}\left(\mathbb{R}^{n-1}\right)$, 则由 (2.5.9) 给出的 $u\in{C}^{\infty}\left(\mathbb{R}^{n}_{+}\right)\cap{L}^{\infty}\left(\mathbb{R}^{n}_{+}\right)$ 且满足

$$
\begin{cases}\Delta{u}=0,&x\in\mathbb{R}^{n}_{+},\\\lim_{x\to{x}_0}u\left(x\right)=\varphi\left(x_0\right),&x_0\in\partial\mathbb{R}^{n}_{+}.\end{cases}
$$

### 解答 2.9

第一步: 记 $P\left(x,y'\right)=\frac{2x_n}{\omega_n}\frac{1}{\left(\left|x'-y'\right|^{2}+x_n^{2}\right)^{\frac{n}{2}}}$ 为**定义 2.5.4 (上半空间 Poisson 核)**, 则 (2.5.9) 即 $u\left(x\right)=\int_{\mathbb{R}^{n-1}}P\left(x,y'\right)\varphi\left(y'\right)\,\mathrm{d}y'$. 由 $\varphi\in{L}^{\infty}$ 与 $P\left(x,\cdot\right)\in{L}^{1}$ (见第三步), 积分绝对收敛.

第二步: 证 $u\in{C}^{\infty}$ 且 $\Delta{u}=0$. $P$ 在 $\mathbb{R}^{n}_{+}\times\mathbb{R}^{n-1}$ 上光滑, 且 $\left|\partial^{\alpha}_{x}P\right|\le{C}_\alpha\left(1+\left|y'\right|\right)^{-n}$ 对任意多重指标 $\alpha$ 成立, 故可在积分号下求任意阶导数, $u\in{C}^{\infty}\left(\mathbb{R}^{n}_{+}\right)$ 且

$$
\partial^{\alpha}u\left(x\right)=\int_{\mathbb{R}^{n-1}}\partial^{\alpha}_{x}P\left(x,y'\right)\varphi\left(y'\right)\,\mathrm{d}y'.
$$

又 $P\left(x,y'\right)=-\frac{\partial{G}}{\partial\nu_y}\left(x,y'\right)$, 其中 $G$ 是上半空间的 Green 函数, 而 $\Delta_xG\left(x,y'\right)=0$, 故 $\Delta_xP\left(x,y'\right)=0$, 从而

$$
\Delta{u}\left(x\right)=\int_{\mathbb{R}^{n-1}}\Delta_xP\left(x,y'\right)\varphi\left(y'\right)\,\mathrm{d}y'=0,\qquad{x}\in\mathbb{R}^{n}_{+}.
$$

第三步: 证归一化 $\int_{\mathbb{R}^{n-1}}P\left(x,y'\right)\,\mathrm{d}y'=1$. 取 $\varphi\equiv1$, 它是 $\mathbb{R}^{n-1}$ 上的有界连续函数, 由**公式 2.5.9 (上半空间的 Poisson 公式)**, 相应的 $u\equiv1$ 是上半空间 Laplace 方程 Dirichlet 问题的解, 而 $u$ 由积分表示给出, 故 $\int_{\mathbb{R}^{n-1}}P\left(x,y'\right)\,\mathrm{d}y'=1$. 由此立即得到 $u\in{L}^{\infty}\left(\mathbb{R}^{n}_{+}\right)$ 且

$$
\left|u\left(x\right)\right|\le\left\|\varphi\right\|_{L^{\infty}}\int_{\mathbb{R}^{n-1}}P\left(x,y'\right)\,\mathrm{d}y'=\left\|\varphi\right\|_{L^{\infty}}.\tag{A}
$$

第四步: 证边界极限. 取定 $x_0\in\partial\mathbb{R}^{n}_{+}$, 即 $x_0=\left(x_0',0\right)$. 由第三步的归一化,

$$
u\left(x\right)-\varphi\left(x_0\right)=\int_{\mathbb{R}^{n-1}}P\left(x,y'\right)\left(\varphi\left(y'\right)-\varphi\left(x_0\right)\right)\mathrm{d}y'.\tag{B}
$$

第五步: 控制 $\left|y'-x_0'\right|<\delta$ 的部分. 由 $\varphi$ 在 $x_0'$ 处连续, 对任意 $\varepsilon>0$ 存在 $\delta>0$, 使得当 $\left|y'-x_0'\right|<\delta$ 时 $\left|\varphi\left(y'\right)-\varphi\left(x_0\right)\right|<\varepsilon$. 于是由 $P\ge0$ 与第三步,

$$
\left|\int_{\left|y'-x_0'\right|<\delta}P\left(x,y'\right)\left(\varphi\left(y'\right)-\varphi\left(x_0\right)\right)\mathrm{d}y'\right|\le\varepsilon\int_{\mathbb{R}^{n-1}}P\left(x,y'\right)\,\mathrm{d}y'=\varepsilon.\tag{C}
$$

第六步: 控制 $\left|y'-x_0'\right|\ge\delta$ 的部分. 设 $x\in\mathbb{R}^{n}_{+}$ 且 $\left|x-x_0\right|\le\frac{\delta}{2}$ (从而 $0<{}x_n\le\frac{\delta}{2}$). 对这样的 $x$ 与 $\left|y'-x_0'\right|\ge\delta$,

$$
\left|x'-y'\right|\ge\left|y'-x_0'\right|-\left|x'-x_0'\right|\ge\left|y'-x_0'\right|-\frac{\delta}{2}\ge\frac12\left|y'-x_0'\right|,
$$

故

$$
P\left(x,y'\right)\le\frac{2x_n}{\omega_n}\left(\frac{2}{\left|y'-x_0'\right|}\right)^{n}=\frac{2^{n+1}x_n}{\omega_n\left|y'-x_0'\right|^{n}}.\tag{D}
$$

第七步: 于是由 $\varphi\in{L}^{\infty}$ 与 (D),

$$
\left|\int_{\left|y'-x_0'\right|\ge\delta}P\left(x,y'\right)\left(\varphi\left(y'\right)-\varphi\left(x_0\right)\right)\mathrm{d}y'\right|\le\frac{2^{n+2}\left\|\varphi\right\|_{L^{\infty}}x_n}{\omega_n}\int_{\left|y'-x_0'\right|\ge\delta}\frac{\mathrm{d}y'}{\left|y'-x_0'\right|^{n}}.\tag{E}
$$

右端积分用球坐标: 在 $\mathbb{R}^{n-1}$ 中 $\int_{\left|y'-x_0'\right|\ge\delta}\left|y'-x_0'\right|^{-n}\mathrm{d}y'=\omega_{n-1}\int_\delta^{+\infty}r^{-n}r^{n-2}\,\mathrm{d}r=\frac{\omega_{n-1}}{\delta}$, 是有限的.

第八步: 由 (E) 与第七步,

$$
\left|\int_{\left|y'-x_0'\right|\ge\delta}P\left(x,y'\right)\left(\varphi\left(y'\right)-\varphi\left(x_0\right)\right)\mathrm{d}y'\right|\le\frac{2^{n+2}\left\|\varphi\right\|_{L^{\infty}}\omega_{n-1}}{\omega_n\delta}x_n\to0\qquad\left(x_n\to0^{+}\right).
$$

第九步: 把 (C) 与第八步代入 (B), 得 $\limsup_{x\to{x}_0}\left|u\left(x\right)-\varphi\left(x_0\right)\right|\le\varepsilon$. 由 $\varepsilon>0$ 任意, $\lim_{x\to{x}_0}u\left(x\right)=\varphi\left(x_0\right)$. 结合第二步与第三步, 结论全部得证.

## 习题 2.10 (球内解的球心值公式)

设 $B_r\equiv\left\{x\in\mathbb{R}^{n}\,\middle|\,\left|x\right|<{}r\right\}$, $f\in{C}^{0}\left(\overline{B}_r\right)$, $\varphi\in{C}^{0}\left(\partial{B}_r\right)$, $u\in{C}^{2}\left(B_r\right)\cap{C}^{0}\left(\overline{B}_r\right)$ 是 Dirichlet 问题

$$
\begin{cases}\Delta{u}=f\left(x\right),&x\in{B}_r,\\u=\varphi\left(x\right),&x\in\partial{B}_r\end{cases}
$$

的解. 证明: 当 $n\ge3$ 时,

$$
u\left(0\right)=\frac{1}{\omega_nr^{n-1}}\int_{\partial{B}_r}\varphi\left(x\right)\,\mathrm{d}S+\frac{1}{\left(n-2\right)\omega_n}\int_{B_r}\left(\frac{1}{r^{n-2}}-\frac{1}{\left|x\right|^{n-2}}\right)f\left(x\right)\,\mathrm{d}x;
$$

当 $n=2$ 时,

$$
u\left(0\right)=\frac{1}{2\pi{r}}\int_{\partial{B}_r}\varphi\left(x\right)\,\mathrm{d}S+\frac{1}{2\pi}\int_{B_r}\left(\ln\left|x\right|-\ln{r}\right)f\left(x\right)\,\mathrm{d}x.
$$

### 解答 2.10

第一步: 以 $a=0$ 代入**定理 2.5.1 (Green 表示公式)**, 注意 $\Gamma\left(0,x\right)=\Gamma\left(x\right)$,

$$
u\left(0\right)=\int_{\partial{B}_r}\left(\Gamma\left(x\right)\frac{\partial{u}}{\partial\nu}\left(x\right)-u\left(x\right)\frac{\partial\Gamma}{\partial\nu}\left(x\right)\right)\mathrm{d}S-\int_{B_r}\Gamma\left(x\right)\Delta{u}\left(x\right)\,\mathrm{d}x.\tag{A}
$$

第二步: 算边界上 $\Gamma$ 及其法向导数. 由**定义 2.4.1 (基本解)**, 在 $\left|x\right|=r$ 上 $\Gamma\left(x\right)=\frac{r^{2-n}}{\left(n-2\right)\omega_n}$ 为常数, 且由 $\partial_{x_i}\Gamma=-\frac{x_i}{\omega_n\left|x\right|^{n}}$ 与外法向 $\nu=\frac{x}{r}$,

$$
\frac{\partial\Gamma}{\partial\nu}\left(x\right)=\sum_{i=1}^{n}\left(-\frac{x_i}{\omega_n\left|x\right|^{n}}\right)\cdot\frac{x_i}{r}=-\frac{1}{\omega_nr^{n-1}},\qquad\left|x\right|=r.\tag{B}
$$

第三步: 把 (B) 代入 (A), 并用 $u=\varphi$, $\Delta{u}=f$,

$$
u\left(0\right)=\frac{r^{2-n}}{\left(n-2\right)\omega_n}\int_{\partial{B}_r}\frac{\partial{u}}{\partial\nu}\,\mathrm{d}S+\frac{1}{\omega_nr^{n-1}}\int_{\partial{B}_r}\varphi\,\mathrm{d}S-\frac{1}{\left(n-2\right)\omega_n}\int_{B_r}\frac{f\left(x\right)}{\left|x\right|^{n-2}}\,\mathrm{d}x.\tag{C}
$$

第四步: 把第一个积分化为体积分. 由散度定理,

$$
\int_{\partial{B}_r}\frac{\partial{u}}{\partial\nu}\,\mathrm{d}S=\int_{B_r}\Delta{u}\left(x\right)\,\mathrm{d}x=\int_{B_r}f\left(x\right)\,\mathrm{d}x.\tag{D}
$$

第五步: 把 (D) 代入 (C), 两项关于 $f$ 的积分合并,

$$
u\left(0\right)=\frac{1}{\omega_nr^{n-1}}\int_{\partial{B}_r}\varphi\,\mathrm{d}S+\frac{1}{\left(n-2\right)\omega_n}\int_{B_r}\left(\frac{1}{r^{n-2}}-\frac{1}{\left|x\right|^{n-2}}\right)f\left(x\right)\,\mathrm{d}x,
$$

这就是 $n\ge3$ 的公式.

第六步: $n=2$ 的情形同法. 此时 $\Gamma\left(x\right)=\frac{1}{2\pi}\ln\frac{1}{\left|x\right|}$, 在 $\left|x\right|=r$ 上 $\Gamma\left(x\right)=\frac{1}{2\pi}\ln\frac{1}{r}$, 且

$$
\frac{\partial\Gamma}{\partial\nu}\left(x\right)=\left(-\frac{1}{2\pi}\frac{x}{\left|x\right|^{2}}\right)\cdot\frac{x}{r}=-\frac{1}{2\pi{r}},\qquad\left|x\right|=r.
$$

于是与第三步同法,

$$
u\left(0\right)=\frac{1}{2\pi}\ln\frac{1}{r}\int_{\partial{B}_r}\frac{\partial{u}}{\partial\nu}\,\mathrm{d}S+\frac{1}{2\pi{r}}\int_{\partial{B}_r}\varphi\,\mathrm{d}S-\frac{1}{2\pi}\int_{B_r}f\left(x\right)\ln\frac{1}{\left|x\right|}\,\mathrm{d}x.
$$

第七步: 再用 (D) 消去 $\partial_\nu{u}$, 并把两个对数项合并,

$$
u\left(0\right)=\frac{1}{2\pi{r}}\int_{\partial{B}_r}\varphi\,\mathrm{d}S+\frac{1}{2\pi}\int_{B_r}\left(\ln\frac{1}{r}-\ln\frac{1}{\left|x\right|}\right)f\left(x\right)\,\mathrm{d}x=\frac{1}{2\pi{r}}\int_{\partial{B}_r}\varphi\,\mathrm{d}S+\frac{1}{2\pi}\int_{B_r}\left(\ln\left|x\right|-\ln{r}\right)f\left(x\right)\,\mathrm{d}x.
$$

## 习题 2.11 (Green 函数与基本解的大小关系)

设 $G\left(x,y\right)$ 是区域 $\Omega\subset\mathbb{R}^{n}$ 上的 Green 函数, 则 $0<{}G\left(x,y\right)<{}K\left(x-y\right)$, $x,y\in\Omega$, $x\ne{y}$, 其中 $K=\Gamma$ 是 Laplace 方程的基本解.

### 解答 2.11

第一步: 先把 $G$ 的上下界拆成两个不等式. 按**定义 2.5.3 (Green 函数)**, $G\left(x,y\right)=\Gamma\left(x-y\right)+\Phi\left(x,y\right)$, 其中 $\Phi\left(x,\cdot\right)$ 在 $\Omega$ 内调和, 在 $\partial\Omega$ 上等于 $-\Gamma\left(x-\cdot\right)$. 故 $G\left(x,y\right)<\Gamma\left(x-y\right)$ 等价于 $\Phi\left(x,y\right)<0$.

第二步: 证 $\Phi<0$ 于 $\overline{\Omega}$. 当 $n\ge3$ 时由**定义 2.4.1 (基本解)**, $\Gamma$ 恒正, 故 $\partial\Omega$ 上 $\Phi=-\Gamma\left(x-\cdot\right)<0$. 由 $\Delta_y\Phi=0$ 于 $\Omega$ 与**定理 2.3.1 (弱极值原理)**,

$$
\max_{\overline{\Omega}}\Phi\left(x,\cdot\right)=\max_{y\in\partial\Omega}\left(-\Gamma\left(x-y\right)\right)<0.\tag{A}
$$

第三步: 由 (A) 得 $\Phi\left(x,y\right)<0$ 于 $\overline{\Omega}$, 于是 $G\left(x,y\right)=\Gamma\left(x-y\right)+\Phi\left(x,y\right)<\Gamma\left(x-y\right)$. 这就证得右半不等式.

第四步: 证 $G>0$ 于 $\Omega\setminus\left\{x\right\}$. 对 $G\left(x,\cdot\right)$: 由**定义 2.5.3 (Green 函数)** 中 $\Phi$ 的调和性与 $\Gamma$ 的调和性, $\Delta_yG\left(x,\cdot\right)=0$ 于 $\Omega\setminus\left\{x\right\}$; 又 $\Gamma,\Phi$ 在 $\partial\Omega$ 上相互抵消, 即 $G\left(x,\cdot\right)=0$ 于 $\partial\Omega$.

第五步: 取 $\varepsilon>0$ 充分小使 $\overline{B}_\varepsilon\left(x\right)\subset\Omega$, 以 $\Omega\setminus\overline{B}_\varepsilon\left(x\right)$ 代 $\Omega$ 用**定理 2.3.1 (弱极值原理)** 于 $-G$, 最小值在边界达到,

$$
\min_{\Omega\setminus\overline{B}_\varepsilon\left(x\right)}G\left(x,\cdot\right)=\min\left\{\min_{\partial\Omega}G\left(x,\cdot\right),\min_{\partial{B}_\varepsilon\left(x\right)}G\left(x,\cdot\right)\right\}=\min\left\{0,\min_{\partial{B}_\varepsilon\left(x\right)}G\left(x,\cdot\right)\right\}.\tag{B}
$$

第六步: 估计 $\partial{B}_\varepsilon\left(x\right)$ 上的值. 由 $G\left(x,y\right)=\Gamma\left(x-y\right)+\Phi\left(x,y\right)$, 而 $\Phi\left(x,\cdot\right)$ 在 $\overline{B}_\varepsilon\left(x\right)$ 上有界 (它在 $\Omega$ 内调和, 故在紧集上连续), 记其界为 $M$; 又 $\Gamma\left(x-y\right)\to+\infty$ 当 $y\to{x}$. 故当 $\varepsilon$ 充分小时

$$
G\left(x,y\right)\ge\Gamma\left(x-y\right)-M>0,\qquad{y}\in\partial{B}_\varepsilon\left(x\right).
$$

第七步: 代回 (B), 得 $G\left(x,y\right)>0$ 于 $\Omega\setminus\overline{B}_\varepsilon\left(x\right)$, 令 $\varepsilon\to0$ 即 $G\left(x,y\right)>0$ 于 $\Omega\setminus\left\{x\right\}$. 结合第三步, 得 $0<{}G\left(x,y\right)<\Gamma\left(x-y\right)$.

注: 第二步用到 $\Gamma>0$, 这对 $n\ge3$ 恒成立. 当 $n=2$ 时 $\Gamma\left(z\right)=\frac{1}{2\pi}\ln\frac{1}{\left|z\right|}$ 在 $\left|z\right|>1$ 处变负, 此时 $\Phi$ 的边界值为正, 结论 $G<\Gamma$ 只在 $\Gamma\left(x-y\right)>0$ (即 $\left|x-y\right|<1$) 的范围内成立; 但 $G>0$ 的证明 (第四至七步) 对 $n=2$ 不变.

## 习题 2.12 (单位圆外部的 Green 函数)

求 Laplace 方程在单位圆外部区域 $\Omega=\mathbb{R}^{2}\setminus\overline{B}_1\left(0\right)$ 上的 Green 函数.

### 解答 2.12

第一步: 用关于单位圆的反演. 对 $x\in\Omega$ ($\left|x\right|>1$) 定义反演点

$$
x^{*}:=\frac{x}{\left|x\right|^{2}},\qquad\left|x^{*}\right|=\frac{1}{\left|x\right|}<1.
$$

第二步: 证边界上的关键等式. 对 $y\in\partial{B}_1\left(0\right)$, 即 $\left|y\right|=1$,

$$
\left|x^{*}-y\right|^{2}=\left|x^{*}\right|^{2}-2x^{*}\cdot{y}+\left|y\right|^{2}=\frac{1}{\left|x\right|^{2}}-\frac{2x\cdot{y}}{\left|x\right|^{2}}+1=\frac{\left|x\right|^{2}-2x\cdot{y}+\left|y\right|^{2}}{\left|x\right|^{2}}=\frac{\left|x-y\right|^{2}}{\left|x\right|^{2}},
$$

其中用了 $\left|x^{*}\right|^{2}=1/\left|x\right|^{2}$, $x^{*}\cdot{y}=\left(x\cdot{y}\right)/\left|x\right|^{2}$, $\left|y\right|=1$. 故

$$
\left|x\right|\left|x^{*}-y\right|=\left|x-y\right|,\qquad{y}\in\partial{B}_1\left(0\right).\tag{A}
$$

第三步: 构造 Green 函数. 由 (A), 函数

$$
G\left(x,y\right):=\Gamma\left(x-y\right)-\Gamma\left(\left|x\right|\left|x^{*}-y\right|\right),\qquad{x},y\in\Omega,x\ne{y}\tag{B}
$$

在 $\partial{B}_1\left(0\right)$ 上为零: 由 (A) 两基本解的宗量绝对值相同, 而 $\Gamma$ 只依赖 $\left|x-y\right|$.

第四步: 验证 (B) 是 Green 函数. 由**定义 2.5.3 (Green 函数)**, 只需验证 $G\left(x,\cdot\right)$ 作为 $y$ 的函数在 $\Omega$ 内除 $y=x$ 外调和, 在 $\partial\Omega$ 上等于零, 并且当 $\left|y\right|\to\infty$ 时 $G\left(x,y\right)\to0$. 调和性: $\Gamma\left(x-y\right)$ 与 $\Gamma\left(\left|x\right|\left|x^{*}-y\right|\right)$ 在 $y\ne{x}$ 与 $y\ne{x}^{*}$ 处分别调和, 而 $x\in\Omega$, $x^{*}\in{B}_1\left(0\right)\subset\mathbb{R}^{2}\setminus\overline{\Omega}$, 故后者在 $\Omega$ 上处处调和. 边界值为零由第三步. 无穷远: 当 $\left|y\right|\to\infty$ 时 $\left|x-y\right|\sim\left|y\right|$, $\left|x^{*}-y\right|\sim\left|y\right|$, 两个对数之差趋于零.

第五步: 写出显式. 把 $\Gamma\left(z\right)=\frac{1}{2\pi}\ln\frac{1}{\left|z\right|}$ 代入 (B),

$$
G\left(x,y\right)=\frac{1}{2\pi}\ln\frac{1}{\left|x-y\right|}-\frac{1}{2\pi}\ln\frac{1}{\left|x\right|\left|x^{*}-y\right|}=\frac{1}{2\pi}\ln\frac{\left|x\right|\left|x^{*}-y\right|}{\left|x-y\right|}.
$$

这就是所求的 Green 函数.
