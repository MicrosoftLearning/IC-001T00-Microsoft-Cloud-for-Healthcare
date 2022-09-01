Module 4 Lesson 1- Lab 2: Azure Health Bot
Overview
The Azure Health Bot Service is a cloud platform that empowers developers in healthcare organizations to build and deploy their compliant, AI-powered Patient insights and health bots, that help them improve processes and reduce costs. It allows you to offer your users intelligent and personalized access to health-related information and interactions through a natural conversation experience.
With the service, healthcare organizations can build a "health bot instance" and integrate it with their systems that patients, nurses, doctors, and other representatives interact with. Building an instance allows you to:
•	Improve processes
•	Improve services
•	Improve outcomes
•	Reduces cost
The Health Bot Service contains a built-in medical database, including triage protocols. You can also extend a health bot instance to include your own scenarios and integrate with other IT systems and data sources. To learn more about Azure Health Bot, see Azure Health Bot Overview on Microsoft Docs.
The Azure Health Bot focuses on the Enhance patient engagement priority scenario by creating a virtual bot health option to allow for new avenues of care with embedded insights.
 

This lab will focus on Lamna Healthcare Company.
 

As part of their digital transformation efforts, Lamna Healthcare Company is seeking to streamline their patient engagement capabilities by implementing Azure Health Bot to help improve processes and services, such as entering medication requests. By allowing patients to interact with this service, Lamna Healthcare Company will move one step closer to their goal of improving patient outcomes while reducing overall costs.
In this lab, you'll play the role of a Lamna Healthcare IT developer and configure Azure Health Bot for a medication refill scenario.

Learning objectives
In this lab, you will:
•	Set up Azure Health Bot
•	Configure Dynamics 365 Customer Service Omnichannel Live Chat
•	Embed Azure Health Bot in a Power Apps Portal
•	Extend Azure Health Bot with custom scenarios

Step 1: Set Up Azure Health Bot
In this exercise, you will do the following:
•	Set up Health Bot from Azure Portal
•	Configure and enable the integration between Dynamics 365 Omnichannel and Health Bot
•	Configure and enable Bot channel to obtain a Bot Id

Azure Health Bot empowers developers in healthcare organizations to build and deploy AI-powered, compliant, conversational healthcare experiences at scale.  It combines built-in medical database with natural language capabilities to understand clinical terminology and can be easily customized to support your organization's clinical use cases. The service ensures alignment with industry compliance requirements and is privacy protected to HIPAA standards. To learn more about Azure Health Bot, please reference this Azure Health Bot documentation.

Task 1: Install Azure Health Bot in Azure Subscription
1.	While logged in to your Microsoft 365 tenant, open a new tab in your internet browser incognito or in-private mode and navigate to Azure Portal at https://portal.azure.com/

2.	Search for Azure Health Bot in the top search bar and select it from the search results. 
 

3.	Click Create button to create a new Azure Health Bot instance.
 

4.	You will be redirected to the Azure Health Bot page.  Enter the following information:
a.	Subscription:  PowerPlatformOpenHacks Subscription
b.	Resource Group:  IndustryLabs
c.	Name:  iaduser[x]-healthbot (e.g., iaduser01-healthbot, using your assigned user)
d.	Region:  East US
e.	Plan:  Free (F0)
 

5.	Select Review + Create.

6.	On the Review and create page, verify your details are correct as Azure validates your Health Bot.  After validation passes, the create button will become enabled. Click Create.

Note: It will take few seconds to run the backend process before the Create button is enabled. 
  

7.	You will be redirected to the Deployment page for your new Azure Health Bot.  
 

8.	When deployment is complete, the Go to resource button will enable.  Please wait until deployment is complete for the Azure Health Bot, then select Go to resource when enabled.
 

9.	You will be redirected to the Resource page for your new Azure Health Bot.  Click the Management portal link in the Essential section to open your Azure Health Bot instance configuration page.

Note: Please copy this Management portal link and store it to access the Health Bot later.
 

10.	You will be navigated to your new Azure Health Bot instance homepage.
 

Congratulations! You have successfully created a new Health Bot instance in your Azure tenant.

Task 2: Update Azure Health Bot Settings to Enable Dynamics 365 Integration
1.	On the Azure Health Bot homepage, expand the side navigation bar to see the sitemap labels.  
 

2.	After expanding, you will see the sitemap labels next to the icons.
 

