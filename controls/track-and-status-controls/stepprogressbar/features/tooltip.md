---
title: ToolTip
page_title: ToolTip - WinForms StepProgressBar Control
description: WinForms StepProgressBar 
slug: stepprogressbar-features-tooltip
tags: stepprogressbar
published: True
position: 0 
CTAControlName: StepProgressBar
---

# Tooltip

There are two ways to assign tooltips to step indicators in __RadStepProgressBar__, namely setting the ToolTipText and AutoToolTip properties of the StepIndicator of each step, or as in most of the RadControls by using the ToolTipTextNeeded event. To assign a tooltip text, you can use the __ToolTipTextNeeded__ event of the __RadStepProgressBar__ control.

## Setting ToolTipText to StepIndicators

The code snippet below demonstrates how you can assign a tooltip to a step indicator.

{{source=..\SamplesCS\TrackAndStatus\StepProgressBar\StepProgressBarGettingStarted.cs region=StepIndicator_ToolTipText}} 
{{source=..\SamplesVB\TrackAndStatus\StepProgressBar\StepProgressBarGettingStarted.vb region=StepIndicator_ToolTipText}}

````C#
private void StepIndicator_ToolTipText()
{
    var stepProgressBar = new RadStepProgressBar();
    var item1 = new StepProgressItem() { Progress = 100, FirstHeader = "Step 1" };
    var item2 = new StepProgressItem() { Progress = 100, FirstHeader = "Step 2" };
    var item3 = new StepProgressItem() { Progress = 80, FirstHeader = "Step 3" };
    var item4 = new StepProgressItem() { Progress = 0, FirstHeader = "Step 4" };
    var item5 = new StepProgressItem() { Progress = 0, FirstHeader = "Step 5" };
    item1.StepIndicator.AutoToolTip = true;
    item1.StepIndicator.ToolTipText = item1.FirstHeader;
    item2.StepIndicator.AutoToolTip = true;
    item2.StepIndicator.ToolTipText = item2.FirstHeader;
    item3.StepIndicator.AutoToolTip = true;
    item3.StepIndicator.ToolTipText = item3.FirstHeader;
    item4.StepIndicator.AutoToolTip = true;
    item4.StepIndicator.ToolTipText = item4.FirstHeader;
    item5.StepIndicator.AutoToolTip = true;
    item5.StepIndicator.ToolTipText = item5.FirstHeader;
    stepProgressBar.Steps.Add(item1);
    stepProgressBar.Steps.Add(item2);
    stepProgressBar.Steps.Add(item3);       
    stepProgressBar.Steps.Add(item4);       
    stepProgressBar.Steps.Add(item5);       
    this.Controls.Add(stepProgressBar);
}

````
````VB.NET
Private Sub StepIndicator_ToolTipText()
	Dim stepProgressBar = New RadStepProgressBar()
	Dim item1 = New StepProgressItem() With {
		.Progress = 100,
		.FirstHeader = "Step 1"
	}
	Dim item2 = New StepProgressItem() With {
		.Progress = 100,
		.FirstHeader = "Step 2"
	}
	Dim item3 = New StepProgressItem() With {
		.Progress = 80,
		.FirstHeader = "Step 3"
	}
	Dim item4 = New StepProgressItem() With {
		.Progress = 0,
		.FirstHeader = "Step 4"
	}
	Dim item5 = New StepProgressItem() With {
		.Progress = 0,
		.FirstHeader = "Step 5"
	}
	item1.StepIndicator.AutoToolTip = True
	item1.StepIndicator.ToolTipText = item1.FirstHeader
	item2.StepIndicator.AutoToolTip = True
	item2.StepIndicator.ToolTipText = item2.FirstHeader
	item3.StepIndicator.AutoToolTip = True
	item3.StepIndicator.ToolTipText = item3.FirstHeader
	item4.StepIndicator.AutoToolTip = True
	item4.StepIndicator.ToolTipText = item4.FirstHeader
	item5.StepIndicator.AutoToolTip = True
	item5.StepIndicator.ToolTipText = item5.FirstHeader
	stepProgressBar.Steps.Add(item1)
	stepProgressBar.Steps.Add(item2)
	stepProgressBar.Steps.Add(item3)
	stepProgressBar.Steps.Add(item4)
	stepProgressBar.Steps.Add(item5)
	Me.Controls.Add(stepProgressBar)
