---
layout: post
title: Xamarin Forms WPF - Quick Start
---

This walkthrough demonstrates how to create an application with Xamarin Forms for WPF. 

The Xamarin Forms WPF platform is available on nightly build. See this tutorial to access to nighlty build : https://blog.xamarin.com/try-the-latest-in-xamarin-forms-with-nightly-builds/

## Create Xamarin Forms Project

1. In Visual Studio, click File > New > Project ... to create a new project:
![Stat Visual Studio](/images/start.png)

2. In the New Project dialog, click Cross-Platform, select the Cross Platform App (Xamarin.Forms or Native) template, set the Name and Solution name to HelloWPF, choose a suitable location for the project and click the OK button:
![New Project](/images/newproject.png)

3. In the New Cross Platform App dialog, click Blank App, select Xamarin.Forms as the UI Technology, select Portable Class Library (PCL) as the Code Sharing Strategy, and click the OK button:
You can select the platforms you want. This interface does not allow to add the WPF platform automatically. We will add it manually later.
![New Cross Platform](/images/newcrossplatform.png)

## Add WPF project

4. In Visual add a new WPF project in your solution. 
![Create WPF Project](/images/newwpfproject.png)

5. The result...

![Solution view](/images/solutionview.png)

6. Open the "Nuget panel" by going to Tools > NuGet Package Manager -> Manage nuget packages for the solution.
  - Click on Update 
  - Select the source package : Xamarin Forms Nightly
  - Install the latest preview in all project (see image)

![Nuget](/images/nugetmaj.png)
  
7. Install Xamarin.Forms.WPF package

![Install WPF package](/images/wpfnugetpackage.png)

8. 


