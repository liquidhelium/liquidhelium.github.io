---
title: 你在玩一种很新的解氢原子方程
---
> 观前提示: 这里没完整解出来, 甚至关于半径的一部分函数都没有, 只解出来能量量子化条件((
> 鉴定为纯纯普通高中生
<!--More-->
首先请出我们的大神, 薛定谔方程 (定态) :
$$ \hat H \phi = E \phi $$
其中 $$ \hat H=-\frac{\bar h^2}{2m}\nabla^2+V$$
是哈密顿算符 (从知乎复制\\(\\LaTeX\\)警告), \\(E\\)是势能函数，而\\(\phi\\)是波函数.
首先得把这个可恶的\\(\nabla\\)化成球坐标, 不然有我们折腾的...然而经过一番与物竞大佬的讨论, 发现硬算不太切合实际, 而我们又都不知道简便方法。遂抄《普通物理学》（（  

代入氢原子周围势能函数\\(E(r) = -\frac{ke}{r^2}\\)，便得到一个很恐怖的式子：
$$\frac 1 {r^2} \frac \partial {\partial r} \left \( r^2 \frac {\partial \phi} {\partial r}\right \) + \frac 1 {r^2 sin \theta} \frac  \partial  {\partial \theta} \left \( sin \theta \frac {\partial \phi} {\partial \theta}\right \) + \frac 1 {r^2 sin^2 \theta }\frac {\partial^2 \phi} {\partial^2 \varphi}\frac {2m} {\hbar}\left \( E+ \frac {e^2}{4\pi \epsilon_0 r}\right \) \phi = 0$$

真服了，打这个公式你知道花了我多长时间吗。。。快一个小时。。。看看下面的代码：
```latex
$$\frac 1 {r^2} \frac \partial {\partial r} \left \( r^2 \frac {\partial \phi} {\partial r}\right \) + \frac 1 {r^2 sin \theta} \frac  \partial  {\partial \theta} \left \( sin \theta \frac {\partial \phi} {\partial \theta}\right \) + \frac 1 {r^2 sin^2 \theta }\frac {\partial^2 \phi} {\partial^2 \varphi}\frac {2m} {\hbar}\left \( E+ \frac {e^2}{4\pi \epsilon_0 r}\right \) \phi = 0$$
```
回归正题，虽然下面还得打三个同样长的东西吧。。。那干脆暂时鸽一下，明天再来（