3.	Select Configuration > Conversation on the navigation bar.
  

4.	You will be landed in the Interactions tab.
 

5.	Select Human Handoff tab in the Conversation settings.
 

6.	Scroll to the bottom of the Human Handoff page. Under Dynamics 365 Omnichannel, toggle Enabled for Bridge Messages. This is required to allow communication and bridge messages between the Azure health Bot and Dynamics 365 Omnichannel for Customer Service.
 

7.	Click Save in the top right.
•	 

Now let’s enable the Health Bot for Microsoft Teams Channel.

8.	Navigate to Integration > Channels.
 

9.	In the Channels list, select the toggle to enable Microsoft Teams.
 

10.	This will bring out a side window with your Bot Id information. Copy and store the BotId for later to use when creating the Dynamics 365 Application User.
 

11.	Select Save. This should enable Teams channel and your Microsoft Teams toggle should reflect accordingly.
 

Congratulations!  You completed the Azure Health Bot settings for integration with Microsoft Teams and Dynamics 365 Omnichannel for Customer Service.

Task 3: Obtain Azure Application ID
In this task, you will be using an Azure Application ID already created in our Azure tenant called “MCH Application Id”. Registering this Id establishes a trusted relationship between your Dynamics 365 app and the Microsoft identity platform. Using this Id, you will later create a Dynamics 365 Application User to bridge the authentication between Azure Health Bot and Power Apps.
1.	Navigate back to the Azure Portal and search for App Registrations in the Search box.
 

2.	You will be landed in the App registration homepage on the Owned applications tab.
 

3.	Select the All applications tab.
 

4.	To search for our Application Id, type “MCH Application Id” in the Search box.
 

5.	Select the MCH Application Id app registration resource. Copy and store the Application (client) ID for later to use when creating the Dynamics 365 Application User. 

Note: ID values have been removed in the screenshot for privacy purposes.
 

Congratulations! You have successfully obtained the MCH Application ID from Application Registrations in the Azure Portal.

Step 2: Configure Omnichannel Live Chat
In this exercise, you will be configuring live chat for Dynamics 365 Omnichannel for Customer Service.  Omnichannel for Customer Service offers a suite of capabilities that extend the power of Dynamics 365 Customer Service Enterprise to enable organizations to instantly connect and engage with their customers across digital messaging channels.
In the following tasks, you will complete the following:
1.	Assign Omnichannel agent security role
2.	Create an Application User using the MCH Application Id and your Bot ID
3.	Configure Queues for Bot and Agent Users
4.	Configure a Context Variable and Routing rule to route the message either to a Bot or Agent.
•	
Task 1: Assign Omnichannel Agent Security Role
1.	While in the In-Private or Incognito window, navigate to Power Apps.

2.	Ensure the correct environment from the upper right Environment drop down is selected.
  

3.	Select the gauge icon in the upper right corner and navigate to Advanced Settings.
 

4.	A new window should open and navigate to Dynamics 365.  It may take a while to load.  If it’s been longer than a minute, stop and reload the page.  It should then load faster.  It will land you in the Business Management section of Dynamics 365.
 

5.	On the top command bar next to Dynamics 365, select Settings to open the drop-down, then select Security in the third column under System.
 

6.	Under Security, select Users.
 

7.	Switch the view drop down from Omnichannel Users to Enabled Users for the grid view so that your user will show in the list.
 

8.	While in the Enabled User list, scroll to find your user or use the Search bar.
Note: If you are in an official training, search for you assigned user – IAD User [x]
 

9.	Select your user for the training and select Manage Roles on the top command bar.
 

10.	Select the Omnichannel Agent roles to assign to your user and select OK.
  

Congratulations!  You assigned the proper omnichannel agent role to your user to allow you to be a live agent in omnichannel.

Task 2: Create Health Bot User in Dynamics 365 Customer Service
We need two users to configure in Omnichannel for Dynamics 365 Customer Service:
•	Health Bot User – This is the Azure Health Bot user we created in the previous exercise.
•	Omnichannel Agent User – This is your current user whom you are logged into Dynamics 365.  This will allow you to be a live agent in Customer Service who receives messages from portal users through Azure Bot escalations.  Note: For official trainings, this is your assigned user, iaduser[x]
In this task, you will create a Bot User which helps connect Azure Health Bot with Omnichannel live Chat . 
1.	Go to https://admin.powerplatform.microsoft.com/.
Select your Microsoft Cloud for Healthcare environment from the list 

