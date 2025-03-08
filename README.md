# meteo.data.gouv.fr - Tools
Notebooks python de Visualisation-Extraction (& Téléchargement éventuellement) des données de Météo-France, ouvertes en open-data en décembre 2023, en ligne sur [meteo.data.gouv.fr](https://meteo.data.gouv.fr/)

### Portail meteo.data.gouv.fr - Carte des postes météorologiques de Météo-France (Métropole & outre-mer)
<p style="color:red;">CE code fonctionnel en janvier 2024 fonctionne maintenant en mode en partie dégradée, faute de quoi l'exécution est sans fin. L'instruction de sauvegarde du fichier PNG par fig.write_image(file_png) est pour l'instant désactivée.</p>

Une connexion internet est nécessaire pour accéder aux fichiers TEXTE Météo-France et au fond de carte OpenStreetMap<br>
NB: les fichiers TEXTE couvrent tous les postes OUVERTS et FERMES, ainsi que les postes dit "complémentaires" qui correspondent au Type 5 (expertise absente ou non garantie)<br>
Pour connaitre le détail des postes, et notamment l'historique pour chaque paramètre, allez sur https://publitheque.meteo.fr/ où les données sont également gratuites et téléchargeables

- La carte dynamique des postes est tracée à partir du fichier TEXTE de Météo-France. Elle différencie les postes professionnels et complémentaires, et permet de sélectionner les postes fermés ou ouverts.<br>
  Le survol à la souris permet d'afficher le noms du poste et de la commune, l'altitude, les coordonnées en lat/lon & Lambert, et surtout les dates d'ouverture et de fermeture<br>
- La carte dynamique est enregistrée en Html (et théoriquement la version png si l'export fig.write_image() marche)
- La liste est enregistrée au format excel, avec en plus l'url qui permet d'afficher le PDF Météo-France des informations détaillées sur la station (même si le document n'existe pas parfois)
- NB: code adapté au nouveau format TEXTE beaucoup plus complet et stable que l'ancien fichier JSON abandonné par Météo-France après plus d'une année de problèmes pour les utilisateurs.

data : https://meteo.data.gouv.fr/<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)

<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/postes%20meteo-france%20-%20carte%20France_2025-03-08.png" width="30%"></img>
<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/postes%20meteo-france%20-%20carte%20Monde_2025-03-08.png" width="30%"></img>

### Portail meteo.data.gouv.fr - Téléchargement-affichage-Extraction des données MENSUELLES de Météo-France (Métropole & outre-mer)
Une connexion internet est nécessaire pour le téléchargement automatique des archives de données.
1) Téléchargement des fichiers et décompression automatique, pour différents postes, dans plusieurs départements si besoin
2) Tracé du graphique chronologique pour le paramètre Précipitations RR des postes choisis par l'utilisateur
3) Sauvegarde des données intégrales et du graphique dans un fichier Excel (tous paramètres pour tous les postes des départements concernés).

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)<br>
Fichier CSV descriptif champs: https://www.data.gouv.fr/fr/datasets/r/6d4ac560-8f7c-477f-9a3f-3c33137fc04e
- NB: code adapté au format du fichier JSON en décembre 2023 (ATTENTION le fichier JSON Météo-France est variable entre 2 formats, ce qui oblige à supprimer parfois ".T" à la ligne df = pd.DataFrame(data_json['features']).T)
  
Utilisez mon autre script pour visualiser sous forme de carte la liste des postes météorologiques fournie par Météo-France sous forme de fichier JSON https://meteo.data.gouv.fr/https://www.data.gouv.fr/fr/datasets/r/1fe544d8-4615-4642-a307-5956a7d90922

NB:
- Les historiques MENSUELS sont réparties en 3 fichiers pour chaque département: xxxx-1949, previous-1950-2022, latest-2023-2024 (LATEST indique le dernier fichier mis à jour quotidiennement depuis janvier de l'année précédente jusqu'au mois en cours, XXXX représent l'année de début de la période la plus ancienne variable selon le département).
- Les données MENSUELLES ne sont pas simplement équivalentes à des données QUOTIDIENNE agrégées (les paramètres ne sont pas strictement les mêmes. Par exemple, il existe des des NOMBRES DE JOURS DE PLUIE/GELEE/CHALEUR/etc.., ainsi que des précipitations MENSUELLES ESTIMEES 'RR_ME' plus anciennes que les mesures)

<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/meteo.data%20HOR_latest-2022-2023.png" width="30%"></img>
<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/meteo.data%20QUOT_latest-2022-2023_RR-T-Vent.png" width="30%"></img>
<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/meteo.data%20MENS_latest-2022-2023.png" width="30%"></img>

### Portail meteo.data.gouv.fr - Téléchargement-affichage-Extraction des données QUOTIDIENNES LATEST de Météo-France (RR-T-Vent)
Ce script ntraite uniquement le fichier "RR-T-vent" (Paramètres liés aux Précipitations, Température & Vent) à l'exclusion du fichier "autres-parametres" contenant notamment l'ETP.<br>
Une connexion internet est nécessaire pour accéder aux archives des données à l'url ci-dessous.

1) Téléchargement des fichiers quotidiens et décompression automatique, pour plusieurs départements si besoin
2) Tracé du graphique chronologique QUOTIDIEN pour le paramètre Précipitations RR des postes choisis par l'utilisateur
3) Tracé du graphique chronologique de l'agrégation MENSUELLE
4) Sauvegarde d'un fichier excel rassemblant:
    - Les données intégrales QUOTIDIENNES et agrégées MENSUELLEMENT (tous paramètres de la période "Latest" pour tous les postes des départements concernés).
    - la comparaison des paramètres pour les postes et la période choisis, ainsi que pour les précipitations les graphiques quotidien & mensuel

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)<br>
Fichier CSV descriptif champs: https://www.data.gouv.fr/fr/datasets/r/6a8df7e9-45ff-445d-9260-6c65475dda86
- NB: code adapté au format du fichier JSON en décembre 2023 (ATTENTION le fichier JSON Météo-France est variable entre 2 formats, ce qui oblige à supprimer parfois ".T" à la ligne df = pd.DataFrame(data_json['features']).T)
  
