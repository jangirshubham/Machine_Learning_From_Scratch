# Logistic Regression
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
