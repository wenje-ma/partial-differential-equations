# week6

> **定理 2.3.1 (弱极值原理)**
> 
> 设 $u\in{C}^{2}\left(\Omega\right)\cap{C}^{0}\left(\overline{\Omega}\right)$ 在 $\Omega$ 内满足 $\Delta{u}\ge0$ (或 $\Delta{u}\le0$), 则 $u$ 在 $\overline{\Omega}$ 上的最大值 (最小值) 在 $\partial\Omega$ 上达到.

> **定义 2.4.1 (基本解)**
> 
> $\Gamma\left(x\right)=\frac{1}{2\pi}\ln\frac{1}{\left|x\right|}$ ($n=2$), $\Gamma\left(x\right)=\frac{1}{\left(n-2\right)\omega_n}\left|x\right|^{2-n}$ ($n\ge3$).

> **定理 2.5.7 (Poisson 积分公式)**
> 
> 设 $\varphi\in{C}^{0}\left(\partial{B}_R\left(0\right)\right)$, 则由球面 Poisson 积分定义的 $u$ 属于 $C\left(\overline{B}_R\left(0\right)\right)\cap{C}^{\infty}\left(B_R\left(0\right)\right)$, 且在 $B_R\left(0\right)$ 内调和, 在 $\partial{B}_R\left(0\right)$ 上等于 $\varphi$.

> **定义 2.6.12 (外球条件)**
> 
> 设 $x_0\in\partial\Omega$. 若存在球 $B_R\left(y\right)\subset\mathbb{R}^{n}\setminus\Omega$, 使得 $\overline{B}_R\left(y\right)\cap\overline{\Omega}=\left\{x_0\right\}$, 则称 $\Omega$ 在 $x_0$ 处满足外球条件. 若 $\Omega$ 在每一个边界点都满足外球条件, 则称 $\Omega$ 满足外球条件.

> **定理 2.6.14 (Dirichlet 问题解的存在性)**
> 
> 设区域 $\Omega\subset\mathbb{R}^{n}$ 有界, 边界函数 $\varphi\in{C}^{0}\left(\partial\Omega\right)$. 若 $\Omega$ 满足外球条件, 则 Laplace 方程 Dirichlet 边值问题存在唯一解 $u\in{C}^{2}\left(\Omega\right)\cap{C}^{0}\left(\overline{\Omega}\right)$, 唯一性由弱极值原理保证.

## 习题 2.18 (椭圆方程组的最大模估计)

设 $\Omega$ 是 $\mathbb{R}^{n}$ 的一个有界区域, $f,g\in{C}^{0}\left(\overline{\Omega}\right)$, $u,v\in{C}^{2}\left(\Omega\right)\cap{C}^{0}\left(\overline{\Omega}\right)$ 满足方程组

$$
\begin{cases}-\Delta{u}+2u-v=f\left(x\right),&x\in\Omega,\\-\Delta{v}+2v-u=g\left(x\right),&x\in\Omega,\end{cases}
$$

及边界条件 $u\left(x\right)=v\left(x\right)=0$, $x\in\partial\Omega$. 证明:

$$
\max\left\{\max_{\overline{\Omega}}\left|u\right|,\max_{\overline{\Omega}}\left|v\right|\right\}\le\max\left\{\max_{\overline{\Omega}}\left|f\right|,\max_{\overline{\Omega}}\left|g\right|\right\}.
$$

### 解答 2.18

第一步: 记 $M=\max\left\{\max_{\overline{\Omega}}\left|f\right|,\max_{\overline{\Omega}}\left|g\right|\right\}$. 由对称性 (把 $\left(u,v,f,g\right)$ 换成 $\left(-u,-v,-f,-g\right)$ 方程与边界条件形式不变), 只需证 $\max_{\overline{\Omega}}u\le{M}$.

第二步: 记 $m=\max_{\overline{\Omega}}u=u\left(x_0\right)$, $x_0\in\overline{\Omega}$. 若 $x_0\in\partial\Omega$, 则 $m=u\left(x_0\right)=0\le{M}$ (因 $M\ge0$). 若 $m\le0$, 同样有 $m\le{M}$. 以下设 $x_0\in\Omega$ 且 $m>0$.

