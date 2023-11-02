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
- There is a link to the weight Record screen.
![bg right h:700px](images/2023-11-02-18-50-07.png)

---
###### Weight Record screen
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
Let's Preview the appearance of the pet registration screen.
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
  - The Rectangle is now hiding the Text because the one on top is displayed in front of the others.

![bg right h:500px](images/2021-10-22-01-38-45.png)

--- 
- Let's switch the order. Put Text at the top and Rectangle at the second.
  - The Text is now in the foreground, and the Rectangle makes it easier to see the white text!
![bg right h:500px](images/2021-10-22-01-41-54.png)

---
Next, let's add one more pet.
- Select the three components you added (Image, Rectangle, Text) on Canvas, and click "MAKE GROUP".
![bg right h:500px](images/2021-10-22-01-53-38.png)

---
- Copy and paste (`Ctrl + C` and `Ctrl + V` on Windows, `Command + C` and `Command + V` on Mac) the created Group while it is selected, and place the duplicated Group under first pet.
![bg right h:700px](images/2021-10-22-02-01-32.png)

---
- Change the second Image and Text to those of another pet.
![bg right h:700px](images/2021-10-22-02-06-16.png)

---
Next, add the link to the pet registration page.
- Select "Action Button" from ADD COMPONENT
![bg right h:370px](images/2021-10-22-02-11-11.png)

---
- Place it in the lower right corner of the screen.
- Change the "Icon and Text Color" to "Default Background"(White).
![bg right h:500px](images/2021-10-22-02-26-03.png)

---
- Select "ADD ACTION"
  - Select "Link"
    - Select [Pet Registration Screen Name]
![bg right h:500px](images/2021-10-22-02-28-24.png)

---
Let's add a link from the pet registration screen to the pet list screen.
- Select the Register button on the Pet Registration page
- ADD ACTION -> Link -> Select [Pet List Screen Name]
You can't register your pets yet because you just added a link (Data registration is in the next lecture).
![bg right h:500px](images/2021-10-22-02-33-55.png)

---
- Change the destination of the SIGNUP button on the SignUp screen and the LOGIN button on the Login screen from Home to the Pet List screen.
![bg right h:340px](images/2021-10-22-03-52-31.png)

---
- The Home screen that was created by default is no longer needed. You can delete it.
![bg right h:480px](images/2021-10-22-03-57-57.png)

---
Preview the appearance of the Pet List screen.
- Change the "Screen Navigation Type" of the Pet List screen to "Home Screen" as you did when you previewed the Pet Registration screen.
- After logging, you can see the Pet List screen.

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
- Select "Info with Links" from ADD SCREEN and enter the Screen Name.
![bg right h:650px](images/2021-10-22-02-58-46.png)

---
- Upload one of the photos used in the Pet List screen in Image Source.
![bg right h:500px](images/2021-10-22-03-05-37.png)


---
- Rewrite the Text with the label "Birthday" and its value, and the label "Latest Weight" and its value.
![bg right h:700px](images/2021-10-22-03-18-32.png)

---
- Change the Text named "Link 1" to "Weight Log"
- Leave Link 2 as it is.
(This will be used as a link to the screen created in the exercise)

![bg right h:700px](images/2021-10-22-03-28-26.png)

---
Let's make it possible to move from the pet list screen to the pet detail screen.
- Select the Group that contains the components for the first pet in the Pet List screen, and click "ADD ACTION" -> "Link" -> [PetDetailScreenName]

![bg right h:450px](images/2021-10-22-03-31-30.png)

---
- Preview the appearance of the Pet Detail screen.

The pet detail screen seems OK.
![bg right h:700px](images/2021-10-22-04-07-06.png)

---
###### Weight Record screen
- A graph showing the transition in weight is displayed.
- You can enter your pet's current weight.
- You can add your pet's weight by pressing the button.

Let's create this screen.
![bg right h:700px](images/2021-10-22-16-42-42.png)

---
- Select "App Bar" from ADD SCREEN and enter the Screen Name.
![bg right h:700px](images/2021-10-20-06-26-12.png)

---
- To create a Chart, we need to prepare a database, which will be explained in the next lecture.
- This time, paste the Chart image instead of using actual chart.
  - I'll share the Chart image with you via Slack.
  (You can also take a screenshot of the image on the right and use it)
![bg right h:350px](images/pet-weight-log-chart.png)

---
- Add an Image from ADD COMPONENT and upload the Chart image.
![bg right h:500px](images/2021-10-22-16-33-13.png)

---
- Add "Text Input" from ADD COMPONENT.
- Change "Type" to "Number".
- Change "Placeholder" to "Enter current weight".
![bg right h:500px](images/2021-10-22-16-35-03.png)

---
- Add a "Text" from ADD COMPONENT.
- Change the value to "Weight(kg)".
![bg right h:500px](images/2021-10-22-16-35-39.png)

---
- Add "Button" from ADD COMPONENT.
- Change Text to "Add".
![bg right h:500px](images/2021-10-22-16-36-06.png)

---
Set up a link from the pet detail screen to the weight record screen.
- Set up a link to the weight record screen with "Click Action" of the Group containing "Text:'Weight Log'" in the pet detail screen.
![bg right h:500px](images/2021-10-22-12-40-18.png)

---
Let's preview the screen.

The weight record screen seems OK.
![bg right h:700px](images/2021-10-22-16-42-42.png)

---
We have created all UI for the sample app :tada:

![h:383px](images/2021-10-20-06-09-56.png)![h:383px](images/2021-10-20-06-16-03.png)![h:383px](images/2021-10-22-02-23-09.png)![h:384px](images/2021-10-22-02-40-24.png)![h:383px](images/2021-10-22-04-07-06.png)![h:383px](images/2021-10-22-16-42-42.png)

---
#### URL for cloning
- You can clone the application from the following URL, and use it to check completed version.
https://previewer.adalo.com/014fd9d1-80c6-4325-899a-d943e778c865

![bg right h:400px](images/2021-10-22-17-31-06.png)

---
## Exercise
- Create your own screen that will be the transition destination for "Link 2" on the pet details screen.
- Alternatively, you can create a new app as you like.

When you are ready, share the URL on Slack to make it available for everyone.

![bg right h:500px](images/2021-10-22-18-37-12.png)

---
#### Notes about the exercise
- Components and Screens named "xxxxList" may be difficult to use because they need to be connected to the database, which will be explained in the next lecture.
  - If you face a problem and can't solve by yourself, I recommend you to avoid using "xxxxList" for today.
- While the NoCode tool allows you to create apps easily, it may not allow you to achieve complex UI and functions.
  - If you are stuck, think about how you can achieve what you want to do with a simple UI and functions.
    - For example: Avoid including too many components in one screen(separate them into multiple screens).

---
#### Presentation of exercise results
(If there is enough time)

Would you like to present the app you made in the exercise?

---
## Summary
- In this lecture, we learned about Adalo and created the UI of the pet health management application.
  - We used only simple components that do not require a database.
- In the next lecture, we will continue to use Adalo to build a database that matches the UI we created today, and make it possible to manipulate data from the app. 
  - By using a database, various functions can be realized and the UI can be easily created. I hope you'll enjoy it!

---
# That's all!
# Thanks for your time!