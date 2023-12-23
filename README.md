# meteo.data.gouv.fr - Tools
Outils de Visualisation-Extraction (& Téléchargement éventuellement) des données open-data de Météo-France en ligne sur [meteo.data.gouv.fr](https://meteo.data.gouv.fr/)

### Carte des postes météorologiques de Météo-France (Métropole & outre-mer)
Une connexion internet est nécessaire pour accéder au fichier JSON et au fond de carte

- La carte dynamique des postes est tracée à partir du fichier JSON de Météo-France (avec l'affichage des noms du poste et de la commune, ainsi que l'alitude)<br>
- La carte dynamique est enregistrée en Html, ainsi qu'en version statique png
- La liste est enregistrée au format excel
- NB: code adapté au format du fichier JSON en décembre 2023, qui n'était pas conforme au format geoJSON

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)<br>

<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/postes%20meteo-france%20-%20carte_2023-12-20.png" width="30%"></img>
<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/postes%20meteo-france%20-%20carte_2023-12-20_monde.png" width="30%"></img>

### Portail meteo.data.gouv.fr - Téléchargement-affichage-Extraction des "dernières" données (latest) MENSUELLES de Météo-France (Métropole & outre-mer)
Une connexion internet est nécessaire pour l'accès en ligne aux archives des données

Les "dernières" données (latest) correspondent aux fichiers mis à jour quotidiennement, et qui vont du mois de janvier de l'année précédente au mois en cours même partiel (pour les données mensuelles).
1) Téléchargement des fichiers et décompression automatique, pour plusieurs départements si besoin
2) Tracé du graphique chronologique pour le paramètre Précipitations RR des postes choisis par l'utilisateur
3) Sauvegarde des données intégrales et du graphique dans un fichier Excel (tous paramètres de la période "Latest" pour tous les postes des départements concernés).

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)<br>
Fichier CSV descriptif champs: https://www.data.gouv.fr/fr/datasets/r/6d4ac560-8f7c-477f-9a3f-3c33137fc04e

<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/meteo.data%20QUOT_latest-2022-2023_RR-T-Vent.png" width="45%"></img>
<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/meteo.data%20MENS_latest-2022-2023.png" width="45%"></img>

### Téléchargement-affichage-Extraction des "dernières" données (latest) QUOTIDIENNES de Météo-France (RR-T-Vent)
Ce script ntraite uniquement le fichier "RR-T-vent" (Précipitations, Température, Vent) à l'exclusion du fichier "autres-parametres" contenant notamment l'ETP.<br>
Une connexion internet est nécessaire pour accéder aux archives des données à l'url ci-dessous.

Les "dernières" données (latest) correspondent aux fichiers mis à jour quotidiennement, et qui vont du mois de janvier de l'année précédente au mois en cours même partiel.
1) Téléchargement des fichiers quotidiens et décompression automatique, pour plusieurs départements si besoin
2) Tracé du graphique chronologique QUOTIDIEN pour le paramètre Précipitations RR des postes choisis par l'utilisateur
3) Tracé du graphiqueu chronologiqueu MENSUEL
4) Sauvegarde d'un fichier excel rassemblant:
    - Les données intégrales (tous paramètres de la période "Latest" pour tous les postes des départements concernés).
    - la comparaison des précipitations pour les postes et la période choisis, avec les graphiques quotidien & mensuel

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)<br>
Fichier CSV descriptif champs: https://www.data.gouv.fr/fr/datasets/r/6a8df7e9-45ff-445d-9260-6c65475dda86

### Données climatiques quotidienne (SIM2 = SAFRAN-ISBA) - Extraction de série chronologique pour une maille (1x1 km)
Auparavant, télécharger les données depuis le portail ci-dessous (chaque décennie repésente 1.1 Go en archive et 5 Go décompressé)<br>
1) Lecture du fichier de la décennie voulue
2) Extraction du point voulu et tracé de la carte de situation
3) Tracé du graphique chronologique de la décennie pour les paramètres et le point de maille choisis (par exemple 10 paramètres pour limiter l'occupation en mémoire vive)
4) Sauvegarde des séries chronologiques avec le graphique dans un fichier Excel<br>
    Le graphique dynamique est également sauvegardé en Html

<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/SIM2_graph.png" width="45%"></img>
