# Lab #2 (Structured Data): Mapping

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Table of Contents

- [Data](#data)
- [Mapping Overview](#mapping-overview)
- [Google MyMaps](#google-mymaps) 
- [ArcGIS Online](#arcgis-online)
- [Carto](#carto)
- [Mapping in Python](#mapping-in-python)
- [Mapping in RStudio](#mapping-in-rstudio)
- [Other Mapping Tools/Resources](#other-mapping-toolsresources)
  * [ArcGIS StoryMaps and Web App Builder](#arcgis-storymaps-and-web-app-builder)
  * [ArcMap](#arcmap)
  * [QGIS](#qgis)
- [Mapping Discussion/Reflection Questions](#mapping-discussionreflection-questions)
 
## Data

1- We'll be using two sample datasets in the Mapping section of the lab.

2- `ND_Directory_Cleaned_Geography.csv` represents a data structure based on the 1922-1923 student directory. Fields in the dataset include:
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

3- `combined_nd_schedules_cleaned.csv` represents a data structure scraped from Sports Reference's Notre Dame college football season results pages. Fields in the dataset include:
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

# Mapping Overview

4- Up to this point, we have focused on exploratory data analysis/visualization in a Cartesian Coordinate system, that is data plotted on an `X` (horizontal) and `Y` (vertical) axis.

5- But for data with geographic or geospatial components, we might want to analyze and visualize those spatial components by mapping the data, or using the data to generate maps that use a `latitude` and `longitude` coordinate system.

6- The next section of the lab covers a few different tools to get started with visualizing spatial data.

7- The lab procedure is going to used the `combined_nd_schedules_cleaned.csv` file.

8- but you can use any of the sample datasets that include spatial (latitude/longitude) information.
- Directories
- Roster data merged with directory data (table we generated from the Excel section of the lab)

9- For most of these mapping tools, we need data that is georeferenced, or data that includes discrete `latitude` and `longitude` coordinates for each location.

10- There are lots of different ways to approach geocoding data, but a couple of free online geocoding services:
- [LocalFocus data journalism batch geocoder](https://geocode.localfocus.nl/)
- [Texas A&M Geocoding Services](https://geoservices.tamu.edu/Services/Geocode/)
  * *Requires creating a free account*

11- Most GIS (geographic information system) software programs also include a geocoding tool:
- QGIS (open-source)
  * Bryan Tor and Thomas Sawano, ["QGIS Geocoding Address Tutorial"](https://guides.library.ucsc.edu/DS/Resources/QGIS) *UC Santa Cruz Library Guide* (Fall 2019)
  * Caitlin Dempsey, ["How to Geocode Addresses Using QGIS"](https://www.gislounge.com/how-to-geocode-addresses-using-qgis/) *GIS Lounge* (9 January 2018) 
- ArcMap (proprietary)
  * ArcMap, ["A quick tour of geocoding"](https://desktop.arcgis.com/en/arcmap/latest/manage-data/geocoding/a-quick-tour-of-geocoding.htm) *ArcGIS Desktop*
  * ArcMap, ["Geocoding a table of addresses in ArcMap"](https://desktop.arcgis.com/en/arcmap/latest/manage-data/geocoding/geocoding-a-table-of-addresses-in-arcmap.htm) *ArcGIS Desktop*

12- Python and RStudio also have specialized packages to facilitate geocoding data:
- Python
  * Abdishakur, ["Geocode with Python"](https://towardsdatascience.com/geocode-with-python-161ec1e62b89) *Towards Data Science* (15 September 2019)
  * [`Geocoder` library documentation](https://geocoder.readthedocs.io/)
  * [`GeoPy` library documentation](https://geopy.readthedocs.io/en/stable/)
- RStudio
  * Oleksandr Titorchuk, ["Breaking Down Geocoding in R: A Complete Guide"](https://towardsdatascience.com/breaking-down-geocoding-in-r-a-complete-guide-1d0f8acd0d4b) *Towards Data Science* (25 April 2020)
  * Aleszu Bajak, ["How to geocode a csv of addresses in R"](https://www.storybench.org/geocode-csv-addresses-r/) *StoryBench* (21 April 2017)

13- All sample datasets for this lab have already been geocoded.

## Google MyMaps

14- Google launched [Google My Maps](https://www.google.com/maps/about/mymaps) in 2007 as part of the Google cloud services suite of programs. Through the My Map interface, users with a Google account can map points, lines, and shapes, with additional display customization options. My Maps allows users to generate maps from spreadsheets, work collaboratively on maps, and share interactive maps.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-473" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="332" /></a></p>

15- Use your ND Google credentials to log into [Google MyMaps](https://www.google.com/maps/).

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-full wp-image-474" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="178" height="55" /></a></p>

16- Click the `Create New Map` icon in the top left-hand corner.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter size-full wp-image-479" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="407" height="295" /></a></p>

17- Name the map by clicking on `Untitled map` in the top left-hand corner. 
- `Football Lab Map` is absolutely fine as a name

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-475" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="317" height="308" /></a></p>

18- Click the blue `Import` icon to start the data import process. 

19- Select or drop a `.csv` file with latitude/longitude information to upload the dataset.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter size-full wp-image-477" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="504" height="433" /></a></p>

20- Check that only `Latitude` and `Longitude` are selected before clicking `Continue`. 

21- My Maps will keep all the original data records but needs to detect which fields contain spatial data.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter size-full wp-image-478" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="509" height="412" /></a></p>

22- The next screen asks what field you want to use for the place marker titles. 

23- Select a useful title field and click `Finish`.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-full wp-image-480" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="307" height="286" /></a></p>

24- Click on the three dots next to the layer to rename the layer with a descriptive name.

25- Depending on the dataset you're using, you may get a message that select rows could not be drawn on the map.

26- If you have additional time, you can come back and explore this error message. For now, click `Dismiss`

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter size-full wp-image-481" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="309" height="41" /></a></p>

27- On the left-hand side of the window is a `Base map` icon that inclues a drop-down menu.

28- You can explore different available base maps to see what works best with your data. 

29- For example, My Maps???s default base map includes topographical data. If that data is not essential for our analysis, a simpler base map (like `Simple Atlas`) can help users focus on the most important aspects of the spatial visualization.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_48.png?raw=true" alt="Capture" /></p>

30- Click on the blue paint roller icon next to the data layer to open a pop-up with style customization options.

31- The default setting is a uniform style for all map markers.

32- We want to think about display customization options that are a good fit for the data we're working with.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_43.png?raw=true" alt="Capture" /></p>

33- We can experiment with grouping points by a particular field, coloring points based on discrete categories or numeric ranges (for numeric fields).
- For example, if you're working with the directory information, you could color points by `Major`.
- Or if you're working with the schedule information, you could color points by `Conf` or `Season`.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_45.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_46.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_47.png?raw=true" alt="Capture" /></p>

34- Once you have a map display you like, you can download, share, or print, using some of the options highlighted in the screenshots.
- Prof. Walden's sample Google My Map for this lab
  * [Public map](https://www.google.com/maps/d/edit?mid=1CUC36a-kqnX7ljy8Wtebc6lYvfxVZODV&usp=sharing)
  * [My Map project](https://www.google.com/maps/d/edit?mid=1CUC36a-kqnX7ljy8Wtebc6lYvfxVZODV&usp=sharing)

### Google MyMaps Discussion/Relection Questions:

- How does working in this mapping tool shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate using this tool?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

## ArcGIS Online

- [Logging in to ArcGIS Online](#logging-in-to-arcgis-online)
- [Creating a New Map](#creating-a-new-map)
- [Adding Data to Your Map](#adding-data-to-your-map)
- [Customizing Your Map](#customizing-your-map)
  * [Basemap](#basemap)
  * [Legend](#legend)
  * [Point symbol, color, and size](#point-symbol-color-and-size)
  * [Heatmaps and clustering](#heatmaps-and-clustering)
  * [Configuring Popups](#configuring-popups)
  * [Other Options](#other-options)
- [Saving, Sharing, and Printing Your Map](#saving-sharing-and-printing-your-map)

35- ArcGIS is an industry-standard tool developed by geographers in the 1970s, from parent company ESRI.

36- From the [ArcGIS Online "Overview" page](https://www.esri.com/en-us/arcgis/products/arcgis-online/overview): 
- "Build interactive web maps with ArcGIS Online, Esri's web-based mapping software. Gain new perspectives and enhanced details as you interact with data, zoom in, and search on the map. Use smart, data-driven mapping styles and intuitive analysis tools to gain location intelligence. Work effectively across your organization by collaboratively building and using maps. Share your insights with specific people or the entire world."

## Logging in to ArcGIS Online

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_54.png?raw=true" alt="Capture" /></p>

37- Open Firefox or Chrome and navigate to https://www.arcgis.com/sharing/rest/oauth2/signup?client_id=arcgisonline&redirect_uri=http://www.arcgis.com&response_type=token in a web brower.

38- Create a free ArcGIS public account.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_49.png?raw=true" alt="Capture" /></p>

39- Once you have an account and have logged in, click `Map` in the top-left page menu.

<blockquote>Note: This rest of this tutorial is written using a sample data set. Your data, map, and map layers will look different than the images included in the tutorial.</blockquote>

## Creating a New Map

<p align="center"><img class=" size-full wp-image-59 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="Capture_6"  /></p>

40-You are now in ArcGIS Online???s map builder interface.

<p align="center"><img class=" size-full wp-image-64 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="Capture_11"  /></p>

41- Click the `Save` icon above the map to save your map.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_50.png?raw=true" alt="Capture" /></p>

42- Add a title, tags, and summary, and click the blue `Save Map` icon. Provide information that will help you find and identify the map you're creating. 

## Adding Data to Your Map

<p align="center"><img class=" size-full wp-image-60 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_7.png?raw=true" alt="Capture_7"  /></p>

43- Click on the `Add` icon in the top-left corner of the page, and select `Add Layer from File`.

44- Click the Browse icon and select one of the lab CSV files that includes geospatial data.

<p align="center"><img class=" size-full wp-image-61 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="Capture_8"  /></p>

45- Click the blue `Import Layer` icon to add the data to your map.

<p align="center"><img class=" size-full wp-image-62 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="Capture_9" /></p>

46- Click the blue `Done` icon to finish adding data to your map.

<p align="center"><img class=" size-full wp-image-64 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="Capture_11"  /></p>

47- Click the `Save` icon above the map to save your map.

## Customizing Your Map

48- The default setting for ArcGIS Online is to display the locations in your data without any styling or customization. 

49- Hover your cursor over the data layer to see additional customization options. 

50- You can use multiple layers to display or highlight different aspects of the data on the map.

### Basemap

<p align="center"><img class=" size-full wp-image-63 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="Capture_10"  /></p>

51- You can change the background map by click a different option in the `Basemap` dropdown.

### Legend

<p align="center"><img class=" wp-image-66 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="Capture_13" /></p>

52- If you want to style points by particular fields, click on the `Change Style` icon. 

53- Choose an element from your data, and explore the drawing style options.

### Point symbol, color, and size

<p align="center"><img class=" size-full wp-image-69 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_16.png?raw=true" alt="Capture_16"  /></p>

<p align="center"><img class=" size-full wp-image-68 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true" alt="Capture_15"  /></p>

54- Click on the `Change Style` icon, and click the blue `Options` icon to explore options for customizing point symbol, color, size, etc..

### Heatmaps and clustering

<p align="center"><img class=" size-full wp-image-70 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_17.png?raw=true" alt="Capture_17"  /></p>

55- You can create a Heat Map in the Change Style window.

56- You can also cluster points using the Cluster Points option in the main map editing window.

### Configuring Popups

<p align="center"><img class=" size-full wp-image-65 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_12.png?raw=true" alt="Capture_12"  /></p>

57- Hover your cursor over the data layer and click the three dots that appear.

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true" alt="Capture_19"  /></p>

58- Click on the Configure Pop-up option to select what data fields display in the pop-up window that appears when you click on a map point. You can also reorder these elements.

### Other options

59- Hover your cursor over the data layer and click the three dots that appear to see additional options for customizing transparency, copying a layer, or naming a layer.

60-Explore display options for this data. One layer does not have to communicate all relevant aspects of the data.

<p align="center"><img class=" size-full wp-image-65 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_12.png?raw=true" alt="Capture_12" /></p>

61-Once you have a layer customized, you can copy that layer to continue exploring other display options without losing the customized layer.

62-Rename layers using descriptive titles to keep them organized.

<p align="center"><img class=" size-full wp-image-64 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="Capture_11"  /></p>

63-Save the Web Map regularly to avoid losing any changes.

## Saving, Sharing, and Printing Your Map

64-Save your map regularly by clicking the Save icon.

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_j.png?raw=true"  /></p>

65-Click the Share icon when you are ready to share your map.

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_k.png?raw=true" /></p>

66-Click the Print icon to generate a static image with your map and legend that you can save as an image or print to a PDF.
- [Prof. Walden's sample map for this lab](https://arcg.is/1n5i1e)

### ArcGIS Online Discussion/Reflection Questions

- How does working in this mapping tool shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate using this tool?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

### Additional Resources

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_51.png?raw=true" alt="Capture" /></p>

67- There's a lot more you can do with ArcGIS Online.

68- NOTE: Notre Dame provides subscription access to ArcGIS Online. Email Prof. Walden for next steps on being added to the ND enterprise account.

69- The tutorials on the landing page are a great place to start.

70- We'll do more with ArcGIS Online in the next lab when we work with digital exhibits. But there are a lot of additional things you can do with ArcGIS Online, especially around bringing interactive maps in conversation with text/media/etc (StoryMaps), or creating interactive dashboards similar to Carto's functionality (ArcGIS Web App Builder).
- [Link to section of the lab that talks more about some of the additional options](#arcgis-storymaps-and-web-app-builder)
  
## Carto

71- [Carto](https://carto.com) is a cloud-computing platform released in 2011 by developer Vizzuality. Written in Ruby and Javascript, Carto is designed to allow businesses to analyze and visualize spatial data without prior or detailed technical GIS knowledge. As we???ll learn in another tutorial, GIS programs like ArcGIS are not always intuitive and user-friendly. Carto was designed as an alternative, with a web-hosted option that doesn???t require a local installation, although Carto is available as <a href="https://github.com/CartoDB/CartoDB">open source software</a>. The short version???users can work with Carto in the browser without needing to set up their own server to host the program. The web-based version of Carto is considered a ["freemium"](https://carto.com/pricing) software- free for some types of users with limited web-based functionality with scaled pricing plans for long-term use.

72- From [Carto](https://carto.com/help/getting-started/student-accounts/): "Students can create a free CARTO account via GitHub???s Student Developer Pack."

73- [Sign up](https://education.github.com/pack) for a free GitHub Student Developer Pack.

74- The Developer Pack also gives you discounted or free access to a range of different toolks and resources, including Canva, Digital Ocean, Microsoft Azure, and Carto.

75- Once you have signed up for the GitHub Student Developer Pack, create a free Carto account.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-461" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="335" /></a></p>

76- Log in to Carto. If needed, click on `My Dashboard`

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-full wp-image-462" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="424" height="211" /></a></p>

77- Next to your name in the top menu is a `Maps` icon with a dropdown arrow. 

78- Select `Your datasets` from the dropdown

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-463" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="381" height="77" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true"><img class="aligncenter size-large wp-image-464" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="" width="676" height="549" /></a></p>

79- Click the `New Dataset` icon in the upper right-hand corner of the page.

80- Select one of the `CSV` files for this lab that includes geospatial data, or drag and drop it into the upload section of the page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter size-full wp-image-465" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="273" height="98" /></a></p>

81-Click the `Connect Dataset` blue icon in the bottom right-hand corner of the page to upload the dataset to Carto.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter size-large wp-image-466" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="676" height="329" /></a></p>

82- Once your data has been added to Carto, compare how the data was structured in Excel or Tableau versus how it is structured and described in Carto. 
- What similarities do you notice? What has changed? Why do you think Carto made these changes or added this additional information?

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter size-full wp-image-467" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="181" height="78" /></a></p>

83- Click the blue `Create Map` icon in the bottom right-hand corner of the page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-large wp-image-468" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="676" height="331" /></a></p>

84- Once you???ve created a map, you move into Carto???s `builder environment`. Use the four-step tour to learn more about Carto???s map editing page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true"><img class="aligncenter size-full wp-image-450" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="" width="347" height="398" /></a></p>

85- Rename the map by clicking on the three vertical dots next to the data file name.

86- Click `Rename` to add a descriptive title. You can also rename the map by double-clicking the title.

87- Let???s explore the map editing page. 
- Use the plus or minus symbols in the bottom left-hand corner of the map to zoom in and out on the map. 
- Double-clicking an area or using your mouse scroll wheel are also ways to zoom in and out.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter size-full wp-image-471" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="324" height="307" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true"><img class="aligncenter size-full wp-image-449" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true" alt="" width="346" height="947" /></a></p>

88- Click on any map point and click on the small light blue pencil icon that appears. 

89- Clicking this editing icon shows you that point???s attributes, such as its latitude, longitude, and other descriptive information. 
- If needed, you could edit point data on this screen.

90- To exit looking at data points, click the `Back` arrow in the top left-hand corner of the page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter size-full wp-image-470" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="306" height="287" /></a></p>

91- Although we are only working with one data layer in this tutorial, many mapping projects work with multiple layers so naming data layers is a useful practice. 

92- To rename the data layer:
- Click on the three vertical dots next to the dataset???s title. 
- Click `rename` and enter an appropriate descriptive name for the data set. 
- You can also rename the data set by double-clicking the title.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true"><img class="aligncenter size-full wp-image-451" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true" alt="" width="347" height="946" /></a></p>

93- Click on the data layer to move into Carto???s layer editing environment.

94- Another brief tour can help you navigate the layer pane, which includes a menu with `Data`, `Analysis`, `Style`, `Pop-Up`, and `Legend` options.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true"><img class="aligncenter size-full wp-image-452" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true" alt="" width="332" height="222" /></a></p>

95- Select `Style` from the layer menu.

96- `Aggregation` offers different ways to visualize your data points on the map, from the default circular points to hexagons to heat maps and time animations. 
- What types of aggregation are most effective for this data set? 
- What types of aggregation do not work for this data set? 
- What aspects of the data are highlighted in different aggregations?

97- The second option in the `Style` menu allows you to change the size and color of your data points. 

98- In Carto???s default settings, point size and color is standardized across all data points.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true"><img class="aligncenter size-full wp-image-453" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true" alt="" width="325" height="240" /></a></p>

99- Under `Point Size`, switch the selection from `Fixed` to `By value` to size points by a numeric data field.

100- Sizing points by value selects a data field and sizes points based on how frequently they appear in the dataset.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_17.PNG?raw=true"><img class="aligncenter size-full wp-image-454" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_17.PNG?raw=true" alt="" width="379" height="334" /></a></p>

101- When sizing points by value, you can customize how many buckets (categories) you want to have, as well as how the distribution of those buckets is calculated. 

102- Carto???s default setting uses Quantiles to calculate bucket distribution, but you can select other ways to calculate those ranges.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true"><img class="aligncenter size-full wp-image-453" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true" alt="" width="325" height="240" /></a></p>

103- In addition to sizing points by value, we can also assign colors to points based on their value. 
- Switch the `Point Size` selection back to `Fixed`
- Switch the `Point Color` selection from `Solid` to `By Value`
- Select a data field (numeric or string) to use for point color

104- As with `Point Size`, Carto lets you select your number of buckets and how those bucket ranges are calculated. 

105- You can use one of Carto???s preset color palettes or build your own custom color set using a free online resource like [Color Brewer](http://colorbrewer2.org). 

106- Carto also gives you the option to change the size of your points (`point size`), the size of your point outline (`point stroke`) and the color of your point outline (`stroke color`).

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true"><img class="aligncenter size-full wp-image-456" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true" alt="" width="344" height="826" /></a></p>

107- Select the `Pop-Up` icon in the layer menu. 

108- Pop-Ups include data that displays when you click on a specific map point. In Carto???s default settings, no customized pop-ups appear.

109- Select `Click` to design the pop-up that appears when you click on a map point. 

110- Select `Hover` to design the pop-up that appears when you hover over a map point.

111- For `Click` and `Hover`, Carto lets you to determine the size and coloring of the pop-up window, as well as what data fields are displayed (and how they are labeled).

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_20.PNG?raw=true"><img class="aligncenter size-full wp-image-457" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_20.PNG?raw=true" alt="" width="497" height="837" /></a></p>

112- If you wanted to further customize your pop-ups, Carto provides an `HTML view` where you could further customize the style of text in your pop-ups.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-large wp-image-468" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="676" height="331" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_21.PNG?raw=true"><img class="aligncenter size-full wp-image-458" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_21.PNG?raw-true" alt="" width="111" height="62" /></a></p>

113- Once you are satisfied with the styling of your pop-ups, click the `back` arrow to return to the main editing page. 

114- Because Carto is a cloud-based service, it is saving edits as you make them. 

115- However, the map project will not be published or shared until you click the `Publish` blue rectangular icon on the bottom left-hand side of the page.
- [Prof. Walden's sample map for this lab](https://kwalden.carto.com/builder/be217bb8-46f4-47a1-83dc-96ccd200e175/embed)

### Carto Discussion/Reflection Questions

- How does working in this mapping tool shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate using this tool?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

### Additional Resources

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_22.PNG?raw=true"><img class="size-full wp-image-459 aligncenter" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_22.PNG?raw=true" alt="" width="340" height="299" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_23.PNG?raw-true"><img class="size-full wp-image-460 aligncenter" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_23.PNG?raw=true" alt="" width="332" height="233" /></a></p>

116- In this tutorial, we have been focusing on editing a data layer in Carto. The program also includes tools that let you analyze your data (`Layers` and `Analysis`) and add interactive `Widgets` for a dynamic public interface.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_52.png?raw=true" alt="Capture" /></p>

117- [Link to Prof. Walden's sample map with widgets for this lab](https://kwalden.carto.com/builder/be217bb8-46f4-47a1-83dc-96ccd200e175/embed)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_53.png?raw=true" alt="Capture" /></p>

118- To learn more about Carto's features and functionality: https://carto.com/help/

## Mapping in Python

119- As mentioned earlier in the lab, Prof. Walden has built out a Jupyter notebook that goes into more detail about using Python for exploratory data analysis for the sample datasets presented in this lab.

120- That notebook also includes sample code for static and interactive mapping in Python.

121- The Jupyter notebook uses the following programs and Python libraries:
- `matplotlib`
- `pandas`
- `geopandas`
- `plotly`

122- The Jupyter notebook includes sample code for the following steps/tasks, using the roster, directory, and schedule datasets:
- Load data as Pandas `DataFrame`
- Merging directory and roster datasets
- Static visualization with `Pandas` and `Matplotlib`
- Static geospatial data visualization with `geopandas`, `shapely`, and `matplotib`
- Interactive visualization with `plotly`
- Interactive geospatial data visualization with `plotly`

123- Jupyter Notebook:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.ipynb)
- [NBviewer](https://nbviewer.jupyter.org/github/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.ipynb)
- [Google CoLab](https://drive.google.com/file/d/1MybxGo9ngdm20rzV1xAqAGYZwNsLINTM/view?usp=sharing)

### Python Discussion/Reflection Questions

- How does with mapping in Python shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate using Python?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

## Mapping in RStudio

124- As mentioned earlier in the lab, Prof. Walden has built out an RMarkdown file that goes into more detail about using RStudio for exploratory data analysis for the sample datasets presented in this lab.

125- That RMarkdown file also includes sample code for static and interactive mapping in RStudio.

126- The RMarkdown file uses the following programs and packages:
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

127- The RMarkdown notebook includes sample code for the following steps/tasks, using the roster, directory, and schedule datasets:
- Load data as `DataFrame`
- Merging directory and roster datasets using `dplyr` and `tidyr`
- Static visualization with `ggplot2`
- Static geospatial data visualization with `ggplot2`, `sf`, `sp`, `tmap`, and `maps`
- Interactive visualization with `plotly`
- Interactive geospatial data visualization with `plotly` and `leaflet`

128- RMarkdown File:
- [`.rmd` file on GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.Rmd)
- [`.rmd` file on Google Drive](https://drive.google.com/file/d/1gvhci2x1IVsHOFCEwkeVvm_HSUPU0l2V/view?usp=sharing)
- [RStudio Cloud](https://rstudio.cloud/project/2977118)

129- RStudio Project:
- [GitHub, `.zip`](https://drive.google.com/file/d/1zex8zotq6TpLtzcDukl0NtH8oxaswBqR/view?usp=sharing)
- [RStudio Cloud](https://rstudio.cloud/project/2977118)

### RStudio Discussion/Reflection Questions

- How does with mapping in RStudio shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate using RStudio?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

## Mapping Discussion/Reflection Questions

- Thinking holistically across the mapping tool(s) you interacted with, what questions were you interested in asking or exploring about the spatial components of the sample datasets? 
- How did using spatial analysis/visualization tools shape your understanding of the data?
- Where would you go next with spatial analysis/visualization tools? 
  * What questions or topics would you want to explore using the sample datasets? 
  * Or, what other types of spatial information/data related to ND football would you want to work with?
- Other comments/questions/observations

## Other Mapping Tools/Resources

- [ArcGIS StoryMaps and Web App Builder](#arcgis-storymaps-and-web-app-builder)
- [ArcMap and QGIS](#arcmap-and-qgis)
- [On-Campus Resources](#on-campus-resources)

### ArcGIS StoryMaps and Web App Builder

We'll do more with ArcGIS Online in the next lab when we work with digital exhibits. But there are a lot of additional things you can do with ArcGIS Online, especially around bringing interactive maps in conversation with text/media/etc (StoryMaps), or creating interactive dashboards similar to Carto's functionality (ArcGIS Web App Builder).

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

### ArcMap and QGIS

There are also desktop software applications that can be used for spatial data analysis and visualization.

NOTE: This is not a GIS (geographical information systems) class. Prof. Walden can connect folks with resources, but advanced GIS work is beyond the scope of the class.

#### ArcMap

ArcGIS is an industry-standard tool developed by geographers in the 1970s. As digital historians have pursued more complex and large-scale spatial analysis projects, ArcGIS is a tool frequently used to visualize and analyze spatial data. The ArcGIS Online platform (not covered in this tutorial but featured in many digital mapping projects) allows data analyzed and visualized in ArcGIS to be interactive and publicly-accessible. 
- NOTE: The ArcGIS desktop application is only available for PC users.

Tutorials:
- [Getting Started with ArcMap](https://github.com/kwaldenphd/ArcMap-introduction)

Current ND students have access to the ArcMap title through OIT.
- [Virtual Computer Lab](http://go.nd.edu/vcl)
- [Contact OIT about getting ArcMap on your personal computer](https://oit.nd.edu/services/software/software-downloads/arcgis-desktop/)

#### QGIS

QGIS is a powerful open-source alternative to ArcMap that works across operating systems.

Documentation:
- [More information abou tthe QGIS project](https://qgis.org/en/site/index.html)
- [Download QGIS](https://qgis.org/en/site/forusers/download.html)

Tutorials:
- [QGIS Documentation](https://docs.qgis.org/3.16/en/docs/training_manual/index.html)
- Jim Clifford, Josh MacFadyen, and Daniel Macfarlane, "Installing QGIS 2.0 and Adding Layers," The Programming Historian 2 (2013), https://doi.org/10.46430/phen0031.
- Justin Colson, "Geocoding Historical Data using QGIS," The Programming Historian 6 (2017), https://doi.org/10.46430/phen0066.

## On-Campus Resources

We also have a deep bench of expertise in the [Navari Family Center for Digital Scholarship](https://cds.library.nd.edu/):
- [Matt Sisk](https://directory.library.nd.edu/directory/employees/msisk1), GIS/Anthropology Librarian
  * Matt is an absolute wizard with all things GIS, mapping, and spatial data. His many areas of expertise include QGIS and mapping in RStudio.

We'll come back to these on-campus resources when we start working on the final project.
