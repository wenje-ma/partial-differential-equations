# week9

> **定理 4.4.1 (初边值问题的唯一性和稳定性)**
> 
> 初边值问题 (4.4.1) 的解在 $C^{2}\left(\overline{\Omega}\times\left[0,+\infty\right)\right)$ 中是唯一的, 且在以下意义下稳定: 给定 $T>0$, 对任意 $\varepsilon>0$, 存在 $\delta=\delta\left(\varepsilon,T\right)>0$, 使得当
> $\int_{\Omega}\left(\varphi^{2}\left(x\right)+\psi^{2}\left(x\right)+a^{2}\left|D\varphi\left(x\right)\right|^{2}\right)\mathrm{d}x<\delta^{2}$, $\int_0^{T}\int_{\Omega}f^{2}\left(x,t\right)\mathrm{d}x\mathrm{d}t<\delta^{2}$
> 时, 对任意 $t\in\left[0,T\right]$ 有 $\int_{\Omega}\left(u^{2}\left(x,t\right)+u_t^{2}\left(x,t\right)+a^{2}\left|\nabla{u}\left(x,t\right)\right|^{2}\right)\mathrm{d}x<\varepsilon^{2}$.

> **定理 4.4.2 (Cauchy 问题的唯一性和稳定性)**
> 
> Cauchy 问题 (4.4.5) 的解在 $C^{2}\left(\mathbb{R}^{n}\times\left[0,+\infty\right)\right)$ 中是唯一的, 且在以下意义下稳定: 给定 $T>0$, 对任意 $\varepsilon>0$, 存在 $\delta=\delta\left(\varepsilon,T\right)>0$, 使得当
> $\int_{\mathbb{R}^{n}}\left(\varphi^{2}\left(x\right)+\psi^{2}\left(x\right)+a^{2}\left|D\varphi\left(x\right)\right|^{2}\right)\mathrm{d}x<\delta^{2}$, $\int_0^{T}\mathrm{d}t\int_{\Omega_t}f^{2}\left(x,t\right)\mathrm{d}x<\delta^{2}$
> 时, 对任意 $t\in\left[0,T\right]$ 有 $\int_{\Omega_t}\left(u^{2}\left(x,t\right)+u_t^{2}\left(x,t\right)+a^{2}\left|\nabla{u}\left(x,t\right)\right|^{2}\right)\mathrm{d}x<\varepsilon^{2}$.

> **公式 (4.4.3) (能量不等式)**
> 
> $E\left(t\right)\le{E}\left(0\right)\mathrm{e}^{t}+\int_0^{t}\mathrm{e}^{t-s}\int_{\Omega}f^{2}\left(x,s\right)\,\mathrm{d}x\,\mathrm{d}s$, 其中 $E\left(t\right)=\frac{1}{2}\int_{\Omega}\left(u_t^{2}+a^{2}\left|\nabla{u}\right|^{2}\right)\mathrm{d}x$, $E\left(0\right)=\frac{1}{2}\int_{\Omega}\left(\psi^{2}+a^{2}\left|D\varphi\right|^{2}\right)\mathrm{d}x$.

> **公式 (4.4.4) (能量不等式)**
> 
> $E_0\left(t\right)\le\left(E_0\left(0\right)+tE\left(0\right)\right)\mathrm{e}^{t}+\int_0^{t}\mathrm{d}s\int_{\Omega}\left(t-s\right)\mathrm{e}^{t-s}f^{2}\left(x,s\right)\,\mathrm{d}x$, 其中 $E_0\left(t\right)=\int_{\Omega}u^{2}\left(x,t\right)\,\mathrm{d}x$, $E_0\left(0\right)=\int_{\Omega}\varphi^{2}\left(x\right)\,\mathrm{d}x$.

