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


# histogramme 2d

```py
# histogramme en 2d
# réussir à présenter 3 informations avec un graphique en 2dimensions (hist2d)


plt.hist2d( X[:,0] , X[:,1] , cmap="Blues")
plt.xlabel("longueur sépale")
plt.ylabel("largueur sépale")
plt.colorbar()
```


# contour

```py
# contour plt => un graphique de type carte de montage


f = lambda x, y: np.sin(x) + np.cos(x+y)

X = np.linspace(0,5, 1000)
Y = np.linspace(0,5, 1000)
X,Y = np.meshgrid(X, Y )
Z = f(X, Y)

plt.contour( X,Y,Z ,20 , cmap="RdGy")
plt.colorbar()
```