# exo 

pouvez vous créer un graphique qui contient une grille de 2 x 2 (4 sous graphique)

le 1er graphique contient un histogramme de la colonne 0 de X
le 2eme graphique contient un histogramme de la colonne 1 de X
le 3eme graphique contient un nuage de point  de la colonne 2 de X
le 4eme graphique contient un nuage de point  de la colonne 3 de X

ne pas hésiter à mettre un titre pour chaque élément graphique de la grille

voici le code de départ :

```py
# j'ai besoin de créer un histogramme 
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris
from mpl_toolkits.mplot3d import Axes3D 
import numpy as np

fleurs = load_iris()

X = fleurs.data
Y = fleurs.target

plt.hist(X[:,0])
```
 