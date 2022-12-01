---
title: Working with Labels
page_title: Working with labels - WinForms RadialGauge Control
description: RadialGaugeLabels class represents the scale labels displayed next to the ticks.
slug: winforms/gauges/radialgauge/understanding-gauge-elements/working-with-labels
tags: working,with,labels
published: True
position: 2
previous_url: radialgauge-understanding-gauge-elements-working-with-labels
---

# Working with Labels

__RadialGaugeLabels__ class represents the scale labels displayed next to the ticks.

>caption Figure 1: Label
![WinForms RadGauges Label](images/radialgauge-understanding-gauge-elements-working-with-labels001.png)

The following properties allow you to modify the labels' look:

* __LabelFontSize__ - specifies the font size. On the following picture the black labels font size is *8* but the red labels font size is *5*.

>caption Figure 2: Font
![WinForms RadGauges Font](images/radialgauge-understanding-gauge-elements-working-with-labels002.png)

* __LabelStartVisibleRange__ - specifies the start value from which the labels are displayed. On the following picture the black labels starts from value *40* but the red labels start from value *140*.

>caption Figure 3: Start Visible Range
![WinForms RadGauges Start Visible Range](images/radialgauge-understanding-gauge-elements-working-with-labels003.png)

* __LabelEndVisibleRange__ - specifies the end value to which the labels are displayed. On the following picture the black labels ends with value *60* but the red labels ends with value *140*.

>caption Figure 4: End Visible Range
![WinForms RadGauges End Visible Range](images/radialgauge-understanding-gauge-elements-working-with-labels004.png)

* __LabelRadiusPercentage__ - controls how far according to the gauge's arc the labels are rendered. If the __LabelRadiusPercentage__ is greater than *100*, the labels will be displayed outside the gauge. The smaller the value is, the closer to the center the label gets.

>caption Figure 5: Radius Percentage
![WinForms RadGauges Radius Percentage](images/radialgauge-understanding-gauge-elements-working-with-labels005.png)

* __LabelFormat__ - specifies the format of the label's value. You can display labels with one digit after the decimal place, e.g. refer to the black labels below. The red ones show two digits after the decimal place.

>caption Figure 6: Labels Format
![WinForms RadGauges Labels Format](images/radialgauge-understanding-gauge-elements-working-with-labels006.png)

* __LabelsCount__ - controls how many labels will be displayed next ticks for the specified range.

>note  __RadRadialGauge__ always displays one additional label to the __LabelsCount__ in order to distribute the labels correctly on the arc.
>

# See Also

* [Structure]({%slug winforms/gauges/radialgauge/structure%})
* [Design Time]({%slug winforms/gauges/radialgauge/design-time%})
* [Properties and Events]({%slug winforms/gauges/radialgauge/properties-and-events%})
