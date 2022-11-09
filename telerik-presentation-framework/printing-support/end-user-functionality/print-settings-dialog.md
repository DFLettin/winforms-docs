---
title: Print Settings Dialog
page_title: Print Settings Dialog - Telerik Presentation Framework
description: RadPrintSettingsDialog represents a base dialog for editing printing settings.
slug: winforms/telerik-presentation-framework/printing-support/end-user-functionality/print-settings-dialog
tags: print,settings,dialog
published: True
position: 1
previous_url: tpf-printing-support-radprintsettingdialog
---

# Print Settings Dialog

RadPrintSettingsDialog represents a base dialog for editing printing settings. Each printable object should provide such dialog to edit its settings. This dialog should not be used directly. Instead, the control-specific extended RadPrintSettingsDialogs like SchedulerPrintSettingsDialog and GridPrintSettingsDialog should be used.


The RadPrintSettingsDialog contains three tabs:


* The first of them (__"Format"__ tab) is empty and is reserved for specific settings of the printed object.


* The __"Paper"__ tab provides the means for editing page settings like orientation, margin and size.


* The __"Header/Footer"__ tab provides the means for editing the text that appears at the top and at the bottom of each page. You can use a set of predefined strings to display system dependent text like page number, page count, current date and time or current user. The command buttons at the bottom of this page allows you to insert these strings to the currently focused text field.


# See Also
* [Print Preview Dialog]({%slug winforms/telerik-presentation-framework/printing-support/end-user-functionality/print-preview-dialog%})

* [Watermark Dialog]({%slug winforms/telerik-presentation-framework/printing-support/end-user-functionality/watermark-dialog%})
