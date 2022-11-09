---
title: Section
page_title: Section - UI for WinForms Documentation
description: Section
slug: winforms/richtextbox-(obsolete)/features/document-elements/section
tags: section
published: True
position: 2
previous_url: richtextbox-features-document-elements-section
---

# Section

The __Section__ class allows you to separate the content into sections. __Sections__ are chunks of the document that can be displayed on one or several pages. Currently only one section in the document is supported and all declared sections are merged into one when the document is measured.

A __Section__ can contain only __Paragraph__ and __Table__ elements. You are also able to customize the section layout by setting its properties.

This topic will explain you how to:

* [Add Paragraphs to a Section](#add-paragraphs-to-a-section)

* [Customize the Section](#customize-the-section)

## Add Paragraphs to a Section

In order to add paragraphs you have to use the __Paragraphs__ collection of the __Section__.

{{source=..\SamplesCS\RichTextBox\Features\Document Elements\RichTextBoxSection.cs region=AddSection}} 
{{source=..\SamplesVB\RichTextBox\Features\Document Elements\RichTextBoxSection.vb region=AddSection}} 

````C#
Section section = new Section();
Paragraph paragraph = new Paragraph();
section.Blocks.Add(paragraph);
this.radRichTextBox1.Document.Sections.Add(section);

````
````VB.NET
Dim section As New Section()
Dim paragraph As New Paragraph()
section.Blocks.Add(paragraph)
Me.RadRichTextBox1.Document.Sections.Add(section)

````

{{endregion}}

## Customize the Section

The __Section__ exposes several properties that allow you to customize the layout of the elements placed underneath it. Here is a list of these properties:

* __PageMargin__ - represents the margin towards the edges of the page when in __Paged__ mode.
