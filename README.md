### Titre:
Identification des zones habitées non éclairées par croisement **GHSL-VIIRS**: cas de la commune de **Bokidiawé**
### Contexte et objectif du projet
L'accès à l'éclairage nocturne constitue un indicateur essentiel du développement et de la qualité de vie, en particulier dans les zones rurales. Dans la commune de Bokidiawé, une partie de la population vit probablement sans lumière artificielle, ce qui peut accroitre la vulnérabilité en matière de sécurité, d'éducation et d'accès aux services.

Ce projet a pour objectif d'identifier et de cartographier les zones **habitées mais non éclairées** à l'aide de données satellitaires. En croisant les données de population (`GHSL`), de lumière nocturne(`VIIRS`) et les limites administratives locales, il vise à :
- quantifier les **surfaces et population concernées**;
- localiser les **poches de vulnérabilité énrgétique**;
- fournir des **outils d'aide à la décision pour les acteurs de développement territorial**.
### Données
1. **VIIRS (Visible Infrared Imaging Radiometer Suite)**
   - Dataset: `NOAA/VIIRS/DNB/MONTHLY_V1/VCMCFG`. Il s'agit d'une image composite de la radiance moyenne mensuelle générée à l'aide des données nocturne de la bande Day/Night(DNB).
   - Résolution: 450m
   - Bande de fréquence: `avg_rad`, valeur moyenne de la radiance DNB
3. **GHSL (Global Human Settlement Layer)**
   - Dataset `JRC/GHSL/P2023A/GHS_POP`. Cette ensemble de données représente la distribution spatiale de la population résidentielle, exprimée en nombre absolue d'habitants de la cellule.
   - Résolution: 100m
   - Bande: `population_count`, représente le nombre d'habitants par pixel.
5. **Limites administratives**: Polygones délimitant les communes du Sénégal.

### Plateformes et Bibliothèques
- **Google Earth Engine(GEE)**: Plateforme cloud de traitement d'images satellites, utilisés pour les requêtes, les calculs spatiaux et l'extraction des données.
- **Python**: Langage principal utilisé pour interagir avec GEE via l'API Python.
- **Folium**: Bibliothèque de visualisation cartographique interactive en Python.
- **Jupyter Notebook**: Environnement interactif de développement, idéal pour organiser les scripts, afficher les cartes, tester des extraits de code et documenter les étapes du projet.
### Méthodologie
- **filtrage spatial**: Découpage de VIIRS et GHS_POP sur la commune de *Bokidiawé*.
- **Reprojection**: Aligner les images sur le même système de coordonnées(CRS), la même résolution et le même point d'origine.
- **Seuil de densité**: Densité officielle de la commune de Bokidiawé (124.4 hab/km2) convertie en hab/pixel (à 100m).
- **Seuil de lumière VIIRS**: Intensité lumineuse, seuil définie par test visuel.
- **Croisement**: `habité et non éclairé` donne zones vulnérables à l'obscurité.
### Résultat attendu
- Carte des **zones habitées mais non éclairées**
- Statistiques:
  - % de la superficie des zones vulnérables (en ha)
  - Nombre estimé d'habitants concernés

➡Tous les détails sont disponibles dans le notebook `.ipynb` et les images dans le dossier `docs`
### Contributions
Toutes les suggestions, retours, ou contributions sont les bienvenus afin d'améliorer et enrichir ce projet.
### Contact
Email: sidiniang20@gmail.com
