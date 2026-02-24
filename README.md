# Classification Chats vs Chiens - Projet Jupyter

Projet de classification d'images basé sur le matériel du cours AI_4-6
(Introduction à l'AI).

Ce projet utilise un réseau de neurones convolutif (CNN) pour effectuer
une classification binaire d'images : - 0 = Chat - 1 = Chien

## Structure attendue du dataset

Placer un fichier zip (ex. `kagglecatsanddogs_5340.zip`) à la racine du
projet.

Dataset compatible :
https://download.microsoft.com/download/3/E/1/3E1C3F21-ECDB-4869-8368-6DEBA77B919F/kagglecatsanddogs_5340.zip

Structure typique après extraction :

PetImages/ Cat/ image1.jpg image2.jpg ... Dog/ image1.jpg image2.jpg ...

Chaque sous-dossier correspond à une classe.

Si aucun fichier zip n'est trouvé, le notebook peut utiliser un dataset
de secours pour démonstration.

## Installation

Installer les dépendances :

pip install -r requirements.txt

## Lancer le notebook

jupyter notebook cats_vs_dogs.ipynb

Exécuter les cellules dans l'ordre.

## Étapes du projet (dans le notebook)

1.  Import des bibliothèques et configuration
    -   Import de NumPy, TensorFlow, Matplotlib
    -   Définition des paramètres globaux (taille image, nombre
        d'images, chemins)
2.  Extraction et chargement des données
    -   Extraction du fichier zip si nécessaire
    -   Lecture des images
    -   Redimensionnement
    -   Création des labels (0 = Chat, 1 = Chien)
3.  Visualisation des données
    -   Affichage d'exemples d'images
    -   Vérification du bon chargement
4.  Pré-traitement
    -   Conversion en tableaux NumPy
    -   Normalisation des pixels (division par 255)
    -   Passage des valeurs de \[0--255\] à \[0--1\]
5.  Séparation des données
    -   Division en train / validation / test
    -   Utilisation de stratify
    -   random_state pour reproductibilité
6.  Construction du modèle CNN
    -   Couches Conv2D
    -   MaxPooling
    -   Flatten
    -   Dense
    -   Dropout
    -   Activation Sigmoid en sortie
7.  Compilation du modèle
    -   Fonction de perte (binary_crossentropy)
    -   Optimiseur (Adam)
    -   Métrique (accuracy)
8.  Entraînement
    -   model.fit
    -   Définition du nombre d'epochs
    -   Validation pendant l'entraînement
    -   Callbacks (EarlyStopping, ReduceLROnPlateau)
9.  Analyse des performances
    -   Graphiques loss / val_loss
    -   Graphiques accuracy / val_accuracy
    -   Identification du surapprentissage (overfitting)
10. Évaluation finale
    -   Test sur données jamais vues
    -   Mesure de la performance finale
11. Sauvegarde du modèle
    -   Export du modèle entraîné
    -   Possibilité de le recharger ultérieurement

## Objectif pédagogique

Ce projet permet de comprendre :

-   Le pipeline complet d'un projet de Deep Learning
-   Le rôle du pré-traitement
-   Le fonctionnement des CNN
-   Le concept d'epoch
-   La différence entre entraînement et évaluation
-   Les notions d'overfitting et d'underfitting
