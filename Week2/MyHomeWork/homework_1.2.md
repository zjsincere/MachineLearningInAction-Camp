在构建一个决策树模型时，我们对某个属性分割节点，下面四张图中，哪个属性对应的信息增益最大？
![](https://i.imgur.com/63M5WVD.png)

解答：根据李航《统计学习方法》中，对信息增益有如下定义：特征\\(A\\)对训练数据集\\(D\\)的信息增益为 \\(g(D,A)\\)，定义为集合\\(D\\)的经验熵 \\(H(D)\\)与特征A给定条件下D的经验条件熵\\(H(D|A)\\)之差，即
$$g(D,A) = H(D) - H(D|A)$$
从图中可以看到一共有14条数据，其中结果为yes的有9条，为no的有5条，故可以计算经验熵\\(H(D)\\)：
\begin{align*}
H(D) & = -\frac{9}{14}log\left(\frac{9}{14}\right)-\frac{5}{14}log\left(\frac{5}{14}\right) \\\\
 & = 0.6518
\end{align*}
从左边到右，从上到下分别为图一、图二、图三、图四。  
图一中，经验条件熵\\(H(D|A)\\)为：
\begin{align*}
H(D|A) & = \frac{5}{14}\left(-\frac{2}{5}log\left(\frac{2}{5}\right)-\frac{3}{5}log\left(\frac{3}{5}\right)\right) \\\\
 & + \frac{4}{14}\left(-1 \cdot log(1)-0\right) \\\\
 & + \frac{5}{14}\left(-\frac{3}{5}log\left(\frac{3}{5}\right)-\frac{2}{5}log\left(\frac{2}{5}\right)\right) \\\\
 & = 0.4807
\end{align*}
图一中的信息增益为：  
\begin{align*}
g(D,A) & = H(D) - H(D|A) = 0.6518 - 0.4807 \\\\
 & = 0.1711
\end{align*}
图二中，经验条件熵\\(H(D|A)\\)为：
\begin{align*}
H(D|A) & = \frac{7}{14}\left(-\frac{3}{7}log\left(\frac{3}{7}\right)-\frac{4}{7}log\left(\frac{4}{7}\right)\right) \\\\
 & + \frac{7}{14}\left(-\frac{6}{7}log\left(\frac{6}{7}\right)-\frac{1}{7}log\left(\frac{1}{7}\right)\right) \\\\
 & = 0.5465
\end{align*}
图二中的信息增益为：  
\begin{align*}
g(D,A) & = H(D) - H(D|A) = 0.6518 - 0.5465 \\\\
 & = 0.1053
\end{align*}
图三中，经验条件熵\\(H(D|A)\\)为：
\begin{align*}
H(D|A) & = \frac{8}{14}\left(-\frac{6}{8}log\left(\frac{6}{8}\right)-\frac{2}{8}log\left(\frac{2}{8}\right)\right) \\\\
 & + \frac{6}{14}\left(-\frac{3}{6}log\left(\frac{3}{6}\right)-\frac{3}{6}log\left(\frac{3}{6}\right)\right) \\\\
 & = 0.6184
\end{align*}
图三中的信息增益为：  
\begin{align*}
g(D,A) & = H(D) - H(D|A) = 0.6518 - 0.6184 \\\\
 & = 0.0334
\end{align*}
图四中，经验条件熵\\(H(D|A)\\)为：
\begin{align*}
H(D|A) & = \frac{4}{14}\left(-\frac{2}{4}log\left(\frac{2}{4}\right)-\frac{2}{4}log\left(\frac{2}{4}\right)\right) \\\\
 & + \frac{6}{14}\left(-\frac{4}{6}log\left(\frac{4}{6}\right)-\frac{2}{6}log\left(\frac{2}{6}\right)\right) \\\\
 & + \frac{4}{14}\left(-\frac{3}{4}log\left(\frac{3}{4}\right)-\frac{1}{4}log\left(\frac{1}{4}\right)\right) \\\\
 & = 0.6315
\end{align*}
图四中的信息增益为：  
\begin{align*}
g(D,A) & = H(D) - H(D|A) = 0.6518 - 0.6315 \\\\
 & = 0.0203
\end{align*}
可以得到，图一的信息增益最大