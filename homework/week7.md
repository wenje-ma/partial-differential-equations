# week7

第 II 章 §5–§6, 基本解, Newton 位势与 Green 表示. 这一章是整本书的地基, 计算量集中在这里.

> **定义 5.1 (基本解)**
>
> $\Gamma(x)=\frac{1}{2\pi}\log\frac{1}{|x|}$ ($n=2$), $\Gamma(x)=\frac{1}{(n-2)\omega_n|x|^{n-2}}$ ($n>3$); 且 $D_\nu\Gamma(x)=-\frac{1}{\omega_nr^{n-1}}$ 于 $|x|=r$.

> **定理 5.2 (基本解的分布意义)**
>
> 在分布意义下 $-\Delta\Gamma=\delta_0$, 即对 $\varphi\in C_c^\infty(\mathbb R^n)$ 有 $\int_{\mathbb R^n}\Gamma\Delta\varphi\,\mathrm dx=-\varphi(0)$.

> **定理 5.4 (Newton 位势的 $C^1$ 正则性)**
>
> 若 $f\in C(\Omega)$, 令 $u_0(x)=-\int_\Omega\Gamma(x-y)f(y)\,\mathrm dy$, 则 $u_0\in C^1(\mathbb R^n)$ 且 $D_iu_0(x)=\frac{1}{\omega_n}\int_\Omega\frac{x_i-y_i}{|x-y|^n}f(y)\,\mathrm dy$.

> **例 5.7 (球内的常源问题)**
>
> $\Delta u=1$ 于 $B_R(0)$, $u|_{\partial B_R}=0$ 的唯一经典解是 $u(x)=\frac{|x|^2-R^2}{2n}$.

> **定理 6.1 (基本解表示公式)**
>
> 设 $\Omega$ 有界且边界分片 $C^1$, $u\in C^2(\Omega)\cap C^1(\overline\Omega)$, $\Delta u\in L^1(\Omega)$. 则
> $$
> u(x)=-\int_\Omega\Gamma(x-y)\Delta u(y)\,\mathrm dy+\int_{\partial\Omega}\Gamma(x-y)D_\nu u(y)\,\mathrm dS_y-\int_{\partial\Omega}u(y)D_{\nu_y}\Gamma(x-y)\,\mathrm dS_y.
> $$

> **定理 6.2 (Green 函数的性质)**
>
> 设 $\Omega$ 有界, 且校正函数存在. 则 $G(x,y)$ 由 $\Gamma$ 与区域唯一确定; $G(x,y)=G(y,x)$; 且 $G(x,y)\gt0$ 当 $x\ne y$.

> **命题 6.4 (Poisson 核的非负性与归一化)**
>
> 在足够光滑的有界区域上, $K(x,y)=-D_{\nu_y}G(x,y)\gt0$ 且 $\int_{\partial\Omega}K(x,y)\,\mathrm dS_y=1$.

## 习题 7.1 (径向调和函数与通量归一化)

设 $u(x)=v(r)$, $r=|x|$.

(1) 由链式法则写出 $D_iu$ 与 $D_i^2u$, 求和得径向 Laplace 方程 $v''+\frac{n-1}{r}v'=0$;
(2) 令 $w=v'$, 解 $w'=-\frac{n-1}{r}w$, 得 $v=C_1\log r+C_2$ ($n=2$) 与 $v=\frac{C_1}{2-n}r^{2-n}+C_2$ ($n>3$), 说明 $C_2$ 为何不影响点源强度;
(3) 用 $\int_{\partial B_r(0)}D_\nu v\,\mathrm dS=-1$ 定出 $C_1$, 得到**定义 5.1** 中的两个常数, 并验证 $D_\nu\Gamma=-\frac{1}{\omega_nr^{n-1}}$ 与维数无关;
(4) 直接算 $\Delta\Gamma$ 于 $\mathbb R^n\setminus\{0\}$, 说明原点之外它确实调和.

> 自测 30 分钟. 核对: 附录 A §5.1.

## 习题 7.2 (定理 5.2 的挖球证明)

对 $\varphi\in C_c^\infty(\mathbb R^n)$, 取 $R$ 使 $\operatorname{supp}\varphi\subset B_R(0)$.

