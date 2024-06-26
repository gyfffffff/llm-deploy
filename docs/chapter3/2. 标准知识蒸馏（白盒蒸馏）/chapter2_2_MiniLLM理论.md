# MiniLLM

## KL散度
了解传统知识蒸馏的同学应该对KL散度并不陌生，这里我们再复习一下它的概念：
老师分布为p, 学生分布为$q_\theta$, 

前向KL散度可以看成是定义了分布之间的一种除法，p除以q，是 $KL(p||q_\theta) = \sum_i p(i)ln(p(i)/q(i))$。一般都要最小化KL散度。

从定义可以看出，在p分布为0的地方，q分布无论为多少，都不影响这一项为0，所以前向KL散度的一个特点是p会在老师分布小的地方比较大。对应到大模型生成上，就是在老师模型输出可能性很小的地方，学生模型却放大了这种可能性，显然这是不对的。

## 逆向KL散度

