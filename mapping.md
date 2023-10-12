# Lab #2 (Structured Data): Mapping

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Table of Contents

- [Files](#files)
- [Mapping Overview](#mapping-overview)
- [Google MyMaps](#google-mymaps) 
- [ArcGIS Online](#arcgis-online)
- [Oh, the Places You Could Go!](#oh-the-places-you-could-go)
- [Discussion/Reflection Questions](#discussionreflection-questions)
 
## Files

We'll be using two sample datasets in the Mapping section of the lab.

`ND_Directory_Cleaned_Geography.csv` represents a data structure based on the 1922-1923 student directory. Fields in the dataset include:
- `Combined_Name_Original` (combined first name, last name, and major field)
- `Combined_Name` (combined first name, last name field)
- `Last_Name` (standarized last name)
- `First_Name` (standardized first name)
- `Major` (standardized major)
- `Combined_Address` (combined street, city, state, and country field)
- `Street` (standardized-ish street)
- `City` (standardized city)
- `State` (standardized state)
- `Country` (standardized country)
- `Standardized_Address` (standardized combined street, city, state, country field)
- `Standardized_City_State` (standardized city, state, country field)
- `Country` (standardized country)
- `Latitude` (latitude)
- `Longitude` (longitude)

`combined_nd_schedules_cleaned.csv` represents a data structure scraped from Sports Reference's Notre Dame college football season results pages. Fields in the dataset include:
- `G` (game number)
- `Season` (season or year)
- `Standarized_Date` (standardized game date, YYYY-MM-DD)
- `Date` (original date field, MM DD, YYYY)
- `Day` (game day of week)
- `Time` (game time of day)
- `School` (Notre Dame, includes ranking)
- `Standardized_School` (standardized Notre Dame school field, does not include ranking)
- `Game_Type` (home, away, neutral site game)
- `Opponent` (opponent, includes ranking)
- `Standarized_Opponent` (standardized opponent school field, does not include ranking)
- `Post_Season` (Y/N field indicating if game is postseason/bowl/playoff game)
- `Conf` (conference)
- `Result` (W/L/T game result)
- `Combined_Location` (combined game location, location/city/state/country)
- `City` (game site city)
- `State` (game site state)
- `Country` (game site country)
- `Pts` (number of ND points in game)
- `Opp` (number of opponent points in game`
- `W` (win number)
- `L` (loss number)
- `T` (tie number)
- `Streak` (W/L/T streak)
- `Notes` (additional notes on game)
- `Latitude` (latitude)
- `Longitude` (longitude)

# Overview

Up to this point, we have focused on exploratory data analysis/visualization in a Cartesian Coordinate system, that is data plotted on an `X` (horizontal) and `Y` (vertical) axis. But for data with geographic or geospatial components, we might want to analyze and visualize those spatial components by mapping the data, or using the data to generate maps that use a `latitude` and `longitude` coordinate system.

The next section of the lab covers a few different tools to get started with visualizing spatial data. The lab procedure is going to used the `combined_nd_schedules_cleaned.csv` file, but you can use any of the sample datasets that include spatial (latitude/longitude) information.
- Directories
- Roster data merged with directory data (table we generated from the Excel section of the lab)

## Geocoding

For most of these mapping tools, we need data that is georeferenced, or data that includes discrete `latitude` and `longitude` coordinates for each location. All sample datasets for this lab have already been geocoded.

If you end up needing to geocode your own data, there are lots of different ways to approach geocoding data, but a couple of free online geocoding services:
- [LocalFocus data journalism batch geocoder](https://geocode.localfocus.nl/)
- [Texas A&M Geocoding Services](https://geoservices.tamu.edu/Services/Geocode/)
  * *Requires creating a free account*

Most GIS (geographic information system) software programs also include a geocoding tool:
- QGIS (open-source)
  * Bryan Tor and Thomas Sawano, ["QGIS Geocoding Address Tutorial"](https://guides.library.ucsc.edu/DS/Resources/QGIS) *UC Santa Cruz Library Guide* (Fall 2019)
  * Caitlin Dempsey, ["How to Geocode Addresses Using QGIS"](https://www.gislounge.com/how-to-geocode-addresses-using-qgis/) *GIS Lounge* (9 January 2018) 
- ArcMap (proprietary)
  * ArcMap, ["A quick tour of geocoding"](https://desktop.arcgis.com/en/arcmap/latest/manage-data/geocoding/a-quick-tour-of-geocoding.htm) *ArcGIS Desktop*
  * ArcMap, ["Geocoding a table of addresses in ArcMap"](https://desktop.arcgis.com/en/arcmap/latest/manage-data/geocoding/geocoding-a-table-of-addresses-in-arcmap.htm) *ArcGIS Desktop*

Python and RStudio also have specialized packages to facilitate geocoding data:
- Python
  * Abdishakur, ["Geocode with Python"](https://towardsdatascience.com/geocode-with-python-161ec1e62b89) *Towards Data Science* (15 September 2019)
  * [`Geocoder` library documentation](https://geocoder.readthedocs.io/)
  * [`GeoPy` library documentation](https://geopy.readthedocs.io/en/stable/)
- RStudio
  * Oleksandr Titorchuk, ["Breaking Down Geocoding in R: A Complete Guide"](https://towardsdatascience.com/breaking-down-geocoding-in-r-a-complete-guide-1d0f8acd0d4b) *Towards Data Science* (25 April 2020)
  * Aleszu Bajak, ["How to geocode a csv of addresses in R"](https://www.storybench.org/geocode-csv-addresses-r/) *StoryBench* (21 April 2017)

# Google MyMaps

1- Google launched [Google My Maps](https://www.google.com/maps/about/mymaps) in 2007 as part of the Google cloud services suite of programs. Through the My Map interface, users with a Google account can map points, lines, and shapes, with additional display customization options. My Maps allows users to generate maps from spreadsheets, work collaboratively on maps, and share interactive maps.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-473" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="332" /></a></p>

2- Use your ND Google credentials to log into [Google MyMaps](https://www.google.com/maps/).

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-full wp-image-474" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="178" height="55" /></a></p>

3- Click the `Create New Map` icon in the top left-hand corner.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter size-full wp-image-479" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="407" height="295" /></a></p>

4- Name the map by clicking on `Untitled map` in the top left-hand corner. 
- `Football Lab Map` is absolutely fine as a name

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-475" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="317" height="308" /></a></p>

5- Click the blue `Import` icon to start the data import process. Select or drop a `.csv` file with latitude/longitude information to upload the dataset.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter size-full wp-image-477" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="504" height="433" /></a></p>

6- Check that only `Latitude` and `Longitude` are selected before clicking `Continue`. My Maps will keep all the original data records but needs to detect which fields contain spatial data.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter size-full wp-image-478" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="509" height="412" /></a></p>

7- The next screen asks what field you want to use for the place marker titles. Select a useful title field and click `Finish`.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-full wp-image-480" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="307" height="286" /></a></p>

8- Click on the three dots next to the layer to rename the layer with a descriptive name. 

9- Depending on the dataset you're using, you may get a message that select rows could not be drawn on the map. If you have additional time, you can come back and explore this error message. For now, click `Dismiss`

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter size-full wp-image-481" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="309" height="41" /></a></p>

10- On the left-hand side of the window is a `Base map` icon that inclues a drop-down menu. You can explore different available base maps to see what works best with your data. 

11- For example, My Maps’s default base map includes topographical data. If that data is not essential for our analysis, a simpler base map (like `Simple Atlas`) can help users focus on the most important aspects of the spatial visualization.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_48.png?raw=true" alt="Capture" /></p>

12- Click on the blue paint roller icon next to the data layer to open a pop-up with style customization options. The default setting is a uniform style for all map markers. We want to think about display customization options that are a good fit for the data we're working with.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_43.png?raw=true" alt="Capture" /></p>

13- We can experiment with grouping points by a particular field, coloring points based on discrete categories or numeric ranges (for numeric fields).
- For example, if you're working with the directory information, you could color points by `Major`.
- Or if you're working with the schedule information, you could color points by `Conf` or `Season`.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_45.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_46.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_47.png?raw=true" alt="Capture" /></p>

14- Once you have a map display you like, you can download, share, or print, using some of the options highlighted in the screenshots.
- Prof. Walden's sample Google My Map for this lab
  * [Public map](https://www.google.com/maps/d/edit?mid=1CUC36a-kqnX7ljy8Wtebc6lYvfxVZODV&usp=sharing)
  * [My Map project](https://www.google.com/maps/d/edit?mid=1CUC36a-kqnX7ljy8Wtebc6lYvfxVZODV&usp=sharing)

## Google MyMaps Discussion/Relection Questions:

- How does working in this mapping tool shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate using this tool?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

# ArcGIS Online

15- ArcGIS is an industry-standard tool developed by geographers in the 1970s, from parent company ESRI. From the [ArcGIS Online "Overview" page](https://www.esri.com/en-us/arcgis/products/arcgis-online/overview): 
- "Build interactive web maps with ArcGIS Online, Esri's web-based mapping software. Gain new perspectives and enhanced details as you interact with data, zoom in, and search on the map. Use smart, data-driven mapping styles and intuitive analysis tools to gain location intelligence. Work effectively across your organization by collaboratively building and using maps. Share your insights with specific people or the entire world."

## Logging in to ArcGIS Online

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_54.png?raw=true" alt="Capture" /></p>

16- Accept the ArcGIS Online email invitation you received at your ND email address.
- Alternatively, open Firefox or Chrome and log in at https://notredame.maps.arcgis.com.

## Getting Started With ArcGIS Online

17- A few tutorials and resources for getting started with ArcGIS Online:
- [ArcGIS Online documentation](https://doc.arcgis.com/en/arcgis-online/get-started/get-started-with-maps-mv.htm)
- [ArcGIS Online documentation tutorial that includes screenshots but uses a specific dataset](https://learn.arcgis.com/en/projects/get-started-with-map-viewer/arcgis-online/)
- [ArcGIS Online: Mapping Basics, video tutorial](https://mediaspace.esri.com/media/t/1_7ok0ourg)

18- Other ArcGIS Online resources:
- [ESRI Resources](https://www.esri.com/en-us/arcgis/products/arcgis-online/resources)
- [ESRI Video Resources](https://mediaspace.esri.com/channel/ArcGIS%2BOnline/238048082)

## ArcGIS Online Discussion/Reflection Questions

19-Spend some time (20-25 minutes as a starting point) exploring at least one of the sample datasets for this lab in ArcGIS Online.

20-Discussion/reflection questions:
- How does working in this mapping tool shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate using this tool?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

# Oh, the Places You Could Go!

In addition to the web-based graphical user interface (GUI) tools we've explored, there are also programmatic workflows and more advanced desktop software to support working with geospatial data.
- [Click here](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping-advanced.md) to access this section of the lab.

# Discussion/Reflection Questions

- Thinking holistically across the mapping tool(s) you interacted with, what questions were you interested in asking or exploring about the spatial components of the sample datasets? 
- How did using spatial analysis/visualization tools shape your understanding of the data?
- Where would you go next with spatial analysis/visualization tools? 
  * What questions or topics would you want to explore using the sample datasets? 
  * Or, what other types of spatial information/data related to ND football would you want to work with?
- Other comments/questions/observations
