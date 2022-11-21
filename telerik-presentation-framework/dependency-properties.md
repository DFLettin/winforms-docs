---
title: Dependency Properties
page_title: Dependency Properties - Telerik Presentation Framework
description: RadControls support the Telerik Presentation Framework (TPF) dependency property system.
slug: winforms/telerik-presentation-framework/dependency-properties
tags: dependency,properties
published: True
position: 7
previous_url: tpf-dependency-properties
---

# Dependency Properties

RadControls support the Telerik Presentation Framework (TPF) dependency property system. Dependency properties are properties that depend on the values of other inputs. Unlike the standard Common Language Runtime (CLR) properties, dependency properties may get their input from multiple sources like themes, animation, data binding, or through parent-child relationships with other elements in the element tree.

The naming convention for the property is a descriptive property name followed by "Property", i.e. for a "Height" property the dependency property name is "HeightProperty".

Dependency properties are static and are created using the static [RadProperty]({%slug winforms/telerik-presentation-framework/class-hierarchy/radproperty%}) Register() method. The Register method describes the name of the property, owner type, property type and meta data for the property. Typically, the property is then wrapped as a standard CLR type property using the [RadObject]({%slug winforms/telerik-presentation-framework/class-hierarchy/radobject%}) __GetValue()__ and __SetValue()__ methods.

The example below registers a new __IsDefaultButtonProperty__, wraps the dependency property as a standard CLR property - "IsDefaultButton". In addition the property meta data sets the default value and the callback method (this method will be executed when the property is changed).

{{source=..\SamplesCS\TPF\DependencyProperties.cs region=property}} 
{{source=..\SamplesVB\TPF\DependencyProperties.vb region=property}} 

````C#
public class MyButtonElement : RadButtonElement
{
    public static RadProperty IsDefaultButtonProperty;
    public MyButtonElement()
    {
        IsDefaultButtonProperty = RadProperty.Register("IsDefaultButton", typeof(bool), typeof(MyButtonElement),
            new RadElementPropertyMetadata(false, ElementPropertyOptions.None, new PropertyChangedCallback(OnIsDefaultButtonPropertyChanged)));
    }
    public bool IsDefaultButton
    {
        get
        {
            return (bool)this.GetValue(IsDefaultButtonProperty);
        }
        set
        {
            this.SetValue(IsDefaultButtonProperty, value);
        }
    }
    protected override Type ThemeEffectiveType
    {
        get
        {
            return typeof(RadButtonElement);
        }
    }
    private static void OnIsDefaultButtonPropertyChanged(RadObject obj, RadPropertyChangedEventArgs e)
    {
        Console.WriteLine("OnIsDefaultButtonChanged");
    }
}

````
````VB.NET
Public Class MyButtonElement
    Inherits RadButtonElement
    Public Shared IsDefaultButtonProperty As RadProperty
    Public Sub New()
        IsDefaultButtonProperty = RadProperty.Register("IsDefaultButton", GetType(Boolean), GetType(MyButtonElement), New RadElementPropertyMetadata(False, ElementPropertyOptions.None, New Telerik.WinControls.PropertyChangedCallback(AddressOf OnIsDefaultButtonPropertyChanged)))
    End Sub
    Public Property IsDefaultButton() As Boolean
        Get
            Return CBool(Me.GetValue(IsDefaultButtonProperty))
        End Get
        Set(value As Boolean)
            Me.SetValue(IsDefaultButtonProperty, value)
        End Set
    End Property
    Protected Overrides ReadOnly Property ThemeEffectiveType() As Type
        Get
            Return GetType(RadButtonElement)
        End Get
    End Property
    Private Shared Sub OnIsDefaultButtonPropertyChanged(obj As RadObject, e As RadPropertyChangedEventArgs)
        Console.WriteLine("OnIsDefaultButtonChanged")
    End Sub
End Class

````

{{endregion}}

# See Also
* [Animations]({%slug winforms/telerik-presentation-framework/animations%})

* [Handling User Input]({%slug winforms/telerik-presentation-framework/handling-user-input%})

* [HTML-like Text Formatting]({%slug winforms/telerik-presentation-framework/html-like-text-formatting%})

* [Inherit themes from RadControls derivatives]({%slug winforms/telerik-presentation-framework/inherit-themes-from-radcontrols-derivatives%})

* [Microsoft Active Accessibility Support]({%slug winforms/telerik-presentation-framework/microsoft-active-accessibility-support%})

* [Override Theme Settings at Run Time]({%slug winforms/telerik-presentation-framework/override-theme-settings-at-run-time%})

* [RadMarkupDialog]({%slug winforms/telerik-presentation-framework/radmarkupdialog%})

