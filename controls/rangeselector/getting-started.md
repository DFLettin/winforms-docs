---
title: Getting Started
page_title: Getting Started - WinForms RangeSelector Control
description: WinForms RangeSelector provides an elegant solution for end-users to select range (in percentages) and these percentages could be mapped to any kind of visually represented data. 
slug: winforms/rangeselector/getting-started
tags: getting,started
published: True
position: 3
previous_url: rangeselector-getting-started
---

# Getting Started

This tutorial demonstrates how to use __RadRangeSelector__ to get a fine grain view of the data represented in __RadChartView__.

1\. Place a __RadRangeSelector__ and __RadChartView__ controls on a form.

2\. Setup your __RadChartView__ with some data.

3\. Associate the __RadChartView__ control to __RadRangeSelector__ by setting its __AssociatedControl__ property. You can do that by one of the following ways:

* Set in code:

{{source=..\SamplesCS\RangeSelector\RangeSelectorGettingStarted.cs region=set associatedControl}} 
{{source=..\SamplesVB\RangeSelector\RangeSelectorGettingStarted.vb region=set associatedControl}} 

````C#
this.radRangeSelector1.AssociatedControl = this.radChartView1;

````
````VB.NET
Me.radRangeSelector1.AssociatedControl = Me.radChartView1

````

{{endregion}}

* Set in Property Builder at design time:

    ![WinForms RadRangeSelector Property Builder](images/rangeselector-getting-started001.png)

* Set it by using the control’s SmartTag at design time:
    ![WinForms RadRangeSelector Smart Tag ](images/rangeselector-getting-started002.png)

4\. Press F5 to run the project.
    ![WinForms RadRangeSelector Visualization](images/rangeselector-getting-started003.gif)

# See Also

* [Design Time]({%slug winforms/rangeselector/design-time%})
* [Structure]({%slug winforms/rangeselector/structure%})
* [Integration with RadChartView]({%slug winforms/rangeselector/integration-with-radchartview%})
