---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Ryo Imahashi'

page_number: true
paginate: true
---

**Programming Boot Camp**

# Adalo Basics

**Tokyo Institute of Technology 2021/10/23**
　
　
　
　　　　　　　　　　　　　　　　　　　　　　**Ryo Imahashi**

---
## Table of Contents
  - What is Adalo?
  - Adalo account registration
  - Try template application
  - Overview of application development with Adalo
  - Sample application development
  - Exercise
  - Summary

---
## What is Adalo?
- [Adalo](https://www.adalo.com/) is a no-code tool from the United States. It allows you to develop applications without programming.
- You can create an app by selecting the parts you want to use from those provided and dragging and dropping them onto the screen.
- You can develop not only web apps(to be displayed in a browser), but also smartphone apps for Android and iOS. It is also possible to publish the developed application on Google Play and AppStore.


---
#### Example of apps created with Adalo
- Union: https://union-jp.site/
  - A social networking service limited to undergraduates, graduate students, university faculty and university staff developed by university students.
  - Funding of 10 million yen was raised in 2021.
    - https://prtimes.jp/main/html/rd/p/000000001.000076669.html
- More examples on #MadeInAdalo
  - https://www.adalo.com/made-in-adalo

---
## Adalo account registration
- Go to Adalo's SignUp page.
  - https://app.adalo.com/signup
![w:800px](images/signup.png)

---
- You can register for free!
-  Enter your email address, password and full name.
-  Check the box to agree to the Terms of Use.
- Click the  DO THIS! button to proceed.

---
#### Reference: Limitations of the [Free Plan](https://www.adalo.com/pricing)
- Cannot use external integration with other applications.
  - However, trial use is available for 14 days
- The maximum number of database records is 50.

:white_check_mark:  Consider using a Pro Plan when you actually launch your app.

---
#### Platform Selection
- You can select Native Mobile App or Desktop Web App.
- This time, select Native Mobile App.
![bg 90% right](images/select-native-mobile-app.png)

---
#### Selecting a template
- Finished apps are provided as templates.
- This time, select Chat template.
![bg 90% right](images/select-chat-template.png)


---
#### Branding
- Enter the App Name, Primary Color, and Secondary Color.
  - Primary Color is the base color that will be used most in your app.
  - Secondary Color is the color for important parts (e.g. register button)
![bg 90% right](images/branding-chat-app.png)

---
- When you see Adalo's admin panel like this, you are good to go!
- From now on, we will use this admin panel to develop our application.
![w:900px](images/dev-tool-of-chat-app.png)

---
## Try template application
- First of all,  try to operate the Chat app template to see how the application created by Adalo works.
- Click the Preview button in the upper right corner of the screen

![w:1100px](images/preview-button.png)

---
- The preview screen will be launched.
- Let's operate the Chat application together!
![w:800px](images/chat-app-preview.png)

---
- Sign up.
  -  Enter your Email and Password (remember them so that you can use again later).
![bg 50% right](images/chat-app-signup.png)

---
- The list is empty because no conversation has taken place yet
-  Press the + button at the bottom right of the screen.
![bg 50% right](images/chat-app-no-conversation.png)

---
- It looks like you can't chat because you just created the app and there are no other users.
![bg 50% right](images/no-other-chat-app-user.png)

---
- Let's share the app you created with others and have a conversation with them.
- Close Preview mode with the x button in the upper left corner, and click SHARE in the menu.

![w:1100px](images/share-button.png)

---
- Click on the SHARE APP button and select COPY LINK.
- Post the copied link to Slack so that all students can see it.

![w:800px](images/share-chat-app.png)

---
- Click on a links posted in slack to signup for their app and send them a message.
  - You'll see the creator of the app (and other students) in the list of users!
![bg 50% right](images/start-conversation.png)

---
- (Around the time when the message would have been sent to everyone's apps,)
Display the Preview screen of your app again.
  - You should have received a message, so click on it to check it!
![w:800px](images/preview-got-new-message.png)

---
- Message received :tada:
![bg 50% right](images/messages.png)

---
- In addition to the Chat we tried this time, there are several other templates available.
- If there is one that is similar to the application you want to build, you may be able to use that template to boost your development. When you have time, try out other templates.

---
## Overview of application development with Adalo
Next,  take a look at how to develop an app with Adalo.

---
## Three basic concepts
- Let's learn the following three basic concepts of Adalo.
  - Components
  - Database
  - Actions

--- 
#### Components
- Elements that are placed on the screen to create a user interface.
- Examples:
  - Lists
  - Buttons
  - Text
  - Image
![bg 35% right](images/components.png)

---
#### Database
- A set of organized data.
- Data can be registered, read (displayed), updated, and deleted.
- Example: In the case of a Chat application
![w:400px](images/2021-10-19-23-49-03.png)
![bg 35% right](images/2021-10-19-23-13-47.png)

---
#### Actions
- This is used to specify what to do when a specific component is clicked.
- Example :
  - Transition to another screen.
  - Registering, updating, and deleting data in the database.
![bg 35% right](images/2021-10-19-23-12-42.png)

---
### Explanation of Adalo's functions
Next, take a look at the features available in Adalo's admin panel.
![w:900px](images/dev-tool-of-chat-app.png)

---
#### Canvas
- A work area for creating screens.
- Elements can be selected and moved by dragging and dropping.
![w:680px](images/canvas.png)


---
#### Left Toolbar
Let's learn each function of the left toolbar.

![w:60px](images/left-tool-bar.png)

---
###### ![w:60px](images/add-panel.png) Add Panel
- This allows you to select a component or screen to add to your app.
![bg right 95%](images/2021-10-20-00-37-54.png)
![bg right 93%](images/2021-10-20-00-44-42.png)

---
###### ![w:60px](images/2021-10-20-00-52-07.png) Branding
- You can change colors and fonts.
![bg right 100%](images/2021-10-20-00-50-02.png)
![bg right 92%](images/2021-10-20-00-50-42.png)

---
###### ![w:60px](images/2021-10-20-00-54-44.png) Screens
- List of screens and their configurations.
![bg right 100%](images/2021-10-20-01-18-20.png)
![bg right 93%](images/2021-10-20-01-14-53.png)

---
###### ![w:60px](images/2021-10-20-01-20-56.png) Database
- Displays the structure of the database and the data stored in it.
- Collection: A collection of data that has the same properties.
![w:214px](images/2021-10-20-01-38-57.png) ![w:878px](images/2021-10-20-01-30-09.png)

---
###### ![w:60px](images/2021-10-20-01-45-09.png) Settings 
- You can change the name of the app and set the app's icon.
- You can configure display settings for the canvas.
- You can set access permissions to the app.
- You can copy or delete an app.
![bg right 90%](images/2021-10-20-01-47-47.png)

---
###### ![w:60px](images/2021-10-20-01-56-00.png)Publish
- You can publish your apps (paid plan required).
![bg right 90%](images/2021-10-20-01-59-11.png)

---
###### ![w:60px](images/2021-10-20-02-06-34.png) Analytics
- Show usage analysis report.
![bg right 90%](images/2021-10-20-02-07-44.png)

---
#### Top Bar
Let's learn each function of the top toolbar.

![w:1150px](images/2021-10-20-02-11-14.png)

---
###### App Switcher
- Displays the name of the opened app.
- You can switch to other app.
- New apps can be added.

![bg right 90%](images/2021-10-20-02-27-22.png)


---
###### Preview
- You can run the app and try it out.
- You can switch to devices with different screen sizes to check the display image.
![w:830px](images/2021-10-20-02-42-08.png)

---
###### Share
- You can share the app to get others to use it.
  No Adalo account required to use shared app.
![w:830px](images/2021-10-20-02-44-28.png)

---
###### Account Menu
- Allows you to configure various settings.
- Link to help and documentation.
- Sign Out.
![bg right 90%](images/2021-10-20-02-56-33.png)

---
#### Tips
- If you edit something by mistake, you can undo it with `Ctrl + Z` on Windows or `Command + Z ` on Mac!
- Entering japanese text may not work well with Adalo's development tools. Use copy and paste instead.

---
## Sample application development
Let's create a new application.

- In this lecture, we will create a static site without using a database (the content displayed will remain the same no matter which user accesses the site).
- In the next lecture, we will create a dynamic app using a database (the content displayed will change for each user).

---
#### UI of the sample application
This is a health management application for your pet.
First, check the UI.

![h:383px](images/2021-10-20-06-09-56.png)![h:383px](images/2021-10-20-06-16-03.png)![h:383px](images/2021-10-22-02-23-09.png)![h:384px](images/2021-10-22-02-40-24.png)![h:383px](images/2021-10-22-04-07-06.png)![h:383px](images/2021-10-22-16-42-42.png)


---
###### User Registration Screen
- You can register as a user by entering the following information
  - Email
  - Password
  - Full Name
- For those who have already registered, there is a link to the login screen.
![bg right h:700px](images/2021-10-20-06-09-56.png)

---
###### Login screen
- You can log in by entering the following information
  - Email
  - Password
- There is a link for those who have forgotten their password.
- There is a link to the user registration page.
![bg right h:700px](images/2021-10-20-06-16-03.png)

---
###### Pet Registration Screen
- You can enter your pet's name.
- You can select your pet's photo.
- You can enter your pet's birthday.
- You can click the "Register" button to register your pet and move to the pet list screen.
![bg right h:700px](images/2021-10-22-02-23-09.png)

---
###### Pet List screen
- Registered pets can be displayed in a list.
- Clicking on a pet will take you to the pet details screen for that pet.
- Clicking the icon at the bottom right take you to the Pet Registration screen.
![bg right h:700px](images/2021-10-22-02-40-24.png)

---
###### Pet Detail Screen
- There is a link to the weight Record screen.
(Link2 is for exercise)
- Birthday is displayed.
- The latest weight is displayed.
![bg right h:700px](images/2021-10-22-04-07-06.png)

---
###### Weight Record screen
- A graph showing the transition in weight is displayed.
- You can enter your pet's current weight.
- You can add your pet's weight by pressing the button
![bg right h:700px](images/2021-10-22-16-42-42.png)

---
#### Creating the application
Now, let's start creating the application.

-  select CREATE NEW APP
![bg right 90%](images/2021-10-20-05-31-12.png)

--- 
- Select Native Mobile App !
![bg right 90%](images/select-native-mobile-app.png)

---
-  select Template: Blank
![bg right 90%](images/2021-10-20-05-35-47.png)

---
- Enter App Name and Color as you like.
- Leave Team setting as default.
  (It won't be displayed to people who haven't set up a Team.)
![bg right 90%](images/2021-10-20-05-40-11.png)

---
- The application is ready!
![h:550px](images/2021-10-20-05-45-06.png)

---
###### User registration screen, login screen

User registration screen and login screen are generated by default.
![h:400px](images/2021-10-20-05-53-24.png)

---
Check the preview function to see how they works.

- User Registration Screen
  - When you signup, you will be redirected to the Home screen.
  - You can log out from the icon in the upper right corner of the Home screen.
![bg right h:600px](images/2021-10-20-06-09-56.png)
![bg right h:600px](images/2021-10-20-06-11-03.png)

---
- Login screen
  - Log in with the same Email and Password that you used to register earlier, then you will be redirected to the Home screen.

![bg right h:600px](images/2021-10-20-06-16-03.png)
![bg right h:600px](images/2021-10-20-06-11-03.png)

---
It seems like the registration screen and login screen are fine as they are.
Let's create the other four screens.


---
###### Pet Registration Screen
- You can enter your pet's name.
- You can select your pet's photo.
- You can enter your pet's birthday.
- You can click the "Register" button to register your pet and move to the pet list screen.
Let's create this screen!
![bg right h:700px](images/2021-10-22-02-23-09.png)

---
- Select "App Bar" from ADD SCREEN.
![bg right h:700px](images/2021-10-20-06-26-12.png)

---
- Enter the Screen Name.
![w:900px](images/2021-10-20-06-28-11.png)


---
The Screen has been added.

Let's add components on this screen.

![bg right h:700px](images/2021-10-20-06-37-56.png)

---
- Select "Text" from ADD COMPONENT.
![bg right h:500px](images/2021-10-20-06-47-19.png)

---
- Place it on the screen.
![bg right h:500px](images/2021-10-20-06-49-18.png)

---
- Change the value of "Text" to Name.
![bg right h:500px](images/2021-10-20-06-52-11.png)

---
- Let's put text "Image" and "Birthday" in the same way.
![bg right h:500px](images/2021-10-20-07-02-04.png)

---
- Select "Text Input" from ADD COMPONENT
![bg right h:500px](images/2021-10-20-06-53-05.png)

---
- Place it on the screen and change the "Placeholder" value to "Enter Name"
![bg right h:480px](images/2021-10-20-07-03-27.png)

---
- Select "Image Picker" from ADD COMPONENT.
![bg right h:600px](images/2021-10-20-07-05-23.png)

---
- Place it on the screen.
![bg right h:480px](images/2021-10-20-07-06-54.png)

---
- Select "Date Picker" from ADD COMPONENT.
![bg right h:480px](images/2021-10-20-07-08-35.png)

---
- Place it on the screen and change the Style to "Date Picker".
![bg right h:480px](images/2021-10-20-07-10-35.png)

---
- Select "Button" from ADD COMPONENT.
![bg right h:480px](images/2021-10-20-07-12-13.png)

---
- Place it on the screen.
- Change the "Text" value to Register.
- Change "Button Color" to "Secondary".
- Change the "Icon & Text Color" to "Default Background"(White)

![bg right h:530px](images/2021-10-22-02-19-14.png)

---
Let's check the appearance of the pet registration screen.
- Since there is no link yet, we can't display this screen with screen transitions, so we'll set it to the Home Screen, which is the screen displayed after logging in.
- Change the Screen Navigation Type of Pet Registration screen to Home Screen.
![bg right h:400px](images/2021-10-20-07-28-52.png)

---
- Open Preview. After logging in, you can see the Pet Registration screen.
- You can enter a name, select an image, and select a birthday.
- Nothing happens when you press the Register button yet.

The pet registration screen is done.
![bg right h:700px](images/2021-10-22-02-23-09.png)

---
###### Pet List Screen
- Registered pets can be displayed in a list.
- Clicking on a pet will take you to the pet details screen for that pet.
- Clicking the icon at the bottom right take you to the Pet Registration screen.
![bg right h:700px](images/2021-10-22-02-40-24.png)

Next, let's create this screen.

---
- Select "App Bar" from ADD SCREEN and enter the Screen Name.
![bg right h:700px](images/2021-10-20-06-26-12.png)

---
- Select "Image" from ADD COMPONENT
![bg right h:700px](images/2021-10-21-23-24-54.png)

---
- Place it on the screen.
- Upload a photo of your pet from "Image Source" -> "Upload"
![bg right h:540px](images/2021-10-22-01-08-36.png)

---
- Select "Text" from ADD COMPONENT
![bg right h:500px](images/2021-10-22-00-07-29.png)

---
- Enter your pet's name in "Text" value and change the text color to White.
- Depending on the photo you choose, the white text may be difficult to see, so the next step is to make the text easier to read.
![bg right h:450px](images/2021-10-22-01-10-24.png)

---
- Select "Rectagle" from ADD COMPONENT
![bg right h:500px](images/2021-10-22-01-13-13.png)

---
- Place it over the pet's name.
- After selecting Black as the Background color, change the value of A in RGBA to 10.
  - RGBA is a form of color representation that combines the intensity of each of the three primary colors (Red, Green, and Blue) with a degree of transparency (Alpha).
![bg right h:500px](images/2021-10-22-01-23-50.png)

---
- Select the Pet List screen from Screens, and confirm that Rectangle is above Text in the Components order.
  - The Rectangle is now hiding the Text because the one on top is displayed in front of the other.

![bg right h:500px](images/2021-10-22-01-38-45.png)

--- 
- Let's switch the order, putting Text at the top and Rectangle at the second.
  - The Text is now in the foreground, and the Rectangle makes it easier to see the white text!
![bg right h:500px](images/2021-10-22-01-41-54.png)

---
Next,  display one more pet!
- Select the three components you added (Image, Rectangle, Text) on Canvas, and click MAKE GROUP
![bg right h:500px](images/2021-10-22-01-53-38.png)

---
- Copy and paste (`Ctrl + C` and `Ctrl + V` on Windows, `Command + C` and `Command + V` on Mac) the created Group while it is selected, and place the duplicated Group on the bottom.
![bg right h:700px](images/2021-10-22-02-01-32.png)

---
-  change the second Image and Text to those of another pet!
![bg right h:700px](images/2021-10-22-02-06-16.png)

---
Next, we will add the lead to the pet registration page.
- Select Action Button from ADD COMPONENT
![bg right h:370px](images/2021-10-22-02-11-11.png)

---
- Place it in the lower right corner of the screen.
- Change the Icon and Text Color to Default Background (White).
![bg right h:500px](images/2021-10-22-02-26-03.png)

---
- ADD ACTION -> Link -> Select [Pet Registration Screen Name
![bg right h:500px](images/2021-10-22-02-28-24.png)

---
 add a lead line from the pet registration screen to the pet list screen.
- Select the Register button on the Pet Registration page
- ADD ACTION -> Link -> Select [Pet List Screen Name
You can't register your pets yet because you just added a line (we will do the data registration in the next lecture).
![bg right h:500px](images/2021-10-22-02-33-55.png)

---
-  also change the destination of the SIGNUP button on the SignUp screen and the LOGIN button on the Login screen from Home to the Pet List screen.
![bg right h:340px](images/2021-10-22-03-52-31.png)

---
- The Home screen that was created by default is no longer needed, so  delete it!
![bg right h:480px](images/2021-10-22-03-57-57.png)

---
 check the appearance of the Pet List screen.
- Change the Screen Navigation Type of the Pet List screen to Home Screen as you did when you previewed the Pet Registration screen.
- After logging in with the preview function, you can see the Pet List screen.

Pet List screen seems OK.
![bg right h:650px](images/2021-10-22-02-40-24.png)

---
###### Pet Detail Screen
- There is a link to the weight Record screen.
(Link2 is for exercise)
- Birthday is displayed.
- The latest weight is displayed.

Next, let's create this screen
![bg right h:700px](images/2021-10-22-04-07-06.png)

---
- Select Info with Links from ADD SCREEN and enter the Screen Name
![bg right h:650px](images/2021-10-22-02-58-46.png)

---
- Upload the photo used in the Pet List screen in Image Source.
![bg right h:500px](images/2021-10-22-03-05-37.png)


---
- Rewrite the Text with the label Birthday and its value, and the label Latest Weight and its value!
![bg right h:700px](images/2021-10-22-03-18-32.png)

---
- Let's change the Text named Link 1 to Weihgt Log
- Leave Link 2 as it is.
(Use it as a lead-in to the screen you created in the last exercise time)

![bg right h:700px](images/2021-10-22-03-28-26.png)

---
Let's make it possible to move from the pet list screen to the pet detail screen.
- Select the Group that contains the components for the first pet in the Pet List screen, and click ADD ACTION -> Link -> PetDetail

![bg right h:450px](images/2021-10-22-03-31-30.png)

---
- Let's check the display on the preview screen.

The UI of the pet detail screen is now ready.
![bg right h:700px](images/2021-10-22-04-07-06.png)

---
###### Weight record screen
- A graph showing the transition in weight is displayed.
- You can enter your pet's current weight.
- You can add your pet's weight by pressing the button

Let's create this screen
![bg right h:700px](images/2021-10-22-16-42-42.png)

---
- To create a Chart, we need to prepare a database, which will be explained in the next lecture.
- This time,  paste the Chart image instead using actual chart.
  - I'll share the image with you via Slack.
  (You can also take a screenshot of the image on the right and use it)
![bg right h:350px](images/pet-weight-log-chart.png)

---
- Add an Image from ADD COMPONENT and upload the Chart image!
![bg right h:500px](images/2021-10-22-16-33-13.png)

---
- Add Text Input from ADD COMPONENT
- Change Type to Number.
- Change Placeholder to Enter current weight
![bg right h:500px](images/2021-10-22-16-35-03.png)

---
- Add a Text from ADD COMPONENT
- Change the value to Weight(kg)
![bg right h:500px](images/2021-10-22-16-35-39.png)

---
-  add Button from ADD COMPONENT
-  change Text to Add.
![bg right h:500px](images/2021-10-22-16-36-06.png)

---
 set up a lead line from the pet detail screen to the weight record screen
- Set up a link to the weight record screen with Click Action for the Group containing Text:'Weight Log' in the pet detail screen.
![bg right h:500px](images/2021-10-22-12-40-18.png)

---
-  check the display on the preview screen.

This is the UI for the weight record screen.
![bg right h:700px](images/2021-10-22-16-42-42.png)

---
We have created all UI for the app :tada:

![h:383px](images/2021-10-20-06-09-56.png)![h:383px](images/2021-10-20-06-16-03.png)![h:383px](images/2021-10-22-02-23-09.png)![h:384px](images/2021-10-22-02-40-24.png)![h:383px](images/2021-10-22-04-07-06.png)![h:383px](images/2021-10-22-16-42-42.png)

---
#### URL for cloning
- You can clone the application from the following URL, and use it to check your answers
https://previewer.adalo.com/014fd9d1-80c6-4325-899a-d943e778c865

![bg right h:400px](images/2021-10-22-17-31-06.png)

---
## Exercise
- Create your own screen that will be the transition destination for Link 2 on the pet details screen.
  - When you are done, share the URL on Slack for everyone to see!

![bg right h:500px](images/2021-10-22-18-37-12.png)

---
#### Notes on the exercise
- Components and Screens with "List" in their names may be difficult to use because they need to be connected to the database, which we will discuss in the next lecture.
  - If you can't solve this problem by yourself, we recommend you to substitute them with something else today.
- While the NoCode tool allows you to create apps easily, it may not allow you to achieve complex UI and functions!
  - If you are stuck, think about how you can achieve what you want to do with a simple UI and functionality.
    - For example: don't include too many components in one screen, separate screens, etc.

---
#### Presentation of exercise results
(If there is enough time)

Would you like to present the screens you made in the exercise?

---
## Summary
- In this lecture, we introduced Adalo and created the UI of an application based on a pet health management application.
  - We used only simple components that do not require a database.
- In the next lecture, we will continue to use Adalo to build a database that matches the UI we created this time, so that we can manipulate data from the app. 
  - By using a database, various functions can be realized and the UI can be easily created. Enjoy!

---
# That's all!
# Thanks for your time!