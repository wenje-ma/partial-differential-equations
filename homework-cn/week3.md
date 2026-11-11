# week3

> **定理 2.3.1 (弱极值原理)**
> 
> 设 $u\in{C}^{2}\left(\Omega\right)\cap{C}^{0}\left(\overline{\Omega}\right)$ 在 $\Omega$ 内满足 $\Delta{u}\ge0$ (或 $\Delta{u}\le0$), 则 $u$ 在 $\overline{\Omega}$ 上的最大值 (最小值) 在 $\partial\Omega$ 上达到, 即 $\max_{\overline{\Omega}}u=\max_{\partial\Omega}u$ ($\min_{\overline{\Omega}}u=\min_{\partial\Omega}u$).

> **定义 2.3.2 (下调和函数, 上调和函数)**
> 
> 若 $u\in{C}^{2}\left(\Omega\right)$ 满足 $\Delta{u}\left(x\right)\ge0$ ($\le0$), $x\in\Omega$, 则称 $u$ 为下调和 (或上调和) 函数.

> **定理 2.3.3 (最大模估计)**
> 
> 设 $f\in{C}^{0}\left(\overline{\Omega}\right)$, $\varphi\in{C}^{0}\left(\partial\Omega\right)$. 若 $u\in{C}^{2}\left(\Omega\right)\cap{C}^{0}\left(\overline{\Omega}\right)$ 是 Dirichlet 边值问题 (2.1.2) 的解, 则 $\max_{\overline{\Omega}}\left|u\right|\le\max_{\partial\Omega}\left|\varphi\right|+\frac{d^{2}}{2n}\max_{\overline{\Omega}}\left|f\right|$, 其中 $d=\operatorname{diam}\left(\Omega\right)$.

> **定义 2.4.1 (基本解)**
> 
> Laplace 方程的基本解为 $\Gamma\left(x\right)=\frac{1}{2\pi}\ln\frac{1}{\left|x\right|}$ ($n=2$), $\Gamma\left(x\right)=\frac{1}{\left(n-2\right)\omega_n}\left|x\right|^{2-n}$ ($n\ge3$), 其中 $\omega_n$ 为 $\mathbb{R}^{n}$ 中单位球面的面积; 且 $\partial_{x_i}\Gamma\left(x\right)=-\frac{x_i}{\omega_n\left|x\right|^{n}}$.

## 习题 2.3 (极坐标下的 Laplace 算子)

证明: 在极坐标 $x=r\cos\theta$, $y=r\sin\theta$, $r\ge0$, $0\le\theta<2\pi$ 下, 二维 Laplace 算子可以写成

$$
\Delta{u}=U_{rr}+\frac{1}{r^{2}}U_{\theta\theta}+\frac{1}{r}U_r,
$$

其中 $U\left(r,\theta\right)=u\left(r\cos\theta,r\sin\theta\right)$.

### 解答 2.3

第一步: 由链式法则, 记 $U_r=\frac{\partial{U}}{\partial{r}}$, 先算一阶导数

$$
U_r=u_x\frac{\partial{x}}{\partial{r}}+u_y\frac{\partial{y}}{\partial{r}}=u_x\cos\theta+u_y\sin\theta.
$$

第二步: 对 $U_r$ 再关于 $r$ 求导, 用 $\frac{\partial{x}}{\partial{r}}=\cos\theta$, $\frac{\partial{y}}{\partial{r}}=\sin\theta$,

$$
U_{rr}=\cos\theta\left(u_{xx}\cos\theta+u_{xy}\sin\theta\right)+\sin\theta\left(u_{xy}\cos\theta+u_{yy}\sin\theta\right)=u_{xx}\cos^{2}\theta+2u_{xy}\sin\theta\cos\theta+u_{yy}\sin^{2}\theta.
$$

第三步: 算关于 $\theta$ 的导数. 由 $\frac{\partial{x}}{\partial\theta}=-r\sin\theta$, $\frac{\partial{y}}{\partial\theta}=r\cos\theta$,

$$
U_{\theta}=u_x\left(-r\sin\theta\right)+u_y\left(r\cos\theta\right).
$$