2.	You will land on your environments detail page.
 

3.	Click the Settings button on the top command bar.
 

4.	Expand Users + permissions and click Application users. 
 

5.	Select (+) New app user button to create a new Application User.
 

6.	Select (+) Add an app on the create screen that slides out on the right side. 
 

7.	Paste the Application ID (the Application (client) ID you obtained in the Azure portal for the supplied MCH Application ID) into the search box and select the app from the list. Click Add at the bottom right. 
  

8.	Select a Business unit from the drop-down list (the options in the list will be unique for each Dynamics 365 environment). Click Create at the bottom right. 
 

9.	Return to the Dynamics 365 User page, switch the view to Enabled Users.
  

10.	While in the Enabled User list, scroll to find your App user or use the Search bar. Double click on the user or select the row and click Edit.
Note: If you are in an official training, search for the Application User – MCH Application ID
 

11.	Change the form type from User to Application User above the User Name.
 

12.	You will see a new form appear that aligns to an Application User.
 

13.	In the User Information section, enter or select the following information and click the Save icon in the bottom right corner:
a.	User type: Select Bot application user.  This will display a new field to store the Bot application Id.
b.	Bot application ID: This is the Azure Health BotId you copied when enabling the Teams channel.  This field is displayed once the User Type is selected to be Bot application user.
 

14.	Select Manage Roles on the command bar.
 

15.	Assign the Omnichannel Agent role to the Bot User as you did for your own user in the previous task.  This will allow the bot to act as an omnichannel agent like your user.
  

Congratulations!  You successfully created a Bot User and assigned to it the Omnichannel Agent role.

Task 3: Create and Configure Omnichannel Queues
In this task, you will create and configure the omnichannel queues necessary to communicate with the correct bot or agent depending on the situation.
1.	In http://make.powerapps.com, open the Omnichannel admin center app.
 

2.	Select Queues on the left navigation bar.
 

3.	Open Default Messaging Queue.
 

4.	We will now associate the Default messaging queue with the Bot User so it will respond to incoming messages from customers without agent (human) intervention.

5.	Select Add Existing User on the User (Agents) subgrid to add the Bot user you previously created. 
  

6.	In the Lookup Records pane, search for your Bot User (MCHApplicationId) created in the earlier task.  
 

7.	Select the record from the list and click Add.
 

8.	You should now see the Bot User (MCH Application Id) in the Users (Agents) list. Save & Close.
Note: If the user does not populate after adding, make sure you assigned the omnichannel agent security role to the bot user in the previous task (it may take up to 15 minutes for changes to take effect).
 

9.	Go back to the Omnichannel queues grid.  Click + New to create a new Queue.
 

10.	Give the new Queue the following details:
a.	Name: “Escalate To Human”
b.	Priority: 1 (lower than default queue)
c.	Click Save.  
 

11.	A Users (Agents) subgrid should appear on the right and your user should be automatically added to the list.  If your user account is not on the list, add it through the Add Existing User button now.

The queue Escalate To Human is created to manage and redirect the incoming messages from a user to a Customer Service (human) Agent when Bot sends the user through to a live agent.
 

Congratulations!  You have created the necessary queue to escalate to human agent and added the appropriate users to each messaging queue.

Task 4: Update Live Work Stream with Context Variables and Routing Rules
In this task, we will set up basic chat routing.  This will allow for users to chat with a bot user in certain cases and a live human agent in other scenarios.  The routing rules will allow chat to behave as follows:
•	Route to Bot: Initial customer conversation is through Health Bot in the default messaging queue.  When the chat bot is first opened, route to Default queue which only contains the bot user (agent).
•	Human Routing Rule: When context variable EscalateToAgent is present and set to 1, we route to the queue that has only human users (agents) who can take over conversation.

1.	Navigate to Work Streams.
 

2.	Select and edit the Live chat workstream .
 

3.	In the Live chat workstream record, select the Context Variables tab.  Select + New.
 

4.	Create the new Context Variable with the following details:
a.	DisplayName: EscalateToAgent
b.	Name: EscalateToAgent
c.	Type: Number
 

5.	Click Save and Close.

6.	You should now see the new Context Variable in the Live chat workstream.
 

7.	Select the Routing Rules tab.  Click + Add to create a new routing rule.
 

