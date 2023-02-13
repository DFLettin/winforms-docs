---
title: Free Form Date Time Parsing
page_title: Free Form Date Time Parsing - WinForms TimePicker Control
description: With the new MaskType TimePicker tries to parse the input string to valid DateTime object by using very complex logic.
slug: winforms/editors/timepicker/free-form-date-time-parsing
tags: free,form,date,time,parsing
published: True
position: 5
previous_url: editors-timepicker-enable-free-form-date-time-parsing
---

# Free Form Date Time Parsing
 

From Q2 2014 we introduced new MaskType of RadMaskedEditBox that is designed to work with DateTime objects and it is not format restricted as the old one. With the new MaskType RadMaskedEditBox tries to parse the input string to valid DateTime object by using very complex logic.  Read more about this parsing logic [here]({%slug winforms/editors/maskededitbox/parsing-dates%}).
      

The embedded text editor of RadTimePicker is RadMaskedEditBox. So if you want to take the advantages from new DateTime parsing logic the only thing that you should to do is to change the MaskType of embedded editor.
       
{{source=..\SamplesCS\Editors\TimePicker1.cs region=FreeFormDateTimeTimePicker}} 
{{source=..\SamplesVB\Editors\TimePicker1.vb region=FreeFormDateTimeTimePicker}} 

````C#
            
this.radTimePicker1.TimePickerElement.MaskedEditBox.MaskType = MaskType.FreeFormDateTime;

````
````VB.NET
Me.RadTimePicker1.TimePickerElement.MaskedEditBox.MaskType = MaskType.FreeFormDateTime

````

{{endregion}} 
 

## 
