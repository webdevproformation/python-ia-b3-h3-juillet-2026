# indexing / slicing / masques sur les tableaux numpy

```py

# sur les listes de base 

prix = [ 10,30,100 ]

# indexing => récupérer une valeur via sa position (index)

prix[0] # 10

# récupérer plusieurs valeurs qui sont collées dans un tableau 

prix[0:2] # [ 10, 30 ] # slicing

```

```py
# indexing et slicing
A = np.array([ 
    [2 ,   9, 7] ,
    [11, 45, 24]
]);


A[0][0] # 2
A[0,0] # 2 # c'est cette notation que l'on va utiliser le plus souvent pour accéder à des valeurs 


# exo pouvez me donner la manière pour récupérer les valeurs [11,45] depuis la tableau A 

A[ 1, 0:2 ]

# exo pouvez me  donner la manière pour récupérer les valeurs [7, 24] depuis la tableau A 

A [ : , 2 ]
```


# subsetting


```py
# un exemple de subsetting

A = np.array([
    [ 'a', 'b', 'c'],
    [ 'd', 'e' , 'f'],
    [ 'g' , 'h' , 'i' ]
]); 

A[ :2 , 1: ]

# retourner le sous ensemble 
# [ b , c ]
# [ e  , f ]


# masking 

B = np.array([ 1,10 , 50 , 3 ])

masque =   B < 5
masque # array([ True, False, False,  True])


image = np.array([ 1 , 200 , 20 , 255 , 190  ])

# si la couleur est inférieure à 30 je veux que la valeur soient plutôt 0 
# normalement on doit utiliser une boucle ET une condition

# avec numpy il est possible de 

image[image < 30] = 0 

image

```