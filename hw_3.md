# 概率论第三次作业

## Problem 1(Warm-up Problems)

211240042 林凡琪

- [**Variance (I)**] Let $\displaystyle{ X_1,X_2,\cdots, X_n }$ be pairwise independent random variables. Show that $\displaystyle{ \textbf{Var}\left[\sum_{i=1}^n X_i\right] =\sum_{i=1}^n \textbf{Var} [X_i] }$ .

  Proof:

  Let $\displaystyle{ Y=\sum_{i=1}^n X_i }$. Then, we have:

  $$\begin{aligned} \textbf{Var}[Y] &= \textbf{E}[Y^2] - \textbf{E}[Y]^2 \\ &= \textbf{E}\left[\left(\sum_{i=1}^n X_i\right)^2\right] - \left(\textbf{E}\left[\sum_{i=1}^n X_i\right]\right)^2 \\ &= \textbf{E}\left[\sum_{i=1}^n X_i^2 + 2\sum_{i<j}X_iX_j\right] - \left(\sum_{i=1}^n \textbf{E}[X_i]\right)^2 \\ &= \sum_{i=1}^n \textbf{E}[X_i^2] + 2\sum_{i<j}\textbf{E}[X_iX_j] - \left(\sum_{i=1}^n \textbf{E}[X_i]\right)^2. \end{aligned}$$

  Since $\displaystyle{ X_1,X_2,\cdots, X_n }$ are pairwise independent, we have $\displaystyle{ \textbf{E}[X_iX_j]=\textbf{E}[X_i]\textbf{E}[X_j] }$ for $\displaystyle{i\neq j}$.

  Substituting this into the above equation, we get:

  $$\begin{aligned} \textbf{Var}[Y] &= \sum_{i=1}^n \textbf{E}[X_i^2] + 2\sum_{i<j}\textbf{E}[X_i]\textbf{E}[X_j] - \left(\sum_{i=1}^n \textbf{E}[X_i]\right)^2 \\ &= \sum_{i=1}^n (\textbf{E}[X_i^2]-\textbf{E}[X_i]^2) \\ &= \sum_{i=1}^n \textbf{Var}[X_i]. \end{aligned}$$

  Hence, we have shown that $\displaystyle{\textbf{Var}\left[\sum_{i=1}^n X_i\right] =\sum_{i=1}^n \textbf{Var} [X_i]}$.

- [**Variance (II)**] Each member of a group of $n$ players rolls a (fair) die. For any pair of players who throw the same number, the group scores 1 point. Find the mean and variance of the total score of the group.

  Solution:

  设 $X$ 是这组的总分. 
  $$
  E[X]=\frac{1}{6} \times\left(\begin{array}{l}
  n \\
  2
  \end{array}\right)=\frac{n(n-1)}{12}
  $$
  设 $X_{i, j}$ 表示第 $i$ 个玩家和第 $j$ 个玩家投掷相同数字时该团队得分。则 $X=\sum_{1 \leq i<j \leq n} X_{i, j}$ 
  $$
  \operatorname{Var}[X]=E\left[X^2\right]-E[X]^2
  $$
  $$
  \begin{aligned}
  E\left[X^2\right]&=E\left[\left(\sum_{1 \leq i<j \leq n} X_{i, j}\right)^2\right]\\
  &=E\left[\sum_{1 \leq i<j \leq n} X_{i, j}^2+2 \sum_{1 \leq i<j<k \leq n} X_{i, j} X_{j, k}\right]
  \end{aligned}
  $$
  因为 $X_{i, j}$ 只能取0或 1 , 所以 $X_{i, j}^2=X_{i, j}$
  因此
  $$
  \begin{aligned}
  E\left[X^2\right]&=E\left[\sum_{1 \leq i<j \leq n} X_{i, j}+2 \sum_{1 \leq i<j<k \leq n} X_{i, j} X_{j, k}\right]\\
  &=\sum_{1 \leq i<j \leq n} E\left[X_{i, j}\right]+2 \sum_{1 \leq i<j<k \leq n} E\left[X_{i, j} X_{j, k}\right]+2 \sum_{1 \leq i<j<k<l \leq n} E\left[X_{i, j} X_{k, l}\right]
  \end{aligned}
  $$

  由于每一对玩家得到相同数字的概率为 $\frac{1}{6}$, 则 $E\left[X_{i, j}\right]=\frac{1}{6}$, 又因为三个玩家投到相同数字的概率为 $\frac{1}{6^2}$, 则 $E\left[X_{i, j} X_{j, k}\right]=\frac{1}{36}$, 四个玩家投到相同数字的概率为 $\frac{1}{6^3}$, 则 $E\left[X_{i, j} X_{k, l}\right]=\frac{1}{216}$
  因此, $E\left[X^2\right]=\left(\begin{array}{l}n \\ 2\end{array}\right) \times \frac{1}{6}+2 \times\left(\begin{array}{l}n \\ 3\end{array}\right) \times \frac{1}{36}+2 \times\left(\begin{array}{l}n \\ 4\end{array}\right) \times \frac{1}{216}=\frac{n(n-1)(n^2+19n+174)}{2592}$
  即 $\operatorname{Var}[X]=\left(\begin{array}{l}n \\ 2\end{array}\right) \times \frac{1}{6}+2 \times\left(\begin{array}{l}n \\ 3\end{array}\right) \times \frac{1}{36}+2 \times\left(\begin{array}{l}n \\ 4\end{array}\right) \times \frac{1}{216}-\left(\frac{n(n-1)}{12}\right)^2=\frac{n(n-1)(n^2+19n+174)}{2592}-\left(\frac{n(n-1)}{12}\right)^2$ (此题致谢陈子元同学)

