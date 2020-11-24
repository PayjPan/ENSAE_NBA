
# Table of Contents

1.  [Questions](#org7dc9950)
    1.  [Une métrique pour comprendre l'importance des variables ?](#org5738f22)
    2.  [Comment avoir des variables quantitatives](#org9c8f089)
2.  [Retours](#org8349935)
3.  [Plan de route](#org1cba3e5)



<a id="org7dc9950"></a>

# Questions


<a id="org5738f22"></a>

## Une métrique pour comprendre l'importance des variables ?

**Ici pas besoin de s'embêter car finalement on va faire une séléction automatique des variables**

Mais pour savoir si le rang de l'équipe influence sur le score moyen d'un joueur on peut utiliser : 

-   [Tau de Kendall](https://fr.wikipedia.org/wiki/Tau_de_Kendall) : permet de caractériser la corrélation entre deux variables de rang


<a id="org9c8f089"></a>

## Comment avoir des variables quantitatives

Pour pouvoir utiliser des variables qualitatives comme le score la chose à faire est un **lagged variables**. On prends les variables de score et on les décales temporairement : on peut prendre par exemple les scores des trois derniers matchs.

**Utiliser la fonction \`pandas.shift\` pour décaler les variables**

Il faut bien se rendre compte aussi que nous avons des variables indexées par \(t\) et par \(i\) (par le temps et par le joueur) donc il faudra refléchire à comment les mettres en relation.


<a id="org8349935"></a>

# Retours

Ce qu'il faut retenir c'est que pour faire de la *data science* il faut pas commencer par faire des statistiques descriptives. En faite, on ne peut que voir des **relations monotones** avec ces méthodes.

Des models comme **arbre de décision** ou **random forest** rendent compte de relations non monotones.

Il ne faut pas partir sur de la série temporel car nous n'avons pas encore fait les cours.

Pour la séléction de variable prévilégier les modèles directement :

-   [Lasso](https://fr.wikipedia.org/wiki/Lasso_(statistiques)) : prédicteur efficace quand les variables sont peu corrélées (norme \(L_1\))
-   [Ridge](https://fr.wikipedia.org/wiki/R%C3%A9gularisation_de_Tikhonov) : prédicteur efficace quand les variables sont beaucoup corrélées (norme \(L_2\))
-   [Elsatic Net](https://en.wikipedia.org/wiki/Elastic_net_regularization) : un mélange des deux

Pour utiliser proprement un de ces modèles il faut bien choisir les hyperparamètres :

-   [Grid search](https://fr.wikipedia.org/wiki/Hyperparam%C3%A8tre) : On créer une grille avec des incréments des hyperparamètres et on les tests (tous ou pas)
-   [Cross Validation](https://fr.wikipedia.org/wiki/Validation_crois%C3%A9e) : méthode d'estimation de fiablitité d'un modèle fonder sur l'échantillonage
-   [K-fold Cross Validation](https://en.wikipedia.org/wiki/Cross-validation_(statistics)#k-fold_cross-validation) : cross validation avec des échantillonages temporels


<a id="org1cba3e5"></a>

# Plan de route

-   Étape 1 : Faire l'inventaire de toutes les variables que l'on peut vouloir utiliser sans trop se pencher sur leur pertinance
-   Étape 2 : Créer le dataset énorme avec toutes les variables
-   Étape 3 : Choisir un modèle (Lasso/Ridge/Elastic)
-   Étape 4 : Appliquer un *grid search* (séléction d'hyperparamètres) coupler à un *k fold cross validation*

