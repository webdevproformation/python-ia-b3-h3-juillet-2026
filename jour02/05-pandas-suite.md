# pandas suite 

un peu comme un tableau croisé dynamique en Excel => `groupby()`


# exo

- en utilisant la fonction que l'on vient de voir `groupby()`
- pouvez vous me donner la moyenne des passagers qui ont survénu par class et par age 


```py
data.groupby(["Pclass" , "Age"])[["Survived"]].mean()
# attention il faut enlever la colonne "Sex" car elle contient du texte impossible d'effectuer dessus une moyenne
```