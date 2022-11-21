---
title: Iterating the child rows collection of a chosen parent row in hierarchy RadGridView
page_title: Iterating the child rows collection of a chosen parent row in hierarchy RadGridView - RadGridView
description: Iterate the child rows collection of a chosen parent row in hierarchy RadGridView.
slug: winforms/gridview/hierarchical-grid/how-to/iterating-the-child-rows-collection-of-a-chosen-parent-row-in-hierarchy-radgridview
tags: iterating,the,child,rows,collection,of,a,chosen,parent,row,in,hierarchy,radgridview
published: True
position: 2
previous_url: gridview-hirarchical-grid-how-to-iterating-the-child-rows-collection-of-a-chosen-parent-row
---

# Iterating the child rows collection of a chosen parent row in hierarchy RadGridView

In order to iterate all child rows in RadGridView, you need to change the ActiveView of each hierarchy row to each of the available Views. This is needed as the grid will create the child rows for the sibling views (tabs in the detail cell) only after they are requested - when the tab is clicked.

{{source=..\SamplesCS\GridView\HierarchicalGrid\HowTo\HowTo.cs region=iterateChildRows}} 
{{source=..\SamplesVB\GridView\HierarchicalGrid\HowTo\HowTo1.vb region=iterateChildRows}} 

````C#
void IterateRows()
{
    foreach (GridViewRowInfo row in radGridView1.Rows)
    {
        Console.WriteLine(row.Cells[1].Value);
        GridViewHierarchyRowInfo hierarchyRow = row as GridViewHierarchyRowInfo;
        if (hierarchyRow != null)
        {
            IterateChildRows(hierarchyRow);
        }
    }
}
private void IterateChildRows(GridViewHierarchyRowInfo rowInfo)
{
    GridViewInfo currentView = rowInfo.ActiveView;
    foreach (GridViewInfo view in rowInfo.Views)
    {
        rowInfo.ActiveView = view;
        foreach (GridViewRowInfo row in rowInfo.ChildRows)
        {
            Console.WriteLine(row.Cells[2].Value);
        }
    }
    rowInfo.ActiveView = currentView;
}

````
````VB.NET
Private Sub IterateRows()
    For Each row As GridViewRowInfo In radGridView1.Rows
        Console.WriteLine(row.Cells(1).Value)
        Dim hierarchyRow As GridViewHierarchyRowInfo = TryCast(row, GridViewHierarchyRowInfo)
        If hierarchyRow IsNot Nothing Then
            IterateChildRows(hierarchyRow)
        End If
    Next
End Sub
Private Sub IterateChildRows(rowInfo As GridViewHierarchyRowInfo)
    Dim currentView As GridViewInfo = rowInfo.ActiveView
    For Each view As GridViewInfo In rowInfo.Views
        rowInfo.ActiveView = view
        For Each row As GridViewRowInfo In rowInfo.ChildRows
            Console.WriteLine(row.Cells(2).Value)
        Next
    Next
    rowInfo.ActiveView = currentView
End Sub

````

{{endregion}} 





# See Also
* [Accessing Child Templates]({%slug winforms/gridview/hierarchical-grid/how-to/accessing-child-templates%})

* [Applying formatting only to cells in a child template]({%slug winforms/gridview/hierarchical-grid/how-to/applying-formatting-only-to-cells-in-a-child-template%})

* [Expanding all rows]({%slug winforms/gridview/hierarchical-grid/how-to/expanding-all-rows%})

* [Resizing child GridViewInfo]({%slug winforms/gridview/hierarchical-grid/how-to/resizing-child-gridviewinfo%})

