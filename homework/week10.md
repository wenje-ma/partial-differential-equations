# week10

第 III 章 §3, Fourier 变换与初值问题. 这一节闭卷主要考两件事: 会不会算变换, 会不会把变换解写回卷积.

## 习题 10.1 (变换的定义与两个基本例)

记 $\mathcal F[f](\xi)=\int_{\mathbb R^n}f(x)e^{-ix\cdot\xi}\,\mathrm dx$, 逆变换为 $\frac{1}{(2\pi)^n}\int_{\mathbb R^n}\hat f(\xi)e^{ix\cdot\xi}\,\mathrm d\xi$.

(1) 算 $\mathcal F[\mathbf 1_{[-A,A]}](\xi)$, 得 $\frac{2\sin(A\xi)}{\xi}$, 并说明 $\xi=0$ 时的取值;
(2) 算 $\mathcal F[e^{-x}\mathbf 1_{(0,\infty)}](\xi)=\frac{1}{1+i\xi}$, 说明它的模方 $\frac{1}{1+\xi^2}$ 与 Cauchy 分布密度只差常数;
(3) 说明 $\mathcal F[\mathbf 1_{[0,\infty)}]$ 在通常意义下为什么不存在, 而 $\mathcal F[\mathbf 1_{[-A,A]}]$ 可以 (提示: 平方可积性);
(4) 对 (1) 的结果用逆变换公式算回去, 得 $\mathbf 1_{[-A,A]}$, 即矩形窗与 sinc 互为变换.

> 自测 30 分钟. 核对: 第 III 章 §3 p303–320.

## 习题 10.2 (Gauss 函数)

(1) 配方把 $e^{-Ax^2-ix\xi}$ 写成 $e^{-\xi^2/(4A)}\cdot e^{-A\left(x+\frac{i\xi}{2A}\right)^2}$, 并说明沿实轴平移后 $\int e^{-A(x+ic)^2}\,\mathrm dx=\sqrt{\pi/A}$;
(2) 得 $\mathcal F[e^{-A|x|^2}](\xi)=\left(\frac{\pi}{A}\right)^{n/2}e^{-|\xi|^2/(4A)}$, 对 $n=1$ 与 $n=3$ 分别核对常数;
(3) 取 $A=\frac{1}{4a^2t}$, 说明热核 $g$ 的变换是 $e^{-a^2|\xi|^2t}$;
(4) 说明 $A\to0^+$ 时形式上趋于 $\delta$ 函数, 从而 $\int_{\mathbb R^n}g\,\mathrm dx=1$ 可由 $\xi=0$ 处读出.

> 自测 30 分钟. 核对: 第 III 章 §3 (Gauss 函数例).

## 习题 10.3 (三条性质的证明)

(1) 线性: 说明 $\mathcal F$ 把函数线性组合送到变换的线性组合;
(2) 伸缩: 对 $c>0$, 令 $y=cx$, 证明 $\mathcal F[f(cx)](\xi)=\frac{1}{c}\mathcal F[f]\left(\frac{\xi}{c}\right)$;
(3) 乘子: 对 $f$ 衰减足够快, 分部积分证明 $\mathcal F[xf(x)](\xi)=i\frac{\mathrm d}{\mathrm d\xi}\mathcal F[f](\xi)$;
(4) 用 (2)(3) 说明"对 $x$ 求导变成乘 $-|\xi|^2$", 并指出这是热方程能用变换解的关键.

> 自测 30 分钟. 核对: 第 III 章 §3 p303–339.

## 习题 10.4 (热方程的初值问题)

$$
u_t=a^2u_{xx},\quad x\in\mathbb R,\ t>0;\qquad u(x,0)=\varphi(x).
$$

