# meteo.data-Tools
Outils de Visualisaiton-Extraction des données opendata de Météo-France en ligne sur meteo.data.gouv.fr

### Portail meteo.data - Carte des postes météorologiques de Météo-France (Métropole & outre-mer)
Une connexion internet est nécessaire pour accéder au fichier JSON et au fond de carte

Le fichier JSON de Météo-France contient les noms du poste et de la commune, et l'alitude<br>

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)

### Portail meteo.data - Téléchargement & affichage des "dernières" (latest) données MENSUELLES de Météo-France (Métropole & outre-mer)
Une connexion internet est nécessaire pour accéder aux archives des données à l'url ci-dessous

- Les "dernières" données (latest) correspondent aux fichiers mis à jour quotidiennement, et qui vont du mois de janvier de l'année précédente au mois en cours même partiel (pour les données mensuelles).
- Les fichiers sont téléchargés et décompressés automatiquement, pour plusieurs départements si besoin
- Le graphique chronologique est tracé pour le paramètre Précipitations RR des postes choisis par l'utilisateur
- Les données intégrales sont rassemblées dans un même fichier Excel avec le graphique (tous paramètres de la période "Latest" pour tous les postes des départements concernés).

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)<br>
Fichier CSV descriptif champs: https://www.data.gouv.fr/fr/datasets/r/6d4ac560-8f7c-477f-9a3f-3c33137fc04e

### Portail meteo.data - Téléchargement-affichage-Extraction des "dernières" données (latest) QUOTIDIENNES de Météo-France (RR-T-Vent)
Ce script ntraite uniquement le fichier "RR-T-vent" (Précipitations, Température, Vent) à l'exclusion du fichier "autres-parametres" contenant notamment l'ETP.<br>
Une connexion internet est nécessaire pour accéder aux archives des données à l'url ci-dessous.

- Les "dernières" données (latest) correspondent aux fichiers mis à jour quotidiennement, et qui vont du mois de janvier de l'année précédente au mois en cours même partiel.
- Les fichiers quotidiens sont téléchargés et décompressés automatiquement, pour plusieurs départements si besoin
- Les graphiques chronologiques QUOTIDIEN & MENSUEL sont tracés pour le paramètre Précipitations RR des postes choisis par l'utilisateur
- Un fichier excel rassemble:
    - Les données intégrales (tous paramètres de la période "Latest" pour tous les postes des départements concernés).
    - la comparaison des précipitations pour les postes et la période choisis, avec les graphiques quotidien & mensuel

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)<br>
Fichier CSV descriptif champs: https://www.data.gouv.fr/fr/datasets/r/6a8df7e9-45ff-445d-9260-6c65475dda86

### Portail meteo.data - Données climatiques quotidienne (SIM2 = SAFRAN-ISBA) - Extraction de série chronologique pour une maille (1x1 km)

- Télécharger auparavant les données depuis le portail ci-dessous (chaque décennie repésente 1.1 Go en archive et 5 Go décompressé)<br>
- Le scrit trace le graphique sur une décennie des paramètres choisis (par exemple 10 pour limiter l'occupation en mémoire vive), et sauvegarde les séries chronologiques dans un fichier Excel.<br>
Le graphique dynamique est également sauvegardé en Html

data: https://meteo.data.gouv.fr/<br>