- [**Variance (III)**] An urn contains $n$ balls numbered $\displaystyle{ 1, 2, \ldots, n }$. We select $k$ balls uniformly at random **without replacement** and add up their numbers. Find the mean and variance of the sum.

  Solution:

  Let's define the random variable $\displaystyle{X}$ as the sum of the numbers on the $\displaystyle{k}$ balls selected. We can break down $\displaystyle{X}$ into a sum of indicator random variables $\displaystyle{X_i}$ for $\displaystyle{1\leq i\leq n}$, where $\displaystyle{X_i=i}$ if ball $\displaystyle{i}$ is selected and $\displaystyle{0}$ otherwise.

  Since we are selecting $\displaystyle{k}$ balls uniformly at random without replacement from a total of $\displaystyle{n}$ balls, the probability that any particular ball is selected is $\displaystyle{\frac{k}{n}}$. Therefore, the expected value of each $\displaystyle{X_i}$ is:

  $$\textbf{E}[X_i] = i \cdot \frac{k}{n} + 0 \cdot \left(1-\frac{k}{n}\right) = \frac{ik}{n}.$$

  The expected value of $\displaystyle{X}$ is:

  $$\textbf{E}[X] = \textbf{E}\left[\sum_{i=1}^n X_i\right] = \sum_{i=1}^n \textbf{E}[X_i] = \sum_{i=1}^n \frac{ik}{n} = \frac{k}{n} \sum_{i=1}^n i = \frac{k(n+1)}{2}.$$

  To find the variance of $\displaystyle{X}$, we can use the formula for the variance of a sum of pairwise independent random variables that you mentioned earlier:

  $$\textbf{Var}[X] = \sum_{i=1}^n \textbf{Var}[X_i].$$

  Since $\displaystyle{X_i}$ is an indicator random variable with expected value $\displaystyle{\frac{ik}{n}}$, its variance is:

  $$\textbf{Var}[X_i] = \textbf{E}[X_i^2] - \textbf{E}[X_i]^2 = i^2\cdot\frac{k}{n} - \left(\frac{ik}{n}\right)^2 = i^2\cdot\frac{k}{n} - i^2\cdot\frac{k^2}{n^2} = i^2\cdot\frac{k(n-k)}{n^2}.$$

  Therefore, the variance of $\displaystyle{X}$ is:

  $$\textbf{Var}[X] = \sum_{i=1}^n \textbf{Var}[X_i] = \sum_{i=1}^n i^2\cdot\frac{k(n-k)}{n^2} = \frac{k(n-k)}{n^2}\sum_{i=1}^ni^2 = \frac{k(n-k)(n+1)(2n+1)}{6n}.$$

  So, the mean and variance of the sum are $\displaystyle{\frac{k(n+1)}{2}}$ and $\displaystyle{\frac{k(n-k)(n+1)(2n+1)}{6n}}$, respectively.

