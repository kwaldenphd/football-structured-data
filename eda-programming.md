# Lab #2 (Structured Data): Programming Workflows for Exploratory Data Analysis/Visualization

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Section Table of Contents

- [Overview](#overview)
- [Python](#python)
- [R](#r)
- [Discussion/Reflection Questions](#discussionreflection-questions)

# Overview 

In addition to the graphical-user-interface (GUI) based tools covered in the previous sections of the lab, we can also apply these methods using programmatic workflows, specifically Python & R.

## Python

We can use a programming language like Python to generate and customize many of the types of visualizations we created using a spreadsheet program or Tableau. Prof. Walden has built out a Jupyter notebook that goes into more detail about using Python for exploratory data analysis for the sample datasets presented in this lab.
- [Link to access Jupyter Notebook via Google Colab](https://drive.google.com/file/d/1MybxGo9ngdm20rzV1xAqAGYZwNsLINTM/view?usp=sharing)

Since we're dealing with single data files, running things on your personal computer should not cause any problems. But you can also make copies of the CoLab notebooks and connect to data files within Google Drive. 

To mount Google Drive files within CoLab:
- [Google Colab, "External Data: Local Files, Drive, Sheets, and Cloud Storage"](https://colab.research.google.com/notebooks/io.ipynb#scrollTo=XDg9OBaYqRMd)
- Mdkaish Ansari, "[How to Connect Google Colab with Google Drive](https://www.marktechpost.com/2019/06/07/how-to-connect-google-colab-with-google-drive/)" *Markettechpost* (7 June 2019)

The Jupyter notebook uses the following programs and Python libraries:
- `matplotlib`
- `pandas`
- `geopandas`
- `plotly`

The Jupyter notebook includes sample code for the following steps/tasks, using the roster, directory, and schedule datasets:
- Load data as Pandas `DataFrame`
- Merging directory and roster datasets
- Static visualization with `Pandas` and `Matplotlib`
- Static geospatial data visualization with `geopandas`, `shapely`, and `matplotib`
- Interactive visualization with `plotly`
- Interactive geospatial data visualization with `plotly`

# R

We can also use a scripting language like R/RStudio to generate and customize many of the types of visualizations we created using a spreadsheet program or Tableau. Prof. Walden has built out an RMarkdown file that goes into more detail about using R for exploratory data analysis for the sample datasets presented in this lab.

RMarkdown File:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.Rmd)
- [Google Drive](https://drive.google.com/file/d/1gvhci2x1IVsHOFCEwkeVvm_HSUPU0l2V/view?usp=sharing)
- [RStudio/Posit Cloud](https://rstudio.cloud/project/2977118)

RStudio Project:
- [GitHub, `.zip`](https://drive.google.com/file/d/1zex8zotq6TpLtzcDukl0NtH8oxaswBqR/view?usp=sharing)
- [RStudio Cloud](https://rstudio.cloud/project/2977118)

The RMarkdown file uses the following programs and packages:
- `tidyr`
- `dplyr`
- `magrittr`
- `ggplot2`
- `viridis`
- `htmltools`
- `geojsonio`
- `plotly`
- `leaflet`
- `sf`
- `sp`
- `tmap`
- `maps`

The RMarkdown notebook includes sample code for the following steps/tasks, using the roster, directory, and schedule datasets:
- Load data as `DataFrame`
- Merging directory and roster datasets using `dplyr` and `tidyr`
- Static visualization with `ggplot2`
- Static geospatial data visualization with `ggplot2`, `sf, `sp`, `tmap`, and `maps`
- Interactive visualization with `plotly`
- Interactive geospatial data visualization with `plotly` and `leaflet`

### Discussion/Reflection Questions

- How does working in a programming environment shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations
