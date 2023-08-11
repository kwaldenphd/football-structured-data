# Lab #2 (Structured Data): Networks

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Table of Contents

- [Overview](#overview)
- [DataBasic: Connect the Dots](#databasic-connect-the-dots)
- [Palladio](#palladio)
- [Oh, the Places You Could Go!](#oh-the-places-you-could-go)
- [Discussion/Reflection Questions](#discussionreflection-questions)

# Overview

In this section of the lab, we'll think about how structured data can be the starting point for looking at networks and relationships, under the umbrella of network analysis.

<p align="center"><a href="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/graphwords.png?raw=true"><img class="aligncenter size-large wp-image-473" src="https://github.com/kwaldenphd/football-structured-data/blob/main/figures/graphwords.png?raw=true" alt="" width="676" height="332" /></a></p>

According to Miriam Posner, networks are “a finite set (or sets) of actors and the relations defined on them. It consists of three elements: 
- (1) a set of actors;
- (2) each actor has a set of individual attributes; and 
- (3) a set of ties that defines at least one relation among actors.” 
 
A network graph is “a common way to visually represent social networks, consisting of two dimensions: actors and relations (also called nodes and edges). Nodes are the entities in graph (also called vectors)..[edges] are the relationships between nodes.”  
- Learn more via the [PDF included in this Repository](https://github.com/kwaldenphd/football-structured-data/blob/main/files/Posner_SocialNetworkAnalysisGlossary.pdf)

## Coaching tree as a type of network

From [Wikipedia](https://en.wikipedia.org/wiki/Coaching_tree):
<blockquote>
"A coaching tree is similar to a family tree except that it shows the relationships of coaches instead of family members. There are several ways to define a relationship between two coaches. The most common way to make the distinction is if a coach worked as an assistant on a particular head coach's staff for at least a season then that coach can be counted as being a branch on the head coach's coaching tree. Coaching trees can also show philosophical influence from one head coach to an assistant.
<br>
"Coaching trees are common in the National Football League and most coaches in the NFL can trace their lineage back to a certain head coach for whom they previously worked as an assistant."</blockquote>

We can think of a coaching tree as a type of network, where the relationship of coaches in the tree is understood via nodes and edges. An example of research that uses this approach/method:
- Andrew Fast and David Donald Jensen, "[The NFL Coaching Network: Analysis of the Social Network Among Professional Football Coaches](https://www.researchgate.net/publication/228968729_The_NFL_Coaching_Network_Analysis_of_the_Social_Network_Among_Professional_Football_Coaches)" *American Association for Artificial Intelligence* (2006)

## Rockne Coaching Tree Data Processing Overview

No fancy Jupyter Notebooks for this one. Prof. Walden went through a few iterations of how to organize and structure the Rockne coaching tree facilitate network analysis.

The `Rockne_Coaching_Tree` Excel workbook documents this iterative process: *[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Rockne_Coaching_Tree.xlsx), [Google Drive](https://docs.google.com/spreadsheets/d/1B2RaD_qtrQaupo6FznKzuAMnYCGt6eEJJ-aAcU9z8I4/edit?usp=sharing)*

The first step was to take the information on Wikipedia and map it onto a tabular data structure that would move in the direction of having nodes, edges, and weights.

The `Original_Coaching_Tree.csv` file reflects this preliminary structure. *[[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Rockne_Coaching_Tree_Full.csv), [Google Drive](https://docs.google.com/spreadsheets/d/1B2RaD_qtrQaupo6FznKzuAMnYCGt6eEJJ-aAcU9z8I4/edit?usp=sharing)]*

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

The `Simplified_Coaching_Tree_CTD.csv` file reflects this `source-target` structure: *[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Simplified_Coaching_Tree_CTD.csv), [Google Drive](https://drive.google.com/file/d/1AvPk8sKYhlsCz6RjUTzkSyxxULX_Wf2U/view?usp=sharing)]*

We can also include the other institutions these individuals played at as source nodes.

The `Alternate_Simplified_Coaching_Tree_CTD.csv` file reflects this expanded `source-target` structure: *[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Alternate_Simplified_Coaching_Tree_CTD.csv), [Google Drive](https://drive.google.com/file/d/1OTel7xqn2yxx9fzDFWPQkdwR67oP-pJc/view?usp=sharing)*

But the simplified `source-target` structure doesn't account for aspects of these relationships like how many years someone played at ND, or how many years they coached at subsequent institutions.

We can use the concept of weighted edges to incorporate these other pieces of data. One way to incorporate weighted edges is to use the number of years someone played at ND or coached elsewhere as the weight.

The `Full_Coaching_Tree_Edges.csv` file reflects this weighted edge structure: *[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Full_Coaching_Tree_Edges.csv), [Google Drive](https://drive.google.com/file/d/1NK3JPimaISPy8NCifrCSSV7w8ZMtCOYO/view?usp=sharing)*
- When Rockne is the `source` node, the weight is the number of seasons the `target` individual played under him at ND.
- When an institution or team is the `source` node, the weight is the number of seasons the `target` individual coached at this program.

# Palladio

*Developed through a National Endowment for the Humanities Implementation grant, [Palladio](http://hdlab.stanford.edu/palladio) was released by Stanford University in June 2016. Designed for historians and other digital humanities scholars, Palladio is a web-based application that allows users to analyze data that includes time and network features and display that data via maps, timelines, other types of visualizations, and gallery exhibits. Designed as a browser-based GUI interface, Palladio works well for quick visualizations and offers limited interactive export options.*

## Loading data into Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-498" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="334" /></a></p>

1- Open the [Palladio home page](http://hdlab.stanford.edu/palladio) in Chrome or Firefox. Click on the `Start` icon to open a new project.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-large wp-image-499" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="676" height="454" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-500" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="876" height="764" /></a></p>

2- Drag and drop one of the Rockne network files into the `Load CSV` window. Any of the network CSV files will work in Palladio.
- `Simplified_Coaching_Tree_CTD.csv` (just Rockne and former players)
- `Alternate_Simplified_Coaching_Tree_CTD.csv` (Rockne, former players, and institutions they coached for)
- `Full_Coaching_Tree_Edges.csv` (Rockne, former players, and institutions they coached for with attached weights based on number of years played under Rockne or number of years coaching elsewhere)

4- Click the `Load` icon to load the data.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true"><img class="aligncenter size-full wp-image-486" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="" width="502" height="531" /></a></p>

5- Click on `Untitled` to give the table a descriptive label. You may notice Palladio has a red dot next to some fields. We're going to ignore this message for now.
- Palladio requires you to verify special or unexpected characters in the data fields. You can click on the red dot and select `Verify special characters` and then `Done` to address the error message.

6- Back on the `Data` screen, you can see the error has been resolved, and Palladio has also automatically described your data fields as a text, date, or number. 

## Analyzing and Visualizing Data in Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter size-full wp-image-491" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="391" height="55" /></a></p>

7- Palladio does offer mapping functionality, but our data does not contain spatial information. Click on the `Graph` tab to start building a network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter size-full wp-image-492" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="614" height="364" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter size-large wp-image-493" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="676" height="314" /></a></p>

8- Select `Source` from the `Source dimension` drop-down menu, and `Target` from the `Target dimension` drop-down. Palladio has now generated a network graph.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true"><img class="aligncenter size-large wp-image-495" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="" width="676" height="310" /></a></p>

9- We can also choose to size the nodes based on another data field. Check the box next to `Size nodes` and select `Weight` for `According to`. These settings size our nodes based on the weight assigned or determined by the number of years someone played under Rockne or number of years they coached at another institution.

10-Palladio offers additional facet, timeline, and timespan analysis via the buttons on the bottom of the page. These features can be useful depending on what types of information are included in the data you are working with.

11- For a more in-depth look at network analysis in Palladio: Marten Düring, "From Hermeneutics to Data to Networks: Data Extraction and Network Visualization of Historical Sources," The Programming Historian 4 (2015), https://doi.org/10.46430/phen0044.

## Palladio Discussion/Reflection Questions

- What do you notice about the results for this dataset displayed in Palladio?
- How does the tool's analysis/visualization results shape your understanding of the data?
- What additional questions do you have about this data? Where would you go next with exploring this dataset using some of the analysis tools/approaches highlighted in the tool?
- Other comments/questions/observations

# DataBasic: Connect The Dots

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_1.jpg?raw=true" alt="Capture" /></p>

12- Navigate to the [DataBasic home page.](https://databasic.io)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_13.png?raw=true" alt="Capture" /></p>

13- Click on the `ConnectTheDots` icon to open the ConnectTheDots tool. As described on the page, “ConnectTheDots shows you how your data is connected by analyzing it as a network. Analyzing the connections between the "dots" in your data is a fundamentally different approach to understanding it. This tool shows you a network diagram to reveal those links, and gives you a high level report about what your network looks like.”

<blockquote>Images and screenshots included in this tutorial are from a sample dataset and do not reflect what you will see working with different data.</blockquote>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_14.png?raw=true" alt="Capture" /></p>

14- ConnectTheDots gives you the option to use sample network data, paste your own data, or upload a file.

15- For ConnectTheDots, our network data is formatted as a list of edges, or connections, between a source and target node. 

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

16- We have two sample datasets that work with ConnectTheDots:
- `Simplified_Coaching_Tree_CTD.csv` has Rockne is the source and the person who played/coached for him is the target (*[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Simplified_Coaching_Tree_CTD.csv), [Google Drive](https://drive.google.com/file/d/1AvPk8sKYhlsCz6RjUTzkSyxxULX_Wf2U/view?usp=sharing)*)
- `Alternate_Simplified_Coaching_Tree_CTD.csv` has Rockne or institutions his players coached for as source nodes and the players/coaches as target nodes (*[GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Alternate_Simplified_Coaching_Tree_CTD.csv), [Google Drive](https://drive.google.com/file/d/1OTel7xqn2yxx9fzDFWPQkdwR67oP-pJc/view?usp=sharing)*)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_15.png?raw=true" alt="Capture" /></p>

17- The top of the ConnecTheDots results page provides an overview of your network. The network graph uses colors to indicate groups of nodes, and the graph caption provides a description of the network graph.

18- The table on the right-hand side of the page includes a list of nodes in your network, as well as the degree and centrality for each node.

<blockquote> Degree refers to the number of connections a node has. Centrality is a calculation of how central a node is within the network.</blockquote> 

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_15a.png?raw=true" alt="Capture" /></p>

19- Clicking the square arrow icon at the top of the page gives you a link to your results (good for 60 days).

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_15b.png?raw=true" alt="Capture" /></p>

20- Clicking the `Download` button by the network graph gives you the option to download the graph as an image file (PNG or SVG) or a network graph file to use in a network analysis software program (GEXF). You can also download the table of nodes with degree and centrality metrics as a CSV file.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_16.png?raw=true" alt="Capture" /></p>

## ConnectTheDots Discussion/Reflection Questions

- What do you notice about the results for this dataset displayed in ConnectTheDots?
- How does the tool's analysis/visualization results shape your understanding of the data?
- What additional questions do you have about this data? Where would you go next with exploring this dataset using some of the analysis tools/approaches highlighted in the tool?
- Other comments/questions/observations

# Oh, the Places You Can Go!

ConnectTheDots and Palladio are both browser-based tools for generating network visualizations and preliminary network analysis. Both tools offer limited options for calculating or analyzing more advanced network metrics.

[Gephi](https://github.com/gephi/gephi) is an open-source network analysis and visualization software created by students at the University of Technology of Compiègne in 2008. The Gephi Consortium, which supports the ongoing development and documentation for Gephi, is a non-profit corporation supported by members that include SciencesPo, Linfluence, WebAtlas, and Quid. Gephi runs on Linux, Windows, and macOS operating systems and is available in 9 different languages.
- [Link to more information and a tutorial](https://github.com/kwaldenphd/football-structured-data/blob/main/gephi.md)

There are also network analysis programmatic workflows that run in Python, R, and Javascript.
- [Link to more information and tutorials](https://github.com/kwaldenphd/football-structured-data/blob/main/networks-advanced.md)

# Discussion/Reflection Questions

- Thinking holistically across the network analysis/visualization tool(s) you interacted with, what questions were you interested in asking or exploring about the sample network data?
- How did using network analysis shape your understanding of the data (or the Rockne coaching tree more broadly)?
- Where would you go next with network analysis/visualization tools?
  * What questions or topics would you want to explore using the sample datasets?
  * Or, what other types of network information/data related to ND football would you want to work with?
- Other comments/questions/observations
