# Module 4 Lesson 1- Lab 2: Azure Health Bot

### Overview

The Azure Health Bot Service is a cloud platform that empowers developers in healthcare organizations to build and deploy their compliant, AI-powered Patient insights and health bots, that help them improve processes and reduce costs. It allows you to offer your users intelligent and personalized access to health-related information and interactions through a natural conversation experience.

With the service, healthcare organizations can build a "health bot instance" and integrate it with their systems that patients, nurses, doctors, and other representatives interact with. Building an instance allows you to:

-   Improve processes
-   Improve services
-   Improve outcomes
-   Reduces cost

The Health Bot Service contains **a built-in medical database**, including **triage protocols**. You can also extend a health bot instance to include your own scenarios and integrate with other IT systems and data sources. To learn more about Azure Health Bot, see [Azure Health Bot Overview](https://docs.microsoft.com/en-us/azure/health-bot/) on Microsoft Docs.

The Azure Health Bot focuses on the Enhance patient engagement priority scenario by creating a virtual bot health option to allow for new avenues of care with embedded insights.

![](./IMAGES/Lab02/L2P1.png)

This lab will focus on Lamna Healthcare Company.

![Timeline Description automatically generated](./IMAGES/Lab02/L2P2.png)

As part of their digital transformation efforts, Lamna Healthcare Company is seeking to streamline their patient engagement capabilities by implementing Azure Health Bot to help improve processes and services, such as entering medication requests. By allowing patients to interact with this service, Lamna Healthcare Company will move one step closer to their goal of improving patient outcomes while reducing overall costs.

In this lab, you'll play the role of a Lamna Healthcare IT developer and configure Azure Health Bot for a medication refill scenario.

### Learning objectives

In this lab, you will:

-   Set up Azure Health Bot
-   Configure Dynamics 365 Customer Service Omnichannel Live Chat
-   Embed Azure Health Bot in a Power Apps Portal
-   Extend Azure Health Bot with custom scenarios

### Exercise 1: Set Up Azure Health Bot

In this exercise, you will do the following:

-   Set up Health Bot from Azure Portal
-   Configure and enable the integration between Dynamics 365 Omnichannel and Health Bot
-   Configure and enable Bot channel to obtain a Bot Id

**Azure Health Bot** empowers developers in healthcare organizations to build and deploy AI-powered, compliant, conversational healthcare experiences at scale. It combines built-in medical database with natural language capabilities to understand clinical terminology and can be easily customized to support your organization's clinical use cases. The service ensures alignment with industry compliance requirements and is privacy protected to HIPAA standards. To learn more about Azure Health Bot, please reference this [Azure Health Bot documentation](https://docs.microsoft.com/en-us/azure/health-bot/).

**Task 1: Install Azure Health Bot in Azure Subscription**

1.  While logged in to your Microsoft 365 tenant, open a new tab in your internet browser incognito or in-private mode and navigate to Azure Portal at <https://portal.azure.com/>

1.  Search for **Azure Health Bot** in the top search bar and select it from the search results.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P3.png)

1.  Click **Create** button to create a new Azure Health Bot instance.

    ![Create Azure Health Bot subscription](./IMAGES/Lab02/L2P4.png)

1.  You will be redirected to the Azure Health Bot page. Enter the following information:
    1.  **Subscription**: PowerPlatformOpenHacks Subscription
    2.  **Resource Group**: IndustryLabs
    3.  **Name**: iaduser[x]-healthbot (e.g., iaduser01-healthbot, using your assigned user)
    4.  **Region**: East US
    5.  **Plan**: Free (F0)

        ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P5.png)

1.  Select **Review + Create**.

1.  On the **Review and create** page, verify your details are correct as Azure validates your Health Bot. After validation passes, the create button will become enabled. Click **Create**.

    Note: It will take few seconds to run the backend process before the Create button is enabled.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P6.png)

1.  You will be redirected to the **Deployment** page for your new Azure Health Bot.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P7.png)

1.  When deployment is complete, the **Go to resource** button will enable. Please wait until deployment is complete for the Azure Health Bot, then select **Go to resource** when enabled.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P8.png)

1.  You will be redirected to the **Resource** page for your new Azure Health Bot. Click the **Management portal** link in the Essential section to open your Azure Health Bot instance configuration page.

    Note: Please copy this Management portal link and store it to access the Health Bot later.

    ![Text, letter Description automatically generated](./IMAGES/Lab02/L2P9.png)