8.	Create the new Health Bot routing rule with the following details:
a.	Name: ToHealthcareBot
b.	Queue: Default messaging queue
c.	No Conditions.  
 

9.	Select Save & Close.  On the Live chat workstream, click + Add to add another new Routing Rule.
 

10.	Create the new Omnichannel Agent routing rule with the following details:
a.	Name: ToAgent
b.	Queue: EscalateToHuman
c.	Add Condition: Context Variable “EscalateToAgent = 1”
 
 

11.	Select Save & Close.

12.	On the Live chat workstream, you should now see the two Routing Rules we created for Bot (ToHealthcareBot) and Agent (ToAgent).
 

Congratulations! You have created the proper context variable and routing rules that will allow customers to begin conversation with a health bot and escalate to a human agent.

Task 5: Create Chat Widget for Health Bot 
1.	Navigate to Chat.
 

2.	Select +New Chat Widget.
 

3.	Give the Chat Widget a Name (eg., Patient Portal Chat Widget).
 

4.	Click Save.
 

5.	After the record is saved, a Widget Code Snippet  will be generated.  Copy the code snippet and store it for later use.
 

Congratulations! In this exercise, you have successfully configured Customer Service Omnichannel Live chat by creating the necessary Users, Queues, Work Streams, Context Variables, Routing Rules, and Chat Widget. These all work together and allow patients to chat with a virtual health bot with the option to escalate up to a human agent if needed. 

Step 3: Embed Health Bot in Power Apps Portal
In this exercise, you will be embedding the Omnichannel Chat Widget into the Power Apps Customer self-service portal using Portal Management configuration.  In your environment, we created a Lamna Healthcare Company Portal using the Customer self-service portal template before deploying Microsoft Cloud for Healthcare.  Now we will configure the chat widget to show on the customer website.
Customer self-service portal: A customer self-service portal enables customers to access self-service knowledge, support resources, view the progress of their cases, and provide feedback.
Portal Management: Application to help you get started with the advanced portal configuration. In this walk-through, you will learn how to configure Chat widget in Portal Management app.

1.	In http://make.powerapps.com, open the Portal Management app. 
 

2.	Select Content Snippets in the left navigation pane
 

3.	In Active Content Snippets, type “Chat” in the Search box and press enter.
 

4.	You will see two Chat Widget Code records retrieved in the list. Click to open the Chat Widget Code record related to Customer Self-service.
 

5.	In the Chat Widget Code record associated with Customer self-service, select Value (HTML) > Html Tab and then paste the Chat Widget Code snippet that you copied and stored in the previous task.
 

6.	Click Save & Close.
 

7.	Now open the other Chat Widget Code associated with the Healthcare Patient Portal website.
 

8.	In the Chat Widget Code record associated with the Healthcare Patient Portal, paste in Value (HTML) the same Chat Widget Code snippet that you copied and stored previously and added to the customer self-service chat widget code.  Replace any value that may have already populated the field. 
 

9.	Select Save and Close.

Congratulations!  In this exercise you have successfully updated the chat widget in the Power App Portal Content Snippets.  With this configuration, the Health Bot will be visible on the Power Apps portal for both the customer self-service template and the healthcare patient portal template.

Step 4: Extend Azure Health Bot with Custom Scenarios
Dynamics 365 Omnichannel integration allows the patient to interact with Azure Health Bot using the Dynamics 365 chat widget to access the medical knowledge and your custom scenarios.  It also, allows the escalation of a bot conversation to a live agent to continue the interaction.  When escalating a conversation, Dynamics passes along the conversation history and the context to the agent.
In this exercise, you will be doing the following:
•	Designing the below Health Bot Scenario called MCH_PatientService



 













•	Design another Health Bot Scenario called MCH_PatientServiceWelcome. This scenario holds the starting statement which will allow the user to invoke the MCH_PatientService scenario.
•	Set the Automatic Welcome Scenario to be the  MCH_PatientServiceWelcome custom scenario you create. This will begin the scenario when a user first interacts with the Health Bot.

Task 1: Create MCH_PatientService Scenario
In this task, you will create the MCH_PatientService bot scenario using the designer canvas.
1.	Navigate back to the Azure Health Bot instance homepage where you set the bot settings.  This is the portal management link you copied from the Azure portal.
 

2.	Click to Expand the Side navigation bar.  Navigate to Scenario > Manage.
 

