---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Naotake KYOGOKU'

page_number: true
paginate: true
---

**Programming Boot Camp**

# Bubble Basic #2-2

**Tokyo Institute of Technology 2022/11/26**
　
　
　
　
　
　　　　　　　　　　　　　　　　　　　**Naotake KYOGOKU**


---

## Table of Contents

- External Collaboration with Bubble
- Tips for Collaboration with Bubble
- Team Development Exercise
- Summary

---

### Confirmation of what we will do this time

- First, you will learn how to integrate your Bubble application with external services.
- Next, we will show you some tips and tricks for working together on a single application.
- Finally, we will practice and present the application development in teams in the Development Phase.

---

## External Collaboration with Bubble

![w:900px](images/2022-11-23-17-57-09.png)

---

The functionality of this screen includes the following

- YouTube video listings
- Social login using Google Account
- Dynamic search of YouTube video listings

![w:650px](images/2022-11-23-17-57-09.png)

---

##### First, we need to prepare a new application as a foundation.

- Bubble I would like to copy the application used in the first lecture and use it again.
- Go to https://bubble.io/home?tab=apps

---

- A list of Bubble applications created under your account will be displayed.
- In the list, click COPY under the application you created in the first Bubble class.

![bg right w:600px](images/2022-11-23-15-36-25.png)

---

- A dialog box for the name of the application after copying is displayed.
- Leave the `Copy the application database content` checkbox OFF, since you will not be using the previous data.
- Click COPY

![bg right w:600px](images/2022-11-23-15-41-06.png)

---

- When the copying is finished, it is OK if the edit screen (index) of the copied application is displayed

![w:850px](images/2022-11-23-15-42-33.png)

---

##### Preparation for YouTube integration

- We will do the necessary preparations for displaying a list of YouTube videos.
- In this lecture, we will use various APIs provided by Google's cloud service "Google Cloud Platform".
  - Think of it as Google's version of Amazon's "Amazon Web Service" (AWS).

---

- Access the following URL
  - https://console.developers.google.com/
- Sign in with your Google Account
  - If you do not have a Google Account, please create one.

![bg right w:550px](images/2022-11-23-15-44-32.png)

---

- After logging in, when you access the Google Cloud Platform (GCP) screen for the first time, you will see a dialog like this, select your country, check the Terms of Service, and "Agree and Continue".

![w:600px](images/2021-11-25-20-10-55.png)

---

- Once you agree, you will see the API and Services dashboard, and click the Create Project link to create a project (box) for this lecture.

![w:1000px](images/2021-11-25-20-12-13.png)

---

- When the Create New Project screen appears, specify an appropriate name for the project and create it.

![bg right h:460px](images/2021-11-25-20-13-50.png)

---

- When the creation is complete, the dashboard of the created project will be displayed.
- If you see the name of the project you created at the top of the screen to the left of Google Cloud, you are good to go.

![bg right w:600px](images/2022-11-23-15-58-15.png)

---

- Next, we will issue the authentication key needed to display the YouTube video list.
- Type "API" in the search box at the top of the screen to open the API and Services menu

- Select "APIs and Services" in the "Projects and Pages" block from the list of suggestions

![bg right h:400px](images/2022-11-23-15-53-45.png)

---

- When the API and Services page opens, select "Credentials" from the left menu.
- The right panel will change to "Credentials", click "+ Create Credentials" at the top of the screen.
- Select "API Key" from the pop-up window.

![w:800px](images/2022-11-23-16-01-40.png)

---

- You will then get a pop-up message saying that your API key creation is complete, so take note of the value.
- You will be asked to limit the keys, but we will delete these keys at the end of the lecture, so we will leave it as is.

![bg right h:350px](images/2022-11-23-16-02-41.png)

---

- Now that we have issued the key to retrieve the YouTube listings from Bubble, let's configure the Bubble side.
- First, let's prepare to get the YouTube listings from Bubble via API.

---

##### Preparing Bubble for API integration

- Select Plugins from the left menu and check that the `API Connector` is already present in the Installed Plugins.

![bg right h:500px](images/2022-11-23-16-06-15.png)

---

- If it is not included, click the Add plugins button.
- Search for "API" and install the plugin `API Connector`.

![bg right h:500px](images/2021-11-25-20-24-21.png)

---

