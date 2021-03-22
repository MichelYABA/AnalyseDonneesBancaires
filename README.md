# AnalyseDonneesBancaires
Ce projet consiste à faire des analyses sur les clients d'une banque fictive en vue de savoir les raisons des départs anormaux

L'analyse est faire sur l'outil Tableau sur un dataset de 10000 clients.
La banque ayant constaté le taux de départ anormal de ses clients a décidé de faire une analyse des ses données pour connaitre les raisons.
Cette analyse consiste à :
- Connaitre le nombre de clients par pays 
- A/B Test sur le genre (le graphe obtenu permet de déduire qu'il y a 16% d'hommes qui partent contre 25% de femmes)
- Test sur les pays (Il y a 32% des clients qui quittent la banque en Allemagne contre 17% en Espagne et enfin 16% en France)
- A/B test sur les cartes de crédit (21% des clients n'ayant pas de cartes de crédit partent contre 20% des clients ayant une carte de crédit)
- A/B test sur l'activité du client (27 % des clients qui partent ne sont pas des membres actifs, 14% d'entre eux sont des membres actifs)
- Test sur le nombre de produits du clients (Ce test permet de déterminer la raison du départ des clients en fonction du nombre de produit qu'il  a dans la banque. 
On constate alors qu'il y a  28% des clients qui partent en ayant 1 seul produit.
8% pour 2 produits; 83% pour 3 produits et 100% pour 4 produits. Ces résultats doivent présenter des anomalies car normalement un client 
qui a bcp de produit est susceptible de rester car cela montre sa fidélité à la banque.)

De ces analyses, on peut déjà en déduire que le sexe du client, la localision, l'activité du client a un fort impact sur le départ des clients.
- Validation des résultats (On choisit une variable qui ne va avoir aucun impact sur la décision du client de quitter la banque ou pas.  
On choisit par exemple dernier le chiffre de la variable "customer ID" car il n'y a aucune corrélation entre le dernier chiffre de customer ID 
et le fait que le client quitte ou pas la banque. On fait donc un A/B test sur ce dernier chiffre de customer ID qu'on devrait extraire et 
on doit vérifier qu'il y a la même proportion des clients qui quittent la banque dans chacune des 10 catégories de ce dernier chiffre du Customer ID càd 0 à 9.
Pour faire ce A/B Test, j'ai commencé par créer la variable donnant ce dernier chiffre du Customer ID. On va donc créer une variable calculée à partir de Customer ID comme suit : Right(str(CustomerID), 1)
On obtient une distribution(répartition) des données uniformes pour laquelle il y a à peu près la même proportion des clients qui quittent la banque. On constate aussi que cette proportion est proche de 20%. Le fait d'avoir obtenu une distribution uniforme permet donc de valider les données puisqu'elles sont bien homogènes. En revanche si on obtenu un pourcentage très élevé pour l'une des catégories, cela voudrait dire qu'il y a un problème dans les données puisque cela indiquera une anomalie.)
