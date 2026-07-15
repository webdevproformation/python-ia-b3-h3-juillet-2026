# exo 

à partir du code suivant :

{
    "releve 1" : [],
    "relevé 2" : []
}

```py
# datasets  c'est dictionnaire
# 
datasets = { f"releve {i}" : np.random.randn(100) for i in range(1,4) }

```

la question : pouvez vous réaliser le graphique suivant `08-exo-matplot.png` dans google colab

# correction

```py
# correction
import matplotlib.pyplot as plt
import numpy as np 

np.random.seed(42)

# dataset (données)
datasets = { f"releve {i}" : np.random.randn(100) for i in range(1,4) }
# dessiner sous forme de graphique
plt.figure( figsize=( 10 , 8 ) )
i = 1
for label in datasets :
  Y = datasets[label]
  plt.subplot( len(datasets), 1 ,   i)
  plt.title( label )
  plt.xlabel("temps")
  plt.ylabel("euros")
  X = np.arange(0, len(Y))
  plt.plot( X , Y )
  i = i + 1

plt.tight_layout()
```