第四步: 对 $U_\theta$ 再关于 $\theta$ 求导, 用 $\frac{\partial{u}_x}{\partial\theta}=u_{xx}\left(-r\sin\theta\right)+u_{xy}\left(r\cos\theta\right)$ 与 $\frac{\partial{u}_y}{\partial\theta}=u_{xy}\left(-r\sin\theta\right)+u_{yy}\left(r\cos\theta\right)$,

$$
\begin{aligned}
U_{\theta\theta}&=-r\sin\theta\left(u_{xx}\left(-r\sin\theta\right)+u_{xy}r\cos\theta\right)+u_x\left(-r\cos\theta\right)\\
&\quad+r\cos\theta\left(u_{xy}\left(-r\sin\theta\right)+u_{yy}r\cos\theta\right)+u_y\left(-r\sin\theta\right)\\
&=u_{xx}r^{2}\sin^{2}\theta-2u_{xy}r^{2}\sin\theta\cos\theta+u_{yy}r^{2}\cos^{2}\theta-r\left(u_x\cos\theta+u_y\sin\theta\right).
\end{aligned}
$$

第五步: 把第四步的末项与第一步的 $U_r$ 相认, 即 $U_r=u_x\cos\theta+u_y\sin\theta$, 并用第二步的 $U_{rr}$,

$$
\frac{1}{r^{2}}U_{\theta\theta}+\frac{1}{r}U_r=u_{xx}\sin^{2}\theta-2u_{xy}\sin\theta\cos\theta+u_{yy}\cos^{2}\theta.
$$

第六步: 两式相加,

$$
U_{rr}+\frac{1}{r^{2}}U_{\theta\theta}+\frac{1}{r}U_r=u_{xx}\left(\cos^{2}\theta+\sin^{2}\theta\right)+u_{yy}\left(\sin^{2}\theta+\cos^{2}\theta\right)=u_{xx}+u_{yy}=\Delta{u}.
$$

## 习题 2.4 (调和函数梯度的模)

设 $u\in{C}^{3}\left(\Omega\right)\cap{C}^{1}\left(\overline{\Omega}\right)$ 在 $\Omega$ 内满足 $\Delta{u}=0$, 则

(1) 在 $\Omega$ 内 $\Delta\left(\left|\nabla{u}\right|^{2}\right)\ge0$;

(2) $\left|Du\right|$ 在 $\Omega$ 的边界上取到它在 $\overline{\Omega}$ 上的最大值.

### 解答 2.4

第一步: 记 $w=\left|\nabla{u}\right|^{2}=\sum_{i=1}^{n}\left(\frac{\partial{u}}{\partial{x_i}}\right)^{2}$. 由 $u\in{C}^{3}\left(\Omega\right)$, $w\in{C}^{2}\left(\Omega\right)$, 可逐项求导.

第二步: 算 $w$ 的一阶导数

$$
\frac{\partial{w}}{\partial{x_j}}=2\sum_{i=1}^{n}u_{x_i}u_{x_ix_j}.
$$

第三步: 再关于 $x_j$ 求导

$$
\frac{\partial^{2}w}{\partial{x_j}^{2}}=2\sum_{i=1}^{n}\left(u_{x_ix_j}\right)^{2}+2\sum_{i=1}^{n}u_{x_i}u_{x_ix_jx_j}.
$$

第四步: 对 $j$ 求和, 并把末项的求和次序交换, 使内层求和恰为 $\Delta{u}$ 对 $x_i$ 的导数,

$$
\Delta{w}=2\sum_{i,j=1}^{n}\left(u_{x_ix_j}\right)^{2}+2\sum_{i=1}^{n}u_{x_i}\frac{\partial}{\partial{x_i}}\left(\sum_{j=1}^{n}u_{x_jx_j}\right)=2\sum_{i,j=1}^{n}\left(u_{x_ix_j}\right)^{2}+2\sum_{i=1}^{n}u_{x_i}\frac{\partial}{\partial{x_i}}\Delta{u}.
$$

第五步: 由 $\Delta{u}=0$ 在 $\Omega$ 内成立, 第二项为 $0$, 而第一项是平方和,

$$
\Delta{w}=2\sum_{i,j=1}^{n}\left(u_{x_ix_j}\right)^{2}\ge0,\qquad{x}\in\Omega.
$$

这就证明了 (1).

