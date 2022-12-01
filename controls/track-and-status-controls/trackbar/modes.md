---
title: Modes
page_title: Modes - WinForms TrackBar
description: WinForms TrackBar supports three different modes - SingleThumb, StartFromTheBeginning and Range.
slug: winforms/track-and-status-controls/trackbar/modes
tags: modes
published: True
position: 4
previous_url: track-and-status-controls-trackbar-modes
---

# Modes

**RadTrackBar** supports three different modes - *SingleThumb*, *StartFromTheBeginning* and *Range*. Each of these modes defines its own functionality and behavior. You can change the mode of the control via its __TrackBarMode__ property.
      
## SingleThumb

In this mode **RadTrackBar** works like a standard **TrackBar**. It contains one thumb and its value can be accessed through the __Value__ property of **RadTrackBar**. To receive notification when value is changed you can use the __ValueChanged__ event.

>caption Figure 1: 

![WinForms RadTrackBar ](images/track-and-status-controls-trackbar-modes001.png)

## StartFromTheBeginning

In this mode **RadTrackBar** looks like **RadTrackBar** in *SingleThumb* mode, but it can contain more than one thumb. To show more than one thumb you should add the desired ranges (__TrackBarRange__) in the __Ranges__ collection of control. For example:

{{source=..\SamplesCS\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.cs region=TrackBarModeStartFromTheBeginning}} 
{{source=..\SamplesVB\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.vb region=TrackBarModeStartFromTheBeginning}} 

````C#
this.radTrackBar1.TrackBarMode = Telerik.WinControls.UI.TrackBarRangeMode.StartFromTheBeginning;
this.radTrackBar1.Ranges.Add(new TrackBarRange(0, 5, "MyRange1"));
this.radTrackBar1.Ranges.Add(new TrackBarRange(0, 15, "MyRange2"));

````
````VB.NET
Me.RadTrackBar1.TrackBarMode = Telerik.WinControls.UI.TrackBarRangeMode.StartFromTheBeginning
Me.RadTrackBar1.Ranges.Add(New TrackBarRange(0, 5, "MyRange1"))
Me.RadTrackBar1.Ranges.Add(New TrackBarRange(0, 15, "MyRange2"))

````

{{endregion}} 


![WinForms RadTrackBar track-and-status-controls-trackbar-modes 002](images/track-and-status-controls-trackbar-modes002.png)

In order to access the values of the thumbs in this mode you should go through the __Ranges__ collection and check the values of each __TrackBarRange__. Please, note that even though __TrackBarRange__ has both __Start__ and __End__ properties, in this mode **RadTrackBar** uses only the __End__ property, so you should access it in order to take the value of some range.

{{source=..\SamplesCS\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.cs region=accessValuesStartFromTheBeginningMode}} 
{{source=..\SamplesVB\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.vb region=accessValuesStartFromTheBeginningMode}} 

````C#
float fitstRangeValue = this.radTrackBar1.Ranges[0].End;
float secondRangeValue = this.radTrackBar1.Ranges[1].End;

````
````VB.NET
Dim fitstRangeValue As Single = Me.RadTrackBar1.Ranges(0).[End]
Dim secondRangeValue As Single = Me.RadTrackBar1.Ranges(1).[End]

````

{{endregion}} 

To receive notification when the **Value** is changed in this mode, you should use the __RangeValueChanged__ event of the __RadTrackBar__:

{{source=..\SamplesCS\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.cs region=Ranges_CollectionChangedEvent}} 
{{source=..\SamplesVB\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.vb region=Ranges_CollectionChangedEvent}}
````C#
private void RadTrackBar1_RangeValueChanged(object sender, RangeChangedEventArgs e)
{
    Console.WriteLine("Radge {0} Start {1}, End {2}", e.ChangedRange.Text, e.ChangedRange.Start, e.ChangedRange.End);
}

````
````VB.NET
Private Sub RadTrackBar1_RangeValueChanged(ByVal sender As Object, ByVal e As RangeChangedEventArgs)
    Console.WriteLine("Radge {0} Start {1}, End {2}", e.ChangedRange.Text, e.ChangedRange.Start, e.ChangedRange.End)
End Sub

```` 
 

{{endregion}} 

## Range

This mode allows you to define one or more __Ranges__ with __Start__ and __End__ values.  In this mode there the __Ranges__ cannot to overlap each other. To display a second range, you should add the desired __Range (TrackBarRange)__ in the __Ranges__ collection of the control. For example:

{{source=..\SamplesCS\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.cs region=TrackBarModeRange}} 
{{source=..\SamplesVB\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.vb region=TrackBarModeRange}} 

````C#
this.radTrackBar1.TrackBarMode = Telerik.WinControls.UI.TrackBarRangeMode.Range;
this.radTrackBar1.Ranges[0].Start = 2;
this.radTrackBar1.Ranges[0].End = 5;
this.radTrackBar1.Ranges.Add(new TrackBarRange(10, 15));

````
````VB.NET
Me.RadTrackBar1.TrackBarMode = Telerik.WinControls.UI.TrackBarRangeMode.Range
Me.RadTrackBar1.Ranges(0).Start = 2
Me.RadTrackBar1.Ranges(0).[End] = 5
Me.RadTrackBar1.Ranges.Add(New TrackBarRange(10, 15))

````

{{endregion}} 

![WinForms RadTrackBar track-and-status-controls-trackbar-modes 003](images/track-and-status-controls-trackbar-modes003.png)

To receive notification when the **Value** is changed in this mode, you should use the __RangeValueChanged__ event of the RadTrackBar:

{{source=..\SamplesCS\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.cs region=Ranges_CollectionChangedEvent}} 
{{source=..\SamplesVB\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.vb region=Ranges_CollectionChangedEvent}}
````C#
private void RadTrackBar1_RangeValueChanged(object sender, RangeChangedEventArgs e)
{
    Console.WriteLine("Radge {0} Start {1}, End {2}", e.ChangedRange.Text, e.ChangedRange.Start, e.ChangedRange.End);
}

````
````VB.NET
Private Sub RadTrackBar1_RangeValueChanged(ByVal sender As Object, ByVal e As RangeChangedEventArgs)
    Console.WriteLine("Radge {0} Start {1}, End {2}", e.ChangedRange.Text, e.ChangedRange.Start, e.ChangedRange.End)
End Sub

```` 

 

{{endregion}} 

>important The __Ranges__ collection of **RadTrackBar** contains one default range that is used to display a default range for all modes. This collection should always contain at least one range, so if you execute the *Clear* method of the collection all ranges except the first one will be removed.
>

>note When the mode is changed from __StartFromTheBeginning__ to something else, the __Ranges__ collection will be reset to prevent overlappings that are not allowed in the other modes.
>

# See Also

* [Structure]({%slug winforms/track-and-status-controls/trackbar/control-element-structure%})	
* [Design Time]({%slug winforms/track-and-status-controls/trackbar/design-time%})
* [Getting Started]({%slug winforms/track-and-status-controls/trackbar/getting-started%})	
* [Properties and Events]({%slug winforms/track-and-status-controls/trackbar/properties-events%})	
