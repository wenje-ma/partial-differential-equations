# week12

> **定义 3.4.3 (Fourier 变换)**
> 
> 对 $f\in{L}^{1}\left(\mathbb{R}^{n}\right)$, 记 $\hat{f}\left(\xi\right)=\int_{\mathbb{R}^{n}}f\left(x\right)\mathrm{e}^{-\mathrm{i}\xi\cdot{x}}\,\mathrm{d}x$; 若 $\hat{f}\in{L}^{1}\left(\mathbb{R}^{n}\right)$, 则 $f\left(x\right)=\frac{1}{\left(2\pi\right)^{n}}\int_{\mathbb{R}^{n}}\hat{f}\left(\xi\right)\mathrm{e}^{\mathrm{i}\xi\cdot{x}}\,\mathrm{d}\xi$.

> **定理 4.2.6 (三维波动方程的 Poisson 公式)**
> 
> 若 $\varphi\in{C}^{2}\left(\mathbb{R}^{3}\right)$, $\psi\in{C}^{1}\left(\mathbb{R}^{3}\right)$, 则三维波动方程 Cauchy 问题 $u_{tt}-a^{2}\Delta{u}=0$, $u\left(x,0\right)=\varphi\left(x\right)$, $u_t\left(x,0\right)=\psi\left(x\right)$ 的解为
> $u\left(x,t\right)=\frac{1}{4\pi{a}^{2}}\left[\frac{\partial}{\partial{t}}\int_{S_{at}\left(x\right)}\frac{\varphi\left(y\right)}{t}\,\mathrm{d}S_y+\int_{S_{at}\left(x\right)}\frac{\psi\left(y\right)}{t}\,\mathrm{d}S_y\right]$, 即公式 (4.2.15), 其中 $S_{at}\left(x\right)=\left\{y\in\mathbb{R}^{3}:\left|y-x\right|=at\right\}$.

> **定理 6.2.3 (奇点可去性)**
> 
> 设 $u$ 在 $B_R\left(0\right)\setminus\left\{0\right\}$ 内调和, 且满足奇性条件
> $u\left(x\right)=\begin{cases}o\left(\log\left|x\right|\right),&n=2,\\o\left(\left|x\right|^{2-n}\right),&n\ge3,\end{cases}$ 当 $\left|x\right|\to0$ 时, 则 $u$ 在 $x=0$ 处的奇点可去, 即可以在 $x=0$ 处定义 $u$ 的值, 使得 $u\in{C}^{2}\left(B_R\right)$ 且在 $B_R\left(0\right)$ 上调和.

> **定理 6.2.4 (Böcher 定理)**
> 
> 设 $u$ 是 $B_1\left(0\right)\setminus\left\{0\right\}$ 内的正的调和函数, 则存在一个函数 $v$ 在 $B_1\left(0\right)$ 内调和与一个常数 $a\ge0$, 使得
> $u\left(x\right)=\begin{cases}v\left(x\right)+a\log\frac{1}{\left|x\right|},&n=2,\\v\left(x\right)+\frac{a}{\left|x\right|^{n-2}},&n\ge3,\end{cases}\qquad{x}\in{B}_1\left(0\right)\setminus\left\{0\right\}$.

## 习题 4.13 (退化系数的波动型方程的通解)

设 $h$ 是一个常数. 证明: 方程

$$
\frac{\partial}{\partial{x}}\left(\left(1-\frac{x}{h}\right)^{2}u_x\right)=\frac{1}{a^{2}}\left(1-\frac{x}{h}\right)^{2}u_{tt}
$$

的通解可以写成 $u\left(x,t\right)=\frac{F\left(x-at\right)+G\left(x+at\right)}{h-x}$, 其中 $F,G$ 是任意可微函数.

### 解答 4.13

第一步: 把方程化成不含量级因子的形式. 由 $\left(1-\frac{x}{h}\right)^{2}=\frac{\left(h-x\right)^{2}}{h^{2}}$, 方程两端同乘 $h^{2}$ 得等价形式

$$
\frac{\partial}{\partial{x}}\left(\left(h-x\right)^{2}u_x\right)=\frac{1}{a^{2}}\left(h-x\right)^{2}u_{tt},\tag{A}
$$

这里用到 $h\ne0$ 与 $h^{2}\ne0$.

第二步: 作未知函数替换. 令

$$
w\left(x,t\right):=\left(h-x\right)u\left(x,t\right),\qquad\text{即}\quad{u}\left(x,t\right)=\frac{w\left(x,t\right)}{h-x},\tag{B}
$$

在 $x\ne{h}$ 处这是可逆的替换.

第三步: 计算 (A) 的左端. 由 (B),

$$
u_x=\frac{w_x\left(h-x\right)+w}{\left(h-x\right)^{2}},\tag{C}
$$

故 $\left(h-x\right)^{2}u_x=w_x\left(h-x\right)+w$, 再对 $x$ 求导,

$$
\frac{\partial}{\partial{x}}\left(\left(h-x\right)^{2}u_x\right)=w_{xx}\left(h-x\right)-w_x+w_x=\left(h-x\right)w_{xx}.\tag{D}
$$

第四步: 计算 (A) 的右端. 由 (B), $u_{tt}=\frac{w_{tt}}{h-x}$, 故

$$
\frac{1}{a^{2}}\left(h-x\right)^{2}u_{tt}=\frac{1}{a^{2}}\left(h-x\right)w_{tt}.\tag{E}
$$

