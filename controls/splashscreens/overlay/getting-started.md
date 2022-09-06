---
title: Getting Started
page_title: Getting Started 
description: Check our &quot;Getting Started&quot; documentation article for the Overlay Screen {{ site.framework_name }} control.
slug: overlay-getting-started
tags: overlay,show,close
published: True
position: 1
CTAControlName: Overlay
---

# Getting Started

This tutorial will walk you through how you can use __Overlay Screen__. 

![overlay-overview 001](images/overlay-overview001.png)

The overlay form can be activated throught the __RadOverlayManager.Show()__ method. This method accept parameter of type __Control__. When the Show() method is called, the Overlay from will take the size of the control which is passed as a parameter and it will appear on top of that control. This will make the control beneath the screen inactive. In the center rotating dots will notify the user that currently long runnuing operation is executing. After this operation finish, we can close the overlay screen by calling the __RadOverlayManager.Close()__ static method. 

## Show Overlay

{{source=..\SamplesCS\SplashScreens\Overlay\OverlaySettings.cs region=GettingStarted_Show}} 
{{source=..\SamplesVB\SplashScreens\Overlay\OverlaySettings.vb region=GettingStarted_Show}} 

````C#

RadOverlayManager.Show(this.radGridView1);
	

````
````VB.NET

RadOverlayManager.Show(this.radGridView1)


````

{{endregion}}

## Close Overlay

{{source=..\SamplesCS\SplashScreens\Overlay\OverlaySettings.cs region=GettingStarted_Close}} 
{{source=..\SamplesVB\SplashScreens\Overlay\OverlaySettings.vb region=GettingStarted_Close}} 

````C#

RadOverlayManager.Close();
	

````
````VB.NET

RadOverlayManager.Close()


````

{{endregion}}

# See Also

* [Overview]({%slug overlay-overview%})
 
        