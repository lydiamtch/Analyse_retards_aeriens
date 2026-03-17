# Analyse des retards aériens - nycflights13



## Description du projet



Ce projet analyse les retards des vols au départ des trois principaux aéroports de New York (JFK, LGA, EWR) en 2013, à partir de la base de données `nycflights13`.



**Objectif :** Identifier quand, où et pourquoi les retards se produisent, et analyser les différences entre compagnies, mois et aéroports.

Remarque : Ce projet met particulièrement l'accent sur l'Hypothèse 3 : la relation entre les retards au départ et les retards à l'arrivée, avec une analyse statistique approfondie (corrélation de Pearson = 0,92)


##  Source des données



La base de données nycflights13 contient l'ensemble des vols au départ des trois principaux aéroports de New York (JFK, LGA et EWR) durant l'année 2013. Chaque ligne correspond à un vol individuel.



**Colonnes principales :**

- `year` : Année (2013)

- `month` : Mois du vol

- `day` : Jour du vol

- `dep\_time` : Heure réelle de départ

- `sched\_dep\_time` : Heure prévue de départ

- `dep\_delay` : Retard au départ (en minutes)

- `arr\_time` : Heure réelle d'arrivée

- `arr\_delay` : Retard à l'arrivée (en minutes)

- `carrier` : Code de la compagnie aérienne

- `origin` : Aéroport de départ (JFK, LGA, EWR)

- `dest` : Aéroport de destination

- `air\_time` : Durée du vol (minutes)

- `distance` : Distance parcourue (miles)



##  Les 4 hypothèses analysées



### Hypothèse 1 : Les retards sont plus fréquents pendant l'été et en fin de journée

- Histogramme du nombre de vols en retard par mois

- Boxplot des retards (arr\_delay) par mois

- Courbe de tendance des retards moyens par heure de départ

- Heatmap mois × heure du retard moyen



### Hypothèse 2 : Certains aéroports new-yorkais sont plus touchés par les retards

- Bar chart du retard moyen par aéroport d'origine

- Boxplot des retards à l'arrivée selon l'aéroport

- Violin plot des retards au départ selon l'aéroport

- Heatmap origine × destination du nombre moyen de retards



### Hypothèse 3 : Les retards au départ entraînent des retards à l'arrivée \*\*(mon analyse principale)\*\*

- Nuage de points (dep\_delay vs arr\_delay) avec ligne de régression

- Courbe moyenne du retard à l'arrivée en fonction du retard au départ

- Jointplot de densité entre départ et arrivée

- Histogramme du taux de rattrapage (arr\_delay - dep\_delay)



### Hypothèse 4 : Les compagnies n'ont pas la même performance de ponctualité

- Bar chart du retard moyen par compagnie (carrier)

- Boxplot de la distribution des retards par compagnie

- Bar chart du nombre de vols annulés par compagnie

- Heatmap de corrélation entre distance, air\_time, dep\_delay, arr\_delay



##  Résultats clés obtenus



- **Corrélation retard départ → arrivée :** r = 0,92

- **R² :** 0,84

- **74,1%** des vols partis en retard arrivent en retard

- **Seuil critique :** 20 minutes de retard au départ



##  Technologies utilisées



- **Python** : Pandas, NumPy

- **Visualisation** : Matplotlib, Seaborn, GeoPandas

- **Statistiques** : SciPy

- **Outils** : Jupyter Notebook, GitGitHub



## Installation et démarrage

### Prérequis
- Python 3.x
- Jupyter Notebook (optionnel)

### Étapes d'installation

1. **Cloner le repository**
```bash
git clone https://github.com/lydiamtch/analyse-retards-aeriens.git
cd analyse-retards-aeriens

# Sur Mac/Linux
python -m venv .venv
source .venv/bin/activate

# Sur Windows
python -m venv .venv
.venv\Scripts\activate

pip install -r requirements.txt

# Lance Jupyter et ouvre le notebook
jupyter notebook notebooks/analyse_retards.ipynb

# Exécute directement le script Python
python scripts/analyse_retards.py
