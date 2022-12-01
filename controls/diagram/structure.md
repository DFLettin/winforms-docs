---
title: Structure
page_title: Structure - WinForms Diagram Control
description: Get familiar with the internal elements structure of WinForms Diagram. 
slug: winforms/diagram/structure
tags: structure
published: True
position: 1
previous_url: diagram-structure
---

# Structure

## Diagram structure

__RadDiagram__ allows you to create various kinds of diagrams like Organizational, Class and Flow as well as many others. This section defines terms and concepts used in the scope of __RadDiagram__ you have to get familiar with prior to continue reading this help. In the following picture you can see the main components which a __RadDiagram__ could have: 

![WinForms RadDiagram diagram-structure 001](images/diagram-structure001.png)

1. __Rotation Thumb__ - it is part of the manipulation adorner and you can use it to rotate the shape or group of shapes and connections.
            

1. __Resizing Thumb__ - every shape has four resizing thumbs that you can use to resize the shape.
               
      

1. __Connection__ -  its main purpose is to connect two shapes but it could be also used separately. You can select it, resize it, rotate it, copy/paste it.            
            

1. __Shape__ -  this is the base element of the diagram, just like a node for a graph. You can select it, drag it, resize it, rotate it, connect it to other shapes, set its content, copy/paste it. There are three types of predefined, geometrical shapes - Basic Shapes, Flow Shapes and Arrows. You can also define your own custom shape by deriving from RadDiagramShapeBase or RadDiagramShape class.
               

1. __Connector__ - every shape has four connectors. The connections connect shapes by linking their connectors.
            

1. __Manipulation Adorner__ - when a shape or group of shapes and connections is selected, they are being surrounded by manipulation rectangle called manipulation adorner.  

1. __Information Tooltips__ - tooltips that appear below the manipulation adorner when you resize, rotate or drag a shape or group of shapes and connections.
            

# See Also

* [Design Time]({%slug winforms/diagram/design-time%})
* [Getting Started]({%slug winforms/diagram/getting-started%})