3.	Click + New button on the top ribbon.
 

4.	Provide the following details for the new health bot scenario:
a.	Name: MCH_PatientService
b.	Scenario ID: MCH_PatientService
 

5.	Now let’s design the scenario conversation. It should navigate you directly to the designer. If not, select the MCH_PatientService scenario in Scenarios > Manage to edit.
 

Step 1: Add Bot Introduction Statement
1.	Add a beginning Statement to the scenario by selecting the icon and dragging Statement icon onto the editor.
 

2.	Enter the Display Text:
Hi there, I’m your Healthcare Assistant.

3.	Select the pencil next to Statement in the top bar and Change Title to “Intro”. Click OK.
 

4.	Click OK. You will see the intro statement added to the designer canvas. Double click anytime to edit.
 

Step 2: Add Statement for Medication Request or Live Agent
This section prompts two buttons Medication Refill and Live Agent. When user click any one of the buttons it will set the appropriate text to the variable MedicationOrAgent.
1.	Select Prompt icon and drag down onto canvas
 

2.	Enter the following details:
a.	Display Text: Would you like to request a medication refill or chat with a live agent?
b.	Variable name: MedicationOrAgent
c.	Data type: string
d.	Rename title to MedOrAgent.

3.	Click Cards button.
 

4.	Select Add Card.
 

5.	Select Card Type as HeroCard. Leave title blank as we already prompted with display text.

6.	Click Add Action button twice to add two actions:
a.	For the first action, select the following:
i.	Action type: imBack
ii.	Action value: MedicationRefill
iii.	Action title: “Medication Refill”
b.	For the second action, fill in the following:
iv.	Action type: imBack
v.	Action value: LiveAgent
vi.	Action title: “Live Agent”
 

7.	Click Ok three times to get back to designer
 
 

8.	Connect Intro and Appointment boxes. Select the bottom circle on intro and drag it to the top circle on the new prompt. An arrow will automatically appear when you try to connect Intro and MedOrAgent boxes using ellipse pointer.
 

9.	Select Save.
 

10.	Select Run to see the output in the WebChat on the right.
 
 

Step 3:  Add MedicationOrAgent Decision Branch 
This section checks whether the user has clicked Medication Refill or Live Agent with the help of the variable MedicationOrAgent. It will redirect the message accordingly.
1.	Add a Branch to the designer canvas.
 

2.	Enter the following in the javascript Boolean expression:
•	scenario.MedicationOrAgent ===  "MedicationRefill"

3.	Rename to IsMedRefill. Select OK.
 

4.	Select and drag the bottom circle of the MedOrAgent prompt to the top circle of the IsMedRefill branch decision to connect them.
 

Step 4: Prompt User to Enter Data for Medication Refill Option
1.	Add a Prompt element.  This will be used to display the Form data (using Adaptive Card) to capture Patient name, email, and phone to create an appointment.
 

2.	Add the following details:
a.	Variable name: formData
b.	Variable Data Type: Object
c.	Change Title to Submit
d.	Do not add any display text since the adaptive card will display instead
 

3.	Click Cards button > Add Card > Adaptive Card.

4.	Refer to the lab resources file AdaptiveCardForMedicationRefill.txt and copy the json content and paste it in the json section of your card.
 

5.	Select OK three times to get back to the designer.

6.	Connect the Yes condition of the IsMedRefill branch to the Submit prompt.
 

7.	Save and run your current scenario. If you don’t save the scenario first, it won’t run with updates since the last save. If you haven’t saved at all, it won’t recognize any conversation.
 

8.	You should see the below output when running the conversation and selecting “Medication Refill” card when prompted to show the AdaptiveCard.
 

Step 5: Add Confirmation Statement
1.	Add a Statement element.
 

2.	Add Display text as the following: 
scenario.formData.myName + " - Thanks for providing the information, we have created a Medication Request for you regarding the following medication: " + scenario.formData.myMedReq

3.	Rename the statement to Confirmation.
 

4.	Connect the Submit step to the Confirmation step in the designer canvas.
 

5.	Select Save and Run to see your scenario in the webchat.
 

6.	Fill in information for the request and click Submit to see the confirmation text.
 

Step 6: Invoke Live Agent Action
1.	Add a Statement element to the canvas.
 

2.	Enter Display Text: Please wait, I am transferring your request to a live agent for further assistance.

