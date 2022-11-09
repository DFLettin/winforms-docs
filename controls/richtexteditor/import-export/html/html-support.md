---
title: HTML support
page_title: HTML support - RadRichTextEditor
description: RadRichTextEditor is a control that is able to display and edit rich-text content including formatted text arranged in pages, paragraphs, spans (runs), tables, etc.
slug: winforms/richtexteditor-/import/export/html-support
tags: html,support
published: True
position: 3
previous_url: richtexteditor-import-export-html-support
---

# HTML support

A major requirement for providing rich text editing capabilities is support for HTML. The __RadRichTextEditor__ control is designed to offer [import/export]({%slug winforms/richtexteditor/import-export/overview%}) functionality for __HTML__ out of the box – through the __HtmlFormatProvider__. However, as __HTML__ is a diverse and complicated standard, supporting it comes with certain limitations. __HtmlFormatProvider__ is designed to handle slightly malformed __HTML__ (missing closing tags, missing quotes around attributes), however in this case correct parsing cannot be guaranteed. For best results we recommend importing valid __XHTML__ content.
      
The purpose of this article is to outline which parts of the __HTML__ are supported.
      
## Importing

When the __HtmlFormatProvider__ imports an __HTML__ document, it parses it and converts the HTML element tree to a [RadDocument]({%slug winforms/richtexteditor-/document-elements/raddocument%}). Importing is basically made up of two parts – content and styling.
        
## Content

HTML content is mapped to several types of __RadDocument__ elements – paragraphs, spans and tables.
        
Tags mapped to paragraphs are:
        
* __\<p\>__

* __\<h1\>__ through __\<h6\>__

* __\<ul\>, \<ol\>, \<li\>__

* __\<tr\>__

Tags generating table content:
        
* __\<table\>__

* __\<tr\>__

* __\<th\>__

* __\<td\>__

>note The content of the __\<th\>__ tags will be bold, as they are treated as table headers.
>

Tags mapped to spans are:
        
* __formatting tags, \<span\>, \<font\>__

>note Additionally, line breaks are inserted between consequent block elements ( __\<div\>__ ).
>

## Styling

Styling is supported through CSS styles (classes or inline) and a number of formatting tags (including __\<font\>__). Although the __\<font\>__ tag has been deprecated, legacy software and markup requires support for it.
        
Supported formatting tags are:        

* __\<b\>, \<strong\>__ – turn on bold
            
* __\<i\>, \<em\>__ – turn on italic
            
* __\<u\>__ – turn on underline
            
* __\<h1\>__ through __\<h6\>__ – apply heading
            
* __\<sub\>__ – turn on subscript
            
* __\<sup\>__ – turn on superscript
            
Supported CSS properties are:
        
* __text-align__

* __margin-left__

* __margin-right__

* __color__

* __background-color__

* __font-family__

* __font-size__

* __font-style__

* __font-weight__

* __text-decoration (underline, line-through)__

* __vertical-align (sub, super)__

Supported __\<font\>__ tag attributes are:
        
* __face__ – equivalent to CSS property __font-family__

* __size__ – equivalent to CSS property __font-size__

* __color__ – equivalent to CSS property __color__

## Exporting

When exporting to __HTML__, the __HtmlFormatProvider__ iterates through the __RadDocument__ tree and generates __HTML__ nodes. It is designed to generate valid __XHTML__ document in order to preserve the formatting as much as possible. Styles are exported as CSS classes in the head of the document and used through the body. The structure of the __HTML__ document closely resembles that of __RadDocument__ – paragraphs and spans.
        
