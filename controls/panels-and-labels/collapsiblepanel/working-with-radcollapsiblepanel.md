---
title: Working with RadCollapsiblePanel
page_title: Working with RadCollapsiblePanel - WinForms CollapsiblePanel Control
description: This article demonstrates how RadCollapsiblePanel can be manipulated via its API.
slug: winforms/panels-and-labels/collapsiblepanel/methods-and-properties
tags: methods,and,properties
published: True
position: 5
previous_url: panels-and-labels-collapsible-panel-methods-and-properties
---

# Working with RadCollapsiblePanel

This article demonstrates how **RadCollapsiblePanel** can be manipulated via its API. 

## Important Properties

__ExpandDirection__ - Indicates the direction of the expand animation. The collapse animation is in the opposite direction.

#### RadDirection.Down

{{source=..\SamplesCS\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.cs region=ExpandDirections1}} 
{{source=..\SamplesVB\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.vb region=ExpandDirections1}} 

````C#
this.radCollapsiblePanel1.ExpandDirection = RadDirection.Down;

````
````VB.NET
Me.RadCollapsiblePanel1.ExpandDirection = RadDirection.Down

````

{{endregion}}

![WinForms RadTemplates panels-and-labels-radcollapsiblepanel-methods-and-properties 001](images/panels-and-labels-radcollapsiblepanel-methods-and-properties001.png)

#### RadDirection.Left

{{source=..\SamplesCS\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.cs region=ExpandDirections2}} 
{{source=..\SamplesVB\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.vb region=ExpandDirections2}} 

````C#
this.radCollapsiblePanel1.ExpandDirection = RadDirection.Left;

````
````VB.NET
Me.RadCollapsiblePanel1.ExpandDirection = RadDirection.Left

````

{{endregion}} 


![WinForms RadTemplates panels-and-labels-radcollapsiblepanel-methods-and-properties 002](images/panels-and-labels-radcollapsiblepanel-methods-and-properties002.png)

#### RadDirection.Right

{{source=..\SamplesCS\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.cs region=ExpandDirections3}} 
{{source=..\SamplesVB\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.vb region=ExpandDirections3}} 

````C#
this.radCollapsiblePanel1.ExpandDirection = RadDirection.Right;

````
````VB.NET
Me.RadCollapsiblePanel1.ExpandDirection = RadDirection.Right

````

{{endregion}} 


![WinForms RadTemplates panels-and-labels-radcollapsiblepanel-methods-and-properties 003](images/panels-and-labels-radcollapsiblepanel-methods-and-properties003.png)

#### RadDirection.Up

{{source=..\SamplesCS\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.cs region=ExpandDirections4}} 
{{source=..\SamplesVB\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.vb region=ExpandDirections4}} 

````C#
this.radCollapsiblePanel1.ExpandDirection = RadDirection.Up;

````
````VB.NET
Me.RadCollapsiblePanel1.ExpandDirection = RadDirection.Up

````

{{endregion}} 


![WinForms RadTemplates panels-and-labels-radcollapsiblepanel-methods-and-properties 004](images/panels-and-labels-radcollapsiblepanel-methods-and-properties004.png)

__EnableAnimation__ - Indicates whether to use animation to expand or collapse the control.

{{source=..\SamplesCS\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.cs region=EnableAnimation}} 
{{source=..\SamplesVB\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.vb region=EnableAnimation}} 

````C#
this.radCollapsiblePanel1.EnableAnimation = false;

````
````VB.NET
Me.RadCollapsiblePanel1.EnableAnimation = False

````

{{endregion}}

__ContentSizingMode__ -  Indicates whether the controls container will resize to fit the width or the height of its content.

{{source=..\SamplesCS\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.cs region=ContentSizingMode1}} 
{{source=..\SamplesVB\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.vb region=ContentSizingMode1}} 

````C#
this.radCollapsiblePanel1.ContentSizingMode = CollapsiblePanelContentSizingMode.FitToContentWidth;

````
````VB.NET
Me.RadCollapsiblePanel1.ContentSizingMode = CollapsiblePanelContentSizingMode.FitToContentWidth

````

{{endregion}} 


![WinForms RadTemplates panels-and-labels-radcollapsiblepanel-methods-and-properties 005](images/panels-and-labels-radcollapsiblepanel-methods-and-properties005.png)

{{source=..\SamplesCS\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.cs region=ContentSizingMode2}} 
{{source=..\SamplesVB\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.vb region=ContentSizingMode2}} 

````C#
this.radCollapsiblePanel1.ContentSizingMode = CollapsiblePanelContentSizingMode.FitToContentHeight;

````
````VB.NET
Me.RadCollapsiblePanel1.ContentSizingMode = CollapsiblePanelContentSizingMode.FitToContentHeight

````

{{endregion}} 

![WinForms RadTemplates panels-and-labels-radcollapsiblepanel-methods-and-properties 006](images/panels-and-labels-radcollapsiblepanel-methods-and-properties006.png)

{{source=..\SamplesCS\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.cs region=ContentSizingMode3}} 
{{source=..\SamplesVB\PanelsAndLabels\CollapsiblePanel\CollapsiblePanelGettingStarted.vb region=ContentSizingMode3}} 

````C#
this.radCollapsiblePanel1.ContentSizingMode = CollapsiblePanelContentSizingMode.FitToContentWidth | CollapsiblePanelContentSizingMode.FitToContentHeight;

````
````VB.NET
Me.RadCollapsiblePanel1.ContentSizingMode = CollapsiblePanelContentSizingMode.FitToContentWidth Or CollapsiblePanelContentSizingMode.FitToContentHeight

````

{{endregion}} 


![WinForms RadTemplates panels-and-labels-radcollapsiblepanel-methods-and-properties 007](images/panels-and-labels-radcollapsiblepanel-methods-and-properties007.png)

**ShowHeaderLine** - If *true*, a line will be displayed in the header which will fill the available space, otherwise it will not be displayed.

![WinForms RadTemplates panels-and-labels-radcollapsiblepanel-methods-and-properties 008](images/panels-and-labels-radcollapsiblepanel-methods-and-properties008.png)

__HorizontalHeaderAlignment__ -Determines how the elements in the header to be aligned when it is in a horizontal position:

* Center

* Right

* Left

* Stretch

__VerticalHeaderAlignment__ - Determines how the elements in the header to be aligned when it is in a vertical position:

* Center

* Bottom

* Top

* Stretch

__AnimationType__ - Determines the type of the animation when expanding or collapsing the control:

* Reveal

![WinForms RadTemplates panels-and-labels-collapsible-panel-methods-and-properties 010](images/panels-and-labels-collapsible-panel-methods-and-properties010.gif)

* Slide

![WinForms RadTemplates panels-and-labels-collapsible-panel-methods-and-properties 011](images/panels-and-labels-collapsible-panel-methods-and-properties011.gif)

# See Also

* [Properties, Methods and Events]({%slug winforms/panels-and-labels/collapsiblepanel/properties-methods-events%})
