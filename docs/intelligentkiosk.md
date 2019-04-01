# What is Microsoft's Intelligent Kiosk?

Intelligent Kiosk is an interactive demo space for Microsoft's Cognitive Services APIs that uses the services available across various scenarios, including Bing News Search, Bing Image Search, Bing Autosuggest, Text Analytics, Face, Emotion, Vision, and the LUIS/Bot Framework. Here are the scenarios in the Kiosk demos, and their underlying product features.

- **Automatic Photo Capture.** Capture an image and apply analytics when people approach the web camera. 
Features: Windows 10 Face Tracking; Face API for age & gender prediction and face identification.
- **News Analytics.** Analyze search terms and detect sentiments. 
Features: Bing News API, Bing Autosuggest API, Text Analytics API for sentiment analysis and key phrase extraction
- **Emotion API Explorer.** Analyze faces and detect emotion. 
Features: Windows 10 Face Tracking; Emotion API; Bing Image Search API; Bing Autosuggest API
- **Face API Explorer.** Analyze faces and detect age and gender. 
Features: Windows 10 Face Tracking; Face API for age & gender prediction and face identification; Bing Image Search API; Bing Autosuggest API
- **Face Identification Setup.** Train the machine learning model behind the Face APIs to recognize specific people. 
Features: Face API for face identification; Bing Image Search API; Bing Autosuggest API
- **Mall Kiosk.** Makes product recommendations based on the people in front of the camera and then analyzes their reaction to it.
Features: Windows 10 Face Tracking; Face API for age & gender prediction and face identification; real-time sampling using Emotion API; Windows 10 Speech-To-Text; Text Analytics API for sentiment analysis.
- **Realtime Crowd Insights** – processes frames from a web camera to derive realtime crowd insights such as demographics, emotion and unique face counting. 
Features: Windows 10 Face Tracking; Realtime sampling; Face API for age and gender prediction, face identification, and unique face counting; Emotion API.

[Get the details about each of the APIs](https://www.microsoft.com/cognitive-services/en-us/apis)

You may view a video overview at the following link: [https://channel9.msdn.com/Shows/AI-Show/An-Introduction-to-the-Intelligent-Kiosk](https://channel9.msdn.com/Shows/AI-Show/An-Introduction-to-the-Intelligent-Kiosk)

### List of Demos

- **Bing News Analytics** – Categorizes search results based on the sentiment of the news headlines, and uses Key Phrase extraction to create a word cloud with the top keywords of the headlines
- **CaptionBot** – Captions whatever is in front of the camera
- **Crankify Kiosk** – Turns the user into a Crank from the Maze Runner series
- **Emotion API Explorer** – Allows the user to load images from Bing or Local Files, or from the web-camera, and displays the top three emotions on each face
- **Emotion Match (baby face edition)** – Analyzes the emotion on each face and matches it with a face with similar emotion from a set of baby photos; performs real-time face tracking to detect when people are near the camera; once it detects people, it guides them through the rest of the experience
- **Emotion Photo Booth** – Challenges the user to express the eight emotions that are recognized by the Emotion API; can handle many people at the same time: whoever shows the most expressive look for each emotion wins
- **Face API Explorer** – Performs age and gender prediction as well as face identification by using web cam photos, local files on your hard drive, or images from Bing Images; for people who have been added to the Face Identification Setup model, it will show their names and age, for unknown people it will show their gender and age
- **How Old** – Guesses the age and gender of people; performs real-time face tracking to detect when people are near the camera; once it detects people it guides them through the rest of the experience; can also be trained to identify specific people
- **Mall Kiosk** – Makes product recommendations based on the person’s gender and age; can be configured to make personalized recommendations when specific people are recognized
- **Realtime Crowd Insights** – Analyzes emotion, age, gender, and identification while the people are looking at the camera, and displays those insights
- **Realtime Video Insights** – similar to the Realtime Crowd demo, except that it uses as input a video file (from a local file or YouTube) and provides a different visualization of the emotion by slicing it for each person in the video and plotting it on a timeline
- **What Dog** – similar to Emotion Match, except it matches each person with a dog, based on the age and gender of the person
- **What If** – uses Cognitive Services and the Bot Framework to analyze “what-if” like questions and answer them with an image

## How Microsoft Cities uses Intelligent Kiosk

Intelligent Kiosk is a powerful application that the team uses to showcase the application of Cognitive Services with interactive play and engagement. Microsoft Cities attends the NYC CS Fair every year and uses the Kiosk to demonstrate how APIs can be used to create applications such as the "How Old", "Emotion Photo Booth", and "Face API Explorer" among other demo favorites. 

This affords us the opportunity to engage interested students in the underlying technology used to develop and implement these APIs and offer tips and instruction on how they can use the APIs themselves!

## Installation
To install the kiosk, you will need a Windows 10 machine with a webcam and access to the Microsoft App Store. 

The download is located at [https://aka.ms/intelligentkiosk](https://aka.ms/intelligentkiosk) or [https://microsoft.sharepoint.com/teams/IntelligentKiosk](https://microsoft.sharepoint.com/teams/IntelligentKiosk). *You must sign in with your Microsoft credentials to access the site.*

1. Click "INSTALL INTELLIGENT KIOSK" or go to [https://microsoft.sharepoint.com/teams/IntelligentKiosk/Documentation%20Wiki/Installation.aspx?web=1](https://microsoft.sharepoint.com/teams/IntelligentKiosk/Documentation%20Wiki/Installation.aspx?web=1)
2. Go to [http://aka.ms/kioskapp​](http://aka.ms/kioskapp​) or [https://www.microsoft.com/en-us/p/intelligent-kiosk/9nblggh5qd84?rtc=1&activetab=pivot:overviewtab](https://www.microsoft.com/en-us/p/intelligent-kiosk/9nblggh5qd84?rtc=1&activetab=pivot:overviewtab). The Windows Store should open. If not, you will be routed to a web page. Click "Get" from here and agree to launching the Microsoft Store. 
3. Click "Install" from the Microsoft Store.
4. Once  installs, Click "Launch" from the Microsoft Store. 

## Configuration

Once you launch the Kiosk app for the first time, you will be prompted once to allow the app access to your web camera and once more to allow access to your microphone. A camera and microphone are necessary to run the demos. Click, "Yes" to enable for both prompts.

The following steps will walk you through configuring the Intelligent Kiosk app using API keys.

1. Click the hamburger menu on the top-left of the app screen and select "Settings".
2. Turn off "Use Shared Keys" if it is on.
3. Click the "Click Here if You Need Keys" button below the first API key fields. Azure Portal sign-in page will launch. Use your Azure credentials to log in.
4. Select "All Resources" and filter by "kiosk" in the *filter by name field*. The resources listed are the API keys needed for the Intelligent Kiosk app. You will only need kiosk-text-analytics, kiosk-face, and kiosk-computer-vision for the demos.
5. Select one of the kiosk resources listed and click "Keys" under Resource Management on the left panel. 
6. Copy/paste the API key into the appropriate field in the Intelligent Kiosk app. **NOTE**: DO NOT regenerate keys while someone is running a demo. This will cause their demo to fail. Make sure each region is set to *eastus2*.
7. Click "Run Key Validation Test" to confirm your API keys are functional.
8. Under the Miscellaneous header, generate a workspace name and change your starting page to "Emotion API Explorer".
9. Click the hamburger menu on the top-left again and go back to the main screen.

Go ahead and have fun exploring the Intelligent Kiosk!

*These API keys were generated using the Cognitive Services resource in Azure.*