第六步: 由**定义 2.3.2 (下调和函数, 上调和函数)**, $w$ 在 $\Omega$ 内下调和. 由**定理 2.3.1 (弱极值原理)**, $w$ 在 $\overline{\Omega}$ 上的最大值在 $\partial\Omega$ 上达到. 由于 $w=\left|\nabla{u}\right|^{2}=\left|Du\right|^{2}$, $\left|Du\right|$ 与 $w$ 同时在同一点取最大值, 故 $\left|Du\right|$ 在 $\Omega$ 的边界上取到它在 $\overline{\Omega}$ 上的最大值. 这就证明了 (2).

## 习题 2.5 (三次源项的极值控制)

设 $\Omega$ 是 $\mathbb{R}^{n}$ 中的有界区域, $\varphi\in{C}^{0}\left(\partial\Omega\right)$, $u\in{C}^{2}\left(\Omega\right)\cap{C}^{0}\left(\overline{\Omega}\right)$ 是问题

$$
\begin{cases}\Delta{u}\left(x\right)=u^{3}\left(x\right)-u\left(x\right),&x\in\Omega,\\u\left(x\right)=\varphi\left(x\right),&x\in\partial\Omega\end{cases}
$$

的解. 证明: 若 $\max_{\partial\Omega}\left|\varphi\right|\le1$, 则 $\max_{\overline{\Omega}}\left|u\right|\le1$.

### 解答 2.5

第一步: 先证 $\max_{\overline{\Omega}}u\le1$. 若最大值在 $\partial\Omega$ 上达到, 由 $u=\varphi$ 与 $\max_{\partial\Omega}\left|\varphi\right|\le1$ 立得 $u\le1$.

第二步: 设最大值在某个内点 $x_0\in\Omega$ 达到. 由多元函数取极大值的二阶必要条件, 该点处 $\frac{\partial^{2}u}{\partial{x_i}^{2}}\left(x_0\right)\le0$ 对 $i=1,\dots,n$ 成立, 故

$$
\Delta{u}\left(x_0\right)\le0.
$$

第三步: 代入方程并用 $u=u\left(x_0\right)$ 记该点的值,

$$
u^{3}-u=u\left(u-1\right)\left(u+1\right)=\Delta{u}\left(x_0\right)\le0.
$$

三次多项式 $u\left(u-1\right)\left(u+1\right)$ 取非正值的集合是 $\left(-\infty,-1\right]\cup\left[0,1\right]$, 故 $u\left(x_0\right)\le1$ (若 $u\left(x_0\right)\le-1$, 则更有 $u\left(x_0\right)\le1$). 结合第一步, 得 $\max_{\overline{\Omega}}u\le1$.

第四步: 再证 $\min_{\overline{\Omega}}u\ge-1$. 以 $-u$ 代替 $u$, 它满足 $\Delta\left(-u\right)=-\left(\Delta{u}\right)=-\left(u^{3}-u\right)=\left(-u\right)^{3}-\left(-u\right)$, 即同一形式的方程, 边界值 $-\varphi$ 也满足 $\max_{\partial\Omega}\left|-\varphi\right|\le1$. 由第三步的结果, $\max_{\overline{\Omega}}\left(-u\right)\le1$, 即 $\min_{\overline{\Omega}}u\ge-1$.

第五步: 合并第一, 四步, 得 $\max_{\overline{\Omega}}\left|u\right|\le1$.

## 习题 2.6 (Dirichlet 外问题的唯一性与稳定性)

设 $\Omega$ 是 $\mathbb{R}^{n}$ 中的有界区域, $f\in{C}^{0}\left(\overline{\Omega}\right)$, $\varphi\in{C}^{0}\left(\partial\Omega\right)$. 证明: 下面 Laplace 方程 Dirichlet 外问题

$$
\begin{cases}\Delta{u}\left(x\right)=f\left(x\right),&x\in\mathbb{R}^{n}\setminus\overline{\Omega},\\u\left(x\right)=\varphi\left(x\right),&x\in\partial\Omega,\\\lim_{x\to\infty}u\left(x\right)=0\end{cases}
$$

的解在 $C^{2}\left(\mathbb{R}^{n}\setminus\overline{\Omega}\right)\cap{C}^{0}\left(\mathbb{R}^{n}\setminus\overline{\Omega}\right)$ 中的唯一性和稳定性 (即解连续依赖于边界数据).

