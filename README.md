# iOS_Calculator_Tutorial
This will be a beginner's tutorial for making an application on the iPhone. Not all concepts will be explained in detail, so if you have anything you don't understand, don't worry, it's normal.
We are going to create an application in which we will perform some basic calculations of math. We can say it is a calculator.  This is how the main part looks like.
<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/Calculator.png">
# First step: Setting up 
Let's start from the beginning.  Click on the Xcode app.  Currently, the latest one available on the app store is Xcode 11.1 so make sure that is the one you have. This should show up.  Click on "create a new Xcode project."
<p float="center">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/1.png" width="45%" height="45%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/2.png" width="45%" height="45%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/3.png" width="45%" height="45%">
</p>
Select **single view application** then fill in the app's name.  We will creatively name it "Calculatordemo".  Make sure the language is set to swift and user interface should be **Storyboard**.  Don't worry about the other fields.
Before we change anything, run the app on the simulator by pressing the "play" button on top of the xcode window. Let's get started.
As you can see in the first screenshot, we would like to have the app be only used in potrait mode and only for iPhone so let's make sure it can't be used in landscape mode and iPad by unchecking these boxes: 
<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/4.png">
## Second step: Creating the UI Part
Let’s start with the UI design of the calculator. In Calculator UI design basically we will use UIButtons to perform the specific task and UILabel to show the result.
Just go to the Main.Storyboard file and start designing your app. There is a view in Main.Storyboard named **View Controller Scene**. This class is the main view of the application that the user interacts with. You can see a **+** button on the top.  Click on that button.  A small window will pop up, in which all the design elements are available. Search for the UIButton and drag and drop the button to the View Controller. The View should look like this:
<p float="center">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/6.png" width="50%" height="50%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/5.png" width="50%" height="50%">
</p>
After adding the button, we can customize that button. Like we can change its text, font, font color etc. from the attributes inspector. All the numeric buttons have font style **Helvetica Light**, font size **30.0** and background color **E6E6E6**(Hex Color). All the math operation buttons have font style **Helvetica Light**, font size **30.0** and background color **FF8000**(Hex Color). Add more buttons to **View Controller** and customize that according to your design. After that, add a UILabel to show the result and, same as the buttons, you can customize the UILabel also from the attributes inspector. It looks like this.
<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/7.png">
# Third step: Set up constraint layout (Auto Layout)
Auto Layout is a constraint-based layout system. It allows developers to create an adaptive interface that responds appropriately to changes in screen size and device orientation. Without using Auto Layout, it would be very hard for you to build an app that supports all screen sizes.
Auto Layout is a way that lets developers create a user interface by defining relationships between elements. It provides a flexible and powerful system that describes how views and the UI controls relate to each other. By using Auto Layout, you can get incredible control over layout, with a wide range of customization, and yield the perfect interface.
There is a button **Add new Constraints** at the bottom. Click on that button and add new constraints. In this tutorial we use four types of constraints on buttons like Left Alignment, Right Alignment, Bottom Alignment and Top Alignment. Let's take the example of button **0**. See the attached image:
<p float="center">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/8.png" width="70%" height="50%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/9.png" width="70%" height="50%">
</p>
that's the way to add the constraints. Now think that how can you use autolayout for whole UI part. It's time to Show your creativity 👍
# Fourth step: Coding Part 
Now it's time to write some logic to create the math calculation. It includes multiple things like declaring variables, creating functions, making buttons clickable etc. So let's start.
There is the ViewController.swift class in which we will write all the code.  See the attached image:
<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/10.png">
Now connect the UILabel to ViewController.swift. We call it **@IBoutlet**. So next question arise in your mind that **What is IBoutlet?**
**IBOutlets** are used for referencing something that's on the storyboard. Let's say there's a label on the storyboard that needs to be access in the code, you can control drag it onto the associated viewcontroller class file.
To connect the label to ViewController.swift class, there is a button on the top named **Adjust Editor Opetion**. Click on it and choose 3rd option **Assistant**. ViewController class opens in a new window along with storyboard. Now Right click on Label and drag to ViewController class as shown in image. We named it as **lblResult**. Now you can access the label in ViewController class.
<p float="center">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/11.png" width="45%" height="45%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/12.png" width="45%" height="45%">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/13.png" width="45%" height="45%">
</p>
We have given a Tag (Unique ID) to every button so that we can get the specific operation of that clicked button. With the use of Tag we can identify which button has been pressed. Like in the given image, we have set Tag 1 for button 0, 2 for button 1, 3 for button 2 and so on...
<img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/14.png">
Now declare 4 variables in the ViewController Class that helps us to perform the logic.
```
    var numberOnScreen:Double = 0 // current number display on label
    var previousNumber:Double = 0 // Store previous number
    var performingMath = false // bool will use to perform the math operations
    var operation = 0 // Math operation which need to perform on the numbers
```
 Make an @IBAction to get the click event of the number buttons. Now a question arises in your mind - **What is an @IBAction?**
 @IBAction – a special method triggered by user-interface objects. Interface Builder recognizes them. 
 To make an IBAction, perform it in the same way as the IBOutlet. 
 
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/15.png">
 
Now connect all the numeric buttons with same IBAction. Click on the **Connections Inspector** and then drag a line to ViewControllerScene to connect the selected numeric button with **ClickNumbers**.
<p float="center">
  <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/16.png" width="70%" height="70%">
 <img src="https://github.com/code-techniq/Project1_iOS_Calculator_Doc/blob/master/ScreenShots/17.png" width="70%" height="70%">
  
</p>
 
 Now write some logic inside the IBAction to display the clicked numeric button value on the Label and store the value in a variable.
```
@IBAction func ClickNumbers(_ sender: UIButton) {
        if performingMath == true
        {
            lblResult.text = String(sender.tag-1)
            numberOnScreen = Double(lblResult.text!)!
            performingMath = false
        }
        else
        {
            lblResult.text = lblResult.text! + String(sender.tag-1)
            numberOnScreen = Double(lblResult.text!)!
        }
    }
  ```
    
It's time to perform some math operations. For this, create another action which performs the math operations logic. Connect the operations button, **+** and **=**, with the new @IBAction and write logic inside it.  We have given a Tag value for both the operations button like **+ has tag value 15** and **= has tag value 16**.
```
@IBAction func ClickOperations(_ sender: UIButton)
        {
            if lblResult.text != "" && sender.tag != 16 //Validation {
                previousNumber = Double(lblResult.text!)! //Store previous number 
              
                 if sender.tag == 15 { // Display Plus on Label
                    lblResult.text = "+"
                }
                operation = sender.tag // Store operation tag value
                performingMath = true
            }
            else if sender.tag == 16 {
               if operation == 15 {  //15 Tag value is for + operation
                    lblResult.text = String(previousNumber + numberOnScreen) // Addition of numbers
                }
            }
    }
 ```
    
  
 The above code is performing only one operation. Now show your creativity and complete the basic calculator.👍
