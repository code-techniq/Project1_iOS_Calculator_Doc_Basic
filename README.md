# iOS_Calculator_Tutorial

This will be a beginner's tutorial for making Application on the iPhone. Not all concepts will be explained in detail, so if you have anything you don't understand, don't worry, it's normal.



We are going to create an Application in which we will perform basic some calculations of maths. We can say it a calculator.This is how Main part looks like.

<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/Calculator.png">

# First step: Setting up 
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

After adding the button, We can coustmize that button. Like we can change It's text, font, font color etc from Attributes Inspetcor. All the numeric buttons has font style **Helvetica Light**, font size **30.0** and background color **E6E6E6**(Hex Color). All the math operations buttons has font style **Helvetica Light**, font size **30.0** and background color **FF8000**(Hex Color). Add more buttons to **View Controller** and coustmize that according to your Design. After that add a UILabel to show the result and same as buttons you can coustmize the UILable also from Attributes Inspetcor. It looks like as follows.

<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/7.png">

# Third step: Setup constraint layout(Auto Layout)

Auto Layout is a constraint-based layout system. It allows developers to create an adaptive interface that responds appropriately to changes in screen size and device orientation. Without using Auto Layout, it would be very hard for you to build an app that supports all screen sizes.

Auto Layout is a way that lets developers create user interface by defining relationships between elements. It provides a flexible and powerful system that describes how views and the UI controls relate to each other. By using Auto Layout, you can get an incredible control over layout, with a wide range of customization, and yield the perfect interface.

There is button **Add new Constraints** at the bottom. Click on that button and add new constraints. In this tutorial we use four type of constraints on buttons like Left alignment, Right alignment, Bottom alignment and Top alignment. Let's took the example of button **0**. See attached image 

<p float="center">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/8.png" width="70%" height="50%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/9.png" width="70%" height="50%">
</p>
that's the way to add the constraints. Now think that how can you use autolayout for whole UI part. It's time to Show your creativity 👍


# Fourth step: Coding Part 
Now It's time write some logic to create the math calculation. It include multiple things like Declaring variables, Create functions, Make buttons clickable etc. So Let's start 


There is ViewController.swift class in which we will write all the code. see in attached image.

<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/10.png">

Now connect the UILabel to ViewController.swift. We call it **@IBoutlet**. So next question arise in your mind that **What is IBoutlet?**
**IBOutlets** are used for referencing something that's on the storyboard. Let's say there's a label on the storyboard that needs to be access in the code, you can control drag it onto the associated viewcontroller class file.
To connect the label to ViewController.swift class, there is a button on the top named **Adjust Editor Opetion**. Click on it and choose 3rd option **Assistant**. ViewController class opens in a new window along with storyboard. Now Right click on Label and drag to ViewController class as shown in image. We named it as **lblResult**. Now you can access the label in ViewController class.

<p float="center">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/11.png" width="45%" height="45%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/12.png" width="45%" height="45%">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/13.png" width="45%" height="45%">
</p>

We have given a Tag (Unique ID) to every button so that we can  get the specific operation of that clicked button. With the use of Tag we can identify that which button has pressed. Like in given image we have set Tag 1 for button 0, 2 for button 1, 3 for button 2 and so on..

<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/14.png">



Now Declare 4 variables in ViewController Class that helps us to perform the logic.

```
    var numberOnScreen:Double = 0 // current number display on label
    var previousNumber:Double = 0 // Store previous number
    var performingMath = false // bool will use to perform the math operations
    var operation = 0 // Math operation which need to perform on the numbers
```

 make an @IBAction to get the click event of the numbers buttons. Now a question arise in your mind that **What is @IBAction ?**
 @IBAction – a special method triggered by user-interface objects. Interface Builder recognizes them. 
 To make an IBAction perform the same way that we follow to make the IBOutlet. 
 
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/15.png">
 
Now Connect all the numeric buttons with same IBAction. Click on the **Connections Inspector** and then drag a line to ViewControllerScene to connect the selected numeric button with **ClickNumbers**.


<p float="center">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/16.png" width="70%" height="70%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/17.png" width="70%" height="70%">
  
</p>
 
