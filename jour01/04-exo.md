## Exercice – Manipulation de tableaux NumPy 

On considère les tableaux NumPy suivants :

```python
import numpy as np

a = np.array([[1, 2, 3],
              [4, 5, 6]])

b = np.array([[7, 8, 9]])

c = np.array([[[10, 11, 12]]])
```

Écrire un script Python utilisant **NumPy** permettant de :

1. Afficher la dimension (`ndim`) et la forme (`shape`) de chacun des tableaux `a`, `b` et `c`.

2. Utiliser la fonction **`vstack()`** pour empiler verticalement les tableaux `a` et `b`, puis afficher :
   - le tableau obtenu ;
   - sa dimension ;
   - sa forme.

3. Transformer le tableau obtenu à la question précédente en un tableau à une seule dimension à l'aide de la fonction **`ravel()`**.

4. Utiliser la fonction **`squeeze()`** sur le tableau `c` afin de supprimer les dimensions inutiles de taille 1.

# Correction

```py
import numpy as np

a = np.array([[1, 2, 3],
              [4, 5, 6]])

b = np.array([[7, 8, 9]])

c = np.array([[[10, 11, 12]]])

# question 1
a.ndim , a.shape , b.ndim , b.shape , c.ndim , c.shape


# question 2
ab_vstack = np.vstack( ( a , b ) )

ab_vstack , ab_vstack.ndim , ab_vstack.shape


# question 3
ab_ravel = np.ravel(ab_vstack)

ab_ravel # array([1, 2, 3, 4, 5, 6, 7, 8, 9])

# question 4 
c_vecteur = np.squeeze( c )

c_vecteur , c_vecteur.ndim # (array([10, 11, 12]), 1)
```