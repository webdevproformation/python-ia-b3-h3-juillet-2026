
# split

```py
from sklearn.model_selection import train_test_split


X = np.linspace(0,10, 100).reshape(m, 1)
y = X + np.random.randn(m, 1)

# on veut correctement entrainer notre model et l'évaluer
# IL est conseillé de découper en 2 parties les données 
# on va split les données en 2 parties
# X_train , y_train que l'on doit utiliser au moment de l'entrainement 

# X_test  , y_test que l'on va utiliser au moment du score 
X_train , X_test , y_train , y_test = train_test_split(X , y , test_size=0.2, random_state=42  )

model = SRV(C=100)

# phase d'entrainement
model.fit(X_train,y_train)

# phase d'évaluation
score = model.score(X_test,y_test)
```

# recherche des meilleurs hyperparamètres pour votre model

```py
from sklearn.model_selection import cross_val_score
from sklearn.neighbors import KNeighborsClassifier

cross_val_score(
    KNeighborsClassifier(),
    X_train ,
    y_train ,
    cv=5 , # cross validation le nombre de découpes pour faire les comparaisons
    scoring="accuracy"
)

model = GridSearchCV(
    KNeighborsClassifier(),
    {
        'C' : np.arange(0, 200 ),
        'metric' : [ 'euclidean' , 'manhattan' ]
    }                 
)

meilleur_model = model.best_estimator_

meilleur_model = KNeighborsClassifier(c:181 , metric: 'euclidean')

model.score( X_test , y_test )
```

# exo 

- en utilisant le dataset titanic 
- et en utilisation le model KNeighborsClassifier
- faire un split entre les données de test / donnée de train
- entrainer votre model
- donner lui un score
- recherché via `GridSearchCV` quels sont les meilleurs paramètres pour le modèle `KNeighborsClassifier`



```py
import numpy as np 
import pandas as pd 

titanic = pd.read_csv("titanic_dataset.csv")

titanic = titanic.drop(["PassengerId","Name" , "SibSp" , "Parch" , "Ticket" , "Fare"  , "Cabin" , "Embarked" ] , axis=1)

titanic = titanic.dropna(axis=0)

titanic["Sex"] = titanic["Sex"].map({ 'male' : 0 , 'female' : 1 })

y = titanic["Survived"]
y = y.values.reshape(-1,1)

X = titanic.drop(["Survived"] , axis=1)

X.shape , y.shape

from sklearn.model_selection import train_test_split

X_train, X_test , y_train , y_test = train_test_split( X , y , test_size=0.2 , random_state=42 )

from sklearn.neighbors import KNeighborsClassifier

model = KNeighborsClassifier(n_neighbors=2 , metric='manhattan' )

model.fit(X_train ,y_train  )

score = model.score(X_test , y_test) # 0.7952380952380952

score



from sklearn.model_selection import GridSearchCV 

param_grid = {
    'n_neighbors' : np.arange(1, 20),
    'metric' : [ 'euclidiean' , 'manhattan'  ]
}

grid = GridSearchCV(
    KNeighborsClassifier() ,
    param_grid,
    cv=5
)

grid.fit( X_train , y_train )

model = grid.best_estimator_

model.score(X_test , y_test)

```

# last exo 

En utilisant le dataset du iris et en utilisant le modèle KNeighborsClassifier

- séparer votre dataset en train et test
- déterminer quelles sont les meilleures valeurs pour les meta paramètres de l’estimateur en utilisant GridSearchCV
- déterminer les erreurs que génére le model entrainé avec `confusion_matrix`

