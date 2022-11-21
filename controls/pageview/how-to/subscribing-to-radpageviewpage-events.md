---
title: Subscribing to RadPageViewPage Events
page_title: Subscribing to RadPageViewPage Events - RadPageView
description: RadPageView is yet another great addition to the Telerik UI for WinForms suite. As the name implies, this control layouts pages of subcontrols in different views.
slug: winforms/pageview/how-to/subscribing-to-radpageviewpage-events
tags: subscribing,to,radpageviewpage,events
published: True
position: 2
previous_url: pageview-how-to-subscribing-to-radpageviewpage-events
---

# Subscribing to RadPageViewPage Events

Subscribing to **RadPageViewPage**'s event is no different then subscribing to any other event. Following is an example code snippet:

{{source=..\SamplesCS\PageView\HowTo.cs region=subscribeToEvents}} 
{{source=..\SamplesVB\PageView\HowTo.vb region=subscribeToEvents}}

````C#
            
radPageViewPage1.MouseClick += new MouseEventHandler(radPageViewPage1_MouseClick);
radPageViewPage1.MouseDoubleClick += new MouseEventHandler(radPageViewPage1_MouseDoubleClick);

````
````VB.NET
AddHandler radPageViewPage1.MouseClick, AddressOf radPageViewPage1_MouseClick
AddHandler radPageViewPage1.MouseDoubleClick, AddressOf radPageViewPage1_MouseDoubleClick

````

{{endregion}} 

{{source=..\SamplesCS\PageView\HowTo.cs region=eventHandlers}} 
{{source=..\SamplesVB\PageView\HowTo.vb region=eventHandlers}} 

````C#
 
void radPageViewPage1_MouseDoubleClick(object sender, MouseEventArgs e)
{
    //do something
}
void radPageViewPage1_MouseClick(object sender, MouseEventArgs e)
{
    //do something
}

````
````VB.NET
Private Sub radPageViewPage1_MouseDoubleClick(ByVal sender As Object, ByVal e As MouseEventArgs)
    'do something
End Sub
Private Sub radPageViewPage1_MouseClick(ByVal sender As Object, ByVal e As MouseEventArgs)
    'do something
End Sub

````

{{endregion}} 

# See Also

* [Getting Started]({%slug winforms/pageview/getting-started%})	
* [Design Time]({%slug winforms/pageview/design-time%})	



