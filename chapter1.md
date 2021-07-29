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
$$ Q = a+bi+cj+dk\in \mathbb{H} (1)
$$其中$\{a,b,c,d\}\in \mathbb{R}$,$\{i,j,k\}$这三个虚数单位有如下性质：
$$ i^2=j^2=k^2=ijk=-1, 
$$同时可以得到：
$$ ij=-ji=k, jk=-kj=i, ki=-ik=j. 
$$从式（1），我们可以在四元数定义中嵌入虚数也就是实数和虚数，也即实数、虚数和复数均为四元数，
$$ 
   Q =a \in \mathbb{R} \subset \mathbb{H},
   \\Q =bi \in \mathbb{I} \subset \mathbb{H},
   \\Q =a+bi \in \mathbb{Z} \subset \mathbb{H}.
$$同样的，可以在$\mathbb{H}$的三维空间子集中定义纯虚数以示完备性，同时记$\mathbb{H}_p = Im(\mathbb{H})$为纯虚数空间，
$$
    Q = bi+cj+dk \in \mathbb{H}_p \subset\mathbb{H}.   (4)
$$需要注意的是，类比常规单位长度复数$z=\textbf{e}^{i\theta}$能够表征二维平面下的旋转（用一个复数积，即$x{'}=zx$),扩展的复数或单位长度的四元数$\textbf{q}=e^{(u_xi+u_yj+u_zk)\theta/2}$可以表征三维空间下的旋转（用双四元数积，即$x{'}=q\otimes{x}\otimes{q}^{*}$),
后续会详细解释。
$\textbf{注意：}$ 并非所有四元数的定义都相同，有些论文将$bi$写作$ib$，也因此可以得到$k=ji=-ij，ijk=1$，也即左手坐标系下的四元数。
此外，实部和虚部位置也存在不同，比如会有$Q=ia+kc+d$。这些写法区别没啥其他根本含义，不过会使得公式会有所区别。具体可以参看第三节的解释。
$\textbf{注意：}$还有一些其他约定也会使得公式会有所不同。它们涉及我们赋予旋转运算子的“意义”或“解释”，无论是旋转向量还是旋转参考系——实质上，它们构成了相反的运算。同样请参阅第3节以获得进一步的解释。
$\textbf{注：}$在上述不同的约定中，本文主要涉及了Hamilton约定，其最显著的特性是定义（2）。具体消除歧义的方法被归入第三节。

### 1.1.1 四元数表示
实数+虚数表示法$\{1,i,j,k\}$不一定总是符合我们要求。若使用式(2)，即可将其表示为标量和矢量的和，
$$
    Q=q_w+q_xi+q_yj+q_zk \Leftrightarrow  Q=q_w+\textbf{q}_v  (5)
$$其中$q_w$指实部或标量，$\textbf{q}_v = q_xi+q_yj+q_zk=(q_x,q_y,q_z)$为虚部或矢量。同时也可定义为标量和矢量的有序对。
$$
    Q=\left \langle q_w,\textbf{q}_v \right \rangle (6)
