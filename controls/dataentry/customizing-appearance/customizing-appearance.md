---
title: Customizing Appearance 
page_title: Customizing Appearance - WinForms DataEntry Control
description: Learn how one can customize the RadDataEntry appearance.
slug: winforms/dataentry/customizing-appearance
tags: appearance
published: True
position: 0
---

# Customizing Appearance

Accessing and customizing elements can be performed either at design time, or at run time. Before proceeding with this topic, it is recommended to get familiar with the [visual structure]({%slug winforms/dataentry/control-element-structure%}) of the RadDataEntry.

## Design Time

You can access and modify the style for different elements in __RadDataEntry__ by using the `Element Hierarchy Editor`.

>caption Fig.1 Element Hierarchy Editor

![WinForms RadDataEntry Element Hierarchy Editor](images/dataentry-customizing-appearance001.png)   

## Programmatically

The following snippet show how you can customize the RadDataEntry styles at runtime. 

#### Change Border Color

{{source=..\SamplesCS\DataEntryAndBindingNavigator\RadDataEntryHowTo.cs region=SetBorderColor}} 
{{source=..\SamplesVB\DataEntryAndBindingNavigator\RadDataEntryHowTo.vb region=SetBorderColor}}
````C#
radDataEntry1.DataEntryElement.Border.ForeColor = ColorTranslator.FromHtml("#e83737");

````
````VB.NET
radDataEntry1.DataEntryElement.Border.ForeColor = ColorTranslator.FromHtml("#e83737")

```` 

{{endregion}}

>caption Fig2. The changed border.

![WinForms RadDataEntry Fig The changed border](images/dataentry-customizing-appearance002.png)  

## Changing The Styles Of The Underlying Controls. 

The following snippet shows how you access the underlying controls and change the their styles:

#### Set Labels ForeColor

{{source=..\SamplesCS\DataEntryAndBindingNavigator\RadDataEntryHowTo.cs region=LabelColor}} 
{{source=..\SamplesVB\DataEntryAndBindingNavigator\RadDataEntryHowTo.vb region=LabelColor}}
````C#
foreach (RadPanel item in radDataEntry1.PanelContainer.Controls)
{
    foreach (RadControl control in item.Controls)
    {
        if (control is RadLabel)
        {
            control.ForeColor = ColorTranslator.FromHtml("#e83737");
        }
    }
}

````
````VB.NET
For Each item As RadPanel In radDataEntry1.PanelContainer.Controls
    For Each control As RadControl In item.Controls
        If TypeOf control Is RadLabel Then
            control.ForeColor = ColorTranslator.FromHtml("#e83737")
        End If
    Next control
Next item

````
 

{{endregion}}

>caption Fig3. Set Labels ForeColor.

![WinForms RadDataEntry Fig Set Labels ForeColor](images/dataentry-customizing-appearance003.png)  

## Changing Validation Panel BackColor

The following code snippets represent how to change the BackColor property of Validation Panel:

### Change Back Color

{{source=..\SamplesCS\DataEntryAndBindingNavigator\RadDataEntryHowTo.cs region=ChangeBackColor}} 
{{source=..\SamplesVB\DataEntryAndBindingNavigator\RadDataEntryHowTo.vb region=ChangeBackColor}}
````C#
this.radDataEntry1.ValidationPanel.PanelElement.Fill.BackColor = Color.PapayaWhip;

````
````VB.NET
Me.radDataEntry1.ValidationPanel.PanelElement.Fill.BackColor = Color.PapayaWhip

```` 

{{endregion}}

>caption Fig4. Set Validaton Panel BackColor.

![WinForms RadDataEntry Fig4 Set Validaton Panel BackColor](images/dataentry-customizing-appearance004.png)  

# See Also

 * [Structure]({%slug winforms/dataentry/control-element-structure%})
 * [Getting Started]({%slug winforms/dataentry/getting-started%})
 * [Properties, events and attributes]({%slug winforms/dataentry/properties,-events-and-attributes%})
 * [Themes]({%slug winforms/dataentry/themes%})
 * [Change the editor to RadDropDownList]({%slug winforms/dataentry/how-to/change-the-editor-to-a-bound-raddropdownlist%})