End Sub

````

{{endregion}}

![stepprogressbar-layout 001](images/stepprogressbar-features-tooltip001.png)

## Setting Tooltips in the ToolTipTextNeeded Event

The code snippet below demonstrates how you can use the ToolTipTextNeeded event handler to set the ToolTipText of step indicators.

{{source=..\SamplesCS\TrackAndStatus\StepProgressBar\StepProgressBarGettingStarted.cs region=ToolTipTextNeeded}} 
{{source=..\SamplesVB\TrackAndStatus\StepProgressBar\StepProgressBarGettingStarted.vb region=ToolTipTextNeeded}}

````C#
private void ToolTipTextNeeded()
{
    var stepProgressBar = new RadStepProgressBar();
    stepProgressBar.ToolTipTextNeeded += StepProgressBar_ToolTipTextNeeded;
    var item1 = new StepProgressItem() { Progress = 100, FirstHeader = "Step 1",  };
    var item2 = new StepProgressItem() { Progress = 100, FirstHeader = "Step 2" };
    var item3 = new StepProgressItem() { Progress = 80, FirstHeader = "Step 3" };
    var item4 = new StepProgressItem() { Progress = 0, FirstHeader = "Step 4" };
    var item5 = new StepProgressItem() { Progress = 0, FirstHeader = "Step 5" };
    stepProgressBar.Steps.Add(item1);
    stepProgressBar.Steps.Add(item2);
    stepProgressBar.Steps.Add(item3);       
    stepProgressBar.Steps.Add(item4);       
    stepProgressBar.Steps.Add(item5);       
    this.Controls.Add(stepProgressBar);
}
private void StepProgressBar_ToolTipTextNeeded(object sender, ToolTipTextNeededEventArgs e)
{    
    var indicator = sender as StepItemIndicatorElement;
    if (indicator != null)
    {
        e.ToolTipText = (indicator.Parent as StepProgressItem).FirstHeader;
    }
}


````
````VB.NET
Private Sub ToolTipTextNeeded()
	Dim stepProgressBar = New RadStepProgressBar()
	stepProgressBar.ToolTipTextNeeded += AddressOf StepProgressBar_ToolTipTextNeeded
	Dim item1 = New StepProgressItem() With {
		.Progress = 100,
		.FirstHeader = "Step 1"
	}
	Dim item2 = New StepProgressItem() With {
		.Progress = 100,
		.FirstHeader = "Step 2"
	}
	Dim item3 = New StepProgressItem() With {
		.Progress = 80,
		.FirstHeader = "Step 3"
	}
	Dim item4 = New StepProgressItem() With {
		.Progress = 0,
		.FirstHeader = "Step 4"
	}
	Dim item5 = New StepProgressItem() With {
		.Progress = 0,
		.FirstHeader = "Step 5"
	}
	stepProgressBar.Steps.Add(item1)
	stepProgressBar.Steps.Add(item2)
	stepProgressBar.Steps.Add(item3)
	stepProgressBar.Steps.Add(item4)
	stepProgressBar.Steps.Add(item5)
	Me.Controls.Add(stepProgressBar)
End Sub

Private Sub StepProgressBar_ToolTipTextNeeded(ByVal sender As Object, ByVal e As ToolTipTextNeededEventArgs)
	Dim indicator = TryCast(sender, StepItemIndicatorElement)

	If indicator IsNot Nothing Then
		e.ToolTipText = (TryCast(indicator.Parent, StepProgressItem)).FirstHeader
	End If
End Sub

````

{{endregion}}

![stepprogressbar-layout 001](images/stepprogressbar-features-tooltip002.png)

# See Also

* [Getting Started]({%slug stepprogressbar-getting-started%})
* [Design Time]({%slug stepprogressbar-design-time%}) 
* [Structure]({%slug stepprogressbar-structure%}) 
* [How to Add Callout for StepProgressBar]({%slug callout-for-stepprogresbar%})
 
        
