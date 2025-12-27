# Projet-Python---ENSAE-2025

**Vulnérabilité aux pollutions et caractéristiques sociodémographiques des territoires**

Auteurs : *Réda Bounechar, Juliette Lesné, Aurélian Moge*

**Sujet :**

Les territoires ne sont pas exposés de manière homogène aux effets du changement climatique et aux dégradations environnementales qui l’accompagnent. Dans ce projet, nous avons cherché à analyser le lien entre vulnérabilité sociale et vulnérabilité climatique, afin de déterminer si certains territoires cumulent plusieurs formes de risques. En nous concentrant sur la région Île-de-France, nous étudions la relation entre, d’une part, les caractéristiques sociodémographiques et territoriales des communes — telles que la superficie, la densité de population, la composition socioprofessionnelle, le niveau de revenu médian ou encore la dotation en infrastructures — et, d’autre part, l’exposition de leurs populations à différentes formes de pollution. Plus précisément, notre analyse porte sur les effets mesurables de la dégradation de l’environnement local, appréhendée principalement à travers la qualité de l’air. À cette fin, nous construisons plusieurs modèles économétriques visant à expliquer les concentrations de pollution atmosphérique à partir de caractéristiques sociales et géographiques des territoires.

**Problématique :**

Les territoires les plus exposés aux pollutions sont ils également des espaces plus vulnérables socialement ? Quels sont les liens entre vulnérabilité climatique, vulnérabilité sociale et géographie ? Quelles sont les caractéristiques des territoires les plus exposés aux pollutions en Ile-de-France ?

**Plan :**

**Introduction**

**Partie 1 : Importation des données**
- *1.1. Données de pollution industrielle*
- *1.2. Données géographiques et sociodémographiques*
- *1.3. Recodage pour l'Ile-de-France*
- *1.4. Création de nouvelles variables et sélection des variables d'intérêt*

**Partie 2 : Analyses statistiques descriptives et visualisations**
- *2.1. Description statistique univariée de la base*
- *2.2. Exploration de la cartographie des pollutions*
- *2.3. Lien pollution / conditions sociales : premiers essais*
- *2.4. Conditions sociales et pollution : renversement de perspective*
- *2.5. Corrélations entre pollutions*
- *2.6. Corrélations entre pollution et démographie*

**Partie 3 : Modélisation**
- *3.1. Régression de la qualité de l'air (pm10, o3, no2) sur des variables démographiques et spatiales*
- *3.2. Analyse de l'autocorrélation spatiale dans notre régression OLS finale*
- *3.3. Régression du revenu (variable sociale) sur les variables environnementales*
- *3.4. Saisir les covariations par une ACP*

**Conclusion**



**Répartition du travail**

Réda : 1.2, 2.2, 2.3, 2.6.

Juliette : 1.1, 2.1, 3.2, 3.3.

Aurélian : 1.3, 1.4, 2.4, 2.5, 3.1



**Modèle utilisé :**

Nous avons utilisé principalement la régression linéaire multiple qui permet d'estimer la concentration atmosphérique en NO2 en fonction de différentes variables explicatives, démographiques, sociales, et géographiques, ainsi que, réciproquement, le revenu médian d'une commune en fonction des conditions spatiales et de l'intensité de l'exposition aux facteurs de pollution.

**Données utilisées :**

- Dossier des installations industrielles rejetant des polluants sur Géorisques (https://files.georisques.fr/irep/2023.zip) (2024) : exploitation des fichiers recensant les établissements polluants, celui concernant les rejets, celui des émissions, et celui des déchets dangereux.

- fichier avec les shapefiles des communes de Data.gouv (https://www.data.gouv.fr/api/1/datasets/r/0e117c06-248f-45e5-8945-0e79d9136165) (2022)

- dossier complet de l'INSEE sur le site Insee.fr (https://www.insee.fr/fr/statistiques/fichier/5359146/dossier_complet.zip) (2025)

- fichier sur la pollution de l'air de Data.gouv (https://www.data.gouv.fr/api/1/datasets/r/da7a4869-b584-48ad-8a81-784a02eb297a) (2018)

- fichier avec les shapefiles des communes pour avoir les arrondissements de Paris, depuis le site de la ville de Paris (https://opendata.paris.fr/api/explore/v2.1/catalog/datasets/arrondissements/exports/csv?lang=fr&timezone=Europe%2FBerlin&use_labels=true&delimiter=%3B) (2016)

Toutes les données récupérées dans ce projet sont en accès public.

**Navigation au sein du projet :**

 Il suffit d'exécuter successivement les cellules du notebook : main.ipynb


**Description des packages :**


*Importation de données*

- openpyxl permet d'ouvrir des fichiers Excel.
  
- zipfile permet d'extraire les fichiers zip qu'on a importé par requests.

- requests permet de récupérer des url (et en l'occurrence d'importer les données publiques).


*Manipulation de données*

- pandas permet de manipuler des dataframes.
  
- geopandas permet de manipuler des geodataframes.
  

*Visualisation de données*

- matplotlib.pyplot permet de faire des graphiques.

- seaborn permet de faire des graphiques différents, notamment des heatmap (pour les matrices de corrélation principalement dans notre cas)
  
- contextily récupère des cartes sur internet.

  
*Conversion de formats*

- json permet de convertir en json les données des shapefiles.

- shape (depuis shapely.geometry) permet de convertir les jsons en objets Shapely.

  
*Modalisation statistique*

- scipy est orienté initialement vers le calcul mathématique mais nous permet, après avoir construit nos régressions, de tester simplement les liens statistiques entre les variables. 

- statsmodels permet de calculer les VIF (avec variance_inflation_factor depuis statsmodels.stats.outliers_influence), de réaliser des tests d'hétéroscédasticité...

- sklearn est utile pour le Machine Learning ; dans notre cas, nous utilisons statsmodels pour les régressions mais StandardScaler (depuis sklearn.preprocessing) pour standardiser les variables explicatives. 


*Analyse spatiale*

- Moran (depuis edsa) permet de réaliser des tests de Moran (pour l'analyse de l'autocorrélation spatiale)

- Queen (depuis libpysal.weights) permet de créer des matrices de voisinage spatiales, et notamment d'analyser les clusters locaux (LISA) dans notre cas.