第三步: 由 $x_0$ 是 $u$ 在 $\Omega$ 内部的极大值点, $-u$ 的 Hessian 在 $x_0$ 处半正定, 故 $-\Delta{u}\left(x_0\right)\ge0$. 代入第一个方程,

$$
-\Delta{u}\left(x_0\right)=f\left(x_0\right)-2u\left(x_0\right)+v\left(x_0\right)=f\left(x_0\right)-2m+v\left(x_0\right)\ge0,
$$

即 $\varepsilon:=v\left(x_0\right)-2m+f\left(x_0\right)\ge0$, 从而 $v\left(x_0\right)\ge2m-f\left(x_0\right)$.

第四步: 由于 $\left|f\left(x_0\right)\right|\le{M}$ 且 $m>0$, 由第三步

$$
v\left(x_0\right)\ge2m-M.\tag{A}
$$

若 $v\left(x_0\right)\le{M}$, 则 (A) 给出 $2m\le{v}\left(x_0\right)+M\le2M$, 即 $m\le{M}$, 结论已得. 以下设 $v\left(x_0\right)>{}M$.

第五步: 由 $v\left(x_0\right)>{}M\ge\max_{\partial\Omega}\left|v\right|=0$, 点 $x_0$ 也是 $v$ 在 $\Omega$ 内取到正的最大值的点, 故 $-\Delta{v}\left(x_0\right)\ge0$, 于是由第二个方程

$$
-\Delta{v}\left(x_0\right)=g\left(x_0\right)-2v\left(x_0\right)+u\left(x_0\right)\ge0,\tag{B}
$$

即 $2v\left(x_0\right)\le{g}\left(x_0\right)+u\left(x_0\right)\le{M}+m$, 这里用了 $\left|g\right|\le{M}$ 与 $u\left(x_0\right)=m$.

第六步: 把 (A) 代入第五步的不等式,

$$
2\left(2m-M\right)\le2v\left(x_0\right)\le{M}+m,
$$

即 $4m-2M\le{M}+m$, $3m\le3M$, 故 $m\le{M}$.

第七步: 由第二至六步, $\max_{\overline{\Omega}}u\le{M}$. 对 $-u$ 与 $-v$ 重复上述论证 (此时 $f,g$ 换成 $-f,-g$, 仍有 $\max\left|{-f}\right|\le{M}$, $\max\left|{-g}\right|\le{M}$), 得 $\max_{\overline{\Omega}}\left(-u\right)\le{M}$, 即 $\min_{\overline{\Omega}}u\ge-{M}$. 于是 $\max_{\overline{\Omega}}\left|u\right|\le{M}$.

第八步: 对称性. 把方程组中 $u$ 与 $v$ 互换, $f$ 与 $g$ 互换, 方程组的形状不变: $-\Delta{v}+2v-u=g$ 与 $-\Delta{u}+2u-v=f$ 恰是互换后的两个方程. 故第七步的论证对 $v$ 同样成立, $\max_{\overline{\Omega}}\left|v\right|\le{M}$. 合并两式即得所求不等式.

## 习题 2.19 (边界单点例外时调和函数恒为零)

设 $\Omega\subset\mathbb{R}^{n}$ ($n\ge3$) 是有界区域, $x_0\in\partial\Omega$. 证明: 问题

$$
\begin{cases}\Delta{u}=0,&x\in\Omega,\\u=0,&x\in\partial\Omega\setminus\left\{x_0\right\}\end{cases}
$$

在 $C^{2}\left(\Omega\right)\cap{C}^{0}\left(\overline{\Omega}\setminus\left\{x_0\right\}\right)$ 中的有界解恒为零.

### 解答 2.19

第一步: 取 $x_0$ 为原点的记号只影响写法, 直接以 $x_0$ 为中心构造闸函数. 由题设有界, 存在 $M>0$ 使 $\left|u\right|\le{M}$ 于 $\Omega$.

