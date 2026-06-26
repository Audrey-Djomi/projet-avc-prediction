Nous avons collecté nos données sur le site kaggle : https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset?resource=download


La taille du dataset : 5110 lignes, 12 colonnes soit 5110 patients observés.
## Informations sur nos variables

Variable	    Signification
id	            Identifiant patient
gender	        Sexe
age	            Âge
hypertension	Hypertension (0 = Non, 1 = Oui)
heart_disease	Maladie cardiaque (0 = Non, 1 = Oui)
ever_married	Déjà marié(e)
work_type	    Type d'emploi
Residence_type	Urbain ou Rural
avg_glucose_level	Glycémie moyenne
bmi	            imc: Indice de masse corporelle
smoking_status	Statut tabagique
stroke	        AVC (0 = Non, 1 = Oui)

Nous avons les variables numériques, les varaibles catégorielles et binaires.
Le dataset présente une excellente qualité globale. Seule la variable bmi contient des valeurs manquantes, représentant environ 3,9 % des observations. Toutes les autres variables sont complètes.

## Notre variable cible
Notre variable cible est stroke, on allons chercher à la comprendre.
Aucun doublon complet n'a été identifié dans le jeu de données.