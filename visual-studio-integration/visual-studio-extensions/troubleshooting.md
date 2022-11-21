---
title: Troubleshooting
page_title: Troubleshooting - UI for WinForms Documentation
description: Troubleshooting
slug: winforms/installation-deployment-and-distribution/visual-studio-extensions/troubleshooting
tags: troubleshooting 
published: True
position: 10
---

# Troubleshooting

## 

*Problem:*

**Missing Telerik menu in Visual Studio**

*Reason:*

Telerik Visual Studio Extensions are disabled or not installed correctly.

*Suggested solution 1(Extension is Disabled):*

* Open Visual Studio;

* Go to menu Tools - > Extensions and Updates...(for Visual Studio 2019 Extensions - > Manage Extensions)

* Open the Installed tab on the left​

* Search for Telerik WinForms VSExtensions and make sure they are Enabled

![vsextensions-disabled](images/vsextensions-disabled.png)

*Suggested solution 2(Extension is not installed):*

* Open Visual Studio;

* Go to menu Tools - > Extensions and Updates...(for Visual Studio 2019 Extensions - > Manage Extensions)

* Open the Online tab on the left​

* Search for Telerik WinForms VSExtensions

* Download and install the extensions


>important If the article does not help solving your problem, please follow these steps to generate Visual Studio [ActivityLog](https://docs.microsoft.com/en-us/visualstudio/ide/reference/log-devenv-exe?view=vs-2019) file before contacting our support:
>* Open [Developer Command prompt](https://docs.microsoft.com/en-us/dotnet/framework/tools/developer-command-prompt-for-vs) for Visual Studio 20xx under **Administrative rights**.
>* Execute the command - devenv /log %userprofile%\desktop\ActivityLog.xml . This will start Visual Studio and create logs on your Desktop.
>* Reproduce the problem
>* Attach the **Activitylog** files when you contact our support.
