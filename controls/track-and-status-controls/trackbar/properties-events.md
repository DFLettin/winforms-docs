---
title: Properties and Events
page_title: Properties and Events - WinForms TrackBar Control
description: RadTrackBar, sometimes called a slider control, can be used for navigating a large amount of information or for visually adjusting a numeric setting.
slug: winforms/track-and-status-controls/trackbar/properties-events
tags: programming,radtrackbar
published: True
position: 5 
---

# Properties

|Property|Description||
|----|----|----|
|**TrackBarElement**|Gets the instance of RadTrackBarElement wrapped by this control. RadTrackBarElement is the main element in the hierarchy tree and encapsulates the actual functionality of RadTrackBar.||
|**Minimum** and **Maximum**|Specify the lower end and upper end of the range which thumbs can scroll over. It is possible to specify a negative value for the Minimum.||
|**Value**|Gets or sets the value of the thumb in *SingleThumb* mode of RadTrackBar||
|**TickStyle**|Controls whether the tick marks are drawn on one or both sides of the control. The default value is *Both*. Setting __TickStyle__ to *None* will disable the ticks. Setting __TickStyle__ to *Both* will enable ticks on both sides. Setting __TickStyle__ to *TopLeft* will show only the ticks on the top side, when the Orientation is Horizontal. If the Orientation is set to Vertical, only the ticks on the left side will be shown. Setting __TickStyle__ to *BottomRight* will show only the ticks on the down side, when the Orientation is Horizontal. If the Orientation is set to Vertical, only the ticks on the right side will be shown.|![WinForms RadTrackBar TickStyle Top](images/track-and-status-controls-trackbar-programming-radtrackbar025.png)</br> ![WinForms RadTrackBar TickStyle Bottom](images/track-and-status-controls-trackbar-programming-radtrackbar026.png) </br> ![WinForms RadTrackBar TickStyle Both](images/track-and-status-controls-trackbar-programming-radtrackbar027.png)</br> ![WinForms RadTrackBar TickStyle None](images/track-and-status-controls-trackbar-programming-radtrackbar028.png)|
|**Orientation**|Gets or Sets the orientation of the RadTrackBar.|![WinForms RadTrackBar Horizontal Orientation](images/track-and-status-controls-trackbar-programming-radtrackbar029.png)</br>![WinForms RadTrackBar Vertical Orientation](images/track-and-status-controls-trackbar-programming-radtrackbar030.png)|
|**LargeChange**|Gets or sets the change in value that one click of the mouse outside of the slider makes. Let's say that the position of your thumb is at the beginning of the **RadTrackBar** (at position *0*), the value of this property is *5* and you click on tick number 14. The thumb will reposition itself to tick number *5*, following the step determined by the __LargeChange__ property. However, if the __LargeChange__  has value 0, the thumb will move to position 14.||
|**SmallChange**|Gets or Sets the number of positions that the trackbar moves in response to keyboard arrow keys and the trackbar buttons.||
|**TextOrientation**|Gets or Sets the orientation of the text associated with TrackBar. Whether it should appear horizontal or vertical.|![WinForms RadTrackBar TextOrientation](images/track-and-status-controls-trackbar-programming-radtrackbar031.png)|
|**LabelStyle**|Gets or Sets whether the RadTrackBar's labels should be drawn.The default value is None. *TopLeft* value will show only the labels on the top side, when the Orientation is Horizontal. If the Orientation is set to Vertical, only the labels on the left side will be shown.  *BottomRight* value will show only the labels on the bottom side, when the Orientation is Horizontal.  If the Orientation is set to Vertical, only the labels on the right side will be shown. *BottomRight* - will show only the labels on the bottom side, when the Orientation is Horizontal.  If the Orientation is set to Vertical, only the labels on the right side will be shown.|![WinForms RadTrackBar LabelStyle None](images/track-and-status-controls-trackbar-programming-radtrackbar032.png)</br>![WinForms RadTrackBar LabelStyle Top](images/track-and-status-controls-trackbar-programming-radtrackbar033.png)</br>![WinForms RadTrackBar LabelStyle Bottom](images/track-and-status-controls-trackbar-programming-radtrackbar034.png)</br>![WinForms RadTrackBar LabelStyle Both](images/track-and-status-controls-trackbar-programming-radtrackbar035.png)|
|**ShowButtons**|Controls the visibility of the navigation buttons in RadTrackBar. By default these buttons are not displayed. To show them, set the property to true.|![WinForms RadTrackBar ShowButtons](images/track-and-status-controls-trackbar-programming-radtrackbar036.png)|
|**LargeTickFrequency**|Sets the spacing between the large tick marks. The default value is *5*.|![WinForms RadTrackBar LargeTickFrequency](images/track-and-status-controls-trackbar-programming-radtrackbar015.png)|
|**SmallTickFrequency**|Sets the spacing between the small tick marks. The default value is 1.|![WinForms RadTrackBar SmallTickFrequency](images/track-and-status-controls-trackbar-programming-radtrackbar016.png)|
|**TrackBarMode**|Determinates in which mode the control will operate.  Each [WinForms RadTrackBar mode]({%slug winforms/track-and-status-controls/trackbar/modes%}) has different functionality and behavior.|![WinForms RadTrackBar TrackBarMode](images/track-and-status-controls-trackbar-programming-radtrackbar017.png)|
|**Ranges**|Gets the TrackBarRangeCollection.||
|**SnapMode**|Controls the way the thumb is moving in RadTrackBar. When this property is set to *SnapToTicks* the thumb is moving only at tick positions.  When the value is set to __None__ the slider is moving freely.|![WinForms RadTrackBar SnapMode None](images/track-and-status-controls-trackbar-programming-radtrackbar020.gif)</br>![WinForms RadTrackBar SnapToTick](images/track-and-status-controls-trackbar-programming-radtrackbar021.gif)|
|**ThumbSize**|Gets or Sets TrackBar's Size.|![WinForms RadTrackBar ThumbSize](images/track-and-status-controls-trackbar-programming-radtrackbar021.png)|
|**ShowSlideArea**|Controls whether the line down the middle of the control where the slider rides is drawn. The default value is *true*.|![WinForms RadTrackBar ShowSlideArea](images/track-and-status-controls-trackbar-programming-radtrackbar022.png)|