第五步: 比较 (D)(E). 把 (D)(E) 代入 (A) 得 $\left(h-x\right)w_{xx}=\frac{1}{a^{2}}\left(h-x\right)w_{tt}$, 两边约去非零因子 $h-x$,

$$
w_{tt}=a^{2}w_{xx}.\tag{F}
$$

于是原方程等价于 $w$ 的一维齐次波动方程.

第六步: 用 d'Alembert 公式写出 $w$ 的通解. 一维波动方程 (F) 的通解为 $w\left(x,t\right)=F\left(x-at\right)+G\left(x+at\right)$, 其中 $F,G$ 是任意二阶可微函数.

第七步: 还原为 $u$. 把 (B) 代回,

$$
u\left(x,t\right)=\frac{F\left(x-at\right)+G\left(x+at\right)}{h-x}.\tag{G}
$$

第八步: 反过来说明 (G) 对任意可微的 $F,G$ 都给出解. 设 $F,G$ 任意可微, 令 $w=F\left(x-at\right)+G\left(x+at\right)$, 则 $w$ 满足 (F); 由 (D)(E) 的推导 (这两步只用到 (B) 这个替换, 与 $w$ 的具体形式无关) 知 (A) 成立, 即 u 满足原方程. 于是 (G) 确为通解.

第九步: 说明解在 $x=h$ 处退化. 方程在 $x=h$ 处的主部系数 $\left(1-x/h\right)^{2}$ 为零, $x=h$ 是方程的退化点; 由 (G) 可见 $u$ 在 $x=h$ 处一般趋于无穷, 故通解只在 $x\ne{h}$ 的区间上有效.

## 习题 4.14 (五维波动方程解的一个表示)

证明: 若 $\psi\in{C}^{3}\left(\mathbb{R}^{5}\right)$, 令

$$
v\left(x,t\right)=\frac{3}{8\pi^{2}\left(at\right)^{4}}\int_{\left|y-x\right|=at}\psi\left(y\right)\,\mathrm{d}S_y,
$$

则 $u\left(x,t\right)=\left(\frac{1}{3}t^{2}\frac{\partial}{\partial{t}}+t\right)v\left(x,t\right)$ 是五维波动方程 Cauchy 问题

$$
\begin{cases}u_{tt}-a^{2}\Delta{u}=0,&x\in\mathbb{R}^{5},t>0,\\u\left(x,0\right)=0,u_t\left(x,0\right)=\psi\left(x\right),&x\in\mathbb{R}^{5}\end{cases}
$$

的解.

### 解答 4.14

第一步: 弄清 $v$ 的几何含义. 记 $S_r\left(x\right)=\left\{y\in\mathbb{R}^{5}:\left|y-x\right|=r\right\}$, 则四维球面 $S_r$ 的面积是 $\left|S_r\right|=\omega_5r^{3}$, 其中 $\omega_5=\frac{8\pi^{2}}{3}$ 是单位球面 $S^{4}$ 的面积, 而 $\frac{3}{8\pi^{2}}=\frac{1}{\omega_5}$. 于是题给的 $v$ 可写成

$$
v\left(x,t\right)=\frac{1}{at}\cdot\frac{1}{\omega_5\left(at\right)^{3}}\int_{S_{at}\left(x\right)}\psi\left(y\right)\,\mathrm{d}S_y=\frac{\bar{\psi}\left(x,at\right)}{at},\qquad\bar{\psi}\left(x,r\right)=\frac{1}{\omega_5r^{3}}\int_{S_r\left(x\right)}\psi\left(y\right)\,\mathrm{d}S_y,\tag{A}
$$

即 $v$ 是球面平均 $\bar\psi$ 再除以 $at$. 下面记 $P\left(x,t\right):=\bar\psi\left(x,at\right)$, 并按 $v=P$ 论证; 题面分母上的 $\left(at\right)^{4}$ 应为 $\left(at\right)^{3}$ 的理由见文末的注.

第二步: 算球面平均的 Fourier 变换. 对固定的 $\xi\in\mathbb{R}^{5}$ 记 $\rho=\left|\xi\right|$, $z=\rho{at}$. 由 $S^{4}$ 的旋转对称性, 取 $\xi$ 沿第一坐标轴,

$$
\int_{S_{at}\left(x\right)}\mathrm{e}^{\mathrm{i}\xi\cdot{y}}\,\mathrm{d}S_y=\mathrm{e}^{\mathrm{i}\xi\cdot{x}}\cdot\left(at\right)^{3}\int_{S^{4}}\mathrm{e}^{\mathrm{i}zs}\,\mathrm{d}S\left(\omega\right),\tag{B}
$$

