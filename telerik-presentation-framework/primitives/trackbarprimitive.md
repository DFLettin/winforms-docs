---
title: TrackBarPrimitive
page_title: TrackBarPrimitive - Telerik Presentation Framework
description: TrackBarPrimitive provides the basic visual layout of a track-bar background.
slug: winforms/telerik-presentation-framework/primitives/trackbarprimitive
tags: trackbarprimitive
published: True
position: 14
previous_url: tpf-primitives-trackbarprimitive
---

# TrackBarPrimitive
 

TrackBarPrimitive provides the basic visual layout of a trackbar background.  Typically you would use a higher level object, i.e. the [RadTrackBarElement]({%slug winforms/telerik-presentation-framework/elements/radtrackbarelement%}) to include in your control. [RadTrackBarElement]({%slug winforms/telerik-presentation-framework/elements/radtrackbarelement%}) handles the position of the track bar thumb and the various events that go into making the track bar useful.

![tpf-primitives-trackbarprimitive 001](images/tpf-primitives-trackbarprimitive001.png)

#### Creating a TrackBarPrimitive

{{source=..\SamplesCS\TPF\Primitives\TrackBarPrimitive1\MyTrackBarPrimitiveElement.cs region=myTrackBarPrimitiveElement}} 
{{source=..\SamplesVB\TPF\Primitives\TrackBarPrimitive1\MyTrackBarPrimitiveElement.vb region=myTrackBarPrimitiveElement}} 

````C#
public class MyTrackBarPrimitiveElement : RadElement
{
    protected override void CreateChildElements()
    {        
        TrackBarPrimitive trackBarPrimitive = new TrackBarPrimitive();
        trackBarPrimitive.ForeColor = Color.Blue;
        trackBarPrimitive.BackColor = Color.SkyBlue;
        trackBarPrimitive.TickColor = Color.Green;
        trackBarPrimitive.ThumbWidth = 5;
        trackBarPrimitive.ShowSlideArea = true;
        trackBarPrimitive.TickStyle = Telerik.WinControls.Enumerations.TickStyles.Both;
        trackBarPrimitive.TrackBarOrientation = Orientation.Horizontal;
        this.Children.Add(trackBarPrimitive);
        base.CreateChildElements();
    }
}

````
````VB.NET
Public Class MyTrackBarPrimitiveElement
    Inherits RadElement
    Protected Overrides Sub CreateChildElements()
        Dim trackBarPrimitive As New TrackBarPrimitive()
        trackBarPrimitive.ForeColor = Color.Blue
        trackBarPrimitive.BackColor = Color.SkyBlue
        trackBarPrimitive.TickColor = Color.Green
        trackBarPrimitive.ThumbWidth = 5
        trackBarPrimitive.ShowSlideArea = True
        trackBarPrimitive.TickStyle = Telerik.WinControls.Enumerations.TickStyles.Both
        trackBarPrimitive.TrackBarOrientation = Orientation.Horizontal
        Me.Children.Add(trackBarPrimitive)
        MyBase.CreateChildElements()
    End Sub
End Class

````

{{endregion}}

# See Also
* [ArrowPrimitive]({%slug winforms/telerik-presentation-framework/primitives/arrowprimitive%})

* [BorderPrimitive]({%slug winforms/telerik-presentation-framework/primitives/borderprimitive%})

* [CheckPrimitive]({%slug winforms/telerik-presentation-framework/primitives/checkprimitive%})

* [FillPrimitive]({%slug winforms/telerik-presentation-framework/primitives/fillprimitive%})

* [FocusPrimitive]({%slug winforms/telerik-presentation-framework/primitives/focusprimitive%})

* [GripPrimitive]({%slug winforms/telerik-presentation-framework/primitives/gripprimitive%})

* [ImagePrimitive]({%slug winforms/telerik-presentation-framework/primitives/imageprimitive%})

* [ImageShape]({%slug winforms/telerik-presentation-framework/primitives/imageshape%})

