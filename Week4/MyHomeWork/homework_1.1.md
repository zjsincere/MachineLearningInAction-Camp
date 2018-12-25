# 写出并解释逻辑回归的损失函数，并推导参数$w$的梯度下降公式
&emsp;&emsp;根据《统计学习方法》第6章中6.1节介绍，下面对损失函数以及参数$w$的梯度下降公式的推导：  
$Sigmoid$函数为：  
$$g(z)=\frac{1}{1+e^{-z}}$$
给定一个样本$x$，可以使用一个线性函数对自变量进行线性组合
$$z=w_0+w_1x_1+w_2x_2+\dots+w_nx_n=\sum_{i=0}^{n}w_ix_i=w^TX$$
根据$sigmoid$函数，预测函数表达式为：  
\begin{align*}
&h_w(x)=g(w^TX)=\frac{1}{1+e^{-w^TX}} \\\\
&P(Y=1|X)=h_w(x) \\\\
&P(Y=0|X)=1-h_w(x) \\\\
&P(Y|X)=h_w(x)^y(1-h_w(x))^{1-y}
\end{align*}
极大似然函数：
\begin{align*}
&L(w)=\prod_{i=1}^mh_w(x_i)^y_i(1-h_w(x_i))^{1-y_i} \\\\
logL(w)&=\sum_{i=1}^mlog[h_w(x_i)^yi(1-h_w(x_i))^{1-y_i}] \\\\ 
& = \sum_{i=1}^m[y_ilogh_w(x_i)+(1-y_i)log(1-h_w(x_i))]
\end{align*}
损失函数：  
\begin{align*}
J(w)&=-\frac{1}{m}\sum_{i=1}^m[y_i \cdot logh_w(x)+(1-y_i)log(1-h_w(x_i))] \\\\
&=-\frac{1}{m}sum_{i=1}^m[y_i \cdot ln \frac{1}{1+e^{wx_i}}+(1-y_i) \cdot ln \frac{e^{-wx_i}}{1+e^{-wx_i}}] \\\\
&=-\frac{1}{m}sum_{i=1}^m[ln \frac{1}{1+e^{wx_i}}+y_i \cdot ln \frac{1}{e^{-wx_i}}] \\\\
&=\frac{1}{m}\sum_{i=1}{m}[-wx_iy_i+ln(1+e^{wx_i})]
\end{align*}
梯度下降$w$参数的梯度为：  
\begin{align*}
\frac{\partial J(w)}{\partial w_i}&=\frac{1}{m}\sum_i^m[-x_{i,j}y_i+\frac{x_{i,j} \cdot e^{wx_i}}{1+e^{wx_i}}] \\\\
&=\frac{1}{m}\sum_i^mx_{i,j}(\frac{1}{1+e^{-wx_i}}-y_i) \\\\
&=\frac{1}{m}\sum_i^m[h_w(x_i)-y_i]x_{i,j}
\end{align*}
所以最后的$w$参数公式为：  
$$w_{j+1}=w_j-\alpha\sum_{i=1}^m[h_w(x_i)-y_i]x_{i,j}$$
对于随机梯度下降的$w$参数公式为：  
$$w_{j+1}=w_j-\alpha[h_w(x)-y]x_j$$