其中 $\omega=\left(s,\omega'\right)\in{S}^{4}$, $s\in\left[-1,1\right]$, $\omega'\in{S}^{3}$, 且 $\mathrm{d}S\left(\omega\right)=\left|S^{3}\right|\left(1-s^{2}\right)\,\mathrm{d}s\,\mathrm{d}\sigma\left(\omega'\right)$ 而 $\left|S^{3}\right|=2\pi^{2}$.

第三步: 算出 (B) 中的定积分. 被积函数的虚部关于 $s$ 是奇函数, 只留实部, 并注意

$$
\int_{-1}^{1}\cos\left(zs\right)\,\mathrm{d}s=\frac{2\sin{z}}{z},\qquad\int_{-1}^{1}s^{2}\cos\left(zs\right)\,\mathrm{d}s=\frac{2\sin{z}}{z}+\frac{4\cos{z}}{z^{2}}-\frac{4\sin{z}}{z^{3}},\tag{C}
$$

故

$$
\int_{-1}^{1}\left(1-s^{2}\right)\cos\left(zs\right)\,\mathrm{d}s=\frac{2\sin{z}}{z}-\left(\frac{2\sin{z}}{z}+\frac{4\cos{z}}{z^{2}}-\frac{4\sin{z}}{z^{3}}\right)=\frac{4}{z^{2}}\left(\frac{\sin{z}}{z}-\cos{z}\right).\tag{D}
$$

第四步: 得到球面平均的 Fourier 变换. 由 (B)(D),

$$
\int_{S_{at}\left(x\right)}\mathrm{e}^{\mathrm{i}\xi\cdot{y}}\,\mathrm{d}S_y=\mathrm{e}^{\mathrm{i}\xi\cdot{x}}\cdot\frac{8\pi^{2}\left(at\right)}{z^{2}}\left(\frac{\sin{z}}{z}-\cos{z}\right),\tag{E}
$$

除以 $\left|S_{at}\right|=\frac{8\pi^{2}}{3}\left(at\right)^{3}$, 在对单个频率 $\psi=\mathrm{e}^{\mathrm{i}\xi\cdot{x}}$ 计算时得

$$
\hat{P}\left(\xi,t\right)=\frac{3}{z^{2}}\left(\frac{\sin{z}}{z}-\cos{z}\right)=:g\left(z\right);\tag{F}
$$

一般的 $\psi$ 由叠加得 $\hat{P}\left(\xi,t\right)=g\left(z\right)\hat\psi\left(\xi\right)$.

第五步: 算 $\hat{u}$. 由 (F), $\hat{v}=\hat{P}=g\left(z\right)\hat\psi\left(\xi\right)$, 且 $\partial_t\hat{v}=\rho{a}\,g'\left(z\right)\hat\psi\left(\xi\right)$ (因 $\dot{z}=\rho{a}$). 又 $t=\frac{z}{\rho{a}}$, 故

$$
\hat{u}=\left(\frac{1}{3}t^{2}\partial_t+t\right)\hat{v}=\left[\frac{1}{3}\frac{z^{2}}{\rho^{2}a^{2}}\,\rho{a}\,g'\left(z\right)+\frac{z}{\rho{a}}g\left(z\right)\right]\hat\psi\left(\xi\right)=\frac{1}{\rho{a}}\left[\frac{z^{2}}{3}g'\left(z\right)+zg\left(z\right)\right]\hat\psi\left(\xi\right).\tag{G}
$$

第六步: 化简方括号, 这是全题唯一的技术点. 由 (F) 记 $G\left(z\right)=\frac{\sin{z}}{z}-\cos{z}$, 则 $g\left(z\right)=\frac{3G\left(z\right)}{z^{2}}$, 于是

$$
\frac{z^{2}}{3}g'\left(z\right)=\frac{z^{2}}{3}\cdot3\left(\frac{G'\left(z\right)}{z^{2}}-\frac{2G\left(z\right)}{z^{3}}\right)=G'\left(z\right)-\frac{2G\left(z\right)}{z},\qquad{z}g\left(z\right)=\frac{3G\left(z\right)}{z}.\tag{H}
$$

两式相加, $-\frac{2G}{z}$ 与 $+\frac{3G}{z}$ 合成 $+\frac{G}{z}$,

$$
\frac{z^{2}}{3}g'\left(z\right)+zg\left(z\right)=G'\left(z\right)+\frac{G\left(z\right)}{z}.\tag{I}
$$

第七步: 算出 $G'+G/z$. 由 $G\left(z\right)=\frac{\sin{z}}{z}-\cos{z}$,

$$
G'\left(z\right)=\frac{\cos{z}}{z}+\sin{z}-\frac{\sin{z}}{z^{2}},\qquad\frac{G\left(z\right)}{z}=\frac{\sin{z}}{z^{2}}-\frac{\cos{z}}{z},\tag{J}
$$

相加时 $\frac{\cos{z}}{z}$ 与 $-\frac{\cos{z}}{z}$ 相消, $-\frac{\sin{z}}{z^{2}}$ 与 $+\frac{\sin{z}}{z^{2}}$ 相消,

$$
G'\left(z\right)+\frac{G\left(z\right)}{z}=\sin{z}.\tag{K}
$$

第八步: 得 $\hat{u}$ 的显式. 把 (I)(K) 代入 (G),

$$
\hat{u}\left(\xi,t\right)=\frac{\sin\left(\rho{a}t\right)}{\rho{a}}\hat\psi\left(\xi\right).\tag{L}
$$

第九步: 验证 (L) 就是五维 Cauchy 问题的解. 由 (L): $\hat{u}\left(\xi,0\right)=0$; $\partial_t\hat{u}\left(\xi,0\right)=\cos0\cdot\hat\psi\left(\xi\right)=\hat\psi\left(\xi\right)$; 又

$$
\partial_t^{2}\hat{u}\left(\xi,t\right)=-\rho^{2}a^{2}\,\frac{\sin\left(\rho{a}t\right)}{\rho{a}}\,\hat\psi\left(\xi\right)=-a^{2}\rho^{2}\,\hat{u}\left(\xi,t\right),\tag{M}
$$

