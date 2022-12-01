---
title: Section Columns
page_title: Section Columns - WinForms RichTextEditor Control
description: With the Section Columns feature, WinForms RichTextEditor allows you arrange the text in a Section into columns.
slug: radrichtexteditor-ui-for-applying-rich-text-formatting-section-columns
tags: section, column
published: True
position: 1
---

# Section Columns

With the Section Columns feature, **RadRichTextEditor** allows you arrange the text in a [Section]({%slug winforms/richtexteditor-/document-elements/section%}) into columns. This article will show you how to use the predefined UI to arrange the text into columns with equal or different width.

* [Create Section Columns](#create-section-columns)

* [Changing the Width of a Section Column](#changing-the-width-of-a-section-column)

>caption Figure 1: Text laid out in column

![WinForms RadRichTextEditor Text laid out in column](images/RadRichTextEditor_Features_Section_Columns_01.png)

## Create Section Columns

The Page Layout tab of [RadRichTextEditorRibbonUI]({%slug winforms/richtexteditor-/ui-for-applying-rich-text-formatting/ribbon-ui%}) allows you set different types of section columns.

>caption Figure 2: Section columns menu

![WinForms RadRichTextEditor Section columns menu](images/RadRichTextEditor_Features_Section_Columns_03.png)

* **One**: Represents a single text column.

* **Two**: Represents two text columns with equal width.

* **Three**: Represents three text columns with equal width.

* **Left**: Represents two text columns where the left one has a smaller width than the right one.

* **Right**: Represents two text columns where the right one has a smaller width than the left one.

* **More Columns...**: Opens the *Section Columns Dialog* that allows you set columns with custom width and spacing. 

>caption Figure 3: Left option applied on a section

![WinForms RadRichTextEditor Left option applied on a section](images/RadRichTextEditor_Features_Section_Columns_02.png)

## Changing the Width of a Section Column

When the Section contains columns with equal width, you can customize the width of a column through the Document Ruler. When the caret is positioned on a column, a thumb appears that allows you change the width by dragging it.

>caption Figure 4: Customizing the width of a column

![WinForms RadRichTextEditor Customizing the width of a column](images/RadRichTextEditor_Features_Section_Columns_04.png)

Another approach for applying different settings to section columns is through the Columns dialog.

>caption Figure 5: Customizing the width and spacing of columns using dialog

![WinForms RadRichTextEditor Customizing the width and spacing of columns using dialog](images/RadRichTextEditor_Features_Section_Columns_05.png)

# See Also

* [Section]({%slug winforms/richtexteditor-/document-elements/section%})
* [RadDocument]({%slug winforms/richtexteditor-/document-elements/raddocument%})
* [RadDocumentEditor]({%slug winforms/richtexteditor-/features/raddocumenteditor%})
