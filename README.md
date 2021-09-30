# Lab #2: Structured Data

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Overview

This lab will involve using data analysis and visualization methods to interact with digitized football-related material from the University Archives as structured data. The project will include opportunities to develop a data model/structure, use manual or computational methods to map information from primary sources to a data structure, and conduct exploratory data analysis/visualization (using coding and no-coding tools/methods). This lab will focus on methods for working with structured data. 

# Table of Contents

# Background

To prepare for this lab, we read Miriam Posner's 2015 keynote "[Humanities Data: A Necessary Contradiction](https://miriamposner.com/blog/humanities-data-a-necessary-contradiction/)" and explored the companion "[Early African American Film: Reconstructing the History of Silent Race Films, 1909-1930](https://earlyracefilm.github.io/database/)" digital project.

Discussion Questions:
- What stood out to you from this reading about how "data" can be a useful concept for research questions that might fall broadly under the umbrella of the humanities (or other qualitative disciplines/fields)?
- What stood out to you from this reading about how "data" can be a challenging or less than useful concept for research questions that might fall broadly under the umbrella of the humanities (or other qualitative disciplines/fields)?
- How does the way this reading talks about "data" relate to your own prior experience with different kinds of research/analysis methods? 
- In what ways do you think the way Posner talks and thinks about data would be a useful starting point for engaging with archival materials related to Notre Dame football?
  * To put this another way, what kinds of questions or topics would thinking of primary sources as data allow us to explore or engage with?
- Other questions/observations from this reading

Thinking about the companion digital project that goes along with this reading...
- What can we tell about how the project is thinking about and using data in the way Posner frames it in the reading?
- How do we see the project (and reading) talking about, contextualizing, or framing the way it uses data within the scope of a particular set of research questions/topics?
  * To put this another way, what role does data play in framing the project's scope, goals, questions, etc?
- What types of research questions/topics does the project take up using structured data?
- Other questions/comments/observations from looking at the project

# University Archive Digital Collections

We've previously looked at some of the digital collections in the Notre Dame [University Archives](http://archives.nd.edu/digital).

In the previous lab, we focused on using these source materials as unstructured text for different types of analysis facilitated by digital/computational tools.

In some cases, that analysis did lead to structured data (or data in a spreadsheet-like format). Or the back-end data driving the visualizations and analysis the different tools presented was made possible through analyzing and processing unstructured text to produce or generate structured data.

Discussion Questions:
- In what ways have you seen or engaged with that workflow (unstructured text to structured data) in our first lab?
- How is that similar or different from the ways we see structured data show up in the Posner reading and companion digital project?

Now we're going to think about how we can engage with primary source material with structured data as a starting point for other kinds of analysis and exploration that rely on modes of data analysis/visualization that work with structured data.

Let's take a look at a few different types of primary sources that can lend themselves to working as structured data.