- This plugin is designed to connect Bubble apps to other APIs that are publicly available, and to information on the other side of those APIs.
- Some Bubble plugins are specialized for specific APIs and are simpler to configure than the API Connector.
- Let's use the YouTube API via the API Connector plugin in its most basic form to display a list of videos.

---

- Now let's configure the YouTube API to use it
- In the Plugins tab, select "API Connector" from the Installed Plugins list.
- In the right panel, you will see a summary of this plugin, and below that, click "Add another API" to start setting up your new API connection

![w:650px](images/2021-11-25-20-31-17.png)

---

- "Add another API", you should see API configuration components like this
- Here is a brief description of each item and its settings

![w:950px](images/2022-11-23-16-09-10.png)

---

1. API Name: Group name for this API linkage
  - In this case, it is YouTube.

![w:1000px](images/2022-11-23-16-12-12.png)

---

2. Authentication: Common authentication method for APIs under this group.
  - In this case, "None or self-handled".

![w:1000px](images/2022-11-23-16-12-12.png)

---

3. Shared headers for all calls: Common header information to be specified for all APIs under this group.
  - Not specified at this time

![w:900px](images/2022-11-23-16-12-12.png)

---

4. Shared parameters for all calls: Common parameter information to be specified for all APIs under this group.
  - Not specified at this time

![w:900px](images/2022-11-23-16-12-12.png)

---

- Next, let's set up the API for this group.
- Click on the "expand" link to the right of the "API Call" block on the previous screen.

![w:800px](images/2022-11-23-16-14-34.png)

---

- Then you will see the specific API configuration items, which are briefly explained below

![w:900px](images/2022-11-23-16-15-18.png)

---

1. Name: A specific API name.
  * In this case, enter "search".

![w:800px](images/2022-11-23-16-20-11.png)

---

2. Path: URL of the specific API
  * In this case, enter `https://www.googleapis.com/youtube/v3/search`.

![w:700px](images/2022-11-23-16-20-11.png)

---

3. Headers: Header information specific to this API
  * Not specified at this time

![w:800px](images/2022-11-23-16-20-11.png)

---

4. Parameters: Parameter information specific to this API
  * In this case, the following two parameters are specified: Private / Allow blank / Optional as shown in the attachment. 1.
    1. Key: `key`, Value: the API key you just issued in your Google account 2.
    2. Key: `q`, Value: Keyword for searching behavior on YouTube (feel free to specify)

---

- When everything is set up, it looks like this

![w:950px](images/2022-11-23-16-21-06.png)

---

- When you are done, check to make sure your settings are correct
- Click the "Initialize call" button at the bottom

---

- You probably got back an error message with Status code 403
- The content of the message is as written, but in summary it looks like this


> YouTube Data API v3 is disabled in your project.
> Please visit this URL to enable it and try again.


![bg right h:500px](images/2022-11-23-16-22-26.png)

---

- It seems that the YouTube Data API we used this time is not enabled on each person's Google account.
- This is because Google has turned off the function that not everyone will use from the beginning, and only those who need it can turn it on by themselves.
- So, since we want to use the YouTube Data API, let's access the URL in the message to enable it.
  https://console.developers.google.com/apis/api/youtube.googleapis.com/overview?project={各人のプロジェクトID}

---

- You should then be redirected to the "YouTube Data API v3" screen.
- Click "Enable" to activate it as indicated on the screen.

![w:1000px](images/2022-11-23-16-26-30.png)

---

- After a few moments, you should be taken to a screen like this
- If the red line at the top of the screen reads "Disable API," the activation was successful.

![w:900px](images/2022-11-23-16-27-18.png)

---

- Now that the YouTube Data API has been activated, go back to the Bubble screen and click the "Initialize call" button.
- If successful, you should see a popup saying "Returned values - search

![bg right h:600px](images/2021-11-25-20-57-48.png)

---

- This shows the result (response) of executing the "https://www.googleapis.com/youtube/v3/search" API that you have set up this time

![bg right w:600px](images/2022-11-23-16-28-15.png)

---

I won't go into details, but the three main points are as follows.

- The `items(list)` is the list of videos in the search results.
- The type of the list is `search item`, which means that it is the data of multiple items in the search results.
- And the most important part is the `id videoId`.

---

