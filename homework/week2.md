# week2

> **习题 1.1 (径向函数的拉普拉斯算子)**
> 
> 若 $u\left(x\right)=U\left(r\right)$, $r=\left|x\right|$, 则 $\partial_{x_i}u=U'\left(r\right)\frac{x_i}{r}$, $\frac{\partial^{2}u}{\partial{x_i}^{2}}=\left(\frac{U''\left(r\right)}{r^{2}}-\frac{U'\left(r\right)}{r^{3}}\right)x_i^{2}+\frac{U'\left(r\right)}{r}$, $\Delta{u}=U''\left(r\right)+\frac{n-1}{r}U'\left(r\right)$.

## 习题 1.5 (Lane-Emden 型非线性方程的正解)

设 $n\ge3$. 求正常数 $\alpha,\beta$, 使得 $u=\alpha\left(1-\left|x\right|^{2}\right)^{-\beta}$ 是 $\Delta{u}=u^{\frac{n+2}{n-2}}$ 在 $B_1\left(0\right)$ 中的解.

### 解答 1.5

第一步: 记 $r=\left|x\right|$, $p=\frac{n+2}{n-2}$, 则 $u\left(x\right)=\alpha\varphi\left(r\right)$, $\varphi\left(r\right)=\left(1-r^{2}\right)^{-\beta}$. 由**习题 1.1 (径向函数的拉普拉斯算子)**,

$$
\Delta{u}=\alpha\left(\varphi''\left(r\right)+\frac{n-1}{r}\varphi'\left(r\right)\right).\tag{A}
$$

第二步: 逐次求导. 记 $w=1-r^{2}$, 则 $\varphi=w^{-\beta}$, 且

$$
\varphi'\left(r\right)=2\beta{r}w^{-\beta-1},\qquad\varphi''\left(r\right)=2\beta{w}^{-\beta-1}+4\beta\left(\beta+1\right)r^{2}w^{-\beta-2}.
$$

第三步: 代入 (A) 并合并同类项,

$$
\begin{aligned}
\Delta{u}&=\alpha\left[2\beta{w}^{-\beta-1}+4\beta\left(\beta+1\right)r^{2}w^{-\beta-2}+\left(n-1\right)2\beta{w}^{-\beta-1}\right]\\
&=2\alpha\beta{w}^{-\beta-2}\left[w+2\left(\beta+1\right)r^{2}+\left(n-1\right)w\right]\\
&=2\alpha\beta{w}^{-\beta-2}\left[n+\left(2\beta+2-n\right)r^{2}\right].\tag{B}
\end{aligned}
$$

第四步: 要求 $\Delta{u}=u^{p}=\alpha^{p}w^{-\beta{p}}$ 在 $B_1\left(0\right)$ 中逐点成立. (B) 的右端含方括号 $n+\left(2\beta+2-n\right)r^{2}$, 它是 $r$ 的非平凡多项式, 而右端 $\alpha^{p}w^{-\beta{p}}$ 只是 $w$ 的纯幂, 故方括号必须不含 $r^{2}$ 项, 即

$$
2\beta+2-n=0,\qquad\beta=\frac{n-2}{2}.
$$

第五步: 确定 $\alpha$. 此时 (B) 给出 $\Delta{u}=2\alpha\beta{n}w^{-\beta-2}$, 与 $u^{p}=\alpha^{p}w^{-\beta{p}}$ 比较 $w$ 的幂次与系数, 得

$$
\beta{p}=\beta+2,\qquad{2\alpha\beta{n}}=\alpha^{p}.
$$

第一式给出 $p=\frac{\beta+2}{\beta}=\frac{n+2}{n-2}$, 与题设一致; 第二式即 $\alpha^{p-1}=2\beta{n}=n\left(n-2\right)$.

第六步: 用 $p-1=\frac{4}{n-2}$ 得

$$
\alpha=\left(n\left(n-2\right)\right)^{\frac{1}{p-1}}=\left(n\left(n-2\right)\right)^{\frac{n-2}{4}}.
$$

于是所求的正常数为

$$
\alpha=\left(n\left(n-2\right)\right)^{\frac{n-2}{4}},\qquad\beta=\frac{n-2}{2}.
$$

## 习题 1.6 (线性弹性方程解的散度)

设 $u=\left(u^{1},u^{2},u^{3}\right)$ 是线性弹力发展方程

$$
u_{tt}-\mu\Delta{u}-\left(\lambda+\mu\right)\nabla\left(\operatorname{div}u\right)=0,\qquad\left(x,t\right)\in\mathbb{R}^{3}\times\left(0,+\infty\right)
$$

的解, 其中 $\lambda,\mu$ 是常数. 则对某个常数 $C$, $w:=\operatorname{div}u$ 满足波动方程

$$
w_{tt}=C\Delta{w}.
$$

### 解答 1.6

第一步: 对原方程两端取散度. 散度与 $\Delta,\nabla\operatorname{div}$ 可交换次序, 故

$$
\left(\operatorname{div}u\right)_{tt}-\mu\Delta\left(\operatorname{div}u\right)-\left(\lambda+\mu\right)\operatorname{div}\nabla\left(\operatorname{div}u\right)=0.\tag{A}
$$

第二步: 注意 $\operatorname{div}\nabla=\Delta$, 记 $w=\operatorname{div}u$, 则 (A) 即

$$
w_{tt}-\mu\Delta{w}-\left(\lambda+\mu\right)\Delta{w}=0,
$$

即

$$
w_{tt}=\left(\lambda+2\mu\right)\Delta{w}.
$$

故 $C=\lambda+2\mu$.

## 习题 2.1 (二阶层叠的临界光滑性)

在 $B_{1/2}=\left\{\left(x,y\right)\in\mathbb{R}^{2}\,\middle|\,x^{2}+y^{2}<\frac{1}{4}\right\}$ 上定义函数

$$
u\left(x,y\right)=\begin{cases}\left(x^{2}-y^{2}\right)\left(-\ln\left(x^{2}+y^{2}\right)\right)^{\frac{1}{2}},&\left(x,y\right)\in{B}_{1/2}\setminus\left\{0\right\},\\0,&\left(x,y\right)=\left(0,0\right)\end{cases}
$$

和

$$
f\left(x,y\right)=\begin{cases}-\frac{x^{2}-y^{2}}{x^{2}+y^{2}}\left(4\left(-\ln\left(x^{2}+y^{2}\right)\right)^{-\frac{1}{2}}+\left(-\ln\left(x^{2}+y^{2}\right)\right)^{-\frac{3}{2}}\right),&\left(x,y\right)\in{B}_{1/2}\setminus\left\{0\right\},\\0,&\left(x,y\right)=\left(0,0\right).\end{cases}
$$

试证明: $u\in{C}^{1}\left(\overline{B}_{1/2}\right)\cap{C}^{2}\left(B_{1/2}\setminus\left\{0\right\}\right)$, $f\in{C}^{0}\left(\overline{B}_{1/2}\right)$, 并且在 $B_{1/2}\setminus\left\{0\right\}$ 中 $\Delta{u}=f\left(x,y\right)$, 但是 $u\notin{C}^{2}\left(B_{1/2}\right)$.

### 解答 2.1

第一步: 记 $r^{2}=x^{2}+y^{2}$, $L=-\ln\left(x^{2}+y^{2}\right)=-\ln{r}^{2}$, $u=\left(x^{2}-y^{2}\right)L^{\frac{1}{2}}$. 在 $B_{1/2}$ 上 $r^{2}<\frac{1}{4}$, 故 $L>\ln4>0$, 从而 $L^{\frac{1}{2}}$ 在 $B_{1/2}$ 上光滑, $u$ 在 $B_{1/2}\setminus\left\{0\right\}$ 内光滑.

第二步: 算 $\Delta{u}$. 注意 $L=-\ln{r}^{2}$, 故

$$
\nabla{L}=\frac{-2\left(x,y\right)}{r^{2}},\qquad\nabla{L}^{\frac{1}{2}}=-\frac{\left(x,y\right)}{r^{2}}L^{-\frac{1}{2}},\qquad\Delta{L}^{\frac{1}{2}}=-\frac{L^{-\frac{3}{2}}}{r^{2}}.\tag{A}
$$

其中第三式由前两式直接求散度得到: $\operatorname{div}\left(\frac{\left(x,y\right)}{r^{2}}\right)=0$ 而 $\frac{\left(x,y\right)}{r^{2}}\cdot\nabla{L}^{-\frac{1}{2}}=-\frac{L^{-\frac{3}{2}}}{r^{2}}$.

第三步: 用二阶导数的乘积法则, 并注意 $\Delta\left(x^{2}-y^{2}\right)=0$,

$$
\Delta{u}=\Delta\left(x^{2}-y^{2}\right)L^{\frac{1}{2}}+2\nabla\left(x^{2}-y^{2}\right)\cdot\nabla{L}^{\frac{1}{2}}+\left(x^{2}-y^{2}\right)\Delta{L}^{\frac{1}{2}}.\tag{B}
$$

第一项为 $0$. 对第二项, $\nabla\left(x^{2}-y^{2}\right)=\left(2x,-2y\right)$, 代入 (A) 的 $\nabla{L}^{\frac{1}{2}}$,

$$
2\nabla\left(x^{2}-y^{2}\right)\cdot\nabla{L}^{\frac{1}{2}}=2\left(-4\left(x^{2}-y^{2}\right)\frac{L^{-\frac{1}{2}}}{2r^{2}}\right)=-\frac{4\left(x^{2}-y^{2}\right)L^{-\frac{1}{2}}}{r^{2}}.
$$

第四步: 由 (A) 的 $\Delta{L}^{\frac{1}{2}}$ 得第三项 $\left(x^{2}-y^{2}\right)\Delta{L}^{\frac{1}{2}}=-\frac{\left(x^{2}-y^{2}\right)L^{-\frac{3}{2}}}{r^{2}}$. 把三项代入 (B),

$$
\Delta{u}=-\frac{x^{2}-y^{2}}{r^{2}}\left(4L^{-\frac{1}{2}}+L^{-\frac{3}{2}}\right)=f\left(x,y\right),\qquad\left(x,y\right)\in{B}_{1/2}\setminus\left\{0\right\}.\tag{C}
$$

第五步: 证 $f\in{C}^{0}\left(\overline{B}_{1/2}\right)$. 在 $B_{1/2}\setminus\left\{0\right\}$ 上 (C) 的表达式是连续函数的复合, 连续. 又 $\left|\frac{x^{2}-y^{2}}{r^{2}}\right|\le1$, 且由 $L\to+\infty$ (当 $r\to0$) 得 $L^{-\frac{1}{2}}\le\left(\ln\frac{1}{r^{2}}\right)^{-\frac{1}{2}}\to0$, 同法 $L^{-\frac{3}{2}}\to0$, 故 $\left|f\right|\le4L^{-\frac{1}{2}}+L^{-\frac{3}{2}}\to0$, 即 $f\left(x,y\right)\to0=f\left(0,0\right)$. 所以 $f$ 在 $\overline{B}_{1/2}$ 上连续.

第六步: 证 $u\in{C}^{1}\left(\overline{B}_{1/2}\right)$. 在 $r>0$ 处由 (A),

$$
u_x=2xL^{\frac{1}{2}}-\frac{x\left(x^{2}-y^{2}\right)L^{-\frac{1}{2}}}{r^{2}},\qquad{u}_y=-2yL^{\frac{1}{2}}-\frac{y\left(x^{2}-y^{2}\right)L^{-\frac{1}{2}}}{r^{2}},
$$

它们当 $r>0$ 时连续. 估计 $r\to0$ 时的极限. 因为 $rL^{\frac{1}{2}}=r\left(\ln\frac{1}{r^{2}}\right)^{\frac{1}{2}}\to0$, 所以

$$
\left|2xL^{\frac{1}{2}}\right|\le2rL^{\frac{1}{2}}\to0,\qquad\left|\frac{x\left(x^{2}-y^{2}\right)L^{-\frac{1}{2}}}{r^{2}}\right|\le\frac{r\cdot{r}^{2}L^{-\frac{1}{2}}}{r^{2}}=rL^{-\frac{1}{2}}\to0.
$$

故 $u_x,u_y\to0$ (当 $r\to0$).

第七步: 算 $u$ 在原点处的一阶偏导数. 对 $x$ 方向作差商, 注意 $u\left(h,0\right)=h^{2}L\left(h\right)^{\frac{1}{2}}$, 其中 $L\left(h\right)=-\ln{h}^{2}$,

$$
\frac{u\left(h,0\right)-u\left(0,0\right)}{h}=hL\left(h\right)^{\frac{1}{2}}\to0\qquad\left(h\to0\right),
$$

故 $u_x\left(0,0\right)=0$; 同理 $u_y\left(0,0\right)=0$. 结合第六步, $u_x,u_y$ 在 $\overline{B}_{1/2}$ 上连续, 即 $u\in{C}^{1}\left(\overline{B}_{1/2}\right)$.

第八步: 证 $u\notin{C}^{2}\left(B_{1/2}\right)$. 沿 $y=0$ 的正半轴 ($x>0$, 此时 $r^{2}=x^{2}$) 计算 $u_{xx}$. 由第六步,

$$
u_x=2xL^{\frac{1}{2}}-x^{3}\frac{L^{-\frac{1}{2}}}{r^{2}},
$$

对 $x$ 再求导一次,

$$
u_{xx}=2L^{\frac{1}{2}}+2x\partial_{x}L^{\frac{1}{2}}-2x\frac{L^{-\frac{1}{2}}}{r^{2}}-x^{3}\partial_{x}\left(\frac{L^{-\frac{1}{2}}}{r^{2}}\right).\tag{D}
$$

第三步已给出 $\partial_{x}L^{\frac{1}{2}}=-\frac{xL^{-\frac{1}{2}}}{r^{2}}$, 且

$$
\partial_{x}\left(\frac{L^{-\frac{1}{2}}}{r^{2}}\right)=\frac{xL^{-\frac{3}{2}}}{r^{4}}-\frac{2xL^{-\frac{1}{2}}}{r^{4}}.
$$

第九步: 在 $y=0$, $r^{2}=x^{2}$ 处把 (D) 逐项取值,

$$
u_{xx}\left(x,0\right)=2L^{\frac{1}{2}}+2x\left(-\frac{L^{-\frac{1}{2}}}{x}\right)-2L^{-\frac{1}{2}}-x^{3}\left(\frac{L^{-\frac{3}{2}}}{x^{4}}-\frac{2L^{-\frac{1}{2}}}{x^{4}}\right)=2L^{\frac{1}{2}}-3L^{-\frac{1}{2}}-L^{-\frac{3}{2}}.\tag{E}
$$

第十步: 当 $x\to0^{+}$ 时 $L\to+\infty$, 而 $L^{-\frac{1}{2}},L^{-\frac{3}{2}}\to0$, 故由 (E) 得 $u_{xx}\left(x,0\right)=2L^{\frac{1}{2}}+o\left(1\right)\to+\infty$. 于是 $u_{xx}$ 在原点附近无界, $u$ 不可能有二阶连续导数, 即 $u\notin{C}^{2}\left(B_{1/2}\right)$.

注: 第九, 十步的现象与 (C) 并不矛盾. (C) 中 $u_{xx},u_{yy}$ 各含一个发散项 $2L^{\frac{1}{2}}$ 与 $-2L^{\frac{1}{2}}$, 二者在 $\Delta{u}$ 中抵消, 故 $\Delta{u}=f$ 在原点附近有界.

## 习题 2.2 (Emden-Fowler 变换)

设 $u\in{C}^{2}\left(\mathbb{R}^{n}\right)$ 是径向对称函数, 其中 $n\ge3$. 作 Emden-Fowler 变换

$$
v\left(t\right)=r^{\frac{2}{p-1}}u\left(\left|x\right|\right),\qquad{t}=-\ln\left|x\right|,\qquad{p}>1.
$$

试证明: $\Delta{u}=\mathrm{e}^{\frac{2pt}{p-1}}\left(v''+av'-bv\right)$, 其中 $a=\frac{n-2}{p-1}\left(\frac{n+2}{n-2}-p\right)$, $b=\frac{4p}{\left(p-1\right)^{2}}-\frac{2n}{p-1}$.

### 解答 2.2

第一步: 换回旧变量. 由 $t=-\ln{r}$, $r=\mathrm{e}^{-t}$, 且题设 $v\left(t\right)=r^{\frac{2}{p-1}}u\left(r\right)$ 等价于

$$
U\left(r\right)=u\left(r\right)=\mathrm{e}^{\frac{2t}{p-1}}v\left(t\right),\qquad{r}=\mathrm{e}^{-t}.\tag{A}
$$

由**习题 1.1 (径向函数的拉普拉斯算子)**, $\Delta{u}=U''\left(r\right)+\frac{n-1}{r}U'\left(r\right)$. 于是只需把 $U$ 关于 $r$ 的导数换成关于 $t$ 的导数.

第二步: 求 $U'\left(r\right)$. 由 $\frac{\mathrm{d}t}{\mathrm{d}r}=-\frac{1}{r}=-\mathrm{e}^{t}$,

$$
U'\left(r\right)=\left(\frac{2}{p-1}\mathrm{e}^{\frac{2t}{p-1}}v+\mathrm{e}^{\frac{2t}{p-1}}v'\right)\left(-\mathrm{e}^{t}\right)=-\mathrm{e}^{\frac{p+1}{p-1}t}\left(\frac{2}{p-1}v+v'\right).\tag{B}
$$

第三步: 求 $U''\left(r\right)$. 对 (B) 再用链式法则, 乘以 $-\mathrm{e}^{t}$ 并对 $t$ 求导,

$$
\begin{aligned}
U''\left(r\right)&=\mathrm{e}^{t}\left[\frac{p+1}{p-1}\mathrm{e}^{\frac{p+1}{p-1}t}\left(\frac{2}{p-1}v+v'\right)+\mathrm{e}^{\frac{p+1}{p-1}t}\left(\frac{2}{p-1}v'+v''\right)\right]\\
&=\mathrm{e}^{\frac{2p}{p-1}t}\left[v''+\left(\frac{p+1}{p-1}+\frac{2}{p-1}\right)v'+\frac{2\left(p+1\right)}{\left(p-1\right)^{2}}v\right]\\
&=\mathrm{e}^{\frac{2p}{p-1}t}\left[v''+\frac{p+3}{p-1}v'+\frac{2\left(p+1\right)}{\left(p-1\right)^{2}}v\right].\tag{C}
\end{aligned}
$$

第四步: 把 (B), (C) 与 $1/r=\mathrm{e}^{t}$ 代入 $\Delta{u}=U''+\frac{n-1}{r}U'$,

$$
\begin{aligned}
\Delta{u}&=\mathrm{e}^{\frac{2p}{p-1}t}\left[v''+\frac{p+3}{p-1}v'+\frac{2\left(p+1\right)}{\left(p-1\right)^{2}}v\right]-\left(n-1\right)\mathrm{e}^{\frac{2p}{p-1}t}\left[v'+\frac{2}{p-1}v\right]\\
&=\mathrm{e}^{\frac{2p}{p-1}t}\left[v''+\left(\frac{p+3}{p-1}-\left(n-1\right)\right)v'+\left(\frac{2\left(p+1\right)}{\left(p-1\right)^{2}}-\frac{2\left(n-1\right)}{p-1}\right)v\right].\tag{D}
\end{aligned}
$$

第五步: 化简两个系数. 由 $\left(n-1\right)\left(p-1\right)=np-n-p+1$,

$$
\frac{p+3}{p-1}-\left(n-1\right)=\frac{p+3-np+n+p-1}{p-1}=\frac{n+2-p\left(n-2\right)}{p-1}=\frac{n-2}{p-1}\left(\frac{n+2}{n-2}-p\right)=a,
$$

$$
\frac{2\left(p+1\right)}{\left(p-1\right)^{2}}-\frac{2\left(n-1\right)}{p-1}=\frac{2p+2-2\left(np-n-p+1\right)}{\left(p-1\right)^{2}}=\frac{4p-2np+2n}{\left(p-1\right)^{2}}=\frac{4p}{\left(p-1\right)^{2}}-\frac{2n}{p-1}=b.
$$

把它代回 (D), 即得

$$
\Delta{u}=\mathrm{e}^{\frac{2pt}{p-1}}\left(v''+av'-bv\right),
$$

其中 $a,b$ 如题设.
