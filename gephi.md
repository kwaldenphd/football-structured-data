# Lab #2 (Structured Data): Network Analysis in Gephi

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

# Table of Contents

- [Overview](#overview)
- [Installing](#installing)
- [Loading Data](#loading-data)
- [Calculating Network Metrics](#calculating-network-metrics)
- [Customizing a Network Visualization](#customizing-a-network-visualization)
- [Exporting Networks](#exporting-networks)
- [Discussion/Reflection Questions](#discussionreflection-questions)

# Overview

ConnectTheDots and Palladio are both browser-based tools for generating network visualizations and preliminary network analysis. Both tools offer limited options for calculating or analyzing more advanced network metrics. [Gephi](https://github.com/gephi/gephi) is an open-source network analysis and visualization software created by students at the University of Technology of Compiègne in 2008. The Gephi Consortium, which supports the ongoing development and documentation for Gephi, is a non-profit corporation supported by members that include SciencesPo, Linfluence, WebAtlas, and Quid. Gephi runs on Linux, Windows, and macOS operating systems and is available in 9 different languages.

# Installing

1- To download Gephi on your own computer, go to [Gephi’s download page](https://gephi.org/users/download) and select the correct version for your operating system.

# Loading Data

2- Launch Gephi and select `New Project` in the `Welcome` pop-up window.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture.PNG?raw=true" alt="" width="840" height="473" /></a></p>

3- Select `Import Spreadsheet` under the `File` menu tab. Select the `Full_Coachign_Tree_Edges.csv` file.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture2.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture2.PNG?raw=true" alt="" width="843" height="500" /></a></p>

4- Make sure `Comma` is selected as the `Seperator`, `Edges` table is selected under `Import as`.
- If needed, make sure `UTF-8` is selected under `Charset`.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture3.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture3.PNG?raw=true" alt="" width="845" height="498" /></a></p>

5- Click `Next`. In the `Import settings (2 of 2)` pop-up, leave the default settings, and click `Finish`.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture4.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture4.PNG?raw=true" alt="" width="662" height="460" /></a></p>

6- Select `Undirected` under `Graph Type`, and switch the default selection from `New workspace` to `Append to existing workspace`. Click `OK` to load the data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture5.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture5.PNG?raw=true" alt="" width="840" height="475" /></a></p>

7- The Rockne coaching tree data is now loaded in the `Data Laboratory` tab. Before we go any further, click `Save` under the `File` menu option to save the project.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture11.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture11.PNG?raw=true" alt="" width="511" height="105" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture12.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture12.PNG?raw=true" alt="" width="840" height="472" /></a></p>

8- Click on the `Overview` tab (and `Graph` tab if needed) to see Gephi’s default visualization of your network data. As you probably noticed, the default visualization is an interesting connection of nodes and edges, but doesn’t do much to help us more fully understand and analyze our data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture14.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture14.PNG?raw=true" alt="" width="366" height="141" /></a></p>

9- Click on `Choose a layout` under the `Layout` panel to select how Gephi displays your nodes and edges. Gephi uses a variety of layout algorithms to determine the shape of network graphs. These different layouts algorithms highlight different aspects or features of your data.

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

10- `Label Adjust`, `Noverlap`, `Expansion`, and `Contraction` make graphic adjustments to how your data displays, rather than using an underlying algorithm to change the structure of the network visualization.

11- Select different layout options and click the `Run` icon to see how the different algorithms and settings change the visualization of your data. 
- If needed, click the `Stop` icon to stop the layout operation.

# Calculating Network Metrics

12- Gephi includes built-in options to calculate a number of different network statistics.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture15.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture15.PNG?raw=true" alt="" width="324" height="617" /></a></p>

13- The `Statistics` panel gives you the option to run a number of different calculations on your network data. While Gephi allows us to easily perform these calculations, the program doesn’t automatically tell us what these measures mean or how they are calculated.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture16.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture16.PNG?raw=true" alt="" width="701" height="603" /></a></p>

14- The HTML report in the pop-up window that displays after you run a statistics gives you a graph of the data calculation, and sometimes the source for the algorithm used to calculate the statistic. Click `Run` for some of the options under `Statistics`.
- Consult [Gephi's GitHub repository](https://github.com/gephi/gephi/wiki/Statistics) for more information on these statistics.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture19.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture19.PNG?raw=true" alt="" width="840" height="473" /></a></p>

15- If you click on the `Data Laboratory` tab, you will see these calculated statistics have been added to your network data.

# Customizing a Network Visualization

16- Select `Noverlap` for your Layout so your nodes and edges don’t overlap as you are exploring display customization options.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture21.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture21.PNG?raw=true" alt="" width="840" height="655" /></a></p>

17- The border icons in the Graph panel allow you to customize the display of your network visualization.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture22.PNG?raw=true"><img class="size-full wp-image-196 alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture22.PNG?raw=true" alt="" width="28" height="24" /></a></p>

18- Click on the `Show Node Labels` icon to display the node labels. You can change the size of text for your labels by using the slider to the right of `Arial Bold, 32.`

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture24.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture24.PNG?raw=true" alt="" width="359" height="362" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture23.PNG?raw=true"><img class="alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture23.PNG?raw=true" alt="" width="22" height="29" /></a></p>

19- You can also click on the `Attributes` icon to customize what data fields display as part of your labels. While your nodes now have labels, the large number of nodes and edges makes it difficult to differentiate or discern various attributes about our network data.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture20.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture20.PNG?raw=true" alt="" width="347" height="110" /></a></p>

20- The `Appearance` panel allows you to customize the color, size or weight, and labels for your nodes and edges. Changing the coloring or sizing of nodes in the `Appearance` panel can help make our network visualization more meaningful.

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture26.PNG?raw=true"><img class="alignright" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture26.PNG?raw=true" alt="" width="24" height="25" /></a></p>

21- Select the `Size` icon to change the default size of your nodes. Click the `Apply` icon to change the setting for your network visualization.
- You can explore different sizes, but 3 works well with this dataset. 

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture27.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Capture27.PNG?raw=true" alt="" width="349" height="330" /></a></p>

22- You can also rank the size of nodes based on one of the network metrics you calculated in the `Statistics` panel. 
- Click the `Ranking` icon in the `Appearance` panel.
- Select `Degree` from the drop-down menu. Click `Apply` to update the graph.

23- Ranking our node size by degree determines the size of a node based on its degree of centrality (or connectedness). Nodes with higher numbers of connections appear larger, and nodes with lower numbers of connections are smaller.

24- You can change the minimum and maximum node size, and also select different statistics to use for determining node size. Explore these different settings and options to see how different node size calculations shape your understanding of the network data.

25- Save your project.

# Exporting Networks

<p align="center"><a href="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Picx.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/Gephi-tutorial/blob/master/screenshots/Picx.png?raw=true" alt="" width="244" height="264" /></a></p>

26- Click `Export` under the `File` menu tab to save your project as a static image (SVG, PNG, PDF) or network file (CSV, GDF, GEXF, GraphML, Pajek Net).
- Learn more about the different export options by consulting Gephi's [graph format documentation](https://gephi.org/users/supported-graph-formats)

# Discussion/Reflection Questions

- What do you notice about the results for this dataset displayed in Gephi?
- How does the tool's analysis/visualization results shape your understanding of the data?
- What additional questions do you have about this data? Where would you go next with exploring this dataset using some of the analysis tools/approaches highlighted in the tool?
- Other comments/questions/observations
