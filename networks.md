# Lab #2 (Structured Data): Networks

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Networks

- [DataBasic: Connect the Dots](#databasic-connect-the-dots)
- [Palladio](#palladio)
- [Gephi](#gephi)
- [General Network Discussion/Reflection Questions](#general-network-discussionreflection-questions)
- [Other Network Tools/Resources](#other-network-toolsresources)

## Knute Rockne Coaching Tree

1- In this section of the lab, we're thinking about how structured data can be the starting point for looking at networks and relationships, under the umbrella of network analysis.

### What is a network?

2- According to Miriam Posner, networks are “a finite set (or sets) of actors and the relations defined on them. It consists of three elements: 
- (1) a set of actors;
- (2) each actor has a set of individual attributes; and 
- (3) a set of ties that defines at least one relation among actors.” 
 
3- A network graph is “a common way to visually represent social networks, consisting of two dimensions: actors and relations (also called nodes and edges). Nodes are the entities in graph (also called vectors)..[edges] are the relationships between nodes.” 

4- Learn more via the [PDF included in this Repository](https://github.com/kwaldenphd/football-structured-data/blob/main/files/Posner_SocialNetworkAnalysisGlossary.pdf)

### Coaching tree as a type of network

5- From [Wikipedia](https://en.wikipedia.org/wiki/Coaching_tree):
- "A coaching tree is similar to a family tree except that it shows the relationships of coaches instead of family members. There are several ways to define a relationship between two coaches. The most common way to make the distinction is if a coach worked as an assistant on a particular head coach's staff for at least a season then that coach can be counted as being a branch on the head coach's coaching tree. Coaching trees can also show philosophical influence from one head coach to an assistant. Coaching trees are common in the National Football League and most coaches in the NFL can trace their lineage back to a certain head coach for whom they previously worked as an assistant."

6- We can think of a coaching tree as a type of network, where the relationship of coaches in the tree is understood via nodes and edges.

7- As an example of research that uses this approach/method:
- Andrew Fast and David Donald Jensen, "[The NFL Coaching Network: Analysis of the Social Network Among Professional Football Coaches](https://www.researchgate.net/publication/228968729_The_NFL_Coaching_Network_Analysis_of_the_Social_Network_Among_Professional_Football_Coaches)" *American Association for Artificial Intelligence* (2006)

### Rockne Coaching Tree Data Processing Overview

8- No fancy Jupyter Notebooks for this one. Prof. Walden went through a few iterations of how to organize and structure the Rockne coaching tree facilitate network analysis.

9- The `Rockne_Coaching_Tree` Excel workbook documents this iterative process:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Rockne_Coaching_Tree.xlsx)
- [Google Drive](https://docs.google.com/spreadsheets/d/1B2RaD_qtrQaupo6FznKzuAMnYCGt6eEJJ-aAcU9z8I4/edit?usp=sharing)

10- The most straightforward way to represent this data as a network is to have `source` and `target` nodes, in which Rockne is the source and the person who played/coached for him is the target. 

11- The `Simplified_Coaching_Tree_CTD.csv` file reflects this `source-target` structure:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Simplified_Coaching_Tree_CTD.csv)
- [Google Drive](https://drive.google.com/file/d/1AvPk8sKYhlsCz6RjUTzkSyxxULX_Wf2U/view?usp=sharing)

12- We can also include the other institutions these individuals played at as source nodes.

13- The `Alternate_Simplified_Coaching_Tree_CTD.csv` file reflects this expanded `source-target` structure:
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Alternate_Simplified_Coaching_Tree_CTD.csv)
- [Google Drive](https://drive.google.com/file/d/1OTel7xqn2yxx9fzDFWPQkdwR67oP-pJc/view?usp=sharing)

14- But the simplified `source-target` structure doesn't account for aspects of these relationships like how many years someone played at ND, or how many years they coached at subsequent institutions.

15- We can use the concept of weighted edges to incorporate these other pieces of data.

16- One way to incorporate weighted edges is to use the number of years someone played at ND or coached elsewhere as the weight.

17- The `Full_Coaching_Tree_Edges.csv` file reflects this weighted edge structure.
- [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Full_Coaching_Tree_Edges.csv)
- [Google Drive](https://drive.google.com/file/d/1NK3JPimaISPy8NCifrCSSV7w8ZMtCOYO/view?usp=sharing)

18- When Rockne is the `source` node, the weight is the number of seasons the `target` individual played under him at ND.

19- When an institution or team is the `source` node, the weight is the number of seasons the `target` individual coached at this program.

## DataBasic: Connect The Dots

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_1.jpg?raw=true" alt="Capture" /></p>

20- Navigate to the [DataBasic home page.](https://databasic.io)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_13.png?raw=true" alt="Capture" /></p>

21- Click on the `ConnectTheDots` icon to open the ConnectTheDots tool.

23- As described on the page, “ConnectTheDots shows you how your data is connected by analyzing it as a network. Analyzing the connections between the "dots" in your data is a fundamentally different approach to understanding it. This tool shows you a network diagram to reveal those links, and gives you a high level report about what your network looks like.”

<blockquote>Images and screenshots included in this tutorial are from a sample dataset and do not reflect what you will see working with different data.</blockquote>

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_14.png?raw=true" alt="Capture" /></p>

24- ConnectTheDots gives you the option to use sample network data, paste your own data, or upload a file.

25- For ConnectTheDots, our network data is formatted as a list of edges, or connections, between a source and target node. 

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

26- We have two sample datasets that work with ConnectTheDots:
- `Simplified_Coaching_Tree_CTD.csv` has Rockne is the source and the person who played/coached for him is the target
  * [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Simplified_Coaching_Tree_CTD.csv)
  * [Google Drive](https://drive.google.com/file/d/1AvPk8sKYhlsCz6RjUTzkSyxxULX_Wf2U/view?usp=sharing)
- `Alternate_Simplified_Coaching_Tree_CTD.csv` has Rockne or institutions his players coached for as source nodes and the players/coaches as target nodes
  * [GitHub](https://github.com/kwaldenphd/football-structured-data/blob/main/data/Alternate_Simplified_Coaching_Tree_CTD.csv)
  * [Google Drive](https://drive.google.com/file/d/1OTel7xqn2yxx9fzDFWPQkdwR67oP-pJc/view?usp=sharing)

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_15.png?raw=true" alt="Capture" /></p>

27- The top of the ConnecTheDots results page provides an overview of your network. The network graph uses colors to indicate groups of nodes, and the graph caption provides a description of the network graph.

28- The table on the right-hand side of the page includes a list of nodes in your network, as well as the degree and centrality for each node.

<blockquote> Degree refers to the number of connections a node has. Centrality is a calculation of how central a node is within the network.</blockquote> 

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_15a.png?raw=true" alt="Capture" /></p>

29- Clicking the square arrow icon at the top of the page gives you a link to your results (good for 60 days).

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_15b.png?raw=true" alt="Capture" /></p>

30- Clicking the `Download` button by the network graph gives you the option to download the graph as an image file (PNG or SVG) or a network graph file to use in a network analysis software program (GEXF). You can also download the table of nodes with degree and centrality metrics as a CSV file.

<p align="center"><img class=" size-full wp-image-53 aligncenter" src="https://github.com/kwaldenphd/DataBasic-tutorial/blob/master/screenshots/Capture_16.png?raw=true" alt="Capture" /></p>

#### ConnectTheDots Discussion/Reflection Questions

- What do you notice about the results for this dataset displayed in ConnectTheDots?
- How does the tool's analysis/visualization results shape your understanding of the data?
- What additional questions do you have about this data? Where would you go next with exploring this dataset using some of the analysis tools/approaches highlighted in the tool?
- Other comments/questions/observations

## Palladio

*Developed through a National Endowment for the Humanities Implementation grant, [Palladio](http://hdlab.stanford.edu/palladio) was released by Stanford University in June 2016. Designed for historians and other digital humanities scholars, Palladio is a web-based application that allows users to analyze data that includes time and network features and display that data via maps, timelines, other types of visualizations, and gallery exhibits. Designed as a browser-based GUI interface, Palladio works well for quick visualizations and offers limited interactive export options.*

## Loading data into Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true"><img class="aligncenter size-large wp-image-498" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_1.PNG?raw=true" alt="" width="676" height="334" /></a></p>

31- Open the [Palladio home page](http://hdlab.stanford.edu/palladio) in Chrome or Firefox. 

32- Click on the `Start` icon to open a new project.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true"><img class="aligncenter size-large wp-image-499" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_2.PNG?raw=true" alt="" width="676" height="454" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter size-full wp-image-500" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="876" height="764" /></a></p>

33- Drag and drop one of the Rockne network files into the `Load CSV` window.

34- Any of the network CSV files will work in Palladio.
- `Simplified_Coaching_Tree_CTD.csv` (just Rockne and former players)
- `Alternate_Simplified_Coaching_Tree_CTD.csv` (Rockne, former players, and institutions they coached for)
- `Full_Coaching_Tree_Edges.csv` (Rockne, former players, and institutions they coached for with attached weights based on number of years played under Rockne or number of years coaching elsewhere)

35- Click the `Load` icon to load the data.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true"><img class="aligncenter size-full wp-image-486" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="" width="502" height="531" /></a></p>

36- Click on `Untitled` to give the table a descriptive label.

37- You may notice Palladio has a red dot next to some fields. We're going to ignore this message for now.
- Palladio requires you to verify special or unexpected characters in the data fields. You can click on the red dot and select `Verify special characters` and then `Done` to address the error message.

38- Back on the `Data` screen, you can see the error has been resolved, and Palladio has also automatically described your data fields as a text, date, or number. 

## Analyzing and Visualizing Data in Palladio

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter size-full wp-image-491" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="391" height="55" /></a></p>

39- Palladio does offer mapping functionality, but our data does not contain spatial information. 

40- Click on the `Graph` tab to start building a network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter size-full wp-image-492" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="614" height="364" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter size-large wp-image-493" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="676" height="314" /></a></p>

41- Select `Source` from the `Source dimension` drop-down menu, and `Target` from the `Target dimension` drop-down.

42- Palladio has now generated a network graph.

<p align="center"><a href="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true"><img class="aligncenter size-large wp-image-495" src="https://github.com/kwaldenphd/Palladio-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="" width="676" height="310" /></a></p>

43- We can also choose to size the nodes based on another data field.

44- Check the box next to `Size nodes` and select `Weight` for `According to`.

45- These settings size our nodes based on the weight assigned or determined by the number of years someone played under Rockne or number of years they coached at another institution.

46- Palladio offers additional facet, timeline, and timespan analysis via the buttons on the bottom of the page. These features can be useful depending on what types of information are included in the data you are working with.

47- For a more in-depth look at network analysis in Palladio: Marten Düring, "From Hermeneutics to Data to Networks: Data Extraction and Network Visualization of Historical Sources," The Programming Historian 4 (2015), https://doi.org/10.46430/phen0044.

### Palladio Discussion/Reflection Questions

- What do you notice about the results for this dataset displayed in Palladio?
- How does the tool's analysis/visualization results shape your understanding of the data?
- What additional questions do you have about this data? Where would you go next with exploring this dataset using some of the analysis tools/approaches highlighted in the tool?
- Other comments/questions/observations

## Gephi

*ConnectTheDots and Palladio are both browser-based tools for generating network visualizations and preliminary network analysis. Both tools offer limited options for calculating or analyzing more advanced network metrics. [Gephi](https://github.com/gephi/gephi) is an open-source network analysis and visualization software created by students at the University of Technology of Compiègne in 2008. The Gephi Consortium, which supports the ongoing development and documentation for Gephi, is a non-profit corporation supported by members that include SciencesPo, Linfluence, WebAtlas, and Quid. Gephi runs on Linux, Windows, and macOS operating systems and is available in 9 different languages.*

## Installing Gephi

48- To download Gephi on your own computer, go to [Gephi’s download page](https://gephi.org/users/download) and select the correct version for your operating system.

## Loading Data into Gephi

49- Launch Gephi and select `New Project` in the `Welcome` pop-up window.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture.PNG?raw=true" alt="" width="840" height="473" /></a></p>

50- Select `Import Spreadsheet` under the `File` menu tab.

51- Select the `Full_Coachign_Tree_Edges.csv` file.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture2.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture2.PNG?raw=true" alt="" width="843" height="500" /></a></p>

52- Make sure `Comma` is selected as the `Seperator`, `Edges` table is selected under `Import as`.
- If needed, make sure `UTF-8` is selected under `Charset`.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture3.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture3.PNG?raw=true" alt="" width="845" height="498" /></a></p>

53- Click `Next`.

54- In the `Import settings (2 of 2)` pop-up, leave the default settings, and click `Finish`.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture4.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture4.PNG?raw=true" alt="" width="662" height="460" /></a></p>

55- Select `Undirected` under `Graph Type`, and switch the default selection from `New workspace` to `Append to existing workspace`.

56- Click `OK` to load the data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture5.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture5.PNG?raw=true" alt="" width="840" height="475" /></a></p>

57- The Rockne coaching tree data is now loaded in the `Data Laboratory` tab.

58- Before we go any further, click `Save` under the `File` menu option to save the project.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture11.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture11.PNG?raw=true" alt="" width="511" height="105" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture12.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture12.PNG?raw=true" alt="" width="840" height="472" /></a></p>

59- Click on the `Overview` tab (and `Graph` tab if needed) to see Gephi’s default visualization of your network data.

60- As you probably noticed, the default visualization is an interesting connection of nodes and edges, but doesn’t do much to help us more fully understand and analyze our data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture14.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture14.PNG?raw=true" alt="" width="366" height="141" /></a></p>

61- Click on `Choose a layout` under the `Layout` panel to select how Gephi displays your nodes and edges.

62- Gephi uses a variety of layout algorithms to determine the shape of network graphs. These different layouts algorithms highlight different aspects or features of your data.

<table>
<tr>
<td>Divisions</td>
<tdOpenOrd</td>
</tr>
<tr>
<td>Complementarities</td>
<td>ForceAtlas, Yifan Hu, Frushterman-Reingold</td>
</tr>
<tr>
<td>Ranking</td>
<td>Circular, Radial Axis</td>
</tr>
<tr>
<td>Geographic Repartition</td>
<td>GeoLayout</td>
 </tr>
</table>

63- `Label Adjust`, `Noverlap`, `Expansion`, and `Contraction` make graphic adjustments to how your data displays, rather than using an underlying algorithm to change the structure of the network visualization.

64- Select different layout options and click the `Run` icon to see how the different algorithms and settings change the visualization of your data. 
- If needed, click the `Stop` icon to stop the layout operation.

## Calculating Network Metrics in Gephi

65- Gephi includes built-in options to calculate a number of different network statistics.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture15.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture15.PNG?raw=true" alt="" width="324" height="617" /></a></p>

66- The `Statistics` panel gives you the option to run a number of different calculations on your network data.

67- While Gephi allows us to easily perform these calculations, the program doesn’t automatically tell us what these measures mean or how they are calculated.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture16.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture16.PNG?raw=true" alt="" width="701" height="603" /></a></p>

68- The HTML report in the pop-up window that displays after you run a statistics gives you a graph of the data calculation, and sometimes the source for the algorithm used to calculate the statistic.

69- Consult [Gephi's GitHub repository](https://github.com/gephi/gephi/wiki/Statistics) for more information on these statistics.

70- Click `Run` for some of the options under `Statistics`.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture19.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture19.PNG?raw=true" alt="" width="840" height="473" /></a></p>

71- If you click on the `Data Laboratory` tab, you will see these calculated statistics have been added to your network data.

## Customizing a Network Visualization in Gephi

72- Select `Noverlap` for your Layout so your nodes and edges don’t overlap as you are exploring display customization options.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture21.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture21.PNG?raw=true" alt="" width="840" height="655" /></a></p>

73- The border icons in the Graph panel allow you to customize the display of your network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture22.PNG?raw=true"><img class="size-full wp-image-196 alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture22.PNG?raw=true" alt="" width="28" height="24" /></a></p>

74- Click on the `Show Node Labels` icon to display the node labels. 

75- You can change the size of text for your labels by using the slider to the right of `Arial Bold, 32.`

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture24.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture24.PNG?raw=true" alt="" width="359" height="362" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture23.PNG?raw=true"><img class="alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture23.PNG?raw=true" alt="" width="22" height="29" /></a></p>

76- You can also click on the `Attributes` icon to customize what data fields display as part of your labels.

77- While your nodes now have labels, the large number of nodes and edges makes it difficult to differentiate or discern various attributes about our network data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture20.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture20.PNG?raw=true" alt="" width="347" height="110" /></a></p>

78- The `Appearance` panel allows you to customize the color, size or weight, and labels for your nodes and edges. 

79- Changing the coloring or sizing of nodes in the `Appearance` panel can help make our network visualization more meaningful.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture26.PNG?raw=true"><img class="alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture26.PNG?raw=true" alt="" width="24" height="25" /></a></p>

80- Select the `Size` icon to change the default size of your nodes. 
- You can explore different sizes, but 3 works well with this dataset. 

81- Click the `Apply` icon to change the setting for your network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture27.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture27.PNG?raw=true" alt="" width="349" height="330" /></a></p>

82- You can also rank the size of nodes based on one of the network metrics you calculated in the `Statistics` panel.

83- Click the `Ranking` icon in the `Appearance` panel.

84- Select `Degree` from the drop-down menu. Click `Apply` to update the graph.

85- Ranking our node size by degree determines the size of a node based on its degree of centrality (or connectedness). Nodes with higher numbers of connections appear larger, and nodes with lower numbers of connections are smaller.

86- You can change the minimum and maximum node size, and also select different statistics to use for determining node size.

87- Explore these different settings and options to see how different node size calculations shape your understanding of the network data.

88- Save your project.

## Exporting Networks

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Picx.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Picx.png?raw=true" alt="" width="244" height="264" /></a></p>

89- Click `Export` under the `File` menu tab to save your project as a static image (SVG, PNG, PDF) or network file (CSV, GDF, GEXF, GraphML, Pajek Net).

90- Learn more about the different export options by consulting Gephi's [graph format documentation](https://gephi.org/users/supported-graph-formats)

### Gephi Discussion/Reflection Questions

- What do you notice about the results for this dataset displayed in Gephi?
- How does the tool's analysis/visualization results shape your understanding of the data?
- What additional questions do you have about this data? Where would you go next with exploring this dataset using some of the analysis tools/approaches highlighted in the tool?
- Other comments/questions/observations

## General Network Discussion/Reflection Questions

- Thinking holistically across the network analysis/visualization tool(s) you interacted with, what questions were you interested in asking or exploring about the sample network data?
- How did using network analysis shape your understanding of the data (or the Rockne coaching tree more broadly)?
- Where would you go next with network analysis/visualization tools?
  * What questions or topics would you want to explore using the sample datasets?
  * Or, what other types of network information/data related to ND football would you want to work with?
- Other comments/questions/observations

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