而 $\Delta$ 在 $\xi$ 空间中就是乘以 $-\rho^{2}$, 故 (M) 正是方程 $u_{tt}-a^{2}\Delta{u}=0$ 的 Fourier 像. 于是由 **定义 3.4.3 (Fourier 变换)** 与反演的唯一性, 题给的 $u=\left(\frac{1}{3}t^{2}\partial_t+t\right)v$ 就是该 Cauchy 问题的解.

第十步: 直接核对初值. 球面平均在 $t\to0$ 时有展开 $\bar\psi\left(x,at\right)=\psi\left(x\right)+O\left(t^{2}\right)$ (其中一阶项含 $\int_{S^{4}}\omega\,\mathrm{d}S\left(\omega\right)=0$), 且 $\partial_t\bar\psi=O\left(t\right)$, 于是

$$
u\left(x,t\right)=t\bar\psi\left(x,at\right)+O\left(t^{3}\right)=t\psi\left(x\right)+O\left(t^{2}\right),\tag{N}
$$

故 $u\left(x,0\right)=0$, $u_t\left(x,0\right)=\psi\left(x\right)$, 与第九步吻合.

注: 若严格按题面的 $\frac{3}{8\pi^{2}\left(at\right)^{4}}$ 取 $v$, 则 $v=\bar\psi/\left(at\right)$, 用与第五步至第八步相同的计算可得

$$
\hat{u}=\frac{1}{z}\left(\frac{\cos{z}}{z}+\sin{z}-\frac{\sin{z}}{z^{2}}\right)\hat\psi\left(\xi\right),\tag{O}
$$

它不是形如 $C\left(z\right)\hat\psi$ 里应当出现的 $\frac{\sin\left(\rho{a}t\right)}{\rho{a}}\hat\psi$ (量纲也不对), 因而 $\hat{u}_{tt}+a^{2}\rho^{2}\hat{u}\ne0$, 即 $u$ 不满足波动方程; 所以题面分母上的 $\left(at\right)^{4}$ 应为 $\left(at\right)^{3}$, 也就是让 $v$ 恰为 $\psi$ 的球面平均. 上文的全部推导都按 $v=\bar\psi$ 进行.

## 习题 4.15 (三维波动方程解的 $1/t$ 衰减)

设 $u$ 是三维波动方程 Cauchy 问题

$$
\begin{cases}u_{tt}-a^{2}\Delta{u}=0,&x\in\mathbb{R}^{3},t>0,\\u\left(x,0\right)=\varphi\left(x\right),u_t\left(x,0\right)=\psi\left(x\right),&x\in\mathbb{R}^{3}\end{cases}
$$

的经典解. 证明: 若 $\varphi,\psi\in{C}_0^{\infty}\left(\mathbb{R}^{3}\right)$, 则存在正常数 $C$, 使得 $\left|u\left(x,t\right)\right|\le\frac{C}{t}$, $x\in\mathbb{R}^{3}$, $t>0$.

### 解答 4.15

第一步: 写出解的积分表示. 由**定理 4.2.6 (三维波动方程的 Poisson 公式)**,

$$
u\left(x,t\right)=\frac{1}{4\pi{a}^{2}}\left[\frac{\partial}{\partial{t}}\int_{S_{at}\left(x\right)}\frac{\varphi\left(y\right)}{t}\,\mathrm{d}S_y+\int_{S_{at}\left(x\right)}\frac{\psi\left(y\right)}{t}\,\mathrm{d}S_y\right],\qquad{S}_{at}\left(x\right)=\left\{y:\left|y-x\right|=at\right\}.\tag{A}
$$

第二步: 引入支撑集与球面平均. 记 $K=\overline{\operatorname{supp}\varphi\cup\operatorname{supp}\psi\cup\operatorname{supp}\nabla\varphi}$, 由 $\varphi,\psi\in{C}_0^{\infty}\left(\mathbb{R}^{3}\right)$ 知 $K$ 是紧集, 取 $R>0$ 使 $K\subset{B}_R\left(0\right)$. 把面积分化成单位球面上的积分: 以 $n$ 记单位向量,

$$
\int_{S_{at}\left(x\right)}f\left(y\right)\,\mathrm{d}S_y=\left(at\right)^{2}\int_{\left|n\right|=1}f\left(x+at\,n\right)\,\mathrm{d}S_n=:\left(at\right)^{2}I_f\left(x,t\right).\tag{B}
$$

第三步: 把 (A) 写成 $I_{\varphi},I_{\psi}$ 的组合. 由 (B),

$$
\int_{S_{at}\left(x\right)}\frac{\varphi\left(y\right)}{t}\,\mathrm{d}S_y=\left(at\right)I_{\varphi},\qquad\int_{S_{at}\left(x\right)}\frac{\psi\left(y\right)}{t}\,\mathrm{d}S_y=\left(at\right)I_{\psi},\tag{C}
$$

于是

$$
u\left(x,t\right)=\frac{1}{4\pi{a}^{2}}\left[a\,I_{\varphi}+a^{2}t\,\partial_{at}I_{\varphi}+at\,I_{\psi}\right],\tag{D}
$$

其中 $\partial_{at}I_{\varphi}$ 表示对半径求导后的取值, 即 $\partial_{at}I_{\varphi}=\int_{\left|n\right|=1}\nabla\varphi\left(x+at\,n\right)\cdot{n}\,\mathrm{d}S_n$; 这一步只是把 $\frac{\partial}{\partial{t}}$ 作用在 $t^{-1}\int_{S_{at}}\varphi$ 上并整理.

