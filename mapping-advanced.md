# Lab #2 (Structured Data): Mapping Next Steps

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Table of Contents

- [Overview](#overview)
- [Python](#python)
- [R](#r)
- [Other Mapping Tools/Resources](#other-mapping-toolsresources)
  * [ArcGIS StoryMaps and Web App Builder](#arcgis-storymaps-and-web-app-builder)
  * [ArcMap](#arcmap)
  * [QGIS](#qgis)
  * [On-Campus Resources](#on-campus-resources)

# Overview

In addition to the web-based graphical user interface (GUI) tools we've explored, there are also programmatic workflows and more advanced desktop software to support working with geospatial data.

## Python

Prof. Walden has built out a Jupyter notebook that goes into more detail about using Python for exploratory data analysis for the sample datasets presented in this lab. That notebook also includes sample code for static and interactive mapping in Python.
- [Link to access Jupyter Notebook via Google Colab](https://drive.google.com/file/d/1MybxGo9ngdm20rzV1xAqAGYZwNsLINTM/view?usp=sharing)

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

### Python Discussion/Reflection Questions

- How does with mapping in Python shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate using Python?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

# R

Prof. Walden has also built out an RMarkdown file that goes into more detail about using RStudio for exploratory data analysis for the sample datasets presented in this lab. That RMarkdown file also includes sample code for static and interactive mapping in RStudio.

RMarkdown File:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.Rmd)
- [Google Drive](https://drive.google.com/file/d/1gvhci2x1IVsHOFCEwkeVvm_HSUPU0l2V/view?usp=sharing)
- [RStudio Cloud](https://rstudio.cloud/project/2977118)

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
- Static geospatial data visualization with `ggplot2`, `sf`, `sp`, `tmap`, and `maps`
- Interactive visualization with `plotly`
- Interactive geospatial data visualization with `plotly` and `leaflet`

## R Discussion/Reflection Questions

- How does with mapping in RStudio shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate using RStudio?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

## ArcGIS StoryMaps and Web App Builder

But there are a lot of additional things you can do with ArcGIS Online, especially around bringing interactive maps in conversation with text/media/etc (StoryMaps), or creating interactive dashboards similar to Carto's functionality (ArcGIS Web App Builder).

NOTE: Notre Dame provides subscription access to ArcGIS Online. Email Prof. Walden for next steps on being added to the ND enterprise account.

[More info on StoryMaps](https://www.esri.com/en-us/arcgis/products/arcgis-storymaps/stories)

A few examples of things folks are doing with StoryMaps:
- [Mapping LGBTQ+ St. Louis (Washington University St. Louis)](https://storymaps.arcgis.com/stories/9675a82d3d564c80b950361e709dff5e)
- [Collection of StoryMaps from Library of Congress, Smithsonian, etc.](https://storymaps-classic.arcgis.com/en/gallery/#s=0&md=storymaps-industry:libraries-museums-institutions)
- [Three Empires of Islam at the Metropolitan Museum of Art](https://storymaps.arcgis.com/stories/fa22b665c7894790b1b0441d0593289c)
- [Bombing Missions of the Vietnam War](https://storymaps.arcgis.com/stories/2eae918ca40a4bd7a55390bba4735cdb)

A WebApp Builder example:
- [Mapping Absence in Shakespeare](https://arcg.is/a1Pnq)
  * [Project website](https://absentshakespeare.sites.grinnell.edu/)
- [Mapping Islamophobia](https://mappingislamophobia.org/)
  * [Reporting Islamophobia](https://grinnell.maps.arcgis.com/apps/instant/interactivelegend/index.html?appid=11caab7d852b4ec88defce3f3c100e42)
  * [Countering Islamophobia](https://grinnell.maps.arcgis.com/apps/instant/interactivelegend/index.html?appid=f2215ec572a84047923fbb7f41665b19)
  
Tutorials:
- [ArcGIS StoryMaps](https://github.com/kwaldenphd/ArcGIS-StoryMaps)
- [ArcGIS Web App Builder](https://github.com/kwaldenphd/ArcGIS-WebAppBuilder)

## ArcMap and QGIS

There are also desktop software applications that can be used for spatial data analysis and visualization.

NOTE: This is not a GIS (geographical information systems) class. Prof. Walden can connect folks with resources, but advanced GIS work is beyond the scope of the class.

### ArcMap

ArcGIS is an industry-standard tool developed by geographers in the 1970s. As digital historians have pursued more complex and large-scale spatial analysis projects, ArcGIS is a tool frequently used to visualize and analyze spatial data. The ArcGIS Online platform (not covered in this tutorial but featured in many digital mapping projects) allows data analyzed and visualized in ArcGIS to be interactive and publicly-accessible. 
- NOTE: The ArcGIS desktop application is only available for PC users.

Tutorials:
- [Getting Started with ArcMap](https://github.com/kwaldenphd/ArcMap-introduction)

Current ND students have access to the ArcMap title through OIT.
- [Virtual Computer Lab](http://go.nd.edu/vcl)
- [Contact OIT about getting ArcMap on your personal computer](https://oit.nd.edu/services/software/software-downloads/arcgis-desktop/)

### QGIS

QGIS is a powerful open-source alternative to ArcMap that works across operating systems.

Documentation:
- [More information abou tthe QGIS project](https://qgis.org/en/site/index.html)
- [Download QGIS](https://qgis.org/en/site/forusers/download.html)

Tutorials:
- [QGIS Documentation](https://docs.qgis.org/3.16/en/docs/training_manual/index.html)
- Jim Clifford, Josh MacFadyen, and Daniel Macfarlane, "Installing QGIS 2.0 and Adding Layers," The Programming Historian 2 (2013), https://doi.org/10.46430/phen0031.
- Justin Colson, "Geocoding Historical Data using QGIS," The Programming Historian 6 (2017), https://doi.org/10.46430/phen0066.

## On-Campus Resources

We also have a deep bench of expertise in the [Navari Family Center for Digital Scholarship](https://cds.library.nd.edu/expertise/gis/index.shtml). 

But, our resident campus wizard with all things GIS, mapping, and spatial data is [Prof. Matt Sisk](https://lucyinstitute.nd.edu/people/leadership-team/matthew-sisk/) in the Lucy Family Institute for Data & Society. His many areas of expertise include QGIS and mapping in R. He teaches classes in this area, and also developed an [EdX open educational GIS curriculum](https://edge.edx.org/courses/course-v1:NotreDame+GIS000+0000/about).