>important As of **R3 2019 SP1** **RadTrackBar** offers the **SnapFrequency** property. Its default value is *TrackBarSnapFrequency.Default* in order to keep the existing behavior unchanged. The other possible value  is *TrackBarSnapFrequency.Ticks* aiming to provide snap-to-ticks behavior if the **SnapMode** property is set to *SnapToTicks*. Thus, you can slide the thumb smoothly snapping to the small/large ticks.

![WinForms RadTrackBar TrackBarSnapFrequency Ticks](images/trackbar-snap-to-ticks001.gif)

# Events

|Event|Description|
|----|----|
|**ValueChanged**|Occurs after the user drags  the thumb and drops it somewhere on the slider area, or when the __Value__ property is set. In this event, you can get the value of RadTrackBar from its __Value__ property.|
|**LabelFormatting**|Occurs when a Label needs to be formatted.|
|**TickFormatting**|Occurs when a Tick needs to be formatted.|

#### Formatting ticks

{{source=..\SamplesCS\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.cs region=TickFormattingEvent}} 
{{source=..\SamplesVB\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.vb region=TickFormattingEvent}} 

````C#
void radTrackBar1_TickFormatting(object sender, TickFormattingEventArgs e)
{
    e.TickElement.Line1.BackColor = Color.Red;
}

````
````VB.NET
Private Sub radTrackBar1_TickFormatting(sender As Object, e As TickFormattingEventArgs)
    e.TickElement.Line1.BackColor = Color.Red
End Sub

````

{{endregion}} 

![WinForms RadTrackBar Formatting ticks](images/track-and-status-controls-trackbar-programming-radtrackbar023.png)

#### Formatting labels

{{source=..\SamplesCS\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.cs region=LabelFormattingEvent}} 
{{source=..\SamplesVB\TrackAndStatus\TrackBar\TrackBarPropertiesAndEvents.vb region=LabelFormattingEvent}} 

````C#
void radTrackBar1_LabelFormatting(object sender, LabelFormattingEventArgs e)
{
    e.LabelElement.ForeColor = Color.Red;
}

````
````VB.NET
Private Sub radTrackBar1_LabelFormatting(sender As Object, e As LabelFormattingEventArgs)
    e.LabelElement.ForeColor = Color.Red
End Sub

````

{{endregion}} 

![WinForms RadTrackBar Formatting labels](images/track-and-status-controls-trackbar-programming-radtrackbar024.png)

# See Also

* [Properties](https://docs.telerik.com/devtools/winforms/api/telerik.wincontrols.ui.radtrackbar.html#properties)
* [Methods](https://docs.telerik.com/devtools/winforms/api/telerik.wincontrols.ui.radtrackbar.html#methods)
* [Events](https://docs.telerik.com/devtools/winforms/api/telerik.wincontrols.ui.radtrackbar.html#events)