3.	Rename the statement to Live Chat.
 

4.	Click OK to return to the designer page.

5.	Connect the No decision of the IsMedRefill branch to the Live Chat statement.
 

Step 7: Add Action to Invoke Escalation
1.	Add an Action element to the canvas, used to trigger an escalation to Omnichannel Live Agent
 

2.	Add the following code in the action, which will trigger the Live agent chat:
session.sendChannelData('Escalating...', {
    "tags": JSON.stringify({type: "Escalate", context: {"EscalateToAgent": 1}})
});
3.	Name the action Escalate.  Click OK to return to the designer page.  
 

4.	Connect the Live Chat to the new EscalateToAgent action.  You completed the final connection!
 

5.	Save and run your scenario to see the full scenario output.

6.	Test all logical paths. Selecting Live Agent in the authored card should show the escalation action.
 

7.	Exit the MCH_PatientSerivce scenario editor.
 

Task 2: Create MCH_PatientServiceWelcome Scenario
In this task, you will create another bot scenario called MCH_PatientServiceWelcome to invoke the MCH_PatientService scenario.

1.	On the Azure Health Bot scenarios page, select +New to create another new scenario
 

2.	Provide the following details for the new scenario:
a.	Name: MCH_PatientServiceWelcome
b.	Scenario ID: MCH_PatientServiceWelcome
c.	Select Create.
 

3.	On the scenario editor designer, add a Statement element.
 

4.	Rename the statement Welcome. Do not add any Display text as we will show it in the card instead.
 

5.	Select Cards.
 

6.	Select Add Card.
 

7.	Choose HeroCard. Add Title: Welcome to Lamna Healthcare Patient Service Portal
 

8.	Select Add Action and provide the following details:
a.	Action type: imBack
b.	Action value: "begin MCH_PatientService"
c.	Action title: "Lamna Healthcare Support"
 

9.	Click OK and view your completed scenario.  This will be used to kick off the conversation and allow the other MCH_PatientService scenario to be invoked through the authored card.
 

10.	Save and run to test your bot scenario MCH_PatientServiceWelcome scenario in the Web Chat.
 

11.	Exit the scenario designer.

Task 3: Configure Welcome Scenario as Automatic
In this task, we will set the MCH_ PatientServiceWelcome to be the “Automatic Welcome Scenario” in settings. This will always trigger the welcome scenario when a user starts a conversion with the Azure Health Bot.

1.	Navigate to Configuration > Conversation
 

2.	In the Interactions tab, scroll down to the Automatic Welcome section.
 

3.	In the Automatic welcome scenario dropdown, select the MCH_ PatientServiceWelcome scenario.
 

Task 4: Test Health Bot Escalation from Power Apps Portal to Dynamics 365 Omnichannel
1.	Navigate to Power Apps and click to open Lamna Healthcare Patient Portal.
 

2.	You should see the Health Bot “Let’s Chat” button in the lower right-hand corner of the screen.  This means the chat widget was successfully embedded into the Customer Self-service portal.  
 

3.	When you the click chat widget, bot will trigger a welcome scenario message we created and set as the default welcome message (MCH_PatientServiceWelcome).
 

4.	Navigate back to Power Apps and open Customer Service Workspace.
 
Note: Omnichannel for Customer Chat Widget will work only when you see the presence status is enabled.  There should be a splash loading screen that goes through multiple steps and then displays the status indicator as available once loaded.  (Status is enabled when green with checkmark in circle)
 
Splash screen:
 

5.	In the Health Bot in Lamna Healthcare Patient Portal, click Lamna Healthcare Support button, then the Live Agent button to witness the escalation into Omnichannel to chat with a live agent (your user!)
      

6.	Navigating back to Omnichannel for Customer Service, your user as the Live Agent should receive an incoming notification with Accept/Reject options for that chat.

7.	Click Accept to connect and chat with customer (In this case chat with the patient).
 

8.	As soon as Live Chat Agent accepts the incoming chat notification, Omnichannel for Customer Service has opened a Live Chat Widget and Agent would be able to see the entire bot conversation with user and continue the chat conversation with user for further assistance.
 

Congratulations! You have successfully extended the Azure Health Bot with custom scenarios and tested the end-to-end escalation scenario from a patient using the Azure Health Bot in Power Apps Portals to chatting with a Live Agent in Omnichannel for Customer Service.


