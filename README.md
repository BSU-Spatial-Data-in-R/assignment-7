# Assignment 7: Building spatial databases

It's time to put together the various vector, raster, and tabular code we've learned in order to build a dataframe that you can use for a subsequent statistical analysis. We'll be using the National Forest boundaries that we used in class (I've written a function for you to download and unzip this in the `/code/` folder), a dataset describing the cost of natural disasters from 1999-2020 (described in [this paper](https://www.nature.com/articles/s41597-023-01955-0) and available at `/assignment07/ics209-plus-wf_incidents_1999to2020.csv` folder, a land use dataset (`/assignment07/land_use_pnw.tif`), and the wildfire hazard dataset (`/assignment07/wildfire_hazard_agg.tif`). Your goal is to create a dataframe that includes the total cost of all disasters that have occurred within a National Forest Boundary along with several social and ecological variables that might help explain the difference in dollars expended to contain the hazard (typically fire). By the end of this assignment you should be able to:

* Join data by spatial location and by tabular ids
* Smooth rasters using the `focal` function
* Extract both quantitative and categorical raster data to points of interest.
* Combine all data into a single dataframe with the number of rows equal to the number of National Forests within a region and columns equal to the number of variables you include

## Instructions

1. After you've joined the assignment repository, you should have this file (named Readme.md) inside of a R project named assignment-7-xx where xx is your github username (or initials).

2. Once you've verified that you've correctly cloned the assignment repository, create a new Quarto document. Name this file assignment-7-xxx.qmd and give it a title (like M Williamson Assignment 7). Make sure that you select the html output option (Quarto can do a lot of cool things, but the html format is the least-likely to cause you additional headaches). We'll be using Quarto throughout the course so it's worth checking out the other tutorials in the getting started section.

3. Copy the questions below into your document and change the color of their text.

4. Save the changes and make your first commit!

5. Answer the questions making sure save and commit at least 3 more times (having 4 commits is part of the assignment).

6. Render the document to html (you should now have at least 3 files in the repository: Readme.md, assignment-7-xx.qmd, and assignment-7-xx.html). Commit these changes and push them to the repository on GitHub. You should see the files there when you go to github.com.


## The Assignment

1. You'll need to download the FS boundary shapefiles then load in all of the different spatial and tabular datasets.
2. Validate your geometries and make sure all of your data is in the same CRS.
3. Smooth the wildfire hazard and land use datasets using a 5x5 moving window; use the mean for the continuous dataset and the mode for the categorical dataset.
4. Estimate the total cost of the incidents within each forest (`PROJECTED_FINAL_IM_COST` contains this value for each incident).
5. Next join 3 attributes of your choosing from the CEJST and the extracted fire and land cover values to your dataframe.
6. Make a set of maps that shows the Forest-level values for all of your selected variables.