第二步: 取辅助函数. 由**定义 2.4.1 (基本解)**, $n\ge3$ 时 $\Gamma\left(x-x_0\right)=\frac{1}{\left(n-2\right)\omega_n}\left|x-x_0\right|^{2-n}$ 在 $\mathbb{R}^{n}\setminus\left\{x_0\right\}$ 内调和, 取正值, 且当 $x\to{x}_0$ 时 $\Gamma\to+\infty$.

第三步: 对任意 $\varepsilon>0$, 取 $\delta>0$ 使

$$
\varepsilon\delta^{2-n}>{}M.\tag{A}
$$

记区域 $\Omega_\delta=\Omega\cap\left\{x\,\middle|\,|x-x_0|>\delta\right\}$, 它在 $\overline{\Omega}$ 内的边界由 $\partial\Omega\setminus\left\{x_0\right\}$ 的一部分与球面 $\left\{\left|x-x_0\right|=\delta\right\}$ 的一部分组成, 是有界区域.

第四步: 构造比较函数 $z\left(x\right)=u\left(x\right)-\varepsilon\left|x-x_0\right|^{2-n}$. 由第二步, $\Delta{z}=0$ 于 $\Omega_\delta$ 内. 在 $\partial\Omega\setminus\left\{x_0\right\}$ 上 $u=0$, 故

$$
z=-\varepsilon\left|x-x_0\right|^{2-n}\le0.
$$

在球面部分 $\left\{\left|x-x_0\right|=\delta\right\}$ 上, 由 (A),

$$
z=u\left(x\right)-\varepsilon\delta^{2-n}\le{M}-\varepsilon\delta^{2-n}<0.
$$

第五步: 于是在 $\partial\Omega_\delta$ 上 $z\le0$, 而 $\Delta{z}=0$, 由**定理 2.3.1 (弱极值原理)** (对 $z$ 与 $-z$ 同时使用), $z\le0$ 于 $\overline{\Omega}_\delta$, 即

$$
u\left(x\right)\le\varepsilon\left|x-x_0\right|^{2-n},\qquad{x}\in\Omega_\delta.\tag{B}
$$

第六步: 让 $\delta\to0$. 对任意固定 $x\in\Omega$, 当 $\delta$ 充分小时 $x\in\Omega_\delta$, 由 (B)

$$
u\left(x\right)\le\varepsilon\left|x-x_0\right|^{2-n}.
$$

该式对一切 $\varepsilon>0$ 成立, 而右端当 $\varepsilon\to0$ 时趋于 $0$, 故 $u\left(x\right)\le0$.

第七步: 对 $-u$ 重复第三至六步 (此时 $M$ 不变), 得 $-u\left(x\right)\le0$, 即 $u\left(x\right)\ge0$. 合并得 $u\left(x\right)=0$ 于 $\Omega$.

## 习题 2.20 (两个平面区域上的 Green 函数)

求下列区域 $\Omega$ 上 Laplace 方程 Dirichlet 问题的 Green 函数:

(1) $\frac{1}{4}$ 平面 $\Omega=\left\{x=\left(x_1,x_2\right)\in\mathbb{R}^{2}\,\middle|\,x_1>0,x_2>0\right\}$;

(2) 上半单位圆 $\Omega=\left\{x=\left(x_1,x_2\right)\in\mathbb{R}^{2}\,\middle|\,x_1^{2}+x_2^{2}<1,x_2>0\right\}$.

### 解答 2.20

(1) 第一步: 列出关于两条坐标轴的四个对称点. 记

$$
x^{\left(1\right)}=\left(-x_1,x_2\right),\qquad{x}^{\left(2\right)}=\left(x_1,-x_2\right),\qquad{x}^{\left(3\right)}=\left(-x_1,-x_2\right).
$$

则 $x^{\left(1\right)}$ 关于 $x_1=0$ 对称, $x^{\left(2\right)}$ 关于 $x_2=0$ 对称, $x^{\left(3\right)}$ 是两个对称的复合. 这四个点中只有 $x$ 落在 $\Omega$ 内, 其余三点均在 $\Omega$ 外.

第二步: 用交替符号叠加基本解. 由**定义 2.4.1 (基本解)**, 取 $n=2$, 令

$$
G\left(x,y\right)=\Gamma\left(x-y\right)-\Gamma\left(x^{\left(1\right)}-y\right)-\Gamma\left(x^{\left(2\right)}-y\right)+\Gamma\left(x^{\left(3\right)}-y\right).\tag{A}
$$

