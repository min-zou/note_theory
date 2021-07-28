<!--
 * @Author: your name
 * @Date: 2021-07-28 14:57:20
 * @LastEditTime: 2021-07-28 14:58:51
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /undefined/home/eco/Downloads/slam_test/filter/cn.md
-->
# 1. 四元数的性质和定义

## 1.1 四元数的定义

cayley-dickson给出四元数的一种定义，即存在两个复数
<!-- $ c = \sqrt{a^{2}+b_{xy}^{2}+e^{x}} $
$$ c = \sqrt{a^{2}+b_{xy}^{2} +e^{x}} $$ -->
$ A = a + bi $ 和$ C = c+di$然后即可构造出$Q=A+Cj$ 并且定义$k \triangleq ij$，即可得四元数空间$\mathbb{H}$下的一个数
$$ Q = a+bi+cj+dk\in \mathbb{H} (1)$$
其中$\{a,b,c,d\}\in \mathbb{R}$,$\{i,j,k\}$这三个虚数单位有如下性质：
$$ i^2=j^2=k^2=ijk=-1, $$
同时可以得到：
$$ ij=-ji=k, jk=-kj=i, ki=-ik=j. $$
从式（1），我们可以在四元数定义中嵌入虚数也就是实数和虚数，也即实数、虚数和复数均为四元数，
$$ 
   Q =a \in \mathbb{R} \subset \mathbb{H},
   \\Q =bi \in \mathbb{I} \subset \mathbb{H},
   \\Q =a+bi \in \mathbb{Z} \subset \mathbb{H}.
$$
同样的，可以在$\mathbb{H}$的三维空间子集中定义纯虚数以示完备性，同时记$\mathbb{H}_p = Im(\mathbb{H})$为纯虚数空间，
$$
    Q = bi+cj+dk \in \mathbb{H}_p \subset\mathbb{H}.   (4)
$$
需要注意的是，类比常规单位长度复数$z=\textbf{e}^{i\theta}$能够表征二维平面下的旋转（用一个复数积，即$x{'}=zx$),扩展的复数或单位长度的四元数$\textbf{q}=e^{(u_xi+u_yj+u_zk)\theta/2}$可以表征三维空间下的旋转（用双四元数积，即$x{'}=q\otimes{x}\otimes{q}^{*}$),
后续会详细解释。
$\textbf{注意：}$ 并非所有四元数的定义都相同，有些论文将$bi$写作$ib$，也因此可以得到$k=ji=-ij，ijk=1$，也即左手坐标系下的四元数。
此外，实部和虚部位置也存在不同，比如会有$Q=ia+kc+d$。这些写法区别没啥其他根本含义，不过会使得公式会有所区别。具体可以参看第三节的解释。
$\textbf{注意：}$还有一些其他约定也会使得公式会有所不同。它们涉及我们赋予旋转运算子的“意义”或“解释”，无论是旋转向量还是旋转参考系——实质上，它们构成了相反的运算。同样请参阅第3节以获得进一步的解释。
$\textbf{注：}$在上述不同的约定中，本文主要涉及了Hamilton约定，其最显著的特性是定义（2）。具体消除歧义的方法被归入第三节。

### 1.1.1 四元数表示
实数+虚数表示法$\{1,i,j,k\}$不一定总是符合我们要求。若使用式(2)，即可将其表示为标量和矢量的和，
$$
    Q=q_w+q_xi+q_yj+q_zk \Leftrightarrow  Q=q_w+\textbf{q}_v  (5)
$$
其中$q_w$指实部或标量，$\textbf{q}_v = q_xi+q_yj+q_zk=(q_x,q_y,q_z)$为虚部或矢量。同时也可定义为标量和矢量的有序对。
$$
    Q=\left \langle q_w,\textbf{q}_v \right \rangle (6)
$$
通常将一个四元数表示为一个四维量$\textbf{q}$,
$$
\textbf{q} \triangleq \begin{bmatrix}q_w\\\textbf{q}_v 
\end{bmatrix} = 
\begin{bmatrix}q_w\\q_x \\q_y\\q_z
\end{bmatrix} (7)
$$