### 解答 2.6

第一步: 唯一性等价于齐次问题只有零解. 设 $v$ 满足齐次问题

$$
\Delta{v}=0\,\left(x\in\mathbb{R}^{n}\setminus\overline{\Omega}\right),\qquad{v}=0\,\left(x\in\partial\Omega\right),\qquad\lim_{x\to\infty}v\left(x\right)=0,
$$

需证 $v\equiv0$.

第二步: 由 $\lim_{x\to\infty}v\left(x\right)=0$, 对任意 $\varepsilon>0$ 存在 $R>1$ 使 $\Omega\subset{B}_{R}\left(0\right)$ 且当 $\left|x\right|\ge{R}$ 时 $\left|v\left(x\right)\right|<\varepsilon$.

第三步: 在环形区域 $B_{2R}\left(0\right)\setminus\overline{\Omega}$ 上用**定理 2.3.1 (弱极值原理)**. 该区域有界, $\Delta{v}=0$ 在其内成立, 故

$$
\max_{B_{2R}\left(0\right)\setminus\overline{\Omega}}v=\max_{\partial\left(B_{2R}\left(0\right)\setminus\overline{\Omega}\right)}v=\max\left\{\max_{\partial{B}_{2R}\left(0\right)}v,\max_{\partial\Omega}v\right\}<\varepsilon.
$$

末一个不等号用了第二步的 $\left|v\right|<\varepsilon$ (在 $\left|x\right|\ge{R}$ 上) 与 $v|_{\partial\Omega}=0$. 同法对 $-v$ 用弱极值原理得 $\min{v}>-\varepsilon$.

第四步: 于是 $\left|v\right|<\varepsilon$ 在整个 $B_{2R}\left(0\right)\setminus\overline{\Omega}$ 上成立, 而在 $\left|x\right|\ge{R}$ 上由第二步 $\left|v\right|<\varepsilon$. 由 $\varepsilon>0$ 任意, $v\equiv0$. 唯一性得证.

第五步: 证稳定性. 设 $u_1,u_2$ 分别是数据 $\left(f_1,\varphi_1\right)$, $\left(f_2,\varphi_2\right)$ 的解, 记 $v=u_1-u_2$, $F=f_1-f_2$, $\Phi=\varphi_1-\varphi_2$. 则

$$
\Delta{v}=F\,\left(x\in\mathbb{R}^{n}\setminus\overline{\Omega}\right),\qquad{v}=\Phi\,\left(x\in\partial\Omega\right),\qquad\lim_{x\to\infty}v\left(x\right)=0.
$$

第六步: 由 $\lim_{x\to\infty}v=0$, 对任意 $\varepsilon>0$ 存在 $R>1$ 使 $\left|v\right|<\varepsilon$ 当 $\left|x\right|\ge{R}$. 在环形区域 $B_{2R}\left(0\right)\setminus\overline{\Omega}$ 上用**定理 2.3.3 (最大模估计)**, 取 $d=2R$,

$$
\max_{B_{2R}\left(0\right)\setminus\overline{\Omega}}\left|v\right|\le\max\left\{\varepsilon,\max_{\partial\Omega}\left|\Phi\right|\right\}+\frac{2R^{2}}{n}\max_{\overline{\Omega}}\left|F\right|.
$$

第七步: 于是给定 $\varepsilon>0$, 只要 $\max_{\partial\Omega}\left|\Phi\right|<\varepsilon$ 且 $\max_{\overline{\Omega}}\left|F\right|<\frac{\varepsilon}{2R^{2}/n}$, 就有 $\left|v\right|<\varepsilon$ 在整个 $\mathbb{R}^{n}\setminus\overline{\Omega}$ 上成立. 这正是解按最大模连续依赖于 $\left(f,\varphi\right)$ 的含义.

## 习题 2.7 (引理 2.4.3 的二维情形)

证明: 引理 2.4.3 $n=2$ 的情形.

即证: 设 $f\in{C}^{0}\left(\overline{\Omega}\right)$, 由 $u_0\left(x\right):=-\int_{\Omega}\Gamma\left(x-y\right)f\left(y\right)\,\mathrm{d}y$ 定义的 Newton 位势满足 $u_0\in{C}^{1}\left(\mathbb{R}^{2}\right)$ 且

