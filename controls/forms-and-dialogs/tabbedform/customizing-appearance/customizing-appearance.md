---
title: Customizing Appearance
page_title: Customizing Appearance - RadTabbedForm
description:  RadTabbedForm allows to display tab items directly in the title bar  
slug: radtabbedform-customizig-appearance
tags: radtabbedform
published: True
position: 0
---

# Design Time

You can access and modify the style for the different elements in the editable area of __RadTabbedForm__ by using the Element hierarchy editor.

![WinForms RadTabbedForm Design Time](images/customizing-appearance001.png)


# Programmatically

The following example demonstrates how you can access the visual item of the tab and change its back color. 

### Access the tab visual element

{{source=..\SamplesCS\Forms and Dialogs\TabbedFormCode.cs region=Appearance}} 
{{source=..\SamplesVB\Forms and Dialogs\TabbedFormCode.vb region=Appearance}}
````C#
this.TabbedFormControl.Tabs[0].Item.BackColor = Color.Red;

````
````VB.NET
Me.TabbedFormControl.Tabs(0).Item.BackColor = Color.Red

```` 

{{endregion}}  


# See Also

* [Themes]({%slug radtabbedform-themes%})
