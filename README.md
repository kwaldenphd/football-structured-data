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
- 1922 Student Directory
- Combined Football Rosters from Sports Reference
- Combined Football Schedules from Sports Reference
- Knute Rockne coaching tree from Wikipedia

<blockquote> What is a CSV? 

A comma-separated value file (CSV) is a structured tabular data format in which column values are separated by a comma. Computer programs like Microsoft Excel parse those values and display the underlying data in a spreadsheet format. Saving tabular data as a CSV file type avoids much of the additional formatting added by programs like Microsoft Excel. </blockquote>

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

## Data

We'll be using three sample datasets in the Exploratory Data Analysis section of the lab.

`ND_Directory_Cleaned_Geography.csv` represents a data structure based on the 1922-1923 student directory. Fields in the dataset include:
- `Combined_Name` (combined first name, last name, and major field)
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
  * However the Pivot Table and Pivot Chart functionality is not available within Google Sheets.

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

## Analyzing Data in Microsoft Excel

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

## Creating a Table in Excel

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

### Discussion and Reflection Questions

- How do the AutoSum calculations impact or inform your understanding of the data?
- What questions do you have about the data or calculations?
- Why would it be helpful to be able to sort/filter/etc within a dataset?
- As you explore the sort/search/filter functionality, what questions emerge about the data?
- Other comments/questions/observations

## Data Visualization with Microsoft Excel

Excel includes a range of built-in chart types that you can use to generate visualizations for data in your table.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_11.png?raw=true" alt="Capture" /></p>

Click on the `Recommended Charts` icon under `Data`.

Explore the different options Excel recommends for visualizing your data.

Click on `OK` in the `Insert Chart` pop-up window to insert a chart to your workbook sheet.

You can also click on a specific chart type in the `Charts` menu area to build your own visualizations.

For folks working in Google Sheets:
- Google Docs Help Center, "[Types of charts & graphs in Google Sheets](https://support.google.com/docs/answer/190718?hl=en)"
- Google Docs Help Center, "[Add & edit a chart or graph](https://support.google.com/docs/answer/63824?hl=en&co=GENIE.Platform%3DDesktop)"

### Discussion and Reflection Questions

What types of visualizations were you able to generate in Excel using PivotChart? How could those visualizations shape or impact your understanding of the data? Did you generate any visualizations that were confusing or misleading? Alternatively, did you generate any visualizations that were unexpected or illuminating?

## PivotTables and PivotCharts in Excel

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

### Additional Resources

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

### Takeaways from all the Excel adventures...

You're probably wondering why we spent so much time working in Excel and exploring some of the more advanced functionality, and that's a fair question.

Folks with computer science/data science backgrounds and programming chops are probably wondering why we would spend so much time figuring out how to do things in a proprietary software program that can be accomplished programmatically in open-source programs like Python, RStudio, and SQL.

A few reasons:
- Google Sheets is a powerful spreadsheet tool, but there's a reason Excel is an industry standard for more organizations/companies that have more advanced data processing workflows and don't necessarily have data scientists/computer scientists/programmers on staff
- Excel integrates with other data processing workflows and visualization tools (specifically PowerBI) to create an incredibly powerful data ecosystem
- So yes, Excel will change, but it's not going anywhere. 
- And to Prof. Walden's knowledge, there's no non-coding spreadsheet program (including Apple Numbers, Google Sheets, open-source Libre Office Calc) that comes in terms of functionality.

Additionally, these Excel workflows can help those without a data science/programming/data engineering/etc background understand some of the core concepts and steps involved in data modeling and database systems.
- This helps immensely when you're in a work setting where you need to be able to talk to or interact with folks working in and around database engineering. Even if you're not the one building or maintaining the workflows, you are much better equipped to have intelligent conversations about what those individuals are doing and what you need these systems to do.

## Reflection Questions

What types of visualizations were you able to generate in Excel using PivotChart? How could those visualizations shape or impact your understanding of the data? Did you generate any visualizations that were confusing or misleading? Alternatively, did you generate any visualizations that were unexpected or illuminating?

## Tableau


<a href="https://www.tableau.com/">Tableau</a> is a software company founded in Silicon Valley in 2003. Developed by researchers affiliated with Stanford University’s Computer Science Department, Tableau is a commercialized application of academic research. Represented as DATA on the New York Stock Exchange after a 2013 initial public offering, Tableau reported $877 million in revenue in <a href="s1.q4cdn.com/149179428/files/doc_financials/2017/FY2016-Annual-Report.pdf">the 2017 fiscal year</a>. Most often deployed in business environments, Tableau Desktop is a subscription-based data analysis and visualization software. Tableau Server and Tableau Online offer subscription-based web-publishing options for making data and interactive visualizations available on the web. Tableau Public offers limited Tableau Desktop functionality with some options for uploading visualizations through the Tableau Public website.

<hr />

13-<strong>Open Tableau</strong> by clicking on the <strong>Desktop icon</strong>, or searching in the <strong>Start menu</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_16.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_16.png?raw=true" alt="" /></a></p>

14-<strong>Click on Microsoft Excel</strong> and navigate to the <strong>1870 Federal Census Grinnell Township file</strong> saved to your Desktop.

15-Click <strong>Open</strong> to load the data into Tableau.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_20.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_20.png?raw=true" alt="" /></a></p>

16-Tableau's Data Source previews the structure of the data we loaded from the Excel file. Tableau determines what type of data is contained in each field (integer number values, dates, geographic spatial information, strings of letters or characters, etc.).

17-If we wanted to analyze or visualize data from multiple tables, Tableau's <strong>Data Source tab</strong> offers some functionality for joining tables and building a database structure.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true" alt="" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_21.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_21.png?raw=true" alt="" /></a></p>

18-Click on the <strong>Sheet 1 icon</strong> next to Data Source to move into Tableau's visualization builder interface.

<blockquote>How is the data in Tableau presented or organized differently than the same information in Excel? What similarities or differences do you notice between the two user interfaces for building data visualizations?</blockquote>

19-Tableau distinguishes between <strong>Dimensions</strong> (data fields that cannot be aggregated) and <strong>Measures</strong> (data fields that can be aggregated--or have mathematical operations performed on them).

20-To visualize the distribution of students taking certain types of AP courses, we need a graph that counts the number of students for each AP course category.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_22.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_22.png?raw=true" alt="" /></a></p>

21-Drag "Advanced Placement Course Enrollment...." from Dimensions to Rows, and "Number of......Students" to Columns.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_23.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_23.png?raw=true" alt="" /></a></p>

22-Tableau recognizes the combination of data elements and automatically generates a vertical bar chart.

23-<strong>Move your cursor over the chart</strong> to see the interactive data points.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataVizscreenshots/Capture_23.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_23.png?raw=true" alt="" /></a></p>

