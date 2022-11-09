---
title: Elements Overview
page_title: Overview - Telerik Presentation Framework
description: This article shows the elements types used in Telerik Presentation Framework.
slug: winforms/telerik-presentation-framework/elements/overview
tags: overview
published: True
position: 0
previous_url: tpf-elements-overview
---

# Elements Overview

Elements fall into three categories, depending on their base class:

* __Layout elements__ derive from [LayoutPanel]({%slug winforms/telerik-presentation-framework/class-hierarchy/layoutpanel%}). Each LayoutPanel arranges child items in a particular manner.

* __Painted elements__ derive from [BasePrimitive]({%slug winforms/telerik-presentation-framework/class-hierarchy/baseprimitive%}). They override the OnPaint method to draw figures on the controls graphic surface.

* __Component elements__ derive from [RadItem]({%slug winforms/telerik-presentation-framework/class-hierarchy/raditem%}). RadItem descendants handle user input and can be used in the design environment. A component element overrides the virtual __CreateChildElements__ method to create one or more layout elements and primitives. Typically TPF based controls are simple wrappers around RadItem descendant classes, and the RadItem descendant classes define logic and user interface. See the [RadRadioButtonElement]({%slug winforms/telerik-presentation-framework/elements/radradiobuttonelement%}) and [RadTrackBarElement]({%slug winforms/telerik-presentation-framework/elements/radtrackbarelement%}) topics for examples.

# See Also
* [RadRadioButtonElement]({%slug winforms/telerik-presentation-framework/elements/radradiobuttonelement%})

* [RadTrackBarElement]({%slug winforms/telerik-presentation-framework/elements/radtrackbarelement%})

