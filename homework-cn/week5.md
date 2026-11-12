# week5

> **定理 2.3.1 (弱极值原理)**
> 
> 设 $u\in{C}^{2}\left(\Omega\right)\cap{C}^{0}\left(\overline{\Omega}\right)$ 在 $\Omega$ 内满足 $\Delta{u}\ge0$ (或 $\Delta{u}\le0$), 则 $u$ 在 $\overline{\Omega}$ 上的最大值 (最小值) 在 $\partial\Omega$ 上达到.

> **定义 2.4.1 (基本解)**
> 
> $\Gamma\left(x\right)=\frac{1}{2\pi}\ln\frac{1}{\left|x\right|}$ ($n=2$), $\Gamma\left(x\right)=\frac{1}{\left(n-2\right)\omega_n}\left|x\right|^{2-n}$ ($n\ge3$); 且 $\partial_{x_i}\Gamma\left(x\right)=-\frac{x_i}{\omega_n\left|x\right|^{n}}$.

> **公式 2.5.2 (Green 第二恒等式)**
> 
> $\int_{\Omega}\left(v\Delta{u}-u\Delta{v}\right)\mathrm{d}x=\int_{\partial\Omega}\left(v\frac{\partial{u}}{\partial\nu}-u\frac{\partial{v}}{\partial\nu}\right)\mathrm{d}S$, $\nu$ 为 $\partial\Omega$ 的单位外法向.

> **定义 2.5.3 (Green 函数)**
> 
> 设 $\Phi\left(x,\cdot\right)\in{C}^{1}\left(\overline{\Omega}\right)\cap{C}^{2}\left(\Omega\right)$ 是 $\Delta_y\Phi\left(x,y\right)=0$ ($y\in\Omega$), $\Phi\left(x,y\right)=-\Gamma\left(x,y\right)$ ($y\in\partial\Omega$) 的解, 则 $G\left(x,y\right):=\Gamma\left(x,y\right)+\Phi\left(x,y\right)$ 称为区域 $\Omega$ 上的 Green 函数; 且当 $\Delta{u}=0$ 时, $u\left(x\right)=-\int_{\partial\Omega}\varphi\left(y\right)\frac{\partial{G}}{\partial\nu}\left(x,y\right)\,\mathrm{d}S$.

> **定义 2.7.1 (内球条件)**
> 
> 设 $x_0\in\partial\Omega$. 若存在球 $B_R\left(y\right)\subset\Omega$, 使得 $\overline{B}_R\left(y\right)\cap\overline{\Omega}=\left\{x_0\right\}$ 且 $B_R\left(y\right)$ 在 $x_0$ 处的单位外法向量与 $\Omega$ 在 $x_0$ 处的单位外法向量重合, 则称 $\Omega$ 在 $x_0$ 满足内球条件.

> **引理 2.7.2 (霍普夫引理)**
> 
> 设 $\Omega\subset\mathbb{R}^{n}$ 为一个区域, $\nu$ 是 $\partial\Omega$ 的单位外法向量, $x_0\in\partial\Omega$, 且 $\partial\Omega$ 在 $x_0$ 点满足内球条件. 设函数 $u\in{C}^{2}\left(\Omega\right)\cap{C}^{1}\left(\overline{\Omega}\right)$ 在 $\Omega$ 内下调和, 在 $x_0$ 点连续, 并且对任意 $x\in\Omega$ 有 $u\left(x_0\right)>u\left(x\right)$, 则其在边界点 $x_0$ 处的法向导数满足 $\frac{\partial{u}}{\partial\nu}\left(x_0\right)>0$.

## 习题 2.13 (上半空间的 Poisson 公式)

试求上半空间 $\mathbb{R}^{n}_{+}=\left\{x\in\mathbb{R}^{n}\,\middle|\,x_n>0\right\}$ 上 Laplace 方程 Dirichlet 问题的 Poisson 公式.

### 解答 2.13

第一步: 用关于超平面 $x_n=0$ 的镜像点构造 Green 函数. 记 $\bar{x}=\left(x_1,\dots,x_{n-1},-x_n\right)$, 则 $\bar{x}\notin\mathbb{R}^{n}_{+}$. 定义

