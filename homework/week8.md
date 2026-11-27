# week8

第 II 章 §7–§10, 镜像法, 可去奇点与 Hopf 引理, 外问题, Perron 方法, Neumann 问题. 这一周全是构造, 每一问都能落到具体公式上.

> **引理 7.1 (镜像法的框架)**
>
> 设 $h$ 为 $\Omega$ 上简单的校正函数 (即 $h$ 在 $\Omega$ 内调和, 特别在 $y=x$ 处正则, 且 $h(x,y)=\Gamma(x-y)$ 于 $\partial\Omega$). 令 $G(x,y)=\Gamma(x-y)-h(x,y)$, 则 $G$ 是 $\Omega$ 上的 Green 函数.

> **定理 7.2 (半空间上 Dirichlet 问题的积分表示)**
>
> 取 $\Omega=\{x_n\gt0\}$. 则 $G(x,y)=\Gamma(x-y)-\Gamma(x^*-y)$, $x^*=(x_1,\dots,x_{n-1},-x_n)$, 且 Poisson 核为 $\frac{2x_n}{\omega_n|x-y|^n}$.

> **例 7.3 (半空间, 四分之一平面, 角度区域)**
>
> $\Omega=\{x_n\gt0\}$, $g\in C(\partial\Omega)$ 有界. 则
> $$
> u(x)=\frac{2x_n}{\omega_n}\int_{\mathbb R^{n-1}}\frac{g(y)}{(|x'-y|^2+x_n^2)^{n/2}}\,\mathrm dy,
> $$
> 二维时化为 $u(x)=\frac{x_2}{\pi}\int_{\mathbb R}\frac{g(y_1)}{(x_1-y_1)^2+x_2^2}\,\mathrm dy_1$.

> **定理 7.6 (球与上半球上的公式)**
>
> $\Omega=B_R(0)$ 时 $G(x,y)=\Gamma(x-y)-\Gamma\left(\frac{|x|}{R}\left|y-\tilde x\right|\right)$, 其中 $\tilde x=\frac{R^2}{|x|^2}x$ 是 $x$ 关于球面的反演点, Poisson 核 $K(x,y)=\frac{1}{\omega_nR|x-y|^n}\left(R^2-|x|^2\right)$.

> **例 7.10 (球上二次边值问题)**
>
> $\Delta u=0$ 于 $B_R(0)$, $u=y_1^2$ 于 $\partial B_R(0)$ 的解为 $u(x)=x_1^2+\frac{R^2-|x|^2}{n}$.

> **命题 7.7 (上半球, 平底 Neumann)**
>
> $\Omega=B_R^+(0)$ 平底部分取 Neumann 条件, 用偶延拓 $G^D(x,y)+G^D(\bar x,y)$, $\bar x=(x_1,\dots,x_{n-1},-x_n)$, 得 $G^N$.

> **定理 8.1 (可去奇点)**
>
> 若 $u$ 在 $B_R(x_0)\setminus\{x_0\}$ 调和, 且 $\lim_{x\to x_0}\frac{u}{\Gamma(x-x_0)}=0$ (三维应写成 $\lim_{x\to x_0}|x-x_0|^{n-2}u=0$), 则 $u$ 可延拓为 $B_R(x_0)$ 上的调和函数.

> **定理 8.3 (二维与三维外问题的唯一性)**
>
> (1) 若 $\Delta u=0$ 于 $\mathbb R^n\setminus\overline{B_{r_0}}$, 且 $\lim_{|x|\to\infty}|x|^{n-2}u(x)=0$ ($n=3$) 或 $\lim_{|x|\to\infty}\frac{u(x)}{\log|x|}=0$ ($n=2$), 则 $u$ 有界; 若还有 $u=0$ 于 $\partial B_{r_0}$, 则 $u\equiv0$. (2) 若边界条件改为 $D_\nu u=0$ 于是 $u$ 为常数.

> **定理 9.8 (Perron 方法的解)**
>
> 设 $\Omega$ 有界, $g$ 有界, $\Phi_g$ 是 Perron 下解族的点态上确界. 若 $\Phi_g$ 在 $x_0\in\partial\Omega$ 处由障碍函数控制, 则 $\Delta\Phi_g=0$ 于 $\Omega$, 且 $\lim_{x\to x_0}\Phi_g(x)=g(x_0)$.

> **定理 9.12 (Perron 定理)**
>
> 若 $\Omega$ 有界, 且每个边界点都有障碍函数, 则对任意 $g\in C(\partial\Omega)$, Dirichlet 问题的解存在且等于 $\Phi_g$.

> **定理 10.3 (外问题的 Neumann 问题)**
>
> 若 $\Omega$ 有界, 则外 Neumann 问题有解且仅当 $\int_{\partial\Omega}f\,\mathrm dS=0$; 且解在相差一个常数的意义下唯一.

## 习题 8.1 (半空间 Green 函数的归一化)

取 $n=2$, $\Omega=\{x_2\gt0\}$.

(1) 用**引理 7.1** 写出 $h(x,y)=\Gamma(x^*-y)$, 验证 $h$ 在 $y=x$ 处正则, 且 $y_2=0$ 时 $|x^*-y|=|x-y|$, 于是 $G(x,y)=\Gamma(x-y)-\Gamma(x^*-y)$;
(2) 由 $\Gamma=-\frac{1}{2\pi}\log|x-y|$ 算出 $D_{\nu_y}\Gamma(x-y)=-D_{\nu_y}\Gamma(x^*-y)$ 于 $y_2=0$ (提示: 两点到 $y$ 的距离在边界上相等, 但 $\nu$ 方向反号);
(3) 由**定理 7.2** 得 $K=\frac{2x_2}{\omega_2|x-y|^2}=\frac{x_2}{\pi\left((x_1-y_1)^2+x_2^2\right)}$, 直接算 $\int_{\mathbb R}K\,\mathrm dy_1$ 并验证等于 $1$ (用 $\int\frac{\mathrm dt}{t^2+a^2}=\frac{\pi}{a}$);
(4) 取 $g=\mathbf 1_{[-1,1]}$, 写出 $u$ 的 arctan 形式并检查 $x_2\to0^+$ 时的极限.

> 自测 35 分钟. 核对: 附录 A §7.1, 例 7.3.

## 习题 8.2 (角度区域的解)

$\Omega=\{x_2\gt0\}$ 中取 $g=\mathbf 1_{(0,\infty)}(x_1)$.

(1) 由**例 7.3** 写出 $u$ 的积分式, 并把 $\mathrm dt$ 的积分算成 arctan;
(2) 得 $u(x)=\frac{1}{\pi}\left(\frac{\pi}{2}+\arctan\frac{x_1}{x_2}\right)$, 验证 $\partial\Omega$ 上 $x_1\gt0$ 时为 $1$, $x_1\lt0$ 时为 $0$;
(3) 说明 $u$ 只依赖 $\theta=\arctan(x_1/x_2)$, 并写出 $u$ 在极坐标下的表达式;
(4) 若把 $g$ 换成 $x_1$ 的二次函数, 说明为什么这个积分不再给出初等解.

> 自测 30 分钟. 核对: 附录 A 例 7.3.

## 习题 8.3 (球上的 Poisson 核)

(1) 按**定理 7.6** 写出 $K(x,y)$ 与其归一化 $\int_{\partial B_R}K\,\mathrm dS_y=1$;
(2) 取 $g\equiv1$, 说明解只能是 $u\equiv1$, 并与弱极值原理一致;
(3) 取 $g(y)=y_1$, 说明 $u(x)=x_1$ 是解 (线性函数既调和又在边界上相等), 于是 Poisson 积分必须等于 $x_1$, 由此验证核的一阶矩;
(4) 用**例 7.10** 处理 $g=y_1^2$: 验证 $u=x_1^2+\frac{R^2-|x|^2}{n}$ 调和且边界为 $y_1^2$, 再取 $n=2$, $R=1$ 写成 $u=\frac12+\frac12r^2\cos2\theta$;
(5) 说明 **命题 7.7** 上半球平底取 Neumann 时为何用偶延拓, 而斜边部分仍用 Dirichlet 的镜像.

> 自测 40 分钟. 核对: 附录 A §7.4–§7.5, 例 7.10.

## 习题 8.4 (可去奇点与外问题的唯一性)

(1) 按**定理 8.1**, 对 $\rho\in(0,R)$ 令 $\phi_\rho(x)=\frac{u(x)}{M_\rho\Gamma(x-x_0)}$ (三维用 $|x-x_0|^{n-2}$), 说明 $\phi_\rho$ 在边界 $|x-x_0|\le\rho$ 上 $\ge1$, 在外边界上 $\le1$, 由比较原理得 $u\le M_\rho\Gamma$;
(2) 说明 $\lim_{x\to x_0}\frac{u}{\Gamma}=0$ 这一增长率条件在哪一步用掉, 以及为什么它不能减弱为"$u$ 有界";
(3) 验证 $u=\Gamma(x)$ 本身在 $\mathbb R^n\setminus\{0\}$ 内调和且在原点附近满足 $|\nabla u|\to\infty$, 用来说明可去奇点的条件不可去;
(4) 按**定理 8.3** 构造两个反例: $u=\log\frac{R}{|x|}$ ($n=2$) 与 $u=1-\frac{R}{|x|}$ ($n=3$), 在球外调和、边界为零、但非零, 说明"趋于零"的速率条件恰好是排除它们的临界条件.

> 自测 35 分钟. 核对: 附录 A §8.1, §8.3.

## 习题 8.5 (Perron 方法与障碍函数)

(1) 取 $\Phi_g$ 为 Perron 下解族的点态上确界, 说明它下调和 (取两条下解逐点最大即得上调和的下解族封闭性);
(2) 按**定理 9.8**, 取一列下解 $v_k$ 使 $v_k(x)\to\Phi_g(x)$, 由 Harnack 不等式 (配 $\Phi_g$ 一致有界) 得 $v_k$ 的收敛子列, 从而得到 $\Phi_g$ 的球平均值回归;
(3) 说明为什么在 $x_0\in\partial\Omega$ 处必须另起论证 (强最小值原理 + 障碍函数 $\overline\Phi$ 压住上界), 并写出"$u$ 在 $x_0$ 处连续"的那一步;
(4) 一句话说明**定理 9.12** 与 Neumann 问题的相容条件为何是两类完全不同的存在性障碍.

> 自测 35 分钟. 核对: 附录 A §9.1–§9.5.

## 习题 8.6 (Neumann 问题)

(1) 按**定理 10.3**, 说明外 Neumann 问题 $\Delta u=0$ 于 $\mathbb R^n\setminus\overline\Omega$, $D_\nu u=f$, $\lim_{|x|\to\infty}u=0$ 有两类证法: 全局 Laplace 恒等式, 以及先证无穷远可达性;
(2) 在内部 Neumann 问题 $\Delta u=0$ 于 $B_R$, $D_\nu u=f$ 上, 直接算 $\int_{B_R}\Delta u\,\mathrm dy=\int_{\partial B_R}D_\nu u\,\mathrm dS$, 得相容条件 $\int f\,\mathrm dS=0$;
(3) 重做圆盘例: $n=2$, $\Omega=B_1$, $D_\nu u=\cos2\theta$, 验证 $u=\frac12r^2\cos2\theta+C$ 是解 (提示: $\Delta(r^2\cos2\theta)=0$, $D_r\left(\frac12r^2\cos2\theta\right)|_{r=1}=\cos2\theta$);
(4) 说明常数 $C$ 为何不可去掉, 若加条件 $u(0)=0$ 能否定下来.

> 自测 30 分钟. 核对: 附录 A §10.