$$
\partial_{x_i}u_0\left(x\right)=-\int_{\Omega}\partial_{x_i}\Gamma\left(x-y\right)f\left(y\right)\,\mathrm{d}y,\qquad{i}=1,2.
$$

### 解答 2.7

第一步: 写出 $n=2$ 时的核. 由**定义 2.4.1 (基本解)**,

$$
K\left(x\right):=\Gamma\left(x\right)=\frac{1}{2\pi}\ln\frac{1}{\left|x\right|},\qquad\nabla{K}\left(x\right)=-\frac{1}{2\pi}\frac{x}{\left|x\right|^{2}},\qquad\left|\nabla{K}\left(x\right)\right|=\frac{1}{2\pi\left|x\right|}.
$$

奇性为 $\left|\nabla{K}\right|\sim\frac{1}{\left|x\right|}$, 只局部可积, 故 $\int_{\Omega}\partial_{x_i}\Gamma\left(x-y\right)f\left(y\right)\,\mathrm{d}y$ 是反常积分, 直接求导不可行, 需先正则化.

第二步: 对任意 $\varepsilon>0$, 定义光滑截断核

$$
K_{\varepsilon}\left(x\right):=\begin{cases}\frac{\varepsilon^{2}-\left|x\right|^{2}}{4\pi\varepsilon^{2}}+K\left(\varepsilon\right),&\left|x\right|\le\varepsilon,\K\left(x\right),&\left|x\right|>\varepsilon.\end{cases}\tag{B}
$$

在 $\left|x\right|=\varepsilon$ 处两式为 $\frac{0}{4\pi\varepsilon^{2}}+K\left(\varepsilon\right)=K\left(\varepsilon\right)$, 一阶偏导数为 $\frac{-x_i}{2\pi\varepsilon^{2}}$ 与 $-\frac{1}{2\pi}\left.\frac{x_i}{\left|x\right|^{2}}\right|_{\left|x\right|=\varepsilon}=-\frac{x_i}{2\pi\varepsilon^{2}}$, 两侧相等, 故 $K_\varepsilon\in{C}^{1}\left(\mathbb{R}^{2}\right)$ 且

$$
\partial_{x_i}K_{\varepsilon}\left(x\right)=\begin{cases}-\frac{x_i}{2\pi\varepsilon^{2}},&\left|x\right|\le\varepsilon,\\-\frac{1}{2\pi}\frac{x_i}{\left|x\right|^{2}},&\left|x\right|>\varepsilon.\end{cases}\tag{A}
$$

第三步: 定义正则化解 $u_\varepsilon\left(x\right):=-\int_{\Omega}K_\varepsilon\left(x-y\right)f\left(y\right)\,\mathrm{d}y$. 由于 $K_\varepsilon\in{C}^{1}\left(\mathbb{R}^{2}\right)$ 且 $\Omega$ 有界, 被积函数及其导数都在紧集上连续, 由含参积分的可微性 $u_\varepsilon\in{C}^{1}\left(\mathbb{R}^{2}\right)$ 且

$$
\partial_{x_i}u_\varepsilon\left(x\right)=-\int_{\Omega}\partial_{x_i}K_\varepsilon\left(x-y\right)f\left(y\right)\,\mathrm{d}y,\qquad{i}=1,2.
$$

第四步: 由一致收敛保持可微性, 只需证当 $\varepsilon\to0$ 时

(1) $\left\{u_\varepsilon\right\}$ 在 $\mathbb{R}^{2}$ 上一致收敛到 $u_0$;

(2) $\left\{\partial_{x_i}u_\varepsilon\right\}$ 在 $\mathbb{R}^{2}$ 上一致收敛到 $-\int_{\Omega}\partial_{x_i}\Gamma\left(x-y\right)f\left(y\right)\,\mathrm{d}y$.

第五步: 证 (1). 由 $K\ge{K}_\varepsilon$,

$$
\left|u_\varepsilon\left(x\right)-u_0\left(x\right)\right|\le\sup_{\Omega}\left|f\right|\int_{\left|y-x\right|\le\varepsilon}\left(K\left(x-y\right)-K_\varepsilon\left(x-y\right)\right)\mathrm{d}y.
$$

