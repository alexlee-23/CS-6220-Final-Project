# CS-6220-Final-Project
# MLB Lineup Optimization & Matchup Mining

This project explores how different MLB hitter and pitcher archetypes interact by combining **clustering**, **association rule mining**, and matchup analysis. Our overarching goal is to discover interpretable patterns in historical data and eventually use those insights to construct optimal batting lineups against a known opposing pitcher.

---

## Project Structure Overview

### Pitching Clusters

The final pitching archetype model used in the project is located at:

```./Statcast_Pitchers/pitch_cluster_simple.ipynb```

Other pitching cluster notebooks we explored (but did not use in the final workflow):

```./Retrosheet_Pitchers/pitching_clusters.ipynb```

```./Statcast_Pitchers/pitcher_cluster_by_pitchtype.ipynb```

The retrosheet notebook was the data we first explored with but realized the data was not complex enough.
The other statcast notebook performs a more complex two-level clustering approach (first clustering by pitch-type characteristics, then clustering again to generate pitcher archetypes).

---

### Batting Clusters

The final batter archetypes are generated in:

```./Batting/BatterClusters.ipynb```

This notebook contains the clustering process for hitter discipline, pitch-type effectiveness, and contact tendencies.

---

### Association Rule Mining

The AssociationMining folder contains the complete association rule pipeline and outputs for each season.

#### Downloading Play by Play Data
Use the following notebook to download pitch-level Statcast data:

```./AssociationMining/statcast_data_download.ipynb```

Since each year of pitch-level data is extremely large, you may instead download the preprocessed files from the OneDrive link shared in the projct report.

#### Mining for rules
Moving on to the association rule mining (assuming you have all the data required).

For example, the 2019 workflow:

```./AssociationMining/2019_association_rules.ipynb```

Each notebook performs:
- Preprocessing plate appearances into transactions
- Replacing player IDs with their batter/pitcher archetypes
- Mining rules using FP-Growth or Apriori
- Filtering to keep only outcome-related rules
- Exporting per-season CSVs and summaries

---

## Project Summary

We cluster MLB hitters and pitchers into meaningful archetypes and then apply association rule mining to uncover matchup-driven outcomes (e.g., which batter types succeed or struggle against certain pitcher types). These patterns allow us to extract interpretable baseball insights and form the basis for a future optimization model.

The long-term goal is to use these insights to construct an analytically optimized batting lineup that maximizes expected offensive performance against a known opposing starting pitcher.
