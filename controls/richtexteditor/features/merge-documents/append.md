---
title: Append Documents
page_title: Append Documents - RadRichTextEditor
description: RadRichTextEditor is a control that is able to display and edit rich-text content including formatted text arranged in pages, paragraphs, spans (runs), tables, etc. 
slug: winforms/richtexteditor/features/merge-documents/append
tags: events
published: True
position: 1 
---

# Append Documents

The [RadDocumentMerger]({%slug winforms/richtexteditor/features/merge-documents/raddocumentmerger%}) class exposes the __AppendDocument()__ method that enables you to append a [RadDocument]({%slug winforms/richtexteditor-/document-elements/raddocument%}) instances.

The overloads of the __AppendDocument()__ method allow you to pass a parameter of type **AppendDocumentOptions**. You can use this parameter to customize the way the merge conflicts are resolved and the new document is inserted. The available properties are as follows:

* **ConflictingStylesResolutionMode**: Determines the mode of resolving conflicts between styles with same IDs. This property is of type **ConflictingStylesResolutionMode** and can have the following enum values:

	* **UseTargetStyle**: The style of the target document is used. For example, if the target and source documents have a style with the name "MyStyle", but with different properties, the one from the target document is used by the merged document and the one from the source document is not added to the style repository of the target document.
	
	* **RenameSourceStyle**: The style of the source document is renamed and used. For example, if the target and source documents have a style with the name "MyStyle", but with different properties, the one from the source is renamed to "MyStyle\_1", added to the style repository of the target document and used by the elements merged from the source document. *This is the default value*.

* **FirstSourceSectionPropertiesResolutionMode**: Determines whether the source document should be inserted in the target with a preceding **SectionBreak**, and whether the source section properties should be omitted or preserved. **The value is used only for the first section of the source document**. The rest of the section elements and their properties remain unchanged. 

	The property is of type **SectionPropertiesResolutionMode** and it can have the following enum values:

	* **NoSectionBreak**: Append the document elements from the source **RadDocument** into the target without a preceding section break. Only the block elements from the first source section are inserted. The first section properties, headers and footers are omitted. 
	
	* **Source**: Append the first source section as it is, with a preceding section break. The type of break is specified in the section properties of the first source section. The rest of the section properties, headers and footers are preserved. For example, if the source section has a *landscape* orientation and the target has *portrait*, the result section will have a *landscape* orientation.
	
	* **Target**: Append the first source section with a preceding section break. The type of break is specified in the section properties of the first source section. The section properties, headers and footers are copied from the last section in the target document. For example, if the source section has a *landscape* orientation and the target has *portrait*, the result section will have a *portrait* orientation.
	
	* **SourceStartOnNextPage**: Append the first source section as it is, with a preceding section break of type *SectionBreakType.NextPage*. The section properties, headers and footers are preserved. For example, if the source section has a *landscape* orientation and the target has *portrait*, the result section will have a *landscape* orientation.

	* **SourceStartOnEvenPage**: Append the first source section as it is, with a preceding section break of type *SectionBreakType.EvenPage*. The section properties, headers and footers are preserved. For example, if the source section has  a *landscape* orientation and the target has *portrait*, the result section will have a *landscape* orientation.
	
	* **SourceStartOnOddPage**: Append the first source section as it is, with a preceding section break of type *SectionBreakType.OddPage*. The section properties, headers and footers are preserved. For example, if the source section has  a *landscape* orientation and the target has *portrait*, the result section will have a *landscape* orientation.
	
	* **SourceStartContinuous**: Append the first source section as it is, with a preceding section break of type *SectionBreakType.Continuous*. The section properties, headers and footers are preserved. For example, if the source section has a *landscape* orientation and the target has *portrait*, the result section will have a *landscape* orientation, but the break type will change to a next page since two sections with different orientation or a page size cannot exist on a single page.


#### **Example 1: Using the AppendDocument() method**


{{source=..\SamplesCS\RichTextEditor\GettingStarted\Main.cs region=cs-radrichtextbox-features-merge-append-documents_1}} 
{{source=..\SamplesVB\RichTextEditor\GettingStarted\Main.vb region=cs-radrichtextbox-features-merge-append-documents_1}} 

````C#
Telerik.WinForms.Documents.Model.Merging.RadDocumentMerger documentMerger = new RadDocumentMerger(targetDocument);
Telerik.WinForms.Documents.Model.Merging.AppendDocumentOptions options = new AppendDocumentOptions();
options.ConflictingStylesResolutionMode = ConflictingStylesResolutionMode.UseTargetStyle;
options.FirstSourceSectionPropertiesResolutionMode = SectionPropertiesResolutionMode.Target;
documentMerger.AppendDocument(sourceDocument, options);

````
````VB.NET
Dim documentMerger As Telerik.WinForms.Documents.Model.Merging.RadDocumentMerger = New RadDocumentMerger(targetDocument)
Dim options As Telerik.WinForms.Documents.Model.Merging.AppendDocumentOptions = New AppendDocumentOptions()
options.ConflictingStylesResolutionMode = ConflictingStylesResolutionMode.UseTargetStyle
options.FirstSourceSectionPropertiesResolutionMode = SectionPropertiesResolutionMode.Target
documentMerger.AppendDocument(sourceDocument, options)

````

{{endregion}} 

There is another overload of **AppendDocument()** that takes only a **RadDocument** instance. When you use this overload, the default values of **AppendDocumentOptions** are used when merging documents.  

## Behavior

**AppendDocumentOptions** enables full customization over the way the appending is executed. So, the results of the different scenarios depend on the settings you choose. **Table 1** describes several restrictions you should keep in mind when using **AppendDocument()**.
 
#### **Table 1: Restrictions for using AppendDocument()**
<table>
<tr>
	<th>Action </th>
	<th>Result </th>
</tr>

<tr>
	<td>Append the source document in a table cell and source document contains multiple sections.</td>
	<td>An InvalidOperationException is thrown.</td>
</tr>

<tr>
	<td>Source document is empty.</td>
	<td>An ArgumentException is thrown.</td>
</tr>
</table>


## See Also

* [RadDocumentMerger]({%slug winforms/richtexteditor/features/merge-documents/raddocumentmerger%})
* [Insert Document at the Caret Position]({%slug winforms/richtexteditor/features/merge-documents/merge%})
 
