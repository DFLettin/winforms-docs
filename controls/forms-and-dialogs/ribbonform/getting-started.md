---
title: Getting Started
page_title: Getting Started - WinForms RibbonForm
description: WinForms RibbonForm control is designed to host a RadRibbonBar control and mimic the Microsoft Office 2007 UI form style.
slug: winforms/forms-and-dialogs/ribbonform/getting-started
tags: getting,started
published: True
position: 2
previous_url: forms-and-dialogs-ribbonform-getting-started
---

# Getting Started

There are three ways in which you can use the __RadRibbonForm__ control:

1. Change the base class of a standard Windows Form to __Telerik.WinControls.UI.RadRibbonForm__

1. Drop a __RadRibbonBar__ control on a __RadForm__ control
          
1. Add a new __RadRibbonForm__ item to your project by right-clicking on the Project’s node in the Solution Explorer and selecting the "Add" option from the context menu.
          

##  Drag-and-Drop a RadRibbonBar Control on a RadForm

When you add a __RadRibbonBar__ control on a __RadForm__ the Visual Studio Designer pops up a dialog which asks you whether you would like to switch the form’s behavior to __RadRibbonFormBehavior:__

![WinForms RadRibbonForm forms-and-dialogs-ribbonform-getting-started 001](images/forms-and-dialogs-ribbonform-getting-started001.png)


After you choose to replace the form's default behavior with a __RadRibbonFormBehavior__, the __RadForm__ is transformed to a __RadRibbonForm__:

![WinForms RadRibbonForm forms-and-dialogs-ribbonform-getting-started 002](images/forms-and-dialogs-ribbonform-getting-started002.png)

Switching to __RadRibbonFormBehavior__ does not change the base class to __RadRibbonForm__ but enables the __RadRibbonForm__ functionality on the __RadForm__ control.


