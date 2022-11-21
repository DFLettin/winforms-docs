---
title: Customizing ShapedForm
page_title: Customizing ShapedForm - UI for WinForms Documentation
description: The ShapedForm control allows you to design and display a Windows form with any conceivable shape.
slug: winforms/forms-and-dialogs/shapedform/customizing-shapedform
tags: customizing,shapedform
published: True
position: 2
previous_url: forms-and-dialogs-shapedform-customizing-shapedform
---

# Customizing ShapedForm

Almost all properties of _ShapedForm__ are the same as a standard Windows Form. You can use your knowledge of the __Form__ class to customize your __ShapedForm__. There are two major exceptions:

* ShapedForm does not have a title bar, and so does not have maximize, minimize, or close buttons. To get maximize, minimize and close functionality, add a [RadTitleBar control]({%slug winforms/forms-and-dialogs/radtitlebar%}) to your __ShapedForm__.
          
* __ShapedForm__ adds a __Shape__ property that can be used to choose preset shapes or allow you to create a new custom shape in the __Shape Editor__. 

* Use __ThemeName__ property to set the theme name. 

#### Setting a theme to a ShapedForm 

{{source=..\SamplesCS\Forms and Dialogs\ShapedForm1.cs region=ThemeName}} 
{{source=..\SamplesVB\Forms and Dialogs\ShapedForm1.vb region=ThemeName}} 

````C#
this.ThemeName = "Breeze";

````
````VB.NET
Me.ThemeName = "Breeze"

````

{{endregion}} 



