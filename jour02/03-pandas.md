# Pandas

- LA LIBRAIRIE INCONTOURNABLE pour travailler avec des chiffres 
- chaque objet que vous allez manipuler == un onglet de fichier EXCEL 

- comme pour Numpy et Matplotlib il faut télécharger la linbrairie et l'import dans votre fichier pour pouvoir l'utiliser
- google colab dispose de cette librairie par défaut 
- 


```py
import pandas as pd 

data = pd.read_csv('titanic_dataset.csv')

data.head()
data.tail()
data.columns
data.shape
data.describe()
```
Nettoyage

```py
data = data.drop(["PassengerId", "Name", "SibSp", "Parch" , "Ticket" , "Fare" , "Cabin" , "Embarked"] , axis=1)

data = data.dropna(axis=0)
data.describe()
```


