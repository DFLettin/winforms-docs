---
title: How to Use ToastNotification in .NET Core/.NET 5  
description: Learn how to use ToastNotification .NET Core/.NET 5. 
type: how-to
page_title: How to Use ToastNotification in .NET Core/.NET 5   
slug: toast-notification-in-net-core
position: 0
tags: net, core, toast, notification
res_type: kb
---

## Environment
 
|Product Version|Product|Author|
|----|----|----|
|2021.2.615|UI for WinForms|[Desislava Yordanova](https://www.telerik.com/blogs/author/desislava-yordanova)|
 
## Description

This tutorial aims to show how to use [ToastNotification]({%slug toast-notification-getting-started%}) in a .NET 5 application.

## Solution

Please follow the steps:

1\. Select the Target Framework to be .NET 5:

![winforms/toast-notification-in-net-core001](images/toast-notification-in-net-core001.png) 

2\. Install the **UI.for.WinForms.RadToastNotification** NuGet:

![winforms/toast-notification-in-net-core002](images/toast-notification-in-net-core002.png)

![winforms/toast-notification-in-net-core003](images/toast-notification-in-net-core003.png)
 
3\. Double click the project file and update the TargetFramework. Your project should also targets **net5.0-windows10.0.17763**:

````xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows10.0.17763</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
    <ApplicationManifest>app.manifest</ApplicationManifest>
  </PropertyGroup>
  

  <ProjectExtensions><VisualStudio><UserProperties ShouldAddDPIScalingManifest="True" /></VisualStudio></ProjectExtensions>
  

  <ItemGroup>
    <PackageReference Include="UI.for.WinForms.RadToastNotification" Version="2021.2.615" />
  </ItemGroup>   

</Project>

````

4\. Then, you can drag the RadToastNotificationManager from the toolbox and drop it on the components tray:

![winforms/toast-notification-in-net-core004](images/toast-notification-in-net-core004.png)

# See Also

* [ToastNotification]({%slug toast-notification-getting-started%}) 
