---
title: Pan and Zoom
page_title: Pan and Zoom - RadMap
description: RadMap can be panned and zoomed both from the UI as well as programmatically.
slug: winforms/map/features/pan-and-zoom
tags: map, features, pan, zoom
published: True
position: 5
---

# Pan and Zoom

__RadMap__ can be panned and zoomed both from the UI as well as programmatically.

## UI Pan and Zoom

The end user can pan the control by simply holding the left mouse button and dragging the map to a desired location. The zoom operation can be performed with a double click on the map or by using the mouse scroll wheel. The same behavior can also be achieved with the [navigation controls]({%slug winforms/map/features/navigation-controls%}).

## Programmatic Pan and Zoom

The control exposes an API for panning and zooming programmatically. The responsible __Pan__ and __Zoom__ methods have several overloads handling different scenarios.

>caption Figure 1: Programmatic Pan and Zoom

![WinForms RadMap Programmatic Pan and Zoom](images/map-features-pan-and-zoom001.gif)

## Customizing Appearance

{{source=..\SamplesCS\Map\MapLayers.cs region=ZoomAndPan}} 
{{source=..\SamplesVB\Map\MapLayers.vb region=ZoomAndPan}}
````C#
this.radMap1.Zoom(8, true);
this.radMap1.Pan(new SizeL(200, 200));

````
````VB.NET
Me.RadMap1.Zoom(8, True)
Me.RadMap1.Pan(New SizeL(200, 200))

````



{{endregion}}

## ViewportChanged Event

To get notified when the users pan or zoom the __RadMap__ control, you can subscribe to the __ViewportChanged__ event of the control. When the map is Panned, this event will be called one time with __ViewportChangeAction__ set to __Pan__. However, when the map is Zoomed, first the map will be zoomed then it will be panned. This behavior will trigger the __ViewportChanged__ event twice. The first time the __ViewportChangeAction__ will be set to __ViewportChangeAction.Zoom__, the second time this property will be set to __ViewportChangeAction.All__.


# See Also

* [Layers Overview]({%slug winforms/map/features/layers/overview%})
* [Mini Map]({%slug winforms/map/features/minimap%})
* [Navigation Controls]({%slug winforms/map/features/navigation-controls%})
* [Scale Indicators]({%slug winforms/map/features/scale-indicators%})
* [Legend]({%slug winforms/map/features/legend%})
