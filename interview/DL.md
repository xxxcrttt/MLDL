### Q1. Why is ReLu better than Sigmoid in NN?
<img src='https://user-images.githubusercontent.com/56160038/178143495-dcb20d1c-2929-44bd-838d-59047f5930c7.png' width='300' align=centre/>

1. 相比于Sigmoid, ReLu 放弃了更复杂的计算(幂运算), 提高了运算速度, 使得网络更轻便.    
Improve the operation speed by reduce complex computation, making the network lighter. 
2. 对于深层网络, Sigmoid & tanh 函数反向传播的过程中容易出现梯度消失的问题，会降低收敛速度; 而ReLu的梯度大多数情况下是常数, 有助于解决深层网络收敛问题.     
For deep networks, the back-propagation process of Sigmoid function would lead to gradient disappearance problem, 
while the gradient of ReLu is mostly constant which helps to solve the deep netwokr convergence problem. 
3. ReLu会使得一部分神经元输出为0，造成网络稀疏性，减少参数的相互依赖性，减缓过拟合问题.    
ReLu will make some neurons output to be 0, resulting in network sparsity, reducing the interdependence between parameters, to avoid overfitting.

### Q2. Why use convolutions for for images rather than FC layers? 卷积 vs. 全连接层(Fully Connected)
1. conv层保留并且编码图像中的空间信息，而FC层没有相对空间信息    
CONV preserve and encode the spatial information from the image, while FC do not have relative spatial information. 
2. CNN具有部分内置的平移不变性，因为每个卷积核都是自己的过滤器/特征检测器    
CNN have partially built-in **translation invariance**, since each convolution kernel acts as it's own filter/feature detector. 
3. conv层可以多尺度, 但FC层必须限制输入图像的大小    
CONV can be multi-scla,e but FC must limit the size of the input image. 

### Q3. CNN translation invariant 平移不变性
* 平移不变性意味着系统产生完全相同的相应(输出), 无论他的输入时如何平移的. (卷积 + 最大池化约等于平移不变)    
* 卷积为不同位置的特征检测器, 无论目标出现在图像中的哪个位置, 都会检测到同样的特征 -- 同样的输出; 
* 最大池化返回感受野种的最大值, 最大值被移动了但仍在感受野中，则池化层也会输出相同的最大值 -- 平移不变     
Each convolution kernel acts as it's own filter/feature detector, so the convolution is applied in a sliding windoe across the entire image. 
The same feature is detected no matter where the target appears in the image.
While maximum pooling returns the maximum value of the receptive field. If the maximum value if translation but still in the receptive filed, the pooling layer will output the same value. 

### Q4. Max-pooling in Classification CNN. 
