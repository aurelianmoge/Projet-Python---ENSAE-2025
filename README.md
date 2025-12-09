# Projet-Python---ENSAE-2025
Depôt Github pour le projet de Data Science sur la cartographie des vulnérabilités climatiques auxquelles sont inégalement exposés les territoires de France hexagonale.


Comment utiliser le Github ?

**Description des packages**
geopandas permet de manipuler des geodataframes.


contextily récupère des cartes sur internet.


matplotlib.pyplot permet de faire des graphiques.


pandas permet de manipuler des dataframes.
requests permet de récupérer des url (et en l'occurrence d'importer les données publiques).
zipfile permet d'extraire les fichiers zip qu'on a importé par requests.
re permet de travailler avec des expressions régulières.
sklearn est conçu pour le machine learning et permet, dans notre cas, de construire simplement des modèles, notamment de régression linéaire.
scipy est orienté initialement vers le calcul mathématique mais nous permet, après avoir construit nos régressions, de tester simplement les liens statistiques entre les variables. 
statsmodels.api dispose de fonctions pour la modélisation statistiques absentes de scikit learn, par exemple sm.add_constant et sm.Logit que nous utilisons pour la régression logistique.

