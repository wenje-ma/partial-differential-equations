# week1

## 习题 1.1 (Laplace 方程在 $\mathbb{R}^{n}\setminus\left\{0\right\}$ 的径向对称解)

求 Laplace 方程 $\Delta{u}=\sum_{i=1}^{n}\frac{\partial^{2}u}{\partial{x_i}^{2}}=0$, $x\in\mathbb{R}^{n}\setminus\left\{0\right\}$ 的径向对称解.

### 解答 1.1

第一步: 设 $u$ 径向对称, 即存在一元函数 $U$ 使 $u\left(x\right)=U\left(r\right)$, $r=\left|x\right|$. 径向对称解只可能在 $u$ 的值只依赖 $r$ 时取得, 故不妨设此形式, 再将其代入方程.

第二步: 记 $\partial_{x_i}r=\frac{x_i}{r}$, 由链式法则

$$
\partial_{x_i}u=U'\left(r\right)\frac{x_i}{r}.
$$

再对 $x_i$ 求导, 得

$$
\frac{\partial^{2}u}{\partial{x_i}^{2}}=U''\left(r\right)\left(\frac{x_i}{r}\right)^{2}+U'\left(r\right)\left(\frac{1}{r}-\frac{x_i^{2}}{r^{3}}\right)=\left(\frac{U''\left(r\right)}{r^{2}}-\frac{U'\left(r\right)}{r^{3}}\right)x_i^{2}+\frac{U'\left(r\right)}{r}.
$$

第三步: 对 $i$ 求和, 用 $\sum_{i=1}^{n}x_i^{2}=r^{2}$,

$$
\Delta{u}=\left(\frac{U''\left(r\right)}{r^{2}}-\frac{U'\left(r\right)}{r^{3}}\right)r^{2}+\frac{nU'\left(r\right)}{r}=U''\left(r\right)+\frac{n-1}{r}U'\left(r\right).
$$

于是方程 $\Delta{u}=0$ 等价于常微分方程

$$
rU''\left(r\right)+\left(n-1\right)U'\left(r\right)=0.\tag{A}
$$

第四步: 以 $r^{n-1}$ 乘 (A) 的两端, 左端恰为一个全导数

$$
r^{n-1}U''\left(r\right)+\left(n-1\right)r^{n-2}U'\left(r\right)=\left(r^{n-1}U'\left(r\right)\right)'=0.
$$

故 $r^{n-1}U'\left(r\right)=C$, 即 $U'\left(r\right)=Cr^{1-n}$.

第五步: 分两种情形积分. 当 $n=2$ 时, $U'\left(r\right)=\frac{C}{r}$, 故 $U=C_1\ln{r}+C_2$; 当 $n\ge3$ 时, $U'\left(r\right)=Cr^{1-n}$, 故 $U=\frac{C}{2-n}r^{2-n}+C_2$. 把 $\frac{C}{2-n}$ 仍记作 $C_1$, 并换回 $r=\left|x\right|$, 得所求的全部径向对称解

$$
u\left(x\right)=\begin{cases}C_1\ln\left|x\right|+C_2,&n=2,\\C_1\left|x\right|^{2-n}+C_2,&n\ge3,\end{cases}
$$

其中 $C_1,C_2$ 是任意常数.

## 习题 1.2 (方程的阶数与线性性)

指出下列方程的阶数和线性性.

(1) 伯格斯 (Burgers) 方程

$$
\frac{\partial{u}}{\partial{t}}-a^{2}\frac{\partial^{2}u}{\partial{x}^{2}}+u\frac{\partial{u}}{\partial{x}}=0,
$$

其中 $a$ 是一个常数;

(2) 电报方程

$$
\frac{\partial^{2}u}{\partial{x}^{2}}=CL\frac{\partial^{2}u}{\partial{t}^{2}}+CR\frac{\partial{u}}{\partial{t}},
$$

其中 $C,L,R$ 均为常数;

(3) 卢丁-奥谢尔-法特米 (Rudin-Osher-Fatemi) 图像恢复方程

$$
\operatorname{div}\left(\frac{Du}{\left|Du\right|}\right)=2\lambda\left(u-f\right),
$$

其中 $\lambda,f$ 分别为已知常数与函数;

(4) 平均曲率流方程

$$
\frac{\partial{u}}{\partial{t}}=\frac{\left(1+\left(u_y\right)^{2}\right)u_{xx}-2u_xu_yu_{xy}+\left(1+\left(u_x\right)^{2}\right)u_{yy}}{1+\left(u_x\right)^{2}+\left(u_y\right)^{2}};
$$

(5) 哈密顿-雅可比 (Hamilton-Jacobi) 方程

$$
\frac{\partial{V}}{\partial{t}}+\inf_{\xi}\left\{\sum_{i=1}^{n}b_{\xi}^{i}\left(x,t\right)\frac{\partial{V}}{\partial{x_i}}+c_{\xi}\left(x,t\right)\right\}=0,
$$

其中 $b_{\xi}^{i},c_{\xi}$ 为已知函数;

(6) 守恒律方程

$$
\frac{\partial{u}}{\partial{t}}+\operatorname{div}F\left(u\right)=0,
$$

其中 $F$ 是一个已知的向量值函数;

(7) 波希西内斯克 (Boussinesq) 方程

$$
u_{tt}-u_{xx}-\frac{\partial^{2}\left(u^{2}\right)}{\partial{y}^{2}}+\frac{\partial^{4}u}{\partial{x}^{4}}=0;
$$

(8) 克莱因-戈尔登 (Klein-Gordon) 方程

$$
\frac{\partial^{2}\psi}{\partial{t}^{2}}-\Delta\psi+\psi=0.
$$

### 解答 1.2

先约定两个判据. 阶数即方程中出现的最高阶偏导数的阶. 若方程关于未知函数及其各阶偏导数都是一次的, 称它线性; 若只要求关于最高阶偏导数是一次的, 而系数可依赖低阶导数与未知函数, 称它拟线性; 最高阶导数虽一次但系数含未知函数本身的高次因子, 或最高阶项被非线性函数包裹, 则连拟线性也不是 (半线性指最高阶项线性且系数只依赖自变量, 非线性只出现在低阶项).

(1) 最高阶导数是 $u_{xx}$, 阶数为 $2$. $uu_x$ 一项关于 $u$ 及其导数二次, 故非线性. 最高阶导数 $u_{xx}$ 的系数是常数 $-a^{2}$, 故为拟线性.

(2) 最高阶导数是 $u_{xx}$ 与 $u_{tt}$, 阶数为 $2$. 方程关于 $u,u_t,u_{tt},u_{xx}$ 均一次, 系数 $CL,CR$ 不依赖 $u$, 故线性 (且为常系数).

(3) $Du=\left(u_x,u_y\right)$ 是一阶导数组成的向量, 方程中出现的最高阶导数含在 $\operatorname{div}\left(Du/\left|Du\right|\right)$ 内, 即二阶导数, 阶数为 $2$. 由

$$
\operatorname{div}\left(\frac{Du}{\left|Du\right|}\right)=\frac{\Delta{u}}{\left|Du\right|}-\frac{Du\cdot\nabla\left|Du\right|}{\left|Du\right|^{3}},
$$

右端关于二阶导数是线性的, 系数依赖一阶导数 $Du$, 故拟线性.

(4) 最高阶导数是 $u_{xx},u_{xy},u_{yy}$, 阶数为 $2$. 三者在分子中一次出现, 系数 $1+u_y^{2},-2u_xu_y,1+u_x^{2}$ 与分母 $1+u_x^{2}+u_y^{2}$ 只依赖一阶导数, 故拟线性.

(5) 最高阶导数是一阶导数 $V_{x_i}$ 与 $V_t$, 阶数为 $1$. $\inf_{\xi}$ 对大括号内的一阶导数项取下确界, 这不是一阶导数的线性函数 (例如 $b_{\xi}$ 取两个方向时, $\inf$ 等于 $V$ 的一阶导数绝对值型的量), 故非线性.

(6) 最高阶导数是 $u_t$ 与 $\operatorname{div}F\left(u\right)$ 中的一阶导数, 阶数为 $1$. 由 $F=\left(F_1,\dots,F_n\right)$ 与链式法则

$$
\operatorname{div}F\left(u\right)=\sum_{i=1}^{n}F_i'\left(u\right)\frac{\partial{u}}{\partial{x_i}},
$$

方程关于一阶导数线性, 系数 $F_i'\left(u\right)$ 依赖 $u$, 故拟线性; 当 $F$ 是线性向量函数时它退化为线性方程.

(7) 最高阶导数是 $\frac{\partial^{4}u}{\partial{x}^{4}}$, 阶数为 $4$. 最高阶项 $u_{tt},u_{xx},u_{xxxx}$ 的系数均为常数, 非线性只来自低阶项 $\frac{\partial^{2}\left(u^{2}\right)}{\partial{y}^{2}}$ (二阶), 故为半线性方程, 从而非线性.

(8) 最高阶导数是 $\psi_{tt}$ 与 $\Delta\psi$ 中的二阶导数, 阶数为 $2$. 方程关于 $\psi$ 及其二阶导数为一次, 系数都是常数, 故线性.

## 习题 1.3 (热传导方程的一个不变变换)

若 $u\left(x,t\right)$ 满足热传导方程

$$
\frac{\partial{u}}{\partial{t}}=\frac{\partial^{2}u}{\partial{x}^{2}},
$$

则

$$
v\left(x,t\right)=\frac{1}{\sqrt{t}}\mathrm{e}^{-\frac{x^{2}}{4t}}u\left(\frac{x}{t},-\frac{1}{t}\right)
$$

也满足同一个方程.

### 解答 1.3

第一步: 作自变量替换

$$
y=\frac{x}{t},\qquad{s}=-\frac{1}{t},
$$

并记

$$
a\left(t,x\right)=\frac{1}{\sqrt{t}}\mathrm{e}^{-\frac{x^{2}}{4t}},
$$

于是 $v\left(x,t\right)=a\left(t,x\right)u\left(y,s\right)$, 其中 $u=u\left(y,s\right)$ 满足 $u_s=u_{yy}$. 由 $y,s$ 的定义,

$$
\frac{\partial{y}}{\partial{t}}=-\frac{x}{t^{2}}=-\frac{y}{t},\qquad\frac{\partial{s}}{\partial{t}}=\frac{1}{t^{2}},\qquad\frac{\partial{y}}{\partial{x}}=\frac{1}{t},\qquad\frac{\partial^{2}y}{\partial{x}^{2}}=0.
$$

第二步: 先算 $a$ 的一阶偏导数

$$
a_t=a\left(-\frac{1}{2t}+\frac{x^{2}}{4t^{2}}\right),\qquad{a}_x=a\left(-\frac{x}{2t}\right).
$$

第三步: 对 $x$ 求导两次,

$$
v_x=a_xu+au_y\frac{1}{t}=a\left(-\frac{xu}{2t}+\frac{u_y}{t}\right),
$$

$$
v_{xx}=a\left[-\frac{x}{2t}\left(-\frac{xu}{2t}+\frac{u_y}{t}\right)-\frac{u}{2t}-\frac{xu_y}{2t^{2}}+\frac{u_{yy}}{t^{2}}\right]=a\left[\frac{x^{2}u}{4t^{2}}-\frac{xu_y}{t^{2}}-\frac{u}{2t}+\frac{u_{yy}}{t^{2}}\right].\tag{A}
$$

第四步: 对 $t$ 求导一次, 用 $\partial_t{u}=u_y\left(-\frac{x}{t^{2}}\right)+u_s\frac{1}{t^{2}}$,

$$
v_t=a\left[\left(-\frac{1}{2t}+\frac{x^{2}}{4t^{2}}\right)u-\frac{xu_y}{t^{2}}+\frac{u_s}{t^{2}}\right].\tag{B}
$$

第五步: 将 (A) 与 (B) 相减, 并代入 $u_s=u_{yy}$,

$$
v_t-v_{xx}=a\left[\left(-\frac{1}{2t}+\frac{x^{2}}{4t^{2}}-\frac{x^{2}}{4t^{2}}+\frac{1}{2t}\right)u+\left(-\frac{x}{t^{2}}+\frac{x}{t^{2}}\right)u_y+\frac{u_s-u_{yy}}{t^{2}}\right]=0.
$$

故 $v_t=v_{xx}$, 即 $v$ 满足同一个热传导方程.

## 习题 1.4 (热传导方程的自相似解)

求热传导方程

$$
\frac{\partial{u}}{\partial{t}}=a^{2}\frac{\partial^{2}u}{\partial{x}^{2}}
$$

所有形如

$$
u\left(x,t\right)=\frac{1}{\sqrt{t}}f\left(\frac{x}{2a\sqrt{t}}\right)
$$

的解, 其中 $a$ 是一个正常数.

### 解答 1.4

第一步: 记自相似变量

$$
\xi=\frac{x}{2a\sqrt{t}},
$$

则 $\partial_x\xi=\frac{1}{2a\sqrt{t}}$, $\partial_t\xi=-\frac{\xi}{2t}$, 且

$$
u\left(x,t\right)=t^{-\frac{1}{2}}f\left(\xi\right).
$$

第二步: 算 $u_t$. 由乘积法则与链式法则,

$$
u_t=-\frac{1}{2}t^{-\frac{3}{2}}f+t^{-\frac{1}{2}}f'\left(\xi\right)\left(-\frac{\xi}{2t}\right)=t^{-\frac{3}{2}}\left(-\frac{1}{2}f-\frac{1}{2}\xi{f}'\right).\tag{A}
$$

