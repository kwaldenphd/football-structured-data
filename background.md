# Lab #2 (Structured Data): Background, University Archives, and Sample Datasets

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

**Section table of contents**
- [Background](#background)
- [University Archive Digital Collections](#university-archive-digital-collections)
- [Sample Datasets](#sample-datasets)
  * [Directories](#directories)
  * [Football Rosters](#football-rosters)
  * [Football Schedules](#football-schedules)
  * [Knute Rockne Coaching Tree](#knute-rockne-coaching-tree)
  * [Things to Take Away From This Section](#things-to-take-away-from-this-section)

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

- Initial OCR output (`DIR_1922_1923.txt`) *[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/DIR_1922_1923.txt), [Google Drive](https://drive.google.com/file/d/1u7lk7WAFCU_CCUMqW83ANyN00tFEiRr-/view?usp=sharing)*
- First iteration of OpenRefine output (`ND_Directory_Raw.csv`) *[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/ND_Directory_Raw.csv), [Google Drive](https://drive.google.com/file/d/1BRi8A6O_TFm2Y_Mt7Ek2y4rQLnIMnYa4/view?usp=sharing)*
- Second iteration of OpenRefine output (`ND_Directory_Cleaned.csv`) *[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/ND_Directory_Cleaned.csv), [Google Drive](https://drive.google.com/file/d/1cuF_hhyh3QfwkevHlXX2YGkLaxbayjuG/view?usp=sharing)*
- Excel output with merged geographic data (`ND_Directory_Cleaned_Geography.csv`) *[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/ND_Directory_Cleaned_Geography.csv), [Google Drive](https://drive.google.com/file/d/1x35ml-UUykUnMUXUjtI3VjTvHMT3UCS7/view?usp=sharing)*

Big picture steps for this workflow:
- Scrape plain text from the directory using Optical Character Recognition (OCR) in Python
- Clean/wrangle/restructure data using OpenRefine
- More data cleaning/wrangling in OpenRefine (using a lot of regular expressions)
- Data wrangling in Excel to incorporate latitude/longitude information for mapping

[Click here](https://drive.google.com/file/d/16K9-5dcEqkKXqxuJ_lo5kNEIx8mkFBP4/view?usp=sharing) to access the Jupyter Notebook for this OCR workflows via Google Colab.

### OpenRefine

As described in Library Carpentry's ["Introduction to OpenRefine"](https://librarycarpentry.org/lc-open-refine/01-introduction/index.html):

<em>OpenRefine is described as 'a power tool for working with messy data' (<a href="http://web.archive.org/web/20141021040915/http://davidhuynh.net/spaces/nicar2011/tutorial.pdf">David Huynh</a>) - but what does this mean? It is probably easiest to describe the kinds of data OpenRefine is good at working with and the sorts of problems it can help you solve. OpenRefine is most useful where you have data in a simple tabular format such as a spreadsheet, a comma separated values file (csv) or a tab delimited file (tsv) but with internal inconsistencies either in data formats, or where data appears, or in terminology used. OpenRefine can be used to standardize and clean data across your file. 
  
It can help you:
- Get an overview of a data set
- Resolve inconsistencies in a data set, for example standardizing date formatting
- Help you split data up into more granular parts, for example splitting up cells with multiple authors into separate cells
- Match local data up to other data sets, for example in matching local subjects against the Library of Congress Subject Headings
- Enhance a data set with data from other sources
  
Some common scenarios where you might use OpenRefine include:
- Where you want to know how many times a particular value (name, publisher, subject) appears in a column in your data
- Where you want to know how values are distributed across your whole data set
- Where you have a list of dates which are formatted in different ways, and want to change all the dates in the list to a single common date format."</em>

OpenRefine tutorials/resources:
- [Prof. Walden's OpenRefine tutorial](https://github.com/kwaldenphd/tidy-data-principles/blob/main/README.md#data-wrangling-using-openrefine)
- [Library Carpentry's Open Refine tutorial](https://librarycarpentry.org/lc-open-refine/)

Other data cleaning/wrangling resources:
- [Library Carpentry "Tidy Data for Librarians"](https://librarycarpentry.org/lc-spreadsheets/)

## Football Rosters

Online sports data provider Sports Reference includes specific college football data resources.

Take a look at [their page for Notre Dame's 1924 team](https://www.sports-reference.com/cfb/schools/notre-dame/1924.html).

Discussion Questions:
- What parts of information on this page would you want to work with as structured data?
- What types of analysis/visualization or exploration would you be able to do with this resource as structured data?
  * What questions or topics would you be able to explore using data from this resource? 
- Other comments/questions about this source as structured data

### Football Rosters Data Processing Overview

Prof. Walden has [built out a Jupyter Notebook](https://drive.google.com/file/d/1u2kKRaZj_S3CRfWu4vF2OZTOcZ8UAPw8/view?usp=sharing) that scrapes the rosters into a combined CSV file in Python.
- *NOTE: This notebook/workflow has not been updated since summer 2021 and may no longer run due to changes in the Sports Reference site structure. Folks are welcome to use this code as a starting point for developing their own web scraping programs, as long as the original work is cited.*

Data scraping output: `combined_nd_rosters.csv` ([GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/combined_nd_rosters.csv), [Google Drive](https://drive.google.com/file/d/1LpT-mjNxvvmqsDV0pFmFBFvb8PSwJiTj/view?usp=sharing))

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

Prof. Walden has [built out a Jupyter Notebook](https://drive.google.com/file/d/175Gf_-SNdwdUrhvyhPRKxApMgSaESx-d/view?usp=sharing) that scrapes the rosters into a combined CSV file in Python.
- *NOTE: This notebook/workflow has not been updated since summer 2021 and may no longer run due to changes in the Sports Reference site structure. Folks are welcome to use this code as a starting point for developing their own web scraping programs, as long as the original work is cited.*

Data scraping output: `combined_nd_schedules.csv` ([GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/combined_nd_schedules.csv), [Google Drive](https://drive.google.com/file/d/1-P_6693TjcE7QTgpUDlHrOTD1jprztb6/view?usp=sharing))

Excel data wrangling output: `combined_nd_schedules_cleaned.csv` ([GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/combined_nd_schedules_cleaned.csv), [Google Drive](https://drive.google.com/file/d/15U5nNbKX-BfIWO4CTCeabit7mdokf9SV/view?usp=sharing))

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

The `Rockne_Coaching_Tree` Excel workbook documents this iterative process: [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Rockne_Coaching_Tree.xlsx), [Google Drive](https://docs.google.com/spreadsheets/d/1B2RaD_qtrQaupo6FznKzuAMnYCGt6eEJJ-aAcU9z8I4/edit?usp=sharing)

The first step was to take the information on Wikipedia and map it onto a tabular data structure that would move in the direction of having nodes, edges, and weights.

The `Original_Coaching_Tree.csv` file reflects this preliminary structure.
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Rockne_Coaching_Tree_Full.csv), [Google Drive](https://docs.google.com/spreadsheets/d/1B2RaD_qtrQaupo6FznKzuAMnYCGt6eEJJ-aAcU9z8I4/edit?usp=sharing)

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
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Simplified_Coaching_Tree_CTD.csv), [Google Drive](https://drive.google.com/file/d/1AvPk8sKYhlsCz6RjUTzkSyxxULX_Wf2U/view?usp=sharing)

We can also include the other institutions these individuals played at as source nodes.

The `Alternate_Simplified_Coaching_Tree_CTD.csv` file reflects this expanded `source-target` structure:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Alternate_Simplified_Coaching_Tree_CTD.csv), [Google Drive](https://drive.google.com/file/d/1OTel7xqn2yxx9fzDFWPQkdwR67oP-pJc/view?usp=sharing)

But the simplified `source-target` structure doesn't account for aspects of these relationships like how many years someone played at ND, or how many years they coached at subsequent institutions.

We can use the concept of weighted edges to incorporate these other pieces of data.

One way to incorporate weighted edges is to use the number of years someone played at ND or coached elsewhere as the weight.

The `Full_Coaching_Tree_Edges.csv` file reflects this weighted edge structure.
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Full_Coaching_Tree_Edges.csv), [Google Drive](https://drive.google.com/file/d/1NK3JPimaISPy8NCifrCSSV7w8ZMtCOYO/view?usp=sharing)

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
