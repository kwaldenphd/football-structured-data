# Lab #2 (Structured Data): Exploratory Data Analysis/Visualization

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Section Table of Contents

- [Files](#files)
- [Exploratory Data Analysis](#exploratory-data-analysis)
  * [DataBasic: WTFcsv](#databasic-wtfcsv)
  * [Spreadsheet Programs](#spreadsheet-programs)
    * [Microsoft Excel](#microsoft-excel)
    * [Tableau](#tableau)
  * [Oh, the Places You Could Go!](#oh-the-places-you-could-go)
- [General Discussion/Reflection Questions](#general-discussionreflection-questions)

# Files

We'll be using three sample datasets in the Exploratory Data Analysis section of the lab.

`ND_Directory_Cleaned_Geography.csv` (*[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/ND_Directory_Cleaned_Geography.csv), [Google Drive](https://drive.google.com/file/d/1x35ml-UUykUnMUXUjtI3VjTvHMT3UCS7/view?usp=sharing)*) represents a data structure based on the 1922-1923 student directory. Fields in the dataset include:
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

`combined_nd_rosters.csv` (*[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/combined_nd_rosters.csv), [Google Drive](https://drive.google.com/file/d/1LpT-mjNxvvmqsDV0pFmFBFvb8PSwJiTj/view?usp=sharing)*) represents a data structure scraped from Sports Reference's Notre Dame college football season roster pages. Fields in the dataset include:
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

`combined_nd_schedules_cleaned.csv` (*[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/combined_nd_schedules_cleaned.csv), [Google Drive](https://drive.google.com/file/d/15U5nNbKX-BfIWO4CTCeabit7mdokf9SV/view?usp=sharing)*) represents a data structure scraped from Sports Reference's Notre Dame college football season results pages. Fields in the dataset include:
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

# Exploratory Data Analysis

From [Wikipedia](https://en.wikipedia.org/wiki/Exploratory_data_analysis): "In statistics, exploratory data analysis is an approach of analyzing data sets to summarize their main characteristics, often using statistical graphics and other data visualization methods...EDA is for seeing what the data can tell us beyond the formal modeling or hypothesis testing task."

To think about this another way, "the purpose of EDA is to use summary statistics and visualizations to better understand data, and find clues about the tendencies of the data, its quality and to formulate assumptions and the hypothesis of our analysis" (Andrew Andrade and Lukasz Golab, ["Exploratory Data Analysis"](https://datascienceguide.github.io/exploratory-data-analysis) *Data Science Guide*)

## DataBasic: WTFcsv

1- According to [its website,](https://databasic.io) “DataBasic is a suite of easy-to-use web tools for beginners that introduce concepts of working with data. These simple tools make it easy to work with data in fun ways, so you can learn how to find great stories to tell.” DataBasic is developed and supported by MIT’s [Center for Civic Media](https://civic.mit.edu/) and Emerson College’s [Engagement Lab.](https://elab.emerson.edu/)

*Note: Images and screenshots included in this tutorial are from a sample corpus and do not reflect what you will see working with different texts*

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_1.jpg?raw=true" alt="Capture" /></p>

2- Navigate to https://databasic.io/ in a web browser (preferably Chrome). Click on the `WTFcsv` icon to open the WTFcsv tool.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_1.png?raw=true" alt="Capture" /></p>

3- As described on the page, "WTFcsv tells you WTF is going on with your .csv file. Data arrives at your doorstep in the form of a spreadsheet but how do you find a story in rows and columns? WTFcsv provides the first step by characterizing each column's data type and contents so that you can ask more questions."

4- `WTFcsv` gives you the option to use a sample file or upload your own file. Click on the `Upload a file` icon and select a sample dataset. The lab procedure is going to used the `combined_nd_schedules_cleaned.csv` file, but you can use any of the sample datasets as we move through this section of the lab.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_2.png?raw=true" alt="Capture" /></p>

5- Click `Analyze` to analyze the dataset.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_3.png?raw=true" alt="Capture" /></p>

6- The WTFcsv results include summary information about the entire dataset as well as a summary view of each field. For the whole dataset, we can tell the number of rows and columns.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_4.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_5.png?raw=true" alt="Capture" /></p>

7- For each column, we can see the data type (the icon in the top-left corner of that column's tile), a summary visualization for that column (the default tile view), and additional metadata for that column (available by clicking on the circle `i` icon in the top-right corner of the tile).

<blockquote>What is metadata? In the words of information and infrastructure scholar Janet Evans, metadata is "data about data" (Evans, <a href="https://inventingthemedium.com/glossary/">Inventing the Medium: Principles of Interaction Design as a Cultural Practice</a>, glossary). Within WTFcsv, metadata is described as "[summarizing] basic information about your data."</blockquote>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_5.png?raw=true" alt="Capture" /></p>

8- Looking at the column visualization for `Day`, we can see this is a string field (circle icon in the top-left), and WTFcsv has given us a bar chart showing the counts for each unique column value.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_6.png?raw=true" alt="Capture" /></p>

9- Looking at metadata for `Day` column tile (click the circle `i` icon in the top-right of the tile), we can see this is a string field (a field that includes text characters), the maximum string length, the number of unique values, and the number of entries for the most frequently occurring values.

10- We can go back to the column visualization by clicking on the chart icon in the top-right of the tile.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_4.png?raw=true" alt="Capture" /></p>

11- We can look at the column visualization for `Time` and see it is a time field (clock icon in the top-left), and WTFcsv has given us a line plot showing the number of rows for each time value.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_7.png?raw=true" alt="Capture" /></p>

12- We can look at the metadata for the `Time` column (click the circle `i` icon in the top-right of the tile) and see the smallest and largest values in this field, as well as the number of rows with missing data (or `NA` values) and the number of unique values.

13- Continue exploring the results for the sample dataset you uploaded. Or, upload and explore another sample dataset.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_8.png?raw=true" alt="Capture" /></p>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/Fig_9.png?raw=true" alt="Capture" /></p>

14- You can also click on the arrow icon next to the page title to get a temporary link to share your results. This tool does not include an image export option for specific visualizations- screenshots are your best option for capturing these visuals.

### WTFcsv Discussion and Reflection Questions

- What do you notice about the results for this dataset (or these datasets) displayed in WTFcsv?
- How does the tool's results shape your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis tools/approaches highlighted in the tool?
- Other comments/questions/observations

## Spreadsheet Programs

15-Most contemporary spreadsheet programs include some support for data analysis and visualization. Folks can choose to explore either Microsoft Excel or Google Sheets for this section of the lab- you're not expected to use both.

### Microsoft Excel

16-Microsoft Excel is a proprietary spreadsheet program that is part of the Microsoft Office (or Office365) suite of tools/programs. The Microsoft Office suite is available via campus computers and the virtual computer lab.
- [Campus Computer Labs](https://inside.nd.edu/task/all/computerlabs)
- [Virtual Computer Lab](https://inside.nd.edu/task/all/virtual-computer-lab)

17-IT also provides [free access to the Office suite through Office365](https://inside.nd.edu/task/all/office-365-portal), which includes an option to download and install on your local machine.

18-A few starting tutorials for visualizing data in Microsoft Excel:
- [Microsoft Support](https://support.microsoft.com/en-us/office/import-and-analyze-data-ccd3c4a6-272f-4c97-afbb-d3f27407fcde#ID0EBBD=Charts)
- [Duke University Library Guide](https://guides.library.duke.edu/excel/visualization)
- [Geeks For Geeks](https://www.geeksforgeeks.org/data-visualization-in-excel/)
  * *YouTube and strategic web searching will also surface useful resources!*

19-Microsoft Excel also supports more advanced data processing work through PivotTables & PivotCharts. A few starting points:
- [Microsoft Support](https://support.microsoft.com/en-us/office/create-a-pivottable-to-analyze-worksheet-data-a9a84538-bfe9-40a9-a8e9-f99134456576)
  * *YouTube and strategic web searching will also surface useful resources!*

### Google Sheets

20-[Google Sheets](https://www.google.com/sheets/about/) is a proprietary web-based spreadsheet program that is part of the Google product suite. ND students have access to Google products through the campus license (logging in with your ND username and password).

21-A few starting tutorials for visualizing data in Google Sheets:
- [Google Support](https://support.google.com/docs/answer/190718?hl=en)
- [Ablebits](https://www.ablebits.com/office-addins-blog/make-charts-google-sheets/)
- [Spreadsheet Point](https://spreadsheetpoint.com/google-sheets-charts-guide/)
  * *YouTube and strategic web searching will also surface useful resources!*

### Spreadsheet Program Discussion/Reflection Questions

22-Spend some time (10-15 minutes as a starting point) exploring at least one of the sample datasets for this lab in a spreadsheet program, thinking about options for analysis and visualization

23-Discussion/reflection questions:
- How does working in a spreadsheet program shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

## Tableau

24-[Tableau](https://www.tableau.com) is a software company founded in Silicon Valley in 2003. Developed by researchers affiliated with Stanford University’s Computer Science Department, Tableau is a commercialized application of academic research. Represented as DATA on the New York Stock Exchange after a 2013 initial public offering, Tableau reported $877 million in revenue in <a href="s1.q4cdn.com/149179428/files/doc_financials/2017/FY2016-Annual-Report.pdf">the 2017 fiscal year</a>. Most often deployed in business environments, Tableau Desktop is a subscription-based data analysis and visualization software. Tableau Server and Tableau Online offer subscription-based web-publishing options for making data and interactive visualizations available on the web. Tableau Public offers limited Tableau Desktop functionality with some options for uploading visualizations through the Tableau Public website.

25-To get started, you'll need to download the free version of Tableau (Tableau Public) on your personal computer. Head to https://public.tableau.com/ in a web browser and enter your email to download the program. It's a large program, so be prepared for the installation process to take some time.
- NOTE: Mendoza students in the Business Analytics program have access to Tableau through the [Mendoza virtual computer lab](https://inside.nd.edu/task/all/virtual-computer-lab-mendoza-anaytics).

26-Excel workbooks that include multiple sheets folks can explore in Tableau:
- [Download from GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Football_Lab2_Combined_Workbook.xlsx)
- [Download from Google Drive](https://docs.google.com/spreadsheets/d/12LogN6lkr5yfG3tbs9SAdOO6YvuYqP0CkQVkHqQwONQ/edit?usp=sharing)
  * Click `File` --> `Download` --> `Microsoft Excel (.xlsx)`

27-A few starting places for Tableau Public tutorials:
- Tableau Public Team, "[A Beginner's Guide to Tableau Public](https://www.tableau.com/blog/beginners-guide-tableau-public)" *Tableau* (23 September 2022)
- Tableau, "[Introduction to Tableau Public](https://youtu.be/iT1iHLGawIM)" *YouTube* (25 March 2013)
- Miriam Posner, ["Getting started with Tableau Public"](http://miriamposner.com/classes/dh201w19/tutorials-guides/data-visualization/getting-started-with-tableau-public/) tutorial for Winter 2019 "Digital Humanities 201" class
- Tableau Public, ["How-To Videos and Resources"](https://public.tableau.com/en-us/s/resources)
  * *YouTube and strategic web searching will also surface useful resources!*

## Tableau Discusion/Reflection Questions

28-Spend some time (10-15 minutes as a starting point) exploring at least one of the sample datasets for this lab in a spreadsheet program, thinking about options for analysis and visualization

29-Discussion/reflection questions:
- How does working in Tableau shape your understanding of the data?
- What types of visualizations (or aggregations) were you able to generate in Tableau?
- How could those visualizations shape or impact your understanding of the data?
- What additional questions do you have about this data (or these datasets)? Where would you go next with exploring this dataset using some of the analysis or visualization tools/approaches?
- Other comments/questions/observations

## Oh, the Places You Could Go!

In addition to the graphical-user-interface (GUI) based tools covered in the previous sections of the lab, we can also apply these methods using programmatic workflows (Python & R).

[Click here](https://github.com/kwaldenphd/football-structured-data/blob/main/eda-programming.md) to open this section of the lab.

## General Discussion/Reflection Questions

- Thinking holistically across the data analysis/visualization tool(s) you interacted with, what questions were you interested in asking or exploring about the sample data (or datasets)?
- How did using these tools shape your understanding of the data you worked with?
- Where would you go next with some of these analysis/visualization tools?
  * What questions or topics would you want to explore using the sample datasets?
  * Or, what other types of information/data related to ND football would you want to work with?
- Other comments/questions/observations