> **公式 (4.4.6) (Cauchy 问题的能量不等式)**
> 
> $E\left(t\right)\le{E}\left(0\right)\mathrm{e}^{t}+\int_0^{t}\mathrm{d}s\int_{\Omega_s}\mathrm{e}^{t-s}f^{2}\left(x,s\right)\,\mathrm{d}x$, 其中 $\Omega_s=\left\{\left|x\right|\le{R}-as\right\}$, $E\left(t\right)=\frac{1}{2}\int_{\Omega_t}\left(u_t^{2}+a^{2}\left|\nabla{u}\right|^{2}\right)\mathrm{d}x$.

> **公式 (4.4.7) (Cauchy 问题的能量不等式)**
> 
> $E_0\left(t\right)\le\left(E_0\left(0\right)+tE\left(0\right)\right)\mathrm{e}^{t}+\int_0^{t}\mathrm{d}s\int_{\Omega_s}\left(t-s\right)\mathrm{e}^{t-s}f^{2}\left(x,s\right)\,\mathrm{d}x$, 其中 $E_0\left(t\right)=\int_{\Omega_t}u^{2}\left(x,t\right)\,\mathrm{d}x$.

## 习题 4.1 (带耗散项的波动方程的能量单调性)

设 $u$ 是带一阶耗散项的波动方程初边值问题

$$
\begin{cases}u_{tt}-a^{2}\Delta{u}+\alpha{u}_t=0,&x\in\Omega,t>0,\\u\left(x,0\right)=\varphi\left(x\right),\quad{u}_t\left(x,0\right)=\psi\left(x\right),&x\in\overline{\Omega},\\u\left(x,t\right)=0,&x\in\partial\Omega,t\ge0\end{cases}
$$

的解, 其中 $\Omega$ 是 $\mathbb{R}^{n}$ 中的有界光滑区域, $\alpha$ 是正常数. 证明: 其能量积分

$$
E\left(t\right)=\frac{1}{2}\int_{\Omega}\left(u_t^{2}+a^{2}\left|\nabla{u}\right|^{2}\right)\mathrm{d}x,\qquad{t}\ge0
$$

单调不增. 进而证明: 该问题的解唯一.

### 解答 4.1

第一步: 能量对时间求导. 设 $u$ 充分光滑 (题设 $u$ 是解, 故 $u_{tt}$ 与 $\Delta{u}$ 存在且可积), 在积分号下求导,

$$
\frac{\mathrm{d}E\left(t\right)}{\mathrm{d}t}=\int_{\Omega}\left(u_tu_{tt}+a^{2}\nabla{u}\cdot\nabla{u}_t\right)\mathrm{d}x.\tag{A}
$$

第二步: 对第二项用 Green 公式 (散度定理),

$$
\int_{\Omega}\nabla{u}\cdot\nabla{u}_t\,\mathrm{d}x=-\int_{\Omega}u_t\Delta{u}\,\mathrm{d}x+\int_{\partial\Omega}u_t\frac{\partial{u}}{\partial\nu}\,\mathrm{d}S.\tag{B}
$$

第三步: 边界项消失. 由 $u\left(x,t\right)=0$ 于 $\partial\Omega$ 对一切 $t\ge0$ 成立, 关于 $t$ 求导得 $u_t\left(x,t\right)=0$ 于 $\partial\Omega$, 故 (B) 中边界积分为零.

第四步: 代入方程. 由方程得 $u_{tt}-a^{2}\Delta{u}=-\alpha{u}_t$. 把 (B) 代入 (A) 并用此式,

$$
\frac{\mathrm{d}E\left(t\right)}{\mathrm{d}t}=\int_{\Omega}u_t\left(u_{tt}-a^{2}\Delta{u}\right)\mathrm{d}x=-\alpha\int_{\Omega}u_t^{2}\,\mathrm{d}x\le0.\tag{C}
$$

第五步: 结论 (单调性). 由 $\alpha>0$ 与 (C), $E$ 在 $\left[0,+\infty\right)$ 上单调不增.

第六步: 唯一性. 设 $u_1,u_2$ 是同一问题的两个解, 令 $w=u_1-u_2$. 由线性, $w$ 满足