第四步: 分三种情形估计. 
情形一: 球面与 $K$ 不相交, 即 $\left|x\right|-at>R$ 或 $at-\left|x\right|>R$. 此时 $\varphi,\psi$ 及其导数在 $S_{at}\left(x\right)$ 上为零, 故

$$
u\left(x,t\right)=0.\tag{E}
$$

情形二: $at\le2R$. 此时 $\left|x\right|\le2R+R=3R$, 即 $\left(x,t\right)$ 落在有界闭区域 $\left\{\left|x\right|\le3R,0\le{t}\le2R/a\right\}$ 内, 由 $u$ 是经典解 (连续) 得 $\left|u\left(x,t\right)\right|\le{C}_0$, 于是

$$
\left|u\left(x,t\right)\right|\le{C}_0\le\frac{\left(2R/a\right)C_0}{t}.\tag{F}
$$

情形三: $at>2R$ 且球面与 $K$ 相交. 这是估计衰减的关键情形.

第五步: 估计相交部分在单位球面上的面积. 设 $n,n'$ 都使 $x+at\,n,x+at\,n'\in{K}$, 则 $\left|at\,n-at\,n'\right|\le2R$, 即

$$
\left|n-n'\right|\le\frac{2R}{at}.\tag{G}
$$

故集合 $E=\left\{n:\left|n\right|=1,x+at\,n\in{K}\right\}$ 的直径不超过 $\frac{2R}{at}<\frac{2R}{2R}=1$, 它含在单位球面上半径为 $\frac{2R}{at}$ 的球冠内, 于是

$$
\left|E\right|\le\pi\left(\frac{2R}{at}\right)^{2}=\frac{4\pi{R}^{2}}{\left(at\right)^{2}}.\tag{H}
$$

第六步: 估计三个基本积分. 由 (H) 与 $K\subset{B}_R\left(0\right)$,

$$
\left|I_{\varphi}\right|\le\frac{4\pi{R}^{2}}{\left(at\right)^{2}}\left\|\varphi\right\|_{\infty},\quad\left|I_{\psi}\right|\le\frac{4\pi{R}^{2}}{\left(at\right)^{2}}\left\|\psi\right\|_{\infty},\quad\left|\partial_{at}I_{\varphi}\right|\le\frac{4\pi{R}^{2}}{\left(at\right)^{2}}\left\|\nabla\varphi\right\|_{\infty}.\tag{I}
$$

第七步: 把 (I) 代入 (D). 由 (D)(I),

$$
\left|u\left(x,t\right)\right|\le\frac{1}{4\pi{a}^{2}}\cdot4\pi{R}^{2}\left[\frac{a\left\|\varphi\right\|_{\infty}}{\left(at\right)^{2}}+\frac{a^{2}t\left\|\nabla\varphi\right\|_{\infty}}{\left(at\right)^{2}}+\frac{at\left\|\psi\right\|_{\infty}}{\left(at\right)^{2}}\right]=\frac{R^{2}}{a^{2}}\left[\frac{\left\|\varphi\right\|_{\infty}}{at^{2}}+\frac{\left\|\nabla\varphi\right\|_{\infty}}{t}+\frac{\left\|\psi\right\|_{\infty}}{at}\right].\tag{J}
$$

第八步: 用 $at>2R$ 吸收分母. 由 $at>2R$ 得 $\frac{1}{at}<\frac{1}{2R}$, 故 (J) 右端

$$
\le\frac{1}{t}\cdot\frac{R^{2}}{a^{2}}\left[\left\|\nabla\varphi\right\|_{\infty}+\frac{\left\|\psi\right\|_{\infty}}{a}+\frac{\left\|\varphi\right\|_{\infty}}{2R}\right].\tag{K}
$$

第九步: 取定常数 $C$. 令

$$
C:=\max\left\{\frac{2R}{a}C_0,\frac{R^{2}}{a^{2}}\left(\left\|\nabla\varphi\right\|_{\infty}+\frac{\left\|\psi\right\|_{\infty}}{a}+\frac{\left\|\varphi\right\|_{\infty}}{2R}\right)\right\},\tag{L}
$$

则由 (E)(F)(K) 三种情形, 对一切 $x\in\mathbb{R}^{3}$, $t>0$ 都有 $\left|u\left(x,t\right)\right|\le\frac{C}{t}$.

第十步: 说明结论的含义. (L) 说明衰减只依赖于初值的 $\sup$ 范数与支撑半径 $R$; 物理上, 三维波动方程满足强惠更斯原理, 波形无"尾迹", 波前过后解立即为零, 而经过观察点的那一刻球面与初值支撑集的交集只是一段小"球冠", 其面积按 $t^{-2}$ 缩小, 于是解以 $t^{-1}$ 衰减.

## 习题 6.1 (由奇点可去性定理证明 Böcher 定理)

根据定理 6.2.3, 证明 Böcher 定理 (定理 6.2.4).

### 解答 6.1

第一步: 记球面平均并写出其方程. 设 $u>0$ 在 $B_1\left(0\right)\setminus\left\{0\right\}$ 内调和, 对 $0<{}r<1$ 记

$$
m\left(r\right)=\frac{1}{\omega_nr^{n-1}}\int_{\left|y\right|=r}u\left(y\right)\,\mathrm{d}S_y.\tag{A}
$$

