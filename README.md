# Lab #2: Structured Data

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Overview

This lab will involve using data analysis and visualization methods to interact with digitized football-related material from the University Archives as structured data. The project will include opportunities to develop a data model/structure, use manual or computational methods to map information from primary sources to a data structure, and conduct exploratory data analysis/visualization (using coding and no-coding tools/methods). This lab will focus on methods for working with structured data. 

# Table of Contents

- [Background](#background)
- [University Archive Digital Collections](#university-archive-digital-collections)
- [Sample Datasets](#sample-datasets)
  * [Directories](#directories)
  * [Football Rosters](#football-rosters)
  * [Football Schedules](#football-schedules)
  * [Knute Rockne Coaching Tree](#knute-rockne-coaching-tree)
  * [Things to Take Away From This Section](#things-to-take-away-from-this-section)
- [Exploratory Data Visualization](#exploratory-data-visualization)
  * [DataBasic: WTFcsv](#databasic-wtfcsv)
  * [Excel](#excel)
  * [Tableau](#tableau)
  * [Python](#python)
  * [RStudio](#rstudio)
- [Mapping](#mapping)
  * [Google MyMaps](#google-mymaps) 
  * [ArcGIS Online](#arcgis-online)
  * [Carto](#carto)
  * [Mapping in Python](#mapping-in-python)
  * [Mapping in RStudio](#mapping-in-rstudio)
  * [Other Mapping Tools/Resources](#other-mapping-toolsresources)
    * [ArcGIS StoryMaps and Web App Builder](#arcgis-storymaps-and-web-app-builder)
    * [ArcMap](#arcmap)
    * [QGIS](#qgis)
- [Networks](#networks)
  * [DataBasic: Connect The Dots](#databasic-connect-the-dots)
  * [Palladio](#palladio)
  * [Gephi](#gephi)
  * [Other Network Tools/Resources](#other-network-tools-resources)
- [Next Steps (aka, now it's your turn!)](#next-steps-aka-now-its-your-turn)
  * [Collaborating Well](#collaborating-well)
  * [Where to Start: Articulating a Research Question/Topic and Developing a Data Model](#where-to-start-articulating-a-research-question-topic-and-developing-a-data-model)
  * [Data (Pre)Processing](#data-preprocessing)
    * [OpenRefine](#openrefine)
    * [Excel](#data-cleaning-in-excel)
    * [Python](#data-cleaning-in-python)
    * [RStudio](#data-cleaning-in-rstudio)
    * [Command Line (regular expressions)](#command-line-regular-expressions)
  * [Tool Directory](#tool-directory)
  * [Addressing Your Research Questions](#addressing-your-research-questions)
- [Lab Notebook Components](#lab-notebook-components)
- [Acknowledgements](#acknowledgements) 

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
- [1922 Student Directory](#directories)
- [Combined Football Rosters from Sports Reference](#football-rosters)
- [Combined Football Schedules from Sports Reference](#football-schedules)
- [Knute Rockne coaching tree from Wikipedia](#knute-rockne-coaching-tree)

<blockquote> What is a CSV? <br>&nbspA comma-separated value file (CSV) is a structured tabular data format in which column values are separated by a comma. Computer programs like Microsoft Excel parse those values and display the underlying data in a spreadsheet format. Saving tabular data as a CSV file type avoids much of the additional formatting added by programs like Microsoft Excel. </blockquote>

## Directories

Take another look at the [1922 Student Directory](https://archives.nd.edu/dir/DIR_1922_1923.pdf).

Discussion Questions:
- Where would you get started transforming this primary source into structured data?
- What would that data structure look like?
  * Specifically, what columns would you have, what data would go in each column, etc.
- What types of analysis/visualization or exploration would you be able to do with this resource as structured data?
- Other comments/questions about this source as structured data

### Directories Data Processing Overview

Let's take a look at one way of transforming the directory into structured data.

- Initial OCR output (`DIR_1922_1923.txt`)
  * [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/DIR_1922_1923.txt)
  * [Google Drive](https://drive.google.com/file/d/1u7lk7WAFCU_CCUMqW83ANyN00tFEiRr-/view?usp=sharing)
- First iteration of OpenRefine output (`ND_Directory_Raw.csv`)
  * [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/ND_Directory_Raw.csv)
  * [Google Drive](https://drive.google.com/file/d/1BRi8A6O_TFm2Y_Mt7Ek2y4rQLnIMnYa4/view?usp=sharing)
- Second iteration of OpenRefine output (`ND_Directory_Cleaned.csv`)
  * [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/ND_Directory_Cleaned.csv)
  * [Google Drive](https://drive.google.com/file/d/1cuF_hhyh3QfwkevHlXX2YGkLaxbayjuG/view?usp=sharing)
- Excel output with merged geographic data (`ND_Directory_Cleaned_Geography.csv`)
  * [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/ND_Directory_Cleaned_Geography.csv)
  * [Google Drive](https://drive.google.com/file/d/1x35ml-UUykUnMUXUjtI3VjTvHMT3UCS7/view?usp=sharing)

Big picture steps for this workflow:
- Scrape plain text from the directory using Optical Character Recognition (OCR) in Python
- Clean/wrangle/restructure data using OpenRefine
- More data cleaning/wrangling in OpenRefine (using a lot of regular expressions)
- Data wrangling in Excel to incorporate latitude/longitude information for mapping

Jupyter Notebook for OCR:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/directories-ocr-workflow.ipynb)
- [Google CoLab](https://drive.google.com/file/d/16K9-5dcEqkKXqxuJ_lo5kNEIx8mkFBP4/view?usp=sharing)
- [NBviewer](https://nbviewer.jupyter.org/github/kwaldenphd/football-structured-data/blob/main/notebooks/directories-ocr-workflow.ipynb)

We'll talk in-depth about OpenRefine and data cleaning later in this lab.

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
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/sf-nd-football-rosters.ipynb)
- [NBViewer](https://nbviewer.jupyter.org/github/kwaldenphd/football-structured-data/blob/main/notebooks/sf-nd-football-rosters.ipynb)
- [Google CoLab](https://drive.google.com/file/d/1u2kKRaZj_S3CRfWu4vF2OZTOcZ8UAPw8/view?usp=sharing)

Data scraping output: `combined_nd_rosters.csv`
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/combined_nd_rosters.csv)
- [Google Drive](https://drive.google.com/file/d/1LpT-mjNxvvmqsDV0pFmFBFvb8PSwJiTj/view?usp=sharing)

Big picture steps for this workflow:
- Scrape HTML tables in Python using BeautifulSoup
- Clean/wrangle/restructure data in Python as a Pandas DataFrame
- Write data to CSV file

Eventually, we'll explore how we can get geographic information for these rosters by connecting the rosters with student directories.

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
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/sf-nd-schedules.ipynb)
- [NBViewer](https://nbviewer.jupyter.org/github/kwaldenphd/football-structured-data/blob/main/notebooks/sf-nd-schedules.ipynb)
- [Google CoLab](https://drive.google.com/file/d/175Gf_-SNdwdUrhvyhPRKxApMgSaESx-d/view?usp=sharing)

Data scraping output: `combined_nd_schedules.csv`
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/combined_nd_schedules.csv)
- [Google Drive](https://drive.google.com/file/d/1-P_6693TjcE7QTgpUDlHrOTD1jprztb6/view?usp=sharing)

Excel data wrangling output: `combined_nd_schedules_cleaned.csv`
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/combined_nd_schedules_cleaned.csv)
- [Google Drive](https://drive.google.com/file/d/15U5nNbKX-BfIWO4CTCeabit7mdokf9SV/view?usp=sharing)

Big picture steps for this workflow:
- Scrape HTML tables in Python using BeautifulSoup
- Clean/wrangle/restructure data in Python as a Pandas DataFrame
- Write data to CSV file
- Data wrangling in Excel to incorporate latitude/longitude information for mapping

## Knute Rockne Coaching Tree

We'll also think in this lab about how structured data can be the starting point for looking at networks and relationships, under the umbrella of network analysis.

### What is a network?

According to Miriam Posner, networks are “a finite set (or sets) of actors and the relations defined on them. It consists of three elements: 
- (1) a set of actors;
- (2) each actor has a set of individual attributes; and 
- (3) a set of ties that defines at least one relation among actors.” 
 
A network graph is “a common way to visually represent social networks, consisting of two dimensions: actors and relations (also called nodes and edges). Nodes are the entities in graph (also called vectors)..[edges] are the relationships between nodes.” 

Learn more via the [PDF included in this Repository](https://github.com/kwaldenphd/football-structured-data/blob/main/files/Posner_SocialNetworkAnalysisGlossary.pdf)

### Coaching tree as a type of network

From [Wikipedia](https://en.wikipedia.org/wiki/Coaching_tree):

"A coaching tree is similar to a family tree except that it shows the relationships of coaches instead of family members. There are several ways to define a relationship between two coaches. The most common way to make the distinction is if a coach worked as an assistant on a particular head coach's staff for at least a season then that coach can be counted as being a branch on the head coach's coaching tree. Coaching trees can also show philosophical influence from one head coach to an assistant.

"Coaching trees are common in the National Football League and most coaches in the NFL can trace their lineage back to a certain head coach for whom they previously worked as an assistant."

We can think of a coaching tree as a type of network, where the relationship of coaches in the tree is understood via nodes and edges.

Let's take a look at a couple different representations of Knute Rockne's coaching tree:
- "[Rockne's Coaching Tree](https://my.nd.edu/news/9551)" *Notre Dame, Alumni & Friends* (26 March 2013)
- "[Knute Rockne, Coaching Tree](https://en.wikipedia.org/wiki/Knute_Rockne#Coaching_tree)", *Wikipedia*

Discussion Questions:
- What parts of information on this page would you want to work with as structured data?
- What types of analysis/visualization or exploration would you be able to do with this resource as structured data?
  * What questions or topics would you be able to explore using data from this resource? 
- Other comments/questions about this source as structured data

We'll come back to Rockne's coaching tree and network analysis later in the lab. But as an example of research that uses this approach/method:
- Andrew Fast and David Donald Jensen, "[The NFL Coaching Network: Analysis of the Social Network Among Professional Football Coaches](https://www.researchgate.net/publication/228968729_The_NFL_Coaching_Network_Analysis_of_the_Social_Network_Among_Professional_Football_Coaches)" *American Association for Artificial Intelligence* (2006)

### Rockne Coaching Tree Data Processing Overview

No fancy Jupyter Notebooks for this one. Prof. Walden went through a few iterations of how to organize and structure the Rockne coaching tree facilitate network analysis.

The `Rockne_Coaching_Tree` Excel workbook documents this iterative process:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Rockne_Coaching_Tree.xlsx)
- [Google Drive](https://docs.google.com/spreadsheets/d/1B2RaD_qtrQaupo6FznKzuAMnYCGt6eEJJ-aAcU9z8I4/edit?usp=sharing)

The first step was to take the information on Wikipedia and map it onto a tabular data structure that would move in the direction of having nodes, edges, and weights.

The `Original_Coaching_Tree.csv` file reflects this preliminary structure.
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Rockne_Coaching_Tree_Full.csv)
- [Google Drive](https://docs.google.com/spreadsheets/d/1B2RaD_qtrQaupo6FznKzuAMnYCGt6eEJJ-aAcU9z8I4/edit?usp=sharing)

The preliminary structure included the following columns:
- `Name` (player/coach name)
- `Played_Under` (Rockne)
- `Years_Played` (years playing at ND)
- `ND_No_Years` (total number of years played at ND)
- `Next_Inst` (institution person coached at next)
- `Years_Next_Inst` (years at next institution)
- `Coach_No_Years` (total nubmer of years coaching at next institution)
- `Coach_Rk` (coaching rank, head coach or associate)

The most straightforward way to represent this data as a network is to have `source` and `target` nodes, in which Rockne is the source and the person who played/coached for him is the target. 

The `Simplified_Coaching_Tree_CTD.csv` file reflects this `source-target` structure:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Simplified_Coaching_Tree_CTD.csv)
- [Google Drive](https://drive.google.com/file/d/1AvPk8sKYhlsCz6RjUTzkSyxxULX_Wf2U/view?usp=sharing)

We can also include the other institutions these individuals played at as source nodes.

The `Alternate_Simplified_Coaching_Tree_CTD.csv` file reflects this expanded `source-target` structure:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Alternate_Simplified_Coaching_Tree_CTD.csv)
- [Google Drive](https://drive.google.com/file/d/1OTel7xqn2yxx9fzDFWPQkdwR67oP-pJc/view?usp=sharing)

But the simplified `source-target` structure doesn't account for aspects of these relationships like how many years someone played at ND, or how many years they coached at subsequent institutions.

We can use the concept of weighted edges to incorporate these other pieces of data.

One way to incorporate weighted edges is to use the number of years someone played at ND or coached elsewhere as the weight.

The `Full_Coaching_Tree_Edges.csv` file reflects this weighted edge structure.
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Full_Coaching_Tree_Edges.csv)
- [Google Drive](https://drive.google.com/file/d/1NK3JPimaISPy8NCifrCSSV7w8ZMtCOYO/view?usp=sharing)

When Rockne is the `source` node, the weight is the number of seasons the `target` individual played under him at ND.

When an institution or team is the `source` node, the weight is the number of seasons the `target` individual coached at this program.

## Things to Take Away From This Section

**Develping a data model takes time (and is sometimes hard/messy).**
- Don't overlook the conceptual work needed to figure out the desired endpoint or structure for data from a primary source.
- Thinking through what data structure or format you want/need for the types of analysis and visualization you want to do helps you make choices about next steps for data scraping/cleaning/wrangling.
- And as you go through those data processing steps, you are able to keep in mind what the endpoint is, or what you want/need the data to look like at the end of these processes.

**Reproducability and version control are your friends.**
- You could fire up a Google Sheet or Excel File and hack away at manually entering values from a digitized student directory, Sports Reference web page, etc.
- And sometimes, when you're dealing with data that has a very limited scope and you're not totally sure what the endpoint is going to be in terms of structure, hacking away at the process makes sense.
- *See also: how Prof. Walden approached the Knute Rockne coaching tree data*
- But when we're talking about 100+ years of data on Sports Reference, dozens of student directories, etc., data processing approaches that are reproducible and automated are your friend.
  * Taking the example of Sports Reference web pages, this approach means you just have to figure out one page and then iterate over the other pages that have the same format/structure.
  * Or for student directories, you'll figure out what steps need to happen for cleaning/wrangling each document.
- Data cleaning with tools like OpenRefine, Python, and RStudio lends itself to having reproducible workflows with some level of version control built in

**But also, in the words of Tim Gunn, the goal at the end of the day is to make it work.**
- If trying to make something happen with Python/RStudio is proving to be incredibly time-intensive, and an Excel pivot table or PowerQuery gets you where you need to go, that's absolutely fine. 
- Prioritize reproducability and version control when and where possible, but don't let perfect be the enemy of getting something you can work with.
- When you start doing this on your own, we'll talk in more detail about tools/workflows/strategies/etc. for the materials you're working with and the topics/questions you want to explore.

# Exploratory Data Visualization

From [Wikipedia](https://en.wikipedia.org/wiki/Exploratory_data_analysis): "In statistics, exploratory data analysis is an approach of analyzing data sets to summarize their main characteristics, often using statistical graphics and other data visualization methods...EDA is for seeing what the data can tell us beyond the formal modeling or hypothesis testing task."

To think about this another way, "the purpose of EDA is to use summary statistics and visualizations to better understand data, and find clues about the tendencies of the data, its quality and to formulate assumptions and the hypothesis of our analysis" (Andrew Andrade and Lukasz Golab, ["Exploratory Data Analysis"](https://datascienceguide.github.io/exploratory-data-analysis) *Data Science Guide*)

- [Data](#data)
- [DataBasic: WTFcsv](#databasic-wtfcsv)
- [Excel](#excel)
  * [Getting Data Into Excel](#getting-data-into-excel)
  * [Analyzing Data in Excel](#analyzing-data-in-excel)
  * [Creating a Table](#creating-a-table)
  * [Data Visualization](#data-visualization)
  * [PivotTables and PivotCharts](#pivottables-and-pivotcharts) 
  * [PowerQuery](#powerquery)
- [Tableau](#tableau)
  * [Uploading to Tableau Public](#uploading-to-tableau-public)
  * [Discussion and Reflection Questions](#discussion-and-reflection-questions)
- [Python](#python)
- [RStudio](#rstudio)

## Data

We'll be using three sample datasets in the Exploratory Data Analysis section of the lab.

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

`combined_nd_rosters.csv` represents a data structure scraped from Sports Reference's Notre Dame college football season roster pages. Fields in the dataset include:
- `Rk` (player rank on team at end of season)
- `Season` (season)
- `Player` (combined player name field)
- `First_Name` (player first name)
- `Last_Name` (player last name)
- `G` (number of games)
- `RushingAtt` (number of rushing yards attempted)
- `RushingYds` (number of actual rushing yards)
- `RushingAvg` (average number of rushing yards per attempt)
- `RushingTD` (number of rushing touchdowns)
- `ReceivingRec` (number of receiving receptions)
-  `ReceivingYds` (number of receiving yards)
-  `ReceivingAvg` (average number of receiving yards per reception)
-  `ReceivingTD` (number of receiving touchdowns)
-  `ScrimmagePlays` (number of plays from scrimmage, rush attempts + receptions)
-  `ScrimmageYds` (number of scrimmage yards, rushing + receiving yards)
-  `ScrimmageAvg` (average number of yards from scrimmage per play)
-  `ScrimmageTD` (number of touchdowns from scrimmage, receiving + rushing touchdowns)

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

## DataBasic: WTFcsv

According to [its website,](https://databasic.io) “DataBasic is a suite of easy-to-use web tools for beginners that introduce concepts of working with data. These simple tools make it easy to work with data in fun ways, so you can learn how to find great stories to tell.” DataBasic is developed and supported by MIT’s [Center for Civic Media](https://civic.mit.edu/) and Emerson College’s [Engagement Lab.](https://elab.emerson.edu/)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_1.jpg?raw=true" alt="Capture" /></p>

Navigate to https://databasic.io/ in a web browser (preferably Chrome). 

Click on the `WTFcsv` icon to open the WTFcsv tool.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_1.png?raw=true" alt="Capture" /></p>

As described on the page, "WTFcsv tells you WTF is going on with your .csv file. Data arrives at your doorstep in the form of a spreadsheet but how do you find a story in rows and columns? WTFcsv provides the first step by characterizing each column's data type and contents so that you can ask more questions."

`WTFcsv` gives you the option to use a sample file or upload your own file.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_2.png?raw=true" alt="Capture" /></p>

Click on the `Upload a file` icon and select a sample dataset.

The lab procedure is going to used the `combined_nd_schedules_cleaned.csv` file, but you can use any of the sample datasets as we move through this section of the lab.

Click `Analyze` to analyze the dataset.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_3.png?raw=true" alt="Capture" /></p>

The WTFcsv results include summary information about the entire dataset as well as a summary view of each field.

For the whole dataset, we can tell the number of rows and columns.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_4.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_5.png?raw=true" alt="Capture" /></p>

For each column, we can see the data type (the icon in the top-left corner of that column's tile), a summary visualization for that column (the default tile view), and additional metadata for that column (available by clicking on the circle `i` icon in the top-right corner of the tile).

<blockquote>What is metadata? In the words of information and infrastructure scholar Janet Evans, metadata is "data about data" (Evans, <a href="https://inventingthemedium.com/glossary/">Inventing the Medium: Principles of Interaction Design as a Cultural Practice</a>, glossary). Within WTFcsv, metadata is described as "[summarizing] basic information about your data."</blockquote>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_5.png?raw=true" alt="Capture" /></p>

Looking at the column visualization for `Day`, we can see this is a string field (circle icon in the top-left), and WTFcsv has given us a bar chart showing the counts for each unique column value.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_6.png?raw=true" alt="Capture" /></p>

Looking at metadata for `Day` column tile (click the circle `i` icon in the top-right of the tile), we can see this is a string field (a field that includes text characters), the maximum string length, the number of unique values, and the number of entries for the most frequently occurring values.

We can go back to the column visualization by clicking on the chart icon in the top-right of the tile.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_4.png?raw=true" alt="Capture" /></p>

We can look at the column visualization for `Time` and see it is a time field (clock icon in the top-left), and WTFcsv has given us a line plot showing the number of rows for each time value.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_7.png?raw=true" alt="Capture" /></p>

We can look at the metadata for the `Time` column (click the circle `i` icon in the top-right of the tile) and see the smallest and largest values in this field, as well as the number of rows with missing data (or `NA` values) and the number of unique values.

Continue exploring the results for the sample dataset you uploaded. 

Or, upload and explore another sample dataset.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_8.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_9.png?raw=true" alt="Capture" /></p>

You can also click on the arrow icon next to the page title to get a temporary link to share your results.

This tool does not include an image export option for specific visualizations- screenshots are your best option for capturing these visuals.

### WTFcsv Discussion and Reflection Questions

- What do you notice about the results for this dataset (or these datasets) displayed in WTFcsv?
- How does the tool's results shape your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis tools/approaches highlighted in the tool?
- Other comments/questions/observations

## Excel

Microsoft Excel is a proprietary spreadsheet program that is part of the Microsoft Office (or Office365) suite of tools/programs.

The Microsoft Office suite is available via campus computers and the virtual computer lab.
- [Campus Computer Labs](https://inside.nd.edu/task/all/computerlabs)
- [Virtual Computer Lab](https://inside.nd.edu/task/all/virtual-computer-lab)

OIT also provides [free access to the Office suite through Office365](https://inside.nd.edu/task/all/office-365-portal), which includes an option to download and install on your local machine.

A few notes:
- This tutorial is written on a Windows computer. Mac users will see slightly different menu options in Excel.
- Images and screenshots included in this tutorial are from a sample dataset and do not reflect what you will see working with different data.
- If you do not have Microsoft Excel, some of the tasks we're exploring in Excel (arithmetic operations on a field, generating visualizations, etc) can be accomplished via Google Sheets.
  * However the Pivot Chart, Power Pivot, and Power Query functionality is not available within Google Sheets.

### Getting Data Into Microsoft Excel

The sample datasets provided for this lab are in a `CSV` (comma-separated values) plain-text format.

The operations we are going to explore in Excel require using a workbook file format, rather than a single `CSV` table or sheet.

The goal is to end up with an Excel workbook (or Google Sheets project) that includes the three sample datasets we're using in this section of the lab.

One option is to open a blank Excel workbook, save it with a descriptive file name, and import each CSV.
- HESA, "[Importing `*.csv` formatted data into Excel](https://www.hesa.ac.uk/support/user-guides/import-csv)"

We can also download an Excel workbook that already has these CSV files loaded into a single workbook.
- [Download from GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Football_Lab2_Combined_Workbook.xlsx)
- [Download from Google Drive](https://docs.google.com/spreadsheets/d/12LogN6lkr5yfG3tbs9SAdOO6YvuYqP0CkQVkHqQwONQ/edit?usp=sharing)
  * Click `File` --> `Download` --> `Microsoft Excel (.xlsx)`

If you're working in Google Sheets, you can [make a copy of the Google Sheet project](https://docs.google.com/spreadsheets/d/12LogN6lkr5yfG3tbs9SAdOO6YvuYqP0CkQVkHqQwONQ/copy).

You can also import each CSV file to a new Google Sheets project.
- `File` --> `Import`
- Upload file from your computer or select CSV file in Google Drive
- Select `Comma` as the delimiter
  * Google Docs Help Center, "[Import data sets & spreadsheets](https://support.google.com/docs/answer/40608?hl=en&co=GENIE.Platform%3DDesktop)* 

### Analyzing Data in Microsoft Excel

We can use Excel's `AutoSum` tool to calculate preliminary arithmetic operations on data in our workbook.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_1.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_1.png?raw=true" alt="" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_1a.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_1a.png?raw=true" alt="" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_1aa.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_1aa.png?raw=true" alt="" /></a></p>

Identify a numeric column in one of the workbook sheets.

Use your cursor to select the values in that column.

Click the `AutoSum` icon.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_1b.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_1b.png?raw=true" alt="" /></a></p>

Excel has calculated the sum of the values in your selected cells. The result is printed below your selected values.

The AutoSum function defaults to calculating the sum of selected cells, but it can also perform other mathematical calculations.

For folks working in Google Sheets, the `Functions` icon is in the menu bar, next to the filter and language icons. The drop-down list includes many of the same arithmetic operations covered with the AutoSum tool in Excel.

### Creating a Table

Let's say we want to be able to interact with our dataset by sorting, filtering, etc.

This can be useful for data wrangling/cleaning, or summarizing operations.

Within Excel, we can access these operations by creating a `Table` from our data.

Before creating a table, remove any AutoSum results or outputs.

Select all the cells in your table that include data.
- An easy way to do this is to select the top-left cell, use `Control-Shift-Right Arrow` (PC users) or `Command-Shift-Right Arrow` (Mac users) to select all columns with data and `Control-Shift-Down Arrow` (PC users) or `Command-Shift-Down Arrow` (Mac users) to select all rows with data.

Once you have selected the entire table, click the `Insert` menu option (next to `File`, `Home`, etc) and click the `Table` icon.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_10.png?raw=true" alt="Capture" /></p>

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_3.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_3.png?raw=true" alt="" /></a></p>

Excel has already determined your selection is the data source for the table.

Be sure to the `My table has headers` box is selected.

Click `OK` to create the table.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_20.png?raw=true" alt="Capture" /></p>

Once you've created the table, go to the `Table Design` tab and rename the table.

We also want to add the table to our data model.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_21.png?raw=true" alt="Capture" /></p>

Select the `Power Pivot` menu option (next to `Table Design`).

Click the `Add to Data Model` icon.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_22.png?raw=true" alt="Capture" /></p>

In the pop-up Power Pivot window, select `File` --> `Close` to add the table to the data model.

Go through this process of creating a table (under `Data`), renaming the table (under `Table Design`), and adding the table to the data model (under `Power Pivot`) for each sheet in the workbook.

Renaming tables and adding them to the data model is an important step down the line when we want to start aggregating the data for more fine-tuned analysis and visualization.

For folks working in Google Sheets, there is not an equivalent for this step. Google Sheets already treats your spreadsheet as a table.

BUT, before you start sorting/filtering/etc, you probably want to freeze the first row in the spreadsheet as a column header.
- `View` -- `Freeze` -- `1 row`

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_4.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_4.png?raw=true" alt="" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_5a.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_5a.png?raw=true" alt="" /></a></p>

Formatting your data as a table in Excel allows you to sort values within specific columns, and filter the values that display in your table.

You can access these tools by clicking the arrow drop-down icon in the first row for each column (in the cell with the column header).

For folks working in Google Sheets, many of these same tools are under the `Data` dropdown menu.

Explore some of the searching, sorting, and filtering operations.

#### Discussion and Reflection Questions

- How do the AutoSum calculations impact or inform your understanding of the data?
- What questions do you have about the data or calculations?
- Why would it be helpful to be able to sort/filter/etc within a dataset?
- As you explore the sort/search/filter functionality, what questions emerge about the data?
- Other comments/questions/observations

### Data Visualization with Microsoft Excel

Excel includes a range of built-in chart types that you can use to generate visualizations for data in your table.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_11.png?raw=true" alt="Capture" /></p>

Click on the `Recommended Charts` icon under `Data`.

Explore the different options Excel recommends for visualizing your data.

Click on `OK` in the `Insert Chart` pop-up window to insert a chart to your workbook sheet.

You can also click on a specific chart type in the `Charts` menu area to build your own visualizations.

For folks working in Google Sheets:
- Google Docs Help Center, "[Types of charts & graphs in Google Sheets](https://support.google.com/docs/answer/190718?hl=en)"
- Google Docs Help Center, "[Add & edit a chart or graph](https://support.google.com/docs/answer/63824?hl=en&co=GENIE.Platform%3DDesktop)"

#### Discussion and Reflection Questions

What types of visualizations were you able to generate in Excel using PivotChart? How could those visualizations shape or impact your understanding of the data? Did you generate any visualizations that were confusing or misleading? Alternatively, did you generate any visualizations that were unexpected or illuminating?

### PivotTables and PivotCharts

From [Wikipedia](https://en.wikipedia.org/wiki/Pivot_table):

"A pivot table is a table of grouped values that aggregates the individual items of a more extensive table within one or more discrete categories. This summary might include sums, averages, or other statistics, which the pivot table groups together using a chosen aggregation function applied to the grouped values."

Within Excel, PivotTables (and PivotCharts) let us generate more fine-tuned and customized visualizations for data in the workbook.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_18.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_17.png?raw=true" alt="Capture" /></p>

To create a PivotTable and PivotChart:
- Click on the `PivotChart` dropdown in the `Charts` menu bar area
- Select the `PivotChart & PivotTable` option
- Check that `Use this workbook's Data Model` and `New Worksheet` are selected.
- Click `OK` to create the PivotTable.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_19.png?raw=true" alt="Capture" /></p>

Your data is now formatted as a PivotTable, which allows us to aggregate, analyze, and visualize across different sheets in the workbook.

The steps we took earlier in the lab to name our tables and add them to the data model means we now have a PivotTable and PivotChart that lets us access all three tables for aggregating and visualizing data.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_24.png?raw=true" alt="Capture" /></p>

The PivotChart side bar allows you to select specific data fields and arrange or restructure them to generate visualizations.

You can click on the drop-down arrow next to each table to see a list of its fields (or columns).

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_25.png?raw=true" alt="Capture" /></p>

To show the number of students by major, drag the `Major` field from the `Directory` table into the `Axis (Categories` box.

Then, drag the `Major` field from the `Directory` table into the `Values` box.

The default value and bar chart are showing us the number of students in each major.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_26.png?raw=true" alt="Capture" /></p>

The `Values` box also can calculate other arithmetic values for numeric data fields. You can click on the drop-down arrow next to a field in `Values` and select `Value Field Settings` to see these additional options.

You can right click on various parts of the bar chart to customize colors and labels.

#### Discussion and Reflection Questions

Experiment with other PivotChart functions and other data fields to generate different types of visualizations.

What types of visualizations were you able to generate in Excel using PivotChart? How could those visualizations shape or impact your understanding of the data? Did you generate any visualizations that were confusing or misleading? Alternatively, did you generate any visualizations that were unexpected or illuminating?

### PowerQuery

But one of the things we might want to be able to do with these datasets is connect across them, or generate visualizations that connect across the different discrete datasets.

For example, think about the information that is contained in the directory dataset and the data that is contained in the football roster dataset.

Theoretically, individuals who played on the football team were also students who attended class and majored in particular subjects.

Let's say we wanted to generate visualizations of the home states or majors for individuals playing on the football team.

We would need to connect the roster and directory datasets to be able to access information across both tables.

<blockquote>The larger concept we're talking about here falls under the big umbrella of data models and relational database systems. Those concepts are outside the scope of this class, but for folks who want to learn more about relational databases, entity relationship diagrams, data models, and structured query language (SQL):
 <ul>
  <li>Prof. Walden's <a href="https://github.com/kwaldenphd/data-models">"Introduction to relational database systems and data models" lab</a></li>
  <li>Library Carpentry's <a href="https://librarycarpentry.org/lc-sql/08-database-design/index.html">"Database Design" curriculum</a></li>
  <li>Prof. Walden's <a href="https://github.com/kwaldenphd/sqlite-intro">"SQLite Intro" lab</a></li>
  <li>Prof. Walden's <a href="https://github.com/kwaldenphd/sql-queries-joins">"SQL Queries and Joins" lab</a></li>
  <li>Library Carpentry's <a href="https://librarycarpentry.org/lc-sql/">"SQL" curriculum</a></li>
 </ul>
 </blockquote>

We can connect these two tables using the `Combined_Name` field in the `directory` table and the `Player` field in the `roster` table.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_30.png?raw=true" alt="Capture" /></p>

First, we need to establish query relationships with each of the tables in our workbook.
- Click the `From Table/Range` option (under `Get & Transform Data`, top-left) under the `Data` tab
- In the `Power Query Editor` pop-up window, select `Close & Load`

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_31.png?raw=true" alt="Capture" /></p>

You should now see a `Schedules (2)` sheet that also shows up under `Queries & Connections`.

Do this for each table in the workbook.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_32.png?raw=true" alt="Capture" /></p>

Now, we need to create a new table that merges connecting records from the `rosters` and `directory` tables.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_29.png?raw=true" alt="Capture" /></p>

We can do this by using PowerPivot and PowerQuery to merge connecting records in these fields.
- Click the `Get Data` icon in the `Data` tab
- Hover over `Combine Queries` in the drop-down
- Click `Merge` under `Combine Queries`

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_33.png?raw=true" alt="Capture" /></p>

In the `Merge` pop-up window, select the tables and fields to create this relationship.
- `Player` from `Rosters`
- `Combined_Name` from `Directory`
- `Left Outer` under the `Join Kind` drop-down

Click `OK` to create the relationship.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_34.png?raw=true" alt="Capture" /></p>

Now, we see a new `Merge1` table in the `PowerQuery Editor` window.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_35.png?raw=true" alt="Capture" /></p>

We can rename this table under `Query Settings`.

Now we want to select what columns from the merge will be included in the new table.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_36.png?raw=true" alt="Capture" /></p>

We can click the arrow icons next to the `Directory` column in the new table to expand the list of merged fields.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_37.png?raw=true" alt="Capture" /></p>

We want to select fields from the `Directory` table to merge with the `Rosters` table.

The name fields are duplicated, so we can focus on columns with major and home geographic information.

Click `OK` to merge these columns.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_38.png?raw=true" alt="Capture" /></p>

We can now see the merged columns in our new table.

Click `Close & Load` to save these changes and load the new table to the workbook.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_39.png?raw=true" alt="Capture" /></p>

We can now see a `Merged_Roster_Directory` sheet in our workbook.

We could use this new sheet the connects roster and directory information to aggregate and visualize this data, using the PivotChart tools covered earlier in the lab.

#### Additional Resources

We're just scratching the surface of things you can do in Excel using PowerPivot, PowerQuery, and PivotTables.

Google Sheets has some of the PivotTable functionality, but does not currently support things like PowerPivot and PowerQuery.

For more on PivotTables in Google Sheets:
- Google Docs Help, "[Create & use pivot tables](https://support.google.com/docs/answer/1272900?hl=en&co=GENIE.Platform%3DDesktop)"
- Google Docs Help, "[Create and edit pivot tables](https://support.google.com/a/users/answer/9308944?hl=en)"

For more on data models and queries/joins:
- Microsoft Support, "[Relationships between tables in a Data Model](https://support.microsoft.com/en-us/office/relationships-between-tables-in-a-data-model-533dc2b6-9288-4363-9538-8ea6e469112b)"
- Microsoft Support, "[Create a Data Model in Excel](https://support.microsoft.com/en-us/office/create-a-data-model-in-excel-87e7a54c-87dc-488e-9410-5c75dbcb0f7b)"
- Microsoft Support, "[Merge queries and join tables](https://support.microsoft.com/en-us/office/merge-queries-and-join-tables-cbd17828-7a50-4dc6-9aac-20af4ef6d8a6)"

For more on PivotTables and PivotCharts:
- Microsoft Support, "[Overview of PivotTables and PivotCharts](https://support.microsoft.com/en-us/office/overview-of-pivottables-and-pivotcharts-527c8fa3-02c0-445a-a2db-7794676bce96)"
- Microsoft Support, "[Create a PivotTable to analyze worksheet data](https://support.microsoft.com/en-us/office/create-a-pivottable-to-analyze-worksheet-data-a9a84538-bfe9-40a9-a8e9-f99134456576)"
- Microsoft Support, "[Create a PivotChart](https://support.microsoft.com/en-us/office/create-a-pivotchart-c1b1e057-6990-4c38-b52b-8255538e7b1c)"

For more on PowerPivot and PowerQuery:
- Microsoft Support, "[Get started with Power Pivot in Microsoft Excel](https://support.microsoft.com/en-us/office/create-a-pivotchart-c1b1e057-6990-4c38-b52b-8255538e7b1c)"
- Microsoft Support, "[Power Pivot: Powerful data analysis and data modeling in Excel](https://support.microsoft.com/en-us/office/power-pivot-powerful-data-analysis-and-data-modeling-in-excel-a9c2c6e2-cc49-4976-a7d7-40896795d045)"
- Microsoft Support, "[Learn to use Power Query and Power Pivot in Excel](https://support.microsoft.com/en-us/office/learn-to-use-power-query-and-power-pivot-in-excel-42d895c2-d1d7-41d0-88da-d1ed7ecc102d"
- Microsoft Support, "[Power Pivot- Overview and Learning](https://support.microsoft.com/en-us/office/power-pivot-overview-and-learning-f9001958-7901-4caa-ad80-028a6d2432ed)"
- Microsoft Support, "[Power Query documentation](https://docs.microsoft.com/en-us/power-query/)"

#### Takeaways from all the Excel adventures...

You're probably wondering why we spent so much time working in Excel and exploring some of the more advanced functionality, and that's a fair question.

Folks with computer science/data science backgrounds and programming chops are probably wondering why we would spend so much time figuring out how to do things in a proprietary software program that can be accomplished programmatically in open-source programs like Python, RStudio, and SQL.

A few reasons:
- Google Sheets is a powerful spreadsheet tool, but there's a reason Excel is an industry standard for more organizations/companies that have more advanced data processing workflows and don't necessarily have data scientists/computer scientists/programmers on staff
- Excel integrates with other data processing workflows and visualization tools (specifically PowerBI) to create an incredibly powerful data ecosystem
- So yes, Excel will change, but it's not going anywhere. 
- And to Prof. Walden's knowledge, there's no non-coding spreadsheet program (including Apple Numbers, Google Sheets, open-source Libre Office Calc) that comes in terms of functionality.

Additionally, these Excel workflows can help those without a data science/programming/data engineering/etc background understand some of the core concepts and steps involved in data modeling and database systems.
- This helps immensely when you're in a work setting where you need to be able to talk to or interact with folks working in and around database engineering. Even if you're not the one building or maintaining the workflows, you are much better equipped to have intelligent conversations about what those individuals are doing and what you need these systems to do.

#### Reflection Questions

What types of visualizations were you able to generate in Excel using PivotChart? How could those visualizations shape or impact your understanding of the data? Did you generate any visualizations that were confusing or misleading? Alternatively, did you generate any visualizations that were unexpected or illuminating?

## Tableau

[Tableau](https://www.tableau.com) is a software company founded in Silicon Valley in 2003. Developed by researchers affiliated with Stanford University’s Computer Science Department, Tableau is a commercialized application of academic research. Represented as DATA on the New York Stock Exchange after a 2013 initial public offering, Tableau reported $877 million in revenue in <a href="s1.q4cdn.com/149179428/files/doc_financials/2017/FY2016-Annual-Report.pdf">the 2017 fiscal year</a>. Most often deployed in business environments, Tableau Desktop is a subscription-based data analysis and visualization software. Tableau Server and Tableau Online offer subscription-based web-publishing options for making data and interactive visualizations available on the web. Tableau Public offers limited Tableau Desktop functionality with some options for uploading visualizations through the Tableau Public website.

To get started, you'll need to download the free version of Tableau (Tableau Public) on your personal computer.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_40.png?raw=true" alt="Capture" /></p>

Head to https://public.tableau.com/ in a web browser and enter your email to download the program.

NOTE: Mendoza students in the Business Analytics program have access to Tableau through the [Mendoza virtual computer lab](https://inside.nd.edu/task/all/virtual-computer-lab-mendoza-anaytics).

It's a large program, so be prepared for the installation process to take some time.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true" alt="" /></a></p>

Once the installation has finished, launch the program.

Tableau can connect to a number of different data sources and file types.

You can load single `CSV` files for the sample datasets we're working with in this section of the lab, or you can upload the entire `Football_Lab2_Combined_Workbook` workbook file.
- [Download from GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Football_Lab2_Combined_Workbook.xlsx)
- [Download from Google Drive](https://docs.google.com/spreadsheets/d/12LogN6lkr5yfG3tbs9SAdOO6YvuYqP0CkQVkHqQwONQ/edit?usp=sharing)
  * Click `File` --> `Download` --> `Microsoft Excel (.xlsx)`

NOTE: Images and screenshots included in this tutorial are from a sample dataset and do not reflect what you will see working with different data.

Once you've selected the data you want to load, click `Open` to load the data in Tableau.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_20.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_20.png?raw=true" alt="" /></a></p>

Tableau's Data Source previews the structure of the data we loaded from the Excel file. 

Tableau determines what type of data is contained in each field (integer number values, dates, geographic spatial information, strings of letters or characters, etc.).

If we wanted to analyze or visualize data from multiple tables, Tableau's Data Source offers some functionality for joining tables and building a database structure.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true" alt="" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_20.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_20.png?raw=true" alt="" /></a></p>

Click on the `Sheet 1` icon next to `Data Source` to move into Tableau's visualization builder interface.

Tableau distinguishes between `Dimensions` (data fields that cannot be aggregated) and `Measures` (data fields that can be aggregated--or have mathematical operations performed on them).

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_21.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_21.png?raw=true" alt="" /></a></p>

You can move fields in the dataset to `Columns` and `Rows` to generate aggregate tables.
- This is similar to what we were able to do in Excel using a PivotTable

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_23.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_23.png?raw=true" alt="" /></a></p>

Once you've created an aggregate table for select fields, Tableau may generate a visualization, or the `Show Me` panel on the right-hand side of the window shows other visualization types possible for this data selection.

You can move your cursor over the chart to see the interactive data points.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_41.png?raw=true" alt="Capture" /></p>

Tableau allows chart customization with the `Marks` panel.

You can drag specific fields from `Dimensions` or `Measures` onto elements in the `Marks` panel to customize labels, size, shapes, color, etc.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_42.png?raw=true" alt="Capture" /></p>

The `Show Me` panel on the right-hand side of the Tableau window shows other types of visualizations you can build in Tableau using this combination of data fields and calculations.

### Additional Resources

- Tableau Public, ["How-To Videos and Resources"](https://public.tableau.com/en-us/s/resources)
- Miriam Posner, ["Getting started with Tableau Public"](http://miriamposner.com/classes/dh201w19/tutorials-guides/data-visualization/getting-started-with-tableau-public/) tutorial for Winter 2019 "Digital Humanities 201" class

## Uploading to Tableau Public

One of Tableau's features is that it allows users to upload interactive data visualizations to the web and embed them in websites and other online spaces.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_28.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_28.PNG?raw=true" alt="" /></a></p>

If you have additional time, <a href="https://public.tableau.com/en-us/s/">create a free profile</a> on Tableau Public's website.

Click `File` --> `Save to Tableau Public`, and use your login credentials to save your Tableau workbook to Tableau Public's website.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_29.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_29.PNG?raw=true" alt="" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_30.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_30.PNG?raw=true" alt="" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_31.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_31.PNG?raw=true" alt="" /></a></p>

Your Tableau Public online profile can host your interactive visualizations, and also gives you the option to share, download, and embed the interactive content.

## Python

We can also use a programming language like Python to generate and customize many of the types of visualizations we created using Excel and Tableau.

Prof. Walden has built out a Jupyter notebook that goes into more detail about using Python for exploratory data analysis for the sample datasets presented in this lab.

Since we're dealing with single data files, running things on your personal computer should not cause any problems.

But you can also make copies of the CoLab notebooks and connect to data files within Google Drive.

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

Jupyter Notebook:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.ipynb)
- [NBviewer](https://nbviewer.jupyter.org/github/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.ipynb)
- [Google CoLab](https://drive.google.com/file/d/1MybxGo9ngdm20rzV1xAqAGYZwNsLINTM/view?usp=sharing)

## RStudio

We can also use a scripting language like R/RStudio to generate and customize many of the types of visualizations we created using Excel and Tableau.

Prof. Walden has built out an RMarkdown file that goes into more detail about using R for exploratory data analysis for the sample datasets presented in this lab.

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

RMarkdown File:
- [`.rmd` file on GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.Rmd)
- [`.rmd` file on Google Drive](https://drive.google.com/file/d/1gvhci2x1IVsHOFCEwkeVvm_HSUPU0l2V/view?usp=sharing)
- [RStudio Cloud](https://rstudio.cloud/project/2977118)

RStudio Project:
- [GitHub, `.zip`](https://drive.google.com/file/d/1zex8zotq6TpLtzcDukl0NtH8oxaswBqR/view?usp=sharing)
- [RStudio Cloud](https://rstudio.cloud/project/2977118)

## EDA Discussion and Reflection Questions:

Experiment with other data fields and calculations to generate different types of visualizations. You can add new worksheets or duplicate an existing worksheet to build multiple visualizations.

What types of visualizations were you able to generate in Tableau? How were those visualizations similar or different than what you generated in Excel?

How could those visualizations shape or impact your understanding of the data? Did you generate any visualizations that were confusing or misleading? Alternatively, did you generate any visualizations that were unexpected or illuminating?</blockquote>

- How is the data in Tableau presented or organized differently than the same information in Excel? 
- What similarities or differences do you notice between the two user interfaces for building data visualizations?

# Mapping

Up to this point, we have focused on exploratory data analysis/visualization in a Cartesian Coordinate system, that is data plotted on an `X` (horizontal) and `Y` (vertical) axis.

But for data with geographic or geospatial components, we might want to analyze and visualize those spatial components by mapping the data, or using the data to generate maps that use a `latitude` and `longitude` coordinate system.

The next section of the lab covers a few different tools to get started with visualizing spatial data.

The lab procedure is going to used the `combined_nd_schedules_cleaned.csv` file, but you can use any of the sample datasets that include spatial (latitude/longitude) information.
- Directories
- Roster data merged with directory data (table we generated from the Excel section of the lab)

For most of these mapping tools, we need data that is georeferenced, or data that includes discrete `latitude` and `longitude` coordinates for each location.

There are lots of different ways to approach geocoding data, but a couple of free online geocoding services:
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

All sample datasets for this lab have already been geocoded.

- [Google MyMaps](#google-mymaps)
- [ArcGIS Online](#arcgis-online)
- [Carto](#carto)
- [Mapping in Python](#mapping-in-python)
- [Mapping in RStudio](#mapping-in-rstudio)
- [Mapping Reflection/Discussion Questions](#mapping-reflectiondiscussion-questions)
- [Other Mapping Tools/Resources](#other-mapping-toolsresources)

## Google MyMaps

Google launched [Google My Maps](https://www.google.com/maps/about/mymaps) in 2007 as part of the Google cloud services suite of programs. Through the My Map interface, users with a Google account can map points, lines, and shapes, with additional display customization options. My Maps allows users to generate maps from spreadsheets, work collaboratively on maps, and share interactive maps.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-473" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="332" /></a></p>

Use your ND Google credentials to log into [Google MyMaps](https://www.google.com/maps/).

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-full wp-image-474" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="178" height="55" /></a></p>

Click the `Create New Map` icon in the top left-hand corner.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter size-full wp-image-479" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="407" height="295" /></a></p>

Name the map by clicking on `Untitled map` in the top left-hand corner. 
- `Football Lab Map` is absolutely fine as a name

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-475" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="317" height="308" /></a></p>

Click the blue `Import` icon to start the data import process. 

Select or drop a `.csv` file with latitude/longitude information to upload the dataset.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter size-full wp-image-477" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="504" height="433" /></a></p>

Check that only `Latitude` and `Longitude` are selected before clicking `Continue`. 

My Maps will keep all the original data records but needs to detect which fields contain spatial data.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter size-full wp-image-478" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="509" height="412" /></a></p>

The next screen asks what field you want to use for the place marker titles. 

Select a useful title field and click `Finish`.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-full wp-image-480" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="307" height="286" /></a></p>

Click on the three dots next to the layer to rename the layer with a descriptive name.

Depending on the dataset you're using, you may get a message that select rows could not be drawn on the map.

If you have additional time, you can come back and explore this error message. For now, click `Dismiss`

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter size-full wp-image-481" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="309" height="41" /></a></p>

On the left-hand side of the window is a `Base map` icon that inclues a drop-down menu.

You can explore different available base maps to see what works best with your data. 

For example, My Maps’s default base map includes topographical data. If that data is not essential for our analysis, a simpler base map (like `Simple Atlas`) can help users focus on the most important aspects of the spatial visualization.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_48.png?raw=true" alt="Capture" /></p>

Click on the blue paint roller icon next to the data layer to open a pop-up with style customization options.

The default setting is a uniform style for all map markers.

We want to think about display customization options that are a good fit for the data we're working with.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_43.png?raw=true" alt="Capture" /></p>

We can experiment with grouping points by a particular field, coloring points based on discrete categories or numeric ranges (for numeric fields).
- For example, if you're working with the directory information, you could color points by `Major`.
- Or if you're working with the schedule information, you could color points by `Conf` or `Season`.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_45.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_46.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_47.png?raw=true" alt="Capture" /></p>

Once you have a map display you like, you can download, share, or print, using some of the options highlighted in the screenshots.
- Prof. Walden's sample Google My Map for this lab
  * [Public map](https://www.google.com/maps/d/edit?mid=1CUC36a-kqnX7ljy8Wtebc6lYvfxVZODV&usp=sharing)
  * [My Map project](https://www.google.com/maps/d/edit?mid=1CUC36a-kqnX7ljy8Wtebc6lYvfxVZODV&usp=sharing)

### Discussion and Reflection Questions:

asdfasf as df


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
- [Adding a Georeferenced Historical Map](#adding-a-georeferenced-historical-map)
- [Adding Other Data from ArcGIS Online](#adding-other-data-from-arcgis-online)
- [Saving, Sharing, and Printing Your Map](#saving-sharing-and-printing-your-map)

ArcGIS is an industry-standard tool developed by geographers in the 1970s, from parent company ESRI.

From the [ArcGIS Online "Overview" page](https://www.esri.com/en-us/arcgis/products/arcgis-online/overview): 
- "Build interactive web maps with ArcGIS Online, Esri's web-based mapping software. Gain new perspectives and enhanced details as you interact with data, zoom in, and search on the map. Use smart, data-driven mapping styles and intuitive analysis tools to gain location intelligence. Work effectively across your organization by collaboratively building and using maps. Share your insights with specific people or the entire world."

## Logging in to ArcGIS Online


<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_54.png?raw=true" alt="Capture" /></p>

Open Firefox or Chrome and navigate to https://www.arcgis.com/sharing/rest/oauth2/signup?client_id=arcgisonline&redirect_uri=http://www.arcgis.com&response_type=token in a web brower.

Create a free ArcGIS public account.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_49.png?raw=true" alt="Capture" /></p>

Once you have an account and have logged in, click `Map` in the top-left page menu.

<blockquote>Note: This rest of this tutorial is written using a sample data set. Your data, map, and map layers will look different than the images included in the tutorial.</blockquote>

## Creating a New Map

<p align="center"><img class=" size-full wp-image-59 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="Capture_6"  /></p>

7-You are now in ArcGIS Online’s map builder interface.

<p align="center"><img class=" size-full wp-image-64 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="Capture_11"  /></p>

Click the `Save` icon above the map to save your map.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_50.png?raw=true" alt="Capture" /></p>

Add a title, tags, and summary, and click the blue `Save Map` icon. Provide information that will help you find and identify the map you're creating. 

## Adding Data to Your Map

<p align="center"><img class=" size-full wp-image-60 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_7.png?raw=true" alt="Capture_7"  /></p>

Click on the `Add` icon in the top-left corner of the page, and select `Add Layer from File`.

Click the Browse icon and select one of the lab CSV files that includes geospatial data.

<p align="center"><img class=" size-full wp-image-61 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="Capture_8"  /></p>

Click the blue `Import Layer` icon to add the data to your map.

<p align="center"><img class=" size-full wp-image-62 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="Capture_9" /></p>

Click the blue `Done` icon to finish adding data to your map.

<p align="center"><img class=" size-full wp-image-64 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="Capture_11"  /></p>

Click the `Save` icon above the map to save your map.

## Customizing Your Map

The default setting for ArcGIS Online is to display the locations in your data without any styling or customization. 

Hover your cursor over the data layer to see additional customization options. 

You can use multiple layers to display or highlight different aspects of the data on the map.

### Basemap

<p align="center"><img class=" size-full wp-image-63 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="Capture_10"  /></p>

You can change the background map by click a different option in the `Basemap` dropdown.

### Legend

<p align="center"><img class=" wp-image-66 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="Capture_13" /></p>

If you want to style points by particular fields, click on the `Change Style` icon. 

Choose an element from your data, and explore the drawing style options.

### Point symbol, color, and size

<p align="center"><img class=" size-full wp-image-69 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_16.png?raw=true" alt="Capture_16"  /></p>

<p align="center"><img class=" size-full wp-image-68 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true" alt="Capture_15"  /></p>

Click on the `Change Style` icon, and click the blue `Options` icon to explore options for customizing point symbol, color, size, etc..

### Heatmaps and clustering

<p align="center"><img class=" size-full wp-image-70 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_17.png?raw=true" alt="Capture_17"  /></p>

You can create a Heat Map in the Change Style window.

You can also cluster points using the Cluster Points option in the main map editing window.

### Configuring Popups

<p align="center"><img class=" size-full wp-image-65 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_12.png?raw=true" alt="Capture_12"  /></p>

Hover your cursor over the data layer and click the three dots that appear.

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true" alt="Capture_19"  /></p>

Click on the Configure Pop-up option to select what data fields display in the pop-up window that appears when you click on a map point. You can also reorder these elements.

### Other options

Hover your cursor over the data layer and click the three dots that appear to see additional options for customizing transparency, copying a layer, or naming a layer.

14-Explore display options for this data. One layer does not have to communicate all relevant aspects of the data.

<p align="center"><img class=" size-full wp-image-65 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_12.png?raw=true" alt="Capture_12" /></p>

15-Once you have a layer customized, you can copy that layer to continue exploring other display options without losing the customized layer.

16-Rename layers using descriptive titles to keep them organized.

<p align="center"><img class=" size-full wp-image-64 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="Capture_11"  /></p>

17-Save the Web Map regularly to avoid losing any changes.

## Saving, Sharing, and Printing Your Map

34-Save your map regularly by clicking the Save icon.

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_j.png?raw=true"  /></p>

35-Click the Share icon when you are ready to share your map.

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_k.png?raw=true" /></p>

36-Click the Print icon to generate a static image with your map and legend that you can save as an image or print to a PDF.
- [Prof. Walden's sample map for this lab](https://arcg.is/1n5i1e)

### Additional Resources

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_51.png?raw=true" alt="Capture" /></p>

There's a lot more you can do with ArcGIS Online.

NOTE: Notre Dame provides subscription access to ArcGIS Online. Email Prof. Walden for next steps on being added to the ND enterprise account.

The tutorials on the landing page are a great place to start.

We'll do more with ArcGIS Online in the next lab when we work with digital exhibits. But there are a lot of additional things you can do with ArcGIS Online, especially around bringing interactive maps in conversation with text/media/etc (StoryMaps), or creating interactive dashboards similar to Carto's functionality (ArcGIS Web App Builder).

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
  
## Carto

[Carto](https://carto.com) is a cloud-computing platform released in 2011 by developer Vizzuality. Written in Ruby and Javascript, Carto is designed to allow businesses to analyze and visualize spatial data without prior or detailed technical GIS knowledge. As we’ll learn in another tutorial, GIS programs like ArcGIS are not always intuitive and user-friendly. Carto was designed as an alternative, with a web-hosted option that doesn’t require a local installation, although Carto is available as <a href="https://github.com/CartoDB/CartoDB">open source software</a>. The short version—users can work with Carto in the browser without needing to set up their own server to host the program. The web-based version of Carto is considered a ["freemium"](https://carto.com/pricing) software- free for some types of users with limited web-based functionality with scaled pricing plans for long-term use.

From [Carto](https://carto.com/help/getting-started/student-accounts/): "Students can create a free CARTO account via GitHub’s Student Developer Pack."

[Sign up](https://education.github.com/pack) for a free GitHub Student Developer Pack.

The Developer Pack also gives you discounted or free access to a range of different toolks and resources, including Canva, Digital Ocean, Microsoft Azure, and Carto.

Once you have signed up for the GitHub Student Developer Pack, create a free Carto account.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-461" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="335" /></a></p>

Log in to Carto. If needed, click on `My Dashboard`

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-full wp-image-462" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="424" height="211" /></a></p>

Next to your name in the top menu is a `Maps` icon with a dropdown arrow. 

Select `Your datasets` from the dropdown

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-463" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="381" height="77" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true"><img class="aligncenter size-large wp-image-464" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="" width="676" height="549" /></a></p>

Click the `New Dataset` icon in the upper right-hand corner of the page.

Select one of the `CSV` files for this lab that includes geospatial data, or drag and drop it into the upload section of the page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter size-full wp-image-465" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="273" height="98" /></a></p>

10-Click the `Connect Dataset` blue icon in the bottom right-hand corner of the page to upload the dataset to Carto.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter size-large wp-image-466" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="676" height="329" /></a></p>

Once your data has been added to Carto, compare how the data was structured in Excel or Tableau versus how it is structured and described in Carto. 
- What similarities do you notice? What has changed? Why do you think Carto made these changes or added this additional information?

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter size-full wp-image-467" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="181" height="78" /></a></p>

Click the blue `Create Map` icon in the bottom right-hand corner of the page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-large wp-image-468" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="676" height="331" /></a></p>

Once you’ve created a map, you move into Carto’s `builder environment`. Use the four-step tour to learn more about Carto’s map editing page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true"><img class="aligncenter size-full wp-image-450" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="" width="347" height="398" /></a></p>

Rename the map by clicking on the three vertical dots next to the data file name.

Click `Rename` to add a descriptive title. You can also rename the map by double-clicking the title.

Let’s explore the map editing page. 
- Use the plus or minus symbols in the bottom left-hand corner of the map to zoom in and out on the map. 
- Double-clicking an area or using your mouse scroll wheel are also ways to zoom in and out.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter size-full wp-image-471" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="324" height="307" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true"><img class="aligncenter size-full wp-image-449" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true" alt="" width="346" height="947" /></a></p>

Click on any map point and click on the small light blue pencil icon that appears. 

Clicking this editing icon shows you that point’s attributes, such as its latitude, longitude, and other descriptive information. 
- If needed, you could edit point data on this screen.

To exit looking at data points, click the `Back` arrow in the top left-hand corner of the page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter size-full wp-image-470" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="306" height="287" /></a></p>

Although we are only working with one data layer in this tutorial, many mapping projects work with multiple layers so naming data layers is a useful practice. 

To rename the data layer:
- Click on the three vertical dots next to the dataset’s title. 
- Click `rename` and enter an appropriate descriptive name for the data set. 
- You can also rename the data set by double-clicking the title.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true"><img class="aligncenter size-full wp-image-451" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true" alt="" width="347" height="946" /></a></p>

Click on the data layer to move into Carto’s layer editing environment.

Another brief tour can help you navigate the layer pane, which includes a menu with `Data`, `Analysis`, `Style`, `Pop-Up`, and `Legend` options.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true"><img class="aligncenter size-full wp-image-452" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true" alt="" width="332" height="222" /></a></p>

Select `Style` from the layer menu.

`Aggregation` offers different ways to visualize your data points on the map, from the default circular points to hexagons to heat maps and time animations. 
- What types of aggregation are most effective for this data set? 
- What types of aggregation do not work for this data set? 
- What aspects of the data are highlighted in different aggregations?

The second option in the `Style` menu allows you to change the size and color of your data points. 

In Carto’s default settings, point size and color is standardized across all data points.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true"><img class="aligncenter size-full wp-image-453" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true" alt="" width="325" height="240" /></a></p>

Under `Point Size`, switch the selection from `Fixed` to `By value` to size points by a numeric data field.

Sizing points by value selects a data field and sizes points based on how frequently they appear in the dataset.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_17.PNG?raw=true"><img class="aligncenter size-full wp-image-454" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_17.PNG?raw=true" alt="" width="379" height="334" /></a></p>

When sizing points by value, you can customize how many buckets (categories) you want to have, as well as how the distribution of those buckets is calculated. 

Carto’s default setting uses Quantiles to calculate bucket distribution, but you can select other ways to calculate those ranges.

Discussion questions:
- What happens when you change the number of buckets, min/max values, or the way bucket distribution is calculated?
- What impact do these choices have on the way your data is represented on the map?
- What factors would you need to consider when making these choices to represent, analyze, and visualize data?

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true"><img class="aligncenter size-full wp-image-453" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true" alt="" width="325" height="240" /></a></p>

In addition to sizing points by value, we can also assign colors to points based on their value. 
- Switch the `Point Size` selection back to `Fixed`
- Switch the `Point Color` selection from `Solid` to `By Value`
- Select a data field (numeric or string) to use for point color

As with `Point Size`, Carto lets you select your number of buckets and how those bucket ranges are calculated. 

You can use one of Carto’s preset color palettes or build your own custom color set using a free online resource like [Color Brewer](http://colorbrewer2.org). 

Carto also gives you the option to change the size of your points (`point size`), the size of your point outline (`point stroke`) and the color of your point outline (`stroke color`).

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true"><img class="aligncenter size-full wp-image-456" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true" alt="" width="344" height="826" /></a></p>

Select the `Pop-Up` icon in the layer menu. 

Pop-Ups include data that displays when you click on a specific map point. In Carto’s default settings, no customized pop-ups appear.

Select `Click` to design the pop-up that appears when you click on a map point. 

Select `Hover` to design the pop-up that appears when you hover over a map point.

For `Click` and `Hover`, Carto lets you to determine the size and coloring of the pop-up window, as well as what data fields are displayed (and how they are labeled).

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_20.PNG?raw=true"><img class="aligncenter size-full wp-image-457" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_20.PNG?raw=true" alt="" width="497" height="837" /></a></p>

If you wanted to further customize your pop-ups, Carto provides an `HTML view` where you could further customize the style of text in your pop-ups.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-large wp-image-468" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="676" height="331" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_21.PNG?raw=true"><img class="aligncenter size-full wp-image-458" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_21.PNG?raw-true" alt="" width="111" height="62" /></a></p>

Once you are satisfied with the styling of your pop-ups, click the `back` arrow to return to the main editing page. 

Because Carto is a cloud-based service, it is saving edits as you make them. 

However, the map project will not be published or shared until you click the `Publish` blue rectangular icon on the bottom left-hand side of the page.
- [Prof. Walden's sample map for this lab](https://kwalden.carto.com/builder/be217bb8-46f4-47a1-83dc-96ccd200e175/embed)

### Additional Resources

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_22.PNG?raw=true"><img class="size-full wp-image-459 aligncenter" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_22.PNG?raw=true" alt="" width="340" height="299" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_23.PNG?raw-true"><img class="size-full wp-image-460 aligncenter" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_23.PNG?raw=true" alt="" width="332" height="233" /></a></p>

In this tutorial, we have been focusing on editing a data layer in Carto. The program also includes tools that let you analyze your data (`Layers` and `Analysis`) and add interactive `Widgets` for a dynamic public interface.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_52.png?raw=true" alt="Capture" /></p>

[Link to Prof. Walden's sample map with widgets for this lab](https://kwalden.carto.com/builder/be217bb8-46f4-47a1-83dc-96ccd200e175/embed)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_53.png?raw=true" alt="Capture" /></p>

To learn more about Carto's features and functionality: https://carto.com/help/

## Mapping in Python

As mentioned earlier in the lab, Prof. Walden has built out a Jupyter notebook that goes into more detail about using Python for exploratory data analysis for the sample datasets presented in this lab.

That notebook also includes sample code for static and interactive mapping in Python.

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

Jupyter Notebook:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.ipynb)
- [NBviewer](https://nbviewer.jupyter.org/github/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.ipynb)
- [Google CoLab](https://drive.google.com/file/d/1MybxGo9ngdm20rzV1xAqAGYZwNsLINTM/view?usp=sharing)

## Mapping in RStudio

As mentioned earlier in the lab, Prof. Walden has built out an RMarkdown file that goes into more detail about using RStudio for exploratory data analysis for the sample datasets presented in this lab.

That RMarkdown file also includes sample code for static and interactive mapping in RStudio.

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

RMarkdown File:
- [`.rmd` file on GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/notebooks/nd-football-eda.Rmd)
- [`.rmd` file on Google Drive](https://drive.google.com/file/d/1gvhci2x1IVsHOFCEwkeVvm_HSUPU0l2V/view?usp=sharing)
- [RStudio Cloud](https://rstudio.cloud/project/2977118)

RStudio Project:
- [GitHub, `.zip`](https://drive.google.com/file/d/1zex8zotq6TpLtzcDukl0NtH8oxaswBqR/view?usp=sharing)
- [RStudio Cloud](https://rstudio.cloud/project/2977118)

## MAPPING QUESTIONS/WRAP UP
# Final reflection questions:
<ul>
 	<li>What interested you in this data? Would you have been able to find this information and draw conclusions from it without using spatial analysis tools?</li>
 	<li>What questions do you still have about this data? How could you answer them? How could you answer them digitally?</li>
 	<li>Were there any issues we talked about in historical mapping (change over time, error, certainty, etc.) that you think of differently now that you have tried it?</li>
</ul>

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

# Networks

- [DataBasic: Connect the Dots](#databasic-connect-the-dots)
- [Palladio](#palladio)
- [Gephi](#gephi)
- [Network Discussion/Reflection Questions](#network-discussionreflection-questions)
- [Other Network Tools/Resources](#other-network-toolsresources)

## DataBasic: Connect The Dots

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_1.jpg?raw=true" alt="Capture" /></p>

Navigate to the [DataBasic home page.](https://databasic.io)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_13.png?raw=true" alt="Capture" /></p>

Click on the `ConnectTheDots` icon to open the ConnectTheDots tool.

As described on the page, “ConnectTheDots shows you how your data is connected by analyzing it as a network. Analyzing the connections between the "dots" in your data is a fundamentally different approach to understanding it. This tool shows you a network diagram to reveal those links, and gives you a high level report about what your network looks like.”

## Knute Rockne Coaching Tree

We'll also think in this lab about how structured data can be the starting point for looking at networks and relationships, under the umbrella of network analysis.

### What is a network?

According to Miriam Posner, networks are “a finite set (or sets) of actors and the relations defined on them. It consists of three elements: 
- (1) a set of actors;
- (2) each actor has a set of individual attributes; and 
- (3) a set of ties that defines at least one relation among actors.” 
 
A network graph is “a common way to visually represent social networks, consisting of two dimensions: actors and relations (also called nodes and edges). Nodes are the entities in graph (also called vectors)..[edges] are the relationships between nodes.” 

Learn more via the [PDF included in this Repository](https://github.com/kwaldenphd/football-structured-data/blob/main/files/Posner_SocialNetworkAnalysisGlossary.pdf)

### Coaching tree as a type of network

From [Wikipedia](https://en.wikipedia.org/wiki/Coaching_tree):

"A coaching tree is similar to a family tree except that it shows the relationships of coaches instead of family members. There are several ways to define a relationship between two coaches. The most common way to make the distinction is if a coach worked as an assistant on a particular head coach's staff for at least a season then that coach can be counted as being a branch on the head coach's coaching tree. Coaching trees can also show philosophical influence from one head coach to an assistant.

"Coaching trees are common in the National Football League and most coaches in the NFL can trace their lineage back to a certain head coach for whom they previously worked as an assistant."

We can think of a coaching tree as a type of network, where the relationship of coaches in the tree is understood via nodes and edges.

Let's take a look at a couple different representations of Knute Rockne's coaching tree:
- "[Rockne's Coaching Tree](https://my.nd.edu/news/9551)" *Notre Dame, Alumni & Friends* (26 March 2013)
- "[Knute Rockne, Coaching Tree](https://en.wikipedia.org/wiki/Knute_Rockne#Coaching_tree)", *Wikipedia*

Discussion Questions:
- What parts of information on this page would you want to work with as structured data?
- What types of analysis/visualization or exploration would you be able to do with this resource as structured data?
  * What questions or topics would you be able to explore using data from this resource? 
- Other comments/questions about this source as structured data

As an example of research that uses this approach/method:
- Andrew Fast and David Donald Jensen, "[The NFL Coaching Network: Analysis of the Social Network Among Professional Football Coaches](https://www.researchgate.net/publication/228968729_The_NFL_Coaching_Network_Analysis_of_the_Social_Network_Among_Professional_Football_Coaches)" *American Association for Artificial Intelligence* (2006)

### Rockne Coaching Tree Data Processing Overview

No fancy Jupyter Notebooks for this one. Prof. Walden went through a few iterations of how to organize and structure the Rockne coaching tree facilitate network analysis.

The `Rockne_Coaching_Tree` Excel workbook documents this iterative process:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Rockne_Coaching_Tree.xlsx)
- [Google Drive](https://docs.google.com/spreadsheets/d/1B2RaD_qtrQaupo6FznKzuAMnYCGt6eEJJ-aAcU9z8I4/edit?usp=sharing)

The first step was to take the information on Wikipedia and map it onto a tabular data structure that would move in the direction of having nodes, edges, and weights.

The `Original_Coaching_Tree.csv` file reflects this preliminary structure.
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Rockne_Coaching_Tree_Full.csv)
- [Google Drive](https://docs.google.com/spreadsheets/d/1B2RaD_qtrQaupo6FznKzuAMnYCGt6eEJJ-aAcU9z8I4/edit?usp=sharing)

The preliminary structure included the following columns:
- `Name` (player/coach name)
- `Played_Under` (Rockne)
- `Years_Played` (years playing at ND)
- `ND_No_Years` (total number of years played at ND)
- `Next_Inst` (institution person coached at next)
- `Years_Next_Inst` (years at next institution)
- `Coach_No_Years` (total nubmer of years coaching at next institution)
- `Coach_Rk` (coaching rank, head coach or associate)

The most straightforward way to represent this data as a network is to have `source` and `target` nodes, in which Rockne is the source and the person who played/coached for him is the target. 

The `Simplified_Coaching_Tree_CTD.csv` file reflects this `source-target` structure:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Simplified_Coaching_Tree_CTD.csv)
- [Google Drive](https://drive.google.com/file/d/1AvPk8sKYhlsCz6RjUTzkSyxxULX_Wf2U/view?usp=sharing)

We can also include the other institutions these individuals played at as source nodes.

The `Alternate_Simplified_Coaching_Tree_CTD.csv` file reflects this expanded `source-target` structure:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Alternate_Simplified_Coaching_Tree_CTD.csv)
- [Google Drive](https://drive.google.com/file/d/1OTel7xqn2yxx9fzDFWPQkdwR67oP-pJc/view?usp=sharing)

But the simplified `source-target` structure doesn't account for aspects of these relationships like how many years someone played at ND, or how many years they coached at subsequent institutions.

We can use the concept of weighted edges to incorporate these other pieces of data.

One way to incorporate weighted edges is to use the number of years someone played at ND or coached elsewhere as the weight.

The `Full_Coaching_Tree_Edges.csv` file reflects this weighted edge structure.
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Full_Coaching_Tree_Edges.csv)
- [Google Drive](https://drive.google.com/file/d/1NK3JPimaISPy8NCifrCSSV7w8ZMtCOYO/view?usp=sharing)

When Rockne is the `source` node, the weight is the number of seasons the `target` individual played under him at ND.

When an institution or team is the `source` node, the weight is the number of seasons the `target` individual coached at this program.

For ConnectTheDots, our network data is formatted as a list of edges, or connections, between a source and target node. 

<table>
  <tr>
    <th>source</th>
    <th>target</th>
  </tr>
  <tr>
    <td>Knute Rockne</td>
    <td>Gus Dorais</td>
  </tr>
  <tr>
    <td>Boston College</td>
    <td>Frank Leahy</td>
  </tr>
 </table>

<blockquote>Images and screenshots included in this tutorial are from a sample dataset and do not reflect what you will see working with different data.</blockquote>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_14.png?raw=true" alt="Capture" /></p>

ConnecTheDots gives you the option to use sample network data, paste your own data, or upload a file.

We have two sample datasets that work with ConnectTheDots:
- `Simplified_Coaching_Tree_CTD.csv` has Rockne is the source and the person who played/coached for him is the target
  * [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Simplified_Coaching_Tree_CTD.csv)
  * [Google Drive](https://drive.google.com/file/d/1AvPk8sKYhlsCz6RjUTzkSyxxULX_Wf2U/view?usp=sharing)
- `Alternate_Simplified_Coaching_Tree_CTD.csv` has Rockne or institutions his players coached for as source nodes and the players/coaches as target nodes
  * [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Alternate_Simplified_Coaching_Tree_CTD.csv)
  * [Google Drive](https://drive.google.com/file/d/1OTel7xqn2yxx9fzDFWPQkdwR67oP-pJc/view?usp=sharing)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_15.png?raw=true" alt="Capture" /></p>

The top of the ConnecTheDots results page provides an overview of your network. The network graph uses colors to indicate groups of nodes, and the graph caption provides a description of the network graph.

The table on the right-hand side of the page includes a list of nodes in your network, as well as the degree and centrality for each node.

<blockquote> Degree refers to the number of connections a node has. Centrality is a calculation of how central a node is within the network.</blockquote> 

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_15a.png?raw=true" alt="Capture" /></p>

Clicking the square arrow icon at the top of the page gives you a link to your results (good for 60 days).

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_15b.png?raw=true" alt="Capture" /></p>

Clicking the Download button by the network graph gives you the option to download the graph as an image file (PNG or SVG) or a network graph file to use in a network analysis software program (GEXF). You can also download the table of nodes with degree and centrality metrics as a CSV file.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_16.png?raw=true" alt="Capture" /></p>

#### Reflection Questions

asdf asf dsa network something here

## Palladio

*Developed through a National Endowment for the Humanities Implementation grant, [Palladio](http://hdlab.stanford.edu/palladio) was released by Stanford University in June 2016. Designed for historians and other digital humanities scholars, Palladio is a web-based application that allows users to analyze data that includes time and network features and display that data via maps, timelines, other types of visualizations, and gallery exhibits. Designed as a browser-based GUI interface, Palladio works well for quick visualizations and offers limited interactive export options.*

## Loading data into Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-498" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="334" /></a></p>

Open the [Palladio home page](http://hdlab.stanford.edu/palladio) in Chrome or Firefox. 

Click on the `Start` icon to open a new project.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-large wp-image-499" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="676" height="454" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-500" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="876" height="764" /></a></p>

Drag and drop one of the Rockne network files into the `Load CSV` window.

Any of the network CSV files will work in Palladio.
- `Simplified_Coaching_Tree_CTD.csv` (just Rockne and former players)
- `Alternate_Simplified_Coaching_Tree_CTD.csv` (Rockne, former players, and institutions they coached for)
- `Full_Coaching_Tree_Edges.csv` (Rockne, former players, and institutions they coached for with attached weights based on number of years played under Rockne or number of years coaching elsewhere)

Click the `Load` icon to load the data.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true"><img class="aligncenter size-full wp-image-486" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="" width="502" height="531" /></a></p>

Click on `Untitled` to give the table a descriptive label.

You may notice Palladio has a red dot next to some fields. We're going to ignore this message for now.
- Palladio requires you to verify special or unexpected characters in the data fields. You can click on the red dot and select `Verify special characters` and then `Done` to address the error message.

Back on the `Data` screen, you can see the error has been resolved, and Palladio has also automatically described your data fields as a text, date, or number. 

## Analyzing and Visualizing Data in Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter size-full wp-image-491" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="391" height="55" /></a></p>

Palladio does offer mapping functionality, but our data does not contain spatial information. 

Click on the `Graph` tab to start building a network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter size-full wp-image-492" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="614" height="364" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter size-large wp-image-493" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="676" height="314" /></a></p>

Select `Source` from the `Source dimension` drop-down menu, and `Target` from the `Target dimension` drop-down.

Palladio has now generated a network graph.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true"><img class="aligncenter size-large wp-image-495" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="" width="676" height="310" /></a></p>

We can also choose to size the nodes based on another data field.

Check the box next to `Size nodes` and select `Weight` for `According to`.

These settings size our nodes based on the weight assigned or determined by the number of years someone played under Rockne or number of years they coached at another institution.

Palladio offers additional facet, timeline, and timespan analysis via the buttons on the bottom of the page. These features can be useful depending on what types of information are included in the data you are working with.

For a more in-depth look at network analysis in Palladio: Marten Düring, "From Hermeneutics to Data to Networks: Data Extraction and Network Visualization of Historical Sources," The Programming Historian 4 (2015), https://doi.org/10.46430/phen0044.

## Gephi

ConnecTheDots and Palladio are both browser-based tools for generating network visualizations and preliminary network analysis. Both tools offer limited options for calculating or analyzing more advanced network metrics. [Gephi](https://github.com/gephi/gephi) is an open-source network analysis and visualization software created by students at the University of Technology of Compiègne in 2008. The Gephi Consortium, which supports the ongoing development and documentation for Gephi, is a non-profit corporation supported by members that include SciencesPo, Linfluence, WebAtlas, and Quid. Gephi runs on Linux, Windows, and macOS operating systems and is available in 9 different languages.

## Installing Gephi

To download Gephi on your own computer, go to [Gephi’s download page](https://gephi.org/users/download) and select the correct version for your operating system.

## Loading Data into Gephi

Launch Gephi and select `New Project` in the `Welcome` pop-up window.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture.PNG?raw=true" alt="" width="840" height="473" /></a></p>

Select `Import Spreadsheet` under the `File` menu tab.

Select the `Full_Coachign_Tree_Edges.csv` file.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture2.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture2.PNG?raw=true" alt="" width="843" height="500" /></a></p>

Make sure `Comma` is selected as the `Seperator`, `Edges` table is selected under `Import as`.
- If needed, make sure `UTF-8` is selected under `Charset`.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture3.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture3.PNG?raw=true" alt="" width="845" height="498" /></a></p>

Click `Next`.

In the `Import settings (2 of 2)` pop-up, leave the default settings, and click `Finish`.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture4.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture4.PNG?raw=true" alt="" width="662" height="460" /></a></p>

Select `Undirected` under `Graph Type`, and switch the default selection from `New workspace` to `Append to existing workspace`.

Click `OK` to load the data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture5.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture5.PNG?raw=true" alt="" width="840" height="475" /></a></p>

The Rockne coaching tree data is now loaded in the `Data Laboratory` tab.

Before we go any further, click `Save` under the `File` menu option to save the project.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture11.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture11.PNG?raw=true" alt="" width="511" height="105" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture12.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture12.PNG?raw=true" alt="" width="840" height="472" /></a></p>

Click on the `Overview` tab (and `Graph` tab if needed) to see Gephi’s default visualization of your network data.

As you probably noticed, the default visualization is an interesting connection of nodes and edges, but doesn’t do much to help us more fully understand and analyze our data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture14.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture14.PNG?raw=true" alt="" width="366" height="141" /></a></p>

Click on `Choose a layout` under the `Layout` panel to select how Gephi displays your nodes and edges.

Gephi uses a variety of layout algorithms to determine the shape of network graphs. These different layouts algorithms highlight different aspects or features of your data.

<table>
<tbody>
<tr>
<td width="312">Divisions</td>
<td width="312">OpenOrd</td>
</tr>
<tr>
<td width="312">Complementarities</td>
<td width="312">ForceAtlas, Yifan Hu, Frushterman-Reingold</td>
</tr>
<tr>
<td width="312">Ranking</td>
<td width="312">Circular, Radial Axis</td>
</tr>
<tr>
<td width="312">Geographic Repartition</td>
<td width="312">GeoLayout</td>
</tr>
</tbody>
</table>

`Label Adjust`, `Noverlap`, `Expansion`, and `Contraction` make graphic adjustments to how your data displays, rather than using an underlying algorithm to change the structure of the network visualization.

Select different layout options and click the `Run` icon to see how the different algorithms and settings change the visualization of your data. 
- If needed, click the `Stop` icon to stop the layout operation.

## Calculating Network Metrics in Gephi

Gephi includes built-in options to calculate a number of different network statistics.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture15.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture15.PNG?raw=true" alt="" width="324" height="617" /></a></p>

The `Statistics` panel gives you the option to run a number of different calculations on your network data.

While Gephi allows us to easily perform these calculations, the program doesn’t automatically tell us what these measures mean or how they are calculated.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture16.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture16.PNG?raw=true" alt="" width="701" height="603" /></a></p>

The HTML report in the pop-up window that displays after you run a statistics gives you a graph of the data calculation, and sometimes the source for the algorithm used to calculate the statistic.

Consult [Gephi's GitHub repository](https://github.com/gephi/gephi/wiki/Statistics) for more information on these statistics.

Click `Run` for some of the options under `Statistics`.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture19.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture19.PNG?raw=true" alt="" width="840" height="473" /></a></p>

If you click on the `Data Laboratory` tab, you will see these calculated statistics have been added to your network data.

## Customizing a Network Visualization in Gephi

Select `Noverlap` for your Layout so your nodes and edges don’t overlap as you are exploring display customization options.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture21.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture21.PNG?raw=true" alt="" width="840" height="655" /></a></p>

The border icons in the Graph panel allow you to customize the display of your network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture22.PNG?raw=true"><img class="size-full wp-image-196 alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture22.PNG?raw=true" alt="" width="28" height="24" /></a></p>

Click on the `Show Node Labels` icon to display the node labels. 

You can change the size of text for your labels by using the slider to the right of `Arial Bold, 32.`

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture24.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture24.PNG?raw=true" alt="" width="359" height="362" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture23.PNG?raw=true"><img class="alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture23.PNG?raw=true" alt="" width="22" height="29" /></a></p>

You can also click on the `Attributes` icon to customize what data fields display as part of your labels.

While your nodes now have labels, the large number of nodes and edges makes it difficult to differentiate or discern various attributes about our network data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture20.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture20.PNG?raw=true" alt="" width="347" height="110" /></a></p>

The `Appearance` panel allows you to customize the color, size or weight, and labels for your nodes and edges. 

Changing the coloring or sizing of nodes in the `Appearance` panel can help make our network visualization more meaningful.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture26.PNG?raw=true"><img class="alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture26.PNG?raw=true" alt="" width="24" height="25" /></a></p>

Select the `Size` icon to change the default size of your nodes. 
- You can explore different sizes, but 3 works well with this dataset. 

Click the `Apply` icon to change the setting for your network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture27.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture27.PNG?raw=true" alt="" width="349" height="330" /></a></p>

You can also rank the size of nodes based on one of the network metrics you calculated in the `Statistics` panel.

Click the `Ranking` icon in the `Appearance` panel.

Select `Degree` from the drop-down menu. Click `Apply` to update the graph.

Ranking our node size by degree determines the size of a node based on its degree of centrality (or connectedness). Nodes with higher numbers of connections appear larger, and nodes with lower numbers of connections are smaller.

You can change the minimum and maximum node size, and also select different statistics to use for determining node size.

Explore these different settings and options to see how different node size calculations shape your understanding of the network data.

Save your project.

## Exporting Networks

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Picx.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Picx.png?raw=true" alt="" width="244" height="264" /></a></p>

Click `Export` under the `File` menu tab to save your project as a static image (SVG, PNG, PDF) or network file (CSV, GDF, GEXF, GraphML, Pajek Net).

Learn more about the different export options by consulting Gephi's [graph format documentation](https://gephi.org/users/supported-graph-formats)

An earlier step in this section of the lab had you experiment with display customization settings.

Return to the visualizations you explored in that step, and export those you find useful or interesting as PNG files.

## Other Network Tools/Resources

A couple of additional Gephi tutorials:
- Brian Sarnacki, ["The Complete n00b's Guide to Gephi"](http://www.briansarnacki.com/gephi-tutorial/) *blog* (26 March 2015)
- Martin Grandjean, ["Introduction to Network Visualization with GEPHI"](http://www.martingrandjean.ch/introduction-to-network-visualization-gephi/) *blog* (7 January 2013)

There are a number of other tools, libraries, and packages that can be used for network analysis, if folks want to dig in further.

Some background reading and resources on networks:
- Scott Weingart, ["Demystifying Networks"](http://www.scottbot.net/HIAL/index.html@p=6279.html) *blog* (14 December 2011)
- [Miriam Posner's "Network Analysis" guide](http://miriamposner.com/classes/dh101f16/tutorials-guides/data-visualization/network-analysis/)
- Shawn Graham, Ian Milligan, and Scott Weingart, *Exploring Big Historical Data: The Historian's Macroscope* (Imperial College Press, 2016)
  * [Chapter 6 "Network Analysis" (195-234)](https://drive.google.com/file/d/1MQOF4wgXwjKcMhIsBqp6Ewuf4yXAFUJE/view?usp=sharing) (Google Drive, ND users)
  * [Chapter 7 "Networks in Practice" (235-264) ](https://drive.google.com/file/d/1bES8da6Aa6l_aSpb76bhyRJ6qE49o56c/view?usp=sharing) (Google Drive, ND users)

A few tutorials:
- R/RStudio
  * Alex Brey, "Temporal Network Analysis with R," The Programming Historian 7 (2018), https://doi.org/10.46430/phen0080.
  * Ryan Deschamps, "Correspondence Analysis for Historical Research with R," The Programming Historian 6 (2017), https://doi.org/10.46430/phen0062.
  * Katya Ognyanova, ["Network analysis with R and igraph"](https://kateto.net/networks-r-igraph) *blog* (10 January 2016)
- Python
  * John R. Ladd, Jessica Otis, Christopher N. Warren, and Scott Weingart, "Exploring and Analyzing Network Data with Python," The Programming Historian 6 (2017), https://doi.org/10.46430/phen0064.
  * Prof. Walden's [`networkx` Python tutorial](https://github.com/kwaldenphd/NetworkX-tutorial)
  * [`pyvis` tutorial](https://pyvis.readthedocs.io/en/latest/tutorial.html) (for interactive network in Python)
  * ["Interactive Network Visualizations"](https://pyvis.readthedocs.io/en/latest/), `pyvis` documentation
  * Jose Manuel Napoles Duarte, ["Making network graphs interactive with Python and Pyvis"](https://towardsdatascience.com/making-network-graphs-interactive-with-python-and-pyvis-b754c22c270) *Towards Data Sciecne* (5 January 2021)
- D3/JavaScript
  * D3.js gallery, ["Network graph"](https://www.d3-graph-gallery.com/network)
  * Jim Vallandingham, ["How to Make an Interactive Network Visualization"](https://flowingdata.com/2012/08/02/how-to-make-an-interactive-network-visualization/) *FlowingData* (2 August 2012)
  * Elijah Meeks, [Network Viz Slide Deck](http://elijahmeeks.com/networkviz/)
- Other
  * Jon MacKay, "Dealing with Big Data and Network Analysis Using Neo4j," The Programming Historian 7 (2018), https://doi.org/10.46430/phen0074.
  * Miriam Posner's ["Creating Network Graphs with Cytoscape"](https://github.com/miriamposner/cytoscape_tutorials) tutorial
  * Miriam Posner's ["Build a simple network graph with Flourish"](http://miriamposner.com/classes/dh201w21/tutorials-guides/network-analysis/flourish-graph/) tutorial

# Next Steps (aka, now it's your turn!)

## Collaborating Well

## Where to Start: Articulating a Research Question/Topic and Developing a Data Model

## Data (Pre)Processing

### OpenRefine



### Data Cleaning in Excel



### Data Cleaning in Python

### Data Cleaning in RStudio

### Command Line (regular expressions)



## Tool Directory

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
    * R/RStudio
    * Python
  * Interactive
    * Palladio
    * Python (`networkx` and `pyvis`)
    * ConnectTheDots

## Addressing Your Research Questions

# Lab Notebook Components

## Acknowledgements

### Excel and Tableau

This tutorial was originally written by Katherine Walden, when she was working as a Digital Liberal Arts Specialist at Grinnell College. 

This tutorial was reviewed by <a href="https://www.grinnell.edu/users/purcelsj">Sarah Purcell</a> (L.F. Parker Professor of History) and <a href="https://www.grinnell.edu/users/donovang">Gina Donovan</a> (Instructional Technologist) at Grinnell College, and edited by Papa Kojo Ampim-Darko, a student research assistant at Grinnell College.

This tutorial incorporates elements of the <a href="https://callingbullshit.org/index.html">Calling Bullshit curriculum</a> developed by Carl Bergstrom and Jevin West at the University of Washington.

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
Visualizing Data (Excel and Tableau) is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

### Google MyMaps

This tutorial was originally written by Katherine Walden, when she was working as a Digital Liberal Arts Specialist at Grinnell College. The tutorial framework was created by Sarah Purcell (L.F. Professor of History, Grinnell College) Sophia Gates Stern, student mentor for this class.

This tutorial was reviewed by <a href="https://www.grinnell.edu/users/donovang">Gina Donovan</a> (Instructional Technologist, Grinnell College) and Lauren Frankel and Martin Toney, student workers in Grinnell College’s <a href="http://dasil.sites.grinnell.edu/">Data Analysis and Social Inquiry Lab</a>.

This tutorial uses <a href="http://www.cameronblevins.org/postal-data/">data generated by Cameron Blevins</a> and posted on his personal site.

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
Introduction to Mapping Part II (Google MyMaps) is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

### Carto

ThThis tutorial was originally written by Katherine Walden, when she was working as a Digital Liberal Arts Specialist at Grinnell College. The tutorial framework was created by Sarah Purcell (L.F. Parker Professor of History, Grinnell College) and Sophia Gates Stern, student mentor for the class.

This tutorial was reviewed by <a href="https://www.grinnell.edu/users/donovang">Gina Donovan</a> (Instructional Technologist, Grinnell College) and Lauren Frankel and Martin Toney, student workers in Grinnell College’s <a href="http://dasil.sites.grinnell.edu/">Data Analysis and Social Inquiry Lab</a>.

This tutorial uses <a href="http://www.cameronblevins.org/postal-data/">data generated by Cameron Blevins</a> and posted on his personal site.

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
Introduction to Mapping Part I (Carto) is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

### Palladio

This tutorial was originally written by Katherine Walden, when she was working as a Digital Liberal Arts Specialist at Grinnell College. 

This tutorial was reviewed by <a href="https://www.grinnell.edu/users/purcelsj">Sarah Purcell</a> (L.F. Parker Professor of History) and <a href="https://www.grinnell.edu/users/donovang">Gina Donovan</a> (Instructional Technologist) at Grinnell College, and edited by Papa Ampim-Darko, a student research assistant at Grinnell College.

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
Network Analysis-Part I (Palladio) is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

### Gephi

This tutorial was originally written by Katherine Walden, when she was working as a Digital Liberal Arts Specialist at Grinnell College. 

This tutorial was reviewed by <a href="https://www.grinnell.edu/users/purcelsj">Sarah Purcell</a> (L.F. Parker Professor of History) and <a href="https://www.grinnell.edu/users/donovang">Gina Donovan</a> (Instructional Technologist) at Grinnell College, and edited by Papa Ampim-Darko, a student research assistant at Grinnell College.

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
Network Analysis-Part III (Gephi) is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

### Text and Data Mining for ND Archive Materials

Any text and data mining endeavor is supported by heroic and ongoing work that happens at the nexus of digital infrastructure, archives/special collections, metadata, digital preservation. The workflows outlined in this project would not be possible without significant past, present, and ongoing work from colleagues in the University of Notre Dame Libraries, specifically (but not exclusively)...
- [University Archives](http://archives.nd.edu/) (Patrick Milhoan, Scott Kirycki, Joseph Smith, and Matthew Wilken)
- [Rare Books and Special Collections](https://rarebooks.library.nd.edu/) (Rachel Bohlmann, Tracy Bergstrom, Sara Weber)
- [Navari Family Center for Digital Scholarship](https://cds.library.nd.edu/) (Daniel Johnson, Eric Lease Morgan, Matthew Sisk)
- [Digital Services](https://directory.library.nd.edu/directory/departments/1195) (Mikala Narlock)