1.  You will be navigated to your new Azure Health Bot instance homepage.

    ![Text Description automatically generated](./IMAGES/Lab02/L2P10.png)

**Congratulations!** You have successfully created a new Health Bot instance in your Azure tenant.

**Task 2: Update Azure Health Bot Settings to Enable Dynamics 365 Integration**

1.  On the **Azure Health Bot** homepage, expand the side navigation bar to see the sitemap labels.

    ![Graphical user interface, text Description automatically generated](./IMAGES/Lab02/L2P11.png)

1.  After expanding, you will see the sitemap labels next to the icons.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P12.png)

1.  Select **Configuration** \> **Conversation** on the navigation bar.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P13.png)

1.  You will be landed in the **Interactions** tab.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P14.png)

1.  Select **Human Handoff** tab in the Conversation settings.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P15.png)

1.  Scroll to the bottom of the **Human Handoff** page. Under **Dynamics 365 Omnichannel**, toggle **Enabled** for **Bridge Messages**. This is required to allow communication and bridge messages between the Azure health Bot and Dynamics 365 Omnichannel for Customer Service.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P16.png)

1.  Click **Save** in the top right.
    ![](./IMAGES/Lab02/L2P17.png)

    Now let’s enable the Health Bot for **Microsoft Teams** Channel.

1.  Navigate to **Integration > Channels**.

    ![A screenshot of a computer screen Description automatically generated with medium confidence](./IMAGES/Lab02/L2P18.png)

1.  In the **Channels** list, select the toggle to **enable Microsoft Teams.**

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P19.png)

1.  This will bring out a side window with your **Bot Id** information. Copy and store the **BotId** for later to use when creating the Dynamics 365 Application User.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P20.png)

1.  Select **Save**. This should enable Teams channel and your Microsoft Teams toggle should reflect accordingly.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P21.png)

**Congratulations!** You completed the Azure Health Bot settings for integration with Microsoft Teams and Dynamics 365 Omnichannel for Customer Service.

**Task 3: Obtain Azure Application ID**

In this task, you will be using an Azure Application ID already created in our Azure tenant called “**MCH Application Id**”. Registering this Id establishes a trusted relationship between your Dynamics 365 app and the Microsoft identity platform. Using this Id, you will later create a Dynamics 365 Application User to bridge the authentication between Azure Health Bot and Power Apps.

1.  Navigate back to the Azure Portal and search for **App Registrations** in the **Search** box.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P22.png)

1.  You will be landed in the App registration homepage on the Owned applications tab.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P23.png)

1.  Select the **All applications** tab.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P24.png)

1.  To search for our Application Id, type **MCH Application Id** in the **Search** box.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P25.png)

1.  Select the **MCH Application Id** app registration resource. Copy and store the **Application (client) ID** for later to use when creating the Dynamics 365 Application User.

    Note: ID values have been removed in the screenshot for privacy purposes.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P26.png)

**Congratulations!** You have successfully obtained the MCH Application ID from Application Registrations in the Azure Portal.

### Exercise 2: Configure Omnichannel Live Chat

In this exercise, you will be configuring live chat for **Dynamics 365 Omnichannel for Customer Service**. Omnichannel for Customer Service offers a suite of capabilities that extend the power of Dynamics 365 Customer Service Enterprise to enable organizations to instantly connect and engage with their customers across digital messaging channels.

In the following tasks, you will complete the following:

1.  Assign Omnichannel agent security role
2.  Create an Application User using the **MCH Application Id** and your **Bot ID**
3.  Configure Queues for Bot and Agent Users
4.  Configure a Context Variable and Routing rule to route the message either to a Bot or Agent.
-   

**Task 1: Assign Omnichannel Agent Security Role**

1.  While in the In-Private or Incognito window, navigate to [Power Apps](https://make.powerapps.com/).

1.  Ensure the correct environment from the upper right **Environment** drop down is selected.

    ![](./IMAGES/Lab02/L2P27.png)

1.  Select the **gauge** icon in the upper right corner and navigate to **Advanced Settings**.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P28.png)

1.  A new window should open and navigate to Dynamics 365. It may take a while to load. If it’s been longer than a minute, stop and reload the page. It should then load faster. It will land you in the Business Management section of Dynamics 365.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P29.png)

1.  On the top command bar next to **Dynamics 365**, select **Settings** to open the drop-down, then select **Security** in the third column under **System**.

    ![Screenshot of Dynamics 365 navigation to settings and security on command bar](./IMAGES/Lab02/L2P30.png)

