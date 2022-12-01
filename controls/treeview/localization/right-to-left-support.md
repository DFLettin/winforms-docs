---
title: Right-to-left support
page_title: Right-to-left support - RadTreeView
description: Right-to-left support
slug: winforms/treeview/localization/right-to-left-support
tags: right-to-left,support
published: True
position: 1
previous_url: treeview-localization-rtl
---

# Right-to-left support


You can present the content of your tree view instance in a right-to-left direction by setting the __RightToLeft__ property to *Yes*:

{{source=..\SamplesCS\TreeView\TreeLocalization.cs region=rtl}} 
{{source=..\SamplesVB\TreeView\TreeLocalization.vb region=rtl}} 

````C#
this.radTreeView1.RightToLeft = System.Windows.Forms.RightToLeft.Yes;

````
````VB.NET
Me.RadTreeView1.RightToLeft = Windows.Forms.RightToLeft.Yes

````

{{endregion}} 

![WinForms RadTreeView treeview-localization-rtl 001](images/treeview-localization-rtl001.png)

# See Also
* [Localization]({%slug winforms/treeview/localization/localization%})

