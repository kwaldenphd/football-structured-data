# Lab #2: Structured Data

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Overview

This lab will involve using data analysis and visualization methods to interact with digitized football-related material from the University Archives as structured data. The project will include opportunities to develop a data model/structure, use manual or computational methods to map information from primary sources to a data structure, and conduct exploratory data analysis/visualization (using coding and no-coding tools/methods). This lab will focus on methods for working with structured data. 

[Click here](https://github.com/kwaldenphd/football-structured-data/blob/main/acknowledgements.md) to view a full list of acknowledgements for this lab.

# Table of Contents

- [How to Work Through This Lab](#how-to-work-through-this-lab)
- [Background](#background)
- [University Archive Digital Collections](#university-archive-digital-collections)
- [Sample Datasets](#sample-datasets)
- [Exploratory Data Analysis/Visualization](#exploratory-data-analysisvisualization)
- [Mapping](#mapping)
- [Networks](#networks)
- [Lab Notebook Components](#lab-notebook-components)

# How to Work Through This Lab

There are four main sections to this lab:
- [Background, University Archives, and Sample Datasets](https://github.com/kwaldenphd/football-structured-data)
- [Exploratory data analysis/visualization](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md) (EDA)
- [Mapping](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md)
- [Network Analysis](https://github.com/kwaldenphd/football-structured-data/blob/main/networks.md)

We'll spend two Thursday class periods leading up to the midterm break working on this lab (10/7, 10/14). Folks can (but are not required) to continue working over the break. 

Our endpoint for this lab will be documenting your work going through the three sections of the lab. There will not be a "now it's your turn" section at the end of this lab.

Given time constraints, we're going to try to wrap this lab up before the midterm break. And it's not going to be possible for folks to do more unstructured independent work within those time constraints.

So folks who want to continue working with these tools/methods for your own research questions/topics will have an opportunity to do that in our third and last lab.

Since there's not going to be a collaborative "now it's your turn" section at the end of the lab, folks will work in groups in class time, but you can also choose to turn in an individual lab notebook. 

Collaborate to the degree that it is useful and helpful to work through the material.

# Background

[Link to this section of the lab](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md)

**Section table of contents**
- [Background](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md#background)
- [University Archive Digital Collections](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md#university-archive-digital-collections)
- [Sample Datasets](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md#sample-datasets)
  * [Directories](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md#directories)
  * [Football Rosters](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md#football-rosters)
  * [Football Schedules](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md#football-schedules)
  * [Knute Rockne Coaching Tree](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md#knute-rockne-coaching-tree)
  * [Things to Take Away From This Section](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md#things-to-take-away-from-this-section)

I'm asking everyone to spend time with the discussion/reflection questions for the `Background` and `University Archives` sections.

This lab includes four sample datasets.
- `Directories` takes a PDF of digitized historical student directories and uses a combination of OCR, OpenRefine, and regular expressions to transform the PDF to a `CSV` file
- `Football Rosters` uses Python to scrape Sports Reference web pages for ND football to get a data table
- `Football Schedules` uses Python to scrape Sports Reference web pages for ND football schedule and game results to get data table
- `Rockne Coaching Tree` transforms information about Rockne's coaching tree into a data table that could be used for network analysis

I encourage folks to skim the information provided about the background/data processing workflow for all the sample datasets.

For the lab notebook, you can engage with the discussion/reflection questions for 1-2 of the sample datasets.

# Exploratory Data Analysis/Visualization

[Link to this section of the lab](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md)

**Section table of contents**
- [Exploratory Data Visualization](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md#exploratory-data-visualization)
  * [DataBasic: WTFcsv](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md#databasic-wtfcsv)
  * [Excel](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md#excel)
  * [Tableau](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md#tableau)
  * [Python](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md#python)
  * [RStudio](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md#rstudio)
- [Discussion/Reflection Questions](#discussionreflection-questions) 

I'm asking everyone to spend some time with WTFcsv and Tableau.

PICK ONE:
- Folks with programming backgrounds can spend time working in RStudio/Python.
- Folks who don't have a programming background can do more extensive work with Microsoft Excel and Google Sheets.

The discussion/reflection questions at the end of the lab ask you to think holistically across the different programs/tools you focused on.
- There will be some questions that related to specific programs/tools. You are not required to respond to or engage with all of the questions.
- Definitely cover the general questions and any specific to WTFcsv and Tableau, but pick and choose from the others based on what programs/tools you worked with.

# Mapping

[Link to this section of the lab](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md)

**Section table of contents**

- [Google MyMaps](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#google-mymaps) 
- [ArcGIS Online](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#arcgis-online)
- [Carto](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#carto)
- [Mapping in Python](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#mapping-in-python)
- [Mapping in RStudio](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#mapping-in-rstudio)
- [Other Mapping Tools/Resources](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#other-mapping-toolsresources)
  * [ArcGIS StoryMaps and Web App Builder](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#arcgis-storymaps-and-web-app-builder)
  * [ArcMap](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#arcmap)
  * [QGIS](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#qgis)
- [Mapping Discussion/Reflection Questions](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md#mapping-discussionreflection-questions)

I'm asking everyone to spend some time with ArcGIS Online.
- Folks who don't have a background with data/mapping might want to start with Google MyMaps before you jump into ArcGIS Online.

PICK ONE:
- Folks with programming backgrounds can spend time working in RStudio/Python.
- Folks interested in doing more in-depth work with mapping can explore Carto (web-based program that does not involve any coding).

The discussion/reflection questions at the end of the lab ask you to think holistically across the different programs/tools you focused on.
- There will be some questions that related to specific programs/tools. You are not required to respond to or engage with all of the questions.
- Definitely cover the general questions and any specific to ArcGIS Online, but pick and choose from the others based on what programs/tools you worked with.

# Networks

[Link to this section of the lab](https://github.com/kwaldenphd/football-structured-data/blob/main/networks.md)

**Section table of contents**
- [DataBasic: Connect the Dots](https://github.com/kwaldenphd/football-structured-data/blob/main/networks.md#databasic-connect-the-dots)
- [Palladio](https://github.com/kwaldenphd/football-structured-data/blob/main/networks.md#palladio)
- [Gephi](https://github.com/kwaldenphd/football-structured-data/blob/main/networks.md#gephi)
- [Network Discussion/Reflection Questions](https://github.com/kwaldenphd/football-structured-data/blob/main/networks.md#network-discussionreflection-questions)
- [Other Network Tools/Resources](https://github.com/kwaldenphd/football-structured-data/blob/main/networks.md#other-network-toolsresources)

I'm asking everyone to spend some time with ConnectTheDots.

PICK ONE:
- Folks who want to more in-depth work with network analysis/statistics can spend time with Gephi (open-source software, no coding)
- Folks who want to focus more on network graphs/visualizations can spend time with Palladio (web-based program, no coding)
- Folks with programming backgrounds are welcome to explore some of the linked RStudio/Python resources and tutorials

The discussion/reflection questions at the end of the lab ask you to think holistically across the different programs/tools you focused on.
- There will be some questions that related to specific programs/tools. You are not required to respond to or engage with all of the questions.
- Definitely cover the general questions and any specific to ConnectTheDots, but pick and choose from the others based on what programs/tools you worked with.

# Lab Notebook Components

- Reflections/observations from exploratory data analysis/visualization section of the lab
- Reflections/observations from the mapping section of the lab
- Reflections/observations from the networks section of the lab
- Any data files you worked with (that aren't in the sample datasets)
- If you worked with Python/RStudio: Scripts or notebooks for any original code you generated
- Individual reflection
  * At least 200 words (or 2-3 minutes audio/video), addressing the following questions:
    * What you learned about working with structured data through this lab
    * What you learned about data analysis/visualization through this lab
    * How you're thinking about data analysis/visualization as they relate to ND football history and primary sources differently after this lab
    * Where you would go next with these tools/methods (other research questions/topics you're interested in exploring, other data sources or types of data you would want to be able to work with, etc)
    * Other comments/questions/observations

If you're working in Google Drive, you can just submit a link to Google Drive.

Notebooks can be individual or collaborative.
