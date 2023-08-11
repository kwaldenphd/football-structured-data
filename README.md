# Lab #2: Structured Data

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial was written by <a href="https://github.com/kwaldenphd">Katherine Walden</a> is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

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

[Link to Google Drive folder with lab materials and resources, including notebook template](https://drive.google.com/drive/folders/1L3eJm07Nt7mttozZujo4bsKkkZdAXKBn?usp=sharing) (ND Users)

# How to Work Through This Lab

There are four main sections to this lab:
- [Background, University Archives, and Sample Datasets](https://github.com/kwaldenphd/football-structured-data)
- [Exploratory data analysis/visualization](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md) (EDA)
- [Mapping](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md)
- [Network Analysis](https://github.com/kwaldenphd/football-structured-data/blob/main/networks.md)

# Background

In the previous lab, we focused on using these source materials as unstructured text for different types of analysis facilitated by digital/computational tools.

Now we're going to think about how we can engage with primary source material with structured data as a starting point for other kinds of analysis and exploration that rely on modes of data analysis/visualization that work with structured data.

We'll start by looking at a few different types of data sources and data wrangling workflows for structured data:
- `Directories` takes a PDF of digitized historical student directories and uses a combination of OCR, OpenRefine, and regular expressions to transform the PDF to a `CSV` file
- `Football Rosters` uses Python to scrape Sports Reference web pages for ND football to get a data table
- `Football Schedules` uses Python to scrape Sports Reference web pages for ND football schedule and game results to get data table
- `Rockne Coaching Tree` transforms information about Rockne's coaching tree into a data table that could be used for network analysis

[Link to this section of the lab](https://github.com/kwaldenphd/football-structured-data/blob/main/background.md)

# Exploratory Data Analysis/Visualization

From [Wikipedia](https://en.wikipedia.org/wiki/Exploratory_data_analysis): "In statistics, exploratory data analysis is an approach of analyzing data sets to summarize their main characteristics, often using statistical graphics and other data visualization methods...EDA is for seeing what the data can tell us beyond the formal modeling or hypothesis testing task."

To think about this another way, "the purpose of EDA is to use summary statistics and visualizations to better understand data, and find clues about the tendencies of the data, its quality and to formulate assumptions and the hypothesis of our analysis" (Andrew Andrade and Lukasz Golab, ["Exploratory Data Analysis"](https://datascienceguide.github.io/exploratory-data-analysis) *Data Science Guide*)

Now that we have a sense of what types of data might come from primary sources, we'll work with some of those same datasets using tools and workflows geared toward visualizing structured data. We'll start by getting a sense of what's in a particular dataset (WTFcsv), then spend some time with a spreadsheet program (Microsoft Excel or Google Sheets). Folks comfortable with Python or R/RStudio will have the option to explore those workflows.

[Link to this section of the lab](https://github.com/kwaldenphd/football-structured-data/blob/main/eda.md)

# Mapping

Another aspect of data visualization we'll explore in this lab involves geospatial data, or data that includes location information. Thinking about our sample datasets, student directory data includes location information, as does the game schedule sample dataset. We'll start by getting a sense of how to work with geospatial data, using Google MyMaps and ArcGIS Online. Folks comfortable with Python or R/RStudio will have the option to explore those workflows.

[Link to this section of the lab](https://github.com/kwaldenphd/football-structured-data/blob/main/mapping.md)

# Networks

In this section of the lab, we're thinking about how structured data can be the starting point for looking at networks and relationships, under the umbrella of network analysis. We can think of a coaching tree as a type of network, where the relationship of coaches in the tree is understood via nodes and edges. We'll explore Knute Rockne's coaching tree as a network using a couple of web-based tools (Palladio and Connect The Dots).

[Link to this section of the lab](https://github.com/kwaldenphd/football-structured-data/blob/main/networks.md)

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
