---
title: RadTextBoxControl vs RadTextBox
page_title: RadTextBoxControl vs RadTextBox - RadTextBoxControl
description: This article show the differences between RadTextBox and RadTextBoxControl. 
slug: winforms/editors/textboxcontrol/radtextboxcontrol-vs-radtextbox
tags: radtextboxcontrol,vs,radtextbox
published: True
position: 1
previous_url: editors-textboxcontrol-radtextboxcontrol-vs-radtextbox
---

# RadTextBoxControl vs RadTextBox
 
This article will demonstrate the difference between [RadTextBox]({%slug winforms/editors/textbox%}) and __RadTextBoxControl__.

The main and most important difference between __RadTextBox__ and __RadTextBoxControl__ is that __RadTextBox__ is a wrapper around the standard .NET TextBox control, while __RadTextBoxControl__ is built entirely on top of [Telerik Presentation Framework]({%slug winforms/telerik-presentation-framework/overview%}). This main difference helps avoid some of the limitations that hosted controls introduce such as unsupported clipping, higher memory usage, slower painting, etc. Follows a comparison table with the different features between these controls.

| RadTextBox | RadTextBoxControl |
| ------ | ------ |
|DefaultText|DefaultText|
|TextChanging|TextChanging|
|Only the borders can be themed|Fully themable|
|IME support|IME support|
|RTL support|-|
|-|[Easy customizations and enhancements]({%slug winforms/editors/textboxcontrol/creating-custom-blocks%})|
|-|[TextBlock formatting and replacement]({%slug winforms/editors/textboxcontrol/formatting-blocks%})|
|-|Localizable context menu|
|-|Supports transparency, image or gradient as background|
|-|Lightweight as it does not host control in it|
|-|Flexible and intuitive API|
|-|Customizible AutoComplete with data binding|


# See Also

* [Caret positioning and selection]({%slug winforms/editors/textboxcontrol/caret-positioning-and-selection%})
* [Creating custom blocks]({%slug winforms/editors/textboxcontrol/creating-custom-blocks%})
* [AutoComplete]({%slug winforms/editors/textboxcontrol/autocomplete%})
* [Structure]({%slug winforms/editors/textboxcontrol/element-structure-and-document-object-model%})
* [Properties and Events]({%slug winforms/editors/textboxcontrol/properties%})
* [Text editing]({%slug winforms/editors/textboxcontrol/text-editing%})