由 $u$ 在环域内调和, 平均值函数满足径向方程 $m''+\frac{n-1}{r}m'=0$, 故

$$
m\left(r\right)=\begin{cases}c_1+c_2\log{r},&n=2,\\c_1+c_2r^{2-n},&n\ge3.\end{cases}\tag{B}
$$

第二步: 用正性定出 $c_2$ 的符号. 由 $u>0$ 得 $m\left(r\right)>0$ 对一切 $0<{}r<1$ 成立. 若 $n\ge3$ 而 $c_2<0$, 则 $r\to0$ 时 $c_2r^{2-n}\to-\infty$, 于是 $m\left(r\right)<0$ (当 $r$ 充分小时), 矛盾; 故 $c_2\ge0$. 同理, 若 $n=2$ 而 $c_2>0$, 则 $r\to0$ 时 $c_2\log{r}\to-\infty$, 同样矛盾; 故 $c_2\le0$. 以下以 $n\ge3$ 为例详细证明, $n=2$ 完全同理.

第三步: 构造待证可去性的函数. 取 $a:=c_2\ge0$ 并令

$$
v\left(x\right):=u\left(x\right)-a\left|x\right|^{2-n},\qquad{x}\in{B}_1\left(0\right)\setminus\left\{0\right\}.\tag{C}
$$

由 $\left|x\right|^{2-n}$ 在 $\mathbb{R}^{n}\setminus\left\{0\right\}$ 内调和知 $v$ 调和; 又 $\left|x\right|^{2-n}$ 在球面 $\left|x\right|=r$ 上的平均值恰为 $r^{2-n}$, 故由 (B)(C) 得 $v$ 的每个球面平均值都是 $c_1$:

$$
\frac{1}{\omega_nr^{n-1}}\int_{\left|y\right|=r}v\left(y\right)\,\mathrm{d}S_y=c_1,\qquad0<{}r<1.\tag{D}
$$

第四步: 用 Harnack 不等式证明 $\left|x\right|^{n-2}v\left(x\right)$ 有界. 由 $u>0$ 与 $u$ 在环壳 $\left\{r/2<\left|x\right|<3r/2\right\}$ 内调和, 应用 Harnack 不等式并沿半径相当的球链比较, 得存在只依赖于 $n$ 的常数 $H_n$, 使球面 $\left|y\right|=r$ 上任意两点满足

$$
\max_{\left|y\right|=r}u\le{H}_nu\left(y\right),\qquad{y}\in\left\{\left|y\right|=r\right\}.\tag{E}
$$

把 (E) 用于 $z\left(x\right):=\left|x\right|^{n-2}u\left(x\right)$: 由 (E) 与 (B),

$$
\max_{\left|y\right|=r}z\le{H}_nr^{n-2}\min_{\left|y\right|=r}u\le{H}_n\,r^{n-2}m\left(r\right)=H_n\left(c_1r^{n-2}+c_2\right)\le{H}_n\left(c_1+c_2\right).\tag{F}
$$

即 $\left|x\right|^{n-2}u\left(x\right)\le{H}_n\left(c_1+c_2\right)$ 在 $0<\left|x\right|<1$ 上一致成立; 另一方面 $\left|x\right|^{n-2}u>0$ 而 $a\ge0$, 故由 (C)

$$
-a\,\left|x\right|^{n-2}\le\left|x\right|^{n-2}v\left(x\right)=\left|x\right|^{n-2}u\left(x\right)-a\le{H}_n\left(c_1+c_2\right)-a.\tag{G}
$$

于是存在 $D>0$ 使

$$
\left|x\right|^{n-2}\left|v\left(x\right)\right|\le{D},\qquad0<\left|x\right|<1.\tag{H}
$$

第五步: 用极值原理把 (H) 化为 $v$ 在 $0$ 附近有界. 固定 $0<\rho<1/2$, 记 $M_r=\max_{\left|y\right|=r}\left|v\right|$ ($0<{}r<\rho$) 与 $K_\rho=\max_{\left|y\right|=\rho}\left|v\right|$. 比较函数取

$$
f_r\left(x\right)=M_r\left(\frac{r}{\left|x\right|}\right)^{n-2}+K_\rho,\tag{I}
$$

它是调和函数, 且在 $\left|x\right|=r$ 上等于 $M_r+K_\rho\ge\left|v\right|$, 在 $\left|x\right|=\rho$ 上等于 $M_r\left(r/\rho\right)^{n-2}+K_\rho\ge{K}_\rho\ge\left|v\right|$; 又 $\left|v\right|$ 在 $\left\{r<\left|x\right|<\rho\right\}$ 内次调和, 故由极值原理

$$
\left|v\left(x\right)\right|\le{M}_r\left(\frac{r}{\left|x\right|}\right)^{n-2}+K_\rho,\qquad{r}<\left|x\right|<\rho.\tag{J}
$$

由 (H) 得 $M_r\le{D}r^{2-n}$, 于是 (J) 右端的第一项满足 $M_r\left(\frac{r}{\left|x\right|}\right)^{n-2}\le{D}r^{2-n}r^{n-2}\left|x\right|^{2-n}=D\left|x\right|^{2-n}$, 它与 $r$ 无关; 故 (J) 对固定 $x$ ($\left|x\right|<\rho$) 令 $r\to0$ 得

$$
\left|v\left(x\right)\right|\le{K}_\rho,\qquad0<\left|x\right|<\rho.\tag{L}
$$

