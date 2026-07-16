# graph en 3d


```py
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris
from mpl_toolkits.mplot3d import Axes3D 


fleurs = load_iris()

X = fleurs.data
Y = fleurs.target
ax = plt.axes(projection='3d')
ax.scatter(X[:,0], X[:,1], X[:,2] , c=Y)
```



```py
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D 

f = lambda x, y: np.sin(x) + np.cos(x+y)

X = np.linspace(0,5, 1000)
Y = np.linspace(0,5, 1000)
X,Y = np.meshgrid(X, Y )
Z = f(X, Y)

ax = plt.axes(projection='3d')
ax.plot_surface(X, Y, Z , cmap="plasma")
```