(1) 对方程关于 $x$ 作变换, 得 $\hat u_t=-a^2\xi^2\hat u$, 解出 $\hat u(\xi,t)=\hat\varphi(\xi)e^{-a^2\xi^2t}$;
(2) 把 $e^{-a^2\xi^2t}$ 看成热核的变换, 用卷积定理写回 $u(x,t)=\int_{\mathbb R}g(x-y,t)\varphi(y)\,\mathrm dy$, 其中 $g(x,t)=\frac{1}{2a\sqrt{\pi t}}e^{-x^2/(4a^2t)}$;
(3) 取 $\varphi=\mathbf 1_{[-1,1]}$, 把积分算成 $\frac12\left[\mathrm{erf}\frac{x+1}{2a\sqrt t}-\mathrm{erf}\frac{x-1}{2a\sqrt t}\right]$, 其中 $\mathrm{erf}(z)=\frac{2}{\sqrt\pi}\int_0^ze^{-s^2}\,\mathrm ds$;
(4) 对非齐次 $u_t=a^2u_{xx}+f(x,t)$, 写出 $u=g*\varphi+\int_0^tg(\cdot,t-s)*f(\cdot,s)\,\mathrm ds$ 这一项的来源;
(5) 说明 $\varphi$ 有界时 $u$ 在 $t>0$ 自动光滑, 并解释"热方程的时间方向不可逆"在核上如何体现.

> 自测 40 分钟. 核对: 第 III 章 §3 p340–357.

## 习题 10.5 (半平面的 Laplace 方程)

$$
u_{xx}+u_{yy}=0,\quad x\in\mathbb R,\ y>0;\qquad u(x,0)=g(x).
$$

(1) 关于 $x$ 作变换, 得 $\hat u_{yy}=\xi^2\hat u$;
(2) 由 $y\to\infty$ 时有界 (或趋于零) 舍去 $e^{|\xi|y}$ 分支, 得 $\hat u(\xi,y)=\hat g(\xi)e^{-|\xi|y}$;
(3) 把 $e^{-|\xi|y}$ 写成 $\mathcal F\left[\frac{y}{\pi(x^2+y^2)}\right]$, 用卷积写回 $u(x,y)=\frac{y}{\pi}\int_{\mathbb R}\frac{g(t)}{(x-t)^2+y^2}\,\mathrm dt$;
(4) 与附录 A 中半空间的 Poisson 核 $\frac{2x_n}{\omega_n|x-y|^n}$ 在 $n=2$ 时的形式对照, 说明两处为什么一致;
(5) 取 $g=\mathbf 1_{[0,\infty)}$, 算出 $u=\frac{1}{\pi}\left(\frac{\pi}{2}+\arctan\frac{x}{y}\right)$ 并与第 8 周的结果核对.

> 自测 35 分钟. 核对: 第 III 章 §3 (半平面 Laplace), 附录 A 例 7.3.

## 习题 10.6 (解的验证与半直线)

(1) 把 $(x,t)\to(x_0,0^+)$ 的极限拆成近处与远处: 近处 $|y-x_0|\le\delta$ 上用 $\varphi$ 的连续性, 远处用 $g$ 的衰减, 说明 $\lim u=\varphi(x_0)$;
(2) 说明若 $|\varphi(x)|\le Me^{Ax^2}$, 卷积在 $0\lt t\lt\frac{1}{4Aa^2}$ 内收敛, 由此解释初值增长越快, 解的存在时间越短;
(3) 半直线 $x>0$, $u(0,t)=0$, $u(x,0)=\varphi(x)$: 用奇延拓 (奇函数在 $y>0$ 取 $\varphi$, 在 $y\lt0$ 取 $-\varphi(-y)$), 写出 $u=\int_0^\infty\left[g(x-y,t)-g(x+y,t)\right]\varphi(y)\,\mathrm dy$, 并验证 $u(0,t)=0$;
(4) 把边界条件改为 $u(0,t)=h(t)$ 且 $h(0)=0$, 说明此时该用偶延拓还是其他构造, 并写出对应的解的积分式.

> 自测 40 分钟. 核对: 第 III 章 §3 (解的验证, 半空间问题).