Utilisez mon autre script pour visualiser sous forme de carte la liste des postes météorologiques fournie par Météo-France sous forme de fichier JSON https://meteo.data.gouv.fr/https://www.data.gouv.fr/fr/datasets/r/1fe544d8-4615-4642-a307-5956a7d90922

NB: 
- Les données LATEST correspondent aux DERNIERS FICHIERS mis à jour quotidiennement, et qui vont du mois de janvier de l'année précédente au mois en cours même partiel.
- Les données QUOTDIENNES agrégées mensuellement ne sont pas simplement équivalentes aux donnée MENSUELLES. Les paramètres ne sont pas strictement les mêmes. Certains paramètres quotidiens n'existent pas en mensuel (par exemple concernant le vent), mais les paramètres mensuels sont globalement plus nombreux à cause des paramètres "calculés" (par exemple des NOMBRES DE JOURS DE PLUIE/GELEE/CHALEUR/etc.., ainsi que des précipitations MENSUELLES ESTIMEES 'RR_ME' plus anciennes que les mesures)

### Portail meteo.data.gouv.fr - Téléchargement-affichage-Extraction des données HORAIRES LATEST de Météo-France (RR-T-Vent)
Une connexion internet est nécessaire pour le téléchargement automatique des archives de données.

1) Téléchargement des fichiers HORAIRES et décompression automatique, pour différents postes (si besoin dans plusieurs départements mais au prix d'une longue durée de lecture)
2) Tracé du graphique chronologique HORAIRE pour le paramètre Précipitations RR des postes choisis par l'utilisateur
3) Tracé du graphique chronologique de l'agrégation QUOTIDIENNE
4) Sauvegarde d'un fichier excel rassemblant:
    - la comparaison des paramètres QUOTIDIENS & MENSUELS pour les postes et la période choisis, ainsi que les graphiques pour les précipitations uniquement
    - NB: Les données intégrales HORAIRES ne sont pas sauvegardées pour cause de poids excessif (tous paramètres de la période "Latest" pour tous les postes des départements concernés).
- NB: code adapté au format du fichier JSON en décembre 2023 (ATTENTION le fichier JSON Météo-France est variable entre 2 formats, ce qui oblige à supprimer parfois ".T" à la ligne df = pd.DataFrame(data_json['features']).T)

data : https://meteo.data.gouv.fr/ (6 min, horaire, quotidien, mensuel)<br>
Fiche PDF des postes : https://www.data.gouv.fr/fr/datasets/r/bee4b0c7-260a-40fe-b463-ed5631d6dc39 (paramètres et périodes de mesure)<br>
Fichier CSV descriptif champs: https://www.data.gouv.fr/fr/datasets/r/5d0f9af9-149b-463a-9472-445dafb698d9

Utilisez mon autre script pour visualiser la carte des postes météorologiques dont la liste est fournie par Météo-France sous forme de fichier JSON https://meteo.data.gouv.fr/https://www.data.gouv.fr/fr/datasets/r/1fe544d8-4615-4642-a307-5956a7d90922

NB: 
- Les données LATEST correspondent aux DERNIERS FICHIERS mis à jour quotidiennement, et qui vont du mois de janvier de l'année précédente à la veille du jour en cours même partielle.
- Les données HORAIRES agrégées quotidiennement ne sont pas simplement équivalentes aux donnée QUOTIDIENNES
    - l'agréation quotiodienne est effectuée depuis 0:00 et non depuis 6:00 (et Météo-France affecte le résultat au jour précédent)
    - les paramètres ne sont pas strictement les mêmes. Certains paramètres horaires n'existent pas en quotidiens (ex. DRR1 durée des précipitations (en mn/heure)), et inversement
- NB: code adapté au format du fichier JSON en décembre 2023 (ATTENTION le fichier JSON Météo-France est variable entre 2 formats, ce qui oblige à supprimer parfois ".T" à la ligne df = pd.DataFrame(data_json['features']).T)
  
### Données climatiques quotidienne (SIM2 = SAFRAN-ISBA) - Extraction de série chronologique pour une maille (1x1 km)
Auparavant, télécharger les données depuis le portail ci-dessous (chaque décennie repésente 1.1 Go en archive et 5 Go décompressé)<br>
1) Lecture du fichier de la décennie voulue
2) Extraction du point voulu et tracé de la carte de situation
3) Tracé du graphique chronologique de la décennie pour les paramètres et le point de maille choisis (par exemple 10 paramètres pour limiter l'occupation en mémoire vive)
4) Sauvegarde des séries chronologiques avec le graphique dans un fichier Excel<br>
    Le graphique dynamique est également sauvegardé en Html
- NB: code adapté au format du fichier JSON en décembre 2023 (ATTENTION le fichier JSON Météo-France est variable entre 2 formats, ce qui oblige à supprimer parfois ".T" à la ligne df = pd.DataFrame(data_json['features']).T)

<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/SIM2_graph.png" width="45%"></img>
<img src="https://github.com/loicduffar/meteo.data-Tools/blob/main/out/SIM2_map%20.png" width="45%"></img>