$$
w_{tt}-a^{2}\Delta{w}+\alpha{w}_t=0,\quad{w}\left(x,0\right)=0,\quad{w}_t\left(x,0\right)=0,\quad{w}\left(x,t\right)=0\;\text{于}\;\partial\Omega.\tag{D}
$$

第七步: 对 $w$ 的能量 $E_w\left(t\right)=\frac{1}{2}\int_{\Omega}\left(w_t^{2}+a^{2}\left|\nabla{w}\right|^{2}\right)\mathrm{d}x$ 用 (C): $\frac{\mathrm{d}E_w}{\mathrm{d}t}=-\alpha\int_{\Omega}w_t^{2}\mathrm{d}x\le0$. 又 $E_w\left(0\right)=0$ (由零初值), 故

$$
0\le{E}_w\left(t\right)\le{E}_w\left(0\right)=0,\qquad\text{即}\;E_w\left(t\right)\equiv0.\tag{E}
$$

第八步: 由 (E) 得 $\nabla{w}\left(\cdot,t\right)=0$, $w_t\left(\cdot,t\right)=0$ 于 $\Omega$, 对一切 $t\ge0$. 前者说明 $w\left(\cdot,t\right)$ 在连通的 $\Omega$ 上为常数; 后者说明该常数不依赖于 $t$; 而 $w=0$ 于 $\partial\Omega$ 给出该常数为零. 故 $w\equiv0$, 即 $u_1=u_2$, 唯一性成立.

## 习题 4.2 (Cauchy 问题的唯一性和稳定性)

仿照定理 4.4.1 的证明, 试证明: 定理 4.4.2.

### 解答 4.2

第一步: 回忆定理 4.4.1 的证明骨架. 定理 4.4.1 的证明由三步构成:

(i) 用**公式 (4.4.3) (能量不等式)** 与**公式 (4.4.4) (能量不等式)** 把 $E\left(t\right)$ 与 $E_0\left(t\right)$ 的上界表成"初值能量 + 源项平方的积分";

(ii) 唯一性时两个解之差满足零初值, 零边值与齐次方程, 从而右端为零, 得 $E_0\left(t\right)=0$;

(iii) 稳定性时对解之差用同一条能量不等式, 令小参数 $\delta$ 使右端小于 $\varepsilon^{2}$.

第二步: 指出 Cauchy 情形下对应的三条事实已具备. 定理 4.4.2 讨论的 Cauchy 问题

$$
\begin{cases}u_{tt}-a^{2}\Delta{u}=f\left(x,t\right),&x\in\mathbb{R}^{n},t>0,\\u\left(x,0\right)=\varphi\left(x\right),\quad{u}_t\left(x,0\right)=\psi\left(x\right),&x\in\mathbb{R}^{n}\end{cases}\tag{A}
$$

在无界区域上积分可能发散, 故在 $\Omega_t=\left\{\left|x\right|\le{R}-at\right\}$ 上取能量

$$
E\left(t\right)=\frac{1}{2}\int_{\Omega_t}\left(u_t^{2}+a^{2}\left|\nabla{u}\right|^{2}\right)\mathrm{d}x,\qquad{E}_0\left(t\right)=\int_{\Omega_t}u^{2}\,\mathrm{d}x.\tag{B}
$$

教材中已证明与 (i) 完全平行的两条估计, 即**公式 (4.4.6) (Cauchy 问题的能量不等式)** 与**公式 (4.4.7) (Cauchy 问题的能量不等式)**. 以下照 (ii)(iii) 完成.

第三步: 证唯一性. 设 $u_1,u_2$ 是 (A) 的两个 $C^{2}\left(\mathbb{R}^{n}\times\left[0,+\infty\right)\right)$ 解, $w=u_1-u_2$. 则 $w$ 满足

$$
w_{tt}-a^{2}\Delta{w}=0,\quad{w}\left(x,0\right)=0,\quad{w}_t\left(x,0\right)=0.\tag{C}
$$

第四步: 对 (C) 用**公式 (4.4.7) (Cauchy 问题的能量不等式)**. 此时 $f=0$, $E_w\left(0\right)=0$, $E_{0,w}\left(0\right)=0$, 故右端为零,

