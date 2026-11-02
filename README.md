# TP 2 : Du texte au vecteur – Comprendre la logique de la représentation textuelle

##  Module
Introduction à l'Intelligence Artificielle – MLIAEdu

##  Objectif du TP
Ce TP a pour objectif de comprendre comment transformer des données textuelles en représentations numériques exploitables par les algorithmes de Machine Learning.

Deux méthodes de vectorisation sont étudiées :
- **Bag of Words (BoW)** avec `CountVectorizer`.
- **TF-IDF** avec `TfidfVectorizer`.

---

##  Partie 5 : Représentation Bag of Words (BoW)

### Objectif
Transformer plusieurs phrases en vecteurs numériques en comptant le nombre d'occurrences de chaque mot.

### Bibliothèque utilisée
```python
from sklearn.feature_extraction.text import CountVectorizer
```

### Travail réalisé
- Création d'une liste de trois phrases sur le thème du sport.
- Utilisation de `CountVectorizer()` pour créer le vectoriseur.
- Transformation des phrases en une matrice numérique avec `fit_transform()`.
- Affichage des mots extraits avec `get_feature_names_out()`.
- Affichage de la matrice avec `toarray()`.

### 📸 Capture d'écran 1 : Résultat Bag of Words (BoW)

**Insérer ici la première capture d'écran montrant le code et le résultat de CountVectorizer.**

<img width="1366" height="768" alt="im1" src="https://github.com/user-attachments/assets/c4fdb99a-e400-498e-a27f-68a2d91feea0" />


### Questions et réponses

**1. Que représente chaque colonne de la matrice ?**

Chaque colonne représente un mot unique extrait de l'ensemble des phrases. La valeur indique le nombre d'occurrences de ce mot dans chaque phrase.

**2. Quelles sont les limites du modèle Bag of Words ?**

- Il ne comprend pas le sens des mots.
- Il ignore l'ordre des mots.
- Il ne prend pas en compte le contexte.
- Il peut générer des matrices volumineuses lorsque le vocabulaire est important.

**3. Que perd-on en supprimant l'ordre des mots ?**

On perd la structure grammaticale et une partie du sens des phrases.

Exemple :
- Le chien mord l'homme.
- L'homme mord le chien.

Ces deux phrases contiennent les mêmes mots, mais ont des significations différentes.

---

##  Partie 6 : Représentation TF-IDF

### Objectif
Attribuer un poids à chaque mot selon son importance dans un document et sa fréquence dans l'ensemble des documents.

### Bibliothèque utilisée
```python
from sklearn.feature_extraction.text import TfidfVectorizer
```

### Travail réalisé
- Réutilisation des trois phrases précédentes.
- Création du vectoriseur avec `TfidfVectorizer()`.
- Transformation des phrases en matrice TF-IDF.
- Affichage des mots extraits.
- Affichage des poids numériques obtenus.

### Formule TF-IDF

TF-IDF = TF × IDF

- **TF (Term Frequency)** : fréquence d'un mot dans un document.
- **IDF (Inverse Document Frequency)** : mesure l'importance d'un mot selon sa rareté dans l'ensemble des documents.

### 📸 Capture d'écran 2 : Résultat TF-IDF

**Insérer ici la deuxième capture d'écran montrant le code et le résultat de TfidfVectorizer.**

<img width="1366" height="768" alt="im2" src="https://github.com/user-attachments/assets/006af856-f1c9-441e-8a69-07834bfc1e1a" />


### Questions et réponses

**1. Quelle est la différence principale entre BoW et TF-IDF ?**

- BoW compte le nombre d'occurrences de chaque mot.
- TF-IDF calcule un poids qui représente l'importance de chaque mot dans un document.

**2. Pourquoi les mots très fréquents ont-ils souvent un poids faible ?**

Parce qu'ils apparaissent dans plusieurs documents et permettent moins de distinguer un document d'un autre.

Exemples : « le », « la », « est », « et ».

**3. Donnez un exemple concret où TF-IDF serait plus utile que BoW.**

Dans un moteur de recherche, TF-IDF permet d'identifier les mots importants d'un document. Par exemple, pour rechercher des documents sur le football, le mot « football » peut avoir plus d'importance que des mots généraux comme « le » ou « est ».

---

## 📊 Comparaison entre BoW et TF-IDF

| Critère | Bag of Words | TF-IDF |
|---|---|---|
| Principe | Comptage des mots | Pondération des mots |
| Valeurs | Nombre d'occurrences | Poids numériques |
| Importance des mots | Non évaluée | Évaluée |
| Ordre des mots | Ignoré | Ignoré |
| Contexte | Non pris en compte | Non pris en compte |

---

##  Technologies et outils utilisés

- Python
- Scikit-learn
- NumPy
- CountVectorizer
- TfidfVectorizer

##  Conclusion

Ce TP m'a permis de comprendre comment transformer des phrases en données numériques afin de les rendre exploitables par les algorithmes de Machine Learning.

J'ai appris à utiliser deux techniques importantes de représentation textuelle : Bag of Words et TF-IDF, ainsi qu'à comprendre leurs différences, leurs avantages et leurs limites.

**TP réalisé dans le cadre du module Introduction à l'Intelligence Artificielle – MLIAEdu.**