1.  Under **Security**, select **Users**.

    ![Screenshot of Users option first in the list of security settings](./IMAGES/Lab02/L2P31.png)

1.  Switch the **view** drop down from **Omnichannel Users** to **Enabled Users** for the grid view so that your user will show in the list.

    ![Screenshot of Switching view in drop down to from Omnichannel Users to Enabled Users](./IMAGES/Lab02/L2P32.png)

1.  While in the **Enabled User** list, scroll to find your user or use the **Search** bar.

    Note: If you are in an official training, search for your assigned user – IAD User [x]

    ![Screenshot of searching for user in enabled user list](./IMAGES/Lab02/L2P33.png)

1.  Select your user for the training and select **Manage Roles** on the top command bar.

    ![Screenshot of Selecting current IAD User in list and clicking Manage Roles button on command bar](./IMAGES/Lab02/L2P34.png)

1.  If necessary, select the **Omnichannel Agent** roles to assign to your user and select **OK**.

    ![Table Description automatically generated with medium confidence](./IMAGES/Lab02/L2P35.png)

**Congratulations!** You assigned the proper omnichannel agent role to your user to allow you to be a live agent in omnichannel.

**Task 2: Create Health Bot User in Dynamics 365 Customer Service**

We need two users to configure in Omnichannel for Dynamics 365 Customer Service:

-   **Health Bot User** – This is the Azure Health Bot user we created in the previous exercise.
-   **Omnichannel Agent** **User** – This is your current user whom you are logged into Dynamics 365. This will allow you to be a live agent in Customer Service who receives messages from portal users through Azure Bot escalations*. Note: For official trainings, this is your assigned user, iaduser[x]*

In this task, you will create a **Bot User** which helps connect **Azure Health Bot** with **Omnichannel live Chat**.

1.  Go to <https://admin.powerplatform.microsoft.com/>. Select your Microsoft Cloud for Healthcare environment from the list
    
    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P36.png)

1.  You will land on your environments detail page.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P37.png)

1.  Click the **Settings** button on the top command bar.

    ![Text, whiteboard Description automatically generated](./IMAGES/Lab02/L2P38.png)

1.  Expand **Users + permissions** and click **Application users**.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P39.png)

1.  Select (**+**) **New app user** button to create a new Application User.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P40.png)

1.  Select (+) **Add an app** on the create screen that slides out on the right side.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P41.png)

1.  Paste the **Application ID** (the Application (client) ID you obtained in the Azure portal for the supplied MCH Application ID) into the search box and select the app from the list. Click **Add** at the bottom right.

    ![Graphical user interface, text, application, Teams Description automatically generated](./IMAGES/Lab02/L2P42.png)

1.  Select a **Business unit** from the drop-down list (the options in the list will be unique for each Dynamics 365 environment). Click **Create** at the bottom right.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P43.png)

1.  Return to the **Dynamics 365 User** page, switch the view to **Enabled Users**.

    ![Screenshot of Dynamics 365 navigation to settings and security on command bar](./IMAGES/Lab02/L2P43A.png)
    
    ![Screenshot of Users option first in the list of security settings](./IMAGES/Lab02/L2P43B.png)

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P44.png)

1.  While in the **Enabled User** list, scroll to find your App user or use the **Search** bar. Double-click on the user or select the row and click **Edit**.

    Note: If you are in an official training, search for the Application User – MCH Application ID

    ![](./IMAGES/Lab02/L2P45.png)

1.  Change the form type from **User** to **Application User** above the User Name.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P46.png)

1.  You will see a new form appear that aligns to an Application User.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P47.png)

1.  In the **User Information** section, enter or select the following information and click the **Save** icon in the bottom right corner:
    1.  **User type**: Select **Bot application user**. This will *display a new field* to store the Bot application Id.
    1.  **Bot application ID**: This is the Azure Health BotId you copied when enabling the Teams channel. This field is displayed once the User Type is selected to be Bot application user.

        ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P48.png)

1.  Select **Manage Roles** on the command bar.

    ![Graphical user interface, text, application, Word Description automatically generated](./IMAGES/Lab02/L2P49.png)

1.  If necessary, assign the **Omnichannel Agent** role to the Bot User as you did for your own user in the previous task. This will allow the bot to act as an omnichannel agent like your user.

    ![Table Description automatically generated with medium confidence](./IMAGES/Lab02/L2P50.png)

**Congratulations**! You successfully created a Bot User and assigned to it the Omnichannel Agent role.

