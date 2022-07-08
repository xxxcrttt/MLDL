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
* **Overfitting**: 过拟合, too many parameters, model predicts the known data well but poor predicts the unknow data. 
Low Bias, High Variance 
1. Increase the sample size: Data Augmentation 
2. Simplified model: Dropout, Early Stopping, Tree Pruning
3. L1, L2 Regularization or increase the penalty factor 
4. Bagging or Bootstrapping 
* **Underfitting**: 欠拟合, training is worse, model is too simple 
High Bias, low Variance
1. increase feature
2. increase model complexity: increase the number of neurons in NN; increase number of layers; use Kernel function in SVM
3. decrease the regularization factor 

### Q8. Linear Model vs. Non-Linear Model 线性模型 / 非线性模型
* Linear: Perceptron, Linear SVM, KNN, K-Means Clusering, LSA
* Non-Linear: Kernel SVM, AdaBoost, Neuron Network 