- [**Variance (IV)**] Let $N$ be an integer-valued, positive random variable and let $\displaystyle{ \{X_i\}_{i=1}^{\infty} }$ be indepedently identically distributed random variables that are independent of $N$ , too. Precisely, for any finite subset $\displaystyle{ I \subseteq\mathbb{N}_+ }$ and $N$ are mutually independent. Let$\displaystyle{ X = \sum_{i=1}^N X_i }$, show that $\displaystyle{ \textbf{Var}[X] = \textbf{Var}[X_1] \mathbb{E}[N] + \mathbb{E}[X_1]^2 \textbf{Var}[N] }$.

  Proof:

  Let's define the random variable $\displaystyle{X}$ as $\displaystyle{X = \sum_{i=1}^N X_i}$. We can use the law of total variance to find the variance of $\displaystyle{X}$:

  $$\textbf{Var}[X] = \textbf{E}[\textbf{Var}[X|N]] + \textbf{Var}[\textbf{E}[X|N]].$$

  Since $\displaystyle{\{X_i\}_{i=1}^{\infty}}$ are independent and identically distributed, we have:

  $$\textbf{Var}[X|N] = \textbf{Var}\left[\sum_{i=1}^N X_i\right] = N\textbf{Var}[X_1].$$

  Therefore,

  $$\textbf{E}[\textbf{Var}[X|N]] = \textbf{E}[N]\textbf{Var}[X_1].$$

  Also, since $\displaystyle{\{X_i\}_{i=1}^{\infty}}$ are independent and identically distributed, we have:

  $$\textbf{E}[X|N] = \textbf{E}\left[\sum_{i=1}^N X_i\right] = N\textbf{E}[X_1].$$

  Therefore,

  $$\textbf{Var}[\textbf{E}[X|N]] = \textbf{Var}[N]\textbf{E}[X_1]^2.$$

  Substituting these results into the law of total variance, we get:

  $$\begin{aligned} \textbf{Var}[X] &= \textbf{E}[\textbf{Var}[X|N]] + \textbf{Var}[\textbf{E}[X|N]] \\ &= \textbf{E}[N]\textbf{Var}[X_1] + \textbf{Var}[N]\textbf{E}[X_1]^2. \end{aligned}$$

  Hence, we have shown that $\displaystyle{\textbf{Var}[X] = \textbf{Var}[X_1] \mathbb{E}[N] + \mathbb{E}[X_1]^2 \textbf{Var}[N]}$.

- [**Moments (I)**] Find an example of a random variable with finite $j$-th moments for $\displaystyle{ 1 \leq j \leq k }$ but an unbounded $\displaystyle{ (k + 1) }$-th moment. Give a clear argument showing that your choice has these properties.

  Solution:

  One example of a random variable that has finite $\displaystyle{k}$-th moments for $\displaystyle{k<n}$ but an unbounded $\displaystyle{n}$-th moment is a random variable $\displaystyle{X}$ with a probability density function given by:

  $$f_X(x) = \begin{cases} \frac{n}{x^{n+1}} & x\geq 1 \\ 0 & \text{otherwise}. \end{cases}$$

  This is known as a Pareto distribution with shape parameter $\displaystyle{n}$ and scale parameter $\displaystyle{1}$.

  For $\displaystyle{k<n}$, the $\displaystyle{k}$-th moment of $\displaystyle{X}$ is given by:

  $$\textbf{E}[X^k] = \int_{-\infty}^{\infty} x^k f_X(x) dx = \int_{1}^{\infty} x^k \frac{n}{x^{n+1}} dx = n\int_{1}^{\infty} x^{k-n-1} dx.$$

  Since $\displaystyle{k-n-1<-1}$, this integral converges to a finite value:

  $$\textbf{E}[X^k] = n\int_{1}^{\infty} x^{k-n-1} dx = n\left[\frac{x^{k-n}}{k-n}\right]_{1}^{\infty} = \frac{n}{n-k}.$$

  However, for $\displaystyle{k=n}$, the $\displaystyle{n}$-th moment of $\displaystyle{X}$ is given by:

  $$\textbf{E}[X^n] = \int_{-\infty}^{\infty} x^n f_X(x) dx = \int_{1}^{\infty} x^n \frac{n}{x^{n+1}} dx = n\int_{1}^{\infty} dx = \infty.$$

  Therefore, the random variable $\displaystyle{X}$ has finite $\displaystyle{k}$-th moments for $\displaystyle{k<n}$ but an unbounded $\displaystyle{n}$-th moment.

- [**Moments (II)**] Let $\displaystyle{ X\sim \text{Geo}(p) }$ for some $\displaystyle{ p \in (0,1) }$. Find $\displaystyle{ \mathbb{E}[X^3] }$ and $\displaystyle{ \mathbb{E}[X^4] }$.

  Solution:

  Let $\displaystyle{ X\sim \text{Geo}(p) }$ for some $\displaystyle{ p \in (0,1) }$. The moment generating function of $\displaystyle{ X }$ is given by $\displaystyle{ M_X(t) = \frac{pe^t}{1-(1-p)e^t} }$. 

  To find $\displaystyle{ \mathbb{E}[X^3] }$, we differentiate the moment generating function thrice and evaluate it at $\displaystyle{ t=0 }$:
  $$
  \begin{aligned}
  \mathbb{E}[X^3] &= M_X^{(3)}(0) \\
  &= \left.\frac{\mathrm d^3}{\mathrm dt^3}\frac{pe^t}{1-(1-p)e^t}\right|_{t=0} \\
  & =\frac{2 p(1-p)^2}{(1-p)^3}
  \end{aligned}
  $$

  Similarly, to find $\displaystyle{ \mathbb{E}[X^4] }$, we differentiate the moment generating function four times and evaluate it at $\displaystyle{ t=0 }$:
  $$
  \begin{aligned}
  \mathbb{E}[X^4] &= M_X^{(4)}(0) \\
  &= \left.\frac{\mathrm d^4}{\mathrm dt^4}\frac{pe^t}{1-(1-p)e^t}\right|_{t=0} \\
  & =\frac{6 p(1-p)^3+8 p(1-p)^2+2 p(1-p)}{(1-p)^4} \\
  \end{aligned}
  $$

