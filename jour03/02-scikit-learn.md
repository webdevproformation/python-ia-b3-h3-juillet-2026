# scikit learn

- librairie qui fait partie de l'écosysteme calcul scientifique sur Python
- comme NymPy, Matplot et Pandas

- pour quoi utiliser scikit learn 
- pour faire du ML : Machine Learning 

- librairie est opensource  / utiliser pour ML / AA Apprentissage Automatique
- permet l'analyse de données => créer des modèles prédictifs 

Markov 

- outil de modélisation PREDICTIVE PERFORMANT

# la grande force de scikit learn 

- API SIMPLE ET HOMOGENE
- bonne documentation MAIS technique 
- https://scikit-learn.org > User Guide > 14 Choosing the right estimator > graphique qui fait la synthèse

IA => Machine Learning on fait en générale 2 choses :

- régression : le fait d'estimer une valeur en fonction de critères / valeur continu
- classification : estimer quelque chose qui n'est pas continu 
- clustering : le fait de regrouper des données similaires 


# l'objectif c'est de prédire 

<https://scikit-learn.org/stable/machine_learning_map.html>

```py
model = LinearRegression() // choisir le modele mathématique le plus adapté

model.fit(X , y)     // phase d'entrainement 

model.score(X, y)    // note 

model.predict(X)    // utilise 
```
