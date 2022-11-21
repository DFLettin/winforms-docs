---
title: Inherit themes from RadControls derivatives
page_title: Inherit themes from RadControls derivatives - Telerik Presentation Framework
description: In order the themes to be applied to your custom controls you need to override the ThemeClassName and ThemeEffectiveType properties.
slug: winforms/telerik-presentation-framework/inherit-themes-from-radcontrols-derivatives
tags: inherit,themes,from,radcontrols,derivatives
published: True
position: 18
previous_url: tpf-inherit-themes-from-radcontrols-derivatives
---

# Inherit themes from RadControls derivatives


## Inherit from a RadControl descendant

When you inherit from a __RadControl__ (or any __RadControl__ descendant), the original control themes are not automatically inherited. The good thing is that this behavior can be overridden very easily by overriding the __ThemeClassName__ property of the descendant of __RadControl__: 

{{source=..\SamplesCS\TPF\InheritThemes.cs region=RadCustomButton}} 
{{source=..\SamplesVB\TPF\InheritThemes.vb region=RadCustomButton}} 

````C#
        
public class RadCustomButton : RadButton  
{ 
    public override string ThemeClassName  
    { 
        get 
        { 
            return typeof(RadButton).FullName;  
        }
    }
}

````
````VB.NET
Public Class RadCustomButton
    Inherits RadButton
    Public Overrides Property ThemeClassName As String
        Get
            Return GetType(RadButton).FullName
        End Get
        Set(value As String)
            MyBase.ThemeClassName = value
        End Set
    End Property
End Class

````

{{endregion}} 

The example above uses __RadButton__ as a base class. Since the themes depend on the type of the themed class (which is changed when you inherit), using the described override makes base control themes available in the descendant control.

## Inherit from a RadElement descendant

When you inherit from a __RadElement__ descendant (for example __RadButtonElement__), you need to override the __ThemeEffectiveType__ property. This will allow you to have the styling applied to the instance of your custom element class:

{{source=..\SamplesCS\TPF\InheritThemes.cs region=MyRadButtonElement}} 
{{source=..\SamplesVB\TPF\InheritThemes.vb region=MyRadButtonElement}} 

````C#
        
public class MyRadButtonElement : RadButtonElement     
{ 
    protected override Type ThemeEffectiveType     
    { 
        get    
        { 
            return typeof(RadButtonElement);     
        }
    }
}

````
````VB.NET
Public Class MyRadButtonElement
Inherits RadButtonElement
    Protected Overrides ReadOnly Property ThemeEffectiveType() As Type
        Get
            Return GetType(RadButtonElement)
        End Get
    End Property
End Class

````

{{endregion}}

# See Also
* [Animations]({%slug winforms/telerik-presentation-framework/animations%})

* [Dependency Properties]({%slug winforms/telerik-presentation-framework/dependency-properties%})

* [Handling User Input]({%slug winforms/telerik-presentation-framework/handling-user-input%})

* [HTML-like Text Formatting]({%slug winforms/telerik-presentation-framework/html-like-text-formatting%})

* [Microsoft Active Accessibility Support]({%slug winforms/telerik-presentation-framework/microsoft-active-accessibility-support%})

* [Override Theme Settings at Run Time]({%slug winforms/telerik-presentation-framework/override-theme-settings-at-run-time%})


* [RadMarkupDialog]({%slug winforms/telerik-presentation-framework/radmarkupdialog%})