- [**Moments (III)**] Let $\displaystyle{ X\sim \text{Pois}(\lambda) }$ for some $\displaystyle{ \lambda \gt 0  }$ . Find $\displaystyle{ \mathbb{E}[X^3] }$ and $\displaystyle{ \mathbb{E}[X^4] }$.

  Solution:

  Let $\displaystyle{ X\sim \text{Pois}(\lambda) }$ for some $\displaystyle{ \lambda \gt 0  }$. The moment generating function of $\displaystyle{ X }$ is given by $\displaystyle{ M_X(t) = e^{\lambda(e^t-1)} }$. 

  To find $\displaystyle{ \mathbb{E}[X^3] }$, we differentiate the moment generating function thrice and evaluate it at $\displaystyle{ t=0 }$:
  $$
  \begin{aligned}
  \mathbb{E}[X^3] &= M_X^{(3)}(0) \\
  &= \left.\frac{\mathrm d^3}{\mathrm dt^3}e^{\lambda(e^t-1)}\right|_{t=0} \\
  &= \lambda(\lambda +1)(\lambda +2) \\
  \end{aligned}
  $$

  Similarly, to find $\displaystyle{ \mathbb{E}[X^4] }$, we differentiate the moment generating function four times and evaluate it at $\displaystyle{ t=0 }$:
  $$
  \begin{aligned}
  \mathbb{E}[X^4] &= M_X^{(4)}(0) \\
  &= \left.\frac{\mathrm d^4}{\mathrm dt^4}e^{\lambda(e^t-1)}\right|_{t=0} \\
  &= \lambda(\lambda +1)(\lambda +2)(\lambda + 3)
  \end{aligned}
  $$

- [**Covariance and correlation (I)**] Let $X$ and $Y$ be discrete random variables with correlation $\displaystyle{ \rho }$. Show that $\displaystyle{ |\rho|\leq 1 }$ .

  Proof:

  设 $\displaystyle{ X }$ 和 $\displaystyle{ Y }$ 为具有相关系数 $\displaystyle{ \rho }$ 的离散随机变量。

  $\displaystyle{ X }$ 和 $\displaystyle{ Y }$ 的相关系数定义为 $\displaystyle{ \rho = \frac{\text{Cov}(X,Y)}{\sigma_X\sigma_Y} }$。

  根据柯西-施瓦茨不等式，
  $$
  \begin{aligned}
  |\rho| &= \left|\frac{\text{Cov}(X,Y)}{\sigma_X\sigma_Y}\right| \\
  &\leq \frac{\sqrt{\text{Var}(X)}\sqrt{\text{Var}(Y)}}{\sigma_X\sigma_Y} \\
  &= 1
  \end{aligned}
  $$

  
   因此，$\displaystyle{ |\rho|\leq 1 }$。

- [**Covariance and correlation (II)**] 

  Proof:
  $$
  \begin{aligned}
  \mathbb{E}(\max\{X^2,Y^2\}) &= \mathbb{E}\left(\frac{1}{2}(X^2+Y^2+|X^2-Y^2|)\right) \\
  &= \frac{1}{2}\mathbb{E}(X^2+Y^2) + \frac{1}{2}\mathbb{E}(|X^2-Y^2|)
  \end{aligned}
  $$

  由于 $X$ 和 $Y$ 的方差为 1，我们知道 $\mathbb{E}(X^2)=\mathbb{E}(Y^2)=1$。因此，第一项变为 $\frac{1}{2}\mathbb{E}(X^2+Y^2)=1$。对于第二项，我们可以使用柯西-施瓦茨不等式来获得一个上界：

  $$
  \begin{aligned}
  \mathbb{E}(|X^2-Y^2|) &\leq \sqrt{\mathbb{E}((X^2-Y^2)^2)} \\
  &= \sqrt{\mathbb{E}(X^4-2X^2Y^2+Y^4)} \\
  &= \sqrt{\mathbb{E}(X^4)+\mathbb{E}(Y^4)-2\mathbb{E}(X^2Y^2)}
  \end{aligned}
  $$

   $E\left(\left|X^2-Y^2\right|\right)=E\left[\left(X^2-Y^2\right) I_{X^2 \leq Y^2}\right]+E\left[\left(Y^2-X^2\right) I_{X^2<Y^2}\right]$
  由于 X和Y的均值都为 0 , 所以
  $$
  \operatorname{Cov}\left(X^2, Y^2\right)=E\left(X^2 Y^2\right)-E\left(X^2\right) E\left(Y^2\right)=E\left(X^2 Y^2\right)-1
  $$
  

  因此,
  $$
  \begin{aligned}
  E\left(\max \left\{X^2, Y^2\right\}\right)&=\frac{1}{2}\left(2+E\left(\left|X^2-Y^2\right|\right)\right) \\
  &\leq \frac{1}{2}\left(2+2 \sqrt{\left(1-\rho^2\right)}\right)\\
  &=1+\sqrt{1-\rho^2}
  \end{aligned}
  $$
  

  因此, 得证。

  (此题致谢陈子元同学.)

