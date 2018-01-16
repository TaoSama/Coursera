## Improving Deep Neural Networks: Hyperparameter tuning, Regularization and Optimization

### Setting up your Machine Learning Application

#### Train/dev/test sets

* previous era:
  70%/30%    60%/20%/20%  (100-1000-10000)
* big data era:
  98%/1%/1% [980000-20000 10000 1000]  (100,0000)
* make sure dev and test set come from **same distribution**

#### Bias/Variance

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/55274719.jpg)

### Regularizing your neural network

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/44566696.jpg)
![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/16375511.jpg)

#### Dropout regularization

Intuition: Can’t rely on any one feature, so have to 
spread out weights.

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/20535107.jpg)

#### Other regularization

* Data augmentation
* Early stopping

### Setting up your optimization problem

#### Normalizing inputs

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/90263774.jpg) 

#### Weight initialization for deep networks

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/15990583.jpg)

#### Numerical approximation of gradients and gradient checking

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/88714482.jpg)

### Optimization algorithms

#### Mini-batch gradient descent

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/56961819.jpg)
![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/80527462.jpg)

#### Exponentially weighted averages

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/10765548.jpg)

#### Bias correction in exponentially weighted average

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/11169708.jpg)

#### Gradient descent with momentum

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-14/90962276.jpg)

#### RMSprop

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-15/53430081.jpg)

#### Adam

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-15/32106782.jpg)
![](http://7xru22.com1.z0.glb.clouddn.com/18-1-15/80520080.jpg)

#### Learning rate decay

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-15/90932702.jpg)
![](http://7xru22.com1.z0.glb.clouddn.com/18-1-15/93744149.jpg)

### Hyperparameter tuning, Batch Normalization and Programming Frameworks

#### Tuning process

* **red->orange->purple->none**
  
  ![](http://7xru22.com1.z0.glb.clouddn.com/18-1-15/52889538.jpg)

* random sampling
* optionally consider implementing a coarse to fine search process

#### Using an appropriate scale to pick hyperparameters

##### Learning rate 

* random alpha [0.0001, 1]
* a=log10(0.0001)=-4, b=log10(1)=0
* r=-4\*np.random.rand()
* alpha=10^r

##### Hyperparameters for exponentially weighted averages

* random beta [0.9, 0.999]
* beta=1-beta
* do as above

#### Batch Normalization

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-16/98920180.jpg)


#### Softmax Regression

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-16/43195574.jpg)


#### TensorFlow

```python
import numpy as np 
import tensorflow as tf

coefficients = np.array([[1], [-20], [25]])

w = tf.Variable([0],dtype=tf.float32)
x = tf.placeholder(tf.float32, [3,1])
cost = x[0][0]*w**2 + x[1][0]*w + x[2][0]    # (w-5)**2
train = tf.train.GradientDescentOptimizer(0.01).minimize(cost)
init = tf.global_variables_initializer()
with tf.Session() as session:                        
    for i in range(1000):
        session.run(train, feed_dict={x:coefficients})
    print(session.run(w))
```





