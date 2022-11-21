---
title: Overview
page_title: Backstage View - RadRibbonBar
description: Backstage View is the Office 2010 replacement of the Application Menu.
slug: winforms/ribbonbar/backstage-view/overview
tags: overview
published: True
position: 0
previous_url: ribbonbar-backstage-view-overview
---

# BackStage View

Backstage View is the Office 2010 replacement of the Application Menu. It is a menu that covers the whole window area and contains buttons and tabs. Each tab have a content area, which can be populated with any type of Controls. To enable the Backstage View in RadRibbonBar change the __ApplicationMenuStyle__ property to *BackstageView*.

#### Enabling Backstage view

{{source=..\SamplesCS\RibbonBar\BackstageView\RibbonBackstageView.cs region=ApplicationMenuStyle}} 
{{source=..\SamplesVB\RibbonBar\BackstageView\RibbonBackstageView.vb region=ApplicationMenuStyle}} 

````C#
radRibbonBar1.ApplicationMenuStyle = Telerik.WinControls.UI.ApplicationMenuStyle.BackstageView;

````
````VB.NET
RadRibbonBar1.ApplicationMenuStyle = Telerik.WinControls.UI.ApplicationMenuStyle.BackstageView

````

{{endregion}} 

![ribbonbar-backstage-view-overview 001](images/ribbonbar-backstage-view-overview001.png)

## See Also

* [Design Time]({%slug winforms/ribbonbar/design-time%})
* [Structure]({%slug winforms/ribbonbar/structure%})
* [Getting Started]({%slug winforms/ribbonbar/getting-started%})
