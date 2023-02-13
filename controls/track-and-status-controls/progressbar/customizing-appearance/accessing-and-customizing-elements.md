---
title: Accessing and Customizing Elements
page_title: Accessing and Customizing Elements - WinForms ProgressBar
description: Learn how to access and customize elements either at design time, or at run time. 
slug: winforms/track-and-status-controls/progressbar/accessing-and-customizing-elements
tags: progressbar
published: True
position: 0 
---

# Accessing and Customizing Elements
 
Accessing and customizing elements can be performed either at design time, or at run time. Before proceeding with this topic, it is recommended to get familiar with the [visual structure]({%slug winforms/track-and-status-controls/progressbar/control-element-structure%}) of **RadProgressBar**.
      

## Design time

You can access and modify the style for different elements in **RadProgressBar** by using the *Element hierarchy editor*.

>caption Figure 1: Element hierarchy editor

![WinForms RadProgressBar Element hierarchy editor](images/progressbar-accessing-and-customizing-elements001.png)

## Programmatically

You can customize the nested elements at run time as well:

#### Customize elements 

{{source=..\SamplesCS\TrackAndStatus\ProgressBar\ProgressGettingStarted.cs region=CustomizeElements}} 
{{source=..\SamplesVB\TrackAndStatus\ProgressBar\ProgressGettingStarted.vb region=CustomizeElements}} 

````C#
this.radProgressBar1.ForeColor = Color.Red;
this.radProgressBar1.ProgressBarElement.IndicatorElement1.BackColor = Color.Lime;
this.radProgressBar1.ProgressBarElement.IndicatorElement1.DrawBorder = true;
this.radProgressBar1.ProgressBarElement.IndicatorElement1.BorderColor = Color.Fuchsia;
this.radProgressBar1.ProgressBarElement.IndicatorElement1.BorderGradientStyle = Telerik.WinControls.GradientStyles.Solid;

````
````VB.NET
Me.RadProgressBar1.ForeColor = Color.Red
Me.RadProgressBar1.ProgressBarElement.IndicatorElement1.BackColor = Color.Lime
Me.RadProgressBar1.ProgressBarElement.IndicatorElement1.DrawBorder = True
Me.RadProgressBar1.ProgressBarElement.IndicatorElement1.BorderColor = Color.Fuchsia
Me.RadProgressBar1.ProgressBarElement.IndicatorElement1.BorderGradientStyle = Telerik.WinControls.GradientStyles.Solid

````

{{endregion}}  

# See Also

* [Themes]({%slug winforms/track-and-status-controls/progressbar/themes%})	