- As you may know if you have seen YouTube before, this VideoId is the information that uniquely identifies each video, and this Id is also required to display the video on the screen.
- Other items that do not refer to any particular field are confusing, so select `Ignore field` from the pull-down menu.
- By doing so, when you handle it as Dynamic data, it will not be displayed in the choices, and you will not have to worry when you select a setting item.

---

- This is what it looks like when everything is set up
- When you are done, click "SAVE" to save your settings

![bg right h:600px](images/2022-11-23-16-30-42.png)

---

##### Preparation of Screen Display

- Now that Bubble's API integration is ready, it's time to set up the screens!
- We believe that you have already mastered screen setup in the previous and current lectures, so we will just give you an overview and let you try to build your screen layout.

---

- Create the "video_list" screen by cloning the pet_list page.
- Delete all the contents of each cell in the Repeating Group.
- Instead, place Video in the Visual elements to fill the cell.
- It looks like this.

![bg right w:600px](images/2022-11-23-16-35-46.png)

---

- Now that we have a layout, let's actually set up the YouTube listing.
- First, the Type of content in the Repeating Group will be the `search item` type that we just checked when executing the API.
- The type of data to be repeated will now be each YouTube video.

![bg right h:600px](images/2022-11-23-16-38-00.png)

---

- Next is Data source. This time, we will target the list of YouTube videos obtained from the API.
- If you look at the candidates from Click, you will find an item called `Get data from an external API`, so select it.

![bg right h:600px](images/2022-11-23-16-39-26.png)

---

