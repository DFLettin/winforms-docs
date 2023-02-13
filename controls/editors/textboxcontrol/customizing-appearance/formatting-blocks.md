---
title: Formatting Blocks
page_title: Formatting Blocks - RadTextBoxControl
description: Formatting Blocks
slug: winforms/editors/textboxcontrol/formatting-blocks
tags: formatting,blocks
published: True
position: 2
previous_url: editors-textboxcontrol-formatting-blocks, editors/textboxcontrol/formatting-blocks
---

# Formatting Blocks

The RadTextBoxControl allow appearance customization of each instance of __ITextBlock__. This can be easily achieved by subscribing to the __FormattingTextBlock__ event: 

#### Subscribing to TextBlockFormatting event

{{source=..\SamplesCS\Editors\TextBoxControl.cs region=Formatting1}} 
{{source=..\SamplesVB\Editors\TextBoxControl.vb region=Formatting1}}
````C#
            
this.radTextBoxControl1.TextBlockFormatting += this.OnTextBlockFormatting;
this.radTextBoxControl1.Text = "This is important text.";

````
````VB.NET
AddHandler Me.RadTextBoxControl1.TextBlockFormatting, AddressOf Me.OnTextBlockFormatting
Me.RadTextBoxControl1.Text = "This is important text."

````

{{endregion}} 

#### The TextBlockFormatting event handler

{{source=..\SamplesCS\Editors\TextBoxControl.cs region=formatting2}} 
{{source=..\SamplesVB\Editors\TextBoxControl.vb region=formatting2}} 

````C#
        
private void OnTextBlockFormatting(object sender, Telerik.WinControls.UI.TextBlockFormattingEventArgs e)
{
    TextBlockElement textBlock = e.TextBlock as TextBlockElement;
    if (textBlock != null && e.TextBlock.Text == "important")
    {
        textBlock.ForeColor = Color.Red;
    }
}

````
````VB.NET
Private Sub OnTextBlockFormatting(sender As Object, e As Telerik.WinControls.UI.TextBlockFormattingEventArgs)
    Dim textBlock As TextBlockElement = TryCast(e.TextBlock, TextBlockElement)
    If textBlock IsNot Nothing AndAlso e.TextBlock.Text = "important" Then
        textBlock.ForeColor = Color.Red
    End If
End Sub

````

{{endregion}} 


![WinForms RadTextBoxControl Formatting Blocks](images/editors-textboxcontrol-formatting-blocks001.png)

>note Notice that the event occurs when the text blocks are repositioned. This happens in different cases: editing, control resizing and etc. Hence, you should subscribe to the event before initializing the __Text__ property.

# See Also

* [Themes]({%slug winforms/editors/radtextboxcontrol/themes%})
* [Customizing Appearance]({%slug winforms/editors/textboxcontrol/customizing-appearance%})
