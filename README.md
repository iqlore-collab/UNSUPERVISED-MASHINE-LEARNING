# UNSUPERVISED-MASHINE-LEARNING
Spotify Playlist Clustering


This repository contains an unsupervised machine learning notebook for grouping songs into playlist-like clusters using Spotify audio features.

## Notebook

`spotify_playlist_clustering_github_clean_upgraded.ipynb`

## Project Goal

The goal is to build an interpretable K-Means clustering prototype that can support playlist discovery and music catalog exploration.

This is not a production recommendation engine. It is a compact unsupervised learning project focused on clustering, interpretation, and product-oriented analysis.

## What the Notebook Does

The notebook covers:

1. Loading Spotify-style song data
2. Cleaning metadata columns
3. Removing index-like columns such as `Unnamed: 0`
4. Selecting numeric audio features
5. Comparing scaling strategies
6. Estimating the number of clusters
7. Comparing clustering with and without `duration_ms`
8. Building K-Means playlist clusters
9. Inspecting cluster sizes
10. Visualizing clusters using PCA
11. Creating cluster profiles
12. Selecting representative songs near centroids
13. Generating heuristic playlist labels
14. Exporting cluster assignments, profiles, representatives, and labels

## Main Improvements

This upgraded version improves the original notebook by:

- excluding `Unnamed: 0` and other non-audio metadata from features
- testing whether `duration_ms` should be used
- using the no-duration feature set for the final playlist prototype
- adding PCA visualization
- adding small-cluster diagnostics
- adding heuristic playlist labels
- exporting more useful analysis files

## Methods Used

- K-Means clustering
- StandardScaler and other scaling comparisons
- Silhouette score
- Calinski-Harabasz score
- Davies-Bouldin score
- PCA visualization
- Centroid-based representative song selection

## Why `duration_ms` Is Tested Separately

Track duration can influence distance-based clustering. In playlist discovery, song length is often less important than audio style, mood, or energy.

The notebook compares both variants and uses the version without `duration_ms` for the final prototype.

## Limitations

- K-Means assumes roughly spherical clusters.
- Spotify audio features do not include lyrics, genre, popularity, or listening behavior.
- `k=50` is a business-facing choice, not necessarily the best statistical value.
- Playlist labels are heuristic and should be reviewed manually.
- The model is not personalized.

## Exported Files

The notebook exports:

- `spotify_playlist_clusters_k50.csv`
- `spotify_cluster_profiles.csv`
- `spotify_cluster_representatives.csv`
- `spotify_cluster_labels.csv`

## Libraries

- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

## Suggested Next Steps

Possible future improvements:

- compare K-Means with DBSCAN or Gaussian Mixture Models
- add genre or popularity features
- use user listening behavior
- build an interactive playlist explorer
- manually validate cluster names
