# week5

第 II 章 §1–§2, 调和函数与平均值性质. 这一章按编号条目对答案, 先把本周用到的条目抄在下面.

> **引理 2.1 (球面平均的导数)**
>
> 设 $u\in C^2(\Omega)$, $B_R(x)\subset\Omega$, $A(r)=\fint_{\partial B_r(x)}u\,\mathrm dS$, $0<r<R$. 则 $A'(r)=\frac{1}{\omega_nr^{n-1}}\int_{B_r(x)}\Delta u\,\mathrm dy=\fint_{\partial B_r(x)}D_\nu u\,\mathrm dS$.

> **定理 2.2 (平均值性质)**
>
> 若 $u$ 在 $\Omega$ 内调和, 则对每个 $B_r(x)\subset\Omega$ 有 $u(x)=\fint_{\partial B_r(x)}u\,\mathrm dS=\fint_{B_r(x)}u\,\mathrm dy$. 反之, 若 $u\in C^2(\Omega)$ 且对所有充分小的 $r$ 满足第一式, 则 $u$ 在 $\Omega$ 内调和.

> **定义 2.3 (下调和函数, 上调和函数)**
>
> 设 $u\in C^2(\Omega)$. 若 $\Delta u\ge0$, 称 $u$ 为下调和函数; 若 $\Delta u\le0$, 称 $u$ 为上调和函数.

> **命题 2.4**
>
> 若 $u\in C^2(\Omega)$ 且 $\Delta u\ge0$, 则对 $B_r(x)\subset\Omega$ 有 $u(x)\le\fint_{B_r(x)}u\,\mathrm dy\le\fint_{\partial B_r(x)}u\,\mathrm dS$.

> **定理 2.6 (平均值性质的逆定理)**
>
> 设 $u\in C(\Omega)$, 并且对每个 $x\in\Omega$, 当 $r>0$ 充分小时都有 $u(x)=\fint_{\partial B_r(x)}u\,\mathrm dS$. 则 $u\in C^\infty(\Omega)$, 且 $u$ 在 $\Omega$ 内调和.

> **推论 2.7 (调和函数列的局部一致极限)**
>
> 若 $u_k$ 在 $\Omega$ 内调和, 且 $u_k$ 在 $\Omega$ 的每个紧子集上一致收敛到 $u$, 则 $u$ 在 $\Omega$ 内调和.

## 习题 5.1 (从引理 2.1 到定理 2.2)

只允许用**引理 2.1**与**定理 2.2**的陈述, 补出球体平均值等式.

(1) 由 $\Delta u=0$ 推出 $A'(r)=0$, 从而 $A(r)\equiv A$, 并说明 $A=\lim_{r\to0^+}A(r)=u(x)$ 用到 $u$ 的哪一条性质;
(2) 把 $A(r)=u(x)$ 乘以球面面积 $\omega_nr^{n-1}$, 对 $r$ 从 $0$ 到 $R$ 积分, 左边写成 $\alpha_nR^nu(x)$, 右边写成 $\int_{B_R(x)}u\,\mathrm dy$, 并核对 $\omega_n=n\alpha_n$ 在此处的用处;
(3) 反过来, 若只知道球体平均值等式恒成立, 怎样回到 $A'(r)=0$, 进而回到 $\Delta u(x)=0$ (提示: 对半径求导, 除以 $|B_r(x)|$ 令 $r\to0^+$).

> 自测 25 分钟. 核对: 附录 A §2.2.

## 习题 5.2 ($|x|^2$: 下调和与三重不等式)

取 $u(x)=|x|^2$ 于 $\mathbb R^n$.

(1) 算 $\Delta u$, 由**定义 2.3**判定它是下调和还是上调和;
(2) 取 $x=0$, $r=1$, $n=3$, 分别算出 $u(0)$, $\fint_{B_1}u\,\mathrm dy$, $\fint_{\partial B_1}u\,\mathrm dS$, 核对**命题 2.4** 的三重不等式 (答案里出现 $\frac35$ 与 $1$);
(3) 说明为何 $|x|^2$ 满足不等式链而不满足等式链, 这与"凸函数不超过端点平均"的一维直观如何对应.

> 自测 20 分钟. 核对: 附录 A §2.3, 例 2.5.

## 习题 5.3 ($x_1^2-x_2^2$: 调和与球面平均)

取 $u(x)=x_1^2-x_2^2$ 于 $\mathbb R^2$.

(1) 算 $\Delta u$, 说明它是调和函数;
(2) 不用**定理 2.2**, 直接对 $x=(a,b)$ 算 $\fint_{\partial B_r(x)}u\,\mathrm dS$ 并验证等于 $u(x)$ (提示: 球面上 $y_1^2+y_2^2=r^2+2ay_1+2by_2-|x|^2$, 一次项的积分为零);
(3) 用同一个 $u$ 检验**命题 2.4** 的链在 $\Delta u=0$ 时两端相等.

> 自测 25 分钟. 核对: 附录 A §2.2 与例 2.5.

## 习题 5.4 (定理 2.6 的磨光骨架)

设 $u\in C(\Omega)$ 满足局部球面平均值等式, $\eta_\varepsilon$ 为径向磨光核, $u_\varepsilon=\eta_\varepsilon*u$.

(1) 把 $u_\varepsilon(x)$ 写成 $\int_0^\varepsilon\varepsilon^{-n}\tilde\eta(r/\varepsilon)\left(\int_{\partial B_r(x)}u\,\mathrm dS\right)\mathrm dr$, 说明内层积分为什么可直接换成 $\omega_nr^{n-1}u(x)$;
(2) 从而得 $u_\varepsilon(x)=u(x)\int_{B_1(0)}\eta\,\mathrm dz=u(x)$, 说明这一步用了磨光核的哪两条性质;
(3) 于是 $u=u_\varepsilon$ 于 $\Omega_\varepsilon$, 得 $u\in C^\infty(\Omega)$; 再说明此时回到**定理 2.2** 的逆命题即得 $\Delta u=0$;
(4) 回答: 整个论证为什么不需要预先假设 $u$ 可微.

> 自测 35 分钟. 核对: 附录 A §2.4.

## 习题 5.5 (推论 2.7 与其边界)

(1) 用**推论 2.7** 证明: 若 $u_k$ 调和且在每个紧子集上一致收敛到 $u$, 则 $u$ 调和, 并指出一致收敛给出的连续性用在哪一步;
(2) 构造一例说明"逐点收敛"不够 (取 $\Omega=(0,1)$, 让 $u_k$ 仅在稠密集上趋于目标, 说明极限可以不连续, 因而得不到调和性);
(3) 一句话总结: 平均值性质能替代"可微"这一前提, 靠的是什么.

> 自测 20 分钟. 核对: 附录 A §2.4 末尾.

## 习题 5.6 (陈述默写)

不看讲义, 15 分钟内写出下面五条, 条件与结论都要完整: **引理 2.1**, **定理 2.2** 的正反两半, **定义 2.3**, **命题 2.4**, **定理 2.6**.

> 自测 15 分钟. 核对: 本页顶部引用库.
