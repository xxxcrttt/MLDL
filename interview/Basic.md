## 基本概念

### Q1. The process of solving a ML problem
1. Specified the question: supervised or unsupervised? Classification or Regression?
2. Data collecting and processing 
3. Feature Extraction: construction, selection, combination
4. Model training and evaluation: selection, testing and parameters tuning
5. Model Deployment: edge devices? online? 

### Q2. Loss function 损失函数 -- 单个样本
Loss function calculates the **difference** between the predicted value and the true value about a single sample in ML model.

#### 常用的损失函数
* **0-1 loss**: the predicted value != true value ==> 1        
![image](https://user-images.githubusercontent.com/56160038/178030132-f2284c6d-f4c4-4df4-b289-8dc20053d460.png)
* **绝对值 absolute loss func**: The robustness is good when there are many abnormal points, but its not convinient to do derivation
```𝐿(𝑦,𝑓(𝑥))=|𝑦−𝑓(𝑥)|```
* **平方 quadratic loss func**: The square difference, convinient to do derivation, can be optimized by gradient descent, but sensitive to outliers. 
```𝐿(𝑦,𝑓(𝑥))=(𝑦−𝑓(𝑥))^2```
* **对数 logarithms loss func**: maximum likelihood estimation
```𝐿(𝑦,𝑝(𝑦|𝑥))=−log𝑝(𝑦|𝑥)```
* **Huber loss func**: used in robust regression, less sensitive to ourliers, but needs to tune hyperparameters    
![image](https://user-images.githubusercontent.com/56160038/178037719-6c52693f-326b-4fb9-9b29-689326e2ea3b.png)
* **Log-Cosh**: second order differentiable(Newton's method)    
![image](https://user-images.githubusercontent.com/56160038/178039263-e4fcc95b-974b-4cba-a297-6ad237e23cc1.png)
* **Hinge loss**: used in Classification, especially SVM   
![image](https://user-images.githubusercontent.com/56160038/178060505-5bb9b920-21dd-4b4d-950f-6bdab3b83199.png)


### Q3. Cost Function 代价函数 -- 整个数据集
defined over the entire training set, it is the averag eof all sample errors -- the average of all loss function 

* **MAE/ L1**: 平均绝对误差 Mean Absolute error, used in Regression model, sum of the absolute value 
* **MSE/ L2**: 均方误差 Mean Squared Error, sum of the squares of the distance between the predicted value and the true value; 
can evaluate the degree of change in the data. 
* **RMSE**: 均方根误差 Root MSE 
When dealing with outliers, L1 is more stable, but its derivative is not continuous, so its less effective;   
L2 is more sensitive to outliers. 
* **交叉熵 Cross-Entry**: Shannon Information Theory, measures the difference information between probability distributions. 
Usually used as cost function in Classification.   
<img src='https://user-images.githubusercontent.com/56160038/178061092-803951b3-a071-41e5-b7ce-a7f335e7baae.png' width='300' align=center />

### Q4. 结构误差，经验误差，泛化误差
* 经验风险: Empirical Risk/training error: 模型在训练集上的误差
* 泛化误差: Generalization error: 模型在测试集上的误差
* 结构风险: Structure Risk: 在经验风险上加上正则化, 为了防止过拟合

### Q5. 泛化 -- Generalization
模型对于未知数据的预测能力称为泛化能力，通过测试误差来评价   
The ability of model to predict unknown data is usually called generalization ability. 

### Q6. Metrics 评估指标
**混淆矩阵 Confusion Matrix**:    
<img src='https://user-images.githubusercontent.com/56160038/178064120-2d8c833c-3d8f-4b0e-883a-a937e9d524eb.png' width='300' align=center />

* **Accuracy**: $$ Accuracy = \frac{n_{correct}}{n_{total}} $$ 
* **Precision**: $$ Precision = \frac{TP}{TP+FP} $$
* **Recall**: $$ Recall = \frac{TP}{TP+FN} $$
* **F1-Score**: harmonic mean of Precision and Recall, $$ {\rm F1} = \frac{2 \times precision \times recall}{precision + recall} $$ 
* **ROC**: FPR to TPR,  $$ FPR = \frac{FP}{N} \ TPR = \frac{TP}{P} $$ 
* **AUC**: Area Under Curve, ROC曲线下的面积, 取值一半在 0.5~1 之间
<img src ='https://user-images.githubusercontent.com/56160038/178078824-2393eab7-949e-463b-83b6-5c1c9f521cfd.png' width='300' align=center />

### Q7. Overfitting vs. Underfitting 
#### Trade-off between Bias and Variance 
* **Bias**: 模型预测值与真实值的差异 -- 模型简单，导致欠拟合
* **Variance**: 不同训练数据训练的模型的预测值之间的差异 -- 模型过于复杂，过拟合
* **Overfitting**: 过拟合, too many parameters, model predicts the known data well but poor predicts the unknow data. 
Low Bias, High Variance 
1. Increase the sample size: Data Augmentation 
2. Simplified model: Dropout, Early Stopping, Tree Pruning
3. L1, L2 Regularization or increase the penalty factor 
4. Bagging or Bootstrapping 
5. Use cross-validation 

* **Underfitting**: 欠拟合, training is worse, model is too simple 
High Bias, low Variance
1. increase feature
2. increase model complexity: increase the number of neurons in NN; increase number of layers; use Kernel function in SVM
3. decrease the regularization factor 

### Q8. Linear Model vs. Non-Linear Model 线性模型 / 非线性模型
* **Linear**: ```Perceptron, Linear SVM, KNN, K-Means Clusering, LSA```
* **Non-Linear**: ```Kernel SVM, AdaBoost, Neuron Network```

### Q9. Generative Approach vs. Discriminative Approach 生成模型 / 判别模型
监督学习的模型一般形式为决策函数(decision function): ```Y=f(x)``` 或条件概率分布(conditional prob. distribution)```P(Y|X)```.     
* **生成模型**: 数据学习联合概率分布```P(X,Y)```求出条件概率分布```P(Y|X)```作为预测模型:  $$ P(Y|X) = \frac{P(X,Y)}{P(X)} $$    
A model represents a generative relationship given an input X, produces an output Y.    
```朴素贝叶斯(Naive Bayes), 隐马尔科夫模型(Hidden Markov Model)```
* **判别模型**: 数据直接学习决策函数```f(x)```或者条件概率分布```P(Y|X)```作为预测模型    
What output Y should be predicted for a given input X.   
```KNN, Perceptron, Decision Tree, Logistic Regression, SVM, CRF(conditional random field)```

### Q10. Probability 概率模型 vs. 非概率模型  
* **概率模型**: 一定能表示为联合概率分布(Joint Prob.Distribution) -- 生成模型, ```Decision Tree, Naive Bayes, HMM, CRF, Gaussian Mixture Model```
* **非概率模型**: 判别模型, ```Perceptron, SVM, KNN, AdaBoost, KMeans, Neuron Networks```

### Q11. Parametric 参数化 vs. 非参数化  
* **参数化**: 假设模型参数维度固定(有限), Perceptron, Naive Bayes, Logistic Regression, ```KNN, Gaussian Mixture Model```
* **非参数化**: 维度不固定, 随着训练数据量增加而增大, ```Decision Tree, SVM, AdaBoost, KMeans```

### Q12. Supervised Learning vs. Unsupervised Learning vs. Reinforcement Learning 
### 监督学习 vs 非监督学习 vs 强化学习
* **Supervised**: known and labeled data, has feedback mechanism. ```Decision Tree, Logistic Regression, SVM```
* **Unsupervised**: unlabeled data, ```K-means clustering, PCA, ICA```
* **Reinforcement**: reward from environment ```Game Theory, Cybernetics, Operations Research, information theory```

### Q13. Univariate(单变量), bivariate(双变量) and multivariate(多变量) analysis 
* **Univariate**: one variable, describe the data and find the patterns that exist within it. 
* **Bivariate**: two variables, deals with causes and relationships between these 2 variables
* **Multivarite**: categorized under multivariate, with more than one dependent variable. 

### Q14. Feature Selection Methods 
* **Filter Methods**: ```LDA(Linear Discrimination Analysis), ANOVA(Analysis of Variance), Chi-Square```
* **Wrapper Methods**: ```Forward Selection, Backward Selection, Recursive Feature Elimination```

### Q15. Dimensionality reduction 降维 / curse of dimensionality
Dimensionality reduction refers to the process of converting a vast dimension dataset into data with fewer dimensions to convey similar information.     
This reduction helps in compressing data and reducing storage space, less computing, removes redundant features. 
* Manual Feature Selection 手动筛选特征
* Principal Component Analysis (PCA)
* Multidimensional Scaling (多维度标)
* Locally linear embedding 

### Q16. Gradient Descent 梯度下降
是迭代法(Iterative Method)的一种, 可以用于解决最小二乘问题(Least Square Problem), 可求解ML的模型参数.    
在求解损失函数的最小值时通过梯度下降来迭代求解, 得到最小化的损失函数和模型参数.    
```随机梯度下降(stochastic gradient descent，SGD) & 批量梯度下降(Batch GD)```   

It is an **optimization algorithm** used to find the values of parameters of a function that minimizes a **cost** function.   
It is best used when the parameters cannot be calculated analytically(eg: using linear algebra) and must be searched for by an optimizer algorithm. 

### Q17. Regularization 正则化
A technique that discourage learning a more complex or flexible model, to avoid the risk of overfitting.   
防止过拟合, 在损失函数上加上某些规则(限制), 缩小解空间, 从而减少求出拟合解的可能性    
* **L1/Lasso**: 绝对值, the L1 penalty can force the coefficient estimates to be 0. Performs variavle selection
* **L2/Ridge**: 最小二乘, the coefficients is very close to 0 but never equal to 0. == include all the parameters 

### Q18. Normalization 归一化
A very important **preprocessing** step, used to **rescale** values to fit in a specific range to assure better convergence during ackpropagation.    
The data normalization makes all features weighted equally.    
用于重新调整数值以适应特定范围，确保在反向传播期间能更好的收敛. 数据归一化使得所有特征权重相等

### Q19. PCA 主成分分析
利用正交变换对一系列可能相关的变量的观测值进行线性变换, 从而投影为一系列线性不相关变量的值, 即为主成分。    
* A sequence of p unit vectors, where the i-th vector is the direction of a line that best fits the data while being orthogonal to the first i-1 vectors.
* Different individual dimensions of the data are linear uncorrelated. 
* When many of the variables are highly correlated, and PCA is used to reduce their number to an independent set. 

### Q20. Distance
* **L1 Distance/Manhattan**: ```d(x, y) = |x1 - x2| + |y1 - y2|```
* **L2 Distance/Euclidiean**: ```d(x, y) = sqrt((x1 - y1)^2 + (x2 - y3)^2 + ... + (xn - yn)^2)```

### Q21. How should you maintain a deployed model?
Monitor + Evaluate + Compare + Rebuild.

### Q22. KNN vs. K-Means CLustering 
both need to calculate the distance between samples 
* **KNN**: K Nearest Neighbour, supervised learning, need labeled data, 统计它附近最近的K个样本并将其划分到最多的类别中
* **K-Means**: unsupervised learning, 将数据分成K组，随机选择K个对象作为初始聚类的中心，然后计算每个对象与各个中心之间的距离，将它分入最近的聚类中。



