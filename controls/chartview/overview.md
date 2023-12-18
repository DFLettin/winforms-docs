---
title: Overview 
page_title: ChartView  - ChartView
description: RadChartView is a versatile charting component that offers drawing capabilities, user interaction and real-time updates. Its intuitive object model and public API allow complex charts to be easily setup either in design-time or through code.
slug: winforms/chartview/overview
tags: chartview,
published: True
position: 0
CTAControlName: ChartView
previous_url: chartview-overview
---

# WinForms ChartView Overview

| RELATED VIDEOS |  |
| ------ | ------ |
|[WinForms RadChartView What is new in Q3 2012 Telerik UI for WinForms](http://www.telerik.com/videos/winforms/what-is-new-in-q3-2012-radcontrols-for-winforms)<br>This webinar examines the new features found in Telerik UI for WinForms. Included in the Q3 2012 release is RadPivotGrid (Beta), Coded UI Testing Support, touch, legend and financial charts for __RadChartView__, Visual Studio 2012 compliance and much much more. See what's new in the design-time capabilities of RadChartView. (19:12 - 24:12)|![WinForms RadChartView webinar Q 32012](images/webinarQ32012.png)|
|[WinForms RadChartView Getting Started with RadChartView for WinForms](http://tv.telerik.com/watch/radcontrols-for-winforms/getting-started-with-radchartview-for-winforms) <br>Telerik ChartView control facilitates data visualization, achieving stunning visual effects. This chart component sets no limits on your data visualization needs. It can easily turn into Bar, Pie, Line, Area, Polar, Radar and Scatter with only a few clicks at design time. The input data is contained in a set of series classes. Each series have a collection of data points, that is, a data source which it displays according to the series’ type.|![WinForms RadChartView chartview-overview 002](images/chartview-overview001.png)|

* [Overview](#overview)

* [Architecture](#architecture)

* [Cartesian Area](#cartesian-area)

* [Polar Area](#polar-area)

* [Pie Area](#pie-area)

* [Features](#features)

## Overview

__RadChartView__ is a versatile charting component that offers drawing capabilities, user interaction and real-time updates. Its intuitive object model and public API allow complex charts to be easily setup either in design-time or through code. The control is completely data aware and may work in bound or unbound mode, depending on the requirements. Chart types (or series) are organized in hierarchies, depending on the coordinate system, used to plot data points – for example we have __CartesianArea__ (using Cartesian coordinate system) and __PolarArea__ (using  polar or radial coordinate system) and __PieArea__.

{% if site.has_cta_panels == true %}
{% include cta-panel-overview.html %}
{% endif %}

## Architecture
A charting component in general is used to visualize (or plot) some data in a human-readable way through different representations like lines, areas, bars, pies, etc. Each series has a collection of data points – the data equivalent of a 2D point – and knows how to visualize them. Different series types may process certain types of data points – for example categorical series may contain categorical data points. Data points may be added directly to series or a data binding mechanism may be used to create the appropriate data points from the raw data.

__RadChartView__ works with three area types - __Cartesian__, __Polar__ and __Pie__

## Cartesian Area
As the name hints, this concrete chart uses the Cartesian coordinate system to plot the data points in its chart series. The X and Y axes define how each point’s coordinates in the plot area are calculated.

>caption Figure 1: Cartesian Area Chart
![WinForms RadChartView Cartesian Area Chart](images/chartview-overview002.png)

### Axes Types
Available are the following axes:

#### Categorical
Arranges the plotted data points in categories where the key of each category is the point’s value (if available) for that axis or its index within the points collection. The point’s coordinate, specified by this axis is discrete and is calculated depending on the size of the category slot where the point resides.

#### Date-time Categorical
Special categorical axis that expects each data point to provide a System.DateTime structure as its value for this axis. The points are grouped by a user-defined date-time component (Year, Month, Day, etc.) and then the groups are sorted chronologically.

#### Linear
Calculates the coordinate of each data point, depending on the actual numerical value this point provides for the axis. Exposes Minimum and Maximum properties to allow for explicit definition of the range of values visible on this axis. If these properties are not specified, the axis will automatically calculate the range, depending on the minimum and maximum data point values.

#### Logarithmic
Special linear axis that will transform each data point value using the logarithm function. Allows numerical data with huge delta between the minimum and the maximum to be visualized in a readable way.

#### Date-time Continuous
Special axis that expects each data point to provide a System.DateTime structure as its value for this axis. May be thought of as a timeline where the coordinate of each data point is calculated depending on the position of its associated DateTime on the timeline. The base unit (or the timeline step) of the axis is calculated depending on the smallest difference between any two dates.

### Series Types
The currently implemented chart series are categorical – they accept CategoricalDataPoint and expect a categorical axis to be specified in order to be properly visualized. Following is a list with all the available series: 

#### Area
Data points and the corresponding coordinate axis enclose an area that may be optionally stroked and/or filled.

* __Stack100__: It shows the combined contribution of values as percentages where the combined total for each category is 100 percent. It's good to use it when the relationship between values in a category is more significant than the amounts.

#### SplineArea
An area, which points are connected with smooth rather than straight segments.

* __Stack100__: It shows the combined contribution of values as percentages where the combined total for each category is 100 percent. It's good to use it when the relationship between values in a category is more significant than the amounts.

#### Bar
Data points are represented by a box where the height (width) of the box is the distance between the point’s numerical value and the categorical axis that plots the point. Bars may be either “horizontal” or “vertical” depending on whether the categorical axis is specified as an “X-axis” or as a “Y-axis”.

* __Stack100__: It shows the combined contribution of values as percentages where the combined total for each category is 100 percent. It's good to use it when the relationship between values in a category is more significant than the amounts.

#### Line
Data points are connected with straight line segments.

* __Stack100__: It shows the combined contribution of values as percentages where the combined total for each category is 100 percent. It's good to use it when the relationship between values in a category is more significant than the amounts.

#### Spline
Data points are connected with smooth rather than straight line segments.

#### Scatter Point
Data points are simply plotted in the chart plot area with nothing connecting them. Each scatter data point has X and Y values which make the position of the data point in the data source and its location on the plot area unrelated. For example the third data point in the data source may appear before the first data point when plotted. There are also scatter line and scatter area series which behave in the exact same way with the only (visual)difference that the points define a line and area respectively.

#### Combined Series
Each of the above series of same type may be combined in either stacks or clusters. Combinations are formed when more than one data point from different series falls within a same category. The “Cluster” combine mode will position such points next to each other while the “Stack” one will arrange such points in a stack-like structure. When stacks are formed, the numerical axis (if present) will consider each stack as a single entity and its sum will be the actual value used rather than each point’s one.

## Polar Area
This area setups a polar coordinate system, where each value is positioned using a value-angle couple. Additionally, the Polar area renders Radar series, which splits the polar area into equal-size category sectors.

>caption Figure 2: Polar Area Chart
![WinForms RadChartView Polar Area Chart](images/chartview-overview003.png)

### Axes Types
This area setups a polar coordinate system, where each value is positioned using a value-angle couple.

#### Polar Axis
Special axis which is a fixed line in a system of polar coordinates from which the polar angle, θ, is measured anticlockwise. You may read more about it in Polar Axis topic. 

#### Radial Axis
Special axis used by the PolarArea Radar Series.

* __Categorical__: Positions catgories/labels around the circumference of the circle.

### Series Types
Supports __Polar__ and __Radar__ series.

#### Polar Series
Polar series consists of a group of classes that plot data in radial plot area in polar coordinates. Polar series have three implementations – __PolarLineSeries__, __PolarAreaSeries__ and __PolarPointSeries__.

#### Radar Series
The radar chart is a two-dimensional chart of three or more quantitative variables represented on axes starting from the same point. __RadChartView__ supports the following Radar Series implementations out of the box: __RadarPointSeries__, __RadarLineSeries__ and __RadarAreaSeries__.

## Pie Area
This concrete chart control visualizes its data points using radial coordinate system. Each point is represented as an arc segment where the arc’s length is actually the percentage this point’s value is from the total sum.

>caption Figure 2: Pie Area Chart
![WinForms RadChartView Pie Area Chart](images/chartview-overview004.png)

### Series Types
Pie Area supports __Pie__ and __Donut__ series and it does not use axes.

#### Pie Series
They visualize each data point as a pie slices with arc size directly proportional to the magnitude of the raw data point’s value.

#### Donut Series
They visualize each data point as a slice with arc size directly proportional to the magnitude of the raw data point’s value.

## Controllers
Both chart types (pie and cartesian) have a controllers collection that accepts ChartViewController objects. Each object represents a special interaction behavior such as __Scroll and Zoom__ or __TrackBall__.

## Features
__RadChartView__ provides a wide set of features.

#### Scroll And Zoom
__RadChartView__ provides zoom and scroll interactivity with the __ChartPanZoomController__ class.

#### Lasso Selection
This functionality is defined within the __LassoZoomController__ class and it allows the end use to lasso zoom (zoom to selection).

#### Selection
Selection behavior can also be added to the data points of the chart by using the __ChartSelectionController__.

#### Tooltip
Tooltip interactivity can be achieved by adding a __ChartTooltipController__ displaying arbitrary information about a particular data point.

#### Trackball
The __ChartTrackballController__ can display a vertical line across the chart plot area and also to display little visual indicators (circles by default) at points where the trackball line crosses the visualization of a series object.

#### Title and Legend
__RadChartView__ can display a title for the whole chart and different legends for each of the added series.

#### Smart Labels
__DataPoint__ labels can be arranged in a way so that any possible overlaps be resolved automatically. 

#### DrillDown
The drill down functionality of a chart allows users to click on a graphical element (bar, pie segment etc.), representing some data, in order to navigate to another view which contains different data than the first one.

#### Export
__RadChartView__ can be exported to a Bitmap image.

#### Chart Grid
The chart may be optionally decorated with grid-like visuals which support horizontal and vertical lines, associated with axis ticks and horizontal and vertical stripes – the area between two adjacent ticks. Such visuals are available for both Cartesian and Polar coordinates via Cartesian Grid and Polar Grid respectively.


## Telerik UI for WinForms Learning Resources
* [Telerik UI for WinForms ChartView Homepage](https://www.telerik.com/products/winforms/chartview.aspx)
* [Get Started with the Telerik UI for WinForms ChartView]({%slug winforms/chartview/getting-started%})
* [Telerik UI for WinForms API Reference](https://docs.telerik.com/devtools/winforms/api/)
* [Getting Started with Telerik UI for WinForms Components]({%slug winforms/getting-started/first-steps%})
* [Telerik UI for WinForms Virtual Classroom (Training Courses for Registered Users)](https://learn.telerik.com/learn/course/external/view/elearning/17/TelerikUIforWinForms) 
* [Telerik UI for WinForms Forum](https://www.telerik.com/forums/winforms)
* [Telerik UI for WinForms Knowledge Base](https://docs.telerik.com/devtools/winforms/knowledge-base)

# See Also

* [Design Time]({%slug winforms/chartview/design-time/smart-tag%})
* [Property Builder]({%slug winforms/chartview/design-time/property-builder%})
* [Getting Started]({%slug winforms/chartview/getting-started%})
* [Populating with Data]({%slug winforms/chartview-/populating-with-data%})
* [Series Types]({%slug winforms/chartview-/series-types%})
* [Axes Types]({%slug winforms/chartview-/axes%})
* [Features]({%slug winforms/chartview-/features/scroll-and-zoom%})
