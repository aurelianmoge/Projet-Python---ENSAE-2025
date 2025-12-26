# Projet-Python---ENSAE-2025

**Vulnérabilité aux pollutions et caractéristiques sociodémographiques des territoires**

Auteurs : *Réda Bounechar, Juliette Lesné, Aurélian Moge*

**Sujet :**

Les territoires ne sont pas exposés de manière homogène aux effets du changement climatique et aux dégradations environnementales qui l’accompagnent. Dans ce projet, nous avons cherché à analyser le lien entre vulnérabilité sociale et vulnérabilité climatique, afin de déterminer si certains territoires cumulent plusieurs formes de risques. En nous concentrant sur la région Île-de-France, nous étudions la relation entre, d’une part, les caractéristiques sociodémographiques et territoriales des communes — telles que la superficie, la densité de population, la composition socioprofessionnelle, le niveau de revenu médian ou encore la dotation en infrastructures — et, d’autre part, l’exposition de leurs populations à différentes formes de pollution. Plus précisément, notre analyse porte sur les effets mesurables de la dégradation de l’environnement local, appréhendée principalement à travers la qualité de l’air. À cette fin, nous construisons plusieurs modèles économétriques visant à expliquer les concentrations de pollution atmosphérique à partir de caractéristiques sociales et géographiques des territoires.

**Problématique :**

Les territoires les plus exposés aux pollutions sont ils également des espaces plus vulnérables socialement ? Quels sont les liens entre vulnérabilité climatique, vulnérabilité sociale et géographie ? Quelles sont les caractéristiques des territoires les plus exposés aux pollutions en Ile-de-France ?

**Plan :**

A RAJOUTER QUAND CE SERA FINALISE


**Modèle utilisé :**

Nous avons utilisé principalement la régression logistique qui permet d'estimer la concentration atmosphérique en NO2 en fonction de différentes variables explicatives, démographiques, sociales, et géographiques.

**Données utilisées :**

- Dossier des installations industrielles rejetant des polluants sur Géorisques (https://files.georisques.fr/irep/2023.zip) (2024) : exploitation des fichiers recensant les établissements polluants, celui concernant les rejets, celui des émissions, et celui des déchets dangereux.

- fichier avec les shapefiles des communes de Data.gouv (https://www.data.gouv.fr/api/1/datasets/r/0e117c06-248f-45e5-8945-0e79d9136165) (2022)

- dossier complet de l'INSEE sur le site Insee.fr (https://www.insee.fr/fr/statistiques/fichier/5359146/dossier_complet.zip) (2025)

- fichier sur la pollution de l'air de Data.gouv (https://www.data.gouv.fr/api/1/datasets/r/da7a4869-b584-48ad-8a81-784a02eb297a) (2018)

- fichier avec les shapefiles des communes pour avoir les arrondissements de Paris, depuis le site de la ville de Paris (https://opendata.paris.fr/api/explore/v2.1/catalog/datasets/arrondissements/exports/csv?lang=fr&timezone=Europe%2FBerlin&use_labels=true&delimiter=%3B) (2016)

Toutes les données récupérées dans ce projet sont en accès public.

**Navigation au sein du projet :**

 Il suffit d'exécuter successivement les cellules du notebook : FICHIER PROPRE.ipynb


**Description des packages :**

- geopandas permet de manipuler des geodataframes.


- contextily récupère des cartes sur internet.


- matplotlib.pyplot permet de faire des graphiques.


- pandas permet de manipuler des dataframes.

- requests permet de récupérer des url (et en l'occurrence d'importer les données publiques).

- zipfile permet d'extraire les fichiers zip qu'on a importé par requests.

- re permet de travailler avec des expressions régulières.

- sklearn est conçu pour le machine learning et permet, dans notre cas, de construire simplement des modèles, notamment de régression linéaire.

- scipy est orienté initialement vers le calcul mathématique mais nous permet, après avoir construit nos régressions, de tester simplement les liens statistiques entre les variables. 

- statsmodels.api dispose de fonctions pour la modélisation statistiques absentes de scikit learn, par exemple sm.add_constant et sm.Logit que nous utilisons pour la régression logistique.