第三步: 验证调和性. 由**定义 2.5.3 (Green 函数)** 的要求, 需 $\Delta_yG\left(x,\cdot\right)=0$ 于 $\Omega$ (除 $y=x$). 由 (A) 的四个点都在 $\Omega$ 外 (除 $x$ 本身), $\Gamma\left(x^{\left(k\right)}-\cdot\right)$ 在 $\Omega$ 上调和, 而 $\Gamma\left(x-\cdot\right)$ 在 $\Omega\setminus\left\{x\right\}$ 上调和, 故成立.

第四步: 验证边界条件 $G=0$ 于 $\partial\Omega$. 在 $x_1=0$ 上 ($y_1=0$): 由 $x^{\left(1\right)}=\left(-x_1,x_2\right)$ 与 $x$ 只差第一个坐标的符号, $\left|x^{\left(1\right)}-y\right|=\left|x-y\right|$, 故第一, 二项相消; 同理 $\left|x^{\left(3\right)}-y\right|=\left|x^{\left(2\right)}-y\right|$, 第三, 四项相消.

在 $x_2=0$ 上 ($y_2=0$): 由 $x^{\left(2\right)}$ 与 $x$ 只差第二个坐标的符号, $\left|x^{\left(2\right)}-y\right|=\left|x-y\right|$, 第一, 三项相消; 同理 $\left|x^{\left(3\right)}-y\right|=\left|x^{\left(1\right)}-y\right|$, 第二, 四项相消.

第五步: 写出显式. 由**定义 2.5.3 (Green 函数)** 中 Green 函数的唯一性, (A) 就是所求的 Green 函数; 代入 $\Gamma\left(z\right)=\frac{1}{2\pi}\ln\frac{1}{\left|z\right|}$,

$$
G\left(x,y\right)=\frac{1}{2\pi}\ln\frac{\left|x^{\left(1\right)}-y\right|\left|x^{\left(2\right)}-y\right|}{\left|x-y\right|\left|x^{\left(3\right)}-y\right|}.
$$

(2) 第一步: 由于区域是单位圆与上半平面的交, 需要用关于 $x_2=0$ 的反射与关于单位圆的反演两种变换. 记

$$
\bar{x}=\left(x_1,-x_2\right),\qquad{x}^{*}=\frac{x}{\left|x\right|^{2}},\qquad\bar{x}^{*}=\frac{\bar{x}}{\left|\bar{x}\right|^{2}}=\frac{\bar{x}}{\left|x\right|^{2}}.
$$

第二步: 构造

$$
G\left(x,y\right)=\Gamma\left(x-y\right)-\Gamma\left(\bar{x}-y\right)-\Gamma\left(x^{*}-y\right)+\Gamma\left(\bar{x}^{*}-y\right).\tag{B}
$$

符号的安排是"先反射, 再反演": 第一, 二项关于 $x_2=0$ 反号, 第三, 四项作为反演像也关于 $x_2=0$ 反号.

第三步: 调和性. $x\in\Omega$ 时 $\left|x\right|<1$, 故 $\left|x^{*}\right|=1/\left|x\right|>1$, 同理 $\left|\bar{x}^{*}\right|>1$; 而 $\bar{x}$ 的第二个坐标为负. 于是 $\bar{x},x^{*},\bar{x}^{*}$ 都不属于 $\Omega$, $\Gamma\left(\bar{x}-\cdot\right)$, $\Gamma\left(x^{*}-\cdot\right)$, $\Gamma\left(\bar{x}^{*}-\cdot\right)$ 在 $\Omega$ 上调和, (B) 在 $\Omega\setminus\left\{x\right\}$ 内调和.

第四步: 在 $y_2=0$ 上验证 $G=0$. 此时 $\bar{x}$ 与 $x$ 到 $y$ 的距离相等, 故第一, 二项相消; 又 $\bar{x}^{*}$ 是 $x^{*}$ 关于 $x_2=0$ 的反射, 故 $\left|\bar{x}^{*}-y\right|=\left|x^{*}-y\right|$, 第三, 四项相消.

