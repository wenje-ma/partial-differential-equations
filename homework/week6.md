# week6

第 II 章 §3–§4, 极值原理, 最大模估计, 导数估计与 Harnack. 这一周是第 II 章最"考试化"的部分, 结论密集但证明都短.

> **定理 3.1 (弱极值原理)**
>
> 设 $\Omega$ 有界, $u\in C^2(\Omega)\cap C(\overline\Omega)$. (1) 若 $\Delta u\ge0$, 则 $\max_{\overline\Omega}u=\max_{\partial\Omega}u$; (2) 若 $\Delta u\le0$, 则 $\min_{\overline\Omega}u=\min_{\partial\Omega}u$; (3) 若 $\Delta u=0$, 则对任意 $x\in\Omega$ 有 $\min_{\partial\Omega}u\le u(x)\le\max_{\partial\Omega}u$.

> **定理 3.2 (Dirichlet 问题的唯一性)**
>
> 设 $\Omega$ 有界, 则 $\Delta u=f$ 于 $\Omega$, $u=g$ 于 $\partial\Omega$ 的问题在 $C^2(\Omega)\cap C(\overline\Omega)$ 中至多有一个解.

> **定理 3.3 (最大模估计)**
>
> 设 $\Omega$ 有界, $d=\operatorname{diam}\Omega$. 若 $u\in C^2(\Omega)\cap C(\overline\Omega)$ 满足 $\Delta u=f$ 于 $\Omega$, $u=g$ 于 $\partial\Omega$, 则 $\sup_\Omega|u|\le\sup_{\partial\Omega}|g|+\frac{d^2}{2n}\sup_\Omega|f|$.

> **推论 3.4 (连续依赖性)**
>
> 在与**定理 3.3**相同的区域假设下, $\sup_\Omega|u_1-u_2|\le\sup_{\partial\Omega}|g_1-g_2|+\frac{d^2}{2n}\sup_\Omega|f_1-f_2|$.

> **定理 4.1 (内部一阶导数估计)**
>
> 设 $u$ 在 $\Omega$ 内调和, $B_R(x)\subset\Omega$, 则 $|D_iu(x)|\le\frac{n}{R}\max_{B_R(x)}|u|$, $i=1,\dots,n$.

> **定理 4.3 (有界调和函数的 Liouville 定理)**
>
> 若 $u$ 在 $\mathbb R^n$ 内调和且有界, 则 $u$ 必为常数.

> **引理 4.5 (球上的局部 Harnack 不等式)**
>
> 设 $u>0$ 在 $\Omega$ 内调和, $B_{4r}(z)\subset\Omega$, 则对任意 $x,y\in B_r(z)$ 有 $u(x)\le3^nu(y)$.

> **定理 4.6 (Harnack 不等式)**
>
> 设 $\Omega$ 是区域, $K\subset\Omega$ 是非空紧集, 则存在只依赖于 $\Omega$ 与 $K$ 的常数 $C$, 使得对每个在 $\Omega$ 内非负调和的 $u$ 都有 $\sup_Ku\le C\inf_Ku$.

> **定理 4.9 (非负调和函数的梯度估计)**
>
> 设 $u>0$ 在 $\Omega$ 内调和, $B_R(x)\subset\Omega$, 则 $|\nabla u(x)|\le\frac{n}{R}u(x)$.

> **定理 4.10 (单侧有界的 Liouville 定理)**
>
> 若 $u$ 在 $\mathbb R^n$ 内调和且有下界 (或有上界), 则 $u$ 为常数.

## 习题 6.1 (弱极值原理: 为什么要加 $\varepsilon|x|^2$)

(1) 按**定理 3.1** (1) 的证明, 对任意 $\varepsilon>0$ 令 $u_\varepsilon=u+\varepsilon|x|^2$, 算 $\Delta u_\varepsilon$, 说明它严格为正;
(2) 若 $u_\varepsilon$ 在内点 $x_0$ 取最大值, 写出 $\nabla u_\varepsilon(x_0)=0$ 与 $D^2u_\varepsilon(x_0)$ 半负定, 由此说明 $\Delta u_\varepsilon(x_0)\le0$ 与 (1) 矛盾;
(3) 取 $R=\max_{\overline\Omega}|x|$, 由 $\max_\Omega u\le\max_\Omega u_\varepsilon=\max_{\partial\Omega}(u+\varepsilon|x|^2)\le\max_{\partial\Omega}u+\varepsilon R^2$ 令 $\varepsilon\to0^+$, 得 $\max_\Omega u\le\max_{\partial\Omega}u$;
(4) 回答: 只假设 $\Delta u\ge0$ 而不加强为严格正, 上界还能不能直接得到, 为什么必须引入这个 $\varepsilon$ 项.

