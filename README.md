# Introduction

This repository is for a term project for 270721 Optimization at Chiang Mai University. The problem is to find an optimum travel plan for cafe hopping in Chiang Mai using multi objective problem genetic algorithm (MOPGA).

# Files

1.   **original_data.csv** Original data from the data collection process. This contains the cafe's names, ratings, pluscodes, google map links, and assigned gene codes for the GA process.
2.   **Data_processing.ipynb** This notebook is used to convert the original data to include coordinates of different cafes from their pluscodes use Google Geocoding API. Along with extracting the distance matrix and duration matrix using the Google Distance Matrix API.
3.   **data.csv** Processed data that includes the location coordinates.
4.   **distance_matrix.csv** Extracted distance matrix.
5.   **duration_matrix.csv** Extracted duration matrix.

# Note
This work is originally performed using a demo account for google cloud; thus, there are some restrictions to be considered including locations limit per request and access to departure time function.