第五步: 在 $\left|y\right|=1$ 上验证 $G=0$. 先算反演像的距离. 与习题 2.12 第二步同法,

$$
\left|x^{*}-y\right|^{2}=\frac{\left|x-y\right|^{2}}{\left|x\right|^{2}},\qquad\left|\bar{x}^{*}-y\right|^{2}=\frac{\left|\bar{x}-y\right|^{2}}{\left|x\right|^{2}},\qquad\left|y\right|=1.
$$

于是

$$
\Gamma\left(x^{*}-y\right)=\frac{1}{2\pi}\ln\frac{\left|x\right|}{\left|x-y\right|}=\Gamma\left(x-y\right)+\frac{1}{2\pi}\ln\left|x\right|,\tag{C}
$$

$$
\Gamma\left(\bar{x}^{*}-y\right)=\Gamma\left(\bar{x}-y\right)+\frac{1}{2\pi}\ln\left|x\right|,\tag{D}
$$

两式的附加常数相同. 把 (C)(D) 代入 (B),

$$
G\left(x,y\right)=\Gamma\left(x-y\right)-\Gamma\left(\bar{x}-y\right)-\Gamma\left(x-y\right)-\frac{1}{2\pi}\ln\left|x\right|+\Gamma\left(\bar{x}-y\right)+\frac{1}{2\pi}\ln\left|x\right|=0.
$$

第六步: 由**定义 2.5.3 (Green 函数)** 中 Green 函数的唯一性, (B) 即所求的 Green 函数.

## 习题 2.21 (二维调和函数的奇点可去性)

证明: 若 $a$ 是调和函数 $u\left(x\right)$ 的孤立奇点, 且在 $a$ 点的邻域中满足 $u\left(x\right)=o\left(\ln\frac{1}{\left|x-a\right|}\right)$ ($x\to{a}$), 则可以定义 $u$ 在 $a$ 处的值, 使得 $u$ 在 $a$ 点调和.

### 解答 2.21

第一步: 平移, 设 $a=0$. 题设即: $u$ 在 $0<\left|x\right|<{}R$ 内调和, 且对任意 $\varepsilon>0$ 存在 $\delta\in\left(0,R\right]$, 使得

$$
\left|u\left(x\right)\right|\le\varepsilon\ln\frac{1}{\left|x\right|},\qquad0<\left|x\right|<\delta.\tag{A}
$$

第二步: 先证 $u$ 在 $0$ 的邻域内有界. 取定 $0<\rho_0<\delta$, 并对 $0<\rho<\frac{\rho_0}{2}$ 记

$$
A_\rho=\max_{\left|x\right|=\rho}u,\qquad{B}_{\rho_0}=\max_{\left|x\right|=\rho_0}u.\tag{B}
$$

第三步: 在两圆所夹的环域 $\left\{\rho<\left|x\right|<\rho_0\right\}$ 上构造比较函数

$$
h\left(x\right)=A_\rho\frac{\ln\left(\rho_0/\left|x\right|\right)}{\ln\left(\rho_0/\rho\right)}+B_{\rho_0}\frac{\ln\left(\left|x\right|/\rho\right)}{\ln\left(\rho_0/\rho\right)}.\tag{C}
$$

由 $\ln\left|x\right|$ 在 $\mathbb{R}^{2}\setminus\left\{0\right\}$ 内调和, $h$ 在环域内调和; 且由 $B_\rho$, $B_{\rho_0}$ 的定义, 在 $\left|x\right|=\rho$ 上 $h=A_\rho\ge{u}$, 在 $\left|x\right|=\rho_0$ 上 $h=B_{\rho_0}\ge{u}$. 故由**定理 2.3.1 (弱极值原理)**,

$$
u\left(x\right)\le{h}\left(x\right),\qquad\rho<\left|x\right|<\rho_0.\tag{D}
$$

第四步: 在 (D) 中令 $\rho\to0$. 由 (A), $A_\rho\le\varepsilon\ln\frac{1}{\rho}$, 故 (C) 中第一项的绝对值不超过

