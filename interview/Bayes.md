### Q1. Bayes Theorem
根据一件事情发生的先验知识告诉它的后验概率。    
Bayes Theorem would tell the **posterior** probability based on **prior** knowledge of conditions.    
![image](https://user-images.githubusercontent.com/56160038/179351738-6d6f580c-50c9-49de-8af8-ee37bef2ae98.png)    
* P(A|B): conditional probability: the prob of event A occuring given that B is True. -- the Posterior 
* P(B|A): conditional probability: the **likelihood** of A given a fixed B
* P(A) & P(B): the **marginal / prior** probability 

### Q2. Naive Bayes 
假设: 特征之间是相互独立的 -- 计算条件概率时可以简化成条件概率乘积    
Variables are i.i.d (independent and identically distributed)

### Q3. Probability vs. Likelihood 概率和似然
* 概率: 描述了已知参数时的随机变量的输出结果；describe the output of random variables when the parameters are known.
* 似然: 描述已知随机变量输出结果时，未知参数的可能取值。describe the possible values of an unknown parameter when the output of a known random variable is described. 

