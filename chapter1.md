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