---
title: Overview of RadGridView Structure
page_title: Overview of RadGridView Structure - RadGridView
description: Learn more about the RadGridView Structure and all the elements, which you can use in your WinForms apps.
slug: winforms/gridview/fundamentals/overview-of-radgridview-structure
tags: overview,of,radgridview,structure
published: True
position: 2
previous_url: gridview-fundamentals-overview-of-radgridview-structure
---

# Overview of RadGridView Structure

## Row

Each row in __RadGridView__ is represented by __GridRowElement__ class.

![gridview-fundamentals-overview-of-radgridview-structure 001](images/gridview-fundamentals-overview-of-radgridview-structure001.png)

## HeaderRow

The header element is represented by __GridHeaderRowElement__ class.

![gridview-fundamentals-overview-of-radgridview-structure 002](images/gridview-fundamentals-overview-of-radgridview-structure002.png)

## NewRow

Depending on the value of __GridViewTemplate.AddNewRowPosition__ property, the new row element appears below the header row or after the data rows. 

![gridview-fundamentals-overview-of-radgridview-structure 003](images/gridview-fundamentals-overview-of-radgridview-structure003.png)

## FilteringRow

*FilteringRow* appears automatically when you have [Filtering]({%slug winforms/gridview/filtering/basic-filtering%}) enabled by __EnableFiltering__ or __GridViewTemplate.EnableFiltering__ properties.

![gridview-fundamentals-overview-of-radgridview-structure 004](images/gridview-fundamentals-overview-of-radgridview-structure004.png)

## GridViewIndentColumn

This column appears when the grid data is grouped or there is a hierarchical structure to facilitate the expand/collapse functionality. The expand column is always placed in front of all other grid content columns and cannot be moved.

![gridview-fundamentals-overview-of-radgridview-structure 005](images/gridview-fundamentals-overview-of-radgridview-structure005.png)

## GridViewDataColumn

Displays a column bound to a field in a data source.

![gridview-fundamentals-overview-of-radgridview-structure 006](images/gridview-fundamentals-overview-of-radgridview-structure006.png)

## MasterTemplate

__MasterTemplate__ is the top most __GridViewTemplate__ in the hierarchical structure which stores the columns and rows at the root grid level. It contains all inner __GridViewTemplates__(__GridViewTemplate.Templates__ collection). When there is no hierarchical structure, only the __MasterTemplate__ is displayed. 

![gridview-fundamentals-overview-of-radgridview-structure 007](images/gridview-fundamentals-overview-of-radgridview-structure007.png)

## GridViewTemplate

__GridViewTemplate__ is a basic class containing settings for a single level of the hierarchical structure.

![gridview-fundamentals-overview-of-radgridview-structure 008](images/gridview-fundamentals-overview-of-radgridview-structure008.png)

## GroupPanel

When you want to enable the group-by functionality for the end-user, you need to set __RadGridView.GroupingEnabled__ to *true* and __GridViewTemplate.EnableGrouping__.  If you want to prevent the end-user to drag column header into the __GroupPanel,__  set __GridViewTemplate.AllowDragToGroup__ to *false*. __RadGridView.ShowGroupPanel__ shows/hides the group panel. You can access the group panel using __RadGridView.GridElement.HeaderElement.GroupPanel__ property. 

![gridview-fundamentals-overview-of-radgridview-structure 010](images/gridview-fundamentals-overview-of-radgridview-structure010.png)
# See Also
* [Binding the Grid]({%slug winforms/gridview/fundamentals/binding-the-grid%})

* [Columns]({%slug winforms/gridview/fundamentals/columns%})

* [Creating Hierarchical Grids]({%slug winforms/gridview/fundamentals/creating-hierarchical-grids%})

* [Editing]({%slug winforms/gridview/fundamentals/editing%})

* [Element Hierarchy]({%slug winforms/gridview/fundamentals/element-hierarchy%})

* [Key Features]({%slug winforms/gridview/fundamentals/key-features%})

* [Keyboard Support]({%slug winforms/gridview/fundamentals/keyboard-support%})

* [Logical vs. Visual Grid Structure]({%slug winforms/gridview/fundamentals/logical-vs.-visual-grid-structure%})