$$
\varepsilon\ln\frac{1}{\rho}\cdot\frac{\ln\left(\rho_0/\left|x\right|\right)}{\ln\left(\rho_0/\rho\right)}\to0,
$$

因为分子 $\ln\left(\rho_0/\left|x\right|\right)$ 对固定的 $x$ 是常数, 而分母 $\ln\left(\rho_0/\rho\right)\to+\infty$. 第二项中 $\frac{\ln\left(\left|x\right|/\rho\right)}{\ln\left(\rho_0/\rho\right)}=\frac{\ln\left(1/\rho\right)-\ln\left|x\right|}{\ln\left(1/\rho\right)-\ln\rho_0}\to1$. 故 (D) 的极限给出

$$
u\left(x\right)\le{B}_{\rho_0},\qquad0<\left|x\right|<\rho_0.\tag{E}
$$

第五步: 对 $-u$ 用同样的论证 ($-u$ 也满足 (A)), 若记 $b_{\rho_0}=\min_{\left|x\right|=\rho_0}u$, 则

$$
u\left(x\right)\ge{b}_{\rho_0},\qquad0<\left|x\right|<\rho_0.\tag{F}
$$

由 (E)(F), $u$ 在 $B_{\rho_0}\setminus\left\{0\right\}$ 内有界, 记 $\left|u\right|\le{M}$.

第六步: 由**定理 2.5.7 (Poisson 积分公式)**, 取 $\varphi=u\big|_{\partial{B}_{\rho_0}}$ (它在圆周上连续), 得函数 $U\in{C}^{\infty}\left(B_{\rho_0}\right)\cap{C}^{0}\left(\overline{B}_{\rho_0}\right)$, $\Delta{U}=0$ 于 $B_{\rho_0}$, 且 $U=u$ 于 $\left|x\right|=\rho_0$.

第七步: 证 $u\equiv{U}$. 记 $w=u-U$, 则 $w$ 在 $B_{\rho_0}\setminus\left\{0\right\}$ 内调和, $w=0$ 于 $\left|x\right|=\rho_0$, 且由第五步与 $U$ 的极值原理估计 $\left|w\right|\le2M$. 对 $\varepsilon\in\left(0,\rho_0\right)$ 在环域 $\left\{\varepsilon<\left|x\right|<\rho_0\right\}$ 上取

$$
H_\varepsilon\left(x\right)=2M\frac{\ln\left(\left|x\right|/\rho_0\right)}{\ln\left(\varepsilon/\rho_0\right)}.
$$

由 $\ln\left|x\right|$ 调和知 $H_\varepsilon$ 调和, 且 $H_\varepsilon=0$ 于 $\left|x\right|=\rho_0$, $H_\varepsilon=2M$ 于 $\left|x\right|=\varepsilon$. 故在环域的两条边界圆周上 $\pm{w}\le{H}_\varepsilon$, 由**定理 2.3.1 (弱极值原理)**,

$$
\left|w\left(x\right)\right|\le{H}_\varepsilon\left(x\right)=2M\frac{\ln\left(\left|x\right|/\rho_0\right)}{\ln\left(\varepsilon/\rho_0\right)},\qquad\varepsilon<\left|x\right|<\rho_0.
$$

令 $\varepsilon\to0$, 右端趋于 $0$ (分子固定, 分母趋于 $-\infty$), 故 $w\left(x\right)=0$ 于 $B_{\rho_0}\setminus\left\{0\right\}$, 即 $u=U$ 于该球内除原点.

第八步: 补充定义 $u\left(0\right)=U\left(0\right)$. 则 $u$ 在 $B_{\rho_0}$ 内处处等于调和函数 $U$, 从而 $u$ 在 $a$ 点调和, 且其在该点的值唯一确定为 $U\left(0\right)$.

## 习题 2.22 (二维 Dirichlet 外问题的良定义性)

设 $\Omega$ 是 $\mathbb{R}^{2}$ 的一个有界区域, 且满足内圆条件, $\varphi\in{C}^{0}\left(\partial\Omega\right)$. 试证 Dirichlet 外问题

$$
\begin{cases}\Delta{u}=0,&x\in\mathbb{R}^{2}\setminus\overline{\Omega},\\u=\varphi\left(x\right),&x\in\partial\Omega,\\u\text{在}\mathbb{R}^{2}\setminus\Omega\text{上有界}\end{cases}
$$