- [**Covariance and correlation (III)**] Construct two random variables $X$ and $Y$ such that their covariance $\textbf{Cov}(X,Y) = 0$ but $X$ and $Y$ are not independent. You should prove your construction is true.

  Solution:

  例子:两个随机变量$X$和$Y$ 它们的协方差 $\textbf{Cov}(X,Y) = 0$ 但 $X$ 和 $Y$ 不是独立的：

  设 $X$ 是一个随机变量，它以相等的概率取值 -1、0 和 1。设 $Y = X^2$。那么，$\textbf{E}[X] = 0$，$\textbf{E}[Y] = \frac{1}{3}(-1)^2 + \frac{1}{3}(0)^2 + \frac{1}{3}(1)^2 = \frac{2}{3}$，且 $\textbf{E}[XY] = \textbf{E}[X^3] = \frac{1}{3}(-1)^3 + \frac{1}{3}(0)^3 + \frac{1}{3}(1)^3 = 0$。因此，$\textbf{Cov}(X,Y) = \textbf{E}[XY] - \textbf{E}[X]\textbf{E}[Y] = 0 - 0\cdot\frac{2}{3} = 0$。然而，$X$ 和 $Y$ 显然不是独立的，因为知道 $Y$ 的值会告诉我们一些关于 $X$ 的值的信息。例如，如果 $Y=1$，那么我们知道 $X$ 必须是 -1 或 1。

## Problem 2 (Inequalities)