> 自测 30 分钟. 核对: 附录 A §3.1.

## 习题 6.2 (唯一性与稳定性)

(1) 用**定理 3.1** 证明**定理 3.2**: 设 $u_1,u_2$ 是两个解, $w=u_1-u_2$, 说明 $\Delta w=0$ 且 $w|_{\partial\Omega}=0$, 于是 $0\le w\le0$;
(2) 推出 $f\equiv0$, $g\equiv0$ 时唯一解是 $u\equiv0$;
(3) 用**推论 3.4** 说明: 若 $f_k\rightrightarrows f$ 于 $\Omega$, $g_k\rightrightarrows g$ 于 $\partial\Omega$, 则相应解 $u_k\rightrightarrows u$, 并写出需要的两个一致收敛前提.

> 自测 20 分钟. 核对: 附录 A §3.2–§3.3.

## 习题 6.3 (最大模估计的常数不最优)

取 $n=2$, $\Omega=B_1(0)$, $\Delta u=1$, $u|_{\partial\Omega}=0$.

(1) 由**定理 3.3** 写出上界 ($d=\operatorname{diam}\Omega=2$);
(2) 求出真解 (试 $u=\frac{|x|^2-1}{4}$), 算出 $\sup_\Omega|u|$ 的实际值;
(3) 比较 (1)(2), 说明"常数并非最优"具体指什么, 并指出证明中二次比较函数 $w=\Phi+\frac{F}{2n}(d^2-|x-\hat x|^2)-u$ 的作用 (为何引入 $\hat x$);
(4) 把边界数据改为 $u|_{\partial\Omega}=1$, 写出解并验证它与 (1) 的估计相容.

> 自测 25 分钟. 核对: 附录 A §3.3.

## 习题 6.4 (从引理 4.5 到定理 4.6)

(1) 按**引理 4.5** 的证明, 说明 $q\in B_r(x)$ 时 $|q-y|<3r$, 从而 $B_r(x)\subset B_{3r}(y)\subset B_{4r}(z)$;
(2) 由此 $u(x)\le3^nu(y)$, 说明常数为什么与 $u$ 无关, 且在平移与缩放下不变;
(3) 若 $K$ 被 $N$ 个半径 $r$ 的球覆盖且任意两点在同一球内, 沿球链把 $u(x)\le3^nu(y)$ 连乘 $N$ 次, 说明**定理 4.6** 中 $C=3^{nN}$ 的来源;
(4) 回答: 为什么不能对所有紧集共用同一个常数 (提示: 常数依赖 $K$ 离边界的距离与链长).

> 自测 30 分钟. 核对: 附录 A §4.3–§4.4.

## 习题 6.5 (导数估计, Liouville 与反例)

(1) 由**定理 4.1** 出发, 写出
$$
D_iu(x)=\frac{1}{\alpha_nR^n}\int_{B_R(x)}D_iu\,\mathrm dy=\frac{1}{\alpha_nR^n}\int_{\partial B_R(x)}u\nu_i\,\mathrm dS,
$$
说明这一步用了球体平均值与散度定理, 再由 $|\nu_i|\le1$ 与 $\omega_n=n\alpha_n$ 得估计;
(2) 令 $R\to\infty$ 证明**定理 4.3**;
(3) 由**定理 4.9** 证明**定理 4.10**: 若 $u>m$, 令 $v=u-m>0$, 得 $|\nabla u(x)|\le\frac{n}{R}v(x)$, 令 $R\to\infty$;
(4) 给两个反例说明条件不可去: $u(x)=x_1$ 在 $\mathbb R^n$ 内调和但无界; 一个在 $\mathbb R^n$ 内有上界却非常数的调和函数为何不存在.

> 自测 30 分钟. 核对: 附录 A §4.1–§4.2, §4.6.