在 $C^{2}\left(\mathbb{R}^{2}\setminus\overline{\Omega}\right)\cap{C}^{0}\left(\mathbb{R}^{2}\setminus\Omega\right)$ 中存在唯一解.

### 解答 2.22

一, 唯一性.

第一步: 设 $u_1,u_2$ 是两个解, 记 $w=u_1-u_2$. 则 $w$ 在 $\mathbb{R}^{2}\setminus\overline{\Omega}$ 内调和, $w=0$ 于 $\partial\Omega$, 且 $\left|w\right|\le{M}$ ($M>0$ 由两解的有界性给出).

第二步: 取 $r_0$ 使 $\overline{\Omega}\subset{B}_{r_0}\left(0\right)$, 并对 $R>{}r_0$ 记 $\Omega_R=\left\{x\in\mathbb{R}^{2}\setminus\overline{\Omega}\,\middle|\,|x|<{}R\right\}$. 在 $\Omega_R$ 上取比较函数

$$
h\left(x\right)=M\frac{\ln\left(\left|x\right|/r_0\right)}{\ln\left(R/r_0\right)}.
$$

第三步: 由 $\ln\left|x\right|$ 调和, $\Delta{h}=0$ 于 $\Omega_R$; 且 $h=0$ 于 $\left|x\right|=r_0$ (从而 $h=0$ 于 $\partial\Omega\subset\left\{\left|x\right|\ge{r}_0\right\}$, 那里 $h\ge0$), $h=M$ 于 $\left|x\right|=R$. 于是在 $\partial\Omega$ 上 $w=0\le{h}$, 在 $\left|x\right|=R$ 上 $w\le{M}=h$, 故由**定理 2.3.1 (弱极值原理)** $w\le{h}$ 于 $\Omega_R$.

第四步: 固定 $x\in\mathbb{R}^{2}\setminus\overline{\Omega}$, 令 $R\to\infty$. 由第三步,

$$
w\left(x\right)\le{M}\frac{\ln\left(\left|x\right|/r_0\right)}{\ln\left(R/r_0\right)}\to0,
$$

故 $w\left(x\right)\le0$. 同法对 $-w$ 得 $w\left(x\right)\ge0$. 于是 $w\equiv0$, 唯一性得证.

二, 存在性.

第五步: 用关于点的反演把外问题化为有界区域上的内问题. 因 $\Omega$ 有界, 取一点 $x_1\notin\overline{\Omega}$, 并把坐标原点平移到 $x_1$ (平移不改变调和性与有界性). 于是 $0\notin\overline{\Omega}$, 且 $\overline{\Omega}$ 是紧集, 故存在 $0<{}r<{}d$ 使

$$
\overline{\Omega}\subset\left\{r\le\left|x\right|\le{d}\right\},\qquad\text{特别地}\;0\notin\overline{\Omega}.
$$

定义反演变换

$$
y=\Phi\left(x\right):=\frac{x}{\left|x\right|^{2}},\qquad{x}\in\mathbb{R}^{2}\setminus\left\{0\right\},\tag{A}
$$

并记 $\Omega^{*}:=\Phi\left(\mathbb{R}^{2}\setminus\overline{\Omega}\right)$. 由 $\Phi$ 是自身的逆 ($\Phi\left(\Phi\left(x\right)\right)=x$) 与 $\Phi$ 把 $\mathbb{R}^{2}\setminus\left\{0\right\}$ 同胚地映为自身, $\Omega^{*}$ 是有界区域, $\partial\Omega^{*}=\Phi\left(\partial\Omega\right)$. 又 $\Phi$ 把 $0$ 映射到"无穷远", 故当 $x$ 跑遍 $\mathbb{R}^{2}\setminus\overline{\Omega}$ 时 $\Phi\left(x\right)$ 跑遍一个有界区域; 即 $\overline{\Omega}^{*}$ 紧.

