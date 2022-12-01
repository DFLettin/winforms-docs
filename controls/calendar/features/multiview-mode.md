---
title: MultiView Mode
page_title: MultiView Mode - WinForms Calendar Control
description: WinForms Calendar can be configured to show more than one month in the calendar area.
slug: winforms/calendar/customizing-behavior/multiview-mode
tags: multiview,mode
published: True
position: 3
previous_url: calendar-customizing-behavior-customizing-multi-view, /calendar/customizing-behavior/multiview-mode
---

# MultiView Mode

__RadCalendar__ can be configured to show more than one month in the calendar area. To enable this functionality set the __AllowMultipleView__ property to *true*, then set integer properties __MultiViewColumns__ and __MultiViewRows__ to the number of month views you wish to have displayed. The position of the month view that contains the selected date is controlled by the __CurrentViewRow__ and __CurrentViewColumn__ properties.

>caption Figure 1: MultiView with 2 rows and 2 columns
![WinForms RadCalendar MultiView with  rows and  columns](images/calendar-features-multi-view-mode001.png)

The code sample below shows how multiple views can be configured and positioned. Here the __CurrentViewRow__ and __CurrentViewColumn__ are set to zero, i.e. that is the first row and column. The selected date is shown in the upper left month view. 

#### Configuring multiple views

{{source=..\SamplesCS\Calendar\MultiViewCalendar.cs region=multiView}} 
{{source=..\SamplesVB\Calendar\MultiViewCalendar.vb region=multiView}} 

````C#
radCalendar1.AllowMultipleView = true;
radCalendar1.MultiViewColumns = 3;
radCalendar1.MultiViewRows = 3;
radCalendar1.CurrentViewColumn = 0;
radCalendar1.CurrentViewRow = 0;

````
````VB.NET
RadCalendar1.AllowMultipleView = True
RadCalendar1.MultiViewColumns = 3
RadCalendar1.MultiViewRows = 3
RadCalendar1.CurrentViewColumn = 0
RadCalendar1.CurrentViewRow = 0

````

{{endregion}} 

>caption Figure 2: MultiView with 3 rows and 3 columns
![WinForms RadCalendar MultiView with  rows and  columns](images/calendar-features-multi-view-mode002.png)

## See Also

* [Header]({%slug winforms/calendar/customizing-appearance/header%})
* [Footer]({%slug winforms/calendar/customizing-appearance/footer%})
* [Keyboard Navigation]({%slug  winforms/calendar/customizing-behavior/keyboard-navigation%})
* [Column and Row Headers]({%slug  winforms/calendar/customizing-behavior/column-and-row-headers%})
* [Navigation]({%slug winforms/calendar/customizing-behavior/customizing-navigation%})
* [Repeating Events]({%slug winforms/calendar/customizing-behavior/repeating-events%})
* [Selecting Dates]({%slug winforms/calendar/customizing-behavior/selecting-dates%})
* [Zoom]({%slug winforms/calendar/customizing-appearance/zooming%})