**Task 3: Create and Configure Omnichannel Queues**

In this task, you will create and configure the omnichannel queues necessary to communicate with the correct bot or agent depending on the situation.

1.  In <http://make.powerapps.com>, open the **Omnichannel admin center** app.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P51.png)

1.  Select **Queues** on the left navigation bar.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P52.png)

1.  Open **Default Messaging Queue**.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P53.png)

1.  We will now associate the Default messaging queue with the Bot User so it will respond to incoming messages from customers without agent (human) intervention.

1.  Select **Add Existing User** on the **User (Agents)** subgrid to add the Bot user you previously created.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P54.png)

1.  In the **Lookup Records** pane, search for your Bot User (**MCHApplicationId**) created in the earlier task.

    ![Graphical user interface, application, email Description automatically generated](./IMAGES/Lab02/L2P55.png)

1.  Select the record from the list and click **Add**.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P56.png)

1.  You should now see the Bot User (MCH Application Id) in the Users (Agents) list. **Save & Close.**

    Note: If the user does not populate after adding, make sure you assigned the omnichannel agent security role to the bot user in the previous task (it may take up to 15 minutes for changes to take effect).

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P57.png)

1.  Go back to the **Omnichannel queues** grid. Click **+** **New** to create a new Queue.

    ![Graphical user interface, application Description automatically generated with medium confidence](./IMAGES/Lab02/L2P58.png)

1.  Give the new Queue the following details:
    1.  **Name**: “Escalate To Human”
    1.  **Priority**: 1 (lower than default queue)
    1.  Click **Save**.

        ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P59.png)

1.  A Users (Agents) **subgrid should appear** on the right and your **user should be automatically added** to the list. If your user account is not on the list, add it through the Add Existing User button now. 

    The queue **Escalate To Human** is created to manage and redirect the incoming messages from a user to a Customer Service (human) Agent when Bot sends the user through to a live agent.

    ![A screenshot of a computer Description automatically generated](./IMAGES/Lab02/L2P60.png)

**Congratulations!** You have created the necessary queue to escalate to human agent and added the appropriate users to each messaging queue.

**Task 4: Update Live Work Stream with Context Variables and Routing Rules**

In this task, we will set up basic chat routing. This will allow for users to chat with a bot user in certain cases and a live human agent in other scenarios. The routing rules will allow chat to behave as follows:

-   **Route to Bot:** Initial customer conversation is through Health Bot in the default messaging queue. When the chat bot is first opened, route to Default queue which only contains the bot user (agent).
-   **Human Routing Rule**: When context variable **EscalateToAgent** is present and set to 1, we route to the queue that has only human users (agents) who can take over conversation.

1.  Navigate to **Work Streams**.

    ![Table Description automatically generated](./IMAGES/Lab02/L2P61.png)

1.  Select and edit the **Live chat workstream** .

    ![Graphical user interface, text, application, chat or text message Description automatically generated](./IMAGES/Lab02/L2P62.png)

1.  In the **Live chat** workstream record, select the **Context Variables** tab. Select **+ New**.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P63.png)

1.  Create the new Context Variable with the following details:
    1.  **DisplayName:** EscalateToAgent
    1.  **Name:** EscalateToAgent
    1.  **Type:** Number

        ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P64.png)

1.  Click **Save and Close**.

1.  You should now see the new Context Variable in the Live chat workstream.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P65.png)

1.  Select the **Routing Rules** tab. Click **+ Add** to create a new routing rule.

    ![Graphical user interface Description automatically generated](./IMAGES/Lab02/L2P66.png)

1.  Create the new Health Bot routing rule with the following details:
    1.  **Name:** ToHealthcareBot
    1.  **Queue**: Default messaging queue
    1.  No Conditions.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P67.png)

1.  Select **Save & Close.** On the Live chat workstream, click **+ Add** to add another new Routing Rule.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P68.png)

1.  Create the new Omnichannel Agent routing rule with the following details:
    1. **Name:** ToAgent
    1. **Queue:** EscalateToHuman
    1. **Add Condition:** Context Variable “EscalateToAgent = 1”

    ![Graphical user interface Description automatically generated](./IMAGES/Lab02/L2P69.png)

    ![Graphical user interface, application Description automatically generated with medium confidence](./IMAGES/Lab02/L2P70.png)

1.  Select **Save & Close**.

1.  On the Live chat workstream, you should now see the two **Routing Rules** we created for **Bot** (ToHealthcareBot) and **Agent** (ToAgent).

    ![Application Description automatically generated with medium confidence](./IMAGES/Lab02/L2P71.png)

