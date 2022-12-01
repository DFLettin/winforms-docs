---
title: Formating Items
page_title: Formating Items - WinForms Calendar Control
description: Learn how one can change the styles of the RadCalendar elements upon a condition.
slug: winforms/calendar/customizing-appearance/formatting-items
tags: formating, items
published: True
position: 0
---

# Formatting Items

The __ElementRender__ event will be fired before every element is painted. This allows to easily change the styles of the elements at runtime, or format the items upon a condition. The following example shows how you can change the the border for a particular days. 

#### Formating items in the ElementRender event.

{{source=..\SamplesCS\Calendar\FormattingItems.cs region=RenderEvent}}
{{source=..\SamplesVB\Calendar\FormattingItems.vb region=RenderEvent}}
````C#
private void RadCalendar1_ElementRender(object sender, RenderElementEventArgs e)
{
    if (e.Day.Date.DayOfWeek == DayOfWeek.Monday || e.Day.Date.DayOfWeek == DayOfWeek.Thursday)
    {
        e.Element.DrawBorder = true;
        e.Element.BorderColor = ColorTranslator.FromHtml("#51ab2e");
    }
    else
    {
        e.Element.ResetValue(LightVisualElement.DrawBorderProperty, ValueResetFlags.Local);
        e.Element.ResetValue(LightVisualElement.BorderColorProperty, ValueResetFlags.Local);
    }
}

````
````VB.NET
Private Sub RadCalendar1_ElementRender(ByVal sender As Object, ByVal e As RenderElementEventArgs)
    If e.Day.Date.DayOfWeek = DayOfWeek.Monday OrElse e.Day.Date.DayOfWeek = DayOfWeek.Thursday Then
        e.Element.DrawBorder = True
        e.Element.BorderColor = ColorTranslator.FromHtml("#51ab2e ")
    Else
        e.Element.ResetValue(LightVisualElement.DrawBorderProperty, ValueResetFlags.Local)
        e.Element.ResetValue(LightVisualElement.BorderColorProperty, ValueResetFlags.Local)
    End If
End Sub

````

{{endregion}}

>caption Figure 1: RadCalendar with custom cells border.
![WinForms RadCalendar RadCalendar with custom cells border](images/calendar-formatting-items001.png)

## Refresh the visual elements at runtime.

Since the event is called when the calendar is made visible, you may need to trigger it again at run-time. This can be done by calling __RefreshVisuals__ method.

#### Trigger the ElementRender event at run-time.

{{source=..\SamplesCS\Calendar\FormattingItems.cs region=refresh}}
{{source=..\SamplesVB\Calendar\FormattingItems.vb region=refresh}}
````C#
radCalendar1.CalendarElement.RefreshVisuals();

````
````VB.NET
radCalendar1.CalendarElement.RefreshVisuals()

````

{{endregion}}


## See Also

* [Themes]({%slug winforms/calendar/customizing-appearance/styling%})

* [Using Templates]({%slug winforms/calendar/customizing-appearance/using-templates%})