$$
0\le{E}_{0,w}\left(t\right)\le\left(0+t\cdot0\right)\mathrm{e}^{t}+0=0.\tag{D}
$$

第五步: 由 (D) 得 $w\left(\cdot,t\right)=0$ 于 $\Omega_t$, 即于球 $\left\{\left|x\right|\le{R}-at\right\}$. 由于 $R>0$ 任意, $t\in\left[0,T\right]$ 任意, 对每个固定的 $\left(x,t\right)\in\mathbb{R}^{n}\times\left[0,+\infty\right)$ 取 $R>\left|x\right|+at$ 即得 $w\left(x,t\right)=0$. 故 $w\equiv0$, 唯一性成立.

第六步: 合并能量不等式以备稳定性之用. 由**公式 (4.4.6)** 与**公式 (4.4.7)**, 对 $t\in\left[0,T\right]$,

$$
E\left(t\right)\le{E}\left(0\right)\mathrm{e}^{t}+\int_0^{t}\mathrm{e}^{t-s}F\left(s\right)\,\mathrm{d}s,\qquad{E}_0\left(t\right)\le\left(E_0\left(0\right)+tE\left(0\right)\right)\mathrm{e}^{t}+\int_0^{t}\left(t-s\right)\mathrm{e}^{t-s}F\left(s\right)\,\mathrm{d}s,
$$

其中 $F\left(s\right)=\int_{\Omega_s}f^{2}\left(x,s\right)\mathrm{d}x$. 两式相加并用 $\mathrm{e}^{t},\mathrm{e}^{t-s}\le\mathrm{e}^{T}$, $t\le{T}$,

$$
E_0\left(t\right)+E\left(t\right)\le\left(1+T\right)\mathrm{e}^{T}\left(E_0\left(0\right)+E\left(0\right)+\int_0^{T}F\left(s\right)\,\mathrm{d}s\right),\qquad{t}\in\left[0,T\right].\tag{E}
$$

第七步: 证稳定性. 设 $u_i$ 是数据 $\left(f_i,\varphi_i,\psi_i\right)$ 的解, $i=1,2$, $w=u_1-u_2$. 则 $w$ 满足 (A) 型的 Cauchy 问题, 其右端源项为 $f_1-f_2$, 初值为 $\varphi_1-\varphi_2$, $\psi_1-\psi_2$. 对 $w$ 用 (E) (把 $f$ 换成 $f_1-f_2$ 等),

$$
E_{0,w}\left(t\right)+E_w\left(t\right)\le\left(1+T\right)\mathrm{e}^{T}\left(E_{0,w}\left(0\right)+E_w\left(0\right)+\int_0^{T}\int_{\Omega_s}\left(f_1-f_2\right)^{2}\mathrm{d}x\,\mathrm{d}s\right).\tag{F}
$$

第八步: 取 $\delta=\frac{\varepsilon}{\sqrt{6\left(1+T\right)\mathrm{e}^{T}}}$. 当两组数据的差满足

$$
\int_{\mathbb{R}^{n}}\left(\left(\varphi_1-\varphi_2\right)^{2}+\left(\psi_1-\psi_2\right)^{2}+a^{2}\left|D\left(\varphi_1-\varphi_2\right)\right|^{2}\right)\mathrm{d}x<\delta^{2},\qquad\int_0^{T}\mathrm{d}t\int_{\Omega_t}\left(f_1-f_2\right)^{2}\mathrm{d}x<\delta^{2}
$$

时, 注意 $E_{0,w}\left(0\right)+E_w\left(0\right)=\frac{1}{2}\int_{\mathbb{R}^{n}}\left(\left(\varphi_1-\varphi_2\right)^{2}+\left(\psi_1-\psi_2\right)^{2}+a^{2}\left|D\left(\varphi_1-\varphi_2\right)\right|^{2}\right)\mathrm{d}x<\frac{\delta^{2}}{2}$, 故 (F) 的右端小于

