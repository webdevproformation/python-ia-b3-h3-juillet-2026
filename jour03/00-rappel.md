# Pandas

- fichier excel, Base de données, json , xml, text, fichier html
- extraire et les ranger dans `DataFrame` (qui ressemble à un excel)
- plein de fonction de nettoyage
- plein de fonction de Statistique (data.describe())
- jointure (data.merge())
- donnée temporelle
- sur les données temporelles => moyenne / statistiques
- visualiser des données 


```py
fleurs = [["jasmin", "tulipe", "rose"]]
#            [0][0]
```


```py
fleurs = pd.DataFrame([["jasmin", "tulipe", "rose"], [12,21,33]])
#     

fleurs.loc[0,"nom"]       0



bitcoin.loc["2024-01": "2025-02","prix"]

```