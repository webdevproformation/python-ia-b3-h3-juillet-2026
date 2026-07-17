# premier pas avec sckit learn

- google colab


```py
# générer notre dataset
import numpy as np
import matplotlib.pyplot as plt 

# créer un jeu de données aléatoire je vais utiliser des fonctions de numpy

# seed pour les fonctions random
np.random.seed(42)

# la taille de l'échantillon
m = 100

X = np.linspace(0,10, 100).reshape(m, 1)
y = X + np.random.randn(m, 1)
z = X * 0.85 + 0.6

plt.scatter(X , y)
plt.plot(X , z , c="r")
```

```py
# choisir un model / l'entrainer / l'évaluer / l'utiliser 
from sklearn.linear_model import LinearRegression 

model = LinearRegression()

# entrainement du model
model.fit(X , y  )

# score 
model.score(X, y) # 0.9146941180074883 score R2 la méthode des moindre carrés

# utiliser le model
prediction = model.predict( X )

plt.scatter(X , y)
plt.plot(X , prediction , c="g")
```

# exo

- utiliser sur le jeu de données que nous avons créer le model SVR avec une hyperparamètre `C=100`
- qu'est ce que le model SVR ?? dans scikit learn
- donner le score de ce modèle ? 
- pourquoi il est meilleur que celui de modele `LinearRegression` ?