---
title: Background Grid
page_title: Background Grid - RadDiagram
description: RadDiagram offers flexible and interactive diagramming layouts for your rich data-visualization applications. 
slug: winforms/diagram/background-grid
tags: background,grid
published: True
position: 7
previous_url: diagram-backgroundgrid
---

# Background Grid

You can control the background settings of the diagramming surface through the following properties:
        

* __IsBackgroundSurfaceVisible__: a boolean property that determines whether the background surface of the __RadDiagram__  should be displayed. Its default value is *true*. 

#### Set IsBackgroundSurfaceVisible

{{source=..\SamplesCS\Diagram\DiagramBackgroundGrid.cs region=IsBackgroundSurfaceVisible}} 
{{source=..\SamplesVB\Diagram\DiagramBackgroundGrid.vb region=IsBackgroundSurfaceVisible}} 

````C#
            
this.radDiagram1.DiagramElement.IsBackgroundSurfaceVisible = true;

````
````VB.NET
Me.RadDiagram1.DiagramElement.IsBackgroundSurfaceVisible = True

````

{{endregion}} 
 

| __IsBackgroundSurfaceVisible__ = *true* | __IsBackgroundSurfaceVisible__ = *false* |
|----|----|
|![WinForms RadDiagram diagram-backgroundgrid 001](images/diagram-backgroundgrid001.png)|![WinForms RadDiagram diagram-backgroundgrid 002](images/diagram-backgroundgrid002.png)|

* __Background__: this property is of type *Brush* and it controls the fill of the __RadDiagram__ background.

#### Set Background         

{{source=..\SamplesCS\Diagram\DiagramBackgroundGrid.cs region=Background}} 
{{source=..\SamplesVB\Diagram\DiagramBackgroundGrid.vb region=Background}} 

````C#
        
this.radDiagram1.DiagramElement.BackgroundGrid.Background = new System.Drawing.SolidBrush(Color.LightYellow);

````
````VB.NET
Me.RadDiagram1.DiagramElement.BackgroundGrid.Background = New System.Drawing.SolidBrush(Color.LightYellow)

````

{{endregion}} 
 
>caption Figure 1: Background

![WinForms RadDiagram Background](images/diagram-backgroundgrid003.png)

You can access the __BackgroundGrid__ properties:

* __CellSize__: this property is of type *Telerik.Windows.Diagrams.Core.Size* and it controls the size of the cells in the __RadDiagram__ surface. The default value of this property is a size of *20x20 * units.
            
>caption Figure 2: CellSize

![WinForms RadDiagram CellSize](images/diagram-backgroundgrid004.png)

#### Set CellSize 
 
{{source=..\SamplesCS\Diagram\DiagramBackgroundGrid.cs region=CellSize}} 
{{source=..\SamplesVB\Diagram\DiagramBackgroundGrid.vb region=CellSize}} 

````C#
            
this.radDiagram1.DiagramElement.BackgroundGrid.CellSize = new Telerik.Windows.Diagrams.Core.Size(40, 40);

````
````VB.NET
Me.RadDiagram1.DiagramElement.BackgroundGrid.CellSize = New Telerik.Windows.Diagrams.Core.Size(40, 40)

````

{{endregion}} 

 
* __LineStroke__: this property is of type *Brush* and it specifies how the cells outline is painted.
            
>caption Figure 3: LineStroke

![WinForms RadDiagram LineStroke](images/diagram-backgroundgrid005.png)  

#### Set LineStroke

{{source=..\SamplesCS\Diagram\DiagramBackgroundGrid.cs region=LineStroke}} 
{{source=..\SamplesVB\Diagram\DiagramBackgroundGrid.vb region=LineStroke}} 

````C#
            
this.radDiagram1.DiagramElement.BackgroundGrid.LineStroke = new System.Drawing.SolidBrush(Color.Red);

````
````VB.NET
Me.RadDiagram1.DiagramElement.BackgroundGrid.LineStroke = New System.Drawing.SolidBrush(Color.Red)

````

{{endregion}} 
 
* __LineStrokeThickness__: this property is of type *double* and it gets or sets the thickness of the __RadDiagram__ background grid lines.
            
>caption Figure 4: LineStrokeThickness

![WinForms RadDiagram LineStrokeThickness](images/diagram-backgroundgrid006.png) 

#### Set LineStrokeThickness

{{source=..\SamplesCS\Diagram\DiagramBackgroundGrid.cs region=LineStrokeThickness}} 
{{source=..\SamplesVB\Diagram\DiagramBackgroundGrid.vb region=LineStrokeThickness}} 

````C#
        
this.radDiagram1.DiagramElement.BackgroundGrid.LineStrokeThickness = 5;

````
````VB.NET
Me.RadDiagram1.DiagramElement.BackgroundGrid.LineStrokeThickness = 5

````

{{endregion}} 

# See Also

* [RibbonUI]({%slug winforms/diagram/ribbonui%})	
* [Settings Pane]({%slug winforms/diagram/settings-pane%})	
* [Toolbox]({%slug winforms/diagram/toolbox%})