$$
G\left(x,y\right):=\Gamma\left(x-y\right)-\Gamma\left(\bar{x}-y\right),\qquad{x},y\in\mathbb{R}^{n}_{+}.\tag{A}
$$

第二步: 验证 (A) 是上半空间的 Green 函数. 由**定义 2.5.3 (Green 函数)**, 需 $\Delta_yG\left(x,\cdot\right)=0$ 于 $\mathbb{R}^{n}_{+}$ ($y\ne{x}$), 且 $G\left(x,\cdot\right)=0$ 于 $\partial\mathbb{R}^{n}_{+}$. 前者由 $\Gamma\left(x-\cdot\right)$ 除 $y=x$ 外调和, $\Gamma\left(\bar{x}-\cdot\right)$ 在 $\mathbb{R}^{n}_{+}$ 上处处调和 ($\bar{x}$ 不在 $\mathbb{R}^{n}_{+}$ 内); 后者由第三步的等式.

第三步: 边界上的距离相等. 对 $y\in\partial\mathbb{R}^{n}_{+}$, 即 $y_n=0$,

$$
\left|\bar{x}-y\right|^{2}=\left|x'-y'\right|^{2}+\left(-x_n\right)^{2}=\left|x'-y'\right|^{2}+x_n^{2}=\left|x-y\right|^{2}.\tag{B}
$$

故 $\left|\bar{x}-y\right|=\left|x-y\right|$, 而 $\Gamma$ 只依赖宗量的绝对值, 于是 $G\left(x,y\right)=\Gamma\left(x-y\right)-\Gamma\left(\bar{x}-y\right)=0$.

第四步: 计算 $G$ 的外法向导数. $\mathbb{R}^{n}_{+}$ 的单位外法向是 $\nu=-e_n$, 故 $\frac{\partial{G}}{\partial\nu}\left(x,y\right)=-\frac{\partial{G}}{\partial{y_n}}\left(x,y\right)$. 由**定义 2.4.1 (基本解)**, 对 $z=x-y$,

$$
\frac{\partial}{\partial{y_n}}\Gamma\left(x-y\right)=\frac{x_n-y_n}{\omega_n\left|x-y\right|^{n}},\qquad\frac{\partial}{\partial{y_n}}\Gamma\left(\bar{x}-y\right)=\frac{\bar{x}_n-y_n}{\omega_n\left|\bar{x}-y\right|^{n}}=\frac{-x_n-y_n}{\omega_n\left|x-y\right|^{n}},
$$

其中第二个等式用了 (B). 两式相减并在 $y_n=0$ 上取值,

$$
\frac{\partial{G}}{\partial{y_n}}\left(x,y\right)=\frac{\left(x_n-y_n\right)+\left(x_n+y_n\right)}{\omega_n\left|x-y\right|^{n}}=\frac{2x_n}{\omega_n\left|x-y\right|^{n}}.\tag{C}
$$

第五步: 由 (C) 与 $\nu=-e_n$,

$$
-\frac{\partial{G}}{\partial\nu}\left(x,y\right)=\frac{2x_n}{\omega_n\left|x-y\right|^{n}},\qquad{y}\in\partial\mathbb{R}^{n}_{+}.\tag{D}
$$

第六步: 写出解. 由**定义 2.5.3 (Green 函数)** 给出的表示式, 当 $\Delta{u}=0$ 于 $\mathbb{R}^{n}_{+}$, $u=\varphi$ 于 $\partial\mathbb{R}^{n}_{+}$ 时,