$$
\left(1+T\right)\mathrm{e}^{T}\left(\frac{\delta^{2}}{2}+\delta^{2}\right)=3\left(1+T\right)\mathrm{e}^{T}\delta^{2}=\frac{\varepsilon^{2}}{2}.
$$

于是对任意 $t\in\left[0,T\right]$, 由 (B) 与 $E_0+E=\frac{1}{2}\int\left(u^{2}+u_t^{2}+a^{2}\left|\nabla{u}\right|^{2}\right)$, (F) 的左端给出

$$
\int_{\Omega_t}\left(w^{2}+w_t^{2}+a^{2}\left|\nabla{w}\right|^{2}\right)\mathrm{d}x=2\left(E_{0,w}\left(t\right)+E_w\left(t\right)\right)<\varepsilon^{2},
$$

即解在定理 4.4.2 所述的意义下稳定. 定理 4.4.2 得证.

## 习题 4.3 (一维 Cauchy 问题的能量估计)

设 $u\in{C}^{2}\left(\left(-\infty,+\infty\right)\times\left[0,+\infty\right)\right)$ 是 Cauchy 问题

$$
\begin{cases}u_{tt}-a^{2}u_{xx}=0,&-\infty<{}x<+\infty,t>0,\\u\left(x,0\right)=\varphi\left(x\right),\quad{u}_t\left(x,0\right)=\psi\left(x\right),&-\infty<{}x<+\infty\end{cases}
$$

的解, 其中 $a>0$ 是常数, $\varphi\left(x\right),\psi\left(x\right)\in{C}^{\infty}\left(-\infty,+\infty\right)$. 若 $x_1<{}x_2$, 证明: 如下能量估计成立

