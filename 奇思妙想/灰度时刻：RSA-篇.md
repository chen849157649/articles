---
title: 灰度时刻：RSA 篇
tags:
  - rsa
  - todo
categories:
  - 奇思妙想
date: 2019-06-22 12:12:38
---

## 对称加密算法

（1）甲方选择某一种加密规则，对信息进行加密；
（2）乙方使用同一种规则，对信息进行解密。

> 由于加密和解密使用同样规则（简称"密钥"），这被称为"对称加密算法"（Symmetric-key algorithm）。

## 非对称加密

（1）乙方生成两把密钥（公钥和私钥）。公钥是公开的，任何人都可以获得，私钥则是保密的。
（2）甲方获取乙方的公钥，然后用它对信息加密。
（3）乙方得到加密后的信息，用私钥解密。

> 例子：故剑情深
> 汉宣帝（乙方）下诏寻找一把旧时用过的剑**公钥：表面的意思**。有细心的大臣（甲方）看到诏书（获取公玥），明白宣帝是想立许平君为皇后，于是连夜写了一封奏表，劝立许平君（用公钥进行加密大臣的奏表）。宣帝看到奏表后，（用私钥**宣帝真实的想法**解密）知道这个大臣已经明白了他的意思。宣帝把奏表批阅后发还大臣，大臣确认自己和皇帝的想法一致，知道这事有谱了。
> 宣帝：公玥，私钥->客户端
> 大臣：公玥->主机

## 互质关系

最大公约数为1

## 欧拉函数

> 任意给定正整数$n$，请问在小于等于$n$的正整数之中，有多少个与$n$构成互质关系？（比如，在1到8之中，有多少个数与8构成互质关系？）

计算这个值的方法就叫做欧拉函数，以$\varphi(n)$表示。

1. $n = 1$, $\varphi(1) = 1$
2. 如果$n$是质数，则 $\varphi(n) = n - 1$ ，因为质数与小于它的每个数都是互质关系
3. 如果$n$是质数的某个次方，即 $n = p^k$，则
$$
\varphi\left(p^{k}\right)=p^{k}-p^{k-1}=p^{k}\left(1-\frac{1}{p}\right)
$$
4. 如果$n$可以分解成两个互质的整数$p_1, p_2$之积
$$
\varphi(n) = \varphi(p_1 p_2) = \varphi(p_1) \varphi(p_2)
$$
5. 大于1的整数都可以写成一系列质数的积。
$$
n=p_{1}^{k 1} p_{2}^{k 2} \dots p_{r}^{k r}
$$
$$
\varphi(n)=\varphi\left(p_{1}^{k_{1}}\right) \varphi\left(p_{2}^{k_{2}}\right) \ldots \varphi\left(p_{r}^{k_{r}}\right)
$$
$$
\varphi(n)=p_{1}^{k_{1}} p_{2}^{k 2} \ldots p_{r}^{k r}\left(1-\frac{1}{p_{1}}\right)\left(1-\frac{1}{p_{2}}\right) \dots\left(1-\frac{1}{p_{r}}\right)
$$
$$
\varphi(n)=n\left(1-\frac{1}{p_{1}}\right)\left(1-\frac{1}{p_{2}}\right) \ldots\left(1-\frac{1}{p_{r}}\right)
$$

## 欧拉定理

## 模反元素

## 密钥生成的步骤

> 如何下诏？

1. 随机选择两个不相等的质数$p$和$q$
2. 计算$p, q$的乘积$n$，$n$转成二进制的长度就是密玥长度
3. 计算$n$的欧拉函数$\varphi(n)$

- TODO: 坑啦，太难了，回头写 -
