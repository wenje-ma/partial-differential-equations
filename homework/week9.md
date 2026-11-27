# week9

第 III 章 §1–§2, 热传导方程的定解问题与分离变量法. 前三章的 Cauchy 问题在抛物型这里换成初边值问题, 复习的重点从"通解"换成"特征值问题加展开".

## 习题 9.1 (定解问题的提法)

(1) 写出柱形区域 $Q_T=\Omega\times(0,T]$ 与抛物边界 $\partial_pQ_T$ 的定义, 说明为什么初始条件只加在 $t=0$ 那一层, 而边界条件加在 $\partial\Omega\times(0,T]$;
(2) 写出热方程的三类边界条件, 并说明 Neumann 与 Robin 中系数的符号约定;
(3) 说明 Tikhonov 反例讲的是什么: $u_t-a^2u_{xx}=0$ 于 $\mathbb R\times(0,T]$, $u(x,0)=0$, 存在非零解, 于是无增长限制时唯一性失效;
(4) 据此回答: 热方程定解问题要唯一, 除了初值与边界值, 还必须加什么类型的条件 (给出两种常见的).

> 自测 25 分钟. 核对: 第 III 章 p19–24 (Tikhonov 反例), p25–30 (Fourier 方法).

## 习题 9.2 (齐次 Dirichlet: 完整分离变量)

$$
u_t=a^2u_{xx},\quad 0\lt x\lt L,\ t\gt0;\qquad u(0,t)=u(L,t)=0;\qquad u(x,0)=\varphi(x).
$$

(1) 设 $u=X(x)T(t)$, 代入得 $\frac{T'}{a^2T}=\frac{X''}{X}=-\lambda$, 说明 $\lambda$ 为什么必须是实数且为正;
(2) 解 $X''+\lambda X=0$, $X(0)=X(L)=0$, 得 $\lambda_n=\left(\frac{n\pi}{L}\right)^2$, $X_n=\sin\frac{n\pi x}{L}$;
(3) 写出 $T_n(t)$ 与叠加解 $u=\sum_{n\ge1}A_n\sin\frac{n\pi x}{L}e^{-a^2\lambda_nt}$;
(4) 由 $u(x,0)=\varphi(x)$ 定 $A_n=\frac{2}{L}\int_0^L\varphi(x)\sin\frac{n\pi x}{L}\,\mathrm dx$, 并说明这一步为什么是 $\sin$ 系的正交展开;
(5) 取 $\varphi(x)=1$, $L=\pi$, $a=1$, 算出 $A_n$ 并写出解, 说明 $t\to\infty$ 时它按 $e^{-t}$ 衰减.

> 自测 40 分钟. 核对: 第 III 章 p38–45, p104–112 (情形 (1)).

## 习题 9.3 (九种特征值问题)

讲义把边界条件组合成九种情形. 只要求做三种, 但要说清另六种的结构.

(1) $X(0)=X(L)=0$: 写出 $\lambda_n$ 与 $X_n$;
(2) $X'(0)=X'(L)=0$: 写出 $\lambda_n$ 与 $X_n$, 指出 $n=0$ 这一常值模态为什么必须保留;
(3) $X(0)=0$, $X'(L)+\sigma_2X(L)=0$: 写出超越方程 $\tan(\mu L)=-\frac{\mu}{\sigma_2}$ 与 $X_n=\sin(\mu_nx)$, 说明 $\mu_n$ 只能数值求;
(4) 剩下的周期型与第三类型共六种, 各用一句话说明它们的 $X_n$ 是什么形状, 并说明为什么两端第三类一般没有显式特征值;
(5) 回答: 九种情形里哪些能保证 $\lambda_n\to\infty$ 且 $X_n$ 完备 (展开的合法性靠什么).

> 自测 40 分钟. 核对: 第 III 章 p104–173.

## 习题 9.4 (非齐次方程, 齐次边界)

$$
u_t-a^2u_{xx}=f(x,t),\qquad u(0,t)=u(L,t)=0,\qquad u(x,0)=\varphi(x).
$$

(1) 把 $f$ 按 $X_n$ 展开 $f=\sum f_n(t)\sin\frac{n\pi x}{L}$, 写出 $f_n(t)$ 的积分式;
(2) 设 $u=\sum T_n(t)\sin\frac{n\pi x}{L}$, 代入得 $T_n'+a^2\lambda_nT_n=f_n(t)$, $T_n(0)=\varphi_n$;
(3) 用常数变易法解出 $T_n(t)=e^{-a^2\lambda_nt}\varphi_n+\int_0^te^{-a^2\lambda_n(t-s)}f_n(s)\,\mathrm ds$;
(4) 取 $f(x,t)=\sin\frac{\pi x}{L}$ (不依赖 $t$), 算出 $T_1(t)$ 的显式并说明 $t\to\infty$ 时的稳态.

> 自测 30 分钟. 核对: 第 III 章 p181–190.

## 习题 9.5 (非齐次边界: 齐次化)

$$
u_t-a^2u_{xx}=0,\qquad u(0,t)=g_1(t),\quad u(L,t)=g_2(t),\qquad u(x,0)=\varphi(x).
$$

(1) 取 $w(x,t)=g_1(t)+\frac{x}{L}\left(g_2(t)-g_1(t)\right)$, 验证 $w$ 满足同样的边界条件;
(2) 令 $v=u-w$, 写出 $v$ 满足的方程 (右端出现 $-w_t+a^2w_{xx}$ 的具体表达式) 与齐次边界条件;
(3) 说明 $w$ 在 $g_1,g_2$ 与 $t$ 无关时退化为常值函数, 这时 $v$ 的方程少一项;
(4) 一句话说明"先齐次化边界, 再分离变量"这个顺序为什么不能反过来.

> 自测 30 分钟. 核对: 第 III 章 p191–196.

## 习题 9.6 (带阻尼项与圆域 Laplace)

(1) 对 $u_t-a^2u_{xx}+b^2u=0$ 于 $[0,L]$ 齐次 Dirichlet 边值, 写出 $T_n'+ (a^2\lambda_n+b^2)T_n=0$ 与解, 说明 $b$ 的作用是加速衰减;
(2) 对 Schrödinger 型 $iu_t+u_{xx}=0$ 同样做分离变量, 说明 $T_n=e^{i\lambda_nt}$ 的模不变;
(3) 圆域: $\Delta u=0$ 于 $r\lt a$, $u(a,\theta)=f(\theta)$, 用极坐标分离变量得 $R_n=r^n$, $\Theta_n=\cos n\theta$, $\sin n\theta$, 写出 $u=\frac{a_0}{2}+\sum_{n\ge1}\left(\frac{r}{a}\right)^n\left(a_n\cos n\theta+b_n\sin n\theta\right)$;
(4) 取 $f(\theta)=\cos2\theta$, $a=1$, 写出解并验证 $\Delta u=0$ 与边界值.

> 自测 35 分钟. 核对: 第 III 章 p197–205, p212–241.