(1) 在穿孔球 $B_R(0)\setminus B_r(0)$ 上用 Green 第二恒等式, 写出 $\int_{B_R\setminus B_r}\Gamma\Delta\varphi\,\mathrm dx$ 等于哪两个边界积分;
(2) 说明外球面上的项为什么消失, 内球面 $\partial B_r(0)$ 上外法向为何是 $\nu=-x/r$;
(3) 估 $\int_{\partial B_r}\Gamma D_\nu\varphi\,\mathrm dS$ 的量级 (三维为 $O(r)$, 二维为 $O(r|\log r|)$), 说明它趋于零;
(4) 算出 $-\int_{\partial B_r}\varphi D_\nu\Gamma\,\mathrm dS=\fint_{\partial B_r}\varphi\,\mathrm dS\to\varphi(0)$, 从而 $-\Delta\Gamma=\delta_0$.

> 自测 30 分钟. 核对: 附录 A §5.2.

## 习题 7.3 (Newton 位势的一阶导数)

(1) 说明 $D^2\Gamma$ 具有 $|x|^{-n}$ 阶奇性因而不可积, 所以不能直接在原积分下求二阶导数;
(2) 按**定理 5.4** 的构造写出截断核 $\Gamma_\varepsilon$, 并检查函数值与一阶径向导数在 $|x|=\varepsilon$ 处对接;
(3) 用 $\int_{B_\varepsilon}(\Gamma-\Gamma_\varepsilon)\,\mathrm dz=\frac{\varepsilon^2}{2(n+2)}$ 与 $\int_{B_\varepsilon}\left(\frac{|z|}{\varepsilon^n}+\frac{1}{|z|^{n-1}}\right)\mathrm dz=\frac{n+2}{n+1}\omega_n\varepsilon$ 说明函数差为 $O(\varepsilon^2)$, 一阶导数为 $O(\varepsilon)$;
(4) 取 $f\equiv1$, $\Omega=B_R(0)$, $x=0$, 验证 $D_iu_0(0)=0$ (被积函数关于 $y$ 为奇函数).

> 自测 30 分钟. 核对: 附录 A §5.4.

## 习题 7.4 (常源球与稳态温度)

(1) 用 $\Delta|x|^2=2n$ 说明 $\Delta\left(\frac{|x|^2}{2n}\right)=1$;
(2) 于是**例 5.7** 的解为 $u=\frac{|x|^2-R^2}{2n}$, 验证边界为零, 并用弱极值原理说明唯一;
(3) 若稳态温度满足 $\Delta T=-\frac{q_0}{k}$ ($q_0\gt0$ 均匀热源), 边界温度为零, 写出 $T$ 并求出最高温度与位置;
(4) 说明 $R$ 增大时最高温度按 $R^2$ 增长的具体含义.

> 自测 25 分钟. 核对: 附录 A §5.5 末, 例 5.7.

## 习题 7.5 (定理 6.1 的推导)

(1) 固定 $x\in\Omega$, 在 $\Omega_r=\Omega\setminus B_r(x)$ 上对 $u(y)$ 与 $\Gamma(x-y)$ 用 Green 第二恒等式, 注意 $\Delta_y\Gamma(x-y)=0$;
(2) 说明 $r\to0$ 时体积项趋于 $\int_\Omega\Gamma\Delta u$, 并分别估计内球面上两项;
(3) 算出内球面 $-u D_{\nu_r}\Gamma$ 项 (用 $\nu_r=-(y-x)/r$ 与 $D_{\nu_r}\Gamma=\frac{1}{\omega_nr^{n-1}}$) 的极限为 $-u(x)$, 从而移项得到 (6.2);
(4) 回答: 表示公式里出现了 $D_\nu u$, 而 Dirichlet 问题并不给这一项, 所以下一步必须做什么.

> 自测 35 分钟. 核对: 附录 A §6.1.

## 习题 7.6 (对称性, 正性与归一化)

(1) 按**定理 6.2** 的 (2), 取 $a(z)=G(x,z)$, $b(z)=G(y,z)$, 在 $\Omega\setminus(\overline{B_r(x)}\cup\overline{B_r(y)})$ 上用 Green 第二恒等式, 说明外边界项因齐次条件消失, 只剩两个内球面项;
(2) 算出 $\partial B_r(x)$ 上的积分趋于 $-G(y,x)$, $\partial B_r(y)$ 上的积分趋于 $G(x,y)$, 得对称性;
(3) 按**定理 6.2** 的 (3), 先由奇点邻域与弱最小值原理得 $G(x,\cdot)\ge0$, 再用 Harnack 不等式排除内部零点;
(4) 用**命题 6.4** 说明: 由 $G(x,y-t\nu_y)\gt0$ 取 $t\to0^+$ 得 $K\gt0$; 对 $u\equiv1$ 用表示公式 (6.5) 得 $\int K\,\mathrm dS=1$.

> 自测 35 分钟. 核对: 附录 A §6.3.
