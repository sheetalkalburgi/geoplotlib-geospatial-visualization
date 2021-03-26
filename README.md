# AirBnB Geospatial Analysis using Geoplotlib 
## About Geoplotlib
- Geoplotlib is an open-source python toolbox for visualizing geo-graphical data. Geographical data visualization is a fundamental tool for communicating results related to geospatial analyses, and for generating hypotheses during exploratory data analysis.\
- Geoplotlib uses numpy/scipy for fast numerical computations, and pyglet/OpenGL for hardware-accelerated graphical rendering. This allows the visualizations to scale to millions of datapoints in realtime.\
- Provides implementations of dot density maps,choropleths,heatmaps, kernel density estimation, spatial graphs, Voronoi tesselation and and many more spatial visualizations. We describe geoplotlib design, functionalities and use cases.\
- Simple yet powerful API to generate geographical visualizations on OpenStreetMap tiles.
API refrences are available here: https://andrea-cuttone.github.io/geoplotlib/api.html

Geoplotlib is used for:
- Communicating results related to geospatial analyses.\
- For generating hypotheses during exploratory data analysis.\
- Supporting interactive data analysis.\
- Facilitating the iterative design for visualizations.

Limitations:
- Currently, however,there is limited support for geographical visualization.

DataStoreObjects:
To implement geoplot, it is necessary to convert a dataframe from Pandas to DataAccessObject. There are 2 methods which can used to do so:
Method 1: Read the CSV file and perform necessary modification. Save the new CSV and re-read it as DataAccessObject.\
Method 2: Use in-built class 'DataAccessObject'.


## Geoplotlib Installation
Geoplotlib requires:
1. numpy
2. pyglet 1.2.4\
In order for pyglet to work with ipython on Mac, version 1.2.4 or newer is needed

## Features of Geoplotlib covered in this notebook:
1. Dot Plot: An elementary operation in geographical visualization is to display “what is where”, that is to place a graphic element on the map for each of the objects in consideration. This provides an immediate idea of the absolute and relative locations of objects. The density of points directly maps to the density of objects on geographical surface, identifying zones of higher and lower density.
2. Maptiles: An interesting feature of geoplotlib is that, it provides the ability to have different map tiles as a base. A simple dot plot can be changed to have a different background, such as a watercolour map as shown in the below code. A number of common free tiles providers are supported, including Stamen Watercolor and Toner, CartoDB Positron and DarkMatter.
3. Layers: Geoplotlib allows to overlay multiple plots and most features of Geoplotlib can be overlayed on top of each other. This is called layering. Lables and markers can also be added as another layer.
4. 2D Histogram: One limitation of dot maps is that, it is hard to distinguish between areas of high density, as the number of point is so high that they uniformly cover the visualization canvas. A more direct visualization of density is to compute a 2D histogram of point coordinates. A uniformly spaced grid is placed on the map, and the number of samples within each cell is counted. Compared to the dot map example, the histogram provides a clearer depiction of the density distribution.
5. Kernel Density Estimation (KDE): Further to 2D Histogram, the main drawback of histogram visualizations is that they are discrete approximations of a (effectively continuous) density function. This creates a dependence on the bin size and offset, rendering histograms sensitive to noise and outliers. To generate a smoother approximation, a kernel density estimator approximates the true density function by applying kernel functions in a window around each point. The size of this window depends on the bandwidth parameter: a smaller bandwidth will produce more detailed but also noisier estimation, while a larger bandwidth will produce a less detailed but smoother estimation. A kernel estimation function can then be visualized by a surface where the color encodes the density value (this visualization is often called a “heatmap”).
6. Voronoi Tessellation: A Voronoi tessellation is a partition of space into regions induced by points, so that each region (called a Voronoi cell) consists of all points closer to a specific point than to any others. The analysis of Voronoi tessellation is used in numerous fields including ecology, hydrology, epidemiology, mining and mobility studies. Voronoi cell fill, shading and colors can be configured. In a Voronoi tessellation, each pair of data points is separated by a (perpendicular) line such that it is equally distant from both the data points. As a result, the closer the data points, the smaller the cells.
7. Delaunay triangulation: A Delaunay triangulation is yet another convenient method for generating triangle meshes from a set of points. In geoplotlib the delaunay method can be used for this purpose. The edge color can be configured to a fixed value, or to encode the length of the edges.

Analysis on my [Medium]!

[Medium]:https://sheetalkalburgi.medium.com/

## Advanced features: 
Additionally, there are more advanced features available in geoplotlib such as:
- Animation with time stamp: animation feature work ONLY on time stamp data.\
- Choropleth: each geographic unit is coloured to show a continuous variable.\
- Custom layering: enables you to create and add custom layers.

## References
- http://www.marknagelberg.com/overview-python-and-non-python-mapping-tools-for-data-scientists/
- https://www.researchgate.net/publication/305983877_Geoplotlib_a_Python_Toolbox_for_Visualizing_Geographical_Data
- https://github.com/andrea-cuttone/geoplotlib
- https://github.com/AntoineSueur/Geoplot-landslides
- https://nbviewer.jupyter.org/github/amrrs/mapping_wifi_wigle_r_py/blob/master/Building%20Wifi%20Spots%20Map%20with%20Python%20and%20WiGLE.ipynb