**Congratulations!** You have created the proper context variable and routing rules that will allow customers to begin conversation with a health bot and escalate to a human agent.

**Task 5: Create Chat Widget for Health Bot**

1.  Navigate to **Chat**.

    ![A picture containing graphical user interface Description automatically generated](./IMAGES/Lab02/L2P72.png)

1.  Select **+New** Chat Widget.

    ![A picture containing graphical user interface Description automatically generated](./IMAGES/Lab02/L2P73.png)

1.  Give the Chat Widget a **Name** (eg., Patient Portal Chat Widget).

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P74.png)

1.  Click **Save**.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P75.png)

1.  After the record is saved, a **Widget Code Snippet** will be generated. Copy the code snippet and store it for later use.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P76.png)

**Congratulations!** In this exercise, you have successfully configured Customer Service Omnichannel Live chat by creating the necessary Users, Queues, Work Streams, Context Variables, Routing Rules, and Chat Widget. These all work together and allow patients to chat with a virtual health bot with the option to escalate up to a human agent if needed.

### Exercise 3: Embed Health Bot in Power Apps Portal

In this exercise, you will be embedding the **Omnichannel Chat Widget** into the Power Apps Customer self-service portal using Portal Management configuration. In your environment, we created a Lamna Healthcare Company Portal using the **Customer self-service portal** template before deploying Microsoft Cloud for Healthcare. Now we will configure the chat widget to show on the customer website.

Customer self-service portal: A customer self-service portal enables customers to access self-service knowledge, support resources, view the progress of their cases, and provide feedback.

Portal Management: Application to help you get started with the advanced portal configuration. In this walk-through, you will learn how to configure Chat widget in Portal Management app.

1.  In <http://make.powerapps.com>, open the **Portal Management** app.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P77.png)

1.  Select **Content Snippets** in the left navigation pane

    ![Table Description automatically generated with medium confidence](./IMAGES/Lab02/L2P78.png)

1.  In **Active Content Snippets**, type **Chat** in the **Search** box and press **enter**.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P79.png)

1.  You will see two **Chat Widget Code** records retrieved in the list. Click to open the Chat Widget Code record related to **Customer Self-service.**

    ![Table Description automatically generated with low confidence](./IMAGES/Lab02/L2P80.png)

1.  In the **Chat Widget Code** record associated with Customer self-service, select **Value (HTML) > Html** Tab and then paste the Chat Widget Code snippet that you copied and stored in the previous task.

    ![Graphical user interface, text, application, Teams Description automatically generated](./IMAGES/Lab02/L2P81.png)

1.  Click **Save & Close**.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P82.png)

1.  Now open the other **Chat Widget Code** associated with the **Healthcare Patient Portal** website.

    ![A picture containing text Description automatically generated](./IMAGES/Lab02/L2P83.png)

1.  In the **Chat Widget Code** record associated with the Healthcare Patient Portal, paste in **Value (HTML)** the same Chat Widget Code snippet that you copied and stored previously and added to the customer self-service chat widget code. Replace any value that may have already populated the field.

    ![Graphical user interface, text, application, email, Teams Description automatically generated](./IMAGES/Lab02/L2P84.png)

1.  Select **Save and Close**.

**Congratulations!** In this exercise you have successfully updated the chat widget in the Power App Portal Content Snippets. With this configuration, the Health Bot will be visible on the Power Apps portal for both the customer self-service template and the healthcare patient portal template.

### Exercise 4: Extend Azure Health Bot with Custom Scenarios

**Dynamics 365 Omnichannel** integration allows the patient to interact with **Azure Health Bot** using the Dynamics 365 chat widget to access the medical knowledge and your custom scenarios. It also, allows the escalation of a bot conversation to a live agent to continue the interaction. When escalating a conversation, Dynamics passes along the conversation history and the context to the agent.

In this exercise, you will be doing the following:

-   Designing the below Health Bot Scenario called **MCH_PatientService**

    ![Diagram Description automatically generated](./IMAGES/Lab02/L2P92.png)

-   Design another Health Bot Scenario called **MCH_PatientServiceWelcome**. This scenario holds the starting statement which will allow the user to invoke the **MCH_PatientService** scenario.
-   Set the **Automatic Welcome Scenario** to be the MCH_PatientServiceWelcome custom scenario you create. This will begin the scenario when a user first interacts with the Health Bot.

**Task 1: Create MCH_PatientService Scenario**

