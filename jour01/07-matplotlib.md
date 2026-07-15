```py
# lorque l'on fait du machine learning / deep learning 
# pour visualiser les données que l'on traite / comprendre les traitements
# vous utiliserez surement un graphique

# matplotlib 
# seaborn 

import matplotlib.pyplot as plt
import seaborn as sns 
import numpy as np
# je veux dessiner une ligne droite (modèle linéaire)

# via numpy on va créer un vecteur qui commence à 0 et qui finit à 10 et qui augmente de 1

X = np.arange(0 , 11 , 1)
Y = X * 2 + 1

# dessiner un graphique :
plt.plot( X , Y )


#------------

# dessiner une hyperbole


X = np.arange(-10 , 11 , 1)
Y = X ** 2 + 1

plt.plot( X, Y )


#------------

X = np.arange(-10 , 11 , 1)
Y = X ** 2 + 1
Z = X *  2 + 1

plt.scatter( X, Y , label="temperature" , c="green" ) # nuage de point
plt.plot( X, Z , label="duree" , c="red" )
plt.legend()
plt.xlabel("minutes")
plt.ylabel("euros")

#------------


# vous allez créer un graphique qui contient des sous graphiques
# plot qui contient des subplot()

# 1 créer le graphique qui va contenir tous les graphiques 
plt.figure( figsize=( 10 , 8 ) )

# 2 créer le premier sous graphique 
plt.subplot( 2,1 ,1 ) # dans le graphique il va y avoir une grille qui contient 
                      # 2 lignes 
                      # 1 colonnes
                      # et je suis en train de dessiner le premier graphique

plt.title("graphique 1")
plt.plot( X, Y , label="temperature" )
plt.legend()
# 2ème graphique
plt.subplot( 2,1 ,2 ) 
plt.title("graphique 2")
plt.plot( X, Z , label="prix" )
plt.legend()
```