- Next to the Get data from an external API popup, select the API provider pull-down.
- Then select the `YouTube - search` that you have just set in the pull-down menu.
  - (The hyphen before is the API group name, and the hyphen after is the name of the specific API.

![w:500px](images/2022-11-23-16-41-01.png)

---

- Once the API Provider is set, close it with CLOSE
- Then, in the original Repeating Group, select `'items` as the Data source.
- Now you have specified that the list of videos (items) included in the API results will be repeated.

![bg right w:600px](images/2022-11-23-16-43-51.png)

---

- Next, let's set up each cell, but first, let's set up everyone!

- Hint :bulb:
  - Video source is YouTube
  - Then you will see an item called Video ID, which should refer to the `Video Id` you saw when you set up the API earlier.

![bg right h:380px](images/2021-11-25-21-21-57.png)

---

- Something like this.

![bg right h:400px](images/2021-11-25-21-22-21.png)

---

- Now you're all set! Let's preview it now!
- Do you see a list of videos for the keywords you specified in the API in advance?

---

![w:1100px](images/2022-11-23-16-53-19.png)

---

##### Let's try Google Login!

- Next, let's try signing in to the Bubble app with your Google account!
- First, install the Google plugin

![bg right h:500px](images/2021-11-25-17-18-29.png)

---

- Select the Google plugin you have installed
- Check the `Use a generic redirect URL` box in the right panel.
  - Note down this URL as well, but since you cannot select it on the screen, please replace the app name part of the URL below with your own app name and write it down. 😅
  - `https://{Your App Name}.bubbleapps.io/api/1.1/oauth_redirect`

---

![w:1150px](images/2021-11-25-21-35-23.png)

---

##### Prepare to authenticate back to your app after logging in to Google

- Access the Google Cloud Platform screen

https://console.developers.google.com/

- Display the same API and Services screen as before

---

- Select the project and choose "OAuth Consent Screen" from the left menu

![w:800px](images/2022-11-23-17-01-25.png)

---

- Select "External" for User Type and click Create

![w:700px](images/2022-11-23-17-02-41.png)

- Fill in the required information on the next page

---

- App Information
  - App name: The name of your app as created in bubble
  - User Support Email: Your Google Account email address

![bg right h:500px](images/2022-11-23-17-05-41.png)

---

- Approved Domains
  - bubbleapps.io
- Developer Contact Information
  - Your Google Account email address
- "Save and Continue"

![bg right h:450px](images/2022-11-23-17-06-31.png)

---

- Scope is "Save and Next" without changing any settings.

---

- Enter your Google email address as the test user.
- After setting up, save and continue.

![bg right h:500px](images/2022-11-23-17-07-47.png)

---

- Now that registration is complete, we will issue the credentials.
- Select "Credentials" from the left menu and click "+ Create Credentials".
- Select OAuth Client ID from the submenu

![w:1000px](images/2022-11-23-17-08-58.png)

---

- The Create OAuth Client ID screen will appear, enter the following information and "Save".

- Application Type: Web Application
- Name: `Bubble OAuth

![bg right h:700px](images/2022-11-23-17-11-46.png)

---

- Authorized redirect URI: The URL that the Bubble side has noted when installing the Google plugin.
  `https://{Your App Name}.bubbleapps.io/api/1.1/oauth_redirect`

![bg right h:700px](images/2022-11-23-17-11-46.png)

---

- Click "Create."
- Then you will see a popup saying "OAuth client created", where the client ID and client secret are displayed, so write them down.
  - If you forget to write them down, you can download the JSON file.
- After writing down the information, click OK to close.

![bg right h:500px](images/2022-11-23-17-12-41.png)

---

##### Set the issued credentials on Bubble

- Return to the Google Plugin screen of Bubble, and enter the keys you have just obtained into the respective fields.
  - Client ID → AppID/API Key
  - Client Secret → App Secret

![bg right h:370px](images/2021-11-25-17-44-20.png)

---

- This completes the preconfiguration.
- Next, we will build the login function.

---

##### Replace the login mechanism with Google

- Open the header of the Reusable elements created in the previous lecture

![w:900px](images/2022-11-23-17-16-03.png)

---

- Open the Workflow tab and open the workflow for the login button
- Now only the action to go to the login page (index page) is set, so we will review this.

![w:700px](images/2022-11-23-17-19-41.png)

---

- Since we will be using the login screen provided by Google, we will delete the action to move to the login screen (index page) on the Bubble side.

![bg right h:600px](images/2022-11-23-17-22-01.png)

---

- Next we will set up a workflow for Google Login.
- Click here to add an action... Click here to add an action...
- Select Signup/login with a soccial network from Account

![bg right h:600px](images/2021-11-25-18-12-11.png)

---

- Signup/login with Google popup will appear
- Select Google as OAuth provider
- Since you have configured Google and Bubble plugins in advance, you can now use Google Authentication! 🙌

![bg right h:350px](images/2021-11-25-18-14-22.png)

---

- 折角なのでログイン成功したらヘッダー上部にアカウント名と画像を表示してみましょう

![w:800px](images/2022-11-23-17-41-33.png)

---

- Switch to the Design tab and display the following three components from the Elements tree, which are currently hidden
  - (If you don't do this, it will be difficult to see the image after the image is added.

![bg right h:600px](images/2022-11-23-17-27-53.png)

---

- Select Image from Visual elements and place the image between the "Pet Register" link and the "Log in" button.
  - Make sure it is a 50 x 50 square

![w:950px](images/2022-11-23-17-32-01.png)

---

- Then, set up the image references.
- If you are a Bubbler, you know what to do!
- Dynamic image for dynamic display
- The image you want to display is the profile image of the currently logged in user's Google Account.

---

- Something like this.

![bg right h:450px](images/2021-11-25-18-36-17.png)

---

- Now let's preview!
  - If you have the same email address in User of Data as the Google email address you are going to use to check the operation, please delete it.
- When you click the "Login" button, you will be redirected to the Google login screen, and when you login there, you will be redirected back to the Bubble side, right?
- By the way, when you log in, the email address information of the Google account you logged in is registered in the User data on the Bubble side.
  - Of course, your password is not saved, so don't worry! :smile:

---

![w:800px](images/2022-11-23-17-40-59.png)

![w:800px](images/2022-11-23-17-41-33.png)

---

##### Finally, let's incorporate a search function using the YouTube API

![w:900px](images/2022-11-23-17-57-09.png)

---

- Currently, the YouTube API authentication key and search keywords are fixed.
- So let's change them as follows
  - Authentication keys are obtained from the logged-in user information (add a new field)
  - Search keywords can be entered and searched from the screen.

---

I'll give you a hint on the next page so you can try it first!

---

- First, add a field called `key` for the User and set it in advance.
  - (Normally, it would be more natural to have the user enter the key himself, but for the sake of time, we will skip the API key setting screen this time.
- If you want to dynamically set API parameters in the process, first remove the fixed values and uncheck `Private` so that you can specify the parameters when calling the API from a DataSource, etc.
- Place a new search element (text box and search button) on the video_list page, and when the search button is clicked, search via YouTube API and set the result to the Repeating Group.

---

# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass:
# :hourglass:

---

- Here are the important points
- First, add a field called `key` for the User type

![](images/2021-11-25-22-32-01.png)

---

- Then, set the authentication key (API key) obtained this time to the registered User in advance

![](images/2021-11-25-22-32-29.png)

---

- Next, the YouTube API settings look like this

![bg right h:400px](images/2021-11-25-22-19-37.png)

---

- The key point is that we have removed the Value values for items that we want to specify dynamically, and unchecked the Private checkbox.
- This allows the values of these parameters to be specified when using the API.

![bg right h:400px](images/2021-11-25-22-19-37.png)

---

- In addition, let's add two search options
- key: `maxResults`, the number of data to retrieve in one search.
  - Default is 5.
- key: `type`, type of data to search.
  - By specifying `video`, you can search only videos.

![bg right h:400px](images/2022-11-23-17-48-22.png)

---

- Next, empty the Repeating Group's Data source.
- The target data to be displayed is set in the workflow of the new search function, so there is no problem even if this field is empty.

![bg right h:500px](images/2021-11-25-22-21-24.png)

---

- Next, set up a workflow for the newly prepared search button for the keyword search.
- In this case, the action is for an element (Repeating Group), so select "Display list" in the "Element Actions" section.

![bg right h:600px](images/2021-11-25-22-27-04.png)

---

- For Data source, select Get data from an external API to display data via API.
- Then select `YouTube - search` for the API provicer, and you should see two params that were not there before.
- This is because you have just unchecked the Private checkbox for the parameters you want to specify dynamically in the YouTube API settings.
- The value to be specified here is the usual Dynamic data.

---

- Here's what it looks like when set up

![w:1100px](images/2022-11-23-17-55-08.png)

---

#### Let's preview it!

- Did you see the list of videos you entered in the keyword field while logged in?

![w:750px](images/2022-11-23-17-57-09.png)

---

- How did you like it?
- I think that by working with APIs, the range of things we can do with Bubble has expanded even more!
- There may be teams that use external APIs at the camp, and if so, let's put what we learned today to use and practice API integration!

---

## Tips for Collaborating with Bubble

Here are some tips to help you and your team collaborate with Bubble

---

#### How to invite team members in Bubble

To co-edit one app with your team members...
- You will need to prepare one account for your team, and then everyone will log in to that account and use it together.

---

- Bubble has the ability to co-edit in the regular way, but... 💰💰💰

![h:450px](images/2022-11-23-20-14-14.png)

---

#### Notes on simultaneous edits in Bubble

- Avoid simultaneous editing on the same element (it will be overwritten by edits made later).
  - For this reason, it is recommended to assign a person in charge of each screen and avoid simultaneous editing of the same screen.
- Other than that, there are no special notes.
- Edits are reflected in real time on other people's screens.
  - Not only screen edits, but also database and Workflow edits are reflected in real time.
- If you divide the work by screen, you can develop without difficulty.

<!-- ---
モブプログラミングの紹介?
- ドライバーとナビゲーターみたいなお話を盛り込む？ -->

---

## Team Development Exercise

- Try developing one new app with your DevelopmentPhase team!
  - Make it different from the one you are planning to develop in DevelopmentPhase!
- You can choose to use either Adalo or Bubble!
  - You can choose the one you plan to use in DevelopmentPhase, or you can choose both!
- Make sure everyone has a hand in it!

---

#### Example of how to divide up the work

- First, everyone should work together to identify screens and functions and design the database.
- Assign a person to be in charge of each screen (e.g., in charge of the registration screen, the list screen, the detail screen, the update screen, etc.)
- There is also a method in which multiple people work on a single PC. In this case, the person in charge of operating the PC and the person giving instructions should switch periodically.

---

# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass:
# :hourglass:

---

#### Presentation of Exercise Results

Let's have each team present about the apps they made in the exercise!

---

## Summary

- That's all for this Learning Phase lecture!
  - Have you mastered Adalo and Bubble?
  - Did you get an idea of how team development works?
- From next time, we will start the Development Phase, where we will brush up and develop the ideas presented by each team.
  - In preparation for this phase, let's reconfirm our ideas and select tools (Adalo, Bubble, or others?) to be used in the development phase. (Adalo? Bubble? Other?)) to be used in the development.

Translated with www.DeepL.com/Translator (free version)

---

### Finally.

- Remove API keys and OAuth information issued by Google Cloud Platform!

---

# That's all!
# Thank you for your hard work!
