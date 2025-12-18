# Bor minőség osztályozás – Gépi tanulás beadandó

Ez a projekt a Kaggle **Wine Quality Dataset** adatbázisán alapul.
A cél egy bináris osztályozó neurális háló létrehozása, amely képes
megbecsülni, hogy egy bor **jó minőségű-e** vagy sem a kémiai jellemzői alapján.

A projekt a *Gépi tanulás és adattudomány* tantárgy beadandó feladatának
követelményei szerint készült.

---

## 📊 Adatbázis

- Forrás: https://www.kaggle.com/datasets/yasserh/wine-quality-dataset
- Fájl: `datasets/WineQT.csv`
- Mintaszám: 1143
- Változók száma: 13 (numerikus)

A `quality` oszlop szolgál célváltozóként.

---

## Feladat megfogalmazása

Bináris osztályozás:
- **1** → jó minőségű bor (quality ≥ 6)
- **0** → rossz minőségű bor (quality < 6)

---

## Használt feature-ök

A modell tanításához legalább 6 feature került kiválasztásra:

- fixed acidity  
- volatile acidity  
- citric acid  
- residual sugar  
- alcohol  
- sulphates  

### Származtatott feature
- `acid_ratio` = fixed acidity / volatile acidity  

Ez a mutató az össz-savasság és az illósav arányát fejezi ki, amely
érzékszervileg is releváns a bor minősége szempontjából.

---

## Adatelőkészítés

- Hiányzó értékek ellenőrzése (nem volt hiányzó adat)
- Outlier szűrés **IQR (Interquartile Range)** módszerrel
- Numerikus adatok **StandardScaler** segítségével standardizálva
- Tanító–teszt adathalmaz szétválasztása (80% / 20%)

---

## Vizualizációk

- Feature-ek eloszlása és kiugró értékek megjelenítése (boxplot)
- A neurális háló tanítás és validáció közbeni pontosságának vizualizálása
  epochok mentén

---

## Neurális háló felépítése

A modell egy **Dense-layeres feedforward neurális háló**, amely legalább
öt rejtett réteget tartalmaz:

- ReLU aktivációjú Dense rétegek
- Dropout rétegek a túlillesztés csökkentésére
- Sigmoid kimeneti réteg bináris osztályozáshoz

### Optimalizálás
- Optimizer: Adam
- Loss: Binary Crossentropy
- Metrika: Accuracy

---

## Eredmények

- A modell **75% feletti pontosságot** ér el validációs és teszt adathalmazon
- A tanítás során a tanulási folyamat vizuálisan követhető

---

## Használt technológiák

- Python 3.12
- Pandas
- NumPy
- Scikit-learn
- TensorFlow / Keras
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## ▶Futtatás

1. Klónozd a repót
2. Aktiváld a virtuális környezetet
3. Nyisd meg a `main.ipynb` fájlt
4. Futtasd a cellákat felülről lefelé

---

## Projekt struktúra