24-Tableau recognizes the combination of data elements and automatically generates a vertical bar chart.

25-<strong>Move your cursor over the chart</strong> to see the interactive data points.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataVizscreenshots/Capture_25.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_25.png?raw=true" alt="" /></a></p>

26-Tableau allows chart customization with the <strong>Marks panel</strong>. For example, dragging the "Advanced Placement...." field from <strong>Dimensions</strong> to the <strong>Color</strong> icon in <strong>Marks</strong> colors the bars according to the different AP Course categories.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataVizscreenshots/Capture_24.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/HUM295-DataViz/screenshots/Capture_24.png?raw=true" alt="" /></a></p>

27-The <strong>Show Me panel</strong> on the right-hand side of the Tableau window shows other types of visualizations you can build in Tableau using this combination of data fields and calculations.

28-Experiment with other data fields and calculations to generate different types of visualizations. You can add new worksheets or duplicate an existing worksheet to build multiple visualizations.

## Reflection Questions

What types of visualizations were you able to generate in Tableau? How were those visualizations similar or different than what you generated in Excel?

How could those visualizations shape or impact your understanding of the data? Did you generate any visualizations that were confusing or misleading? Alternatively, did you generate any visualizations that were unexpected or illuminating?</blockquote>

<hr />

## Uploading to Tableau Public

One of Tableau's features is that it allows users to upload interactive data visualizations to the web and embed them in websites and other online spaces.

<p align="center"><a href="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_28.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/excel-pivot-tables-tutorial/blob/master/screenshots/Capture_28.PNG?raw=true" alt="" /></a></p>

If you have additional time, <a href="https://public.tableau.com/en-us/s/">create a free profile</a> on Tableau Public's website.

Click <strong>File-&gt; Save to Tableau Public</strong>, and use your login credentials to save your Tableau workbook to Tableau Public's website.

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

# Mapping

## Google MyMaps

Google launched <a href="https://www.google.com/maps/about/mymaps/">Google My Maps</a> in 2007 as part of the Google cloud services suite of programs. Through the My Map interface, users with a Google account can map points, lines, and shapes, with additional display customization options. My Maps allows users to generate maps from spreadsheets, work collaboratively on maps, and share interactive maps.

<hr />

# Data

Download the 1870_Federal_Census_Grinnell_Township.csv file from this GitHub repo. Save the 1870 Federal Census Grinnell Township file to your Desktop.

Alternatively, you can go to the data page of Blevins’s personal site. Under the “Regional Data: Western Post Offices and Postmaster Salaries” heading, download the 1871_PostmasterSalaries CSV file.

<hr />

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-473" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="332" /></a></p>

1-Sign up for a <a href="https://accounts.google.com/signup/v2/webcreateaccount?hl=en&amp;flowName=GlifWebSignIn&amp;flowEntry=SignUp">free Google Account</a>, and use those credentials to <a href="https://accounts.google.com/ServiceLogin/signinchooser?service=mymaps&amp;passive=1209600&amp;continue=https%3A%2F%2Fwww.google.com%2Fmaps%2Fd%2F%3Fhl%3Den&amp;followup=https%3A%2F%2Fwww.google.com%2Fmaps%2Fd%2F%3Fhl%3Den&amp;hl=en&amp;flowName=GlifWebSignIn&amp;flowEntry=ServiceLogin">log in to My Maps</a>.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-full wp-image-474" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="178" height="55" /></a></p>

2-Click on the <strong>Create New Map</strong> icon in the top left-hand corner.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter size-full wp-image-479" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="407" height="295" /></a></p>

3-Name the map by clicking on <strong>Untitled map</strong> in the top left-hand corner. Use <strong>Postmaster Salaries</strong> or a similar descriptive name.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-475" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="317" height="308" /></a></p>

4-Click the blue <strong>Import</strong> icon to start the data import process. Select or drop the  <strong>1871_Postmaster_Salary CSV</strong> file to upload the data set. 

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter size-full wp-image-477" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="504" height="433" /></a></p>

5-Check that only <strong>Latitude</strong> and <strong>Longitude</strong> are selected before clicking <strong>Continue</strong>. My Maps will keep all the original data records but needs to detect which fields contain spatial data.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter size-full wp-image-478" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="509" height="412" /></a></p>

6-The next screen asks what field you want to use for the place marker titles. Select <strong>Name</strong> and click <strong>Finish</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-full wp-image-480" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="307" height="286" /></a></p>

7-Like with Carto, we can <strong>click on the three vertical dots</strong> next to the layer to rename the layer. Name the layer <strong>Postmaster Salaries</strong> or a similar descriptive title.

8-My Maps is showing a message that 32 rows in the data could not be drawn on the map. If you have additional time, you can come back and explore this error message. For now, click <strong>Dismiss</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter size-full wp-image-481" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="309" height="41" /></a></p>

9-At the bottom of the pop-up in the top left-hand corner is a <strong>Base map icon</strong> with a dropdown icon. You can explore different available base maps to see what works best with your data. For example, My Maps’s default base map includes topographical data. If that data is not essential for our analysis, a simpler base map (like <strong>Simple Atlas</strong>) can help users focus on the most important aspects of the spatial visualization.

10-<strong>Click on the blue paint roller icon</strong> to open a pop-up with style customization options.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter size-full wp-image-482" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="310" height="267" /></a></p>

11-Click <strong>Uniform style</strong> and click <strong>Group places by</strong>, then select <strong>PM_Salary</strong> under <strong>Style by data column</strong> to color the data points based on salary categories.

12-Based on looking at the legend created in the last step, the number of <strong>Nulls</strong> and <strong>Others</strong> means the default options for this style don’t work effectively for our data.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter size-full wp-image-483" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="307" height="294" /></a></p>

13-Click the <strong>blue paint roller icon</strong> again to reopen the customization pop-up. Change the selection from <strong>Categories</strong> to <strong>Ranges</strong>, and change the number from <strong>4</strong> to <strong>10</strong>. My Maps’s default setting calculates categories for the data, but the <strong>range</strong> option lets us determine a <strong>specific number of range distributions</strong>. In this case, specifying <strong>10</strong> ranges effectively represents our data. You can click on the <strong>color</strong> dropdown to select a <strong>color gradient</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true"><img class="aligncenter size-large wp-image-484" src="https://github.com/kwaldenphd/google-mymaps-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true" alt="" width="676" height="483" /></a></p>

14-Now that our data is grouped and displayed on the map, <strong>click on points</strong> to see how the My Maps pop-up compares to Carto. What are the limitations of this platform compared to Carto? What are the advantages? Where would you go next in your customization or analysis?

&nbsp;

<hr />

## Additional exploration:

<ul>
 	<li>When we uploaded our data to My Maps, an error message said 32 rows could not be shown on the map. Open the data table and explore what patterns or discrepancies you can find for these rows. Why can't the mapping program visualize this data? What would be involved in editing the data to make these rows display on the map?</li>
 	<li>Continue exploring the display options in My Maps. What level of customization or analysis does My Maps provide, compared to Carto?</li>
</ul>

<hr />

# Reflection questions:
<ul>
 	<li>How would you compare Carto and Google Maps as mapping tools for digital history?</li>
 	<li>What are the strengths and weaknesses of each platform?</li>
 	<li>What types of projects or data could you see working best with a specific tool?</li>
</ul>

<hr />

# Introduction to Mapping wrap-up

Now that we’ve mapped Blevins’s data using two different tools, let’s explore <a href="http://cameronblevins.org/gotp/">how he maps this data in the larger project</a>. As you explore the maps, keep in mind Blevins was focused on mapping post offices’ hours of service, rather than postmaster salaries which were the focus of our data.

Be sure to read the “About the Map,” “How to Use,” and “About the Data” sections on the interactive mapping site.  Based on the choices you made about analyzing and visualizing your data in this tutorial, what thoughts or reflections do you have on how Blevins made similar choices, just on a much larger scale.

Read about how Blevins uses this data and spatial analysis to construct a historical argument about <a href="http://www.cameronblevins.org/posts/postal-geography-and-the-golden-west/">Postal Geography and the Golden West</a>, as well as <a href="http://www.cameronblevins.org/posts/the-county-problem-in-the-west/">The County Problem in the West</a>. How did Blevins connect the data used in spatial analysis to a larger historical argument? What role did the data and spatial analysis play in that larger argument?

<hr />

# Final reflection questions:
<ul>
 	<li>What interested you in this data? Would you have been able to find this information and draw conclusions from it without using spatial analysis tools?</li>
 	<li>What questions do you still have about this data? How could you answer them? How could you answer them digitally?</li>
 	<li>Were there any issues we talked about in historical mapping (change over time, error, certainty, etc.) that you think of differently now that you have tried it?</li>
</ul>

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

## Logging in to ArcGIS Online

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_a.png?raw=true" alt="Capture" /></p>

1-Open Firefox or Chrome and navigate to <a href="http://grinnell.maps.arcgis.com/">http://grinnell.maps.arcgis.com/</a> in the web browser.

2-Use the username and password you created after accepting the invitation to sign in.

3- Click the blue <strong>Sign In</strong> button in the middle of the page.

<p align="center"><img class=" size-full wp-image-54 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_b.png?raw=true" alt="Capture_1" /></p>

4-Once logged in, click on <strong>Content</strong> in the menu on the top-left of the page.

<hr />

<blockquote><em>Note: This rest of this tutorial is written using a sample data set. Your data, map, and map layers will look different than the images included in the tutorial.</em></blockquote>

## Creating a New Map

<p align="center"><img class=" size-full wp-image-57 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="Capture_4" /></p>

5-Once in Content, click on Create-Map to start building an interactive online map.

<p align="center"><img class=" size-full wp-image-58 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="Capture_5"  /></p>

6-Add a title, tags, and summary, and click the blue OK icon. Provide information that will help you find and identify the map you're creating. 

<p align="center"><img class=" size-full wp-image-59 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="Capture_6"  /></p>

7-You are now in ArcGIS Online’s map builder interface.

<hr />

## Adding Data to Your Map

8-Download the SampleData.csv file from this repo.