$$
通常将一个四元数表示为一个四维量$\textbf{q}$,
$$
\textbf{q} \triangleq \begin{bmatrix}q_w\\\textbf{q}_v 
\end{bmatrix} = 
\begin{bmatrix}q_w\\q_x \\q_y\\q_z
\end{bmatrix} (7)
$$这样我们就可以用矩阵代数来处理四元数的运算。在某些情况下，我们可能允许自己用“$=$”来混合表示。典型实例为四元数和纯四元数，
$$
general: \textbf{q} = q_w+\textbf{q}_v = \begin{bmatrix}q_w\\\textbf{q}_v 
\end{bmatrix} \in \mathbb{H},
real: q_w = \begin{bmatrix}q_w\\\textbf{0}_v 
\end{bmatrix} \in \mathbb{R},
pure: \textbf{q}_v = \begin{bmatrix}0\\\textbf{q}_v 
\end{bmatrix} \in \mathbb{H}_p.
(8)
$$
## 1.2 四元数的主要性质
### 1.2.1 和
求和很简单，
$$
\textbf{p} \textbf{q} = \begin{bmatrix}p_w\\\textbf{p}_v 
\end{bmatrix} \pm \begin{bmatrix}q_w\\\textbf{q}_v 
\end{bmatrix} = \begin{bmatrix}p_w \pm q_w\\\textbf{p}_v \pm \textbf{q}_v 
\end{bmatrix}
$$满足交换律和合并律，
$$
\textbf{p}+\textbf{q} = \textbf{q} + \textbf{p}
\\
\textbf{p} + (\textbf{q}+\textbf{r}) = (\textbf{p}+\textbf{q})+ \textbf{r}.
$$
###1.2.2 积
符号定义为$\otimes$，四元数积使用式(1)和代数式(2),以向量形式给出：
$$
\textbf{p}\otimes \textbf{q} = \begin{bmatrix}p_wq_w-p_xq_x-p_yq_y-p_zq_z\\p_wq_x+p_xq_w+p_yq_z-p_zq_y\\
p_wq_y-p_xq_z+p_yq_w+p_zq_x\\
p_wq_z+p_xq_y-p_yq_x+p_zq_w\end{bmatrix}
$$上式可用标量和向量形式写作：
$$
\textbf{p}\otimes\textbf{q} = \begin{bmatrix}
p_wq_w-\textbf{p}_{v}^{\top}\textbf{q}_v\\
p_w\textbf{q}_v+q_w\textbf{p}_v+\textbf{p}_v\times\textbf{q}_v\end{bmatrix}
$$同时上式表明四元数积不满足交换律，即：
$$
\textbf{p}\otimes\textbf{q}\neq\textbf{q}\otimes\textbf{p}  
$$
需要指出当$\textbf{p}_v\times\textbf{q}_v=0$时，应当知道其中一个四元数虚部为0,为实四元数即$\textbf{p}=p_w$或者$\textbf{q}=q_w$，或者还有一种情况即两个向量部分为平行，即$\textbf{p}_v\parallel\textbf{q}_v$，只有当上述情况出现时，才可以认为四元数积满足交换律。
不过四元数是满足结合律的，即有：
$$
(\textbf{q}\otimes\textbf{q})\otimes\textbf{r}=\textbf{p}\otimes(\textbf{q}\otimes\textbf{r}),
$$同时有和分配律，
$$
\textbf{p}\otimes(\textbf{q}+\textbf{r}) = \textbf{p}\otimes\textbf{q}+\textbf{p}\otimes\textbf{r} 和 
(\textbf{p}+\textbf{q})\otimes\textbf{r} = \textbf{p}\otimes\textbf{r}+\textbf{q}\otimes\textbf{r}.
$$两个四元数乘积为双线线且可以表示为两个相等的矩阵积，如下：
$$
\textbf{q}_1\otimes\textbf{q}_2 = \left [ \textbf{q}_1\right ] _{L}\textbf{q}_2 和 \textbf{q}_1\otimes\textbf{q}_2 = \left [ \textbf{q}_2\right ] _{R}\textbf{q}_1
$$其中$\left[\textbf{q} \right ] _{L}$和$\left[\textbf{q} \right ] _{R}$表示左右四元数乘积矩阵，可通过式(12)和(17)得到：
$$
\left[\textbf{q} \right ] _{L} = \begin{bmatrix}
q_w&-q_x&-qy&-q_z\\q_x&q_w&-q_z&q_y\\
q_y&q_z&q_w&-q_x\\q_z&-q_y&q_x&q_w\end{bmatrix}, 
\left[\textbf{q} \right ] _{R} = \begin{bmatrix}
q_w&-q_x&-qy&-q_z\\q_x&q_w&q_z&-q_y\\
q_y&-q_z&q_w&q_x\\q_z&q_y&-q_x&q_w\end{bmatrix}, 
$$简洁些表示如下：
$$
\left[\textbf{q} \right ] _{L} = q_w\textbf{I}+\begin{bmatrix}0&-\textbf{q}_v^{\top}\\ \textbf{q}_v &\left[\textbf{q}_v \right] _{times}\end{bmatrix},
\left[\textbf{q} \right ] _{R} = q_w\textbf{I}+\begin{bmatrix}0&-\textbf{q}_v^{\top}\\
\textbf{q}_v&-\left[\textbf{q}_v \right] _{times}\end{bmatrix}.
$$这里反对称操作$\left[\cdot \right] _{times}$可以生成叉积矩阵。
$$
\left[a \right] _{times} \triangleq b = a \times b,\forall a,b \in \mathbb{R}^3
$$最后，由
$$
(\textbf(q)\otimes\textbf{x})\otimes\textbf{p}= \left[\textbf{p} \right] _{R}\left[\textbf{q} \right] _{L}X
和 \textbf{q}\otimes(\textbf{x}\otimes\textbf{p}) = \left[\textbf{q} \right] _{L} \left[\textbf{p} \right] _{R}X
$$可得：
$$
\left[\textbf{p} \right] _{R}\left[\textbf{q} \right] _{L}
= \left[\textbf{q} \right] _{L}\left[\textbf{p} \right] _{R}
$$也就是说左四元数积和右四元数积矩阵可以相互转换，2.8节有更详细的内容。
具有乘积运算$\otimes$的四元数构成非交换集，集合的元素同一性，恒等式$\textbf{q}_1 = 1$，逆，后文会提到。

### 1.2.3 


### 1.2.4 共轭
四元数共轭可以定义为：
$$
\textbf{q}^{*} \triangleq q_w - \textbf{q}_v = \begin{bmatrix}
    q_w\\-\textbf{q}_v
\end{bmatrix}
$$即有以下性质：
$$
\textbf{q}\otimes\textbf{q}^* = \textbf{q}^*\otimes\textbf{q}=
q_w^2+q_x^2+q_y^2+q_z^2 = \begin{bmatrix}
    q_w^2+q_x^2+q_y^2+q_z^2\\
    \textbf{0}_v
\end{bmatrix}
$$和
$$
(\textbf{p}\otimes\textbf{q})^* = \textbf{q}^* \otimes\textbf{p}^{*}
$$

### 1.2.5 范数
四元数的范数可以定义为：
$$
\textbf{q}\otimes\textbf{q}^(-1) = \textbf{q}^{-1}\otimes\textbf{q} = q_1.
$$可计算：
$$
\textbf{q}^{-1} = \textbf{q}^* / \left \| \textbf{q} \right \| ^2.
$$将单位四元数解释为方向规范或旋转运算时，意味着可以使用共轭四元数实现反转。单位四元数可以写作：
$$
\textbf{q} = \begin{bmatrix}
    \cos\theta \\
    \textbf{u}\sin\theta
\end{bmatrix}
$$其中$\textbf{u} = u_xi+u_yj+u_zk$为单位向量，$\theta$为常量。
如(28),具有乘积运算的单位四元数构成一个非交换集，其中逆和共轭相同。

## 1.3 其他性质
### 1.3.1 