In this task, you will create the **MCH_PatientService** bot scenario using the designer canvas.

1.  Navigate back to the Azure **Health Bot instance** homepage where you set the bot settings. This is the portal management link you copied from the Azure portal.

    ![Text Description automatically generated](./IMAGES/Lab02/L2P93.png)

1.  Click to expand the side navigation bar. Navigate to **Scenario > Manage**.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P94.png)

1.  Click **+ New** button on the top ribbon.

    ![Graphical user interface, text Description automatically generated](./IMAGES/Lab02/L2P95.png)

1.  Provide the following details for the new health bot scenario:
    1.  **Name**: MCH_PatientService
    2.  **Scenario ID**: MCH_PatientService

        ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P96.png)

1.  Now let’s design the scenario conversation. It should navigate you directly to the designer. If not, select the MCH_PatientService scenario in **Scenarios > Manage** to edit.

    ![A screenshot of a computer Description automatically generated](./IMAGES/Lab02/L2P97.png)

**Step 1: Add Bot Introduction Statement**

1.  Add a beginning **Statement** to the scenario by selecting the icon and dragging Statement icon onto the editor.

    ![A picture containing application Description automatically generated](./IMAGES/Lab02/L2P98.png)

1.  Enter the Display Text: **Hi there, I’m your Healthcare Assistant.**

1.  Select the **pencil** next to **Statement** in the top bar and change Title to **Intro**. Click **OK**.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P99.png)

1.  Click **OK**. You will see the intro statement added to the designer canvas. Double click anytime to edit.

    ![A picture containing graphical user interface Description automatically generated](./IMAGES/Lab02/L2P100.png)

**Step 2: Add Statement for Medication Request or Live Agent**

This section prompts two buttons Medication Refill and Live Agent. When user click any one of the buttons it will set the appropriate text to the variable MedicationOrAgent.

1.  Select **Prompt** icon and drag down onto canvas

    ![A picture containing application Description automatically generated](./IMAGES/Lab02/L2P101.png)

1.  Enter the following details:
    1.  **Display Text**: Would you like to request a medication refill or chat with a live agent?
    2.  **Variable name**: MedicationOrAgent
    3.  **Data type**: string
    4.  Rename Title to **MedOrAgent**.

1.  Click **Cards** button.

    ![Graphical user interface, text, application, email, Teams Description automatically generated](./IMAGES/Lab02/L2P102.png)

1.  Select **Add Card**.

    ![A picture containing chart Description automatically generated](./IMAGES/Lab02/L2P103.png)

1.  Select Card Type as **HeroCard.** Leave title blank as we already prompted with display text.

1.  Click **Add Action** button twice to add two actions:
    1.  For the first action, select the following:
        1.  **Action type**: imBack
        1.  **Action value**: MedicationRefill
        1.  **Action title**: “Medication Refill”
    1.  For the second action, fill in the following:
        1.  **Action type**: imBack
        1.  **Action value**: LiveAgent
        1.  **Action title**: “Live Agent”

        ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P104.png)

1.  Click **Ok** three times to get back to designer

    ![Shape Description automatically generated with medium confidence](./IMAGES/Lab02/L2P105.png)

    ![Graphical user interface, text, application, email, Teams Description automatically generated](./IMAGES/Lab02/L2P106.png)

1.  Connect **Intro** and **Appointment** boxes. Select the bottom circle on **Intro** and drag it to the top circle on the new prompt. An arrow will automatically appear when you try to connect Intro and MedOrAgent boxes using ellipse pointer.

    ![Diagram Description automatically generated](./IMAGES/Lab02/L2P107.png)

1.  Select **Save**.

    ![A screenshot of a computer Description automatically generated with medium confidence](./IMAGES/Lab02/L2P108.png)

1.  Select **Run** to see the output in the WebChat on the right.

    ![Diagram Description automatically generated](./IMAGES/Lab02/L2P109.png)

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P110.png)

**Step 3: Add MedicationOrAgent Decision Branch**

This section checks whether the user has clicked Medication Refill or Live Agent with the help of the variable MedicationOrAgent. It will redirect the message accordingly.

1.  Add a **Branch** to the designer canvas.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P111.png)

1.  Enter the following in the javascript Boolean expression: **scenario.MedicationOrAgent === "MedicationRefill"**

1.  Rename to **IsMedRefill.** Select **OK**.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P112.png)

