# dans votre google colab

créer une nouvelle case qui contient une fonction qui doit faire les traitements suivants :

```py
def exo(m , n):
    """
    m : nombre de ligne
    n : nombre de colonne
    retourner une matrice 2D Array de dimension (m, n+1)
    avec une colonne de biais (remplir de 1) tout à droite
    """

exemple d'exécution de la fonction exo

exo(2,2)

voici le retour attendu 

[
    [0 ,0 , 1]
    [0 ,0 , 1]
]
```

```py
def exo(m , n): 
    """
    solution 1
    m : nombre de ligne
    n : nombre de colonne
    retourner une matrice 2D Array de dimension (m, n+1)
    avec une colonne de biais (remplir de 1) tout à droite
    """
    A = np.zeros( (m, n) )
    B = np.ones( ( m , 1 ) )

    # si je veux additionner des tableaux => concatener / empiler de tableaux
    # empiler => stack des tableaux
    # si vous empilez horizontalement des tableaux => hstack 
    # si vous empiler verticalement des tableaux   => vstack 
    # dans notre cas nous devons faire du hstack 
    RESULTAT = np.hstack( ( A, B ) )
    print(RESULTAT)

exo(4,5)


def exo2(m , n): 
    """
    solution 2
    m : nombre de ligne
    n : nombre de colonne
    retourner une matrice 2D Array de dimension (m, n+1)
    avec une colonne de biais (remplir de 1) tout à droite
    """
    A = np.zeros( (m, n) )
    B = np.ones( ( m , 1 ) )

    # si je veux additionner des tableaux => concatener / empiler de tableaux
    # empiler => stack des tableaux
    # concat 
    RESULTAT = np.concat(  ( A, B ) , axis=1) 
    # axis=0 => axis des lignes => verticalement
    # axis=1 => axis des colonnes => horizontal
    print(RESULTAT)

exo2(4,5)

```