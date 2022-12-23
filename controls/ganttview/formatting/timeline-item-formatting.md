---
title: Timeline Item Formatting
page_title: Timeline Item Formatting - RadGanttView
description: The TimelineItemFormatting event allows you to format the style and look of the items in the timeline container.
slug: winforms/ganttview-/formatting/timeline-item-formatting
tags: timeline,item,formatting
published: True
position: 2
previous_url: ganttview-formatting-timelineviewitem-formatting
---

# Timeline Item Formatting

The __TimelineItemFormatting__ event allows you to format the style and look of the items in the timeline container. The following example demonstrates how to make the timeline appear as a checkered flag.
         
{{source=..\SamplesCS\GanttView\Formatting\TimelineItemFormatting.cs region=TimelineItemFormatting}} 
{{source=..\SamplesVB\GanttView\Formatting\TimelineItemFormatting.vb region=TimelineItemFormatting}} 

````C#
private void radGanttView1_TimelineItemFormatting(object sender, GanttViewTimelineItemFormattingEventArgs e)
{
    CultureInfo currentCulture = CultureInfo.CurrentCulture;
    int weekNo = currentCulture.Calendar.GetWeekOfYear(e.Item.Start, currentCulture.DateTimeFormat.CalendarWeekRule, currentCulture.DateTimeFormat.FirstDayOfWeek);
    Color color1 = Color.Black;
    Color color2 = Color.White;
    if (weekNo % 2 == 0)
    {
        color1 = Color.White;
        color2 = Color.Black;
    }
    e.ItemElement.TopElement.DrawFill = true;
    e.ItemElement.TopElement.DrawBorder = false;
    e.ItemElement.TopElement.GradientStyle = GradientStyles.Solid;
    e.ItemElement.TopElement.BackColor = color1;
    e.ItemElement.TopElement.ForeColor = color2;
    foreach (LightVisualElement element in e.ItemElement.BottomElement.Children)
    {
        element.BackColor = color2;
        element.ForeColor = color1;
        element.DrawBorder = false;
    }
}

````
````VB.NET
Private Sub radGanttView1_TimelineItemFormatting(sender As Object, e As GanttViewTimelineItemFormattingEventArgs)
    Dim currentCulture As CultureInfo = CultureInfo.CurrentCulture
    Dim weekNo As Integer = currentCulture.Calendar.GetWeekOfYear(e.Item.Start, currentCulture.DateTimeFormat.CalendarWeekRule, currentCulture.DateTimeFormat.FirstDayOfWeek)
    Dim color1 As Color = Color.Black
    Dim color2 As Color = Color.White
    If weekNo Mod 2 = 0 Then
        color1 = Color.White
        color2 = Color.Black
    End If
    e.ItemElement.TopElement.DrawFill = True
    e.ItemElement.TopElement.DrawBorder = False
    e.ItemElement.TopElement.GradientStyle = GradientStyles.Solid
    e.ItemElement.TopElement.BackColor = color1
    e.ItemElement.TopElement.ForeColor = color2
    For Each element As LightVisualElement In e.ItemElement.BottomElement.Children
        element.BackColor = color2
        element.ForeColor = color1
        element.DrawBorder = False
    Next
End Sub

````

{{endregion}} 

![WinForms RadGanttView Timeline Item Formatting](images/ganttview-formatting-timelineviewitem-formatting001.png)

# See Also

* [GraphicalView item formatting]({%slug winforms/ganttview-/formatting/graphicalview-item-formatting%})
* [GraphicalView Link Item formatting]({%slug winforms/ganttview-/formatting/graphicalview-link-item-formatting%})
* [TextView item formatting]({%slug winforms/ganttview-/formatting/textview-item-formatting%})
* [Themes]({%slug winforms/ganttview/themes%})
* [Custom Painting]({%slug winforms/ganttview-/formatting/custom-painting%})