1.  Select and drag the bottom circle of the **MedOrAgent** prompt to the top circle of the **IsMedRefill** branch decision to connect them.

    ![Diagram Description automatically generated](./IMAGES/Lab02/L2P113.png)

**Step 4: Prompt User to Enter Data for Medication Refill Option**

1.  Add a **Prompt** element. This will be used to display the Form data (using Adaptive Card) to capture Patient name, email, and phone to create an appointment.

    ![A picture containing application Description automatically generated](./IMAGES/Lab02/L2P114.png)

1.  Add the following details:
    1.  **Variable name**: formData
    2. **Variable Data Type**: Object
    3.  Change Title to **Submit**
    4.  Do not add any display text since the adaptive card will display instead

        ![Graphical user interface, text, application, email, Teams Description automatically generated](./IMAGES/Lab02/L2P115.png)

1.  Click **Cards** button > **Add Card** > **Adaptive Card**.

1.  Refer to the lab resources file **AdaptiveCardForMedicationRefill.txt** and copy the json content and paste it in the json section of your card.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P116.png)

1.  Select **OK** three times to get back to the designer.
  
1.  Connect the **Yes** condition of the **IsMedRefill** branch to the **Submit** prompt.

    ![Diagram Description automatically generated](./IMAGES/Lab02/L2P117.png)

1.  Save and run your current scenario. If you don’t save the scenario first, it won’t run with updates since the last save. If you haven’t saved at all, it won’t recognize any conversation.

    ![Graphical user interface Description automatically generated with medium confidence](./IMAGES/Lab02/L2P118.png)

1.  You should see the below output when running the conversation and selecting “Medication Refill” card when prompted to show the AdaptiveCard.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P119.png)

**Step 5: Add Confirmation Statement**

1.  Add a **Statement** element.

    ![A picture containing application Description automatically generated](./IMAGES/Lab02/L2P120.png)

1.  Add **Display text** as the following: **scenario.formData.myName + " - Thanks for providing the information, we have created a Medication Request for you regarding the following medication: " + scenario.formData.myMedReq**

1.  Rename the statement to **Confirmation**.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P121.png)

1.  Connect the **Submit** step to the **Confirmation** step in the designer canvas.

    ![Diagram Description automatically generated](./IMAGES/Lab02/L2P122.png)

1.  Select **Save** and **Run** to see your scenario in the webchat.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P123.png)

1.  Fill in information for the request and click **Submit** to see the confirmation text.

    ![Graphical user interface, application, email Description automatically generated](./IMAGES/Lab02/L2P124.png)

**Step 6: Invoke Live Agent Action**

1.  Add a **Statement** element to the canvas.

    ![A picture containing application Description automatically generated](./IMAGES/Lab02/L2P125.png)

1.  Enter **Display Text**: **Please wait, I am transferring your request to a live agent for further assistance.**
  
1.  Rename the statement to **Live Chat**.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P126.png)

1.  Click **OK** to return to the designer page.
  
1.  Connect the **No** decision of the **IsMedRefill** branch to the **Live Chat** statement.

    ![Diagram Description automatically generated](./IMAGES/Lab02/L2P127.png)

**Step 7: Add Action to Invoke Escalation**

1.  Add an **Action** element to the canvas, used to trigger an escalation to Omnichannel Live Agent

    ![](./IMAGES/Lab02/L2P128.png)

1.  Add the following code in the action, which will trigger the Live agent chat:

    session.sendChannelData('Escalating...', {

    "tags": JSON.stringify({type: "Escalate", context: {"EscalateToAgent": 1}})

    });

1.  Name the action **Escalate**. Click **OK** to return to the designer page.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P129.png)

1.  Connect the **Live Chat** to the new **EscalateToAgent** action. You completed the final connection!

    ![Diagram Description automatically generated](./IMAGES/Lab02/L2P130.png)

1.  Save and run your scenario to see the full scenario output.

1.  Test all logical paths. Selecting Live Agent in the authored card should show the escalation action.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P131.png)

1.  Exit the **MCH_PatientSerivce** scenario editor.

    ![Graphical user interface, application, Word Description automatically generated](./IMAGES/Lab02/L2P132.png)

**Task 2: Create MCH_PatientServiceWelcome Scenario**

In this task, you will create another bot scenario called **MCH_PatientServiceWelcome** to invoke the **MCH_PatientService** scenario.

1.  On the Azure Health Bot scenarios page, select **+New** to create another new scenario

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P133.png)

