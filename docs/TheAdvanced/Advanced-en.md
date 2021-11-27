---
marp: true
theme: gaia
size: 16:9
header: '　　　　　　　　　　　　　　　　　　　　　　　　　　　　Copyright Ryo Imahashi, Naotake Kyogoku'

page_number: true
paginate: true

---

**Programming Boot Camp**

# Advanced Lecture

**Tokyo Institute of Technology 2021/11/27**
　
　
　
　
　
　　　　　　　　　　　　　　　　**Ryo Imahashi, Naotake Kyogoku**



---
## Table of Contents
  - Review and confirmation of what we will do
  - External Integration
  - Tips for collaborating with no-code tools
  - Team development exercise
  - Summary

---
## Reflection and confirmation of what we will do this time
- In the previous four lectures, we have learned how to develop applications using two no-code tools, Adalo and Bubble.
- In this lecture, we will first learn how to integrate Adalo and Bubble with external services.
- Next, we will show you some tips and cautions about Team collaboration.
- Finally, we will practice and present application development in Development Phase teams.

---
## External Integration
If there is something you cannot achieve with Adalo or Bubble alone, you may be able to achieve it by collaborating with external services.

We will show you how to do that.

---
#### External Integration with Adalo
The following three methods of external integration are introduced.
- Marketplace external integration component
- Custom Action
- External Collection

---
##### Marketplace external integration components
You can add a component that enables external integration from Marketplace.

![bg right h:600px](images/2021-11-26-21-49-01.png)

---
First, let's create a new application.
- Login to Adalo
Go to https://app.adalo.com/login
- Click CREATE NEW APP
![bg right h:300px](images/2021-11-26-22-00-12.png)

---
- Select Native Mobile App for Platform
Click ![bg right h:500px](images/2021-11-26-21-53-43.png)

---
- Select Blank for Template.
![bg right h:500px](images/2021-11-26-09-00-44.png)

---
- For App Name, enter MarketplaceComponentTrial.
- Please set the Color freely.
![bg right h:500px](images/2021-11-26-21-56-35.png)

---
###### Twitter Timeline Component
- Press the + button and click Explore Marketplace in ADD COMPONENT
![bg right h:700px](images/2021-11-26-22-02-19.png)


---
- INSTALL the Twitter Timeline component
![bg right h:450px](images/2021-11-26-08-57-37.png)

---
Place the Twitter Timeline component.
- Add a link button to the Twitter screen to the Home Screen.
![bg right h:600px](images/2021-11-26-22-21-56.png)

---
- Add Link to New Screen from ADD ACTION
![bg right h:600px](images/2021-11-26-22-23-29.png)

---
- Select "App Bar" in Template and create a "Twitter Timeline" screen.
![bg right h:600px](images/2021-11-26-22-14-40.png)

---
- Place the Twitter Timeline component
![bg right h:550px](images/2021-11-26-22-16-29.png)

---
- Enter "tokyotech_jp" as the Twitter Handle Name
  - You can also change it to the Handle Name of your favorite Twitter account!

![bg right h:550px](images/2021-11-26-22-18-43.png)

---
- Signup in the Preview function and click the Twitter button.
![bg right h:670px](images/2021-11-26-22-20-46.png)
![bg right h:670px](images/2021-11-26-22-26-55.png)

---
- The posts of the Twitter account with the Handle Name you entered will be listed.
![bg right h:700px](images/2021-11-26-22-28-24.png)

---
~~Let's modify it so that it lists the posts of the logged-in user's own Twitter account.~~ 
We're going to run out of time because of a lot of slides, so we'll skip this part...
- Add a TwitterHandleName Property to the Users Collection.
  - Select Text as the Type
![bg right h:700px](images/2021-11-26-22-33-36.png)

---
- Click Form on the Signup screen
- Fields > ADD VISIBLE FIEDLD > TwitterHandleName
- Change to Not Required
![bg right h:500px](images/2021-11-26-22-41-05.png)

---
- "ALREADY HAVE AN ACCOUNT?" link was overlapping the form, so moved it to the bottom
![bg right h:700px](images/2021-11-26-22-57-22.png)

---
Let's set the TwitterHandleName for the registered users
- Click the "1 Record" button in the Users Collection
![bg right h:500px](images/2021-11-26-22-44-36.png)

---
- Click on the record of the registered user.
- Enter TwitterHandleName (You can use your own account or any account you like.)
![bg right h:500px](images/2021-11-26-22-49-11.png)

---
- Change the Twitter Handle Name in the Twitter Timeline component to "Logged In User's TwitterHandleName".
![bg right h:500px](images/2021-11-26-22-51-21.png)

---
Theoretically, this should display the list of posts of the Twitter account set by the logged-in user himself.

Let's check it out with the Preview function.

