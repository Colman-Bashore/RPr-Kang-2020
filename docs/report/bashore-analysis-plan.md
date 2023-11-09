### Author:
Colman Bashore

### Planned modifications:
We will improve the translation from hospital catchments to hexagons representing accessibility. 
We will edit the overlap_calc function which currently does not consider catchment areas that don't
take up more than 50% of the area of a given hexagon in the service score of that hexagon.
We will change this such that we calculate an area weighted reaggregation of service scores and we don't 
remove catchment areas that don't meet the 50% threshold. 
Instead of using the service value from only one catchment area we will proportionately sum the service scores
from each of the overlapping catchment areas in a hexagon based upon what percentage of the hexagon's area they take up.

We will also improve the speed limit information used in the study. 
We will replace the network_setting function with a chunk of code that uses the osmnx.speed module to calculate speed limits 
for each road instead of calculating them based on listed speed limits. This will avoid the issue that most roads to not have listed speed limits and thus the speed can be calculated based on the road type such as highway or alley.


### Plan for visualizing results

To visualize the results of changing the hospital catchment to hexagon process we will run the calculate hospital catchment areas code chunk and plot our accessibility map to visually check if there are changes in the output accesibility. This will allow us to see how our change in the code changes the outcome.\
For speed limits, we rerun the re-check speed limit values code chunk after we have used osmnx.speed to see a dataframe that tells us the number of roads that have each speed limit and we should see significantly less roads that have a speed limit of 30mph. 