第三步: 算 $u_{xx}$. 先有一阶导数

$$
u_x=t^{-\frac{1}{2}}f'\left(\xi\right)\frac{1}{2a\sqrt{t}}=\frac{f'\left(\xi\right)}{2at},
$$

再求导一次, 注意 $\partial_x\xi=\frac{1}{2a\sqrt{t}}$,

$$
u_{xx}=\frac{f''\left(\xi\right)}{2at}\cdot\frac{1}{2a\sqrt{t}}=\frac{f''\left(\xi\right)}{4a^{2}t^{\frac{3}{2}}}.\tag{B}
$$

第四步: 把 (A) 与 (B) 代入方程 $u_t=a^{2}u_{xx}$, 得

$$
t^{-\frac{3}{2}}\left(-\frac{1}{2}f-\frac{1}{2}\xi{f}'\right)=\frac{f''\left(\xi\right)}{4t^{\frac{3}{2}}}.
$$

两端乘以 $4t^{\frac{3}{2}}$, 化成关于 $f$ 的常微分方程

$$
f''\left(\xi\right)+2\xi{f}'\left(\xi\right)+2f\left(\xi\right)=0.\tag{C}
$$

第五步: 解 (C). 注意 $f''+2\xi{f}'+2f=\left(f'+2\xi{f}\right)'$, 故 (C) 等价于

$$
f'\left(\xi\right)+2\xi{f}\left(\xi\right)=C_1,
$$

其中 $C_1$ 是常数. 以积分因子 $\mathrm{e}^{\xi^{2}}$ 乘两端,

$$
\left(\mathrm{e}^{\xi^{2}}f\left(\xi\right)\right)'=C_1\mathrm{e}^{\xi^{2}},
$$

积分得

$$
f\left(\xi\right)=\mathrm{e}^{-\xi^{2}}\left(C_1\int_0^{\xi}\mathrm{e}^{s^{2}}\,\mathrm{d}s+C_2\right),
$$

其中 $C_2$ 是另一常数.

第六步: 换回 $x,t$. 所求的全部解为

$$
u\left(x,t\right)=\frac{1}{\sqrt{t}}\mathrm{e}^{-\frac{x^{2}}{4a^{2}t}}\left(C_1\int_0^{\frac{x}{2a\sqrt{t}}}\mathrm{e}^{s^{2}}\,\mathrm{d}s+C_2\right).
$$

当 $C_1=0,C_2=1$ 时右端即热传导方程的基本解.
