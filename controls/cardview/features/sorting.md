---
title: Sorting
page_title: Sorting - UI for WinForms Documentation
description: Sorting is possible in two ways either programmatically by adding the appropriate SortDescriptor to the SortDescriptors collection of RadCardView.
slug: winforms/cardview/features/sorting
tags: sorting
published: True
position: 2
---

# Sorting

Enabling sorting is done by setting __EnableSorting__ property to *true*. You should add appropriate  an __SortDescriptor__ to the __SortDescriptors__ collection as well.

#### Enable Column Sorting

{{source=..\SamplesCS\CardView\CardViewFeatures.cs region=EnableSorting}} 
{{source=..\SamplesVB\CardView\CardViewFeatures.vb region=EnableSorting}} 

````C#
this.radCardView1.EnableSorting = true;

````
````VB.NET
Me.RadCardView1.EnableSorting = True

````

{{endregion}} 

The following code demonstrates how to add __SortDescriptor__ to __RadCardView__:

#### Adding SortDescriptors

{{source=..\SamplesCS\CardView\CardViewFeatures.cs region=SortDescriptor}} 
{{source=..\SamplesVB\CardView\CardViewFeatures.vb region=SortDescriptor}} 

````C#
SortDescriptor sortDescriptor = new SortDescriptor("Id", ListSortDirection.Ascending);
this.radCardView1.SortDescriptors.Add(sortDescriptor);

````
````VB.NET
Dim sortDescriptor As New SortDescriptor("Id", ListSortDirection.Ascending)
Me.RadCardView1.SortDescriptors.Add(sortDescriptor)

````

{{endregion}}
