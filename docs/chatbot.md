##What Is A Chat Bot?
A chat bot is a customized computer program that uses AI softwware to either have a conversation with the user and/or perform actions according to the provided intents by the user.

###The Purpose For Our Chat Bot?
The reason for this chat bot is to create a replicable bot that can be used to help have a quicker response for those that may have simple/FAQ during certain situations. This can lead to increase the amount of customers that can be helped compared to the use of the regular help via calls with operators. The bot will also be able to help a wider variety of customers with the addition of translation to the chat bot.

##Pre-Requisites
- Basic knowledge on how to navigate through Azure
- Understanding the concept of Object-Oriented Programming (OOP)
    - We specifically use C#
- The enthusiasm to learn and read A LOT! 😊

###Technical Breakdown
**What you will need to create this chat bot:**

- Any chat bot created is efficiently made via Azure - using azure to host it and to help you create the basic template for the chat bot in C#.
- This chat bot will consist of a Question and Answer Maker (AKA QnA Maker) for conversation and for the I/O of information for the user.
    - QnA Maker is a Microsoft Cognitive Service that provides a QnA Service with a graphical user interface (GUI). It is a web-based service and REST API that uses artificial intelligence to respond to questions by the use of key words or phrases. In order to respond to the user’s your QnA service must be connected to your knowledge base. A knowledge base is what contains the key value pairs of the questions and answers for the chat bot.
        - **Further references:**
            - [Overview](https://docs.microsoft.com/en-us/azure/cognitive-services/qnamaker/overview/overview)
    - This also consists of creating a knowledge base with its own unique keys created by the QnA maker and your own choice of FAQ.
    - [Here](https://www.captechconsulting.com/blogs/using-qna-maker-service-and-azure-bot-service-to-create-an-faq-bot-in-minutes) is an easy quick guide to make a QnA Maker with a knowledge base.
- This bot also consists of the use of a Language Understanding Intelligent Service (LUIS) app which uses a machine learning -based service to build natural language for the chat bot.
    - LUIS is also a Microsoft Cognitive Service combines easily with the “speech service for instant speech to intent processing, and with the Azure Bot Service, making it easy to create a sophisticated bot.” It is mainly used to create a more natural language by predicting the user’s intent and therefore then understanding how to communicate or respond to the user appropriately.
    - You must create your own intents.
        - Within these intents you must also construct possible utterances to perform this specific intent.
            - **Example:** One intent any user might want to us is “Cancel.” However, not every user will say this intent the same way. This is why we can create our own variety of utterances such as “stop”, “please stop”, “never mind”, or “abort.” These are just a few of the many utterances a user can represent this intent to the bot. This purpose of LUIS is to learn and train itself to understand the different ways a user can portray this intention to then act on it.
            - [Here](https://docs.microsoft.com/en-us/azure/cognitive-services/luis/what-is-luis) is a more thorough guide to what is LUIS and how to create both the possible intents and utterances for your bot.
    - To have the best outcomes with LUIS this consists of consistently testing and training it with understanding your (users) intentions.
- Using the Microsoft Visual Studio has been the best text editor to use in order to track, edit, build and debug your bots code.
- For debugging it is important to use great tools like the Bot Framework Emulator. This will help track your errors and view where and when the issues are taking place when running your bot remotely on a localhost. As a developer you will be able to pin point errors and specifically trace when and if messages are even being sent back and forth through the LUIS intents, methods and QnA dialog. This is a [link](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-debug-emulator?view=azure-bot-service-4.0) to guide you on how to install and use this.

##What You Will Need To Start
- Access to LastPass (Whether you are creating a new or using an existing bot). You will also need to have access to the Civic Machine Azure account.
- An account with QnA Maker here: [www.qnamaker.ai](http://www.qnamaker.ai/)
 **Be sure to use the same Azure email in which you have your QnA bot to create this QnA Maker account.*
- An account with LUIS App here: [www.luis.ai](http://www.luis.ai/)
 **Be sure to use the same Azure email in which you have your LUIS bot to create this LUIS App account.*
- The Microsoft Visual Studio Code text editor.
- The Bot Framework Emulator.
    - More info on this [here](C:\Users\Vanes\Desktop\All Classes For Working LUIS and QnA Bot\o	https:\docs.microsoft.com\en-us\azure\bot-service\bot-service-debug-emulator?view=azure-bot-service-4.0)

##How To Integrate QnA And LUIS

1. Sign in to Azure
2. Create your QnA bot in C# (Be sure to have a knowledge base)
3. Create your LUIS bot in C# (Be sure to have some intents that exist that also match with the intentional questions from the knowledge base)
4. Go to Azure portal and on the left side bar click on “Resource groups” and click on to your QnA bot. Then, click on to your “Web App Bot.” Next, click on “Build” on the left side bar. After this click on “Download bot source code” in order to develop your bot locally.
5. Repeat step 4 but this time for your LUIS bot.
6. Next, on Azure go into your “Resource Groups”, then the QnA bot you have made and click on “Test in Web Chat” inorder to make.
    - If issues do occur be sure to check that in your “Application Settings” all of your “App Setting Names” and “Values” such as “QnAAuthKey”, “QnAEndpointHostName”, “QnAKnowledgebaseId”, and “QnASubcriptionKey” are all titled this way and also have the correct keys/values. (More information of this is in the previously mention Technical Breakdown section above --in this specific [link](https://www.captechconsulting.com/blogs/using-qna-maker-service-and-azure-bot-service-to-create-an-faq-bot-in-minutes).)

7. Then, using Microsoft Visual Studio text editor open up the “sln” file from your locally downloaded QnA bot source code.
8. Now, in your QnA bot source code open up your “Controller” folder and click onto your “MessagesController.cs” file. Here, in the method titled 
```public virtual async Task<HttpResponseMessage> Post([FromBody] Activity activity)S``` specifically and only inside the curly brackets of your first “if-statement” titled ```if (activity.GetActivityType() == ActivityTypes.Message){in here}``` you will add and only be sure to have this line of code (provided below) in there:
```await Conversation.SendAsync(activity, () => new BasicLuisDialog());```
9. After this in the in the “Dialogs” folder please create a new file titled “LuisDialog.cs”. Please also be sure to save all changes.
10. Next, repeat step 7 on a new window for your LUIS bot source code.
11. Then, from your LUIS bot source code be sure to copy all the lines of code from the file “BasicLuisDialog.cs” within the “Dialogs” folder and paste it all into the file “LuisDialog.cs” that is in the QnA bot source code. Please also be sure to save all changes.
12. After, in the QnA bot source code in the “Dialogs” folder please create a new file titled “LuisDialog.cs” and adjust the line ```namespace Microsoft.Bot.Sample.QnABot``` (therefore replace the LUIS “namespace” line with the QnA one)
13. Then, above that ```namespace Microsoft.Bot.Sample.QnABot``` line of code add these two lines of code:
```using Microsoft.Bot.Connector;```
```using System.Threading;```
14. Next, in the "LuisDialog.cs” file within all of your intents such as ```[LuisIntent("None")] public async Task NoneIntent(IDialogContext context, LuisResult result){in here}``` please replace all the lines of code within the curly brackets with these:
```string message = $"I am in the LUIS Intent For {result.Intents[0].Intent} - Routing to QnA... "; await context.PostAsync(message); var userQuestion = (context.Activity as Activity).Text; await context.Forward(new QnADialog(), ResumeAfterQnA, context.Activity, CancellationToken.None); await this.ShowLuisResult(context, result);```
15. To test locally be sure to add all of your App Setting items like “LuisAPIHostName”, “LuisAPIKey”, and “LuisAppId” into your “Web.config” file (as well as all the QnA items mentioned in step 6a) specifically within the <appSettings> tags in this format for example:
```<add key="LuisAppId" value="with your id value in here" />```
16. To test on azure please be sure to add all of the LUIS items mentioned in step 15 into the “Applications Settings” of the QnA Bot after you have also added the updated information from steps 8-14 to the Azure online code editor. You can find the option to “Open code online editor” in the “Build” section under “Bot Management”. Finally, after you have done these changes in order to save these changes you must enter into the “Open Console” within this open code editor (or hold Ctrl+Shift+C) and run the command “build.cmd” then press enter. Your code should have now been updated to the online Azure QnA bot.
17. Now, test your bot in the “Test in Web Chat”.

****Further updates will be added to this chat bot documentation in order to add other features to this project**