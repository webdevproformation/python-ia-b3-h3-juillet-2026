# à partir du code suivant

```py
import scipy.datasets           # calcul scientifique et récupérer l'image
import matplotlib.pyplot as plt # faire des graphiques 

raton_laveur = scipy.datasets.face(gray=True)
plt.gray()
plt.imshow(raton_laveur)

raton_laveur.ndim # 3
raton_laveur.shape  # (768, 1024, 3)


# 1 pouvez vous afficher la moitié de l'image (découpé en horizontal) et l'afficher
# 2 pouvez vous changer la luminosité de l'image = si un pixel a une valeur de 200 vous devez la modifier pour quelle passe à 255 et afficher l'image plus lumineuse 

moitie_largeur = int(raton_laveur.shape[1] / 2)
moitie_largeur

demi_raton_laveur = raton_laveur[: , moitie_largeur:   ]

demi_raton_laveur[demi_raton_laveur >= 180 ] = 255 
plt.imshow(demi_raton_laveur)
```