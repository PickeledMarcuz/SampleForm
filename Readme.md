# Description
Short Xamarin form application for demonstrating how to create a Xamarin.Froms application using simple UI written in C# instead of XAML. The idea being to demonstrate basic uses of layout and objects needed to form an application view. 
 
To allow everyone regardless of using MAC or Windows as the development environment to participate using this guide we will focus on creating an Android application. The other options are UWP for Windows and iOS for Apple. 
 
*** An Apple Mac with XCode installed is required for building an iOS application.
 
## Step 1
Create a Xamarin application in Visual studio 2017 or Visual studio Mac. 
 
 
 
Select File > New > Project.
Or use the short keys on windows Ctrl + Shift + N
 
## Step 2
Visual Studio 2017 has an extensive amount of project types to pick from. We will be focusing on "Cross Platform" applications under the Visual C# tab as seen in this picture
 
 
 
The "Name" and "Solution name" are by default the same name. Location is just where you will store this project and associated files. Since during the cross-platform course we are making use of GitHub I recommend ticking the "Create new Git repository" box in order to not have to do this manually. 
 
## Step 3
The final step in creating the application is to select the type of Xamarin.Froms we will use:
1.	Xamarin.Froms as the UI technology
2.	Code sharing in a "Shared project"
 
 
 
When you click ok 4 projects will be created in your solution one for each platform as well as a shared code in this case the shared code is named "SampleForm". This is seen in the image on the left. 
 
 
The other platforms (UWP and iOS) can be used with this guide by changing the startup project to another platform. Right click on it and select "set as StartUp Project. 
 
 
*** The iOS project will require an Apple MAC with XCode installed in order to compile. 
 
All our shared code will be placed within the "SampleForm" application. In the righthand side picture we can see the folder structure of our "SampleForm" and "SampleForm.Android" application. 
 
The Main entry point for all Xamarin applications is in App.xaml.cs. This file is where starting, stopping and resuming is controlled by your application. The code contained in the app.xaml.cs should match the following:
 
<code>
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
 
using Xamarin.Forms;
 
namespace SampleForm
{
public partial class App : Application
{
public App ()
{
InitializeComponent();
 
MainPage = new SampleForm.MainPage();
}
 
protected override void OnStart ()
{
// Handle when your app starts
}
 
protected override void OnSleep ()
{
// Handle when your app sleeps
}
 
protected override void OnResume ()
{
// Handle when your app resumes
}
}
}
</code>
The App class inherits from the Application class and is what we use when our Xamarin application starts. More in-depth details can be found here. The MainPage.xaml.cs is where the UI for our application is located. The .cs means C# file on both the App.xaml and MainPage.xaml. XAML is the UI language we can use to describe our layouts. 
 
## Step 4
Now that our application is setup we can test it by running the application. If you own an Android phone with minimum version 4.4 (KitKat) then it can be used to install the application directly on the device you own via USB. Follow this guide to enable developer mode on your device. 
 
Android by default comes with emulators installed for you to start an android instance within your computer. The standard emulators from Google can be quite slow on initial startup. To speed this process up Microsoft have created "Visual Studio Emulator for Android" which I recommend you download and install before running the application initially.
 
Install found here
 
Open the Visual Studio Emulator for Android selection window and you will be presented with a list of the most common devices that will be used
 
 
In this tutorial, we will use the "5" KitKat (4.4) XXHDPI Phone" which is similar to a Samsung S5/Sony Xperia Z. To start the emulator, click on the green start icon in the menu. This emulator requires 2GB of RAM to start. If this is not possible on your computer then browse the list to find one with lower requirements. After starting you will be presented with an emulated device on your computer.
 
 
Move back to Visual studio and we can now run the Xamarin application by selecting either the device plugged in via USB or the emulator we have just installed. If the emulator is not visible restart Visual studio to allow the changes take effect. 
 
 
 
After running the application for the first time you will be presented with the screen shown below. It isn't very exciting so let's spice it up a little with some of the UI elements we can use in Xamarin.
 
 
## Step 5
Our application is setup, the emulator is installed and we are no ready to make changes to the code. As stated at the beginning we will build this application using C# instead of XAML but for the sake of showing it lets look at the XAML code where the phrase "Welcome to Xamarin Forms!" is located. Open the file MainPage.xaml. The code seen should be the same as below.
<code>
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:SampleForm"
             x:Class="SampleForm.MainPage">
 
<Label Text="Welcome to Xamarin Forms!" 
           VerticalOptions="Center" 
           HorizontalOptions="Center" />
 
</ContentPage>
</code>

This code in the MainPage.xaml resembles HTML and it does actually follow how extensible markup languages like XML and HTML are used. XAML is short for extensible application markup language and is what we use for describing a layout. In short the code actually is an opening tag known as <ContentPage> and closing tag of </ContentPage> . Apart from the schema attributes in the opening <ContentPage> tag the only other element inside it is the Label which has the value "Welcome to Xamarin Forms!". 
 
Feel free to review the documentation found here about xaml to experiment with layouts. After making changes be sure to stop the current debug session and start a new build in order to deploy fresh changes to your device/emulator. When finished experimenting delete the MainPage.xaml and MainPage.xaml.cs from your solution explorer (If you delete the MainPage.xaml first it will also delete the MainPage.xaml.cs). We will create a new file in the next step.
 
## Step 6
 
 

