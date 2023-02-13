---
title: HTML-like Text Formatting
page_title: HTML-like Text Formatting - WinForms GroupBox Control
description: WinForms Label supports HTML-like Text Formatting which is applied on the text primitive allowing the text to be styled with standard HTML tags.
slug: winforms/panels-and-labels/label/html-like-text-formatting
tags: html-like,text,formatting
published: True
position: 5
previous_url: panels-and-labels-label-html-like-text-formatting
---

# HTML-like Text Formatting

## Introduction

Telerik UI for WinForms provide an advanced text styling mechanism, which can be applied to all Telerik products, because it enhances the smallest element in the Telerik Presentation Framework - the text primitive. The new rich text formatting mechanism uses plain HTML tags to display formatted text such as font style, font color, font size options and simple layouts. To turn on Html-like formatting the text must start with an __\<html\>__ tag; use __\<size=[+|-]value\>__ to set font size use, and __\<br\>__ to create new line feed. To bold, underline and italic text, use the corresponding opening and closing tags. Font family is set through __\<font=Family\>.__

## Supported Tags 


|  __Tag__  |  __End Tag__  |  __Description__  |
| ------ | ------ | ------ |
| __\<font\>__ |N/A|Specifies the font family|
| __\<color\>__ |N/A|Specifies the text color.|
| __\<size\>__ |N/A|Specifies the font size.|
| __\<b\>__ | __\</b\>__ |Defines bold text.|
| __\<i\>__ | __\</i\>__ |Defines italic text.|
| __\<u\>__ | __\</u\>__ |Defines underlined text.|
| __\<br\>__ |N/A|Single line break.|
| __\<a\>__ | __\</a\>__ |Defines a hyperlink|

## Example

The following code snippet will produce the result shown in the screen-shot below:

#### Set HTML-like text formatting to RadLabel text

{{source=..\SamplesCS\PanelsAndLabels\Label\LabelHtmlLikeTextFormatting.cs region=setHtmlText}} 
{{source=..\SamplesVB\PanelsAndLabels\Label\LabelHtmlLikeTextFormatting.vb region=setHtmlText}} 

````C#
this.radLabel1.Text = "<html><size=12>This is RadLabel <br><b><font=Arial>Arial, Bold</b><br><i><color= Red><font=Times New Roman>Times, Italic <u>Underline</u><br><size=9>Size = 9<br><color= 0, 0, 255>Sample Text";

````
````VB.NET
Me.RadLabel1.Text = "<html><size=12>This is RadLabel <br><b><font=Arial>Arial, Bold</b><br><i><color= Red><font=Times New Roman>Times, Italic <u>Underline</u><br><size=9>Size = 9<br><color= 0, 0, 255>Sample Text"

````

{{endregion}} 

>caption Figure 1: HTML-like Text
![WinForms RadLabel HTML-like Text](images/panels-and-labels-label-html-like-text-formatting001.png)

# See Also

* [Getting Started]({%slug winforms/panels-and-labels/label/getting-started%})
* [Themes]({%slug winforms/panels-and-labels/label/customizing-appearance/themes%})
