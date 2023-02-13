---
title: Exact Time Rendering
page_title: Exact time rendering - WinForms Scheduler Control
description: WinForms Scheduler supports functionality to arrange appointments according to their start time and duration.
slug: winforms/scheduler/views/exact-time-rendering
tags: exact,time,rendering
published: True
position: 13
previous_url: scheduler-views-exact-time-rendering
---

# Exact Time Rendering

__RadScheduler__ supports functionality to arrange appointments according to their start time and duration. The __EnableExactTimeRendering__ property should get or set a value, indicating whether the appointment start and end time should be rendered exactly. By default its value is *false*.

>note Due to the great difference in the amount of time, which different time scales represent, appointments might become too small to render accurately in larger time scales.
>

>caption Figure 1: Day View

![WinForms RadScheduler Day View](images/scheduler-views-exact-time-rendering001.png)

>caption Figure 2: Week View

![WinForms RadScheduler Week View](images/scheduler-views-exact-time-rendering002.png)

>caption Figure 3: Month View

![WinForms RadScheduler Month View](images/scheduler-views-exact-time-rendering003.png)

>caption Figure 4: Timeline View

![WinForms RadScheduler Timeline View](images/scheduler-views-exact-time-rendering004.png)

>important Agenda view doesn't support exact time rendering since it uses RadGridView to display appointments.

# See Also

* [Common Visual Properties]({%slug winforms/scheduler/views/common-visual-properties%})
* [Working with Views]({%slug winforms/scheduler/views/working-with-views%})
* [Views Walkthrough]({%slug winforms/scheduler/views/views-walkthrough%})
* [Grouping by Resources]({%slug winforms/scheduler/views/grouping-by-resources%})
* [Exact Time Rendering]({%slug winforms/scheduler/views/exact-time-rendering%})
