---
title: Getting Started
page_title: Getting Started - WinForms CommandBar Control
description: WinForms CommandBar is a fully theme-able tool strip that provides unprecedented flexibility
slug: winforms/commandbar/getting-started
tags: commandbar
published: True
position: 3 
---

# Getting Started with WinForms CommandBar

You can add __RadCommandBar__ either at design time or at run time:

## Design Time

1. To add a __RadCommandBar__ to your form, drag a __RadCommandBar__ from the toolbox onto the surface of the form designer. In order to set up the __RadCommandBar__ at design time you can refer to the [Design time]({%slug  winforms/commandbar/design-time%}) help article.
2. Select the default __CommandBarStripElement__ and in the *Properties* section of Visual Studio open the __Items__ property.
3. Add the desired items by choosing the item type in the drop down button.
4. Click `F5` to start the application.

## Run Time

To programmatically add a __RadCommandBar__ to a form, create a new instance of a __RadCommandBar__, and add it to the form __Controls__ collection.


#### Adding a RadCommandBar at runtime 

{{source=..\SamplesCS\CommandBar\FloatingStrips.cs region=CreatingControl}} 
{{source=..\SamplesVB\CommandBar\FloatingStrips.vb region=CreatingControl}} 

````C#
            
RadCommandBar radCommandBar = new RadCommandBar();
this.Controls.Add(radCommandBar);
radCommandBar.Dock = DockStyle.Top;
CommandBarRowElement row1 = new CommandBarRowElement();
radCommandBar.Rows.Add(row1);
CommandBarStripElement strip1 = new CommandBarStripElement();
row1.Strips.Add(strip1);
CommandBarButton button1 = new CommandBarButton();
strip1.Items.Add(button1);

````
````VB.NET
Dim radCommandBar As New RadCommandBar()
Me.Controls.Add(radCommandBar)
radCommandBar.Dock = DockStyle.Top
Dim row1 As New CommandBarRowElement()
radCommandBar.Rows.Add(row1)
Dim strip1 As New CommandBarStripElement()
row1.Strips.Add(strip1)
Dim button1 As New CommandBarButton()
strip1.Items.Add(button1)

````

{{endregion}} 

## Telerik UI for WinForms Learning Resources
* [Telerik UI for WinForms CommandBar Component](https://www.telerik.com/products/winforms/commandbar.aspx)
* [Getting Started with Telerik UI for WinForms Components](https://docs.telerik.com/devtools/winforms/getting-started/first-steps)
* [Telerik UI for WinForms Setup](https://docs.telerik.com/devtools/winforms/installation-and-upgrades/installing-on-your-computer)
* [Telerik UI for WinForms Application Modernization](https://docs.telerik.com/devtools/winforms/winforms-converter/overview)
* [Telerik UI for WinForms Visual Studio Templates](https://docs.telerik.com/devtools/winforms/visual-studio-integration/visual-studio-templates)
* [Deploy Telerik UI for WinForms Applications](https://docs.telerik.com/devtools/winforms/deployment-and-distribution/application-deployment)
* [Telerik UI for WinForms Virtual Classroom(Training Courses for Registered Users)](https://learn.telerik.com/learn/course/external/view/elearning/17/telerik-ui-for-winforms)
* [Telerik UI for WinForms License Agreement)](https://www.telerik.com/purchase/license-agreement/winforms-dlw-s)

