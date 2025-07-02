### Titre:
Identification des zones habitées non éclairées par croisement **GHSL-VIIRS**: cas de la commune de **Bokidiawé**
### Objectif
Identifier les zones habitées mais non éclairées dans la commune de **Bokidiawé** afin d'évaluer la vulnérabilité à l'obscurité nocturne et aider à la planification des infrastructures.
### Données
1. **VIIRS (Visible Infrared Imaging Radiometer Suite)**
   - Dataset: `NOAA/VIIRS/DNB/MONTHLY_V1/VCMCFG`. Il s'agit d'une image composite de la radiance moyenne mensuelle générée à l'aide des données nocturne de la bande Day/Night(DNB).
   - Résolution: 450m
   - Bande de fréquence: `avg_rad`, valeur moyenne de la radiance DNB
3. **GHSL (Global Humain Settlement Layer)**
   - Dataset `JRC/GHSL/P2023A/GHS_POP/2020`. Cette ensemble de données représente la distribution spatiale de la population résidentielle, exprimée en nombre absolue d'habitants de la cellule.
   - Résolution: 100m
   - Bande: `population_count`, représente le nombre d'habitants par pixel.
5. **Limites administratives**: Polygons délimitant les communes du Sénégal.
### Méthodologie
- **filtrage spatial**: Découpage de VIIRS et GHS_POP sur la commune de *Bokidiawé*.
- **Reprojection**: Aligner les images sur le même système de coordonnées(CRS), la même résolution et le même point d'origine.
- **Seuil de densité**: Densité officielle de la commune de Bokidiawé en 124.4 hab/km2 convertie en hab/pixel (à 100m).
- **Seuil de lumière VIIRS**: Intensité lumineuse, seuil définie par test visuel.
- **Croisement**: `habité et non éclairé` donne zones vulnérables à l'obscurité.
### Résultat attendu
- Carte des **zones habitées mais non éclairées**
- Statistiques:
  - % de la superficie des zones vulnérables (en ha)
  - Nombre estimé d'habitants concernés
