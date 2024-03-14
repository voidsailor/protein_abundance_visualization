# Proteomic characterization of low numbers of human and murine neutrophils freshly isolated from sites of sterile inflammation

This repository contains code for the manuscript named above.

## 1) Correlation Plot

[R code](https://github.com/voidsailor/protein_abundance_visualization/correlation_plot_human_1000.R) for the correlation plots.

## 2) Interactive visualization

An [interactive visualization](https://github.com/voidsailor/protein_abundance_visualization/human_mouse_105_copy_number_plot.html) of the copy number abundances for mouse and human neutrophils were created using Python 3.9, pandas and bokeh for improved exploration of the abundance data. You can download and open the html file containing the visualization dashboard in any modern webbrowser.

### 2.1) Visualization dashboard manual

The visualization dashboard contains a searchable data table with [original data](https://github.com/voidsailor/protein_abundance_visualization/copy_number_distribution_human_mouse_105.xlsx) from the publication and an interactive plot of protein abundance over protein rank for human and mouse neutrophils.

#### Searching

To filter the data table for entries of interest type a search term into the search field (e.g., "CXCR2" to filter for C-X-C chemokine receptor type 2) and hit the ENTER key. The search uses strict string matching, so please consider that it does not tolerate typos. "Unfilter" the data table by deleting your search string and hitting ENTER.

#### Total number of proteins, filtered proteins, selected proteins

Displayed below the search field are the total number of proteins in the dataset, the number of filtered proteins currently displayed in the table (depends whether the data were filtered by a search, e.g., 2 for "CXCR2"), and the number of selected data points.

#### Interactive data table

Below these three metrics is the data table. Select datapoints by clicking on table rows. You can multi-select specific entries by holding CTRL and clicking individual entries, or multi-select a range of entries by holding SHIFT and clicking the first and last entry in that range (much like multi-selecting in Excel). Deselect by clicking on a selected entry. Selected entries are highlighted in the plot on the right side.

#### Interactive plot

You can select datapoints in the interactive plot by directly clicking into the plot (multi-select using SHIFT and clicking is also possible). On the right of the plot you can find a tool column that provides different interaction modes. Active tools are highlighted by a blue bar. The PAN tool allows to pan the figure, BOX SELECT allows to select multiple datapoints by dragging and dropping a selection box, WHEEL ZOOM activates zooming with the mouse wheel, RESET resets the figure into it's initial state, SAVE downloads the figure as .png file, and HOVER displays the information of a datapoint when hovering over a datapoint.

### 2.2) Running the code to generate the visualization dashboard

#### Input data

You can generate the interactive visualization dashboard for your own protein abundance data. Take a look at the [original data table](https://github.com/voidsailor/protein_abundance_visualization/copy_number_distribution_human_mouse_105.xlsx) for an example data set.

- provide the data in .xlsx spreadsheet format
- data for individual species, groups, or samples should be on separate sheets (e.g., human data on sheet one, mouse data on sheet two)
- each sheet should contain a table with features in columns and proteins in rows
  - column names are located in the first row
  - the columns "Rank" and "Copy number" are mandatory, other columns are optional (you could include as many features as you like)
  - column names must be identical across all sheets

#### Executing code

The code is provided as jupyter notebook file (protein_profile_vis.ipynb, [jupyter website](https://jupyter.org/)).

You can run this notebook in [Google Colab](https://colab.google/) without installing anything locally. Check out this [Guide](https://saturncloud.io/blog/how-can-i-run-notebooks-of-a-github-project-in-google-colab/) on how to open a jupyter notebook from GitHub.

You can also run it on your local machine using CONDA. We recommend using [ANACONDA navigator](https://docs.anaconda.com/free/navigator/index.html) for setup. Before running this script, make sure you installed and activated the provided CONDA environment (protein_profiles_env.yaml).

The first parts of the jupyter notebook set up any required python libraries and functions. Execute everything before section 4 "Read data and create the visualization". Below that section is a code cell where you specify the path to your input spreadsheet and the sheets to read ("read_data" function). The script also provides options to set a color palette for your data points, a plot title, etc. Please read the code documentation in the notebook for more information.