由 $K$ 与 $K_\varepsilon$ 的定义, 在 $\left|z\right|\le\varepsilon$ 上 $K\left(z\right)-K_\varepsilon\left(z\right)=\frac{1}{2\pi}\ln\frac{\varepsilon}{\left|z\right|}-\frac{\varepsilon^{2}-\left|z\right|^{2}}{4\pi\varepsilon^{2}}\le\frac{1}{2\pi}\ln\frac{\varepsilon}{\left|z\right|}$. 用球坐标

$$
\int_{\left|z\right|\le\varepsilon}\frac{1}{2\pi}\ln\frac{\varepsilon}{\left|z\right|}\,\mathrm{d}z=2\pi\cdot\frac{1}{2\pi}\int_0^{\varepsilon}r\ln\frac{\varepsilon}{r}\,\mathrm{d}r=\frac{\varepsilon^{2}}{4},
$$

其中末一步是 $\int_0^{\varepsilon}r\ln\frac{\varepsilon}{r}\mathrm{d}r=\varepsilon^{2}\int_0^{1}s\ln\frac{1}{s}\mathrm{d}s=\frac{\varepsilon^{2}}{4}$. 故

$$
\left|u_\varepsilon\left(x\right)-u_0\left(x\right)\right|\le\frac{\varepsilon^{2}}{4}\sup_{\Omega}\left|f\right|\to0\qquad\left(\varepsilon\to0\right),
$$

(1) 得证.

第六步: 证 (2). 由 (A),

$$
\left|\partial_{x_i}u_\varepsilon\left(x\right)+\int_{\Omega}\partial_{x_i}\Gamma\left(x-y\right)f\left(y\right)\,\mathrm{d}y\right|\le\sup_{\Omega}\left|f\right|\int_{\left|z\right|\le\varepsilon}\left|\partial_{x_i}K_\varepsilon\left(z\right)-\partial_{x_i}K\left(z\right)\right|\mathrm{d}z.
$$

在 $\left|z\right|\le\varepsilon$ 上 $\left|\partial_{x_i}K_\varepsilon-\partial_{x_i}K\right|=\frac{\left|z_i\right|}{2\pi}\left|\frac{1}{\varepsilon^{2}}-\frac{1}{\left|z\right|^{2}}\right|$, 且 $\left|z_i\right|\le\left|z\right|=r$, 故

$$
\left|\partial_{x_i}K_\varepsilon-\partial_{x_i}K\right|\le\frac{1}{2\pi}\left(\frac{r}{\varepsilon^{2}}+\frac{1}{r}\right).
$$

用球坐标,

$$
\int_{\left|z\right|\le\varepsilon}\frac{1}{2\pi}\left(\frac{r}{\varepsilon^{2}}+\frac{1}{r}\right)\mathrm{d}z=\frac{1}{2\pi}\int_0^{\varepsilon}2\pi{r}\left(\frac{r}{\varepsilon^{2}}+\frac{1}{r}\right)\mathrm{d}r=\int_0^{\varepsilon}\left(\frac{r^{2}}{\varepsilon^{2}}+1\right)\mathrm{d}r=\frac{4\varepsilon}{3}.
$$

故

$$
\left|\partial_{x_i}u_\varepsilon\left(x\right)+\int_{\Omega}\partial_{x_i}\Gamma\left(x-y\right)f\left(y\right)\,\mathrm{d}y\right|\le\frac{4\varepsilon}{3}\sup_{\Omega}\left|f\right|\to0\qquad\left(\varepsilon\to0\right),
$$

(2) 得证.

第七步: 由 (1) 与 (2), $\left\{u_\varepsilon\right\}$ 与 $\left\{\partial_{x_i}u_\varepsilon\right\}$ 都在 $\mathbb{R}^{2}$ 上一致收敛, 故 $u_0\in{C}^{1}\left(\mathbb{R}^{2}\right)$ 且导数可以搬进积分号内, 即 $\partial_{x_i}u_0\left(x\right)=-\int_{\Omega}\partial_{x_i}\Gamma\left(x-y\right)f\left(y\right)\,\mathrm{d}y$. 引理 2.4.3 的 $n=2$ 情形得证.