This dataset includes details about where Nirvana gave live performances. [Learn more about this dataset.](https://data.world/ben-pfeifer/nirvana-live-performances)

Open the data file in Excel or another spreadsheet program. What data fields are you seeing?

<p align="center"><img class=" size-full wp-image-60 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_7.png?raw=true" alt="Capture_7"  /></p>

9-Click on the Add icon in the top-left corner of the page, and select Add Layer from File.

10-Click the Browse icon and select the CSV file saved to your Desktop.

<p align="center"><img class=" size-full wp-image-61 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="Capture_8"  /></p>

11-Click the blue Import Layer icon to add the data to your map.

<p align="center"><img class=" size-full wp-image-62 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="Capture_9" /></p>

12-Click the blue Done icon to finish adding data to your map.

<p align="center"><img class=" size-full wp-image-64 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="Capture_11"  /></p>

13-Click the Save icon above the map to save your map.

<hr />

## Customizing Your Map

The default setting for ArcGIS Online is to display the locations in your data without any styling or customization. Hover your cursor over the data layer to see additional customization options. You can use multiple layers to display or highlight different aspects of the data on the map.

### Basemap

<p align="center"><img class=" size-full wp-image-63 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="Capture_10"  /></p>

You can change the background map by click a different option in the Basemap dropdown.

### Legend

<p align="center"><img class=" wp-image-66 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="Capture_13" /></p>

If you want to style points by location, emotion, or another attribute, click on the Change Style icon. Choose an element from your data, and explore the drawing style options.

### Point symbol, color, and size

<p align="center"><img class=" size-full wp-image-69 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_16.png?raw=true" alt="Capture_16"  /></p>

<p align="center"><img class=" size-full wp-image-68 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true" alt="Capture_15"  /></p>

Click on the Change Style icon, and click the blue Options icon.

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

<hr />

14-Explore display options for this data. One layer does not have to communicate all relevant aspects of the data.

<p align="center"><img class=" size-full wp-image-65 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_12.png?raw=true" alt="Capture_12" /></p>

15-Once you have a layer customized, you can copy that layer to continue exploring other display options without losing the customized layer.

16-Rename layers using descriptive titles to keep them organized.

<p align="center"><img class=" size-full wp-image-64 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="Capture_11"  /></p>

17-Save the Web Map regularly to avoid losing any changes.

## Adding Other Data From ArcGIS Online

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_7.png?raw=true" alt="Capture_7"  /></p>

31-Select Add--Search for Layers to bring in data that other users have published to ArcGIS Online.

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_n.png?raw=true"  /></p>

32-Click on My Content to open up a drop-down menu. Select the option to search through ArcGIS Online.

33-Use different key words or terms to find other data that you might want to bring into your map.

## Saving, Sharing, and Printing Your Map

34-Save your map regularly by clicking the Save icon.

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_j.png?raw=true"  /></p>

35-Click the Share icon when you are ready to share your map with other users in the Grinnell organization or the general public.

<p align="center"><img class=" size-full wp-image-72 aligncenter" src="https://github.com/kwaldenphd/ArcGIS-Online-tutorial/blob/DASIL-Workshop/screenshots/Capture_k.png?raw=true" /></p>

36-Click the Print icon to generate a static image with your map and legend that you can save as an image or print to a PDF.

## Carto

Historians have long used spatial analysis, but digital mapping tools have made it possible for historians to explore larger and more complex spatial data sets. Northeastern University historian Cameron Blevins does this in his research on the relationship between state formation, westward expansion, and the U.S. postal service. In this tutorial, we will be using some of the data sets from Blevins’s research to learn more about some of the digital spatial analysis and visualization tools used in historical research.

<hr />

## How Blevins describes his research (from<a href="http://www.cameronblevins.org/research/"> his personal site</a>):

<em>My current project is a spatial history of two of the defining projects of the late nineteenth-century United States: state formation and western expansion. Between the 1860s and the 1890s, the western United States underwent one of the most dramatic reorganizations of people, land, capital, and resources in American history. How did this happen so quickly, and across such a large and inhospitable area? Why were so many people willing and able to move to such shockingly remote places? How did the American state consolidate its control over this vast territory? I argue that the sprawling infrastructure of the U.S. Post holds the key to understanding the speed and scale of western expansion. Gossamer Network uses a database of more than 100,000 post offices <a href="http://cameronblevins.org/gotp">to map the spread of the postal network in the western United States</a>. This presents one of the most comprehensive and detailed spatial renderings of the nineteenth-century state that has ever been assembled.</em>

<em>This analysis leads to a series of new interpretations about the American state and the West. The U.S. Post was the era’s most spatially expansive institution. No other network, public or private, connected so many different people in so many different places across such a large area. It did so by operating what I’ve termed a “gossamer network.” The U.S. Post expanded across space by grafting the public functions of mail service onto the existing operations of private businesses: contracting with a stagecoach company to transport bags of mail, or paying a local businessman to periodically distribute letters from his general store. This flexible, ethereal structure allowed the U.S. Post to expand and contract across remote areas with a stunning speed. Its ability to move in lockstep with Anglo-Americans had enormous consequences for the West, accelerating a pattern of imperial conquest and settler colonialism while serving as the underlying machinery of governance in the region. Gossamer Network sheds new light on the familiar subject of western expansion and forces us to reconsider the very nature of state power during this era.</em>

<hr />

## Preliminary reflection questions:
<ul>
 	<li>What are Blevins’s research questions?</li>
 	<li>Why (and how) is spatial analysis important to addressing those questions?</li>
 	<li>What types of data do you think Blevins might work with for this project?</li>
 	<li>Do you see any potential challenges or limitations in using spatial data as the foundation for this project?</li>
</ul>

<hr />

## Data

1-Download the 1870_Federal_Census_Grinnell_Township.csv file from this GitHub repo. Save the 1870 Federal Census Grinnell Township file to your Desktop.  

Alternatively, you can go to the <a href="http://www.cameronblevins.org/postal-data/">data page</a> of Blevins’s personal site. Under the “Regional Data: Western Post Offices and Postmaster Salaries” heading, download the <strong>1871_PostmasterSalaries CSV file</strong>.

2-Open the file in Microsoft Excel.

3-What fields are represented in the data? What questions do you have about the data?

4-Compare the <a href="https://babel.hathitrust.org/cgi/pt?id=loc.ark:/13960/t3kw65n8k;view=1up;seq=7">original data source</a> and what you see in the Excel table—what differences do you observe in how the data is represented? What types of questions do you think this data might be able to address? What gaps or absences do you notice in the data?

5-Save the file to your <strong>Desktop</strong> as a <strong>CSV</strong>. If Excel displays a warning message when you try to save as a CSV, click <strong>OK</strong> and continue.

<hr />

<blockquote>A note on geocoding:

The process of adding spatial information to data or determining exact coordinates for locations is called geocoding. As you notice in Blevins’s data, the original data source does not include specific geocordinates for every post office location. Historically, gazetteer publications (essentially a phone book with locations and geocoordinates) were used to find place information for spatial data. Best practice for limited data sets is still to use a gazetteer to georeferenced spatial data, and the internet has increased the availability and searchability of gazetteers. However, manual geocoding is not feasible for many larger data sets. A variety of free and paid services offer automated geocoding.</blockquote>

<hr />

## The United States in 1871

One of the challenges in historical spatial analysis is maps, boundaries, and territories change over time. A map of the United States in 1800 looks very different than what we encounter in Google Maps or MapQuest. Explore <a href="https://www.davidrumsey.com/luna/servlet/detail/RUMSEY~8~1~26362~1100036:United-States-&amp;-territories-?sort=Pub_List_No_InitialSort%2CPub_Date%2CPub_List_No%2CSeries_No">a map of the U.S.</a> that was drawn and published in 1871. Not all territories drawn on the map had been granted statehood in 1871. Consult a <a href="https://en.wikipedia.org/wiki/List_of_U.S._states_by_date_of_admission_to_the_Union">chronological list of U.S. states by date of admission to the Union</a> to see what territories on the map would not have been recognized states in 1871.

### Reflection questions:
<ul>
 	<li>Why do you think it is important to understand the historical spatial context for Blevins’s data?  What all do we know about context?</li>
 	<li>How would something like knowing states’ dates of admission to the Union impact how we analyze spatial data?</li>
 	<li>What features on the 1871 map stand out as significant?</li>
</ul>

<hr />

## Carto

<a href="https://carto.com/">Carto</a> is a cloud-computing platform released in 2011 by developer Vizzuality. Written in Ruby and Javascript, Carto is designed to allow businesses to analyze and visualize spatial data without prior or detailed technical GIS knowledge. As we’ll learn in another tutorial, GIS programs like ArcGIS are not always intuitive and user-friendly. Carto was designed as an alternative, with a web-hosted option that doesn’t require a local installation, although Carto is available as <a href="https://github.com/CartoDB/CartoDB">open source software</a>. The short version—users can work with Carto in the browser without needing to set up their own server to host the program. The web-based version of Carto is considered a <a href="https://carto.com/pricing/">“freemium” software</a>—free for some types of users with limited web-based functionality with scaled pricing plans for long-term use. Anyone can register for a 30 day Carto trial, which is what we will be using in this tutorial.

<hr />

6-If you do not already have a Carto account, <a href="https://carto.com/signup/">register</a> for a free 30 day trial. No billing and payment information is required to sign up.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-461" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="335" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-full wp-image-462" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="424" height="211" /></a></p>

7-<strong>Log in</strong> to Carto. Next to your name in the top menu is a <strong>Maps</strong> icon with a dropdown arrow. Select <strong>Your datasets</strong> from the dropdown.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-463" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="381" height="77" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true"><img class="aligncenter size-large wp-image-464" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="" width="676" height="549" /></a></p>

8-Click on the <strong>New Dataset</strong> icon in the upper right-hand corner of the page.

9-You can browse to select the <strong>1871_PostmasterSalary CSV file</strong> from your <strong>Desktop</strong>, or drag and drop it into the upload section of the page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter size-full wp-image-465" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="273" height="98" /></a></p>

10-Click the <strong>Connect Dataset</strong> blue icon in the bottom right-hand corner of the page to upload the dataset to Carto.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter size-large wp-image-466" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="676" height="329" /></a></p>

11-Once your data has been added to Carto, compare how the data was structured in Excel versus how it is structured and described in Carto. What similarities do you notice? What has changed? Why do you think Carto made these changes or added this additional information?

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter size-full wp-image-467" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="181" height="78" /></a></p>

12-Click the blue <strong>Create Map</strong> icon in the bottom right-hand corner of the page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-large wp-image-468" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="676" height="331" /></a></p>

13-Once you’ve created a map, you move into Carto’s <strong>builder environment</strong>. Use the four-step tour to learn more about Carto’s map editing page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true"><img class="aligncenter size-full wp-image-450" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="" width="347" height="398" /></a></p>

14-<strong>Rename the map</strong> by clicking on the three vertical dots next to the <strong>table_1871_postmas… header</strong>. Click <strong>Rename</strong> and change your map’s title to “Postmaster Salaries” or another descriptive phrase. You can also rename the map by double-clicking the title.

15-Let’s explore the map editing page. Use the plus or minus symbols in the bottom left-hand corner of the map to zoom in and out on the map. Double-clicking an area or using your mouse scroll wheel are also ways to zoom in and out.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter size-full wp-image-471" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="324" height="307" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true"><img class="aligncenter size-full wp-image-449" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true" alt="" width="346" height="947" /></a></p>

16-Click on any map point and click on the small light blue pencil icon that appears. Clicking this editing icon shows you that point’s attributes, such as its latitude, longitude, and other descriptive information. If needed, you could edit point data on this screen.

17-To exit looking at data points, click the <strong>Back</strong> arrow in the top left-hand corner of the page.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter size-full wp-image-470" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="306" height="287" /></a></p>

18-Although we are only working with one data layer in this tutorial, many mapping projects work with multiple layers so naming data layers is a useful practice. <strong>Click on the three vertical dots</strong> next to the data set’s title. Click <strong>rename</strong> and enter an appropriate descriptive name for the data set. You can also rename the data set by double-clicking the title.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true"><img class="aligncenter size-full wp-image-451" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true" alt="" width="347" height="946" /></a></p>

19-Click on the <strong>dataset layer</strong> to move into Carto’s <strong>layer pane</strong>. Another brief tour can help you navigate the layer pane, which includes a menu with <strong>Data, Analysis, Style, Pop-Up,</strong> and <strong>Legend</strong> options.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true"><img class="aligncenter size-full wp-image-452" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true" alt="" width="332" height="222" /></a></p>

20-We’ll explore spatial analysis more in a later tutorial, but select <strong>Style</strong> from the layer menu. <strong>Aggregation</strong> offers different ways to visualize your data points on the map, from the default circular points to hexagons to heat maps and time animations. What types of aggregation are most effective for this data set? What types of aggregation do not work for this data set? What aspects of the data are highlighted in different aggregations?

21-The second option in the <strong>Style</strong> menu allows you to change the size and color of your data points. In Carto’s default settings, point size and color is standardized across all data points.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true"><img class="aligncenter size-full wp-image-453" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true" alt="" width="325" height="240" /></a></p>

22-Under <strong>Point Size</strong>, switch the selection from <strong>Fixed</strong> to <strong>By value</strong>, and select <strong>pm_salary</strong>. Sizing points by value selects a data field and sizes points based on how frequently they appear in the dataset.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_17.PNG?raw=true"><img class="aligncenter size-full wp-image-454" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_17.PNG?raw=true" alt="" width="379" height="334" /></a></p>

23-When sizing points by value, you can customize how many buckets (categories) you want to have, as well as how the distribution of those buckets is calculated. Carto’s default setting uses <strong>Quantiles</strong> to calculate bucket distribution, but you can select other ways to calculate those ranges.

24-What happens when you change the <strong>number of buckets</strong>, <strong>min/max values</strong>, or the <strong>way bucket distribution is calculated</strong>? What impact do these choices have on how your data is represented on the map? What factors would you need to consider when making these choices to accurately represent your data and analysis?

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true"><img class="aligncenter size-full wp-image-453" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_16.PNG?raw=true" alt="" width="325" height="240" /></a></p>

25-In addition to sizing points by value, we can also assign colors to points based on their value. Switch the <strong>Point Size</strong> selection back to <strong>Fixed</strong>, and switch the <strong>Point Color</strong> selection from <strong>Solid</strong> to <strong>By Value</strong>. Select the <strong>pm_salary</strong> value to recolor your points based on salary ranges.

26-Like with <strong>Point Size</strong>, Carto gives you the option of selecting your number of buckets and how those bucket ranges are calculated. You can also use one of Carto’s preset color palettes or build your own custom color set using a free online resource like <a href="http://colorbrewer2.org/#type=sequential&amp;scheme=BuGn&amp;n=3">Color Brewer</a>. Carto also gives you the option to change the size of your points (<strong>point size</strong>), the size of your point outline (<strong>stroke size</strong>) and the color of your point outline (<strong>stroke color</strong>).

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true"><img class="aligncenter size-full wp-image-456" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true" alt="" width="344" height="826" /></a></p>

27-Select the <strong>Pop-Up</strong> icon in the layer menu. Pop-Ups include data that displays when you click on a specific map point. In Carto’s default settings, no customized pop-ups appear.

28-Select <strong>Click</strong> to design the pop-up that appears when you click on a map point. Select <strong>Hover</strong> to design the pop-up that appears when you hover over a map point.

29-For <strong>Click</strong> and <strong>Hover</strong>, Carto allows you to determine the size and coloring of the pop-up window, as well as what data fields are displayed (and how they are labeled).

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_20.PNG?raw=true"><img class="aligncenter size-full wp-image-457" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_20.PNG?raw=true" alt="" width="497" height="837" /></a></p>

30-If you wanted to further customize your pop-ups, Carto provides an <strong>HTML view</strong> where you could further customize the style of text in your pop-ups.

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-large wp-image-468" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="676" height="331" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_21.PNG?raw=true"><img class="aligncenter size-full wp-image-458" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_21.PNG?raw-true" alt="" width="111" height="62" /></a></p>

31-Once you are satisfied with the styling of your pop-ups, click the <strong>back</strong> arrow to return to the main editing page. Because Carto is a cloud-based service, it is saving edits as you make them. However, the map project will not be published or shared until you click the <strong>Publish</strong> blue rectangular icon on the bottom left-hand side of the page.

<hr />

## Extra time?

### Making corrections to your data:

As we read in the introduction to this tutorial, this dataset includes spatial information about post offices located in the western United States. You have noticed three map points in the Mediterranean when you loaded the data into Carto. Open the editor for those data points and see what steps are needed to correctly geocode the data.

### Additional features to explore:

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_22.PNG?raw=true"><img class="size-full wp-image-459 aligncenter" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_22.PNG?raw=true" alt="" width="340" height="299" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_23.PNG?raw-true"><img class="size-full wp-image-460 aligncenter" src="https://github.com/kwaldenphd/carto-tutorial/blob/master/screenshots/Capture_23.PNG?raw=true" alt="" width="332" height="233" /></a></p>

In this tutorial, we have been focusing on editing a data layer in Carto. The program also includes tools that let you analyze your data (<strong>Layers-&gt;Analysis</strong>) and add interactive <strong>widgets</strong> for a dynamic public interface.


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

## Other Mapping Tools/Resources

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

## DataBasic: Connect The Dots

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_1.jpg?raw=true" alt="Capture" /></p>

Navigate back to the [DataBasic home page.](https://databasic.io)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_13.png?raw=true" alt="Capture" /></p>

Click on the ConnectTheDots icon to open the ConnectTheDots tool.

As described on the page, “ConnectTheDots shows you how your data is connected by analyzing it as a network. Analyzing the connections between the "dots" in your data is a fundamentally different approach to understanding it. This tool shows you a network diagram to reveal those links, and gives you a high level report about what your network looks like.”

<blockquote>What is a network? 

According to Miriam Posner, networks are “a finite set (or sets) of actors and the relations defined on them. It consists of three elements: (1) a set of actors; (2) each actor has a set of individual attributes; and (3) a set of ties that defines at least one relation among actors.” A network graph is “a common way to visually represent social networks, consisting of two dimensions: actors and relations (also called nodes and edges). Nodes are the entities in graph (also called vectors)..[edges] are the relationships between nodes.” 

Learn more via the [PDF included in this Repository.](https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/Posner_SocialNetworkAnalysisGlossary.pdf) </blockquote>

For ConnectTheDots, our network data is formatted as a list of edges, or connections, between a source and target node. 

<table>
  <tr>
    <th>source</th>
    <th>target</th>
  </tr>
  <tr>
    <td>Daddy Yankee</td>
    <td>May-Be</td>
  </tr>
  <tr>
    <td>Daddy Yankee</td>
    <td>May-Be</td>
  </tr>
  <tr>
    <td>Daddy Yankee</td>
    <td>Glory</td>
  </tr>
  <tr>
    <td>Daddy Yankee</td>
    <td>Glory</td>
  </tr>
  <tr>
    <td>Daddy Yankee</td>
    <td>Glory</td>
  </tr>
  <tr>
    <td>Daddy Yankee</td>
    <td>Glory</td>
  </tr>
  <tr>
    <td>Daddy Yankee</td>
    <td>Blacka Nice</td>
  </tr>
  <tr>
    <td>Daddy Yankee</td>
    <td>Blacka Nice</td>
  </tr>
  </table>

In this tutorial, we will be using a list of nodes and edges of the artists featured in the Barrio Fino album.

Download the Barrio_Fino_Network_Data.csv file included in this repository. Save the file to your desktop.

  
<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_14.png?raw=true" alt="Capture" /></p>

ConnecTheDots gives you the option to use sample network data, paste your own data, or upload a file.

Upload the SPN320_BarrioFino_NetworkData.csv file and click the Graph icon.

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

- What do you notice about Daddy Yankee’s collaboration practices in the Barrio Fino album through the results displayed in ConnectTheDotes?
- How does ConnectTheDots’s results shape your understanding of the album’s content?
- What additional questions do you have about the album?

## Palladio


As the authors of <em>Exploring Big Historical Data </em>outline in Chapter 7, historians can use a wide range of software programs and digital tools for network analysis and network visualizations. In this tutorial, we will use a combination of Palladio (a web-based GUI interface), NetworkX (a Python package) and Gephi (an GUI software) to explore various aspects of network analysis and visualization.

<hr />

## Network Analysis using Palladio

<em>Developed through a National Endowment for the Humanities Implementation grant, <a href="http://hdlab.stanford.edu/palladio/">Palladio</a> was released by Stanford University in June 2016. Designed for historians and other digital humanities scholars, Palladio is a web-based application that allows users to analyze data that includes time and network features and display that data via maps, timelines, other types of visualizations, and gallery exhibits. Designed as a browser-based GUI interface, Palladio works well for quick visualizations and offers limited interactive export options.</em>

<hr />

## Data

1-We will be working with sample networked data sets based on the <a href="http://www.oxforddnb.com/">Oxford Dictionary of National Biography</a> and the <a href="http://www.sixdegreesoffrancisbacon.com/">Six Degrees of Francis Bacon</a> project. These data sets include a list of names and relationships for early seventeenth-century Quakers.

2-Download the the quakers_nodelist and quakers_edgelist CSV files from this repository 

3-Save the files to your Desktop.

4-Open these files in Microsoft Excel to explore the data structure.

<blockquote>
<ul>
 	<li><em>What types of historical figures are represented? </em></li>
 	<li><em>How are they described in the nodelist data? </em></li>
 	<li><em>What additional questions do you have about the individuals who will be represented as nodes? </em></li>
 	<li><em>How is the edgelist data structured?</em></li>
 	<li><em>Based on a preliminary scan of the nodelist and edgelist CSV data, what types of networks do you think this data might illuminate? </em></li>
 	<li><em>Are there gaps, silences, or alternative networks that are not accounted for in the data?</em></li>
</ul>
</blockquote>

<hr />

## Loading data into Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-498" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="334" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-large wp-image-499" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="676" height="454" /></a></p>

5-Open the <a href="http://hdlab.stanford.edu/palladio/">Palladio home page</a> in Chrome or Firefox. Click on the <strong>Start</strong> icon to open a new project.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-500" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="876" height="764" /></a></p>

6-<strong>Drag and drop</strong> the nodelist CSV into the <strong>Load csv</strong> window.

7-Click the <strong>Load</strong> icon to load the data into Palladio.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true"><img class="aligncenter size-full wp-image-486" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="" width="502" height="531" /></a></p>

8-Click on <strong>“Untitled”</strong> to relabel the table as <strong>Node_List</strong> or another descriptive name. You may notice Palladio has a red dot next to the Historical Significance field. <strong>Click on the red dot</strong> to open the <strong>Edit dimension</strong> pop-up window.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter size-full wp-image-487" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="897" height="636" /></a></p>

9-Palladio requires you to verify special or unexpected characters in the data fields—in this case, a comma in the “maker of clocks, watches, and barometers” role. Click <strong>Verify special characters </strong>icon, then click <strong>Done</strong>.

10-Back on the <strong>Data screen</strong>, you can see the error has been resolved, and Palladio has also automatically described your data fields as a text, date, or number. Before visualizing this data, we want to also load the edgelist data.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter size-full wp-image-488" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="910" height="636" /></a></p>

11-Click on the <strong>Name field</strong> to open the <strong>Edit dimension</strong> window again.

12-Under <strong>Extension</strong>, click the <strong>Add a new table</strong> icon.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter size-full wp-image-489" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="903" height="571" /></a></p>

13-<strong>Drag and drop</strong> the <strong>edgelist CSV file</strong> into the <strong>Add new table</strong> area. Click the <strong>Load</strong> icon.

14-Palladio returns to the <strong>Edit dimension</strong> window and tells you out of the 119 names included in the nodelist table, 78 also appear in the edgelist table.

15-Click the <strong>Done</strong> icon to add the new table to your Palladio project.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter size-large wp-image-490" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_8.PNG?rawtrue" alt="" width="676" height="342" /></a></p>

16-The new <strong>Untitled</strong> table will appear in your <strong>Data</strong> tab. Rename the new table <strong>Edge_List</strong> or another descriptive name. Click on <strong>Provide a title to this project</strong> to rename the project <strong>Network_Tutorial</strong> or another descriptive name.

<hr />

## Analyzing and Visualizing Data in Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter size-full wp-image-491" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="391" height="55" /></a></p>

17-Palladio does offer mapping functionality, but our data does not contain spatial information. Click on the <strong>Graph tab</strong> to start building a network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter size-full wp-image-492" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="614" height="364" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter size-large wp-image-493" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="676" height="314" /></a></p>

18-Select <strong>Source</strong> as the <strong>Source dimension</strong> and <strong>Target</strong> as the <strong>Target dimension</strong>, and Palladio will generate a network graph.

19-What do you notice about the networks generated in Palladio? How would you describe these networks using the terminology outlined in Chapter 6 of <em>Exploring Big Historical Data</em>? What surprises you about the networks, or what additional questions do you have?

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true"><img class="aligncenter size-large wp-image-495" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="" width="676" height="310" /></a></p>

20-Check the bock next to <strong>Size nodes</strong> and select <strong>Number of Edge_List</strong> for <strong>According to</strong>. These changes sized our nodes based on where they appear in the edge_list data. Select <strong>Number of Node_List</strong> for <strong>According to</strong>, and the nodes are sized according to where they appear in the node_list data.

21-How do these graphs differ? What do they highlight or emphasize about the data? What questions do you have?

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true"><img class="aligncenter size-large wp-image-496" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true" alt="" width="676" height="301" /></a></p>

22-We can choose other <strong>Source</strong> and <strong>Target</strong> fields to alter the network visualization. For example, choosing <strong>Gender</strong> as <strong>Source</strong> and <strong>Name</strong> as <strong>Target</strong> reveals the gender ratio of the names represented in the data.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true"><img class="aligncenter size-large wp-image-497" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_15.PNG?raw=true" alt="" width="676" height="306" /></a></p>

23-Choosing <strong>Gender</strong> as <strong>Source</strong> and <strong>Historical Significance</strong> as <strong>Target</strong> highlights the gendering of historical roles in the data set.

24-Palladio offers additional facet, timeline, and timespan analysis via the buttons on the bottom of the page. Feel free to explore these additional functions on your own.

## Gephi

In the last tutorial, we used a browser-based tool to visualize and briefly analyze networks in the Quaker data. While Palladio is useful for preliminary visualization of network data, it offers limited options for calculating or analyzing more advanced network metrics. <a href="https://github.com/gephi/gephi">Gephi</a> is an open-source network analysis and visualization software created by students at the University of Technology of Compiègne in 2008. The Gephi Consortium, which supports the ongoing development and documentation for Gephi, is a non-profit corporation supported by members that include SciencesPo, Linfluence, WebAtlas, and Quid. Gephi runs on Linux, Windows, and macOS operating systems and is available in 9 different languages.

<hr />

## Installing Gephi

To download Gephi on your own computer, go to Gephi’s <a href="https://gephi.org/users/download/">download page</a> and select the correct version for your operating system.

<hr />

## Data

1-In this tutorial, we will be working with data about Grinnell faculty, the subject of their terminal degree, where they received their terminal degree, and when they were hired by the College.

2-Download the <strong>GC_faculty_nodesheet</strong> and <strong>GC_faculty_edgesheet</strong> CSV files to your Desktop. Open the files in Microsoft Excel to explore the data structure.
<ul>
 	<li>What types of institutions and College instructors are represented?</li>
 	<li>How are they described in the nodelist data?</li>
 	<li>What additional questions do you have about the individuals and degree-granting institutions that will be represented as nodes?</li>
 	<li>How is the edgelist data structured?</li>
 	<li>Based on a preliminary scan of the nodelist and edgelist CSV data, what types of networks do you think this data might illuminate?</li>
 	<li>Are there gaps, silences, or alternative networks that are not accounted for in the data?</li>
</ul>
3-Save these files to your desktop as “<strong>Grinnell_nodelist</strong>” and “<strong>Grinnell_edgelist</strong>” or another descriptive file name.

<hr />

## Loading Data into Gephi

4-Open <strong>Gephi</strong> by selecting it from <strong>Start-&gt;All Programs-&gt;Gephi</strong> or the <strong>Desktop icon</strong>.

5-Click the <strong>X</strong> in the top right-hand corner of the <strong>Welcome</strong> popup window.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture.PNG?raw=true" alt="" width="840" height="473" /></a></p>

6-Click <strong>File-&gt;Import Spreadsheet</strong> and navigate to the <strong>Desktop</strong> where the <strong>nodelist and edgelist CSV files</strong> are saved on your computer.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture2.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture2.PNG?raw=true" alt="" width="843" height="500" /></a></p>

7-Select the <strong>nodelist</strong> file, make sure <strong>Comma</strong> is selected as <strong>Separator</strong>, <strong>Nodes</strong> table is selected under <strong>Import as</strong>, and <strong>UTF-8 </strong>under <strong>Charset</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture3.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture3.PNG?raw=true" alt="" width="845" height="498" /></a></p>

8-Click <strong>Next</strong>. Leave the default settings on the <strong>Import settings (2 of 2)</strong> popup, and click <strong>Finish</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture4.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture4.PNG?raw=true" alt="" width="662" height="460" /></a></p>

9-Select <strong>Undirected</strong> for <strong>Graph Type</strong>, and switch the default selection from <strong>New workspace</strong> to <strong>Append to existing workspace</strong>.

10-Click <strong>OK</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture5.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture5.PNG?raw=true" alt="" width="840" height="475" /></a></p>

11-Your node data is now loaded in the <strong>Data Laboratory tab</strong> in Gephi.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture7.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture7.PNG?raw=true" alt="" width="763" height="114" /></a></p>

12-Click <strong>Import Spreadsheet</strong>, and select the CSV with your edgelist data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture8.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture8.PNG?raw=true" alt="" width="824" height="493" /></a></p>

13-Make sure <strong>Comma</strong> is selected as <strong>Separator</strong>, <strong>Edges</strong> table under <strong>Import as</strong>, and <strong>UTF-8</strong> under <strong>Charset</strong>.

14-Click <strong>Next</strong>.

15-Leave the default settings on the <strong>Import settings (2 of 2)</strong> window and click <strong>Finish</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture9.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture9.PNG?raw=true" alt="" width="663" height="457" /></a></p>

16-Make sure <strong>Undirected</strong> is selected as <strong>Graph Type</strong>, and switch the default selection from <strong>New workspace</strong> to <strong>Append to existing workspace</strong>.

17-Click <strong>OK</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture10.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture10.PNG?raw=true" alt="" width="840" height="472" /></a></p>

18-Now our nodes and edges data has been imported in Gephi.

19-Click <strong>File-&gt;Save</strong> to save your project. Label the Gephi file “<strong>Network_Tutorial</strong>” or another descriptive name.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture11.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture11.PNG?raw=true" alt="" width="511" height="105" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture12.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture12.PNG?raw=true" alt="" width="840" height="472" /></a></p>

20-Click on the <strong>Overview</strong> tab to see Gephi’s default visualization of your network data.

21-As you probably noticed, the default visualization is an interesting connection of nodes and edges, but doesn’t do much to help us more fully understand and analyze our data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture14.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture14.PNG?raw=true" alt="" width="366" height="141" /></a></p>

22-Click on <strong>Choose a layout</strong> under the <strong>Layout panel</strong> to select how Gephi displays your nodes and edges.

23-Gephi uses a variety of layout algorithms to determine the shape of network graphs. These different layouts algorithms highlight different aspects or features of your data.

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

24-<strong>Label Adjust, Noverlap, Expansion, and Contraction</strong> make graphic adjustments to how your data displays, rather than using an underlying algorithm to change the structure of the network visualization.

25-<strong>Select different Layout options</strong> and click the <strong>Run</strong> icon to see how the different algorithms and settings change the visualization of your data. Click the <strong>Stop</strong> icon to stop the layout operation.

26-What Layout option(s) do you prefer, and why? How do different Layout options impact the visualization of your data? How could different Layout options be useful to answer different types of research questions?

<hr />

## Calculating Network Metrics in Gephi

27- As a GUI interface, Gephi allows us to calculate a variety of statistics without having to run the back-end code or use a library like NetworkX (which we will try next time).

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture15.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture15.PNG?raw=true" alt="" width="324" height="617" /></a></p>

28-The <strong>Statistics panel</strong> gives you the option to run a number of different calculations on your network data.

29-While Gephi allows us to easily perform these calculations, the program doesn’t automatically tell us what these measures mean or how they are calculated.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture16.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture16.PNG?raw=true" alt="" width="701" height="603" /></a></p>

30-The HTML report in the pop-up window that displays after you run a <strong>Statistics calculation</strong> gives you a graph of the data calculation, and sometimes the source for the algorithm used to calculate the statistic.

31-Consult <a href="https://github.com/gephi/gephi/wiki/Statistics">Gephi’s GitHub repository</a> for more information on these statistics.

32-Click <strong>Run</strong> for each of the options under <strong>Statistics</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture19.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture19.PNG?raw=true" alt="" width="840" height="473" /></a></p>

33-If you click on the <strong>Data Laboratory tab</strong>, you will see these calculated statistics have been added to your network data.

34-What do these statistics tell you about your network? How do these statistics help you understand your network data more deeply? What questions do you have about the network data or these calculations?

<hr />

## Customizing a Network Visualization in Gephi

35-Select <strong>Noverlap</strong> for your <strong>Layout</strong> so your nodes and edges don’t overlap as you are exploring display customization options.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture21.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture21.PNG?raw=true" alt="" width="840" height="655" /></a></p>

36-The <strong>border icons in the Graph panel</strong> allow you to customize the display of your network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture22.PNG?raw=true"><img class="size-full wp-image-196 alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture22.PNG?raw=true" alt="" width="28" height="24" /></a></p>

37-Click on the <strong>Show Node Labels icon</strong> to display the node labels. You can change the size of text for your labels by using the slider to the right of “Arial Bold, 32.”

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture24.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture24.PNG?raw=true" alt="" width="359" height="362" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture23.PNG?raw=true"><img class="alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture23.PNG?raw=true" alt="" width="22" height="29" /></a></p>

38-You can also click on the <strong>Attributes icon</strong> to customize what data fields display as part of your labels.

39-While your nodes now have labels, the large number of nodes and edges makes it difficult to differentiate or discern various attributes about our network data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture20.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture20.PNG?raw=true" alt="" width="347" height="110" /></a></p>

40-The <strong>Appearance panel</strong> allows you to customize the color, size or weight, and labels for your nodes and edges. Changing the coloring or sizing of nodes in the Appearance panel can help make our network visualization more meaningful.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture26.PNG?raw=true"><img class="alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture26.PNG?raw=true" alt="" width="24" height="25" /></a></p>

41-Select the <strong>Size icon  </strong>to change the default size of your nodes. You can explore different sizes, but 3 works well with this dataset. Click the <strong>Apply icon</strong> to change the setting for your network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture27.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture27.PNG?raw=true" alt="" width="349" height="330" /></a></p>

42-You can also rank the size of nodes based on one of the network metrics you calculated in the Statistics panel.

43-Click the <strong>Ranking icon</strong> in the Appearance panel, and select <strong>Degree</strong> from the dropdown menu. Click <strong>Apply</strong>.

44-Ranking our node size by degree determines the size of a node based on its degree of centrality (or connectedness). Nodes with higher numbers of connections appear larger, and nodes with lower numbers of connections are smaller.

45-What changes did you notice in your network visualization after sizing nodes by degree? How does changing the size of nodes impact your understanding of the network data? What do you see in the network data after this change that you weren’t able to see before?

46-You can change the minimum and maximum node size, and also select different statistics to use for determining node size.

47-Explore these different settings and options to see how different node size calculations shape your understanding of the network data.

48-Save your project.

<hr />

## Exporting Networks

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Picx.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Picx.png?raw=true" alt="" width="244" height="264" /></a></p>

49-Click <strong>File-&gt;Export</strong> to save your project as a static image (SVG, PNG, PDF) or network file (CSV, GDF, GEXF, GraphML, Pajek Net).

50-You can learn more about the different export options on <a href="https://gephi.org/users/supported-graph-formats/">Gephi’s website documentation</a>.

51-Step 47 in this tutorial had you experiment with display customization settings.

52-Return to the visualizations you explored in that step, and export those you find useful or interesting as PNG files.

## Other Network Tools/Resources

NetworkX: https://github.com/kwaldenphd/NetworkX-tutorial

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
    * Python
  * Interactive
    * Palladio
    * Python (`networkx` and `pyvis`)

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
