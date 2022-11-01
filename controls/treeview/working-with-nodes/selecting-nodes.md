---
title: Selecting Nodes
page_title: Selecting Nodes - WinForms TreeView Control
description: WinForms TreeView supports both selecting single or multiple nodes. This article shows how you can select nodes in the code. 
slug: winforms/treeview/working-with-nodes/selecting-nodes
tags: selecting,nodes
published: True
position: 5
previous_url: treeview-working-with-nodes-selecting-nodes
---

# Selecting Nodes

## Selecting a Single Node

To select a node use the __Selected__ property of __RadTreeNode__. The following example demonstrates how to do it.

{{source=..\SamplesCS\TreeView\WorkingWithNodes\WorkingWithNodes1.cs region=selectedNode}} 
{{source=..\SamplesVB\TreeView\WorkingWithNodes\WorkingWithNodes1.vb region=selectedNode}} 

````C#
radTreeView1.SelectedNode = radTreeView1.Nodes[0];

````
````VB.NET
RadTreeView1.SelectedNode = RadTreeView1.Nodes(0)

````

{{endregion}} 

## Selecting Multiple Nodes

To enable the multiple selection the __MultiSelect__ property must be set to *true*. The default value is *false*.


| __Selection__ | __Example__ | __Description__ |
|---------------|-------------|-----------------|
| __Single Selection__ |![](images/treeview-working-with-nodes-selecting-nodes001.png)|The user can select a single node by clicking the node.|
| __Multiple Selection using the Shift key__ |![](images/treeview-working-with-nodes-selecting-nodes002.png)|To select a continuous series of multiple nodes at one time hold __Shift__ and click on a node using the mouse. That will select all nodes between the first selected node and the node that was just clicked. The screenshot shows nodes selected between "Deleted Items" and "Large Mail".|
| __Multiple Selection using the Ctrl key__ |![treeview-working-with-nodes-selecting-nodes 003](images/treeview-working-with-nodes-selecting-nodes003.png)|To select multiple nodes in distributed throughout, hold __Ctrl__ and click on each node using the mouse. That will select the clicked node or unselect the previously selected nodes. The screenshot shows the "Deleted Items" and "Send Items" nodes selected.|

## Selecting Multiple Nodes Programmatically

To select multiple nodes through the API, just set the Selected property of the desired nodes to true. The example below adds four nodes, then selects the last two nodes.

{{source=..\SamplesCS\TreeView\WorkingWithNodes\WorkingWithNodes1.cs region=selectMultiNodes}} 
{{source=..\SamplesVB\TreeView\WorkingWithNodes\WorkingWithNodes1.vb region=selectMultiNodes}} 

````C#
radTreeView1.MultiSelect = true;
RadTreeNode Node1 = new RadTreeNode("Inbox");
RadTreeNode Node2 = new RadTreeNode("Deleted Items");
RadTreeNode Node3 = new RadTreeNode("Outbox");
RadTreeNode Node4 = new RadTreeNode("Sent");
radTreeView1.Nodes.Add(Node1);
radTreeView1.Nodes.Add(Node2);
radTreeView1.Nodes.Add(Node3);
radTreeView1.Nodes.Add(Node4);
Node3.Selected = true;
Node4.Selected = true;

````
````VB.NET
RadTreeView1.MultiSelect = True
Dim Node1 As New RadTreeNode("Inbox")
Dim Node2 As New RadTreeNode("Deleted Items")
Dim Node3 As New RadTreeNode("Outbox")
Dim Node4 As New RadTreeNode("Sent")
RadTreeView1.Nodes.Add(Node1)
RadTreeView1.Nodes.Add(Node2)
RadTreeView1.Nodes.Add(Node3)
RadTreeView1.Nodes.Add(Node4)
Node3.Selected = True
Node4.Selected = True

````

{{endregion}}

## SelectedNodeChanged Event

When multiple selection functionality is turned on, the __SelectedNodeChanged__ event will be called twice: first for the previously selected node first and one more time for the newly selected node. In the RadTreeViewEventArgs you can distinguish the two event firings by the __Action__ property which is set to __Unknown__ when the selection is cleared.

{{source=..\SamplesCS\TreeView\WorkingWithNodes\WorkingWithNodes1.cs region=selectedNodeEvent}} 
{{source=..\SamplesVB\TreeView\WorkingWithNodes\WorkingWithNodes1.vb region=selectedNodeEvent}}

````C#
private void radTreeView1_SelectedNodeChanged(object sender, Telerik.WinControls.UI.RadTreeViewEventArgs e)
{
    if (e.Action != Telerik.WinControls.UI.RadTreeViewAction.ByMouse)
    {
        Console.WriteLine(e.Node.Text);
    }
}

````
````VB.NET
Private Sub RadTreeView1_SelectedNodeChanged(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.RadTreeViewEventArgs)
        If e.Action <> Telerik.WinControls.UI.RadTreeViewAction.ByMouse Then
            Console.WriteLine(e.Node.Text)
        End If
End Sub

````

{{endregion}}

Another approach will be to check the __Selected__ property of the node. If it is true, execute your logic.

{{source=..\SamplesCS\TreeView\WorkingWithNodes\WorkingWithNodes1.cs region=selectedPropertyOfTheNode}} 
{{source=..\SamplesVB\TreeView\WorkingWithNodes\WorkingWithNodes1.vb region=selectedPropertyOfTheNode}}

````C#
private void radTreeView2_SelectedNodeChanged(object sender, RadTreeViewEventArgs e)
{
    if (e.Node.Selected == true)
    {
        Console.WriteLine(e.Node.Text);
    }
}

````
````VB.NET
Private Sub RadTreeView2_SelectedNodeChanged(ByVal sender As Object, ByVal e As RadTreeViewEventArgs)
    If e.Node.Selected = True Then
        Console.WriteLine(e.Node.Text)
    End If
End Sub

````

{{endregion}}

# See Also
* [Adding and Removing Nodes]({%slug winforms/treeview/working-with-nodes/adding-and-removing-nodes%})

* [Bring a Node into View]({%slug winforms/treeview/working-with-nodes/bring-a-node-into-view%})

* [Custom Filtering]({%slug winforms/treeview/working-with-nodes/custom-filtering%})

* [Custom Nodes]({%slug winforms/treeview/working-with-nodes/custom-nodes%})

* [Custom Sorting]({%slug winforms/treeview/working-with-nodes/custom-sorting%})

* [Events]({%slug winforms/treeview/working-with-nodes/events%})

