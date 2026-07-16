# spécialité de Pandas c'est de générer les séries avec dates

Séries temporelles transformer la colonne d'index qui par défaut est numéroté par une date

- Bitcoin - https://www.coingecko.com/en/coins/bitcoin/historical_data?start=2010-06-13&end=2026-06-13
- Etherium - https://www.coingecko.com/en/coins/ethereum/historical_data?start=2015-08-07&end=2026-06-13

---

# Exo 

- Utiliser le fichier qui présente le cours de l'Etherium
- sur ce fichier vous allez afficher dans un graphique l'évolution du prix de cette devise electronique entre février 2022 et avril 2023


```py
etherium = pd.read_csv("eth-usd-max.csv" , index_col="event_date" , parse_dates=True)

# vous allez afficher dans un graphique l'évolution du prix 
# de cette devise electronique entre février 2022 et avril 2023

etherium.loc["2022-02":"2023-04" ,"close_price_usd"].plot()
```


# Exo 

- maitenant que vous avez chargé à la fois bitcoin et etherium 
- pour vous afficher les deux devises sur la période 2025 sur un 1 seul graphique
- astuce attention vous devez utiliser la fonction `.merge()` de pandas pour fusionner les deux Dataframe


```py
etherium = pd.read_csv("eth-usd-max.csv" , index_col="event_date" , parse_dates=True)
bitcoin = pd.read_csv("btc-usd-max.csv" , index_col="event_date" , parse_dates=True)

eth_bit = pd.merge(bitcoin ,etherium , on="event_date" , how="inner" , suffixes=["_bitcoin", "_etherium"]  )

eth_bit.loc["2025", [ "close_price_usd_bitcoin" , "close_price_usd_etherium" ]].plot()
```