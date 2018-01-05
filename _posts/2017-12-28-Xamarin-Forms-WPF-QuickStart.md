---
layout: post
title: Xamarin Forms WPF - Quick Start
---

This walkthrough demonstrates how to create an application with Xamarin Forms for WPF. 

The Xamarin Forms WPF platform is available on nightly build. [Click here to read the tutorial about "How to access to nighlty build"](https://blog.xamarin.com/try-the-latest-in-xamarin-forms-with-nightly-builds/)

## Create Xamarin Forms Project

- In Visual Studio, click File > New > Project ... to create a new project:
![Stat Visual Studio](/images/start.png)

- In the New Project dialog, click Cross-Platform, select the Cross Platform App (Xamarin.Forms or Native) template, set the Name and Solution name to HelloWPF, choose a suitable location for the project and click the OK button:
![New Project](/images/newproject.png)

- In the New Cross Platform App dialog, click Blank App, select Xamarin.Forms as the UI Technology, select Portable Class Library (PCL) as the Code Sharing Strategy, and click the OK button:
You can select the platforms you want. This interface does not allow to add the WPF platform automatically. We will add it manually later.
![New Cross Platform](/images/newcrossplatform.png)

## Add WPF project

- In Visual add a new WPF project in your solution. 
![Create WPF Project](/images/newwpfproject.png)

- The result...

![Solution view](/images/solutionview.png)

- Open the "Nuget panel" by going to Tools > NuGet Package Manager -> Manage nuget packages for the solution.
  - Click on Update 
  - Select the source package : Xamarin Forms Nightly
  - Install the latest preview in all project (see image)

![Nuget](/images/nugetmaj.png)
  
- Install Xamarin.Forms.WPF package
![Install WPF package](/images/wpfnugetpackage.png)

- Add Resource in App.xaml (WPF Project)

```C#
<Application x:Class="HelloWPF.WPF.App"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:local="clr-namespace:HelloWPF.WPF"
             StartupUri="MainWindow.xaml">
    <Application.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="/WPFLightToolkit;component/Assets/Default.xaml" />
            </ResourceDictionary.MergedDictionaries>

            <!-- Default Global Color -->
            <SolidColorBrush x:Key="WindowBackgroundColor" Color="White" />
            <SolidColorBrush x:Key="AccentColor" Color="#3498db" />

            <!-- Default Command Bar Color -->
            <SolidColorBrush x:Key="CommandBarBackgroundColor" Color="#3498db" />
            <SolidColorBrush x:Key="CommandBarTextColor" Color="White" />

            <!-- Default Title Bar Color -->
            <SolidColorBrush x:Key="DefaultTitleBarBackgroundColor" Color="#3498db" />
            <SolidColorBrush x:Key="DefaultTitleBarTextColor" Color="White" />

            <!-- Default Tabbed Bar Color -->
            <SolidColorBrush x:Key="DefaultTabbedBarBackgroundColor" Color="#3498db" />
            <SolidColorBrush x:Key="DefaultTabbedBarTextColor" Color="White" />

        </ResourceDictionary>
    </Application.Resources>
</Application>
```

- Update MainWindow.xaml 

```C#
<wpf:FormsApplicationPage x:Class="HelloWPF.WPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:wpf="clr-namespace:Xamarin.Forms.Platform.WPF;assembly=Xamarin.Forms.Platform.WPF"
        mc:Ignorable="d"
        WindowState="Normal" 
        Title="Hello WPF" >
 
</wpf:FormsApplicationPage>
```

- Update MainWindow.cs

```C#
using Xamarin.Forms.Platform.WPF;

namespace HelloWPF.WPF
{
	/// <summary>
	/// Logique d'interaction pour MainWindow.xaml
	/// </summary>
	public partial class MainWindow : FormsApplicationPage
	{
		public MainWindow()
		{
			InitializeComponent();
			Xamarin.Forms.Forms.Init();
			LoadApplication(new HelloWPF.App());
		}
	}
}
```

## Run it

![Started](/images/hellowpfstarted.png)

## Known Issues

This is a Preview, so you should expect that not everything is production ready. Below are a few things you may encounter as you add WPF to your projects.

#### Not All NuGets are Ready for WPF
In order to work in a WPF project, packages must target net45. You may find that some of your beloved libraries do not yet support WPF. What can you do? Kindly send a request to the project’s maintainer to add it. Until they have support, you may need to look for alternatives.

#### Xamarin.Forms Features
This preview has amazing coverage of Xamarin.Forms UI and features, but there are some known gaps to be aware of.

Not Yet Implemented:
* Accessibility
* TimePicker
* List (Lot of work)
* NativeViewWrapper
* NavigationMenu

## Send Your Feedback!
Add a WPF project to your solutions today and let us know what you think. What do you feel is missing? What problems do you encounter?

[Click here for the github link of this project](https://github.com/mohachouch/HelloWPF.git)

