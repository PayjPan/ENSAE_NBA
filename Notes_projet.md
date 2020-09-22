
# Table of Contents

1.  [Première recherche sur le sujet :](#org5858548)
    1.  [Ressources](#orgd744fba)
    2.  [Trash Talk Fantasy League](#orga4729d5)
    3.  [Calcul des points](#org063b0cd)
    4.  [Plan provisoire](#org73be7d5)
    5.  [Base de données](#org45af751)

<a id="org5858548"></a>

# Première recherche sur le sujet :


<a id="orgd744fba"></a>

## Ressources

- <https://mathematicallysafe.wordpress.com/>: un site qui propose des articles sur l'analyse de données de la premier league de 2015 à 2019

- <https://towardsdatascience.com/beating-the-fantasy-premier-league-game-with-python-and-data-science-cf62961281be>: un article qui parle de comment deux personnes ont utilisé l'analyse de données pour choisir les joueurs pour le FPL. 

- <https://arxiv.org/pdf/1912.07441.pdf>: une publication scientifique sur l'analyse de données pour le FPL. Ils observent que la plus part des prédictions sont faites uniquement sur les données historiques et ne prends donc pas en comptes les blessures, et autres décisions extérieurs. Ils utilisent pour ça Twitter.

- <https://builtin.com/data-science/data-analytics-fantasy-football>: un article sur l'évolution de la prédiction des données dans le monde des fantasy leagues.

- <https://www.reddit.com/r/NBAanalytics/> : subreddit sur l'analyse de données de la nba.


<a id="orga4729d5"></a>

## Trash Talk Fantasy League

Ce fantasy league est un peu différente des autres que j'ai pu voir comme FPL. Ici on n'a pas à payer pour avoir accès aux joueurs mais on a une limite de choix (chaque joueur ne peut être choisi qu'un fois tout les trente jours)
Chaque soir il faut choisir un joueur parmis toute la league qui rapportera le plus de points.
Les points sont calculés par une formule qui ne nous est pas donnée.


<a id="org063b0cd"></a>

## Calcul des points

Dans le code de la page web de la calculatrice on a la fonction :

    function calcScore(){
    
          var bonus = parseInt($('#inputPoints').val())+parseInt($('#inputRebonds').val())+parseInt($('#inputPasses').val())+parseInt($('#inputInterceptions').val())+parseInt($('#inputContres').val())+parseInt($('#inputTiresreussis').val())+parseInt($('#input3pointsreussis').val())+parseInt($('#inputLancersreussis').val());
    
          var malus = parseInt($('#inputBallesperdues').val())+parseInt($('#inputTirsrates').val())+parseInt($('#input3pointsrates').val())+parseInt($('#inputLancersrates').val());
    
    
           $('#score').html(parseInt(bonus)-parseInt(malus));
    
        }

On a donc comme calcul : 

\[Bonus = points + rebonds + passes + interceptions + contres + tires_reussis + 3_points_reussis + lancers_reussis\]
\[Malus = balles_perdues + tires_rates + 3_points_rates + lancers_rates\]
$$Score = Bonus - Malus


<a id="org73be7d5"></a>

## Plan provisoire

-   Choisir le meilleur joueur chaque match 
    -   Prédiction des toutes ses statistiques
        -   Choisir les bases de données
        -   Ajouter des données journalistiques type twitter ?
        -   Choisir les variables

-   Prendre en compte la limite de 30 jours ? 
    -   Comprendre les implications
    -   Quelles contraintes peut on rajouter pour le prendre en compte


<a id="org45af751"></a>

## Base de données

-   sites :
    -   stats.nba.com
    -   www.basketball-reference.com
    -   hoopshype.com
    -   www.nbadraft.net
    -   basketball.realgm.com
    -   www.basketballinsiders.com
    -   sportsdata.io/developers/data-dictionary/nba (payant)

-   librairie pyhton : 
    -   nba<sub>py</sub> (vieux de 5 ans)
    -   nba<sub>api</sub> (tuto : <https://www.playingnumbers.com/2019/12/how-to-get-nba-data-using-the-nba_api-python-module-beginner/>)

-   librairie R : 
    -   nbastatR (2 ans) : permet d'accéder très facilement à un grand nombre de site de statistique sur le basket

-   un scrap de toutes les les saisons play by play de 1996 à 2020 !!!!!
    -   <https://github.com/Jeffery-777/NBA-PBP-Scrape>

