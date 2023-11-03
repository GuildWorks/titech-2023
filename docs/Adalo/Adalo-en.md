---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Ryo Imahashi'

page_number: true
paginate: true
---

**Programming Boot Camp**

# App Development and external integration with Adalo

**Tokyo Institute of Technology 2023/11/3**
　
　
　
　　　　　　　　　　　　　　　　　　　　　　**Ryo Imahashi**

---
## Table of Contents
  - What is Adalo?
  - Adalo account registration
  - Try template application
  - Overview of application development with Adalo
  - Sample application development
  - Sample application improvement
  - External integration
  - Summary

---
## What is Adalo?
- [Adalo](https://www.adalo.com/) is a no-code tool from the United States. It allows you to develop applications without programming.
- You can create an app by selecting the parts you want to use from those provided and dragging and dropping them onto the screen.
- You can develop not only web apps(to be displayed in a browser), but also smartphone apps for Android and iOS. It is also possible to publish the developed application on Google Play and AppStore.
- It is a good tool for learning no-code development for the first time because it is simple and easy to understand.

---
#### Caution
- It is difficult for multiple people to edit an Adalo application at the same time, so using it for team development in DevelopmentPhase is not recommended.
  - However, if only one person is in charge of screen development and all other members are in charge of API development, it can be used without problems.

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
- Recommended browser is the Google Chrom
  - Install: https://www.google.com/intl/ja_jp/chrome/

---
- You can register for free!
-  Enter your email address, password and full name.
-  Check the box to agree to the Terms of Use.
- Click the  DO THIS! button to proceed.

---
#### Reference: Limitations of the [Free Plan](https://www.adalo.com/pricing)
- Cannot use external integration with other applications.
  - However, trial use is available for 14 days
- The maximum number of database records is 200.
- App actions are limited to 1,000 times per month.

:white_check_mark:  Consider using a Paid Plan when you actually launch your app.

---
- Select For teaching or taking a class and Click Go Build Apps! Button.
![w:900px](images/2023-10-29-13-06-38.png)


---
#### Platform Selection
- You can select Responsive App or Mobile Only.
- Select Responsive App. It can be used by both PC and Mobile device sizes.
![bg 90% right](images/2023-10-29-13-09-34.png)

---
#### Selecting a template
- Finished apps are provided as templates.
- This time, select Chat template.
![bg 90% right](images/2023-10-29-13-34-34.png)


---
#### Branding
- Enter the App Name, Primary Color, and Secondary Color.
  - Primary Color is the base color that will be used most in your app.
  - Secondary Color is the color for important parts (e.g. register button)
![bg 90% right](images/2023-10-29-13-36-48.png)

---
- When you see Adalo's admin panel like this, you are good to go!
- From now on, we will use this admin panel to develop our application.
![w:900px](images/2023-10-29-13-37-30.png)

---
## Try template application
- First of all,  try to operate the Chat app template to see how the application created by Adalo works.
- Click the Preview button in the upper right corner of the screen

![w:1100px](images/preview-button.png)

---
- The preview screen will be launched.
- Let's operate the Chat application together!
![w:800px](images/2023-10-29-14-41-39.png)

---
- Sign up.
  -  Enter your Email and Password (remember them so that you can use again later).
![w:900px](images/2023-10-29-14-44-05.png)


---
- The list is empty because no conversation has taken place yet
-  Press the NEW CHAT button at the top right corner of the screen.
![w:900px](images/2023-10-29-14-46-41.png)

---
- You can see the list of sample users.
- Click Will W.
![w:900px](images/2023-10-29-14-48-59.png)

---
- You can send messages.
![w:900px](images/2023-10-29-14-50-08.png)

---
There are other features as below.
- Profile Photo Update
- Password Change
- Logout
- Log in
  - You can log in as the sample user Will W by entering the following.
    - Email: will@email.com
    - Password: 123

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
- Example: In the case of the Chat application
![w:400px](images/2023-10-29-15-08-00.png)
![bg 35% right](images/2021-10-19-23-13-47.png)

---
#### Actions
- This is used to specify what to do when a specific component is clicked.
- Example :
  - Transition to another screen.
  - Registering, updating, and deleting data in the database.
![bg 35% right](images/2021-10-19-23-12-42.png)

---
### Explanation of Adalo's features
Next, take a look at the features available in Adalo's admin panel.
![w:900px](images/2023-10-29-15-10-32.png)

---
#### Canvas
- A work area for creating screens.
- Elements can be selected and moved by dragging and dropping.
![w:670px](images/2023-10-29-15-11-49.png)


---
#### Left Toolbar
Let's learn each function of the left toolbar.

![w:70px](images/2023-10-29-15-13-02.png)

---
###### ![w:60px](images/add-panel.png) Add Panel
- This allows you to select a component or screen to add to your app.
- Feature templates are also available.
![bg right 95%](images/2023-10-29-15-16-43.png)
![bg right 95%](images/2023-10-29-15-17-09.png)

---
###### ![w:60px](images/2021-10-20-00-52-07.png) Branding
- You can change colors and fonts.
![bg right 98%](images/2023-10-29-15-25-23.png)
![bg right 94%](images/2023-10-29-15-25-47.png)

---
###### ![w:60px](images/2021-10-20-00-54-44.png) Screens
- List of screens and their configurations.
![bg right 100%](images/2023-10-29-15-26-42.png)
![bg right 93%](images/2023-10-29-15-27-37.png)

---
###### ![w:60px](images/2021-10-20-01-20-56.png) Database
- Displays the structure of the database and the data stored in it.
- Collection: A collection of data that has the same properties.
![w:200px](images/2023-10-29-15-29-22.png) ![w:850px](images/2023-10-29-15-30-54.png)

---
###### ![w:60px](images/2021-10-20-01-45-09.png) Settings 
- You can configure app name, icon etc.
- You can configure display settings for the canvas.
- You can set access permissions to the app.
- You can copy or delete an app.
- You can set api key for geolocation feature.
![bg right 80%](images/2023-10-29-15-32-03.png)

---
###### ![w:60px](images/2021-10-20-01-56-00.png)Publish
- You can publish your apps (paid plan required).
![bg right 90%](images/2023-10-29-15-33-39.png)

---
###### ![w:60px](images/2021-10-20-02-06-34.png) Analytics
- Show usage analysis report.
![bg right 95%](images/2023-10-29-15-34-38.png)

---
###### ![w:60px](images/2022-11-02-08-01-35.png) Version History
- You can create version history and restore version (paid plan required).
![bg right 80%](images/2022-11-04-23-29-30.png)

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
###### Preview, Share
- You can run the app and try it out.
![w:930px](images/2023-10-29-15-36-52.png)

---
###### Account Menu
- Allows you to configure various settings.
- Link to help and documentation.
- You can find an Adalo Expert.
- Sign Out.
![bg right 90%](images/2023-10-29-15-41-03.png)

---
#### Tips
- If you edit something by mistake, you can undo it with `Ctrl + Z` on Windows or `Command + Z ` on Mac!
- Entering japanese text may not work well with Adalo's development tools. Use copy and paste instead.

---
## Sample application development
Let's create a new application.


---
#### UI of the sample application
This is a health management application for your pet.
First, check the UI.

![h:383px](images/2023-11-02-18-52-28.png) ![h:383px](images/2023-11-02-18-53-10.png) ![h:383px](images/2023-11-02-18-47-35.png) ![h:384px](images/2023-11-02-18-48-18.png) ![h:383px](images/2023-11-02-18-50-07.png) ![h:383px](images/2023-11-02-18-50-36.png)


---
###### User Registration Screen
- You can register as a user by entering the following information
  - Email
  - Password
  - Full Name
- For those who have already registered, there is a link to the login screen.
![bg right h:700px](images/2023-11-02-18-52-28.png)

---
###### Login screen
- You can log in by entering the following information
  - Email
  - Password
- There is a link for those who have forgotten their password.
- There is a link to the user registration page.
![bg right h:700px](images/2023-11-02-18-53-10.png)

---
###### Pet Registration Screen
- You can enter your pet's name.
- You can select your pet's photo.
- You can enter your pet's birthday.
- You can click the "Register" button to register your pet and move to the pet list screen.
![bg right h:700px](images/2023-11-02-18-47-35.png)

---
###### Pet List screen
- Registered pets can be displayed in a list.
- Clicking on a pet will take you to the pet details screen for that pet.
- Clicking the icon at the bottom right take you to the Pet Registration screen.
![bg right h:700px](images/2023-11-02-18-48-18.png)

---
###### Pet Detail Screen
- Birthday is displayed.
- The latest weight is displayed.
- There is a link to the weight log screen.
![bg right h:700px](images/2023-11-02-18-50-07.png)

---
###### Weight Log screen
- A graph showing the transition in weight is displayed.
- You can enter your pet's current weight.
- You can add your pet's weight by pressing the button
![bg right h:700px](images/2023-11-02-18-50-36.png)

---
#### Creating the application
Now, let's create the application.

-  select CREATE NEW APP
![bg right 95%](images/2023-10-29-18-03-42.png)

--- 
- Select Responsive App
![bg right 95%](images/2023-10-29-18-04-45.png)

---
-  select Template: Blank Mobile First
![bg right 95%](images/2023-10-29-18-05-48.png)

---
- Enter App Name, Users of this app, and Color as you like.
![bg right 95%](images/2023-10-29-18-07-55.png)

---
- The application is created
![h:550px](images/2023-11-01-07-56-10.png)

---
#### Let's learn about database
Defining the data to be handled by that application at the beginning of the application development make it easy to develop the application.

First, learn what a database is.

---
###### Database
- A set of organized data.
- Data can be registered, read (displayed), updated, and deleted.
- Example: In the case of a Chat application
![w:400px](images/2023-10-29-15-08-00.png)
![bg 35% right](images/2021-10-19-23-13-47.png)

---
- Databases are often compared to "spreadsheet-like" software.
- A database can be used to CREATE, READ, UPDATE, and DELETE data. These operations are collectively called CRUD operations.

![bg right w:630px](images/2023-11-01-21-39-53.png)

---
###### Basics of Adalo's database
![w:60px](images/2021-10-20-01-20-56.png) You can access Adalo's database from this icon.
There are three components of the Adalo database.
- Collection
- Property
- Record

---
###### What is a Collection?
A collection of data that has the same property.
![w:250px](images/2023-11-01-21-38-02.png) ![w:700px](images/2023-11-01-21-39-53.png)

---
- Collection is used to divide and organize the various data.(An analogous term is table.)
- In many cases, a Collection is a group of data that a user can register, update, or delete in a single operation. <!-- (A collection is often said to be something that can be expressed as a noun.
- By default, Users is prepared as a Collection, and the rest can be added according to the application to be developed.

It is very difficult to decide what kind of collection to add. Let's practice and get used to it. (If you have any problems, consult with mentors.)

---
###### What is Record?
- Record is a unit of information in a collection.
  - One row corresponds to one Record.
- In the example of Users Collection, the information belongs to one user is registered as one Record.
![w:550px](images/2023-11-01-21-39-53.png)

---
- Records are basically registered from the form on the screen of the app, but it is also possible to register from the form by pressing the "+Add xxxx" button on the upper right in Record View.
- You can also search for Records in the Collection, and upload (import) and download CSV files.
![bg right h:460px](images/2023-11-01-21-41-59.png)

---
###### What is Property?
- Property is each and every item that makes up a Record.
- The Users Collection consists of properties such as email, password, user name, and name.
- The value of Property can be empty.

![bg right h:450px](images/2021-11-05-16-25-58.png)

---
To define what kind of data the Property is, select the Type when adding it.
- Text
- Number
- True/False
- Date/Time
- Date/Time
- Image
- File
- Location

![bg right h:600px](images/2022-11-05-12-38-25.png)

---
What is Relationship?
- Instead of storing a large number of properties for a single Record, we can set a special property to relate multiple Collections, called Relationship. This allows you to divide a Collection into manageable pieces.

---
- For example, a message sent by a user in the Chat app is stored in the Messages Collection, which is separate from the Users Collection, and these two collections are related by Relationship.
  - The Users side has a Relationship called Messages, and the Messages side has a Relationship called Sender (with Users).

![bg right h:450px](images/2023-11-01-21-45-10.png)
![bg right h:350px](images/2023-11-01-21-46-52.png)

---
Types of Relationship
- In Adalo's Relationship, you can choose one of two types, one-to-many or many-to-many, depending on the number of Records associated with the Collection. 

---
One-to-many Relationship
- This means that one Record has a relationship with multiple Records in different collections. 
- Depending on whether the Collection you are trying to set the Relationship to is one or many, two choices will appear.

![bg right h:320px](images/2022-11-05-12-42-56.png)

---
Example of a one-to-many Relationship
- In the Chat application, one user sends multiple messages, but the sender of the message is one user, so the Relationship in the Users Collection and Messages Collection is one-to-many.

![h:250px](images/2023-11-01-21-48-22.png) ![h:250px](images/2023-11-01-21-51-33.png)

<!-- For example, if there is only one organizer for an event, then the Relationship between the organizer and the event is one-to-many. -->
<!-- For example, one user organizes multiple events, or there is one organizer for multiple events, both of which represent true one-to-many Relationships. -->

---
Many-to-many Relationships
- This means that one Record in both Collections is tied to multiple Records in the other Collection.

![bg right h:140px](images/2022-11-05-12-48-16.png)

---
An example of a many-to-many Relationship
- In a Chat application, one user can have multiple conversations (to keep track of who and what messages were exchanged), and one conversation can have multiple members (users), so the relationship between the Users Collection and the Conversations Collection is many-to-many.

![h:260px](images/2023-11-01-21-53-05.png) ![h:260px](images/2023-11-01-21-53-42.png)

---
#### Database design
Let's design the database of the sample app.

---
###### Let's design the database.
Let's design the database by looking at the UI of the sample application. The steps are described in the next page.
![h:383px](images/2023-11-02-18-52-28.png) ![h:383px](images/2023-11-02-18-53-10.png) ![h:383px](images/2023-11-02-18-47-35.png) ![h:384px](images/2023-11-02-18-48-18.png) ![h:383px](images/2023-11-02-18-50-07.png) ![h:383px](images/2023-11-02-18-50-36.png)

---
###### Database Design Steps
1. While looking at the UI, make a list of the data that will need to be saved. Write them down in a text editor (e.g. Notepad application).
2. Think about what kind of collections should be created to store the listed data, and create the collections in the Adalo database.
3. Add the data you listed in step 1 as a Property to the appropriate Collection and select the appropriate Type.
4. Set the Relationship Property to collections related to other collection.

---
In the next slide and onwards, there are explanations, but it is highly recommended that you try it by yourself before checking them.

There is no absolute right answer. When in doubt, follow your intuitions.

---
###### Explanations
While looking at the UI, made a list of the data that needs to be saved, and it looked like this
````
- User's Email
- User's Password
- User's FullName
- Pet's Name
- Pet's Photo
- Pet's Birth Date
- Pet's weight
- Date and time the pet's weight was registered
````

- If anyone can name any other data, please let me know!

---
Thinking about what kind of collections should be created to store the listed data, listed these three Collections.
```
- Users
- Pets
- PetWeightLogs
```
- Many of you would have listed two collections, one for users and one for pets.
- Some people would not have listed a collection for pet weight records. (It is not wrong to include the pet's weight and its registration date in the pet's Collection. This will be explained later.)
- Have any of you listed other Collections?
<!-- In extreme cases, you can do it with 1Collection -->.

---
Additional information on Collection classification
- When the relationship "if A is identified, then B is identified" is true, "A" is often a Collection and "B" is a Property of that Collection.
  - If a user is identified, the user's email, password, and FullName are identified.
  - If a pet is identified, the pet's name, photo, and birthday are identified.
- When the relationship "there are multiple B's corresponding to A" is true, A and B are often split into two collections.
  - There are multiple pet weights and their registration times corresponding to a pet.

---
- Register the Collection into the Adalo database.
  - Add manually by ADD TO DATABASE > Add Collection
  - Magic Add will suggest changes to the database based on the description of the feature you entered, but we will not use it this time.
- Users Collection is created by default.
![bg right h:550px](images/2023-11-01-22-10-13.png)

---
Next, I appended the data listed in step1 as a Property of the appropriate Collection. Types are placed in "()".
```
- Users
  - Email(Text)
  - Password(*Password)
  - FullName(Text)
- Pets
  - Name(Text)
  - Image(Image)
  - Birthday(Date)
- PetWeightLogs
  - WeightKg(Number)
  - RegisteredTime(Date&Time)
```
Password is a special Type that is set to Password by default.
<!-- This will be an encrypted version of Text. -->

---
- In Adalo database, add the properties.
- The Users Collection is already set by default and contains all the necessary items.
- We don't need Username, but since we can't delete it, leave it as is.
![bg right h:500px](images/2021-11-03-15-40-03.png)

---
- The Pets Collection Property looks like this.
![bg right h:400px](images/2021-11-03-15-42-07.png)

---
- The Property of the PetWeightLogs Collection looks like this.
- Delete the Name Property, which is set by default when you add a Collection.
  - You can delete it after dragging and dropping it so that the order is not at the top of the collection.

<!-- The name property is not needed. [](images/2021-11-03-15-36-02.png) --> !
![bg right h:300px](images/2021-11-03-15-45-14.png)

---
Finally, for collections that are related to other collections, set the Relationship Property.

- Select the Users Collection to add a one-to-many Relationship with the Pet Collection.
![w:530px](images/2021-11-03-15-50-06.png)

![bg right h:700px](images/2023-11-01-22-18-31.png)

---
- If you check the Pets Collection, you will see that a Relationship with the Users Collection has been automatically added because the Relationship setting was made on the Users Collection side.
  - Since the Users Collection is one side, the "s" at the end is omitted and the Property name is "User".

![bg right h:550px](images/2023-11-01-22-19-28.png)

---
- Add a Relationship to the Pets Collection with the PetWeightLogs Collection.
  - Select the Pets Collection to add a one-to-many Relationship with the PetWeightLogs Collection.
![w:490px](images/2021-11-03-15-58-38.png)
![bg right h:700px](images/2023-11-01-22-20-54.png)

---
If you check the PetWeightLogs Collection, you will see that a Relationship with the Pets Collection has been automatically added because the Relationship setting was made on the Pets Collection side.
  - Since the Pets Collection side is one side, the "s" at the end is omitted, and the Property name is "Pet".

![bg right h:500px](images/2023-11-01-22-21-35.png)

---
Reference: What happens if you include the pet weights and its registration times in the Pets Collection?

The record will be registered as follows, but in this case, you will have the troubles.
![w:1200px](images/2021-11-03-14-47-07.png)

---
The troubles
- Because multiple Records with different pet weights and their registration times are registered for one pet, the pet's information (Name, Image, Birthday) is registered in duplicate.
  - In order to change the information of one pet, we have to update all the duplicated records, which makes the process more complicated.
- Adalo has a convenient function to automatically generate a form to register a record in a single collection, but since the collection is not divided by the unit to register data, it cannot be used.

---
That's it for the sample app database design.

It is recommended that you set up Adalo's database in the same state as the document to avoid confusion in the later work.

---
#### Let's develop an app using the database
Let's develop a sample app using the database you designed.

---
###### User registration screen, login screen

:white_check_mark: User registration screen and login screen are generated by default.
- Check the preview Button to see how they works.
![bg right h:600px](images/2023-11-01-07-59-08.png)

---
To create an app in Mobile First, we will now use the browser's developer tools to preview the app in Mobile size.
- In Chrome, follow these steps to open the Developer Tools
  - Top right three point reader > More Tools > Developer Tools
![h:400px](images/2023-11-01-08-30-43.png)

---
In Chrome's Developer Tools, you can check the display on various device screen sizes.
- Select iPhone 12 Pro to preview
![h:450px](images/2023-11-01-08-32-23.png)

---
- User Registration Screen
  - When you signup, you will be redirected to the Home screen.
  - Use the back button on the browser and click ALREADY HAVE AN ACCOUNT? to go to login screen.
![bg right h:600px](images/2023-11-01-08-37-06.png)
![bg right h:600px](images/2023-11-01-08-39-34.png)

---
- Login screen
  - Log in with the same Email and Password that you registered earlier, then you will be redirected to the Home screen.
![bg right h:600px](images/2023-11-01-08-42-17.png)
![bg right h:600px](images/2023-11-01-08-39-34.png)

---
It seems like the registration screen and login screen are fine as they are.
- Change the part labeled "App Name" to the name of the application.
![w:600](images/2023-11-02-19-01-02.png)

Let's create the other four screens.

---
###### Pet Registration Screen
- You can enter your pet's name.
- You can select your pet's photo.
- You can enter your pet's birthday.
- You can click the "Register" button to register your pet and move to the pet list screen.
Let's create this screen!
![bg right h:700px](images/2023-11-02-18-47-35.png)

---
- Select Blank Mobile First from ADD SCREEN.
![bg right h:700px](images/2023-11-01-22-48-24.png)

---
- Enter the Screen Name.
![w:900px](images/2021-10-20-06-28-11.png)

---
The Screen has been added.

Let's add components on this screen.

![bg right h:700px](images/2023-11-01-22-51-44.png)

---
- Select App Bar from ADD COMPONENT.
![bg right h:650px](images/2023-11-01-22-53-38.png)

---
- Place it on the screen.
![bg right h:700px](images/2023-11-01-22-54-12.png)

---
- Change the value of Title > Text to the screen name (PetRegistration).
![bg right h:700px](images/2023-11-01-22-55-53.png)

---
- Select Form from ADD COMPONENT.
![bg right h:700px](images/2023-11-01-22-57-45.png)

---
- Place it on the screen.
![bg right h:700px](images/2023-11-01-22-59-55.png)

---
- Select Pets for "Which data collection?
  - A form will be automatically generated for the selected collection.
- Select Create New pet for What do you want the form to do?
![bg right h:450px](images/2023-11-01-23-06-42.png)

---
- Change ther order of Birthday and Image in Fields by drag and drop.
![bg right h:580px](images/2023-11-01-23-08-54.png)

---
- Make sure Create Pet is set in ClickActions of Submit Button
![bg right h:580px](images/2023-11-01-23-10-32.png)

---
Since there is no link yet, we can't display it, so let's make it possible.
- Make it Home Screen to be the first screen that appears when you are logged in
  - Select "Pet Registration" from "Screens" and change "Screen Navigation Type" to "Home Screen
![bg right h:400px](images/2021-10-20-07-28-52.png)
---
- Open Form > Submit button on the login screen, and change the Screen of Link to the PetRegistration.
![bg right h:600px](images/2023-11-01-23-29-51.png)

---
Let's see how the Pet Registration Screen works.
- After logging in with the preview function, you can view the pet registration screen.
- You can enter a name, select an image, and choose a birthday.
- Press CREATE PET button to register your pet
![bg right h:700px](images/2023-11-01-23-34-29.png)

---
After registering the pet, it is OK when the Record is registered in the Pets Collection of the database.
![w:300](images/2023-11-01-23-37-16.png) ![w:800](images/2023-11-01-23-36-05.png)

The pet registration screen is done.

---
###### ペット一覧画面
- Registered pets can be displayed in a list.
- Click on a pet to move to the pet details screen.
- Click the icon in the lower right corner to move to the pet registration screen.
![bg right h:700px](images/2023-11-02-18-48-18.png)

Next, let's create this screen.

---
- Select Blank Mobile First from ADD SCREEN and enter Screen Name
![h:500px](images/2023-11-01-22-48-24.png) ![h:300px](images/2023-11-02-05-01-05.png)

---
- Select App Bar from ADD COMPONENT and place it on the screen
- Change the value of Title > Text to the screen name (MyPets)
![bg right h:600px](images/2023-11-02-05-07-19.png)

---
- Select Card List from ADD COMPONENT and place it on the screen
![bg right w:600px](images/2023-11-02-05-10-27.png)

---
- Select Pets under What is this a list of?
- Select Logged In User > Pets in Filter
- Change the value of Columns to 1
![bg right h:600px](images/2023-11-02-05-13-14.png)

---
- Turn off the unwanted Subtitle and Body toggles to hide them.
![bg right h:600px](images/2023-11-02-05-16-40.png)

---
Next, add a lead to the pet registration screen
- Select Action Button from ADD COMPONENT
![bg right h:500px](images/2023-11-02-05-18-12.png)

---
- Place it in the lower right corner of the screen.
- Change Icon and Text Color to Default Background(White)
![bg right h:600px](images/2023-11-02-05-19-29.png)

---
- Select ADD ACTION -> Link -> PetRegistration
- Transition can be left as None
![bg right h:500px](images/2023-11-02-05-20-09.png)

---
Let's also add a link from the Pet Registration screen to the Pet List screen
- Select Form > Submit Button on the pet registration screen.
- ADD ANOTHER ACTION -> Link -> MyPets
![bg right h:500px](images/2023-11-02-05-24-39.png)

---
- Change the destination of the SIGNUP button on the SignUp screen and the LOGIN button on the Login screen from Home to MyPets.
![bg right h:450px](images/2023-11-02-05-26-39.png)

---
- The Home screen that was created by default is no longer needed, so let's delete it.
![bg right h:600px](images/2023-11-02-05-29-02.png)

---
Let's check how the Pets List screen works.
- Change the Screen Navigation Type of the Pet List screen to Home Screen as you did when you previewed the Pet Registration screen!
- After logging in with the Preview function, you can view the Pets List screen.
![bg right h:700px](images/2023-11-02-05-36-18.png)

---
- When you add a pet on the Pet Registration screen, it will also appear on the Pet List screen

The Pets List screen is done.
![bg right h:700px](images/2023-11-02-05-34-18.png)

---
###### ペット詳細画面
- Birthday is displayed
- Shows the latest weight.
- There is a link to the weight log screen

Next, let's create this screen
![bg right h:700px](images/2023-11-02-18-50-07.png)

---
- Select Blank Mobile First from ADD SCREEN and enter Screen Name.
![h:500px](images/2023-11-01-22-48-24.png) ![h:300px](images/2023-11-02-06-41-40.png)

---
- Select App Bar from ADD COMPONENT and place it on the screen
- Change the value of Title > Text to the screen name (PetDetail)
![bg right h:600px](images/2023-11-02-06-44-49.png)

---
- Select Image from ADD COMPONENT and place it on the screen.
![bg right w:500px](images/2023-11-02-07-48-13.png)

---
We want to set Image Source as image of a specific pet that we want to display, but it is ready to do.

It seems like we can choose "Logged In User's > Pets > ...", but it is not an option at this time. 
You could choose "Logged In User's > Pets > ...", but since the user has multiple pets, you can't specify a single pet.

![bg right w:600px](images/2023-11-02-06-47-41.png)

---
Setting up a link to this screen will add the specific pet you want to display to the choices.
- Click ADD ACTION in CardList on the Pet Listing screen to add a Link to PetDetail.
![bg right h:600px](images/2023-11-02-06-56-07.png)

---
- Current Pet is automatically set to Send This Data to PetDetail Screen in the Link you added.

![bg right h:500px](images/2023-11-02-07-00-07.png)

---
- Current Pet is set as Linked Data in Available Data of Pette Detail Screen because Current Pet is set in Send This Data to PetDetail Screen of Link from Pette List Screen.
  - This allows you to handle the pet (Current Pet) selected on the Pet List screen in the Pet Detail screen.
![bg right h:350px](images/2023-11-02-07-01-51.png)

---
- Set Database > Current Pet > Image to ImageSource in the Image component.
![h:400](images/2023-11-02-07-03-10.png)

Now the image of the specific pet will be displayed.

---
We will also add other items.
- Add Text from ADD COMPONENT to display the label Birthday and its value
  - To display the value, select Current Pet's > Birthday from ADD Magic Text
![bg right h:700px](images/2023-11-02-07-08-35.png)

---
- Change the Data Format to No Formatting from the edit icon on the right side of the pet birthday in Text
![bg right h:400px](images/2023-11-02-08-35-08.png)

---
- Add Text from ADD COMPONENT and display the label Latest Weight.
![bg right h:700px](images/2023-11-02-07-14-08.png)

---
To display the value of Latest Weight needs some work.

- Add Text from ADD COMPONENT and make it a list with Make List.
![bg right h:400px](images/2023-11-02-07-17-47.png)

--- 
- Select PetWeightLogs in What is this a list of?
- Select Current Pet > PetWeightLogs in Filtering
- In Sorting, select WeightRegisteredTime - Newest to Oldest
- Set Maximum number of items to 1

![bg right h:600px](images/2023-11-02-07-19-58.png)

This will limit the number of items to only the most recent one.

---
- Set the value of the Text component in the List to Current PetWeightLog's > WeightKg.
![bg right h:600px](images/2023-11-02-07-24-05.png)


---
- Let's see how it works in the preview window

Since PetWeightLog's data has not been registered yet, Latest Weight is not displayed, but this is OK for now.
![bg right h:700px](images/2023-11-02-08-37-34.png)

---
###### Weight Log Screen
- Displays a graph showing weight transitions
- Current weight can be entered
- Weight can be added with the press of a button

Finally, let's create this screen.
![bg right h:700px](images/2023-11-02-18-50-36.png)


---
Add a button on the pet details screen that will lead to the weight recording screen
- Select the Button from ADD COMPONENT and place it on the screen.
- Change the Text to Weight Log.
- Change Icon to chevron_right
![bg right h:600px](images/2023-11-02-08-00-48.png)

---
- Select ADD ACTION > Link > New Screen
![bg right h:600px](images/2023-11-02-08-02-53.png)

---
- Enter Screen Name and select Blank Mobile First to create the screen.
 ![bg right h:600px](images/2023-11-02-08-04-30.png)

---
The created screen can handle the Current Pet data passed from the Pet Details screen.
![bg right h:440px](images/2023-11-02-08-09-20.png)

---
- Select App Bar from ADD COMPONENT and place it on the screen
- Change the value of Title > Text to the screen name (PetWeightLog)
![bg right h:600px](images/2023-11-02-07-46-39.png)

---
Next, we will display the weight of the pets registered in the past as a graph.
- Select EXPLORE MARKETPLACE from ADD COMPONENT
- INSTALL Chart Kit

![bg right h:450px](images/2021-11-04-03-52-55.png)　![bg right h:170px](images/2023-11-02-07-51-53.png)

---
- Add Line Chart to screen
![bg right h:400px](images/2023-11-02-07-54-16.png)


---
Set up a Line Chart.
- Select PetWeightLogs in What is this a chart of?
- Select Current Pet > PetWeightLogs in Filter
- In Custom Filter, set WeightRegisteredTime Is after 30 days ago and specify the display period
- Select WeightRegisteredTime - Oldest to Newest in Sorting

![bg right h:700px](images/2023-11-02-08-12-17.png)

---
- Set PetWeightLog > WeightRegisteredTime in X Axis Value
  - Set Date / Time to Date Format
- Set PetWeightLog > WeightKg to Y Axis Value
![bg right h:350px](images/2023-11-02-08-13-12.png)
![bg right h:250px](images/2021-11-04-04-13-46.png)

Ready to show the graph.

---
Next, let's make it possible to record weight.

- From ADD COMPONENT, add Text Input
- Change the Type to Number
- Change the Placeholder to Enter current weight
![bg right h:500px](images/2023-11-02-08-17-51.png)

---
- Add Text from ADD COMPONENT
- Change the value to Weight(kg)
![bg right h:500px](images/2023-11-02-08-18-37.png)

---
- Add Button from ADD COMPONENT
- Change Text to Add
- Choose Create > PetWeightLog from ADD ACTION 
![bg right h:500px](images/2023-11-02-08-20-46.png)

---
Set the following for the Action.
- WeightKg: Other Components > Input
- WeightRegisteredTime: Date & Time > Current Time
- Pet: Current Pet
![bg right h:500px](images/2023-11-02-08-22-46.png)

Weight log screen is done.

---
Let's set a link to the back icon in the header so that you can go back and forth between screens to check the operation.
- On each of the Pet Registration and Pet Details screens, add a link to MyPets to the Left Icon in the App Bar
![bg right h:450](images/2023-11-02-08-50-25.png)

---
- On the Weight Record screen, select Back in the link in the Left Icon of the App Bar
![bg right h:550](images/2023-11-02-08-53-32.png)

<!-- ---
参考: 体重記録画面で、App BarのLeft Iconのリンク先を、ペット詳細画面にしてしまうと、CurrentPetの情報が失われてしまいます
![bg right h:450](images/2023-11-02-08-56-14.png) -->
<!-- →実際に試すと、動作に問題なかった -->

---
Check the graph with the Preview function. If you add multiple weights, the graph will be drawn.

The date and time is long and not displayed properly. I wanted to test by registering multiple weights on the same day, so I used Date&Time type, but it would be better to use Date type and control that only one weight can be registered per day.
<!-- 、連続で異なる体重を追加するとLineが上下に伸びてしまう -->
<!-- ![bg right h:700px](images/2021-11-04-04-15-38.png) -->
![bg right h:700px](images/2023-11-02-08-28-21.png)

---
You can also see that the Latest Weight is now displayed in the pet details screen.
![bg right h:700px](images/2023-11-02-09-01-42.png)


---
You created a whole set of screens for the application :tada:

![h:383px](images/2023-11-02-18-52-28.png) ![h:383px](images/2023-11-02-18-53-10.png) ![h:383px](images/2023-11-02-18-47-35.png) ![h:384px](images/2023-11-02-18-48-18.png) ![h:383px](images/2023-11-02-18-50-07.png) ![h:383px](images/2023-11-02-18-50-36.png)

---
#### URL for clone
- You can clone the app I created by the CLONE APP button in the lower right corner of the following URL. 
https://ryo-imahashis-team-6.adalo.com/pethealthlog

![bg right h:350px](images/2023-11-03-08-04-43.png)

---

## 演習1
1. Create an edit pet screen where you can edit the information of registered pets
2. Add a function to delete a registered pet.

---
#### Hint
- When creating the Edit Pets screen, please refer to how to create the Pet Registration screen.
- You don't need a new screen for the pet deletion function, so please think about where to add the delete button!
- When adding ACTION, you can choose Update or Delete
![h:300](images/2023-11-02-19-44-50.png)


---
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass:
# :hourglass:

---
#### 演習1の答え合わせ
Try it by yourself first, then see the answer in following pages :pray:

---
###### Pet Edit Screen
Create a new pet edit screen where you can update the information of your registered pets.


---
First, add a lead to the pet information edit screen to the pet details screen.
- Add Action Button from ADD COMPONENT
- Change Icon to edit.
- Change Icon and Text Color to Default Background(white)
![bg right h:600px](images/2023-11-03-00-06-25.png)

---
- Select Link > New Screen from ADD ACTION
![bg right h:630px](images/2023-11-03-00-08-11.png)


---
- Select Blank Mobile First and create EditPetInfo screen
![bg right h:620px](images/2023-11-03-00-09-03.png)

---
- Add App Bar and change Title to EditPetInfo
- Add Form and set the following
  - Pets for Under Which data collection?
  - Update Current Pet for What do you want the form to do?
- In Fields, change the order of Birthday and Image.

![bg right h:460px](images/2023-11-03-00-13-30.png)
<!-- 更新不要な項目があれば、その入力箇所は削除できそう -->

---
- Add a link back to the Submit Button on the Form
![bg right h:600px](images/2023-11-03-00-22-10.png)

---
- Add back link to Left Icon of App Bar.
![bg right h:600px](images/2023-11-03-00-15-38.png)


---
Make sure the Edit Pet Info screen is available in the Preview function.

![bg right h:700px](images/2023-11-03-00-25-31.png)

---
FYI
- The Required Error Text of the Field in the Form component is checked by default, and an error message will be displayed if that field is not filled in.
- Let's check it by clicking UPDATE PET with no entry!
![bg right h:600px](images/2023-11-03-00-27-27.png)
![bg right h:600px](images/2023-11-03-00-28-44.png)

---
###### Pet Delete Function
Add a button to delete a registered pet on the pet details screen.

---
- Select App Bar and turn on the Right Icon 1 toggle
- Change Icon to DELETE
- Select Delete > Current Pet from ADD ACTION
- Select Link > Mypets from ADD ANOTHER ACTION
![bg right h:550px](images/2023-11-03-00-32-55.png)

<!-- TODO: 削除の前に本当によろしいですか？ を挟みたい-->
---
Let's preview deleting function.

When the deletion is completed and you move to the Pets List screen, the deleted pets will not be displayed.

![bg right h:600px](images/2023-11-03-00-34-40.png)
![bg right h:600px](images/2023-11-03-00-34-58.png)

---
## Sample application improvement
We will improve the sample app by using Adalo features that I have not yet introduced.

---
#### Logout
- Select AppBar on the pet list screen and activate Right Icon 1
- Change Icon to logout
- ADD ACTION > More... > Select User Login > Log Out
- Select ADD ANOTHER ACTION > Link > Login
![bg right h:580px](images/2023-11-03-00-56-10.png)

---
Use the Preview function to check it out.
Clicking on the added icon now logs you out and takes you to the login screen.

----
#### Action execution condition setting
If a pet is unregistered and the Pet List screen is displayed, it will transition to the Pet Registration screen.
- Select Actions > ADD ACTION > Link > Pet Registration on the Pet List screen.
- Click SHOW ADVANCED and change When does this happen?
![bg right h:600px](images/2023-11-03-00-59-14.png)

---
- Select More > Logged In User's > Pets' > Count in This action will only happen if... 
- Change the number under Is equal to to 0
![bg right h:600px](images/2023-11-03-01-00-58.png)

---
Check it out with the Preview function.
Signup as a new user and you will be redirected from the Pet List screen to the Pet Registration screen.

---
#### Selective Input Form
Add gender to the pet information and allow selective input on the input form.

---
The choices used in the selective input form are prepared as records by adding a Collection to the database.
- ADD Genders Collection to database (Property can be left as default)
- 0 Click Records > ADD GENDER and add two Records, Male and Female
![h:400px](images/2023-11-03-01-02-28.png)

---
- Add a one-to-many Relationship with the Pets Collection to the Genders Collection
  - Since one pet has one gender and one gender has multiple pets.
![bg right h:600px](images/2021-11-05-00-46-10.png)

---
- Select the form on the pet registration screen
- Select Fields > ADD VISIBLE FIELD > Gender 
![bg right h:600px](images/2023-11-03-01-04-12.png)

---
- Add Gender field on Pet Details screen.
![bg right h:500px](images/2023-11-03-01-06-07.png)

---
Let's check it with Preview function.

- Gender can be selected on the pet registration screen.
- The selected gender will be displayed on the pet details screen.

![bg right h:620px](images/2023-11-03-01-07-18.png)
![bg right h:620px](images/2023-11-03-01-07-56.png)

---
FYI
- If you are concerned about a blank space being displayed for a pet registered before you were able to select its gender, display the Record in the Pet Collection, click on that pet, and manually set its gender.
![h:420px](images/2023-11-03-01-08-51.png)

---
FYI

Multiple-choice input forms can be created using MultiselectDropdown in Marketplace.

If you need it, give it a try.
![bg right h:400px](images/2023-11-03-01-09-51.png)


---
#### Show or hide components depending on conditions.
If the weight is not registered yet, hide the Latest Weight on the Pet Details screen.

![bg right h:620px](images/2023-11-03-01-07-56.png)

---
- Select the label Latest Weight and its value and make them group.
![bg right h:500px](images/2023-11-03-01-12-04.png)

---
- Select Change Visibility

![bg right h:500px](images/2023-11-03-01-13-04.png)

---
- Change Visibility to Sometimes Visible
- Will be visible if... Select Current Pet > PetWeightLogs > Count in
- Set Is not equal to 0
![bg right h:620px](images/2023-11-03-01-14-11.png)

---
If you check with the Preview function, the Latest Weight is now hidden if the weight has not registered yet.

![bg right h:620px](images/2023-11-03-01-14-40.png)


This is the end of the improvements to the sample application for now.

---
#### クローン用URL
- You can clone the app I created by the CLONE APP button in the lower right corner of the following URL.
https://ryo-imahashis-team-6.adalo.com/improvedpethealthlog
![h:400px](images/2023-11-03-01-15-43.png)


---
## External integration
 If there is something you can't achieve with Adalo alone, you may be able to do so by integration with an external service.

Let's check is how to do it.

---
I will introduce four types of external integration methods.
- Marketplace external integration components
- Custom Action
- External Collection
- Linked Services

---
#### Marketplace external integration components
You can add a component to enable external integration from Marketplace.

![bg right h:480px](images/2023-11-02-23-54-00.png)

---
First, create a new application.
- Click CREATE NEW APP
![bg right h:300px](images/2021-11-26-22-00-12.png)
---
- Select Responsive App for Platform
![bg right h:500px](images/2023-10-29-13-09-34.png)

---
- Select "Blank Mobile First" for Template.
![bg right h:500px](images/2023-11-02-20-25-53.png)

---
- Enter MarketplaceComponentTrial for App Name.
- Other items can be set as you like
![bg right h:500px](images/2023-11-02-20-27-20.png)

---
##### Twitter Timeline Component
- Click the + button and click Explore Marketplace in ADD COMPONENT
![bg right h:700px](images/2023-11-02-20-49-56.png)


---
- INSTALL Twitter Timeline component
![bg right h:450px](images/2023-11-02-20-50-46.png)

---
Place the Twitter Timeline component.
- Add Link button to Home Screen
![bg right h:600px](images/2023-11-02-20-52-04.png)

---
- Add Link to New Screen from ADD ACTION
![bg right h:600px](images/2023-11-02-20-52-41.png)

---
- Select Blank Mobile First and create TwitterTimeline screen
![bg right h:600px](images/2023-11-02-20-54-06.png)

---
- Place Twitter Timeline component
![bg right h:600px](images/2023-11-02-20-55-36.png)

---
- Enter "tokyotech_jp" in the Twitter Handle Name field.
  - You can change the Handle Name to any Twitter account.
![bg right h:550px](images/2023-11-02-20-57-01.png)

---
Signup with the Preview function and click the Twitter button in Home, the TwitterTimeline screen will display a list of posts from the Twitter account with the Handle Name you entered.
![bg right h:700px](images/2023-11-02-20-58-47.png)

---
Several other components are provided for integration with external services. If you are interested, try them out.

Examples 
- Youtube (free)
- Google Maps (requires credit card registration, but available in a free trial)

---
#### Custom Action
Next, Let's learn how to handle data obtained from the API on the Adalo screen.

---
FYI
>An application programming interface (API) is a way for two or more computer programs to communicate with each other. It is a type of software interface, offering a service to other pieces of software.

https://en.wikipedia.org/wiki/API

---
Let's try API integration.
We will use The Cat API, which you can try for free. Please access the following URL
https://thecatapi.com/

![h:400px](images/2023-11-02-21-05-32.png)

---
FYI: For dog lovers, there is also The Dog API. It probably does the same thing as The Cat API. (I have not tried it, so I recommend using The Cat API first)
https://www.thedogapi.com/

![h:400px](images/2023-11-02-21-06-15.png)

---
Check the API documentation to see how to use the API.
- Go to the following URL
https://docs.thecatapi.com/

---
Use the API to get a random kitten image listed on the top page.
https://api.thecatapi.com/v1/images/search
![w:900](images/2023-11-02-21-41-46.png)

---
- CREATE NEW APP in the Adalo admin page
- Settings are as follows
  - Platform: Responsive App
  - Template: Blank Mobile First
  - App Name: ApiIntegrationTrial

![bg right h:250px](images/2021-11-27-02-15-47.png)

---
- Add link button to kitten image display screen on Home screen
- Set Link to New Screen from ADD ACTION
![bg right h:500px](images/2023-11-02-21-49-44.png)

---
- Select Blank Mobile First as Template and create Kitten screen
![bg right h:500px](images/2023-11-02-21-50-08.png)

---
- Place the Image component on the screen
- Leave the component settings as they are (we will set them later)
![bg right h:500px](images/2023-11-02-21-51-28.png)

---
- Add Change Kitten Image Button
![bg right h:550px](images/2023-11-02-21-54-13.png)

---
- Select New Custom Action from ADD ACTION
![bg right h:650px](images/2021-11-27-03-57-01.png)

---
You will be prompted to start a 14-day free trial (free of charge).
- Click "START FREE TRIAL."
![bg right h:400px](images/2023-11-02-21-28-44.png)

---
Trial has started.
- Click "CREATE NEW CUSTOM ACTION"
![h:500px](images/2023-11-02-21-27-32.png)

---
- Enter the following and click NEXT
  - Name: GetRandomKitten
  - Type: Create

![h:400px](images/2021-11-27-04-25-58.png)

---
- Set the API Request as follows
  - API Base URL: https://api.thecatapi.com/v1/images/search
  - Method: GET
- After setting, click RUN TEST REQUEST
![bg right h:450px](images/2023-11-02-21-59-14.png)

---
If the Test is successful, the data from the API will be displayed. These can be used in subsequent actions.
- Click SAVE CUSTOM ACTION.
![h:450px](images/2023-11-02-22-03-17.png)

---
Next, set the URL of the kitten image obtained from the API to the Image Source of the Image component.

The data from the API does not appear in the choices...
![h:100px](images/2021-11-27-05-52-10.png)

![bg right h:500px](images/2021-11-27-05-54-04.png)
![bg right h:500px](images/2023-11-02-22-08-34.png)

---
- Add Text Input component on the screen
- Change Name to "Invisible Kitten Image URL Input"
![bg right h:550px](images/2023-11-02-22-09-43.png)

---
- Click "Change Kitten Image Button".
- Select More > Change Input Value from ADD ANOTHER ACTION

![bg right h:550px](images/2023-11-02-22-10-48.png)

---
- Set "Invisible Kitten Image URL Input" for Input
- Set "GetRandomKitten > url" for Valoue
- Click "DONE"
![bg right h:500px](images/2021-11-27-06-02-37.png)

---
- Click on Image component
- Set URL to Other Components > Invisible Kitten Image URL Input
![bg right h:550px](images/2023-11-02-22-12-28.png)

---
- Open the LAYOUT tab of "Invisible Kitten Image URL Input" and click three eye icons in Visible On...
![bg right h:358px](images/2023-11-02-22-17-03.png)

---
Check with the Preview function.

Click the CHANGE button to see the kitten image.
![bg right h:700px](images/2023-11-02-22-19-13.png)

---
FYI

- Data obtained from the API in a Custom Action can be used in subsequent Actions.If you want to use that data in a component, use one of the following methods.
  - Set the data to the value of Text Input on the same screen in the subsequent Action's Change Input Value, as in this case, and load it. 
  - Or, you can save the data to a database in a subsequent Action and load it from another component. 
     - Example: https://help.adalo.com/integrations/custom-actions


---
Caution

Currently, Custom Action has some limitations.
- Custom Action does not work with the Submit button of the Form component.
- If a Custom Action is used as an Action for an entire screen, the data retrieved as an API response cannot be used in subsequent Actions.
- Cloning the app does not copy Custom Action. If you clone the app containing the Custom Action, you must re-create it manually.

---
#### External Collection
This section introduces how to handle data acquired from the API as a collection in Adalo.

If you want to acquire multiple data at once and list them on the screen, use External Collection instead of Custom Action.

---
Add "?limit=10" to the end of the previous API to get 10 cat images.
https://api.thecatapi.com/v1/images/search?limit=10
![h:450px](images/2023-11-02-22-25-58.png)

---
- In External Collections in Database, click "ADD COLLECTION".
![bg right h:700px](images/2023-11-02-22-27-40.png)

---
- Set the following and click NEXT
  - Collection Name: Kittens
  - Base URL: https://api.thecatapi.com/v1/images/search?limit=10
![bg right h:530px](images/2023-11-02-22-28-51.png)


---
In Adalo, five Endpoints (access methods) can be set for each resource (Kittens in this example) to be accessed by the API.

Depending on the specification of the API, you may need to modify it to match your needs, but in this case, you can click NEXT as is.
![bg right h:500px](images/2023-11-02-22-30-19.png)

---
- Run the test and if successful, click "SAVE COLLECTION"
![bg right h:650px](images/2023-11-02-22-30-57.png)


---
An External Collection has been created.

All data to be retrieved from the API are set as properties.
![bg right h:400px](images/2023-11-02-22-31-55.png)

---
List the data.
- Add "Kitten List Link" button on Home screen
- Add LINK to NEW SCREEN from ADD ACTION
![bg right h:600px](images/2023-11-02-22-34-20.png)

--- 
- Select BlankMobileFirst and create "KittenList" screen
![bg right h:600px](images/2023-11-02-22-35-30.png)

---
- Add Image List from ADD COMPONENT
![bg right h:420px](images/2023-11-02-22-38-15.png)


---
- Set as a list of Kittens Collection
- Set "kitten url" to Image URL
- Set "Don't show anything" to "If there's no image..." 
![bg right h:600px](images/2023-11-02-22-41-37.png)


---
- Hide Text and Icon because they are not needed.
![bg right h:500px](images/2023-11-02-22-46-58.png)


---
You can see the list of cats by Preview.
![bg right h:700px](images/2023-11-02-22-48-01.png)


---
#### Integration Service
With Custom Action and Extenal Collection, it may be difficult to understand how to use the API from the documentation.

Let' try the service that can make external integration easy.

---
There are many different integration services, but this time we will try a service called Zapier that is built into Adalo.
![h:500px](images/2021-11-26-16-42-00.png)


---
Adalo does not have an email sending function.

This time, we will use Zapier to link Adalo and Gmail so that a Welcome email will be automatically sent to people who SignUp to the application.

![bg right h:200px](images/2022-11-12-19-46-27.png)

---
- Create a Google account, as you will need it to use Gmail.
  - If you already have one, you can use that account, so you do not need to create new one.
  - If you don't have one, click this URL and create one. 
https://accounts.google.com/signup/v2/webcreateaccount?continue=https%3A%2F%2Faccounts.google.com%2FManageAccount%3Fnc%3D1&dsh=S50453738%3A1637917137418951&biz=false&flowName=GlifWebSignIn&flowEntry=SignUp

---
Once your Google account is ready, we will set up the integration with Zapier.
- Select the Submit Button on the Sign Up screen of the ApiIntegrationTrial app.
- Select ADD ANOTHER ACTION > New Integration > Gmail
![bg right h:650px](images/2023-11-02-23-09-00.png)

---
- Click Use this Zap at the top, Send Gmail emails for new Adalo records.
![bg right h:400px](images/2023-11-02-23-11-50.png)


---
- Click Continue
![bg right h:400px](images/2023-11-02-23-12-46.png)


---
Zapier setup window will open
- Click Sign In under Connect Adalo on the right side.
![w:1000](images/2023-11-02-23-14-09.png)


---
- Log in to Adalo
![w:1000](images/2023-11-02-23-15-37.png)

---
- Click ALLOW ACCESS
![bg right w:400](images/2023-11-02-23-16-44.png)

---
- Set Trigger as follows
  - App: ApiIntegrationTrial
  - Collection: Users
![bg right w:400](images/2023-11-02-23-18-45.png)

---
- Click Test trigger
![bg right w:400](images/2023-11-02-23-19-28.png)


---
- When a record is found, click Continue with selected record
![bg right w:400](images/2023-11-02-23-20-08.png)


---
- Click Connect Gmail Sign in
![bg right w:400](images/2023-11-02-23-20-54.png)


---
- Select Account
![bg right w:400](images/2023-11-02-23-22-03.png)

---
- Click Allow
![bg right w:400](images/2023-11-02-23-22-29.png)

---
Set Action.
- Set your Gmail address in From
- Set the application name in From Name
- Enter Subject and Body as you like.
- Click Continue
![bg right h:700px](images/2023-11-02-23-27-14.png)


---
- If the "to:" address is your actual email address, click "Test step" to confirm receipt of the email.
  - If not, click on "Skip test" (because the test will fail to send the email).
![bg right h:700px](images/2023-11-02-23-29-13.png)

---
- Click Publish

Integration setting with Zapier is done.
![bg right h:600px](images/2023-11-02-23-29-49.png)

---
Make sure a Welcome email is sent to you in Adalo's ApiIntegrationTrial app.
- Enter your actual email address in the Preview function and Signup, and you will receive an email within 2 minutes!
![w:500](images/2023-11-02-23-31-10.png)


---
FYI: You can also manually run Zap immediately from the Zap listing screen without waiting 2 minutes.
- Go to https://zapier.com/app/zaps
- Select the Zap you want to run and click "Run Zap"
![h:500px](images/2023-11-02-23-43-58.png)

---
With Zapier, you can integrate various other services.

When something comes up that cannot be successfully achieved with Adalo alone, you may should consider whether it can be achieved by integration with other services.
![bg right h:480px](images/2023-11-02-23-46-22.png)

---

That's all for external integration in Adalo.

---
## Exercise 2
- Develop one app you want use.
- If you cannot think of an app you want to use, develop a team member management app with the following functions.
    - Registration of team members
    - Display of member list
    - Displaying member details
    - Update member information
    - Delete members
    - Original functions(as many as you want).

---
We would like everyone to make a presentation at the end (if time permits).

When the app is ready to use, share the URL on Slack for everyone to see.

---
Notes for the exercise
- While NoCode tools make it easy to create apps, they may not be able to realize complex UI and functions.
  - If you get stuck, think about how you can achieve what you want to do with a simple UI and functions.
    - For example: do not include many components in one screen, divide the screen into separate screens, etc.

---
FYI
- Adalo has a number of apps that can be cloned, so it might be a good idea to see if there is something similar to what you want to do.
  - App Templates
  https://www.adalo.com/app-templates
  - UI & Functional Kits
  https://www.adalo.com/cloneable-kits

---
Examples of apps that can be cloned
- Event Calendar https://www.adalo.com/cloneables/event-calendar
- SNS follow function https://www.adalo.com/cloneables/follow-function
- Facebook clone https://www.adalo.com/cloneables/facebook-clone
- Blog app https://www.adalo.com/cloneables/minimal-blog-app
- Product sales app https://www.adalo.com/cloneables/ecommerce-app


---
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass:
# :hourglass:

---
#### Presentation of Exercise Results
Please make a presentation about the application you made in the exercise.

---
## Summary
- After introducing Adalo and learning how to design a database, we developed an application on the subject of a pet health care application.
- We introduced the following four methods of external integration with external services.
  - Marketplace external integration component
  - Custom Action
  - External Collection
  - Integration Service

---
- Based on what we have seen so far, it is a good idea for the team to consider whether the application they want to create in the Development Phase can be realized with Adalo.
- Next time, I will give a lecture on Bubble, a no-code tool. Please look forward to it!

---
# That's all!
# Thank you for your hard work!