$$
u\left(x\right)=-\int_{\partial\mathbb{R}^{n}_{+}}\varphi\left(y\right)\frac{\partial{G}}{\partial\nu}\left(x,y\right)\,\mathrm{d}S=\frac{2x_n}{\omega_n}\int_{\mathbb{R}^{n-1}}\frac{\varphi\left(y'\right)}{\left(\left|x'-y'\right|^{2}+x_n^{2}\right)^{\frac{n}{2}}}\,\mathrm{d}y'.\tag{E}
$$

这里用了 $\mathrm{d}S=\mathrm{d}y'$, $\left|x-y\right|^{2}=\left|x'-y'\right|^{2}+x_n^{2}$.

第七步: 核对符号. 由 (D) 知核非负; 又由 (E) 取 $\varphi\equiv1$ 应得 $u\equiv1$, 即该核在 $\mathbb{R}^{n-1}$ 上的积分为 $1$, 这与核的非负性相容. 于是 (E) 就是上半空间 Laplace 方程 Dirichlet 问题的 Poisson 公式.

## 习题 2.14 (上半平面 Poisson 积分的具体计算)

求解 $\mathbb{R}^{2}_{+}=\left\{\left(x_1,x_2\right)\in\mathbb{R}^{2}\,\middle|\,x_2>0\right\}$ 上 Laplace 方程 Dirichlet 问题

$$
\Delta{u}=0,\quad{x}_2>0;\qquad\left.{u}\right|_{x_2=0}=\frac{1}{1+x_1^{2}}.
$$

### 解答 2.14

第一步: 写出 Poisson 积分. 由习题 2.13 的 (E), 取 $n=2$, 注意 $\omega_2=2\pi$, 于是

$$
u\left(x_1,x_2\right)=\frac{2x_2}{2\pi}\int_{\mathbb{R}}\frac{\varphi\left(\xi\right)}{\left(x_1-\xi\right)^{2}+x_2^{2}}\,\mathrm{d}\xi=\frac{x_2}{\pi}\int_{-\infty}^{+\infty}\frac{1}{1+\xi^{2}}\cdot\frac{\mathrm{d}\xi}{\left(x_1-\xi\right)^{2}+x_2^{2}}.\tag{A}
$$

第二步: 记 $A=x_1$, $B=x_2>0$, $D=\left(A^{2}+B^{2}-1\right)^{2}+4A^{2}$, 对被积函数作部分分式分解

$$
\frac{1}{\left(1+\xi^{2}\right)\left(\left(\xi-A\right)^{2}+B^{2}\right)}=\frac{1}{D}\left[\frac{2A\xi+A^{2}+B^{2}-1}{1+\xi^{2}}-\frac{2A\xi-\left(3A^{2}-B^{2}+1\right)}{\left(\xi-A\right)^{2}+B^{2}}\right].\tag{B}
$$

第三步: 验证 (B). 两端分母相同, 只需通分后的分子恒等于 $D$. 该分子为

$$
N\left(\xi\right)=\left(2A\xi+A^{2}+B^{2}-1\right)\left(\left(\xi-A\right)^{2}+B^{2}\right)-\left(2A\xi-3A^{2}+B^{2}-1\right)\left(1+\xi^{2}\right).
$$

把 $\left(\xi-A\right)^{2}+B^{2}=\xi^{2}-2A\xi+A^{2}+B^{2}$ 逐项乘开并按 $\xi$ 的幂次归并,

$$
\xi^{3}\;\text{项}:2A-2A=0,\qquad\xi^{2}\;\text{项}:\left(A^{2}+B^{2}-1\right)-4A^{2}+\left(3A^{2}-B^{2}+1\right)=0,
$$

$$
\xi\;\text{项}:2A\left(A^{2}+B^{2}\right)-2A\left(A^{2}+B^{2}-1\right)-2A=0,\qquad\text{常数项}:\left(A^{2}+B^{2}-1\right)\left(A^{2}+B^{2}\right)+\left(3A^{2}-B^{2}+1\right).
$$

常数项写开得 $\left(A^{2}+B^{2}\right)^{2}-2\left(A^{2}+B^{2}\right)+1+4A^{2}=\left(A^{2}+B^{2}-1\right)^{2}+4A^{2}=D$. 故 $N\left(\xi\right)\equiv{D}$, (B) 成立.

第四步: 逐项积分. 两式的奇函数部分在 $\mathbb{R}$ 上积分为零, 偶函数部分用 $\int_{\mathbb{R}}\frac{\mathrm{d}\xi}{1+\xi^{2}}=\pi$ 与 $\int_{\mathbb{R}}\frac{\mathrm{d}\xi}{\left(\xi-A\right)^{2}+B^{2}}=\frac{\pi}{B}$:

$$
\int_{\mathbb{R}}\frac{2A\xi+A^{2}+B^{2}-1}{1+\xi^{2}}\,\mathrm{d}\xi=\pi\left(A^{2}+B^{2}-1\right),\tag{C}
$$

$$
\int_{\mathbb{R}}\frac{2A\xi-\left(3A^{2}-B^{2}+1\right)}{\left(\xi-A\right)^{2}+B^{2}}\,\mathrm{d}\xi=\frac{\pi}{B}\left(2A^{2}-3A^{2}+B^{2}-1\right)=\frac{\pi}{B}\left(-A^{2}+B^{2}-1\right),\tag{D}
$$

其中第二个积分用了换元 $\xi-A=u$: 分子 $2Au+2A^{2}-3A^{2}+B^{2}-1$, 奇部积分为零, 偶部为 $\left(2A^{2}-3A^{2}+B^{2}-1\right)\int\frac{\mathrm{d}u}{u^{2}+B^{2}}$.

第五步: 把 (C)(D) 代入 (B) 再代入 (A). 注意 (B) 中第二个分式带负号, 而 (D) 的值本身为负, 故两部分同号相加,

$$
\int_{\mathbb{R}}\frac{\mathrm{d}\xi}{\left(1+\xi^{2}\right)\left(\left(\xi-A\right)^{2}+B^{2}\right)}=\frac{1}{D}\left[\pi\left(A^{2}+B^{2}-1\right)+\frac{\pi}{B}\left(A^{2}-B^{2}+1\right)\right],
$$

于是

$$
u\left(x_1,x_2\right)=\frac{B}{\pi}\cdot\frac{\pi}{D}\left[A^{2}+B^{2}-1+\frac{A^{2}-B^{2}+1}{B}\right]=\frac{B\left(A^{2}+B^{2}-1\right)+A^{2}-B^{2}+1}{D}.
$$

第六步: 把 $A=x_1$, $B=x_2$, $D=\left(x_1^{2}+x_2^{2}-1\right)^{2}+4x_1^{2}$ 代回,

$$
u\left(x_1,x_2\right)=\frac{x_2\left(x_1^{2}+x_2^{2}-1\right)+x_1^{2}-x_2^{2}+1}{\left(x_1^{2}+x_2^{2}-1\right)^{2}+4x_1^{2}}.\tag{E}
$$

第七步: 核对边界值. 在 (E) 中令 $x_2=0$,

$$
u\left(x_1,0\right)=\frac{x_1^{2}+1}{\left(x_1^{2}-1\right)^{2}+4x_1^{2}}=\frac{x_1^{2}+1}{\left(x_1^{2}+1\right)^{2}}=\frac{1}{1+x_1^{2}},
$$

与题设边值相符. 又 (E) 是对上半空间 Poisson 积分 (A) 的恒等变形, 由习题 2.13 的结论, (A) 给出的函数在 $x_2>0$ 内调和; 而该问题的解由极值原理 (对两个解的差用**定理 2.3.1 (弱极值原理)**) 在上半平面内唯一, 故 (E) 就是所求的解.

## 习题 2.15 (由一点处的所有导数确定调和函数)

设 $\Omega$ 是 $\mathbb{R}^{n}$ 中的连通开集, $u,v$ 是 $\Omega$ 上的两个调和函数. 若存在一点 $x_0\in\Omega$, 使得对任意多重指标 $\alpha$, 都有 $\partial^{\alpha}u\left(x_0\right)=\partial^{\alpha}v\left(x_0\right)$, 则 $u\equiv{v}$ 于 $\Omega$.

### 解答 2.15

第一步: 化归. 令 $w=u-v$, 则 $w$ 在 $\Omega$ 内调和, 且对任意 $\alpha$ 有 $\partial^{\alpha}w\left(x_0\right)=0$. 只需证 $w\equiv0$.

第二步: 在 $x_0$ 的一个球内 $w\equiv0$. 由 2.2 节末关于调和函数解析性的结论, 调和函数在 $\Omega$ 内实解析, 即存在 $r>0$ 使 $B_r\left(x_0\right)\subset\Omega$ 且 $w$ 在 $B_r\left(x_0\right)$ 内可展成 Taylor 级数

$$
w\left(x\right)=\sum_{\alpha}\frac{\partial^{\alpha}w\left(x_0\right)}{\alpha!}\left(x-x_0\right)^{\alpha},\qquad{x}\in{B}_r\left(x_0\right).
$$

由第一步, 该级数的所有系数为零, 故 $w\equiv0$ 于 $B_r\left(x_0\right)$.

第三步: 证明零点集既开又闭. 记

$$
E:=\left\{x\in\Omega\,\middle|\,\partial^{\alpha}w\left(x\right)=0\quad\text{对一切多重指标}\;\alpha\right\}.
$$

对任意 $x\in{E}$, 由第二步 (把 $x_0$ 换成 $x$) 存在 $\rho>0$ 使 $w\equiv0$ 于 $B_\rho\left(x\right)$, 从而该球内 $w$ 的一切偏导数都为零, 即 $B_\rho\left(x\right)\subset{E}$. 故 $E$ 是开集.

第四步: $E$ 是闭集 (在 $\Omega$ 中). 若 $x_k\in{E}$ 且 $x_k\to{x}\in\Omega$, 则由 $w$ 光滑, $\partial^{\alpha}w$ 连续, 故

$$
\partial^{\alpha}w\left(x\right)=\lim_{k\to\infty}\partial^{\alpha}w\left(x_k\right)=0
$$

对一切 $\alpha$ 成立, 即 $x\in{E}$.

第五步: 用连通性. 由第一步, $x_0\in{E}$, 故 $E$ 非空. 由第三步与第四步, $E$ 在连通的 $\Omega$ 中既开又闭且非空, 故 $E=\Omega$. 于是 $w\equiv0$ 于 $\Omega$, 即 $u\equiv{v}$.

## 习题 2.16 (弱意义下的调和性)

设 $u\in{C}^{2}\left(\Omega\right)$. 证明: 若对一切 $\varphi\in{C}_0^{2}\left(\Omega\right)$ 都有 $\int_{\Omega}u\Delta\varphi\,\mathrm{d}x=0$, 则 $u$ 是 $\Omega$ 上的调和函数.

### 解答 2.16

第一步: 把条件转成 $\Delta{u}$ 的积分条件. 取任意 $\varphi\in{C}_0^{2}\left(\Omega\right)$. 由 $\varphi$ 在 $\partial\Omega$ 的一个邻域内为零, 在**公式 2.5.2 (Green 第二恒等式)** 中边界积分为零, 即

$$
\int_{\Omega}\left(u\Delta\varphi-\varphi\Delta{u}\right)\mathrm{d}x=0.
$$

第二步: 由题设 $\int_{\Omega}u\Delta\varphi\,\mathrm{d}x=0$, 于是

$$
\int_{\Omega}\varphi\left(x\right)\Delta{u}\left(x\right)\,\mathrm{d}x=0,\qquad\text{对一切}\;\varphi\in{C}_0^{2}\left(\Omega\right).\tag{A}
$$

第三步: 反证. 若存在 $x_1\in\Omega$ 使 $\Delta{u}\left(x_1\right)=c\ne0$. 由 $\Delta{u}$ 连续, 存在 $\rho>0$ 使 $\overline{B}_\rho\left(x_1\right)\subset\Omega$ 且在 $B_\rho\left(x_1\right)$ 内 $\Delta{u}$ 与 $c$ 同号, 且 $\left|\Delta{u}\right|\ge\frac{\left|c\right|}{2}$.

第四步: 取试验函数. 取 $\varphi\in{C}_0^{2}\left(\Omega\right)$, 满足 $\varphi\ge0$, $\operatorname{supp}\varphi\subset{B}_\rho\left(x_1\right)$, 且在 $B_{\rho/2}\left(x_1\right)$ 上 $\varphi\equiv1$. 则

$$
\int_{\Omega}\varphi\Delta{u}\,\mathrm{d}x=\int_{B_\rho\left(x_1\right)}\varphi\Delta{u}\,\mathrm{d}x
$$

的被积函数在 $B_\rho$ 内与 $c$ 同号, 且在 $B_{\rho/2}$ 上 $\varphi=1$, 故该积分的符号与 $c$ 相同, 且绝对值不小于 $\frac{\left|c\right|}{2}\left|B_{\rho/2}\left(x_1\right)\right|>0$, 与 (A) 矛盾.

第五步: 故 $\Delta{u}\equiv0$ 于 $\Omega$, 即 $u$ 是 $\Omega$ 上的调和函数.

## 习题 2.17 (环形椭圆区域上调和函数的最大值)

设 $\Omega=\left\{\left(x,y\right)\in\mathbb{R}^{2}\,\middle|\,1<{}x^{2}+2y^{2}<2\right\}$, $u\in{C}^{2}\left(\overline{\Omega}\right)$ 满足

$$
\begin{cases}\Delta{u}=0,&\text{于}\;\Omega,\\u=x+y,&\text{于}\;x^{2}+2y^{2}=2,\\\frac{\partial{u}}{\partial\nu}+\left(1-x\right)u=0,&\text{于}\;x^{2}+2y^{2}=1,\end{cases}
$$

其中 $\nu$ 是 $\partial\Omega$ 的单位外法向. 求 $\max_{\overline{\Omega}}u$.

### 解答 2.17

第一步: 记外边界 $\Gamma_2=\left\{x^{2}+2y^{2}=2\right\}$, 内边界 $\Gamma_1=\left\{x^{2}+2y^{2}=1\right\}$. 先算 $u$ 在 $\Gamma_2$ 上的值. 在 $\Gamma_2$ 上 $u=x+y$, 由 Cauchy-Schwarz 不等式

$$
\left(x+y\right)^{2}=\left(x\cdot1+\sqrt{2}y\cdot\frac{1}{\sqrt{2}}\right)^{2}\le\left(x^{2}+2y^{2}\right)\left(1+\frac{1}{2}\right)=2\cdot\frac{3}{2}=3,\tag{A}
$$

等号当 $\left(x,\sqrt{2}y\right)=t\left(1,\frac{1}{\sqrt{2}}\right)$ 时成立, 即 $x=t$, $y=\frac{t}{2}$. 代入 $x^{2}+2y^{2}=2$ 得 $\frac{3}{2}t^{2}=2$, $t=\frac{2}{\sqrt{3}}$, 对应的点为 $\left(\frac{2}{\sqrt{3}},\frac{1}{\sqrt{3}}\right)\in\Gamma_2$. 故

$$
\max_{\Gamma_2}u=\sqrt{3},\qquad{M}:=\max_{\overline{\Omega}}u\ge\sqrt{3}>0.\tag{B}
$$

第二步: 最大值不在 $\Omega$ 内部达到. 由 $\Delta{u}=0$ 于 $\Omega$ 与**定理 2.3.1 (弱极值原理)** (对 $u$ 与 $-u$ 同时使用), $u$ 的最大值与最小值都在 $\partial\Omega$ 上达到.

第三步: 设最大值在 $\Gamma_1$ 上某点 $p=\left(x,y\right)$ 达到. 椭圆 $\Gamma_1$ 是光滑闭曲线, 区域 $\Omega$ 在 $p$ 处满足**定义 2.7.1 (内球条件)**: 取以 $p$ 为切点的内切圆盘, 它整个含于 $\Omega$ 且与 $\overline{\Omega}$ 只交于 $p$, 法向重合. 又 $u$ 在 $\Omega$ 内调和 (从而下调和), 且 $u\left(p\right)=M>u\left(x\right)$ 对一切 $x\in\Omega$ 成立 (由第二步, $p$ 是整体最大点). 于是由**引理 2.7.2 (霍普夫引理)**,

$$
\frac{\partial{u}}{\partial\nu}\left(p\right)>0,\tag{C}
$$

其中 $\nu$ 是 $\Omega$ 在 $p$ 处的单位外法向 ($\Gamma_1$ 上的外法向指向原点一侧).

第四步: 与内边界条件矛盾. 在 $p$ 处题设的边界条件给出 $\frac{\partial{u}}{\partial\nu}\left(p\right)=-\left(1-x\right)u\left(p\right)=\left(x-1\right)M$. 由 (C) 得 $\left(x-1\right)M>0$, 而 $M>0$, 故 $x>1$. 但 $\Gamma_1$ 上 $x^{2}+2y^{2}=1$, 故 $x^{2}\le1$, $x\le1$, 矛盾.

第五步: 结论. 由第二步与第三, 四步, 最大值只能在 $\Gamma_2$ 上达到, 故由 (B)

$$
\max_{\overline{\Omega}}u=\max_{\Gamma_2}\left(x+y\right)=\sqrt{3}.
$$

最大值在 $\left(\frac{2}{\sqrt{3}},\frac{1}{\sqrt{3}}\right)$ 处取到.
