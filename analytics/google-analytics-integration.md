---
title: Google Analytics Integration
page_title: Google Analytics Integration - UI for WinForms Documentation
description: When you are creating an application for a broad audience, integrating some kind of analytics framework is crucial, because you will need to analyze the usage data of the application and its features and most probably you will need to know about any application crashes or other errors occurred during the execution.
slug: winforms/analytics/google-analytics-integration
tags: telerik,analytics,google,integration
published: True
position: 1
---

# Google Analytics Integration

If you wish to analyze the usage data of the application using **Google Analytics**, you can check the [Windows SDK for Google Analytics GitHub repository](https://github.com/dotnet/windows-sdk-for-google-analytics) and build the project located in **GoogleAnalytics.Core**. You then need to add a reference to the generated assembly (**GoogleAnalytics.Core.dll**) to your custom project.

>important The GoogleAnalytics.Core.dll assembly has a dependency against .NET Framework 4.5.1 which should be targeted in the client`s application. 

This article demonstrates a simple implementation according to the API provided by the Windows SDK for Google Analytics.

#### IPlatformInfoProvider Implementation

{{source=..\SamplesCS\Analytics\AnalyticsForm.cs region=IPlatformInfoProviderImplementation}} 
{{source=..\SamplesVB\Analytics\AnalyticsForm.vb region=IPlatformInfoProviderImplementation}}
````C#
public class PlatformInfoProvider : IPlatformInfoProvider
{
    private string anonymousClientId;
    private int? screenColors;
    private Dimensions? screenResolution;
    private string userAgent;
    private string userLanguage;
    private Dimensions? viewPortResolution;
    public PlatformInfoProvider()
    {
        InitializeWindow();
    }
    public string AnonymousClientId
    {
        get
        {
            return this.anonymousClientId;
        }
        private set
        {
            this.anonymousClientId = value;
        }
    }
    public int? ScreenColors
    {
        get
        {
            return this.screenColors;
        }
        private set
        {
            this.screenColors = value;
        }
    }
    public Dimensions? ScreenResolution
    {
        get
        {
            return this.screenResolution;
        }
        private set
        {
            this.screenResolution = value;
            if (ScreenResolutionChanged != null)
            {
                ScreenResolutionChanged(this, EventArgs.Empty);
            }
        }
    }
    public string UserAgent
    {
        get
        {
            return this.userAgent;
        }
        private set
        {
            this.userAgent = value;
        }
    }
    public string UserLanguage
    {
        get
        {
            return this.userLanguage;
        }
        private set
        {
            this.userLanguage = value;
        }
    }
    public Dimensions? ViewPortResolution
    {
        get { return this.viewPortResolution; }
        private set
        {
            this.viewPortResolution = value;
            if (ViewPortResolutionChanged != null)
            {
                ViewPortResolutionChanged(this, EventArgs.Empty);
            }
        }
    }
    public event EventHandler ScreenResolutionChanged;
    public event EventHandler ViewPortResolutionChanged;
    public void OnTracking()
    { }
    private void InitializeWindow()
    {
        this.AnonymousClientId = "b597d28a-0d6c-42ed-9dcb-f89e98006b37"; // Random UUID
        this.ScreenResolution = new Dimensions(1920, 1080);
        this.UserAgent = "Mozilla/5.0 (Windows NT 6.3; WOW64; Trident/7.0; rv:11.0) like Gecko";
        this.UserLanguage = "en-us";
        this.ViewPortResolution = new Dimensions(1920, 1080);
    }
}

````
````VB.NET
Public Class PlatformInfoProvider
    Implements IPlatformInfoProvider
    Private m_anonymousClientId As String
    Private m_screenColors As System.Nullable(Of Integer)
    Private m_screenResolution As System.Nullable(Of Dimensions)
    Private m_userAgent As String
    Private m_userLanguage As String
    Private m_viewPortResolution As System.Nullable(Of Dimensions)
    Public Sub New()
        InitializeWindow()
    End Sub
    Public ReadOnly Property AnonymousClientId() As String Implements IPlatformInfoProvider.AnonymousClientId
        Get
            Return Me.m_anonymousClientId
        End Get
    End Property
    Public ReadOnly Property ScreenColors() As System.Nullable(Of Integer) Implements IPlatformInfoProvider.ScreenColors
        Get
            Return Me.m_screenColors
        End Get
    End Property
    Public ReadOnly Property ScreenResolution() As System.Nullable(Of Dimensions) Implements IPlatformInfoProvider.ScreenResolution
        Get
            Return Me.m_screenResolution
        End Get
    End Property
    Public ReadOnly Property UserAgent() As String Implements IPlatformInfoProvider.UserAgent
        Get
            Return Me.m_userAgent
        End Get
    End Property
    Public ReadOnly Property UserLanguage() As String Implements IPlatformInfoProvider.UserLanguage
        Get
            Return Me.m_userLanguage
        End Get
    End Property
    Public ReadOnly Property ViewPortResolution() As System.Nullable(Of Dimensions) Implements IPlatformInfoProvider.ViewPortResolution
        Get
            Return Me.m_viewPortResolution
        End Get
    End Property
    Public Event ScreenResolutionChanged As EventHandler Implements IPlatformInfoProvider.ScreenResolutionChanged
    Public Event ViewPortResolutionChanged As EventHandler Implements IPlatformInfoProvider.ViewPortResolutionChanged
    Public Sub OnTracking() Implements IPlatformInfoProvider.OnTracking
    End Sub
    Private Sub InitializeWindow()
        Me.m_anonymousClientId = "b597d28a-0d6c-42ed-9dcb-f89e98006b37"
        ' Random UUID
        Me.m_screenResolution = New Dimensions(1920, 1080)
        Me.m_userAgent = "Mozilla/5.0 (Windows NT 6.3; WOW64; Trident/7.0; rv:11.0) like Gecko"
        Me.m_userLanguage = "en-us"
        Me.m_viewPortResolution = New Dimensions(1920, 1080)
    End Sub
End Class

```` 



{{endregion}}

You can then use this provider in your custom implementation of the **ITraceMonitor** interface. Please note that you have to pass your own **Google Analytics tracking ID** in the **CreateTracker** method of the **TrackerManager**.

#### Custom ITraceMonitor Implementation

{{source=..\SamplesCS\Analytics\AnalyticsForm.cs region=CustomITraceMonitorImplementation}} 
{{source=..\SamplesVB\Analytics\AnalyticsForm.vb region=CustomITraceMonitorImplementation}}
````C#
public class CustomAnalitycsMonitor : ITraceMonitor
{
    private Tracker tracker;
    public CustomAnalitycsMonitor()
    {
        this.CreateGoogleTracker();
    }
    public void CreateGoogleTracker()
    {
        var trackerManager = new TrackerManager(new PlatformInfoProvider());
        tracker = trackerManager.CreateTracker("YOUR_PROPERTY_ID"); // your GoogleAnalytics property ID goes here
        tracker.AppName = "WinForms App";
    }
    public void TrackAtomicFeature(string feature)
    {
        string category;
        string eventAction;
        this.SplitFeatureName(feature, out category, out eventAction);
        var data = HitBuilder.CreateCustomEvent(category, eventAction + " event", feature.ToString(), 1).Build();
        tracker.Send(data);
    }
    public void TrackError(string feature, Exception exception)
    {
        var data = HitBuilder.CreateException(feature + ":" + exception.ToString(), true).Build();
        tracker.Send(data);
    }
    public void TrackFeatureCancel(string feature)
    {
        string category;
        string eventAction;
        this.SplitFeatureName(feature, out category, out eventAction);
        var data = HitBuilder.CreateCustomEvent(category, eventAction + " event.Cancelled", feature.ToString(), 1).Build();
        tracker.Send(data);
    }
    public void TrackFeatureStart(string feature)
    {
        // Measuring timings provides a native way to measure a period of time in Google Analytics. 
        // This can be useful to measure resource load times, for example.
        TimeSpan ts = TimeSpan.FromSeconds(2.2);
        var loadTiming = HitBuilder.CreateTiming("Loaded", "MainWindow", ts).Build();
        tracker.Send(loadTiming);
    }
    public void TrackFeatureEnd(string feature)
    {
        TimeSpan ts = TimeSpan.FromSeconds(2.2);
        var unLoadTiming = HitBuilder.CreateTiming("Loaded", "MainWindow", ts).Build();
        tracker.Send(unLoadTiming);
    }
    public void TrackValue(string feature, long value)
    {
        string category;
        string eventAction;
        this.SplitFeatureName(feature, out category, out eventAction);
        var data = HitBuilder.CreateCustomEvent(category, eventAction + " event", feature.ToString(), value).Build();
        tracker.Send(data);
    }
    private void SplitFeatureName(string feature, out string category, out string eventAction)
    {
        string[] parameters = feature.Split('.');
        category = parameters[0];
        eventAction = parameters[1];
    }
}

````
````VB.NET
Public Class CustomAnalitycsMonitor
    Implements ITraceMonitor
    Private tracker As Tracker
    Public Sub New()
        Me.CreateGoogleTracker()
    End Sub
    Public Sub CreateGoogleTracker()
        ' Random UUID
        Dim trackerManager = New TrackerManager(New PlatformInfoProvider())
        tracker = trackerManager.CreateTracker("YOUR_PROPERTY_ID")
        ' your GoogleAnalytics property ID goes here
        tracker.AppName = "WinForms App"
    End Sub
    Public Sub TrackAtomicFeature(feature As String) Implements ITraceMonitor.TrackAtomicFeature
        Dim category As String
        Dim eventAction As String
        Me.SplitFeatureName(feature, category, eventAction)
        Dim data = HitBuilder.CreateCustomEvent(category, eventAction & Convert.ToString(" event"), feature.ToString(), 1).Build()
        tracker.Send(data)
    End Sub
    Public Sub TrackError(feature As String, exception As Exception) Implements ITraceMonitor.TrackError
        Dim data = HitBuilder.CreateException((feature & Convert.ToString(":")) + exception.ToString(), True).Build()
        tracker.Send(data)
    End Sub
    Public Sub TrackFeatureCancel(feature As String) Implements ITraceMonitor.TrackFeatureCancel
        Dim category As String
        Dim eventAction As String
        Me.SplitFeatureName(feature, category, eventAction)
        Dim data = HitBuilder.CreateCustomEvent(category, eventAction & Convert.ToString(" event.Cancelled"), feature.ToString(), 1).Build()
        tracker.Send(data)
    End Sub
    Public Sub TrackFeatureStart(feature As String) Implements ITraceMonitor.TrackFeatureStart
        ' Measuring timings provides a native way to measure a period of time in Google Analytics. 
        ' This can be useful to measure resource load times, for example.
        Dim ts As TimeSpan = TimeSpan.FromSeconds(2.2)
        Dim loadTiming = HitBuilder.CreateTiming("Loaded", "MainWindow", ts).Build()
        tracker.Send(loadTiming)
    End Sub
    Public Sub TrackFeatureEnd(feature As String) Implements ITraceMonitor.TrackFeatureEnd
        Dim ts As TimeSpan = TimeSpan.FromSeconds(2.2)
        Dim unLoadTiming = HitBuilder.CreateTiming("Loaded", "MainWindow", ts).Build()
        tracker.Send(unLoadTiming)
    End Sub
    Public Sub TrackValue(feature As String, value As Long) Implements ITraceMonitor.TrackValue
        Dim category As String
        Dim eventAction As String
        Me.SplitFeatureName(feature, category, eventAction)
        Dim data = HitBuilder.CreateCustomEvent(category, eventAction & Convert.ToString(" event"), feature.ToString(), value).Build()
        tracker.Send(data)
    End Sub
    Private Sub SplitFeatureName(feature As String, ByRef category As String, ByRef eventAction As String)
        Dim parameters As String() = feature.Split("."c)
        category = parameters(0)
        eventAction = parameters(1)
    End Sub
End Class

```` 



{{endregion}}

All that is left is to set the static **ControlTraceMonitor.AnalyticsMonitor** property, possibly in the constructor of your application.

#### Set AnalyticsMonitor

{{source=..\SamplesCS\Analytics\AnalyticsForm.cs region=ITraceMonitorInstance}} 
{{source=..\SamplesVB\Analytics\AnalyticsForm.vb region=ITraceMonitorInstance}}
````C#
ControlTraceMonitor.AnalyticsMonitor = new CustomAnalitycsMonitor();

````
````VB.NET
ControlTraceMonitor.AnalyticsMonitor = New CustomAnalitycsMonitor()

```` 



{{endregion}}

If you then go to the Google Analytics dashboard after some user interaction has took place, you will find information and statistics for the registered features similar to the ones shown below.

>caption Figure 1: Google Analytics Dashboard 
![Google Analytics Dashboard](images/google-analytics-dashboard.png)

# See Also

* [Analytics Support]({%slug winforms/analytics/analytics-support%})
