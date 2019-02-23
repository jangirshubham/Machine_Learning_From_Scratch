# Machine Learning From Scratch (without using any ML libraries)
## With good visualizations

## Table of contents
- [Logistic Regression](#1-logistic-regression-python)
- [Naive Bayes](#5-naive-bayes)
- Support Vector Machine (yet to implement)
- Decision Trees (yet to implement)
- [Neural Network (matlab/octave)](#3-neural-network-simple-structure-with-any-number-of-layers-matlaboctave)
- [Deep Neural Network-DeepLearning](#2-deep-neural-network---deeplearning-python)
    - Convolutional Network
    - Recurrance Neural Network
- [Kernel Learning & Regularization](#4-kernel-learning--regularization-python)

## 1. Logistic Regression (Python)
### Code ans examples are [here](https://github.com/Nikeshbajaj/MachineLearningFromScratch/tree/master/LogisticRegression)

```
from LogisticRegression import LR # given code
clf = LR(X,y,alpha=0.003,polyfit=True,degree=5,lambd=2)
fig=plt.figure(figsize=(8,4))
gs=GridSpec(1,2)
ax1=fig.add_subplot(gs[0,0])
ax2=fig.add_subplot(gs[0,1])

for i in range(100):
    Clf.fit(X,y,itr=10)
    ax1.clear()
    Clf.Bplot(ax1,hardbound=False)
    ax2.clear()
    Clf.LCurvePlot(ax2)
    fig.canvas.draw()
    plt.pause(0.001)
    
clf.predict(X)
W,b =clf.getWeight()

```

<p align="center">
<img src="https://raw.githubusercontent.com/Nikeshbajaj/MachineLearningFromScratch/master/LogisticRegression/img/example5.gif" width="600"/>
  
<img src="https://raw.githubusercontent.com/Nikeshbajaj/MachineLearningFromScratch/master/LogisticRegression/img/example1.gif" width="300"/>
  <img src="https://raw.githubusercontent.com/Nikeshbajaj/MachineLearningFromScratch/master/LogisticRegression/img/example2.gif" width="300"/>
</p>


## 2. Deep Neural Network - Deeplearning (python)
### Code and examples are [here](https://github.com/Nikeshbajaj/DeepLearning_from_scratch)
#### Full detail of implementation and use of code is describe [here](https://github.com/Nikeshbajaj/DeepLearning_from_scratch)
 
<p align="center">
<img src="https://raw.githubusercontent.com/Nikeshbajaj/DeepLearning_from_scratch/master/figures/deepnet.gif" width="500"/>
<img src="https://raw.githubusercontent.com/Nikeshbajaj/DeepLearning_from_scratch/master/figures/11.png" width="300"/>
</p>

## 3. Neural Network (simple structure) with any number of layers (Matlab/Octave) 
### Code and examples [here](https://github.com/Nikeshbajaj/MachineLearningFromScratch/tree/master/NeuralNet)

Network can be created and trained as for example
```
W= NeuralNet(X,y,HL,Iterations,alpha,verbose);

% For 2 hidden layers with 5 and 3 neurons, 500 iteration and 0.1 alpha(learning rate)
% input and output layers are chosen according to data X,y provided

W= NeuralNet(X,y,[5,3],500,0.1,1); 

% for 8 hidden layers
W= NeuralNet(X,y,[15,10,10,10,5,5,5,3],100,0.1,1);

returns weights W of each layer

```

<p align="center">
<img src="https://raw.githubusercontent.com/Nikeshbajaj/MachineLearningFromScratch/master/NeuralNet/Linear.bmp" width="300"/>
<img src="https://raw.githubusercontent.com/Nikeshbajaj/MachineLearningFromScratch/master/NeuralNet/NonLinear1.bmp" width="300"/>
<img src="https://raw.githubusercontent.com/Nikeshbajaj/MachineLearningFromScratch/master/NeuralNet/NonLinear3.bmp" width="300"/>
</p>

## 4. Kernel Learning & regularization (python)
### Kernel Learning (Linear, Polynomial, Gaussian)
* Linear ![equation1](http://latex.codecogs.com/gif.latex?%5Clarge%20K%28X%2CY%29%20%3D%20X%5ETY)
* Polynomail ![equation2](http://latex.codecogs.com/gif.latex?%5Clarge%20K%28X%2CY%29%20%3D%20%28X%5ET%20Y%20+%201%29%5Ep)
* Gaussian (RBF) ![equation3](http://latex.codecogs.com/gif.latex?%5Clarge%20K%28X%2CY%29%20%3D%20exp%5E%7B-%5Cleft%20%5C%7C%20X-Y%20%5Cright%20%5C%7C%5E2%20/%202%5Csigma%20%5E2%7D)
### Code and examples with GUI are given [here](https://github.com/Nikeshbajaj/Regularization_for_Machine_Learning)
<p align="center">
<img src="https://raw.githubusercontent.com/Nikeshbajaj/Regularization_for_Machine_Learning/master/GUI_Win_Lin.jpg" width="500"/>
</p>



## 5 Naive Bayes
### Probabilistic model
Classifier based on Bayes rule:
<p align="center">
<img src="https://raw.githubusercontent.com/Nikeshbajaj/MachineLearningFromScratch/master/Probabilistic/img/Bayes_rule.png" width="400"/>
</p>

### Example with jupyter notebook [here](https://github.com/Nikeshbajaj/Machine_Learning_From_Scratch/blob/master/Probabilistic/NaiveBayes_example.ipynb)

Notebook include example of Iris data, Breast Cancer and Digit classification (MNIST)

```
import numpy as np
import matplotlib.pyplot as plt

# For dataset
from sklearn import datasets
from sklearn.model_selection import train_test_split

# Library provided
from probabilistic import NaiveBayes

data = datasets.load_iris()
X = data.data
y = data.target

Xt,Xs,yt,ys = train_test_split(X,y,test_size=0.3)

print(Xt.shape,yt.shape,Xs.shape,ys.shape)

# Fitting model (estimating the parameters)
clf = NaiveBayes()
clf.fit(Xt,yt)

# Prediction
ytp = clf.predict(Xt)
ysp = clf.predict(Xs)

print('Training Accuracy : ',np.mean(ytp==yt))
print('Testing  Accuracy : ',np.mean(ysp==ys))

print(clf.parameters)

# Visualization
fig = plt.figure(figsize=(12,10))
clf.VizPx()
```

<p align="center">
<img src="https://raw.githubusercontent.com/Nikeshbajaj/MachineLearningFromScratch/master/Probabilistic/img/FeatureDist.png" width="600"/>
</p>