由此 $v$ 在 $0$ 附近有界.

第六步: 说明 $v$ 满足定理 6.2.3 的奇性条件. 由 (L), $v\left(x\right)=O\left(1\right)$ 当 $x\to0$; 而 $\left|x\right|^{2-n}\to+\infty$, 故

$$
\frac{\left|v\left(x\right)\right|}{\left|x\right|^{2-n}}\le\frac{K_\rho}{\left|x\right|^{2-n}}\longrightarrow0,\qquad\text{即}\quad{v}\left(x\right)=o\left(\left|x\right|^{2-n}\right).\tag{M}
$$

第七步: 应用定理 6.2.3. 由 (C) 知 $v$ 在 $B_1\left(0\right)\setminus\left\{0\right\}$ 内调和, 由 (M) 知它满足 $n\ge3$ 的奇性条件, 故由**定理 6.2.3 (奇点可去性)** $v$ 的奇点 $x=0$ 可去: 可以在 $x=0$ 处补充定义 $v$ 的值, 使 $v\in{C}^{2}\left(B_1\left(0\right)\right)$ 且在 $B_1\left(0\right)$ 内调和.

第八步: 读出 Böcher 定理. 由 (C) 与第七步, 若记补充定义后的函数为 $v$ (在 $B_1\left(0\right)$ 内调和), 则

$$
u\left(x\right)=v\left(x\right)+a\left|x\right|^{2-n},\qquad{x}\in{B}_1\left(0\right)\setminus\left\{0\right\},\tag{N}
$$

其中 $a\ge0$. 这正是**定理 6.2.4 (Böcher 定理)** 在 $n\ge3$ 时的结论.

第九步: $n=2$ 的情形. 此时 $c_2\le0$, 取 $a:=-c_2\ge0$ 并令

$$
v\left(x\right):=u\left(x\right)-a\log\frac{1}{\left|x\right|}=u\left(x\right)+c_2\log\left|x\right|,\tag{O}
$$

由 $\log\left|x\right|$ 调和知 $v$ 调和, 且 $\log\left|x\right|$ 在球面上的平均值为 $\log{r}$, 故结合 (B) 得 $v$ 的球面平均恒为 $c_1$, 与 (D) 平行. 把第五步至第七步中的 $\left|x\right|^{2-n}$ 全部换成 $\log\frac{1}{\left|x\right|}$ (相应的比较函数 $f_r$ 换成 $\frac{\log\left(\rho/\left|x\right|\right)}{\log\left(\rho/r\right)}$), 同样的三步给出 $v=o\left(\log\frac{1}{\left|x\right|}\right)$, 即 $v$ 的对数型奇性系数为零; 由定理 6.2.3 的 $n=2$ 情形得 $v$ 可去延拓到 $B_1\left(0\right)$ 内而调和, 于是

$$
u\left(x\right)=v\left(x\right)+a\log\frac{1}{\left|x\right|},\qquad{a}\ge0,\tag{P}
$$

这就是 **定理 6.2.4 (Böcher 定理)** 在 $n=2$ 时的结论.

第十步: 收尾. 由 (N)(P), 无论 $n=2$ 还是 $n\ge3$, 正调和函数 $u$ 都可写成"$B_1\left(0\right)$ 内的调和函数 + 一个非负常数乘基本解的奇性"之和; 定理 6.2.4 得证.

## 习题 6.2 (Schwarz 反射定理)