$$
\int_{x_1}^{x_2}\left(u_t^{2}\left(x,t\right)+a^{2}u_x^{2}\left(x,t\right)\right)\mathrm{d}x\le\int_{x_1-at}^{x_2+at}\left(\psi^{2}\left(x\right)+a^{2}\varphi'^{2}\left(x\right)\right)\mathrm{d}x,\qquad{t}>0.
$$

### 解答 4.3

第一步: 在随特征线移动的区间上定义能量. 取 $t$ 使得 $y_1+at<{}y_2-at$, 令

$$
E\left(t\right)=\int_{y_1+at}^{y_2-at}\left(u_t^{2}+a^{2}u_x^{2}\right)\mathrm{d}x,\tag{A}
$$

其中 $y_1=x_1$, $y_2=x_2$. 以下对 $E$ 关于 $t$ 求导.

第二步: 对积分限求导. 上限 $y_2-at$ 递减, 下限 $y_1+at$ 递增, 由变限积分求导公式,

$$
\frac{\mathrm{d}}{\mathrm{d}t}\int_{y_1+at}^{y_2-at}F\,\mathrm{d}x=-aF\left(y_2-at,t\right)-aF\left(y_1+at,t\right)+\int_{y_1+at}^{y_2-at}F_t\,\mathrm{d}x.\tag{B}
$$

第三步: 把被积函数的导数用方程化简. 对 $F=u_t^{2}+a^{2}u_x^{2}$,

$$
F_t=2u_tu_{tt}+2a^{2}u_xu_{xt}=2u_t\left(u_{tt}-a^{2}u_{xx}\right)+2a^{2}\left(u_tu_x\right)_x,\tag{C}
$$

这里把 $2a^{2}u_xu_{xt}$ 写成了 $2a^{2}\left(u_tu_x\right)_x-2a^{2}u_tu_{xx}$.

第四步: 用方程消去第一项. 由 $u_{tt}=a^{2}u_{xx}$, (C) 中第一个括号为零, 故

$$
\int_{y_1+at}^{y_2-at}F_t\,\mathrm{d}x=2a^{2}\left[u_tu_x\right]_{y_1+at}^{y_2-at}.\tag{D}
$$

第五步: 合并. 把 (D) 代入 (B),

$$
\frac{\mathrm{d}E}{\mathrm{d}t}=-\left.a\left(u_t^{2}+a^{2}u_x^{2}\right)\right|_{y_2-at}-\left.a\left(u_t^{2}+a^{2}u_x^{2}\right)\right|_{y_1+at}+2a^{2}\left.\left(u_tu_x\right)\right|_{y_2-at}-2a^{2}\left.\left(u_tu_x\right)\right|_{y_1+at}.\tag{E}
$$

第六步: 配方成完全平方. 把 (E) 按端点归并,

$$
\frac{\mathrm{d}E}{\mathrm{d}t}=-\left.a\left(u_t-au_x\right)^{2}\right|_{y_2-at}-\left.a\left(u_t+au_x\right)^{2}\right|_{y_1+at}\le0,\tag{F}
$$

这里用到 $-a\left(u_t^{2}+a^{2}u_x^{2}\right)+2a^{2}u_tu_x=-a\left(u_t-au_x\right)^{2}$ 与 $-a\left(u_t^{2}+a^{2}u_x^{2}\right)-2a^{2}u_tu_x=-a\left(u_t+au_x\right)^{2}$.

第七步: 得到单调性. 由 (F), $E$ 在使 (A) 有意义的 $t$ 上单调不增, 故

$$
E\left(t\right)\le{E}\left(0\right)=\int_{y_1}^{y_2}\left.\left(u_t^{2}+a^{2}u_x^{2}\right)\right|_{t=0}\mathrm{d}x=\int_{y_1}^{y_2}\left(\psi^{2}+a^{2}\varphi'^{2}\right)\mathrm{d}x.\tag{G}
$$

第八步: 把活动区间取成依赖区间. 在 (A) 中取 $y_1=x_1-at$, $y_2=x_2+at$, 则

$$
E\left(t\right)=\int_{x_1-at+at}^{x_2+at-at}\left(u_t^{2}+a^{2}u_x^{2}\right)\mathrm{d}x=\int_{x_1}^{x_2}\left(u_t^{2}+a^{2}u_x^{2}\right)\mathrm{d}x,\qquad{E}\left(0\right)=\int_{x_1-at}^{x_2+at}\left(\psi^{2}+a^{2}\varphi'^{2}\right)\mathrm{d}x.\tag{H}
$$

于是 (G) 恰好就是所要的估计

$$
\int_{x_1}^{x_2}\left(u_t^{2}+a^{2}u_x^{2}\right)\mathrm{d}x\le\int_{x_1-at}^{x_2+at}\left(\psi^{2}+a^{2}\varphi'^{2}\right)\mathrm{d}x,
$$
它在 $y_1+at<{}y_2-at$, 即 $x_1<{}x_2$ 时有效; 而这一条件对一切 $t>0$ 都成立 (题设 $x_1<{}x_2$), 故估计对一切 $t>0$ 成立.

第九步: 说明估计的含义: 区间 $\left[x_1-at,x_2+at\right]$ 正是 $\left(x_1,x_2\right)$ 上初值对时刻 $t$ 的影响范围 (依赖区间), 估计说明"时刻 $t$ 在 $\left(x_1,x_2\right)$ 上的能量不超过依赖区间内的初始能量".

## 习题 4.4 (Goursat 问题)

求解古尔萨 (Goursat) 问题

$$
\begin{cases}u_{tt}-a^{2}u_{xx}=0,&-\infty<{}x<+\infty,t>0,\\\left.u\right|_{x=at}=\varphi\left(t\right),\quad\left.{u}\right|_{x=-at}=\psi\left(t\right),&-\infty<{}t<+\infty,\end{cases}
$$

其中 $\varphi\left(0\right)=\psi\left(0\right)$.

### 解答 4.4

第一步: 写出一维波动方程的通解形式. 由 $u_{tt}-a^{2}u_{xx}=\left(\partial_t-a\partial_x\right)\left(\partial_t+a\partial_x\right)u=0$, 通解为

$$
u\left(x,t\right)=p\left(x-at\right)+q\left(x+at\right),\tag{A}
$$

其中 $p,q$ 是任意 $C^{2}$ 函数 (分别沿 $x-at=$ 常数 与 $x+at=$ 常数 为常数).

第二步: 利用一条特征线上的数据定出 $q$. 在 $x=at$ 上, $x-at=0$, $x+at=2at$, 故由 (A) 与题设

$$
p\left(0\right)+q\left(2at\right)=\varphi\left(t\right),\qquad{t}>0.
$$

令 $\xi=2at$ (则 $t=\frac{\xi}{2a}$), 得

$$
q\left(\xi\right)=\varphi\left(\frac{\xi}{2a}\right)-p\left(0\right),\qquad\xi>0.\tag{B}
$$

第三步: 利用另一条特征线上的数据定出 $p$. 在 $x=-at$ 上, $x-at=-2at$, $x+at=0$, 故

$$
p\left(-2at\right)+q\left(0\right)=\psi\left(t\right),\qquad{t}>0.
$$

令 $\eta=-2at<0$, 得

$$
p\left(\eta\right)=\psi\left(-\frac{\eta}{2a}\right)-q\left(0\right),\qquad\eta<0.\tag{C}
$$

第四步: 确定两个常数. 由 (B)(C) 在 $t=0$ 处给出 $p\left(0\right)+q\left(0\right)=\varphi\left(0\right)$ 与 $p\left(0\right)+q\left(0\right)=\psi\left(0\right)$, 这正是题设的相容性条件 $\varphi\left(0\right)=\psi\left(0\right)$. 记 $p\left(0\right)+q\left(0\right)=C_0$, 则 $C_0=\varphi\left(0\right)=\psi\left(0\right)$. 由于 (A) 只用到 $p,q$ 之和, 可重新分配常数, 不妨取

$$
p\left(0\right)=0,\qquad{q}\left(0\right)=C_0.\tag{D}
$$

第五步: 写出解. 由 (B) 与 (D), 对 $\xi>0$ 有 $q\left(\xi\right)=\varphi\left(\frac{\xi}{2a}\right)$ (在 $\xi\to0^{+}$ 处与 $q\left(0\right)=\varphi\left(0\right)$ 相容); 由 (C) 与 (D), 对 $\eta<0$ 有

$$
p\left(\eta\right)=\psi\left(-\frac{\eta}{2a}\right)-C_0=\psi\left(-\frac{\eta}{2a}\right)-\psi\left(0\right).
$$

于是对 $\left|x\right|<{}at$ 的点 ($x-at<0$, $x+at>0$, 两支都已确定), 由 (A)

$$
u\left(x,t\right)=p\left(x-at\right)+q\left(x+at\right)=\psi\left(-\frac{x-at}{2a}\right)-\psi\left(0\right)+\varphi\left(\frac{x+at}{2a}\right),
$$

即

$$
u\left(x,t\right)=\psi\left(\frac{at-x}{2a}\right)+\varphi\left(\frac{at+x}{2a}\right)-\psi\left(0\right),\qquad\left|x\right|<{}at.\tag{E}
$$

第六步: 验证特征线条件. 在 $x=at$ 上, 由 (E)

$$
u=\psi\left(0\right)+\varphi\left(t\right)-\psi\left(0\right)=\varphi\left(t\right);\tag{F}
$$

在 $x=-at$ 上,

$$
u=\psi\left(t\right)+\varphi\left(0\right)-\psi\left(0\right)=\psi\left(t\right),\tag{G}
$$

这里用了 $\varphi\left(0\right)=\psi\left(0\right)$.

第七步: 结论. 由 (A) 型通解构造出的 (E) 满足方程, 并满足两条特征线上的数据 ((F)(G)), 故

$$
u\left(x,t\right)=\psi\left(\frac{at-x}{2a}\right)+\varphi\left(\frac{at+x}{2a}\right)-\psi\left(0\right),\qquad\left|x\right|\le{at},t\ge0
$$

就是古尔萨问题的解. 说明: Goursat 问题的数据只给在两条特征线上, 解只在它们张成的三角形区域 $\left|x\right|\le{at}$ 中被确定.
