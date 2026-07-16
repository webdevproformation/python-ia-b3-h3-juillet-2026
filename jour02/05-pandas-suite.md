# pandas suite 

un peu comme un tableau croisé dynamique en Excel => `groupby()`


# exo

- en utilisant la fonction que l'on vient de voir `groupby()`
- pouvez vous me donner la moyenne des passagers qui ont survénu par class et par age 


```py
data.groupby(["Pclass" , "Age"])[["Survived"]].mean()
# attention il faut enlever la colonne "Sex" car elle contient du texte impossible d'effectuer dessus une moyenne
```


# correction exo créer une catégorie 

```py
data = pd.read_csv("titanic_dataset.csv")
data = data.drop([ "Name","Fare", "Cabin" , 
            "Ticket", "Parch", "Embarked", 
            "PassengerId" , "SibSp"], axis=1)
data = data.dropna(axis=0)

data.tail()

def categorie_age(age):
  if age <= 20 :
    return "< 20 ans"
  elif (age > 20) & (age <=30):
    return "20 - 30 ans"
  elif (age > 30) & ( age <= 40 ):
    return "30 - 40 ans"
  else:
    return "+40 ans"

data["Age"].map(categorie_age).value_counts()
```

