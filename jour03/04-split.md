
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
