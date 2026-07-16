# rappel

## NumPy

un type de tableau qui est la base de calculs scitifiques, pour le Machine Learning (ML) et Deep Learning

- NDArray : Tableau à N Dimensions
- par rapport à une liste Python classique : plus compact en mémoire / plus rapide à exécuter

```py
import numpy as np
# créer des NDArray

A = np.array([1,2])

B = np.zeros((1,2))

C = np.ones((2,2))

D = np.random.randn(10)

E = np.arange(0, 10 , 1)

F = np.linspace(0 , 10 , 2)

# Modifier les NDArray

- lorsque l'on a des tableaux ce que l'on peut faire additionner 
- soit horizontalement `hstack()`
- soit verticalement  `vstack()`
- une méthode permet de faire les deux en meme temps `concat()`
- `concat((A,B) ,axis=0 ) == `vstack()`
- `concat((A,B) ,axis=1 ) == `hstack()`

- ravel() => mettre une matrice sous forme de vecteur 
- squeeze() => enlever les dimensions 1 de la forme
- reshape() => permet de changer les dimensions d'un tableau existant


# Sélectionner des valeurs dans les NDarray

- indexing => sélectionner une valeur via son index
- slicing  => prendre une part du tableau d'origine
- subseting => prendre une partie complète en fonction de critères
- masking => pour chaque élément du tableau on effectue une comparaison boolean 

# fonctions mathématiques

.sum()
.cumsum()
.min()
.max()
.mean()
.std()
.argmin() / argmax()
``` 


##  Matplotlib

```py
import matplotlib.pyplot as plt 

// informations
// j'ai besoin de deux tableaux qui contiennet la valeur en X 
// un tableau qui contient les valeurs en Y 

X = np.arange( 0 , 10 , 0.5 )
Y = X * 4 + 1

# dessiner un graphique avec une ligne pleine

plt.plot( X , Y , label="température", c="#000" , ls="--" , alpha=0.5 )

# dessiner un graphique qui contient des sous graphiques 

plt.figure()

# 1er sous graphique 
plt.subplot(2,2,1) 

// je vais un graphique qui contient une grille de 2 lignes et 2 colonnes
// et je suis en train de dessiner le 1er graph

plt.plot( X , Y , label="température", c="#000" , ls="--" , alpha=0.5 )

# 2eme sous graphique 
plt.subplot(2,2,2) 

plt.plot( X , Y , label="température", c="#000" , ls="--" , alpha=0.5 )

# 3eme sous graphique 
plt.subplot(2,2,3) 

plt.plot( X , Y , label="température", c="#000" , ls="--" , alpha=0.5 )

# 4eme sous graphique 
plt.subplot(2,2,4) 

plt.plot( X , Y , label="température", c="#000" , ls="--" , alpha=0.5 )

```


- 
- 