第六步: 反演把调和函数映为调和函数. 若 $U\in{C}^{2}\left(\Omega^{*}\right)$ 调和, 令 $v\left(x\right)=U\left(\Phi\left(x\right)\right)$. 由链式法则: 记 $y=x/\left|x\right|^{2}$, $r=\left|x\right|$,

$$
\frac{\partial{y_i}}{\partial{x_j}}=\frac{\delta_{ij}}{r^{2}}-\frac{2x_ix_j}{r^{4}},
$$

逐项求导得

$$
\Delta_xv\left(x\right)=\frac{1}{r^{4}}\Delta_yU\left(y\right),\qquad{y}=\Phi\left(x\right),\tag{B}
$$

(这是二维 Kelvin 变换的公式; 一般 $n$ 维情形为 $v\left(x\right)=\left|x\right|^{2-n}U\left(x/\left|x\right|^{2}\right)$). 故 $U$ 调和蕴含 $v$ 调和. 反之亦然 ($\Phi$ 是自身的逆).

第七步: 化归为有界区域上的 Dirichlet 问题. 令 $\psi\left(y\right)=\varphi\left(\Phi\left(y\right)\right)$, $y\in\partial\Omega^{*}$. 由 $\Phi$ 连续与 $\varphi$ 连续, $\psi\in{C}^{0}\left(\partial\Omega^{*}\right)$. 由第六步, 只需求

$$
\Delta{U}=0\;\text{于}\;\Omega^{*},\qquad{U}=\psi\;\text{于}\;\partial\Omega^{*}
$$

的解 $U$, 则 $u\left(x\right)=U\left(\Phi\left(x\right)\right)$ 就是外问题的解.

第八步: $\Omega^{*}$ 满足外球条件. 设 $x_0$ 在 $\partial\Omega^{*}$ 上. 由题设 $\Omega$ 满足内圆条件, 存在球 $B_R\left(y\right)\subset\Omega$ 与 $\overline{\Omega}$ 只交于一点 $z_0=\Phi\left(x_0\right)$, 且两球 (球与 $\Omega$) 在 $z_0$ 处的外法向重合. 反演把该球 (它不经过原点, 因 $0\notin\overline{\Omega}$) 映为一个圆的外部区域, 记为 $D_R\subset\Omega^{*}$, 其边界是过 $x_0$ 的圆周且该圆盘是凸的. 在 $x_0$ 处沿该圆盘的外法向作半径 $\rho$ 的小球 $B_\rho\left(w\right)$, 其中 $w=x_0+\rho\nu$; 由圆盘的凸性, 该球只与圆盘相切于 $x_0$, 从而

$$
\overline{B}_\rho\left(w\right)\cap\overline{\Omega}^{*}=\left\{x_0\right\},
$$

即 $\Omega^{*}$ 在 $x_0$ 处满足**定义 2.6.12 (外球条件)**. 由 $x_0$ 的任意性, $\Omega^{*}$ 满足外球条件.

第九步: 由**定理 2.6.14 (Dirichlet 问题解的存在性)**, $\Omega^{*}$ 上以 $\psi$ 为边值的 Laplace 方程 Dirichlet 问题存在解 $U\in{C}^{2}\left(\Omega^{*}\right)\cap{C}^{0}\left(\overline{\Omega}^{*}\right)$. 令

$$
u\left(x\right)=U\left(\Phi\left(x\right)\right),\qquad{x}\in\mathbb{R}^{2}\setminus\overline{\Omega}.
$$

则由第六步, $u$ 在 $\mathbb{R}^{2}\setminus\overline{\Omega}$ 内调和; 由 $U$ 连续到边界与 $\Phi$ 连续,

$$
u\left(x\right)\to{U}\left(\Phi\left(x_0\right)\right)=\psi\left(\Phi\left(x_0\right)\right)=\varphi\left(x_0\right),\qquad{x}\to{x}_0\in\partial\Omega,
$$

故 $u=\varphi$ 于 $\partial\Omega$; 又当 $\left|x\right|\to\infty$ 时 $\Phi\left(x\right)\to0$, 而 $U$ 在 $\overline{\Omega}^{*}$ 上有界, 故 $u$ 在 $\mathbb{R}^{2}\setminus\Omega$ 上有界. 于是 $u$ 是所求的解, 存在性得证.
