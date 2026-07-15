# numpy

- Element central de l'IA => tableau 
- on n'utilise les tableaux de bases de python (list)

```py
etudiants = [ "Alain" , "Pierre", "Zorro"  ]
```

- tableau qui viennent de la librairie NumPy => NDArray (Tablau à N Dimensions)

---

# Comparaison entre une liste classique et NDArray

- ça se ressemble énormément
- stocker plusieurs valeurs / chaque valeur sockée va avoir une position (index)
- le premier élément de type de datastructure va avoir la valeur 0

- NDArray sont : beaucoup plus rapide / moins volumineux en mémoire / meilleur pour le calcul scientifique (plein de méthode déjà disponible) 

# pour la suite Google Colab


# présentation des tableaux numpy 

```
import numpy as np 

# tableau à 1D (vecteur)
A = np.array( [ 1,2,3 ] )

A # array([1, 2, 3])

# A est un objet de type numpy
# voici les principales propriétés / méthodes à connaitre sur cet objet 

A.ndim # le nombre de dimension 1 du tableau

A.shape # la forme du tableau 
# il retourne un tuple (3,) tableau immutable ce tableau 
# il dit que A contient 3 lignes (row)
# il dit que A contient 1 colonne (columns)

# savoir le nombre de ligne d'un tableau
A.shape[0] # 3
# A.shape[1] # erreur mais il faut bien comprendre que la valeur est 1

# créer une matrice avec numpy

B = np.array([
    [ 1,2,3],
    [ 4,5,6]
]);

B.ndim # 2
B.shape # (2, 3)
```


# quelques méthodes à connaitre pour créer des tableaux numpy

```py
# tableau rempli de zeros

C = np.zeros( ( 2,4 ) ) # créer un tableau numpy qui contient QUE des 0 qui a 2 lignes et 4 colonnes
C

D = np.ones( (4, 5)  )
D

# créer un vecteur qui contient des valeurs aléatoires (qui suit une loi Normale)

E = np.random.randn(5)
E

# créer des tableaux numpy à 1 dimension

# créer un tableau qui ressemble à un boucle 

D = np.arange(0 , 10 , 2 ) # générer un tableau numpy qui contient [ 0, 2, 4, 6 , 8  ]
D # array([0, 2, 4, 6, 8])

# créer un tableau qui contient contient exactement X elements entre deux chiffres

F = np.linspace( 0, 10 , 4 ) # créer un tableau qui contient 4 valeurs réparties manières égale
F # array([ 0.        ,  3.33333333,  6.66666667, 10.        ])
```