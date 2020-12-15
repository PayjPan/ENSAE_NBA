# Projet Python Data Scientist : TrashTalk Fantasy League

Ce projet réalisé le cadre du cours Python pour le Data Scientist de 2A, a pour but d'étudier les statistiques NBA afin de choisir, chaque jour le joueur qui réalisera le meilleur score TrashTalk Fantasy League.

## Introduction

Dans le cadre de ce projet python, nous nous sommes intéressés aux statistiques de la NBA avec une idée en tête, gagner la 
Trashtalk Fantansy League. 
#### Qu'est-ce que la TrashTalk Fantasy League (TTFL)
Chaque soir où un match NBA se joue, les joueurs de TTFL ont la possibilité de selectionner un joueur, à partir des performances effectives
de ce dernier, un score est calculé : le score TTFL. C'est ce score là qui est alors réalisé par le joueur de TTFL.

Dans ce cas, quoi de plus facile que de selectionner le meilleur joueur de la NBA chaque soir ?
Un joueur n'est selectionnable qu'une fois tous les 30 jours, obligeant le joueur TTFL à redoubler d'effort pour s'assurer le meilleur score possible chaque soir. La saison NBA est longue, 82 matchs et il faut être le plus régulier pour espérer remporter la Trash Talk Fantasy league.

Le rendu se compose de 5 notebooks, chacun correspondant à une étape du projet.

## Exploration
Nous nous familiarisons avec l'API **nba-api**, qui met à disposition de nombreuses bases de données autour de la NBA
[Exploration](<../master/rendu/1 - Exploration.ipynb>)

## Récupération
Nous récupérons les données nécéssaires à la construction d'un grande base de données qui sera analysée et utilisée pour faire de la prédiction.
[Récupération](<../master/rendu/2 - Récupération.ipynb>)

## Préparation
Nous faisons des opérations sur la base de données pour pouvoir lui appliquer les modèles. En particulier, enlever la temporalitée des données : on ne doit pas connaitre le résultat du match avant que celui-ci ne soit jouer. 
[Préparation](<../master/rendu/3 - Préparation.ipynb>)

## Analyse 
Nous commençons par faire quelques statistiques descriptives sur notre base. Nous les utilisons pour répondre aux premières questions que se posent le joueur TTFL au moment de faire son choix.
[Analyse](<../master/rendu/4 - Analyse.ipynb>)

## Prédiction
Nous explorons des modèles de Machine Learning (Lasso, Ridge) afin de prédire le score TTFL.
[Prédiction](<../master/rendu/5 - Modèles.ipynb>)

## Prolongements
Dans le fond, c'est surtout le classement prédit qui nous intéresserait pour choisir un joueur chaque soir. Si les prédictions sont à côté de la réalité mais correctement ordonnées alors le contrat est rempli.
    On pourrait essayer de comparer nos modèles de regression (qui prédisent le score) à des modèles de classification (qui prédiraient si un joueur sera dans le top 10). On pourrait également comparer nos modèles linéaires à des modèles non-linéaires (RandomForest par exemple)
    Dans la mesure où l'on ne peut choisir un joueur qu'une fois tous les 30 jours, il serait intéressant d'implémenter un algorithme qui optimise le choix des joueurs pour maximiser le total de point engrangés sur 30 jours.
    Affaire à suivre...