设 $\Omega^{+}$ 是上半空间 $\mathbb{R}^{n}_{+}=\left\{x=\left(x',x_n\right):x'\in\mathbb{R}^{n-1},x_n>0\right\}$ 的一个子区域, 它以超平面 $x_n=0$ 的一个开区域 $T$ 作为它的边界的一部分. 假设 $u$ 在 $\Omega^{+}$ 中调和, 在 $\Omega^{+}\cup{T}$ 上连续, 并且在 $T$ 上 $u=0$. 证明: 由

$$
U\left(x_1,\dots,x_n\right)=\begin{cases}u\left(x_1,\dots,x_n\right),&x_n\ge0,\\-u\left(x_1,\dots,-x_n\right),&x_n<0\end{cases}
$$

定义的函数 $U$ 在区域 $\Omega^{+}\cup{T}\cup\Omega^{-}$ 中调和, 其中 $\Omega^{-}$ 是 $\Omega^{+}$ 关于超平面 $x_n=0$ 的反射, 即 $\Omega^{-}=\left\{\left(x',x_n\right)\in\mathbb{R}^{n}:\left(x',-x_n\right)\in\Omega^{+}\right\}$.

### 解答 6.2

第一步: 记反射变换. 记 $\sigma\left(x\right)=\left(x',-x_n\right)$, 则 $\sigma$ 是正交变换 ($\sigma^{-1}=\sigma$), 且 $\sigma\left(\Omega^{+}\right)=\Omega^{-}$, $\sigma\left(T\right)=T$; $U$ 的定义可写成

$$
U\left(x\right)=\begin{cases}u\left(x\right),&x\in\Omega^{+}\cup{T},\\-u\left(\sigma{x}\right),&x\in\Omega^{-}.\tag{A}
\end{cases}
$$

第二步: $U$ 在 $\Omega^{+}$ 内调和. 由 (A), $U=u$ 在 $\Omega^{+}$ 内; 因 $u$ 在 $\Omega^{+}$ 内调和, 故 $\Delta{U}=0$ 于 $\Omega^{+}$.

第三步: $U$ 在 $\Omega^{-}$ 内调和. 对 $x\in\Omega^{-}$, 记 $y=\sigma{x}\in\Omega^{+}$, 则 $U\left(x\right)=-u\left(y\right)$. 因 $\sigma$ 是正交变换, 拉普拉斯算子在正交变换下不变, 即 $\Delta_x\left[u\left(\sigma{x}\right)\right]=\left(\Delta{u}\right)\left(\sigma{x}\right)=0$; 于是

$$
\Delta{U}\left(x\right)=-\Delta_x\left[u\left(\sigma{x}\right)\right]=0,\qquad{x}\in\Omega^{-}.\tag{B}
$$

第四步: $U$ 在有内部的点处连续. 在 $\Omega^{+}$ 内 $U=u$ 连续, 在 $\Omega^{-}$ 内 $U=-u\circ\sigma$ 连续. 在 $T$ 上, 由 $u=0$ 得两侧的极限: 当 $x\in\Omega^{+}$, $x\to{x}_0\in{T}$ 时 $U\left(x\right)=u\left(x\right)\to{u}\left(x_0\right)=0$; 当 $x\in\Omega^{-}$, $x\to{x}_0\in{T}$ 时 $\sigma{x}\to\sigma{x}_0=x_0$, 故 $U\left(x\right)=-u\left(\sigma{x}\right)\to-u\left(x_0\right)=0$. 于是 $U$ 在 $T$ 上连续且 $U|_{T}=0$; 结合第二步第三步, $U$ 在 $\Omega^{+}\cup{T}\cup\Omega^{-}$ 上连续.

第五步: 把 $U$ 在 $T$ 上的调和性化为均值性质. 取 $x_0\in{T}$; 由 $T$ 相对 $\partial\Omega^{+}$ 是开集, 存在 $\rho>0$ 使 $B_\rho\left(x_0\right)\subset\Omega^{+}\cup{T}\cup\Omega^{-}$. 对 $0<{}s<\rho$ 计算球面平均

$$
\frac{1}{\left|S^{n-1}_s\right|}\int_{\left|y-x_0\right|=s}U\left(y\right)\,\mathrm{d}S_y=\frac{1}{\left|S^{n-1}_s\right|}\left[\int_{\left|y-x_0\right|=s,y_n>0}u\left(y\right)\,\mathrm{d}S_y-\int_{\left|y-x_0\right|=s,y_n<0}u\left(\sigma{y}\right)\,\mathrm{d}S_y\right].\tag{C}
$$

第六步: 用反射对称性说明两个半球面的积分相等. 作变量替换 $y=\sigma{z}$ ($z_n>0$), 则 $\left|z-x_0\right|=\left|\sigma{y}-\sigma{x_0}\right|=\left|y-x_0\right|=s$ 且 $\mathrm{d}S_y=\mathrm{d}S_z$, 故下半个球面上的积分等于上半个球面上的积分:

$$
\int_{\left|y-x_0\right|=s,y_n<0}u\left(\sigma{y}\right)\,\mathrm{d}S_y=\int_{\left|z-x_0\right|=s,z_n>0}u\left(z\right)\,\mathrm{d}S_z.\tag{D}
$$

第七步: 得到 $U$ 在 $T$ 上的球面均值. 把 (D) 代入 (C), 两项相减为零; 又 $U\left(x_0\right)=0$ (因 $x_0\in{T}$), 故

$$
U\left(x_0\right)=\frac{1}{\left|S^{n-1}_s\right|}\int_{\left|y-x_0\right|=s}U\left(y\right)\,\mathrm{d}S_y,\qquad0<{}s<\rho.\tag{E}
$$

同理把球面平均换成球体平均, 也成立

$$
U\left(x_0\right)=\frac{1}{\left|B_s\right|}\int_{B_s\left(x_0\right)}U\left(y\right)\,\mathrm{d}y,\qquad0<{}s<\rho.\tag{F}
$$

第八步: 由均值性质与连续性得 $U$ 在 $T$ 上调和. 由 (F), $U$ 在 $B_\rho\left(x_0\right)$ 内每一点都满足球体均值性质 (在 $\Omega^{\pm}$ 内因 $U$ 调和而成立, 在 $T$ 上由 (F) 成立), 且 $U$ 在 $B_\rho\left(x_0\right)$ 上连续; 由调和函数的均值性质刻画 (连续且满足球体均值性质的函数必调和, 见第 2 章关于调和函数均值性质的讨论), $U$ 在 $B_\rho\left(x_0\right)$ 内调和, 特别在 $x_0$ 处调和.

第九步: 合并结论. 由第二步, 第七步, 第八步, $U$ 在 $\Omega^{+}$, $\Omega^{-}$ 以及 $T$ 的每一点的邻域内都调和, 故 $U$ 在 $\Omega^{+}\cup{T}\cup\Omega^{-}$ 中调和. 这就是 Schwarz 反射定理: 上半空间内零边值的调和函数可以经超平面作奇反射延拓为整体的调和函数.

第十步: 说明附注. 若把 (A) 中的负号去掉 (即作偶反射), 则第四步与第七步中的相消变为相加, 边界条件应相应改为 $u_n=0$ (Neumann 型), 这说明奇反射与零 Dirichlet 边值相配套; 本题的零边值条件正是奇反射能够奏效的原因.
