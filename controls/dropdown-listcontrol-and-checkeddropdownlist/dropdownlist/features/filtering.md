---
title: Filtering
page_title: Filtering - WinForms DropDownList Control
description: WinForms DropDownList offers filtering functionality for its items.
slug: winforms/dropdown-listcontrol-and-checkeddropdownlist/dropdownlist/filtering
tags: filtering
published: True
position: 11
previous_url: dropdown-and-listcontrol-dropdownlist-filtering
---

# Filtering

__RadDropDownList__ supports filtering of its items. In order to apply a filter, you should set the __Filter__ property of __RadDropDownList__ to a predicate that will be called for every data item in order to determine if the item will be visible.

#### Filter 

{{source=..\SamplesCS\DropDownListControl\DropDownList\DropDownList1.cs region=Filter}} 
{{source=..\SamplesVB\DropDownListControl\DropDownList\DropDownList1.vb region=Filter}}
````C#
            
this.radDropDownList1.Filter = FilterItem;

````
````VB.NET
Me.radDropDownList1.Filter = AddressOf FilterItem

```` 

{{endregion}} 

#### Filtering predicate 

{{source=..\SamplesCS\DropDownListControl\DropDownList\DropDownList1.cs region=FilteringPredicate}} 
{{source=..\SamplesVB\DropDownListControl\DropDownList\DropDownList1.vb region=FilteringPredicate}}
````C#
    
private bool FilterItem(RadListDataItem item)
{
    if (item.Text.StartsWith("L"))
    {
        return true;
    }
    return false;
}

````
````VB.NET
Private Function FilterItem(item As RadListDataItem) As Boolean
    If item.Text.StartsWith("L") Then
        Return True
    End If
    
    Return False
End Function

```` 

{{endregion}} 
 

If you apply the above filter to a __RadDropDownList__ that is bound to the Northwind.__Customers__ table you will obtain the following result:
        
>caption Figure 1: Filter

![WinForms RadDropDownList Filter](images/dropdown-and-listcontrol-dropdownlist-filtering001.png)

Another option to filter the items is to specify the __FilterExpression__ property.

#### FilteringExpression 

{{source=..\SamplesCS\DropDownListControl\DropDownList\DropDownList1.cs region=FilteringExpression}} 
{{source=..\SamplesVB\DropDownListControl\DropDownList\DropDownList1.vb region=FilteringExpression}}
````C#
this.radDropDownList1.FilterExpression = "Country LIKE 'Argentina'";

````
````VB.NET
Me.radDropDownList1.FilterExpression = "Country LIKE 'Argentina'"

```` 

{{endregion}} 
 
>caption Figure 2: FilteringExpression

![WinForms RadDropDownList FilteringExpression](images/dropdown-and-listcontrol-dropdownlist-filtering002.png)

>note The __IsFilterActive__ property gets a value indicating whether there is a __Filter__ or __FilterExpression__ set.
>

