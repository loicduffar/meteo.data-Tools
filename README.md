# meteo.data-Tools
Outils de Visualisaiton-Extraction des données opendata de Météo-France en ligne sur meteo.data.gouv.fr

### Portail meteo.data - Carte des postes météorologiques de Météo-France (Métropole & outre-mer)
Une connexion internet est nécessaire pour accéder au fichier JSON et au fond de carte

Le fichier JSON de Météo-France contient les noms du poste et de la commune, et l'alitude<br>

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)

### Portail meteo.data - Téléchargement & affichage des "dernières" (latest) données MENSUELLES de Météo-France (Métropole & outre-mer)
Une connexion internet est nécessaire pour accéder aux archives des données à l'url ci-dessous

- Les "dernières" données (latest) correspondent aux fichiers mis à jour quotidiennement, et qui vont du mois de janvier de l'année précédente au mois en cours même partiel (pour les données mensuelles)
- Le script trace le graphique chronologique du paramètre Précipitations RR pour plusieurs postes choisis par l'utilisateur
- Les données intégrales des postes choisis (tous les paramètres de la période "Latest") sont sauvegardées dans un fichier Excel avec le graphique

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)<br>
Fichier CSV descriptif champs: https://www.data.gouv.fr/fr/datasets/r/6d4ac560-8f7c-477f-9a3f-3c33137fc04e

Utilisez mon autre script pour visualiser sous forme de carte la liste des postes météorologiques fournie par Météo-France sous forme de fichier JSON https://meteo.data.gouv.fr/https://www.data.gouv.fr/fr/datasets/r/1fe544d8-4615-4642-a307-5956a7d90922

### Portail meteo.data - Données climatiques quotidienne (SIM2 = SAFRAN-ISBA) - Extraction de série chronologique pour une maille (1x1 km)

- Les données sont à télécharger sur le portail ci-dessous (chaque décennie repésente 1.1 Go en archive et 5 Go décompressé)<br>
- Le scrit trace le graphique sur une décennie des paramètres choisis (par exemple 10 pour limiter l'occupation en mémoire vive), et sauvegarde les séries chronologiques dans un fichier Excel.<br>
Le graphique dynamique est également sauvegardé en Html

data: https://meteo.data.gouv.fr/<br>
