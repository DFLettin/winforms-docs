---
title: Formatting Items
page_title: Formatting Items - RadCheckedDropDownList
description: RadCheckedDropDownList combines RadDropDownList and RadAutoCompleteBox in order to provide functionality to check items in the drop down area and tokenize them in the text area. 
slug: winforms/dropdown-listcontrol-and-checkeddropdownlist/checkeddropdownlist/customization
tags: customization
published: True
position: 2
previous_url: dropdown-and-listcontrol-checkeddropdownlist-customization
---

# Formatting Items
 
Formatting __RadCheckedDropDownList__ is easy and can be separated in two parts:
      

## Formatting the editable area

In order to customize the editable area, you must subscribe to the __TextBlockFormatting__ event and modify the properties of the __TokenizedTextBlockElement__:

#### Subscribe to TextBlockFormatting 

{{source=..\SamplesCS\DropDownListControl\CheckedDropDownList\Customization1.cs region=TextBlockFormattingSubscribe}} 
{{source=..\SamplesVB\DropDownListControl\CheckedDropDownList\Customization1.vb region=TextBlockFormattingSubscribe}} 

````C#
this.radCheckedDropDownList1.TextBlockFormatting += radCheckedDropDownList1_TextBlockFormatting;

````
````VB.NET
AddHandler Me.RadCheckedDropDownList1.TextBlockFormatting, AddressOf radCheckedDropDownList1_TextBlockFormatting

````

{{endregion}} 


#### Modify properties 

{{source=..\SamplesCS\DropDownListControl\CheckedDropDownList\Customization1.cs region=TextBlockFormattingHandler}} 
{{source=..\SamplesVB\DropDownListControl\CheckedDropDownList\Customization1.vb region=TextBlockFormattingHandler}} 

````C#
void radCheckedDropDownList1_TextBlockFormatting(object sender, TextBlockFormattingEventArgs e)
{
    TokenizedTextBlockElement token = e.TextBlock as TokenizedTextBlockElement;
    if (token != null)
    {
        token.ForeColor = Color.DarkBlue;
        token.DrawFill = false;
        token.BorderColor = Color.DarkRed;
        token.BorderWidth = 1.3f;
        token.DrawBorder = true;
        token.BorderGradientStyle = GradientStyles.Solid;
    }
}

````
````VB.NET
Private Sub radCheckedDropDownList1_TextBlockFormatting(sender As Object, e As TextBlockFormattingEventArgs)
    Dim token As TokenizedTextBlockElement = TryCast(e.TextBlock, TokenizedTextBlockElement)
    If token IsNot Nothing Then
        token.ForeColor = Color.DarkBlue
        token.DrawFill = False
        token.BorderColor = Color.DarkRed
        token.BorderWidth = 1.3F
        token.DrawBorder = True
        token.BorderGradientStyle = GradientStyles.Solid
    End If
End Sub

````

{{endregion}} 

>caption Figure 1: Customizing tokens

![WinForms RadCheckedDropDownList Customizing tokens](images/dropdown-and-listcontrol-checkeddropdownlist-customization001.png)

## Formatting the drop down items

Customizing the drop down items is similar. Subscribe to the __VisualListItemFormatting__ event:

#### Subscribe to VisualListItemFormatting 

{{source=..\SamplesCS\DropDownListControl\CheckedDropDownList\Customization1.cs region=VisualListItemFormattingSubscribe}} 
{{source=..\SamplesVB\DropDownListControl\CheckedDropDownList\Customization1.vb region=VisualListItemFormattingSubscribe}} 

````C#
this.radCheckedDropDownList1.VisualListItemFormatting += radCheckedDropDownList1_VisualListItemFormatting;

````
````VB.NET
AddHandler Me.RadCheckedDropDownList1.VisualListItemFormatting, AddressOf radCheckedDropDownList1_VisualListItemFormatting

````

{{endregion}} 


#### Modify properties 

{{source=..\SamplesCS\DropDownListControl\CheckedDropDownList\Customization1.cs region=VisualListItemFormattingHandler}} 
{{source=..\SamplesVB\DropDownListControl\CheckedDropDownList\Customization1.vb region=VisualListItemFormattingHandler}} 

````C#
void radCheckedDropDownList1_VisualListItemFormatting(object sender, VisualItemFormattingEventArgs args)
{
    bool itemChecked = ((RadCheckedListDataItem)args.VisualItem.Data).Checked;
    if (itemChecked)
    {
        args.VisualItem.ForeColor = Color.Green;
    }
    else
    {
        args.VisualItem.ForeColor = Color.Red;
    }
}

````
````VB.NET
Private Sub radCheckedDropDownList1_VisualListItemFormatting(sender As Object, args As VisualItemFormattingEventArgs)
    Dim itemChecked As Boolean = DirectCast(args.VisualItem.Data, RadCheckedListDataItem).Checked
    If itemChecked Then
        args.VisualItem.ForeColor = Color.Green
    Else
        args.VisualItem.ForeColor = Color.Red
    End If
End Sub

````

{{endregion}} 

>caption Figure 2: Customizing dropdown items

![WinForms RadCheckedDropDownList Customizing dropdown items](images/dropdown-and-listcontrol-checkeddropdownlist-customization002.png)