---
I think an error will occur.
![bg right h:700px](images/2021-11-26-22-59-00.png)

---
Twitter Timeline is a component that has been made available for free by volunteers.

What someone else makes doesn't always work the way you want it to.
![bg right h:700px](images/2021-11-26-23-00-24.png)

---
Some of you may be thinking, "If you can't do it, don't introduce it." Sorry mm.

After some trial and error, "I found a way to avoid the error!" I thought I had found a way to avoid the error by trial and error, so I wrote about it in the document, but later I realized that it was a misunderstanding. (Browsers have a mechanism called caching, which sometimes shows us something like an illusion.)

I hope you'll keep in mind that it can happen.

---
Note: The code for the Twitter Timeline component is publicly available, so you may be able to modify it to use it. (I won't do it this time).
https://github.com/amezousan/adalo-twitter-timeline/

![h:450px](images/2021-11-27-09-05-18.png)

---
- The Twitter Handle Name in the Twitter Timeline component should be set back to the value we entered directly.

![bg right h:600px](images/2021-11-26-23-53-51.png)

---
##### Video Calling
Next, let's take a look at the video calling component.

---
- INSTALL the "No-Code Video Calling" component in the Marketplace
![bg right h:600px](images/2021-11-27-00-01-27.png)

---
Let's create a new screen to place the video calling component.
- Add a Link button to the Home screen to the screen for the video call.
- Add a Link to New Screen from ADD ACTION
![bg right h:600px](images/2021-11-27-01-48-43.png)

---
- Create a "Video Calling" screen by selecting "App Bar" in Template.
![bg right h:600px](images/2021-11-26-23-58-20.png)

---
- Place the Video Calling component on the screen
- Enter "all-in-one" in Unique Conversation ID
  - This will allow all users to participate in a single video call
- Set Unique User id to "Logged In User's Email
![bg right h:600px](images/2021-11-27-00-04-47.png)

---
Additional information

This time, I set up all users to participate in one video call, but I think it is also possible to create a group with multiple users and call only the group members.

If you are interested, please give it a try.

---
If you check the Preview screen, you will see the message "register your Adalo App ID to your Garlick.io accout for free". Follow the directions.

- Click on "Click to Register Adalo App
![bg right h:700px](images/2021-11-27-00-06-56.png)

---
You will see a login screen, but you have not created an account yet.
- Click on "Or, Sign Up.
![bg right h:600px](images/2021-11-27-00-08-08.png)

---
- Select Development Plan (it's free)
![bg right h:500px](images/2021-11-27-00-08-39.png)

---
- Enter your Email and click "Continue to checkout
  - If you have a Google account, you can also click Sign in with Google.

![bg right h:500px](images/2021-11-27-00-09-58.png)

---
- Tick the three checkboxes and click "Complete sign up
![bg right h:500px](images/2021-11-27-00-10-51.png)

---
- Open the email you received and click "Confirm your account" !
![bg right h:500px](images/2021-11-27-00-12-24.png)

---
- Set your Password
![bg right h:500px](images/2021-11-27-00-14-27.png)

---
Account registration is now complete.
The next step is to register your Adalo App ID.
![h:600px](images/2021-11-27-00-15-27.png)

---
- Open the Adalo admin panel and copy the App ID contained in the URL
  - "xxx..." in the following URL part of the following URL.
  https://app.adalo.com/apps/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/screens/preview

![h:700px](images/2021-11-27-00-15-09.png)

---
- In the Garlick.io admin panel, enter your Adalo App ID and click "Register App" !
![h:400px](images/2021-11-27-00-18-45.png)

---
Reload Adalo's Preview screen and display the video call screen again, and you will be waiting for participants to join the video call.
![bg right h:700px](images/2021-11-27-00-20-20.png)

---
When other users log in and display the video call screen, they can make a call.
![bg right h:700px](images/2021-11-27-00-27-46.png)

---
~~# Question: Would you like to try a video call?~~

~~If I get a reaction that you want to try it, I'll share the URL of the experimental app.~~

We are running out of time because of a lot of slides, so skip this part...


---
With the free plan, it seems that calls are disabled after the total call time reaches 1440 minutes, but I think it's enough for testing during development.
If you need the video calling feature, please take advantage of it.
![](images/2021-11-27-01-33-57.png)

---
There are several other components provided to integrate with external services. If you are interested, you can try them.

Example: 
- Youtube (free)
- Google Map(free trial available)
- Google Signin($25)

---
##### Custom Action
Next to the external integration component, we will show you how to handle the data retrieved from the API on the Adalo screen.

---
Reference
>In a broad sense, an Application Programming Interface (API) is a specification of an interface used by software components to exchange information with each other.

 https://ja.wikipedia.org/wiki/%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9

---
First, let's try API integration.
We will use The Cat API, which is free to try. Please access the following URL.
https://thecatapi.com/

![h:400px](images/2021-11-26-17-04-35.png)

---
Note: For the dog people, there is also The Dog API. It probably does the same thing as The Cat API. (I have not tried it, so I recommend using The Cat API with it first)
https://www.thedogapi.com/

![h:400px](images/2021-11-27-06-36-43.png)

---
When using an API, it is often necessary to have an API key issued by the API provider.
The Cat API also requires an API key, so have it issued to you.
- Scroll down to the bottom and click "SIGNUP FOR FREE" in the Pricing section.
![bg right h:600px](images/2021-11-26-17-08-19.png)

---
- Enter your email, App Description, type of project and click "SIGNUP" !
![bg right h:600px](images/2021-11-26-17-10-01.png)

---
- Check the API key that was sent to you by email (you will use it later).
![h:580px](images/2021-11-26-17-16-56.png)

---
Next, let's check the API documentation to see how to use the API.
- Go to the following URL (you can also find the link "API Documentation" in the email you received earlier)
https://docs.thecatapi.com/

---
Use the API to get a random kitten image as described in the top page.

As in the example, make sure that the image changes when the button is pressed.
![bg right h:600px](images/2021-11-26-18-13-42.png)

---
- CREATE NEW APP in Adalo's admin panel
- The settings are as follows
  - Platform: Native Mobile App
  - Template: Blank
  - App Name: ApiIntegrationTrial

![bg right h:250px](images/2021-11-27-02-15-47.png)

---
- Add a link button to the kitten image display screen on the Home screen.
- Set Link to New Screen from ADD ACTION
![bg right h:500px](images/2021-11-27-02-45-19.png)

---
- Select App Bar as Template and create Kittens screen.
![bg right h:500px](images/2021-11-27-02-49-26.png)

---
- Place the Image component on the screen
- Leave the component settings as they are (we'll set them later)
![bg right h:500px](images/2021-11-27-03-02-07.png)

---
- Add a Change Kitten Image Button
![bg right h:650px](images/2021-11-27-03-55-04.png)

---
- Select New Custom Action from ADD ACTION
![bg right h:650px](images/2021-11-27-03-57-01.png)

---
You will be prompted to start a 14-day Integration Pack Trial (free).
- Click on "START INTEGRATION PACK TRIAL"
![bg right h:400px](images/2021-11-27-03-59-22.png)

---
The trial has started.
- Click on "CREATE NEW CUSTOM ACTION" !
![h:500px](images/2021-11-27-04-05-53.png)

---
- Enter the following and click NEXT
  - Name: GetRandomKitten
  - Type: Create

![h:400px](images/2021-11-27-04-25-58.png)

---
Next, we will configure the API Request to be sent.
![h:600px](images/2021-11-27-04-26-54.png)

---
Go to the following URL to check the configuration items.
https://docs.thecatapi.com/api-reference/images/images-search
- API Base URL is https://api.thecatapi.com/v1/images/search
- Method is GET
- Set the API key in the Header with the name x-api-key
![bg right h:350px](images/2021-11-27-05-22-05.png)

---
- Set the API Request based on the results of the check.
  - API Base URL is https://api.thecatapi.com/v1/images/search
  - Method is GET
  - Set the API key in the Header with the name x-api-key
- Click "RUN TEST REQUEST".
![bg right h:500px](images/2021-11-27-05-28-00.png)

---
If the Test is successful, the data retrieved from the API (Magic Text Output Properties) will be displayed. These can be used in subsequent actions.
- Click on "SAVE CUSTOM ACTION
![h:420px](images/2021-11-27-05-33-42.png)

---
Next, set the URL of the kitten image retrieved from the API to the Image Source of the Image component.

As it is, the data retrieved from the API will not appear in the choices.
![h:100px](images/2021-11-27-05-52-10.png)

![bg right h:500px](images/2021-11-27-05-54-04.png)
![bg right h:500px](images/2021-11-27-05-54-35.png)

---
- Add a Text Input component to the screen
- Change the Name to "Invisible Kitten Image URL Input".
![bg right h:520px](images/2021-11-27-05-58-21.png)

---
- Click on the "Change Kitten Image Button
- Select "Change Input Value" from ADD ANOTHER ACTION

![bg right h:520px](images/2021-11-27-06-01-07.png)

---
- Set "Invisible Kitten Image URL Input" as Input
- Set Valoue to "GetRandomKitten > url".
- Click "DONE
![bg right h:500px](images/2021-11-27-06-02-37.png)

---
- Click on the Image component
- Set the URL to "Invisible Kitten Image URL Input".
![bg right h:550px](images/2021-11-27-06-06-13.png)

---
- Click on the screen name "Kittens".
- Click on the eye icon to the right of "Invisible Kitten Image URL Input" to hide it.
![bg right h:550px](images/2021-11-27-06-07-46.png)

---
Check it with the Preview function.

Click on the CHANGE button and the kitten image is now displayed.
![bg right h:700px](images/2021-11-27-06-10-42.png)

---
Supplemental

- Data acquired from the API in Custom Action can be used in subsequent Actions. If you want to use the data in your component, use one of the following methods.
  - Set the data to the Text Input value on the same screen using the Change Input Value of the subsequent Action and load it.
  - Alternatively, you can save the data to the database in a subsequent Action and load it from another component. In this case, it can be accessed even after the screen transition.
    - Example: https://help.adalo.com/integrations/custom-actions

<! -- ![bg right h:400px](images/2021-11-27-06-13-06.png) -->

---
Notes

Currently, Custom Action has some limitations.
- Custom Actions will not work with the Submit button of the Form component.
- If a Custom Action is used as an Action for the entire screen, data obtained as an API response cannot be used in the Imperial Action.
- Cloning an app does not copy the Custom Action; if you clone an app that contains a Custom Action, you will need to recreate it manually.

---
\>Cloning an app does not copy the Custom Action; if you clone an app that contains a Custom Action, you will need to recreate it manually.

The 14-day Integration Pack Trial is expected to end in the middle of the Development Phase.

If you are likely to use a lot of Custom Actions, we recommend that you create a new Adalo account and start a new Integration Pack Trial before you start working on the Development Phase.

---
##### External Collection
This section describes how to handle data retrieved from the API as an Adalo collection.

If you want to retrieve multiple data at once and list them on the screen, use External Collection instead of Custom Action.

---
Let's use this API to retrieve and display a list of cat breeds.
https://docs.thecatapi.com/api-reference/breeds/breeds-list#send-a-test-request
- Click "ADD COLLECTION" in External Collections of Database
![bg right h:700px](images/2021-11-27-06-44-13.png)

---
- Collection Name: Breeds
- Base URL: https://api.thecatapi.com/v1/breeds
- Method: GET
- Auth Setup
  - Header x-api-key: the issued API Key

![bg right h:530px](images/2021-11-27-06-55-32.png)


---
In Adalo, you can set up five Endpoints (access methods) for each resource (in this example, breeds) that you want to access with the API.

Depending on the specifications of the API, you may need to modify it to fit your needs, but in this case, you can just click NEXT.
![bg right h:500px](images/2021-11-27-06-56-48.png)

---
- Run the test and if it succeeds, click "CREATE COLLECTION".
![bg right h:650px](images/2021-11-27-07-11-41.png)


---
The External Collection has been created.

All the data to be retrieved from the API is set as properties.
![bg right h:700px](images/2021-11-27-07-17-10.png)

---
Let's list the retrieved data.
- Add a "Breeds Link" button to the Home screen.
- Add a LINK to the NEW SCREEN from ADD ACTION.
![bg right h:600px](images/2021-11-27-07-19-58.png)

---
- Enter "Breeds" in Name.
- Select Image List in Template
- Click CREATE SCREEN

![bg right h:600px](images/2021-11-27-07-24-09.png)

---
- Change the List Title Text to "Cat Breeds".
- Set the Image List as the Breeds Collection list.
- Set Image URL to "Breed Image > url".
- "If there's no image..." Set "Don't show anything" to "If there's no image...".
- Remove the + button at the bottom right.
![bg right h:600px](images/2021-11-27-07-30-23.png)

---
- Change Text to "Breed name".
![bg right h:600px](images/2021-11-27-07-37-24.png)

---
Show the back icon since it is hidden.
- Click on the App Bar
- Change the Left Icon toggle to ON.
![bg right h:550px](images/2021-11-27-07-32-24.png)

---
Checking with the Preview function, the list of cat breeds is now displayed.
![bg right h:700px](images/2021-11-27-07-39-21.png)


---
That's it for the introduction of external integration in Adalo.

---
#### External Integration with Bubble

Next, let's try the external integration with Bubble.
The screen we will create looks like this.

![w:800px](images/2021-11-25-22-13-51.png)

---

The screen will have the following functions

- Display of YouTube video list
- Social login using your Google account
- Dynamic search of YouTube video list.

---
##### First, we need a new application to build on.

- Create a new application called Advanced-bubble-{your name}.

![bg right h:500px](images/2021-11-25-20-01-24.png)

---

- As in the third article, delete all the elements except the header.
  - It is OK to delete everything and then reposition the header component.

![bg right h:480px](images/2021-11-24-23-09-20.png)

---

##### Next, let's prepare the Google account side.

- Do the necessary preparations to display the YouTube video list
- Sign in to your Google account and access the following URL
  https://console.developers.google.com/

---

- When you access the Google Cloud Platform (GCP) screen for the first time, you will see a dialog box like this. Select your country, check the Terms of Service, and click "Agree and Continue".

![w:600px](images/2021-11-25-20-10-55.png)

---

- After agreeing, you will see the dashboard of APIs and Services, and click on the Create Project link to create a project (box) for this lecture

![w:1000px](images/2021-11-25-20-12-13.png)

---

- When the Create New Project screen appears, specify an appropriate name for the project name and create it.

![bg right h:460px](images/2021-11-25-20-13-50.png)

---

- Once the creation is complete, the dashboard for the created project will appear
  - If the name of the project you created is displayed at the top of the screen, to the left of Google Cloud Platform, you are good to go.

![bg right h:400px](images/2021-11-25-23-19-27.png)

---

- Next, we will issue the authentication key that is required to display the YouTube video list.
- Select "Authentication Information" from the left menu.
- The right panel will change to Authentication Information, and click "+ Create Authentication Information" at the top of the screen.
- Select "API Key" from the pop-up window.

![w:700px](images/2021-11-25-20-18-01.png)

---

- You will then see a popup saying that the API key creation is complete, so write down the value.
- You will be asked to limit the number of keys, but we will delete these keys at the end of the lecture, so we'll leave it at that.

![bg right h:350px](images/2021-11-25-20-18-53.png)

---

- Now that we have the key to get the YouTube list from Bubble, let's configure the Bubble side
- First, we need to prepare Bubble to retrieve the YouTube list via the API

---

##### Preparing Bubble for API integration

- Select Plugins from the left menu and click the Add plugins button
- Search for `API` and install the `API Connector` plugin

![bg right h:500px](images/2021-11-25-20-24-21.png)

---

- This plugin is used to connect the Bubble app to the other side of the API using the public API.
- Some of the Bubble plugins are specific to a particular API, and some of them are simpler to configure than this API Connector.
- In this example, we will use the YouTube API to display a list of videos via the API Connector plugin, which is the most basic form.

---

- Now let's configure the settings to use the YouTube API.
- First, click on "Add another API" to start setting up a new API integration

![w:950px](images/2021-11-25-20-31-17.png)

---

- After clicking "Add another API", you will see the API configuration part like this

![w:950px](images/2021-11-25-20-32-04.png)

---

- Here is a brief description of each item
- Please set 1 and 2 together.

---
1.API Name: The group name for this API integration.
  - In this case, YouTube

![w:1000px](images/2021-11-25-20-36-11.png)

---
2.Authentication: The common authentication method used by APIs under this group.
  - In this case, "None or self-handled".

![w:1000px](images/2021-11-25-20-36-11.png)

---
3.Shared headers for all calls: Common header information for all APIs under this group.
  * Not specified at this time.

![w:900px](images/2021-11-25-20-36-11.png)

---
4.Shared parameters for all calls: Common parameter information for all APIs under this group.
  * Not specified this time.

![w:900px](images/2021-11-25-20-36-11.png)

---

- Next, let's set up the specific API contents for this group.
- To the right of the block labeled "API Call" in the previous screen, there is a link called "expand".
- Then the specific API settings will be displayed, and I will briefly explain them.

![w:700px](images/2021-11-25-20-38-49.png)

---
1. Name: The specific name of the API.
  * In this case, enter "search".

![w:850px](images/2021-11-25-20-46-27.png)

---
2. Path: The specific URL of the API.
  * In this case, enter `https://www.googleapis.com/youtube/v3/search`.

![w:800px](images/2021-11-25-20-46-27.png)

---

3.Headers: Header information specific to this API.
  * Not specified this time.

![w:800px](images/2021-11-25-20-46-27.png)

---
4.Parameters: Parameter information specific to this API
  * This time we will specify the following two parameters: Private / Allow blank / Optional as shown in the attachment. 1.
    1. key: `key`, Value: the API key you just issued in your Google account. 2.
    2. key: `q`, Value: Keyword to search for the action on YouTube (feel free to specify).

---

- Once everything is set up, it looks like this

![w:950px](images/2021-11-25-20-47-33.png)

---

- After the settings are done, check if the settings are correct
- Click on the "Initialize call" button at the bottom

---

- You will probably get a Status code 403 error message.
- This is what it says, but in summary it looks like this

```
YouTube Data API v3 has been disabled in your project.
Please go to this URL, enable it, and try again.
```

![bg right h:600px](images/2021-11-25-20-49-43.png)

---

- It seems that the YouTube Data API that we used is not enabled on each person's Google account.
- This is because Google has turned off features that not everyone will use, and only those who need them can turn them on themselves.
- So, since we want to use the YouTube Data API, let's access the URL in the message and enable it
  https://console.developers.google.com/apis/api/youtube.googleapis.com/overview?project={project ID of each person}

---

- You should now be kindly redirected to the "YouTube Data API v3" screen.
- Click on "Enable" to activate it as shown on the screen.

![w:1000px](images/2021-11-25-20-54-51.png)

---

- After a while, you should see a screen like this
- If the red line at the top of the screen says "Disable API", you have successfully enabled it!

![w:900px](images/2021-11-25-20-56-15.png)

---

- Now that the YouTube Data API has been activated, go back to the Bubble screen and click the "Initialize call" button.
- If successful, you should see a popup that says "Returned values - search

![bg right h:600px](images/2021-11-25-20-57-48.png)

---

- This shows the results of running the `https://www.googleapis.com/youtube/v3/search` API that we set up.

---

I'll spare you the details, but the point is that

- The key point is that the `items(list)` part is a list of videos of search results.
- The type of the list is `search item`, which means that it is the data of multiple systems included in the search results.
- And the most important part of this setting is the `id videoId`.

---

- If you've ever watched YouTube, you'll know that this VideoId is the video that uniquely identifies each video, and this Id is also required to display the video on the screen.
- For other items that you don't want to refer to, select `Ignore field` from the pull-down menu because it is confusing.
- By doing this, when you handle them as Dynamic data, they will not be shown in the choices, and you will not have to worry about them when selecting settings.

---

- This is what it looks like when everything is set up
- When you are done, click "SAVE" to save your settings.

![bg right h:600px](images/2021-11-25-21-04-26.png)

---

##### Preparing for Screen Display

- Now that Bubble's API is ready, it's time to set up the screen.
- Since you have mastered the screen setup in the 3rd and 4th lectures, we will just give you an overview and let you build the screen layout.

---

- On the index page, we will construct a list using Repeating Group.
- Place a Video in each cell of the Repeating Group
- It looks like this

![bg right h:400px](images/2021-11-25-21-13-15.png)

---

- Now that the layout is done, let's actually set up the YouTube list display.
- First, the Type of content for the Repeating Group will be the `search item` type that we checked when we ran the API earlier.

![bg right h:600px](images/2021-11-25-21-14-23.png)

---

- Next, let's look at the data source, which in this case is a list of YouTube videos obtained from the API.
- If you look at the suggestions from Click, you will see an item called `Get data from an external API`.

![bg right h:600px](images/2021-11-25-21-15-44.png)

---

- When the Get data From an external API popup appears next to it, select the API provider pull-down
- In the pull-down, you will see the candidate `YouTube - search` that you set up earlier, select it
  - Before the hyphen is the group name of the API, and after it is the specific name of the API

![w:900px](images/2021-11-25-21-19-45.png)

---

- Next, let's configure the settings for each cell, but first, let's configure everyone

- Video source is YouTube
- Then you will see the Video ID field, so you can refer to the `Video Id` that you saw when you set up the API earlier.

![bg right h:380px](images/2021-11-25-21-21-57.png)

---

- It looks like this.

![bg right h:400px](images/2021-11-25-21-22-21.png)

---

- Now you're all set! Let's preview it right away!
- Do you see the list of videos for the keywords you specified in the API beforehand?

---

![w:1150px](images/2021-11-25-21-27-35.png)

---

##### Let's try Google Login

- Now let's try to log in to the Bubble app using our Google account!
- First, install the Google plugin

![bg right h:500px](images/2021-11-25-17-18-29.png)

---

- Select the Google plugin you installed.
- Check the `Use a generic redirect URL` box in the right panel.
  - Note down this URL as well, but since you can't select it on the screen, just replace the app name in the following URL with your own app name and note it down
  - `https://advanced-bubble-{Your Name}.bubbleapps.io/api/1.1/oauth_redirect`

---

![w:1150px](images/2021-11-25-21-35-23.png)

---

##### Preparing to authenticate back to the app after logging in to Google

- Access the Google Cloud Platform screen

https://console.developers.google.com/

---

- Select your project and choose OAuth Consent screen from the left menu

![w:800px](images/2021-11-25-17-24-32.png)

---

- Select "External" for User Type and "Create".
- After entering the required information, save and go to next

![w:700px](images/2021-11-25-21-37-25.png)

---

- App Information
  - App name: The name of the app you created with bubble
  - User Support Email: Email address of your Google account.

![bg right h:500px](images/2021-11-25-21-38-39.png)

---

- Approved domain
  - bubbleapps.io
- Developer Contact Information
  - Email address of your Google account

![bg right h:450px](images/2021-11-25-21-39-06.png)

---

- Do not change the scope settings, save and go to the next step.

---

- Enter your own Google email address as the test user.
- After setting, save and go next.

![bg right h:500px](images/2021-11-25-21-40-06.png)

---

- Now that the registration is complete, let's issue the authentication information.
- Select Authentication Information from the left menu, and click "+ Create Authentication Information.
- Select OAuth Client ID from the submenu.

![](images/2021-11-25-17-34-11.png)

---

- When the Create OAuth Client ID screen appears, enter the following information and click "Save.

- Application Type: Web Application
- Name: Bubble OAuth

![bg right h:700px](images/2021-11-25-21-43-34.png)

---

- Accepted redirect URI: The URL that you wrote down when you installed the Google plugin on Bubble
  https://advanced-bubble-{Your Name}.bubbleapps.io/api/1.1/oauth_redirect

  ![bg right h:700px](images/2021-11-25-21-43-34.png)

---

- You will see a popup that says "OAuth client created", and the client ID and client secret will be displayed there, so make a note of it.
  - You can also download the JSON file if you might forget it.
- Close with OK after writing it down

![bg right h:500px](images/2021-11-25-17-41-00.png)

---

##### Set up Bubble with the issued credentials

- Go back to the Google Plug-in screen of Bubble, and enter the key you have just obtained into the respective field
  - Client ID → AppID/API Key
  - Client Secret → App Secret

![bg right h:370px](images/2021-11-25-17-44-20.png)

---

- This completes the preconfiguration.
- Next, let's create the login function.

---

##### Replace the login mechanism with Google

- Open the header component and select the SIGN UP OR LOGIN button to go to the workflow screen.
  - And change the label of the button to "Google LOGIN".

![bg right h:350px](images/2021-11-25-21-47-05.png)

---

- When you go to the Workflow screen, you will see that Button Google LOGIN has been configured to behave in two different ways

![w:900px](images/2021-11-25-21-48-31.png)

---

- When: Button Google LOGIN is clicked and Current User is logged in
- This is literally a workflow for when the current user is logged in and the "Google LOGIN" button is clicked.

---

- When: Button Google LOGIN is clicked and Current User is logged out
- This is also literally the workflow when the current user is logged out and the "Google LOGIN" button is clicked

---

- First of all, we want to set up a workflow for login, so we'll set up a workflow for Current User is logged out.
- Since the "Show Sign up / Login Popup A" step is already defined, we will delete it.

![w:700px](images/2021-11-25-18-10-53.png)

---

- Next, let's configure the Google Login workflow.
- Click here to add an action... Select
- From Account, select Signup/login with a soccial network

![bg right h:600px](images/2021-11-25-18-12-11.png)

---

- The Signup/login with Google popup will appear
- Select Google as OAuth provider
- Now that we've configured the Google and Bubble plugins, we're ready for Google authentication 🙌!

![bg right h:350px](images/2021-11-25-18-14-22.png)

---

- Now that we've successfully logged in, let's display the account name and image at the top of the header!

![w:800px](images/2021-11-25-21-53-36.png)

---

- Open the Header component and delete the element to the left of the LOGIN button
- Select Image from Visual elements and place it to the left of the LOGIN button.
  - Make it a square of 100 x 100 in height and width.

![bg right h:450px](images/2021-11-25-18-33-39.png)

---

- Then set the referrer for the image
- If you're a Bubbler, you'll know how to set this up.
- Dynamic image for dynamic display settings
- We want to display the Google Account profile image of the currently logged in user

---

- It looks like this

![bg right h:450px](images/2021-11-25-18-36-17.png)

---

- Now let's preview it!
  - If you have the same Google email address as the one you are going to use in the User section of the Data, please delete it.
- When you click on the "Login" button, you will be redirected to the Google login screen, and when you login, you will be redirected back to the Bubble side, right?
- When you log in, the email address of the Google account you signed in with will be registered in the User data of Bubble.

---

![w:800px](images/2021-11-25-21-53-11.png)

![w:800px](images/2021-11-25-21-53-36.png)

---

##### Finally, let's incorporate a search function using the YouTube API

![w:1000px](images/2021-11-25-22-13-51.png)

---

- Currently, the YouTube API authentication key and search keywords are fixed.
- So, let's change them as follows
  - The authentication key is obtained from the logged in user information (add a new field)
  - Search keywords can be entered and searched from the screen.

---

I'll give you some hints on the next page, so let's try it first!

---

- First, add a field `key` to User and set it up beforehand.
  - Normally, it would be more natural to let the user input the key himself, but for the sake of time, we will skip the API key setting screen.
- If you want to set the parameters of the API dynamically in the process, first remove the fixed value and uncheck `Private` to specify the parameters when calling the API with a DataSource, etc.
- Place a new search element (text box and search button) on the index page, and when the search button is clicked, perform a search via the YouTube API and set the results to the Repeating Group.

---

# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass:
# :hourglass:

---

- First, we'll add a field called `key` for the User type

![](images/2021-11-25-22-32-01.png)

---

- Then, set the authentication key (API key) to the registered User in advance.

![](images/2021-11-25-22-32-29.png)

---

- Next, the YouTube API side settings look like this

![bg right h:400px](images/2021-11-25-22-19-37.png)

---

- As a point, I removed the Value value for the items I want to specify dynamically, and unchecked Private.
- This will allow you to specify the values of these parameters when using the API

![bg right h:400px](images/2021-11-25-22-19-37.png)

---

- Next, empty the Data source of Repeating Group.
- This is to specify the data to be displayed here in the workflow of the new search function.

![bg right h:500px](images/2021-11-25-22-21-24.png)

---

- The next step is to set up the workflow when a keyword search is performed.
- Since this is an action on an element, we will select "Display list" in "Element Actions".

![bg right h:600px](images/2021-11-25-22-27-04.png)

---

- For Data source, select Get data from an external API to display the data via the API.
- And if you select `YouTube - search` as the API provicer, you should see two param's that were not there before.
- This is because we unchecked the "Private" checkbox for the parameters we want to specify dynamically in the YouTube API settings earlier.
- The value you specify here is the usual Dynamic data

---

- This is what it looks like when you set it

![w:1100px](images/2021-11-25-23-16-53.png)

---

- How did you like it?
- I think the scope of what we can do with Bubble has expanded even more by using API integration!
- There may be teams that use external APIs at the camp, so let's use what we learned today and practice API integration!


---
## Tips for Collaborating with No-Code Tools
Here are some tips to help you collaborate with your team using no-code tools.

---
#### (repost) How to invite team members in Adalo
- To co-edit one app with a team member, select Settings > AppAccess > Add Team Member > Invite New Team Member and enter the team member's email address.

![bg right h:600px](../Adalo2/images/2021-11-04-20-14-37.png)

---
#### How to invite team members in Bubble
- To co-edit a single app with a team member...
![h:500px](images/2021-11-27-09-33-00.png)

---
#### Notes on simultaneous editing in Adalo
- Edits made by others will not be reflected on your screen in real time. You need to reload to reflect them.
- If you edit the same screen at the same time, the edits made earlier will be overwritten by the edits made later, and the screen will be in the state of the last person who made the edits.
  - The earlier edits will be undone, even if the edited components are different.
- For Actions, if you add them to the same screen at the same time, only the later one will be saved.
- Database, too, will be overwritten with the state of the last person who edited it if it is edited at the same time.

---
- If you edit on different screens at the same time, both will be saved and you will be fine. When editing, share with your team members which screen you are editing. It is also recommended to decide who is in charge of each screen.
- Before switching the screen to be edited, reload the screen to reflect the latest state (this will prevent you from reverting to the old state when someone else has edited the screen).
- To avoid inadvertently touching other people's screens, it is also recommended that you develop the screens apart from each other on Canvas.
- For the Database, decide on one person to be in charge and let that person update the database.

---
#### Points to note about simultaneous editing in Bubble
- Avoid simultaneous editing of the same element (it will be overwritten by later edits).
  - For this reason, it is recommended to assign a person in charge of each screen to avoid simultaneous editing of the same screen.

There are no other precautions to be taken.
- Edits will be reflected on other people's screens in real time.
  - Not only screen edits, but also database and Workflow edits are reflected in real time.
- If you divide the work by screen, you won't accidentally touch other screens (Canvas is divided), so you can develop comfortably.

---
## Team Development Exercise
- With your DevelopmentPhase team, try to develop one new app.
  - It should be a different app from the one you plan to develop in DevelopmentPhase.
- You are free to use either Adalo or Bubble.
  - You can choose the one you plan to use in DevelopmentPhase, or both.
- Let's make sure everyone has a hand in this.

---
#### Example of how to divide the work
- Identify the screens and functions and design the database together at the beginning.
- Decide who will be in charge of each screen (registration screen, list screen, detail screen, update screen, etc.)
- There is also a way for multiple people to work on a single PC. In this case, the person who operates the PC and the person who gives instructions should be rotated periodically.

---
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass_flowing_sand:
# :hourglass:
# :hourglass:

---
#### Presentation of the exercise results
Each team should present the application that they made in the exercise.

---
## Summary
- This is the end of the Learning Phase lecture.
  - Have you mastered Adalo and Bubble?
  - Did you get an idea of how to do team development?
- In the next Development Phase, we will brush up and develop the ideas presented by each team.
  - In preparation for this, let's reconfirm our ideas and select tools (Adalo, Bubble, or other?) to be used for development. Bubble?

---
# That's all!
# Thanks for your help!