- **[Reverse Markov's inequality]** Let $X$ be a discrete random variable with bounded range $\displaystyle{ 0 \le X \le U }$  for some $U>0$. Show that $\displaystyle{ \mathbf{Pr}(X \le a) \le \frac{U-\mathbf{E}[X]}{U-a} }$ for any $\displaystyle{ 0 \lt  a \lt  U }$.

  Proof:

  Let $X$ be a discrete random variable with bounded range $\displaystyle{ 0 \le X \le U }$ for some $U>0$. Let $a$ be any value such that $\displaystyle{ 0 \lt  a \lt  U }$. Define the indicator function $\displaystyle{ I_{X \le a} }$ as follows: $\displaystyle{ I_{X \le a} = 1 }$ if $\displaystyle{ X \le a }$, and $\displaystyle{ I_{X \le a} = 0 }$ otherwise. Then, we have:

  $$
  \mathbf{E}[I_{X \le a}] = \mathbf{Pr}(X \le a)
  $$

  Since $\displaystyle{ I_{X \le a} }$ is either 0 or 1, we have:

  $$
  \mathbf{E}[I_{X \le a}] = \mathbf{Pr}(X \le a) = \frac{\mathbf{E}[I_{X \le a}]}{\mathbf{E}[I_{X \le a}]} = \frac{\mathbf{E}[I_{X \le a}]}{\mathbf{E}[1]}
  $$

  Now, let's consider the quantity $\displaystyle{ U - X }$. Since $\displaystyle{ 0 \le X \le U }$, we have $\displaystyle{ 0 \le U - X \le U }$. Therefore, we can apply Markov's inequality to the random variable $\displaystyle{ U - X }$ to obtain:

  $$
  \mathbf{Pr}(U - X \ge U - a) = \mathbf{Pr}(X \le a) =\frac{\mathbf{E}[I_{X \le a}]}{\mathbf{E}[1]} =\frac{\mathbf{E}[U-X]}{\mathbf{E}[U-a]} =\frac{\mathbf{E}[U]-\mathbf{E}[X]}{\mathbf{E}[U]-\mathbf{E}[a]} =\frac{\mathbf{E}[U]-\mathbf{E}[X]}{\mathbf{E}[U]-a} =\frac{(U)-(U-\mathbf{E}[X])}{(U)-a} =\frac{(U-\mathbf{E}[X])}{(U)-a}
  $$

  Thus, we have shown that for any discrete random variable $X$ with bounded range $\displaystyle{ 0 \le X \le U }$ for some $U>0$, and for any value $a$ such that $\displaystyle{ 0 < a < U}$, we have:

  $$
  \mathbf{Pr}(X \le a) \leqslant\frac{(U-\mathbf{E}[X])}{(U)-a}
  $$

- **[Markov's inequality]** Let $X$ be a discrete random variable. Show that for all $\displaystyle{ \beta \geq 0 }$ and all $x>0$, $\displaystyle{ \mathbf{Pr}(X\geq x)\leq \mathbb{E}(e^{\beta X})e^{-\beta x} }$.

  Proof:

  To prove this, let $\displaystyle{ \beta \geq 0 }$ and $x>0$. Then, for any $X\geq 0$, we have:

  $\displaystyle{ e^{\beta X} \geq e^{\beta x} }$ if and only if $\displaystyle{ X \geq x }$.

  Therefore, $\displaystyle{ e^{\beta X} \geq e^{\beta x} \mathbf{1}_{\{X\geq x\}} }$, where $\displaystyle{ \mathbf{1}_{\{X\geq x\}} }$ is the indicator function that takes the value $1$ if $\displaystyle{ X\geq x }$ and $0$ otherwise.

  Taking the expectation of both sides, we get:

  $\displaystyle{ \mathbb{E}(e^{\beta X}) \geq e^{\beta x} \mathbb{E}(\mathbf{1}_{\{X\geq x\}}) }$

  $\displaystyle{ = e^{\beta x} \mathbf{Pr}(X\geq x) }$

  Dividing both sides by $\displaystyle{ e^{\beta x} }$, we get:

  $\displaystyle{ \mathbf{Pr}(X\geq x) \leq \frac{\mathbb{E}(e^{\beta X})}{e^{\beta x}} = \mathbb{E}(e^{\beta X})e^{-\beta x} }$ 

- **[Cantelli's inequality]** Let $\displaystyle{ X }$ be a discrete random variable with mean 0 and variance $\displaystyle{ \sigma^2 }$. Prove that for any $\displaystyle{ \lambda \gt  0 }$, $\displaystyle{ \mathbf{Pr}[X \ge \lambda] \le \frac{\sigma^2}{\lambda^2+\sigma^2} }$. (Hint: You may first show that $\displaystyle{ \mathbf{Pr}[X \ge \lambda] \le \frac{\sigma^2 + u^2}{(\lambda + u)^2} }$ for all $u>0$.)

  Proof:

  首先用 Markov 不等式来证明 $\displaystyle{ \mathbf{Pr}[X \ge \lambda] \le \frac{\sigma^2 + u^2}{(\lambda + u)^2} }$ 对于所有 $u>0$ 成立。

  由于 $\displaystyle{ X }$ 的期望值为 0，有 $\displaystyle{ \mathbf{E}[(X+u)^2] = \sigma^2 + u^2 }$。

  然后，应用 Markov 不等式，得到：
  $$
  \mathbf{Pr}[X \ge \lambda] = \mathbf{Pr}[X+u \ge \lambda+u] = \mathbf{Pr}[(X+u)^2 \ge (\lambda+u)^2] \\
  \le \frac{\mathbf{E}[(X+u)^2]}{(\lambda+u)^2} = \frac{\sigma^2 + u^2}{(\lambda + u)^2}
  $$

  通过最小化 $\displaystyle{ \frac{\sigma^2 + u^2}{(\lambda + u)^2} }$ 来找到最佳的 $u$ 值。对分子求导并令其等于零，得到 $u = \lambda$。因此，

  $$
  \mathbf{Pr}[X \ge \lambda] \le \frac{\sigma^2 + u^2}{(\lambda + u)^2} = \frac{\sigma^2 + \lambda^2}{(\lambda + \lambda)^2} = \frac{\sigma^2}{\lambda^2+\sigma^2}
  $$

- **[The weak law of large numbers]** Let $\displaystyle{ X_1,X_2,\cdots, X_n }$ be independent and identically distributed random variables with mean $\displaystyle{ \mu }$ and finite variance, use Chebyshev's inequality to show that for any constant $\displaystyle{ \epsilon\gt 0 }$ we have $\displaystyle{ \lim_{n\rightarrow \infty} \mathbf{Pr}\left( \left|\frac{X_1 + X_2 + \cdots + X_n}{n} - \mu\right| \gt  \epsilon\right) = 0 }$.

  Proof:

  设 $\displaystyle{ S_n = X_1 + X_2 + \cdots + X_n }$，则 $\displaystyle{ \mathbf{E}[S_n] = n\mu }$。由于 $\displaystyle{ X_1,X_2,\cdots, X_n }$ 独立且具有相同的分布，有 $\displaystyle{ \text{Var}(S_n) = n\sigma^2 }$，其中 $\displaystyle{ \sigma^2 }$ 是每个随机变量的方差。

  应用 Chebyshev 不等式，得：

  $$
  \mathbf{Pr}\left( \left|\frac{S_n}{n} - \mu\right| \gt  \epsilon\right) = \mathbf{Pr}\left( |S_n - n\mu| \gt  n\epsilon\right) \\
  \le \frac{\text{Var}(S_n)}{(n\epsilon)^2} = \frac{n\sigma^2}{n^2\epsilon^2} = \frac{\sigma^2}{n\epsilon^2}
  $$

  由于 $\displaystyle{ \lim_{n\rightarrow \infty} \frac{\sigma^2}{n\epsilon^2} = 0 }$，

  $$
  \lim_{n\rightarrow \infty} \mathbf{Pr}\left( \left|\frac{S_n}{n} - \mu\right| \gt  \epsilon\right) = 0
  $$


- **[Median trick]** Suppose we want to estimate the value of $Z$. Let $\displaystyle{ \mathcal{A} }$ be a randomized algorithm that outputs $\displaystyle{ \widehat{Z} }$ satisfying $\displaystyle{ \mathbf{Pr}[(1-\epsilon) Z \leq \widehat{Z} \leq (1+\epsilon)Z]\geq \frac{3}{4} }$ for some fixed parameter $\displaystyle{ \epsilon \gt  0 }$. We run $\displaystyle{ \mathcal{A} }$ independently for $2n−1$ times, and obtain the outputs $\displaystyle{ \widehat{Z}_1,  \widehat{Z}_2, \cdots, \widehat{Z}_{2n-1} }$. Let $X$ be the median (中位数) of $\displaystyle{ \widehat{Z}_1,  \widehat{Z}_2, \cdots, \widehat{Z}_{2n-1} }$. Use Chebyshev's inequality to show that $\displaystyle{ \mathbf{Pr}[(1-\epsilon) Z \leq X \leq (1+\epsilon)Z] = 1 - O(1/n) }$. (Remark: The bound can be drastically improved with [Chernoff bound](https://en.wikipedia.org/wiki/Chernoff_bound)).

  Proof:

  设 $\displaystyle{ Y_i }$ 为一个随机变量，当 $\displaystyle{ (1-\epsilon) Z \leq \widehat{Z}_i \leq (1+\epsilon)Z }$ 时取值为 1，否则取值为 0。

  由题意可知，$\displaystyle{ \mathbf{E}[Y_i] = \mathbf{Pr}[(1-\epsilon) Z \leq \widehat{Z}_i \leq (1+\epsilon)Z] \geq \frac{3}{4} }$。

  设 $\displaystyle{ Y = \sum_{i=1}^{2n-1} Y_i }$，则 $\displaystyle{ \mathbf{E}[Y] = (2n-1)\mathbf{E}[Y_i] \geq \frac{3}{2}n - \frac{3}{4} }$。

  由 Chebyshev 不等式，
  $$
  \mathbf{Pr}\left[|Y - \mathbf{E}[Y]| \geq n/2\right] \leq \frac{\text{Var}(Y)}{(n/2)^2}
  $$

  由于 $\displaystyle{ Y_i }$ 是独立的随机变量，有 $\displaystyle{ \text{Var}(Y) = (2n-1)\text{Var}(Y_i) }$。

  又因为 $\displaystyle{ Y_i }$ 是一个伯努利随机变量，所以 $\displaystyle{ \text{Var}(Y_i) = p(1-p) }$，其中 $\displaystyle{ p = \mathbf{E}[Y_i] }$。

  因此，
  $$
  \mathbf{Pr}\left[|Y - \mathbf{E}[Y]| \geq n/2\right] \leq \frac{(2n-1)p(1-p)}{(n/2)^2} = O(1/n)
  $$

  这意味着，以至少 $\displaystyle{ 1 - O(1/n) }$ 的概率，$\displaystyle{ Y }$ 的值在其期望值的 $n/2$ 范围内。

  也就是说，
  $$
  \mathbf{Pr}\left[\frac{n}{4} < Y < 2n - \frac{n}{4}\right] = 1 - O(1/n)
  $$

  这意味着，在至少 $n/4$ 个 $\displaystyle{\widehat Z}$ 中，$\displaystyle{(1-\epsilon) Z}$ 和 $\displaystyle{(1+\epsilon)Z}$ 之间有一个值。

  因此，在这些值中，中位数 $X$ 必定在这个范围内。

  所以，
  $$
  \mathbf{Pr}[(1-\epsilon) Z \leq X \leq (1+\epsilon)Z] = 1 - O(1/n)
  $$

  

## Problem 3 (Probability meets graph theory)

- [**Common neighbor**] Let $p∈(0,1)$ be a constant. Show that with a probability approaching to 1 (as $n$ tends to infinity) the Erdős–Rényi random graph $\displaystyle{ \mathbf{G}(n,p) }$ has the property that every pair of its vertices has a common neighbor. (Hint: You may use Markov's inequality.)

  Proof:

  对于任意两个顶点 $u$ 和 $v$，它们没有公共邻居的概率为 $(1-p^2)^{n-2}$，因为剩下的 $n-2$ 个顶点都不与它们同时相邻。

  由于有 $\binom{n}{2}$ 对顶点，根据线性期望,

  $\displaystyle \mathbb{E}[X] = \binom{n}{2}(1-p^2)^{n-2}$

  由于 $p$ 是常数且大于 $0$，所以当 $n$ 趋近于无穷大时，$(1-p^2)^{n-2}$ 趋近于 $0$。因此，$\mathbb{E}[X]$ 也趋近于 $0$。

  使用马尔科夫不等式来估计 $\mathbf{Pr}(X \geq 1)$。

  对于任意正数 $t$，我们有：

  $\displaystyle \mathbf{Pr}(X \geq 1) \leq \frac{\mathbb{E}[X]}{1} = \mathbb{E}[X]$

  由于 $\mathbb{E}[X]$ 趋近于 $0$，所以 $\mathbf{Pr}(X \geq 1)$ 也趋近于 $0$。这意味着当 $n$ 趋近于无穷大时，$\mathbf{G}(n,p)$ 中每对顶点都有一个公共邻居的概率趋近于 $1$。

- [**Isolated vertices**] Prove that $\displaystyle{ p = \log n/n }$ is the threshold probability for the disappearance of isolated vertices. Formally, you are required to show that

  - with a probability approaching to 1 (as $n$ tends to infinity) the Erdős–Rényi random graph $\displaystyle{ \mathbf{G} = \mathbf{G}(n,p) }$ has the property that $G$ has no isolated vertices when $\displaystyle{ p = \omega(\log n/n) }$;

    Proof:

    设 $\displaystyle{ X }$ 为 Erdős–Rényi 随机图 $\displaystyle{ \mathbf{G} = \mathbf{G}(n,p) }$ 中孤立顶点的数量。对于任意一个顶点 $v$，它是孤立的概率为 $(1-p)^{n-1}$，因为剩下的 $n-1$ 个顶点都不与它相邻。由于有 $n$ 个顶点，根据线性期望，则，

    $$
    \mathbf{E}[X] = n(1-p)^{n-1}
    $$

    当 $\displaystyle{ p = \omega(\log n/n) }$ 时，

    $$
    \lim_{n\rightarrow \infty} \frac{\log(1-p)}{\log n/n} = \lim_{n\rightarrow \infty} \frac{\log(1-\omega(\log n/n))}{\log n/n} = -\infty
    $$

    因此，

    $$
    \lim_{n\rightarrow \infty} (1-p)^{n-1} = 0
    $$

    所以，

    $$
    \lim_{n\rightarrow \infty} \mathbf{E}[X] = 0
    $$

    由 Markov 不等式，

    $$
    \mathbf{Pr}[X > 0] \leq \frac{\mathbf{E}[X]}{1} = \mathbf{E}[X]
    $$

    因此，

    $$
    \lim_{n\rightarrow \infty} \mathbf{Pr}[X > 0] = 0
    $$

    这意味着，当 $\displaystyle{ p = \omega(\log n/n) }$ 时，以概率趋近于 1，Erdős–Rényi 随机图 $\displaystyle{ \mathbf{G} = \mathbf{G}(n,p) }$ 没有孤立顶点。

  - with a probability approaching to 0 (as $n$ tends to infinity) the Erdős–Rényi random graph $\displaystyle{ \mathbf{G} = \mathbf{G}(n,p) }$ has the property that $\displaystyle{ \mathbf{G} }$ has no isolated vertices when $\displaystyle{ p = o(\log n/n) }$.

    Proof:

    设 $X$ 表示在 $\mathbf{G}(n,p)$ 中孤立顶点的数量。

    $\displaystyle \mathbb{E}[X] = n(1-p)^{n-1}$

    当 $p=o(\log n/n)$ 时：

    $\displaystyle \mathbb{E}[X] = n(1-p)^{n-1} \leq ne^{-p(n-1)} = ne^{-pn} = o(1)$

    因此，当 $p=o(\log n/n)$ 时，$\mathbb{E}[X]$ 趋近于 $0$。

    由 Markov 不等式，对于任意正数 $t$，

    $\displaystyle \mathbf{Pr}(X \geq 1) \leq \frac{\mathbb{E}[X]}{1} = \mathbb{E}[X]$

    由于 $\mathbb{E}[X]$ 趋近于 $0$，所以 $\mathbf{Pr}(X \geq 1)$ 也趋近于 $0$。这意味着当 $n$ 趋近于无穷大且 $p=o(\log n/n)$ 时，$\mathbf{G}(n,p)$ 中没有孤立顶点的概率趋近于 $1$。