1.  Provide the following details for the new scenario and click **Create**:
    1.  **Name**: MCH_PatientServiceWelcome
    1.  **Scenario ID**: MCH_PatientServiceWelcome

        ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P134.png)

1.  On the scenario editor designer, add a **Statement** element.

    ![A picture containing application Description automatically generated](./IMAGES/Lab02/L2P135.png)

1.  Rename the statement **Welcome**. Do not add any Display text as we will show it in the card instead.

    ![Graphical user interface, text, application, email, Teams Description automatically generated](./IMAGES/Lab02/L2P136.png)

1.  Select **Cards.**

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P137.png)

1.  Select **Add Card**.

    ![A picture containing graphical user interface Description automatically generated](./IMAGES/Lab02/L2P138.png)

1.  Choose **HeroCard.** Add **Title**: **Welcome to Lamna Healthcare Patient Service Portal**

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P139.png)

1.  Select **Add Action** and provide the following details:
    1.  **Action type**: imBack
    1.  **Action value**: "begin MCH_PatientService"
    1.  **Action title**: "Lamna Healthcare Support"

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P140.png)

1.  Click **OK** and view your completed scenario. This will be used to kick off the conversation and allow the other MCH_PatientService scenario to be invoked through the authored card.

    ![Table Description automatically generated with low confidence](./IMAGES/Lab02/L2P141.png)

1.  Save and run to test your bot scenario **MCH_PatientServiceWelcome** scenario in the Web Chat.

    ![Text Description automatically generated with medium confidence](./IMAGES/Lab02/L2P142.png)

1.  Exit the scenario designer.

**Task 3: Configure Welcome Scenario as Automatic**

In this task, we will set the MCH\_ PatientServiceWelcome to be the “Automatic Welcome Scenario” in settings. This will always trigger the welcome scenario when a user starts a conversion with the **Azure** **Health Bot**.

1.  Navigate to **Configuration > Conversation**

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P143.png)

1.  In the **Interactions** tab, scroll down to the **Automatic Welcome** section.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P144.png)

1.  In the **Automatic welcome** scenario dropdown, select the **MCH_PatientServiceWelcomeScenario**.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P145.png)

**Task 4: Test Health Bot Escalation from Power Apps Portal to Dynamics 365 Omnichannel**

1.  Navigate to **Power Apps** and click to open **Lamna Healthcare Patient Portal**.

    ![Open Lamna Healthcare Portal](./IMAGES/Lab02/L2P146.png)

1.  You should see the Health Bot “Let’s Chat” button in the lower right-hand corner of the screen. This means the chat widget was successfully embedded into the Customer Self-service portal.

    ![Graphical user interface, website Description automatically generated](./IMAGES/Lab02/L2P147.png)

1.  When you the click chat widget, bot will trigger a welcome scenario message we created and set as the default welcome message **(MCH_PatientServiceWelcome)**.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab02/L2P148.png)

1.  Navigate back to **Power Apps** and open **Customer Service Workspace.**

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P149.png)

    **Note**: Omnichannel for Customer Chat Widget will work only when you see the presence status is enabled. There should be a splash loading screen that goes through multiple steps and then displays the status indicator as available once loaded. (Status is enabled when green with checkmark in circle**)**

    ![Check presence status](./IMAGES/Lab02/L2P150.png)

    Splash screen:

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab02/L2P151.png)

1.  In the **Health Bot in Lamna Healthcare Patient Portal**, click **Lamna Healthcare Support** button, then the **Live Agent** button to witness the escalation into Omnichannel to chat with a live agent (your user!)

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab02/L2P152.png) ![Graphical user interface, text, application, chat or text message Description automatically generated](./IMAGES/Lab02/L2P153.png)

1.  Navigating back to **Omnichannel for Customer Service**, your user as the Live Agent should receive an incoming notification with Accept/Reject options for that chat.

1.  Click **Accept** to connect and chat with customer (In this case chat with the **patient**).

    ![live agent notification on Customer Service](./IMAGES/Lab02/L2P154.png)

1.  As soon as Live Chat Agent accepts the incoming chat notification, Omnichannel for Customer Service has opened a **Live Chat Widget** and Agent would be able to see the entire bot conversation with user and continue the chat conversation with user for further assistance.

    ![live agent notification on Customer Service](./IMAGES/Lab02/L2P155.png)

**Congratulations!** You have successfully extended the Azure Health Bot with custom scenarios and tested the end-to-end escalation scenario from a patient using the Azure Health Bot in Power Apps Portals to chatting with a Live Agent in Omnichannel for Customer Service.
