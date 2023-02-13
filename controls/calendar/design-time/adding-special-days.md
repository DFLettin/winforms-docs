---
title: Adding Special Days
page_title: Adding Special Days - WinForms Calendar Control
description: Learn how to add special days in WinForms Calendar.
slug: winforms/calendar/design-time-support/adding-special-days
tags: adding,special,days
published: True
position: 1
previous_url: calendar-design-time-support-adding-special-dates
---

# Adding Special Days


"Special days" correspond to public holidays, vacation days, birth days, etc. and are usually marked in a calendar for planning and scheduling purposes. Click the ellipses of the __SpecialDays__ property in the `Properties` window to add, remove and configure special days. The __Special Days Collection Editor__ allows you to: 

* Click the __Add__ button to append a __RadCalendarDay__ object to the collection.
            

* Click the __Remove__ button to delete the selected day from the collection.
            

* Use the up and down arrow keys to reorder special days in the collection. 

* Configure a selected __RadCalendarDay__ including assign an __Image__, set the day to __Disabled__, [set the Recurring enumeration]({%slug winforms/calendar/customizing-behavior/repeating-events%}), determine if the day is __Selectable__, if it is __Selected__ and assign a __ToolTip__. Assign __TemplateItems__ if __RadHostItems__ are available, otherwise see [Using Templates]({%slug winforms/calendar/customizing-appearance/using-templates%}) for how to do this in code.

>caption Figure 1: Adding special days.

![WinForms RadCalendar Adding special days](images/calendar-design-time-support-adding-special-dates001.png)

## See Also

* [Smart Tag]({%slug winforms/calendar/smart-tag%})

* [Adding Selected Dates]({%slug winforms/calendar/design-time-support/adding-selected-dates%})
