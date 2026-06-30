# Journal de bord

## Jour 1 - Initialisation du projet

### Objectif

Démarrer un nouveau projet Data Analytics orienté santé afin d'étudier les facteurs de risque associés aux accidents vasculaires cérébraux (AVC).

### Réalisations

- Création du dépôt GitHub `projet-avc-prediction`
- Mise en place de l'architecture du projet
- Clonage du dépôt en local
- Création de l'environnement virtuel Python
- Installation des bibliothèques nécessaires au projet
- mise en place du requirements pour les bibliothèques utilisées
- Préparation des notebooks d'exploration, de nettoyage et d'analyse
- Sélection du dataset "Stroke Prediction".
- Télécharger le dataset AVC via le site Kaggle: https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset?resource=download 
- Vérification de la pertinence du jeu de données au regard d'une problématique de santé publique.
- Identification des principaux facteurs de risque étudiés : âge, hypertension, maladie cardiaque, IMC, glycémie et tabagisme.
- Préparation du notebook d'exploration pour la compréhension et l'analyse des données.

## Jour 2- Exploration du dataset

Le dataset sélectionné contient 5 110 observations et 12 variables.

Chaque ligne représente un patient et comprend des informations démographiques, médicales et comportementales telles que l'âge, le sexe, l'hypertension, les maladies cardiaques, l'IMC, la glycémie et le statut tabagique.
Cette structure permet d'étudier les facteurs potentiellement associés au risque d'AVC.

La variable cible du projet est `stroke`, indiquant si le patient a subi un AVC (1) ou non (0).

L'analyse de la structure des données montre une combinaison de variables numériques, binaires et catégorielles permettant d'étudier différents facteurs de risque associés aux AVC.

### Qualité des données

- Aucun doublon n'a été identifié.
- Une seule variable présente des valeurs manquantes : `bmi`.
- 201 observations sont concernées, soit environ 3,9 % du jeu de données.

### Premières observations

- Âge moyen : 43 ans.
- 9,7 % des patients présentent une hypertension.
- 5,4 % présentent une maladie cardiaque.
- 4,9 % des patients ont subi un AVC.

La variable cible `stroke` apparaît fortement déséquilibrée avec une majorité de patients n'ayant pas subi d'AVC.
### Analyse des variables catégorielles

L'exploration met en évidence une forte majorité de patients n'ayant pas subi d'AVC (95,1 % contre 4,9 %).

La population étudiée est composée majoritairement de femmes (58,6 %).

La variable `smoking_status` présente une proportion importante de patients dont le statut tabagique est inconnu (environ 30 % des observations).

Les populations urbaines et rurales sont représentées de manière relativement équilibrée.

Une première analyse suggère un taux d'AVC légèrement plus élevé chez les hommes que chez les femmes, bien que l'écart reste limité.

### Analyse préliminaire de l'âge

Une comparaison de l'âge moyen selon la survenue d'un AVC met en évidence une différence importante entre les deux groupes.

- Patients sans AVC : 42 ans en moyenne
- Patients avec AVC : 67,7 ans en moyenne

L'écart observé d'environ 26 ans suggère une forte association entre l'âge et le risque d'AVC. Cette variable apparaît comme un facteur majeur à investiguer dans les analyses suivantes.

### Analyse des facteurs de risque

Une analyse croisée entre les caractéristiques médicales des patients et la survenue d'un AVC met en évidence plusieurs associations importantes.

#### Âge

Les patients ayant subi un AVC présentent un âge moyen de 67,7 ans contre 42 ans pour les autres patients.

#### Hypertension

Le taux d'AVC atteint 13,3 % chez les patients hypertendus contre 4,0 % chez les patients non hypertendus.

#### Maladie cardiaque

Les patients atteints d'une maladie cardiaque présentent un taux d'AVC de 17 %, contre 4,2 % chez les autres patients.

Ces premiers résultats suggèrent que l'âge, l'hypertension et les maladies cardiaques constituent les principaux facteurs associés au risque d'AVC dans ce jeu de données.
#### Glycémie

Les patients ayant subi un AVC présentent une glycémie moyenne de 132,5 contre 104,8 chez les autres patients.

#### IMC

L'IMC moyen est légèrement plus élevé chez les patients ayant subi un AVC (30,5 contre 28,8).

#### Tabagisme

Le taux d'AVC le plus élevé est observé chez les anciens fumeurs (7,9 %), suivi des fumeurs actuels (5,3 %) et des non-fumeurs (4,8 %).

Ces résultats suggèrent une association entre certaines habitudes de vie et la survenue d'un AVC, bien que des analyses complémentaires soient nécessaires pour tenir compte de facteurs de confusion tels que l'âge.

### Prochaines étapes
- début nettoyage : prise de décisions sur la variable
- bmi qui contient 201 valeurs manquantes
- gender pour le sexe Other
- smoking_status pour Unknown

## Jour 3- Debut Nettoyage du dataset
### Traitement des valeurs manquantes

La variable `bmi` présentait 201 valeurs manquantes, soit 3,93 % du jeu de données.

L'analyse de la distribution a montré une légère asymétrie à droite ainsi que la présence de valeurs extrêmes (IMC maximal de 97,6).

Afin de conserver l'ensemble des observations tout en limitant l'influence des valeurs extrêmes, les valeurs manquantes ont été imputées par la médiane (28,1), méthode plus robuste que la moyenne dans ce contexte.

## Jour 4 - Fin nettoyage du dataset

###  Nettoyage des données

Les décisions suivantes ont été prises pour préparer les données :

- La colonne `id`, utilisée uniquement comme identifiant technique, a été supprimée car elle n'apporte aucune information utile à l'analyse.
- L'unique observation appartenant à la catégorie `Other` de la variable `gender` a été exclue en raison de son effectif insuffisant.
- La catégorie `Unknown` de la variable `smoking_status` a été conservée, car elle constitue une information à part entière et concerne une proportion importante des observations.

À l'issue de cette étape, le jeu de données contient 5 109 observations, 11 variables et aucune valeur manquante.
- Nous avons stocker notre dataset stroke clean dans notre repertoir data. Nous l'utiliserons pour la suite de nos analyses, ainsi que sur Power BI.

