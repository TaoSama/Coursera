## Structuring Machine Learning Projects 

### Chain of assumptions in ML

#### Orthogonalization 

Orthogonalization or orthogonality is a system design property that assures that modifying an instruction or a component of an algorithm will not create or propagate side effects to other components of the system.
It becomes easier to verify the algorithms independently from one another, it reduces testing and development time.

#### Assumptions

When a supervised learning system is design, these are the 4 assumptions that needs to be true and orthogonal.

* Fit training set well in cost function
   If it doesn’t fit well, the use of a bigger neural network or switching to a better optimization algorithm might help.
* Fit development set well on cost function
   If it doesn’t fit well, regularization or using bigger training set might help. 
* Fit test set well on cost function
   If it doesn’t fit well, the use of a bigger development set might help
* Performs well in real world
   If it doesn’t perform well, the development test set is not set correctly or the cost function is not evaluating the right thing.



### Error Analysis

#### Carrying out error analysis

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-16/5845899.jpg)

#### Build your first system quickly, then iterate

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-17/83107824.jpg)

### Mismatched training and dev/test data

#### Training and testing on different distributions

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-19/96942983.jpg)

#### Bias and Variance with mismatched data distributions

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-19/83485412.jpg)


### Learning from multiple tasks

#### Transfer learning

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-19/33653335.jpg)
![](http://7xru22.com1.z0.glb.clouddn.com/18-1-19/64711296.jpg)

#### Multi-task learning

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-19/55488456.jpg)
![](http://7xru22.com1.z0.glb.clouddn.com/18-1-19/46915605.jpg)


### End-to-end deep learning

![](http://7xru22.com1.z0.glb.clouddn.com/18-1-19/87015848.jpg)
![](http://7xru22.com1.z0.glb.clouddn.com/18-1-19/3155561.jpg)
![](http://7xru22.com1.z0.glb.clouddn.com/18-1-19/10958917.jpg)


