# Correction

```py
# copier les données dans une variable qui s'appelle data

data = bitcoin.copy()

#ajouter 2 colonnes dans data rempli de 0
data["Acheter"] = np.zeros(len(data))
data["Vendre"] = np.zeros(len(data))

# grâce aux calculs que l'on va faire 0 (ne rien faire) ou -1 (soit acheter / vendre)

data["RollingMax"] = data["close_price_usd"].shift(1).rolling(window=28).max()
data["RollingMin"] = data["close_price_usd"].shift(1).rolling(window=28).min()

# logique 

data.loc[ data["RollingMax"] < data["close_price_usd"] , "Acheter" ] = 1
data.loc[ data["RollingMin"] > data["close_price_usd"] , "Vendre" ]  = -1

# data.tail()
# présenter sous forme de graphique notre Dataset

start= "2025-01"
end  = "2026-06"

fig, ax = plt.subplots(2,1,sharex=True,figsize=(12,8))

ax[0].plot(data.loc[start:end , "close_price_usd"])
ax[0].plot(data.loc[start:end , "RollingMax"])
ax[0].plot(data.loc[start:end , "RollingMin"])
ax[0].legend(["price", "max 28j roulant", "min 28j roulant"])

ax[1].plot(data["Acheter"][start:end] , c="g")
ax[1].plot(data["Vendre"][start:end] , c="r")
ax[1].legend([ "Acheter", "Vendre" ])
```