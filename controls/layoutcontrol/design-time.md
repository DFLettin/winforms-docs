---
title: Design Time
page_title: Design Time - WinForms LayoutControl
description: Get familiar with the design time options that WinForms LayoutControl offers.
slug: winforms/layoutcontrol/design-time
tags: design,time
published: True
position: 2
previous_url: layoutcontrol-design-time
---

# Design Time

This article describes what the user can do with __RadLayoutControl__ at design time.

>important Copying and Pasting of an entire layout control, with added items in it, is not supported in the Visual Studio designer.

## Smart Tag

The smart tag allows you to open the layout editor, change the theme and open the on-line resources. You can dock the control in its parent container as well. The following section describes the layout editor.
        
>caption Figure 1: Smart Tag
![WinForms RadLayoutControl Smart Tag](images/layoutcontrol-design-time001.png)

## Layout Editor

The layout editor allows you to add and arrange [items]({%slug winforms/layoutcontrol/items%}) at design time. It can be opened from the smart tag.
      
>caption Figure 2: The Design Time Layout Editor
![WinForms RadLayoutControl The Design Time Layout Editor](images/layoutcontrol-design-time002.png)

This editor allows you to add items to the layout. To do this just drag and drop an item from the __Items__ tab in the layout panel. You can hide existing items with the default context menu as well. The __Structure__ tab shows the current layout structure and allows easier item selection. You can start drag and drop operation from this tab to the layout panel.

## Arrange Controls 

At design time you will be able to add and arrange any underlying controls you want. To achieve that just drag a control on the layout panel. The drag hint will show you where the control will be positioned. Once you are ready you should just drop the control in the desired position.

>note To position the controls in different location at least one item should be added to the layout panel. It could be an empty space item.
>

>caption Figure 3: Adding Control at Design Time
![WinForms RadLayoutControl Adding Control at Design Time](images/layoutcontrol-design-time003.gif)

## Selection Glyph

The selection glyph is an arrow that is shown when a control in the layout panel is selected. It allows you to select the underlying host [item]({%slug winforms/layoutcontrol/items%}) and change its properties at design time.
        
>caption Figure 4: Selection Glyph
![WinForms RadLayoutControl Selection Glyph](images/layoutcontrol-design-time004.png)

## Adding Groups

The groups can be expanded or collapsed. The group contains separate layout panel which allows you to add and arrange the controls in it just like in the layout control. To add a group you should first open the Layout Editor. First you can just add a free space item. This way the group would not occupy the entire space. Now you can add a group, once the group is added you can close the Layout Editor and add controls to the group. Figure 5 shows a sample layout with a group. 
        
>caption Figure 5: Adding Group
![WinForms RadLayoutControl Adding Group](images/layoutcontrol-design-time005.png)

## Adding Tabbed Groups

The tabbed group allows you to display the underlying controls with tabbed layout. To add a tabbed group first open the Layout Editor and add a free space item to the layout panel. Now add a tabbed group to the panel. Once the group is added you can add tabs by adding regular group items to the tabbed group. The first one should occupy the entire space of the tabbed group. The second should be added to the top of the tabbed group. After the tabs are added you can add controls like you do in the regular layout panel.
        
>caption Figure 6: Adding Tabbed Groups
![WinForms RadLayoutControl Adding Tabbed Groups](images/layoutcontrol-design-time006.gif)

# See Also

 * [Items]({%slug winforms/layoutcontrol/items%})
 * [Getting Started]({%slug winforms/layoutcontrol/getting-started%})
 * [Properties, Methods and Events]({%slug winforms/layoutcontrol/properties-methods-and-events%})
