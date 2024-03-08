# Introduction

This repository is for a term project for 270721 Optimization at Chiang Mai University. The problem is to find an optimum travel plan for cafe hopping in Chiang Mai using multi objective problem genetic algorithm (MOPGA).

# Files

1.   **original_data.csv** Original data from the data collection process. This contains the cafe's names, ratings, pluscodes, google map links, and assigned gene codes for the GA process.
2.   **Data_processing.ipynb** This notebook is used to convert the original data to include coordinates of different cafes from their pluscodes use Google Geocoding API. Along with extracting the distance matrix and duration matrix using the Google Distance Matrix API.
3.   **data.csv** Processed data that includes the location coordinates.
4.   **distance_matrix.csv** Extracted distance matrix.
5.   **duration_matrix.csv** Extracted duration matrix.
6.   **NSGA2.iypnb** Jupyter notebook for finding pareto front on 2 objectives optimization: the most number of cafes to go and best average rating.
7.   **Plotting pareto fronts.iypnb** This is used to plot pareto front from NSGA2.iypnb with varying number of genes together.
8.   **GA for shortest path.iypnb** Jupyter notebook for solving VRP problem based on the different solutions from the NSAGA2.iypnb
9.   **Path plot.iypnb** Jupyter notebook for plotting optimal traveling path for one of the solutions provided from the GA for shortest path.iypnb
10.   **output** This is where most of the solutions and plots are stored.

# Current workflow for usage
This reprository is just a proof of concept work; thus, we apologize if the platform is hard to implement and follow. Nevertheless, here is how to use or code either on the provided dataset or your own.

If use other datasets:
1. Follow the form in the example, data.csv. If can't get the latitude longtitude, follow the original_data.csv.
2. Run the Data_processing.ipynb. If the data.csv is available, load it directly and skip the pluscode_to_coordinates(pluscode) function, load the data.csv to df directly and get the distance/duration matrix. For the google distance matrix API, please refer to: https://developers.google.com/maps/documentation/distance-matrix/overview.
3. Follow the same procedures below.

For the current dataset provided:
1. Run the NSGA2.iypnb at a specific constraint, if use distance matrix make sure to properly load the distance matrix file and set is_duration = False, otherwise load the duration matrix to the distance_matrix variable and set is_duration = True. Note that the units are in metre and second.
2. There are 6 sets of version you need to run to properly get the whole pareto front, simply repeat the NSGA with set = 0, 1, ..., 5.
3. Run the Plotting pareto fronts.iypnb with for different pareto fronts for various cases, the current notebook should be plotting the one for max duration = 7200 seconds (in the code the variable is still named max_distance).
4. Run the GA for shortest path.iypnb for chosen objective function values from NSGA2. Note that one value can have various combination of cafes, hence why GA is performed to solve VRP for all of them and all paths are provided as options.
5. You can choose to export any preferred option to be visualize on the open street map later. Currently, the fastest/shortest trips are chosen for the presentation purpose.
6. run Path plot.iypnb to plot the optimum path on the open street map.
    

# Note
- This work is originally performed using a demo account for google cloud; thus, there are some restrictions to be considered including locations limit per request and access to departure time function.