Sample primary sources:
- [1922 Student Directory](https://archives.nd.edu/dir/DIR_1922_1923.pdf)
- [1923 Football Season Review](http://archives.nd.edu/Football/Football-1922s.pdf)

Discussion Questions:
- What can we tell about who created this resource (specific authors as well as publisher)?
- What kinds of information are included in this resource (images, text, etc)?
  * Where do we see opportunities for this information to work as structured data? 
- What topics are covered or addressed in this resource?
- What kinds of research questions or topics could you analyze/explore using this resource?
  * Specifically, if we were able to engage with the information in this resource as structured data, what kinds of analysis/visualization or questions/topics could we explore.
- Other comments/questions/observations that surface as you think about structured data in relation to this primary source.

# Sample Datasets

To get us started in this lab, Prof. Walden has prepared a few sample datasets based on some of these primary sources.

We'll use these datasets as a starting point for our work in this lab, and as a model/starting point for thinking about what you could do on your own with structured data in this lab.

The sample datasets include:
- 1922 Student Directory
- Combined Football Rosters from Sports Reference
- Combined Football Schedules from Sports Reference
- Knute Rockne coaching tree from Wikipedia

## Directories

Take another look at the [1922 Student Directory](https://archives.nd.edu/dir/DIR_1922_1923.pdf).

Discussion Questions:
- Where would you get started transforming this primary source into structured data?
- What would that data structure look like?
  * Specifically, what columns would you have, what data would go in each column, etc.
- What types of analysis/visualization or exploration would you be able to do with this resource as structured data?
- Other comments/questions about this source as structured data

### Directories Data Processing Overview

Prof. Walden will add more details about the data processing workflow for this source.

But for now, big picture steps for this workflow:
- Scrape plain text from the directory using Optical Character Recognition (OCR) in Python
- Clean/wrangle/restructure data using OpenRefine
- More data cleaning/wrangling in OpenRefine (using a lot of regular expressions)

Again, more details to come and we'll talk in-depth about OpenRefine and data cleaning later in this lab.

## Football Rosters

Online sports data provider Sports Reference includes specific college football data resources.

Take a look at [their page for Notre Dame's 1924 team](https://www.sports-reference.com/cfb/schools/notre-dame/1924.html).

Discussion Questions:
- What parts of information on this page would you want to work with as structured data?
- What types of analysis/visualization or exploration would you be able to do with this resource as structured data?
  * What questions or topics would you be able to explore using data from this resource? 
- Other comments/questions about this source as structured data

### Football Rosters Data Processing Overview

Prof. Walden has built out a Jupyter Notebook that scrapes the rosters into a combined CSV file in Python.
- [GitHub]
- [NBViewer]
- [Google CoLab]

But for now, big picture steps for this workflow:
- Scrape HTML tables in Python using BeautifulSoup
- Clean/wrangle/restructure data in Python as a Pandas DataFrame
- Write data to CSV file

## Football Schedules

Sports Reference's college football resources also include information on Notre Dame football's schedules and season results.

Take a look at [their page for Notre Dame's 1924 season](https://www.sports-reference.com/cfb/schools/notre-dame/1924-schedule.html).

Discussion Questions:
- What parts of information on this page would you want to work with as structured data?
- What types of analysis/visualization or exploration would you be able to do with this resource as structured data?
  * What questions or topics would you be able to explore using data from this resource? 
- Other comments/questions about this source as structured data

### Football Schedules Data Processing Overview 

Prof. Walden has built out a Jupyter Notebook that scrapes the rosters into a combined CSV file in Python.
- [GitHub]
- [NBViewer]
- [Google CoLab]

But for now, big picture steps for this workflow:
- Scrape HTML tables in Python using BeautifulSoup
- Clean/wrangle/restructure data in Python as a Pandas DataFrame
- Write data to CSV file

## Knute Rockne Coaching Tree

We'll also think in this lab about how structured data can be the starting point for looking at networks and relationships, under the umbrella of network analysis.

The idea of a "coaching tree" 

https://my.nd.edu/news/9551

https://en.wikipedia.org/wiki/Knute_Rockne#Coaching_tree

https://www.researchgate.net/publication/228968729_The_NFL_Coaching_Network_Analysis_of_the_Social_Network_Among_Professional_Football_Coaches

### Rockne Coaching Tree Data Processing Overview

## Things to Take Away From This Section

Develping a data model is hard

Developing a data model takes time

Reproducability and version control are your friends

In the words of Tim Gunn, make it work.

When you start doing this on your own, we'll talk in more detail about tools/workflows/strategies/etc.

# Exploratory Data Visualization

## DataBasic

### WTFcsv

## Excel

## Tableau

## Python

## RStudio

# Mapping

## Palladio

## ArcGIS Online

## Python

## RStudio

# Networks

## DataBasic: Connect The Dotes

## Palladio

## Gephi

## Python

# Next Steps (aka, now it's your turn!)

## Collaborating Well

## Where to Start: Articulating a Research Question/Topic and Developing a Data Model

## Data (Pre)Processing

### OpenRefine

### Excel

### Python

### RStudio

### Command Line (regular expressions)

## Data Analysis/Visualization

List of tools:
- Static 2D visualizations
  * WTFcsv
  * Excel
  * Python (`matplotlib`)
  * RStudio (`ggplot2`)
- Interactive 2D visualizations
  * Tableau
  * Python (`plotly`)
  * RStudio (`ggplotly`)
- Mapping
  * Static
    * ArcMap/ArcPro
    * QGIS
    * Python (`matplotlib`)
    * RStudio (`ggplot2`)
  * Interactive
    * Google MyMaps
    * ArcGIS Online
    * Palladio
    * Python (`plotly`)
    * RStudio (`plotly` and `leaflet`)
    * `Leaflet` also has a JavaScript instantiation
- Networks
  * Static
    * Gephi
    * Python
  * Interactive
    * Palladio
    * Python (`networkx` and `pyvis`)

## Addressing Your Research Questions

# Lab Notebook Components
