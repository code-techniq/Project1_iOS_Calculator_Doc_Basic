# iOS_Calculator_Tutorial

This will be a beginner's tutorial for making Application on the iPhone. Not all concepts will be explained in detail, so if you have anything you don't understand, don't worry, it's normal.



We are going to create an Application in which we will perform basic some calculations of maths. We can say it a calculator.This is how Main part looks like.

<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/Calculator.png">

## First step: Setting up 
Let's start from the start, click on Xcode app, currently, the latest one available on the app score is Xcode 11.1 so make sure that is the one you have. This should show up, click on create a new Xcode project

<p float="center">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/1.png" width="45%" height="45%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/2.png" width="45%" height="45%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/3.png" width="45%" height="45%">
</p>

Select **single view application** then fill in the App's name, we will creatively name it "Calculatordemo", make sure the language is set to swift and user interface should be **Storyboard**. Don't worry about the other fields.
Before we change anything, run the app on the simulator by pressing the "play" button on top of xcode window. Let's get started.

As you can see in the first screenshot, we would like to have the app be only on potrait mode and only for iPhone So let's make sure it can't be used in landscape mode and iPad by unchecking this boxes: 

<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/4.png">

## Second step: Creating UI Part

Let’s start with UI design of Calculator. In Calculator UI design basically we will use UIButtons to perform the specific task and UILabel to show the result.
Just go the Main.Storyboard file and start design your App. There is a view in Main.Storyboard named **View Controller Scene**. This class is main view of the Application that intract with the user. As you see a **+** button on the top,  click on that button. A small window pop up, in which all the design elements avaialble. Search for the UIButton and drag drop the button on View Controller. The View is look like as follows:

<p float="center">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/6.png" width="50%" height="50%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/5.png" width="50%" height="50%">
</p>

After adding the button, We can coustmize that button. Like we can change It's text, font, font color etc from Attributes Inspetcor. Add more buttons to **View Controller** and coustmize that according to your Design. and It looks like as follows.

<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/7.png">
