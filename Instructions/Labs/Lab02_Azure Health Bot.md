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

![[](media/df4dee19dba74e977d1d001c9dbd3a3d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P1.png)

This lab will focus on Lamna Healthcare Company.

![[Timeline Description automatically generated](media/c10dc56b18504fc74d826e67b4779581.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P2.png)

As part of their digital transformation efforts, Lamna Healthcare Company is seeking to streamline their patient engagement capabilities by implementing Azure Health Bot to help improve processes and services, such as entering medication requests. By allowing patients to interact with this service, Lamna Healthcare Company will move one step closer to their goal of improving patient outcomes while reducing overall costs.

In this lab, you'll play the role of a Lamna Healthcare IT developer and configure Azure Health Bot for a medication refill scenario.

### Learning objectives

In this lab, you will:

-   Set up Azure Health Bot
-   Configure Dynamics 365 Customer Service Omnichannel Live Chat
-   Embed Azure Health Bot in a Power Apps Portal
-   Extend Azure Health Bot with custom scenarios

### Step 1: Set Up Azure Health Bot

In this exercise, you will do the following:

-   Set up Health Bot from Azure Portal
-   Configure and enable the integration between Dynamics 365 Omnichannel and Health Bot
-   Configure and enable Bot channel to obtain a Bot Id

**Azure Health Bot** empowers developers in healthcare organizations to build and deploy AI-powered, compliant, conversational healthcare experiences at scale. It combines built-in medical database with natural language capabilities to understand clinical terminology and can be easily customized to support your organization's clinical use cases. The service ensures alignment with industry compliance requirements and is privacy protected to HIPAA standards. To learn more about Azure Health Bot, please reference this [Azure Health Bot documentation](https://docs.microsoft.com/en-us/azure/health-bot/).

**Task 1: Install Azure Health Bot in Azure Subscription**

1.  While logged in to your Microsoft 365 tenant, open a new tab in your internet browser incognito or in-private mode and navigate to Azure Portal at <https://portal.azure.com/>
1.  Search for **Azure Health Bot** in the top search bar and select it from the search results.

    ![[Graphical user interface, text, application, email Description automatically generated](media/a65f6285399bdbea243f25673a5d8f49.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P3.png)

1.  Click **Create** button to create a new Azure Health Bot instance.

    ![[Create Azure Health Bot subscription](media/118bd676415131fdddd8f5fd46640242.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P4.png)

1.  You will be redirected to the Azure Health Bot page. Enter the following information:
    1.  **Subscription**: PowerPlatformOpenHacks Subscription
    2.  **Resource Group**: IndustryLabs
    3.  **Name**: iaduser[x]-healthbot (e.g., iaduser01-healthbot, using your assigned user)
    4.  **Region**: East US
    5.  **Plan**: Free (F0)

        ![[Graphical user interface, text, application, email Description automatically generated](media/2404692a9eb1c50aa92368d1c29f2884.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P5.png)

1.  Select **Review + Create**.

1.  On the **Review and create** page, verify your details are correct as Azure validates your Health Bot. After validation passes, the create button will become enabled. Click **Create**.

    Note: It will take few seconds to run the backend process before the Create button is enabled.

    ![[Graphical user interface, text, application, email Description automatically generated](media/e3a5ecbbc2c1a6b50a71cfacd0b04066.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P6.png)

1.  You will be redirected to the **Deployment** page for your new Azure Health Bot.

    ![[Graphical user interface, text, application, email Description automatically generated](media/4ffffa5803371734328aee8b5ebec6ed.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P7.png)

1.  When deployment is complete, the **Go to resource** button will enable. Please wait until deployment is complete for the Azure Health Bot, then select **Go to resource** when enabled.

    ![[Graphical user interface, text, application, email Description automatically generated](media/ac8ddd40635ce57751ed7a2eb7244758.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P8.png)

1.  You will be redirected to the **Resource** page for your new Azure Health Bot. Click the **Management portal** link in the Essential section to open your Azure Health Bot instance configuration page.
2.  

    Note: Please copy this Management portal link and store it to access the Health Bot later.

    ![[Text, letter Description automatically generated](media/53d0583b6517951ee5e9e03bfd90d7be.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P9.png)

1.  You will be navigated to your new Azure Health Bot instance homepage.

    ![[Text Description automatically generated](media/52f9eefb1d4ed9c2d11c32ce39d589e2.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P10.png)

**Congratulations!** You have successfully created a new Health Bot instance in your Azure tenant.

**Task 2: Update Azure Health Bot Settings to Enable Dynamics 365 Integration**

1.  On the **Azure Health Bot** homepage, expand the side navigation bar to see the sitemap labels.

    ![[Graphical user interface, text Description automatically generated](media/28b505ad4ef61e0908ccc38cce4edd3f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P11.png)

1.  After expanding, you will see the sitemap labels next to the icons.

    ![[Graphical user interface, text, application Description automatically generated](media/af26ac689dd10446c23f0aaa289759c9.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P12.png)

1.  Select **Configuration** \> **Conversation** on the navigation bar.

    ![[Graphical user interface, text, application Description automatically generated](media/6680b89dbb7d820457c36561e7f9837b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P13.png)

1.  You will be landed in the **Interactions** tab.

    ![[Graphical user interface, text, application, email Description automatically generated](media/5917220387c308aa24a7312572f02222.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P14.png)

1.  Select **Human Handoff** tab in the Conversation settings.

    ![[Graphical user interface, text, application, email Description automatically generated](media/12b5659e9cf72952080a3719a831e058.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P15.png)

1.  Scroll to the bottom of the **Human Handoff** page. Under **Dynamics 365 Omnichannel**, toggle **Enabled** for **Bridge Messages**. This is required to allow communication and bridge messages between the Azure health Bot and Dynamics 365 Omnichannel for Customer Service.

    ![[Graphical user interface, text, application, email Description automatically generated](media/ed9dd541bc7087a644bb594204b97feb.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P16.png)

1.  Click **Save** in the top right.
-   ![[](media/3ae097b8d24e332135e28974ac75c82b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P17.png)

Now let’s enable the Health Bot for **Microsoft Teams** Channel.

1.  Navigate to **Integration > Channels**.

    ![[A screenshot of a computer screen Description automatically generated with medium confidence](media/f6fb259069e6cffaddc26ea17780d922.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P18.png)

1.  In the **Channels** list, select the toggle to **enable Microsoft Teams.**

    ![[Graphical user interface, text, application, email Description automatically generated](media/7b09cf75cd363f072946ae70a13f4ed6.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P19.png)

1.  This will bring out a side window with your **Bot Id** information. Copy and store the **BotId** for later to use when creating the Dynamics 365 Application User.

    ![[Graphical user interface, application Description automatically generated](media/d4fb13080064608042c9aec426ccfa8d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P20.png)

1.  Select **Save**. This should enable Teams channel and your Microsoft Teams toggle should reflect accordingly.

    ![[Graphical user interface, text, application, email Description automatically generated](media/23e70b74e96269a6d816640975d6314c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P21.png)

**Congratulations!** You completed the Azure Health Bot settings for integration with Microsoft Teams and Dynamics 365 Omnichannel for Customer Service.

**Task 3: Obtain Azure Application ID**

In this task, you will be using an Azure Application ID already created in our Azure tenant called “**MCH Application Id**”. Registering this Id establishes a trusted relationship between your Dynamics 365 app and the Microsoft identity platform. Using this Id, you will later create a Dynamics 365 Application User to bridge the authentication between Azure Health Bot and Power Apps.

1.  Navigate back to the Azure Portal and search for **App Registrations** in the **Search** box.

    ![[Graphical user interface, text, application, email Description automatically generated](media/880203f33b48dd5a45e246ceda634900.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P22.png)

1.  You will be landed in the App registration homepage on the Owned applications tab.

    ![[Graphical user interface, text, application, email Description automatically generated](media/e5d5ad8a841079bc44afe93da9a96c84.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P23.png)

1.  Select the **All applications** tab.

    ![[Graphical user interface, text, application, email Description automatically generated](media/225827994cc3b027e0206ae3a03b1663.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P24.png)

1.  To search for our Application Id, type **MCH Application Id** in the **Search** box.

    ![[Graphical user interface, text, application, email Description automatically generated](media/7465861b1d7ed32268c16628e2a583f3.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P25.png)

1.  Select the **MCH Application Id** app registration resource. Copy and store the **Application (client) ID** for later to use when creating the Dynamics 365 Application User.

    Note: ID values have been removed in the screenshot for privacy purposes.

    ![[Graphical user interface, text, application, email Description automatically generated](media/e2f4af67d7c0e46db4986ad00b291bd2.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P26.png)

**Congratulations!** You have successfully obtained the MCH Application ID from Application Registrations in the Azure Portal.

### Step 2: Configure Omnichannel Live Chat

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

    ![[](media/118bf5867e47b80161dc93e75a5cef91.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P27.png)

1.  Select the **gauge** icon in the upper right corner and navigate to **Advanced Settings**.

    ![[Graphical user interface, application Description automatically generated](media/26d7f778f6db24083fd5f0fc77101de9.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P28.png)

1.  A new window should open and navigate to Dynamics 365. It may take a while to load. If it’s been longer than a minute, stop and reload the page. It should then load faster. It will land you in the Business Management section of Dynamics 365.

    ![[Graphical user interface, text, application, email Description automatically generated](media/bfcdad8c3daa5eb23e266aa932b4b341.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P29.png)

1.  On the top command bar next to **Dynamics 365**, select **Settings** to open the drop-down, then select **Security** in the third column under **System**.

    ![[Screenshot of Dynamics 365 navigation to settings and security on command bar](media/8df791e0613a679d2667dfda6ad39d00.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P30.png)

1.  Under **Security**, select **Users**.

    ![[Screenshot of Users option first in the list of security settings](media/d56e54332566174314f7f98e4b2868da.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P31.png)

1.  Switch the **view** drop down from **Omnichannel Users** to **Enabled Users** for the grid view so that your user will show in the list.

    ![[Screenshot of Switching view in drop down to from Omnichannel Users to Enabled Users](media/4bb54de365815f3f95a48ceb32e4184b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P32.png)

1.  While in the **Enabled User** list, scroll to find your user or use the **Search** bar.

    Note: If you are in an official training, search for your assigned user – IAD User [x]

    ![[Screenshot of searching for user in enabled user list](media/07f63477e1de63e1e662c2e29930b06f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P33.png)

1.  Select your user for the training and select **Manage Roles** on the top command bar.

    ![[Screenshot of Selecting current IAD User in list and clicking Manage Roles button on command bar](media/2fea347790e3a9500986ebef69801b9f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P34.png)

1.  Select the **Omnichannel Agent** roles to assign to your user and select **OK**.

    ![[Table Description automatically generated with medium confidence](media/b05a09d5daad58c6cd7c7b2ed0f05699.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P35.png)

**Congratulations!** You assigned the proper omnichannel agent role to your user to allow you to be a live agent in omnichannel.

**Task 2: Create Health Bot User in Dynamics 365 Customer Service**

We need two users to configure in Omnichannel for Dynamics 365 Customer Service:

-   **Health Bot User** – This is the Azure Health Bot user we created in the previous exercise.
-   **Omnichannel Agent** **User** – This is your current user whom you are logged into Dynamics 365. This will allow you to be a live agent in Customer Service who receives messages from portal users through Azure Bot escalations*. Note: For official trainings, this is your assigned user, iaduser[x]*

In this task, you will create a **Bot User** which helps connect **Azure Health Bot** with **Omnichannel live Chat**.

1.  Go to <https://admin.powerplatform.microsoft.com/>. Select your Microsoft Cloud for Healthcare environment from the list
    
    ![[Graphical user interface, text, application Description automatically generated](media/1836537d73376573e5fb9d2b7558e082.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P36.png)

1.  You will land on your environments detail page.

    ![[Graphical user interface, text, application, email Description automatically generated](media/ef6fd936eacf8812499e25fbbaac2b61.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P37.png)

1.  Click the **Settings** button on the top command bar.

    ![[Text, whiteboard Description automatically generated](media/85896a835a3355e762af5fe9840d9bad.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P38.png)

1.  Expand **Users + permissions** and click **Application users**.

    ![[Graphical user interface, text, application, email Description automatically generated](media/c8a2f4bc9448863f58f0f8420f8139cc.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P39.png)

1.  Select (**+**) **New app user** button to create a new Application User.

    ![[Graphical user interface, text, application, email Description automatically generated](media/935cbf1daaa11d4ab5fc020ab9014ef8.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P40.png)

1.  Select (+) **Add an app** on the create screen that slides out on the right side.

    ![[Graphical user interface, text, application, email Description automatically generated](media/e5d95c0f349069e99f0cf6d5fefcad2b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P41.png)

2.  Paste the **Application ID** (the Application (client) ID you obtained in the Azure portal for the supplied MCH Application ID) into the search box and select the app from the list. Click **Add** at the bottom right.

    ![[Graphical user interface, text, application, Teams Description automatically generated](media/04529b8785762351e44e2e906f5fced3.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P42.png)

1.  Select a **Business unit** from the drop-down list (the options in the list will be unique for each Dynamics 365 environment). Click **Create** at the bottom right.

    ![[Graphical user interface, text, application Description automatically generated](media/766532b9d83e34aa9b8b41dd66e934b8.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P43.png)

1.  Return to the **Dynamics 365 User** page, switch the view to **Enabled Users**.

    ![[Graphical user interface, text, application Description automatically generated](media/985aae3322d74c4bc36d775810b35e47.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P44.png)

1.  While in the **Enabled User** list, scroll to find your App user or use the **Search** bar. Double-click on the user or select the row and click **Edit**.

    Note: If you are in an official training, search for the Application User – MCH Application ID

    ![[](media/abd8a20335589b70afb5ebf62c687f50.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P45.png)

1.  Change the form type from **User** to **Application User** above the User Name.

    ![[Graphical user interface, text, application Description automatically generated](media/4a1e0727b512c95398686e7b7dcd41c7.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P46.png)

1.  You will see a new form appear that aligns to an Application User.

    ![[Graphical user interface, application Description automatically generated](media/188b4b17bee4759cb8c95aec9e9f377f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P47.png)

1.  In the **User Information** section, enter or select the following information and click the **Save** icon in the bottom right corner:
    1.  **User type**: Select **Bot application user**. This will *display a new field* to store the Bot application Id.
    2.  **Bot application ID**: This is the Azure Health BotId you copied when enabling the Teams channel. This field is displayed once the User Type is selected to be Bot application user.

        ![[Graphical user interface, text, application Description automatically generated](media/613b59124cdcbc567f57ec3f6bd36a65.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P48.png)

1.  Select **Manage Roles** on the command bar.

    ![[Graphical user interface, text, application, Word Description automatically generated](media/e0df0d9fd01df99602ded8488485f9f0.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P49.png)

1.  Assign the **Omnichannel Agent** role to the Bot User as you did for your own user in the previous task. This will allow the bot to act as an omnichannel agent like your user.

    ![[Table Description automatically generated with medium confidence](media/b05a09d5daad58c6cd7c7b2ed0f05699.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P50.png)

**Congratulations**! You successfully created a Bot User and assigned to it the Omnichannel Agent role.

**Task 3: Create and Configure Omnichannel Queues**

In this task, you will create and configure the omnichannel queues necessary to communicate with the correct bot or agent depending on the situation.

1.  In <http://make.powerapps.com>, open the **Omnichannel admin center** app.

    ![[Graphical user interface, text, application, email Description automatically generated](media/4a2241abec19cb58b0fa8d53e26568c6.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P51.png)

1.  Select **Queues** on the left navigation bar.

    ![[Graphical user interface, application Description automatically generated](media/4429705a7d07ee921c512d1d56aa0549.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P52.png)

1.  Open **Default Messaging Queue**.

    ![[Graphical user interface, text, application Description automatically generated](media/c381d8b1a189a23a51aba7c4e56b233e.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P53.png)

1.  We will now associate the Default messaging queue with the Bot User so it will respond to incoming messages from customers without agent (human) intervention.

1.  Select **Add Existing User** on the **User (Agents)** subgrid to add the Bot user you previously created.

    ![[Graphical user interface, text, application Description automatically generated](media/53cf7717406aeb991c1c2cbd9ed01202.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P54.png)

1.  In the **Lookup Records** pane, search for your Bot User (**MCHApplicationId**) created in the earlier task.

    ![[Graphical user interface, application, email Description automatically generated](media/1ef135ce446f7448e5f6bc0b394a4448.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P55.png)

1.  Select the record from the list and click **Add**.

    ![[Graphical user interface, application Description automatically generated](media/c96c1e82e974a167ddf6e76e5966c434.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P56.png)

1.  You should now see the Bot User (MCH Application Id) in the Users (Agents) list. **Save & Close.**

    Note: If the user does not populate after adding, make sure you assigned the omnichannel agent security role to the bot user in the previous task (it may take up to 15 minutes for changes to take effect).

    ![[Graphical user interface, text, application Description automatically generated](media/e0629b9ccfa1f6a18f76466cae90165c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P57.png)

1.  Go back to the **Omnichannel queues** grid. Click **+** **New** to create a new Queue.

    ![[Graphical user interface, application Description automatically generated with medium confidence](media/87c1634389cce5500645938304e9a677.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P58.png)

1.  Give the new Queue the following details:
    1.  **Name**: “Escalate To Human”
    2.  **Priority**: 1 (lower than default queue)
    3.  Click **Save**.

        ![[Graphical user interface, application Description automatically generated](media/a33a43043a6c27bc3242c3a98a365144.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P59.png)

1.  A Users (Agents) **subgrid should appear** on the right and your **user should be automatically added** to the list. If your user account is not on the list, add it through the Add Existing User button now.
2.  

    The queue **Escalate To Human** is created to manage and redirect the incoming messages from a user to a Customer Service (human) Agent when Bot sends the user through to a live agent.

    ![[A screenshot of a computer Description automatically generated](media/3a8c720d495e6f1e3e8e233f29feb698.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P60.png)

**Congratulations!** You have created the necessary queue to escalate to human agent and added the appropriate users to each messaging queue.

**Task 4: Update Live Work Stream with Context Variables and Routing Rules**

In this task, we will set up basic chat routing. This will allow for users to chat with a bot user in certain cases and a live human agent in other scenarios. The routing rules will allow chat to behave as follows:

-   **Route to Bot:** Initial customer conversation is through Health Bot in the default messaging queue. When the chat bot is first opened, route to Default queue which only contains the bot user (agent).
-   **Human Routing Rule**: When context variable **EscalateToAgent** is present and set to 1, we route to the queue that has only human users (agents) who can take over conversation.
1.  Navigate to Work Streams.

    ![[Table Description automatically generated](media/90ab5b0f2069e10ac4846949eb221dcc.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P61.png)

1.  Select and edit the **Live chat workstream** .

    ![[Graphical user interface, text, application, chat or text message Description automatically generated](media/afc73927f2b843baad2e47e046e23149.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P62.png)

1.  In the Live chat workstream record, select the Context Variables tab. Select + New.

    ![[Graphical user interface, text, application Description automatically generated](media/ea4e854aca2309c4d6d9885befc69b0c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P63.png)

1.  Create the new Context Variable with the following details:
    1.  **DisplayName:** EscalateToAgent
    2.  **Name:** EscalateToAgent
    3.  **Type:** Number

        ![[Graphical user interface, application Description automatically generated](media/32691edc56dc841ef9aac60430c001e8.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P64.png)

1.  Click Save and Close.
1.  You should now see the new Context Variable in the Live chat workstream.

    ![[Graphical user interface, text, application Description automatically generated](media/23f8d98a4d875d3c9c7240a0b6ee6cfc.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P65.png)

1.  Select the **Routing Rules** tab. Click **+ Add** to create a new routing rule.

    ![[Graphical user interface Description automatically generated](media/da3879889457a2bcf71077613f593572.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P66.png)

1.  Create the new Health Bot routing rule with the following details:
2.  **Name:** ToHealthcareBot
3.  **Queue**: Default messaging queue
4.  No Conditions.

    ![[Graphical user interface, text, application, email Description automatically generated](media/3084b93efbb53cf7a3ae43d4203f6e0a.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P67.png)

1.  Select **Save & Close.** On the Live chat workstream, click **+ Add** to add another new Routing Rule.

    ![[Graphical user interface, text, application, email Description automatically generated](media/6f13259ee245928e25446f58888237f8.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P68.png)

1.  Create the new Omnichannel Agent routing rule with the following details:
2.  **Name:** ToAgent
3.  **Queue:** EscalateToHuman
4.  Add Condition: Context Variable “EscalateToAgent = 1”

    ![[Graphical user interface Description automatically generated](media/b7e8939a21a7c69facab8ea33df0b2c0.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P69.png)

    ![[Graphical user interface, application Description automatically generated with medium confidence](media/f77be203dbddd126107dab5f03db2150.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P70.png)

1.  Select Save & Close.
1.  On the Live chat workstream, you should now see the two **Routing Rules** we created for **Bot** (ToHealthcareBot) and **Agent** (ToAgent).

    ![[Application Description automatically generated with medium confidence](media/274fa2c35fb1bc88254b0bbbac608f55.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P71.png)

**Congratulations!** You have created the proper context variable and routing rules that will allow customers to begin conversation with a health bot and escalate to a human agent.

**Task 5: Create Chat Widget for Health Bot**

1.  Navigate to **Chat**.

    ![[A picture containing graphical user interface Description automatically generated](media/8f6d4e945c13a7c3dbde4b3304d7735d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P72.png)

1.  Select **+New** Chat Widget.

    ![[A picture containing graphical user interface Description automatically generated](media/98d9e34bfd280bbc192a1fb61be1c639.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P73.png)

1.  Give the Chat Widget a **Name** (eg., Patient Portal Chat Widget).

    ![[Graphical user interface, application Description automatically generated](media/92615511958bb3fb70d8990149386c2b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P74.png)

1.  Click **Save**.

    ![[Graphical user interface, text, application Description automatically generated](media/7acbbe5239426e7217887a09a7419d3c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P75.png)

1.  After the record is saved, a **Widget Code Snippet** will be generated. Copy the code snippet and store it for later use.

    ![[Graphical user interface, application Description automatically generated](media/7cb80103a5d724ce25e77ebaffa39486.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P76.png)

**Congratulations!** In this exercise, you have successfully configured Customer Service Omnichannel Live chat by creating the necessary Users, Queues, Work Streams, Context Variables, Routing Rules, and Chat Widget. These all work together and allow patients to chat with a virtual health bot with the option to escalate up to a human agent if needed.

### Step 3: Embed Health Bot in Power Apps Portal

In this exercise, you will be embedding the **Omnichannel Chat Widget** into the Power Apps Customer self-service portal using Portal Management configuration. In your environment, we created a Lamna Healthcare Company Portal using the **Customer self-service portal** template before deploying Microsoft Cloud for Healthcare. Now we will configure the chat widget to show on the customer website.

Customer self-service portal: A customer self-service portal enables customers to access self-service knowledge, support resources, view the progress of their cases, and provide feedback.

Portal Management: Application to help you get started with the advanced portal configuration. In this walk-through, you will learn how to configure Chat widget in Portal Management app.

1.  In <http://make.powerapps.com>, open the **Portal Management** app.

    ![[Graphical user interface, text, application, email Description automatically generated](media/19a7a7226ebe85f3eb612fd238563bbe.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P77.png)

1.  Select **Content Snippets** in the left navigation pane

    ![[Table Description automatically generated with medium confidence](media/f861f24701cf02d528a172ffe0893635.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P78.png)

1.  In **Active Content Snippets**, type **Chat** in the **Search** box and press **enter**.

    ![[Graphical user interface, text, application, email Description automatically generated](media/cff8a7f9411b1163e8fb7c6fc8697868.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P79.png)

1.  You will see two **Chat Widget Code** records retrieved in the list. Click to open the Chat Widget Code record related to **Customer Self-service.**

    ![[Table Description automatically generated with low confidence](media/eec26f0c417e86410fcad217ff590587.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P80.png)

1.  In the **Chat Widget Code** record associated with Customer self-service, select **Value (HTML) > Html** Tab and then paste the Chat Widget Code snippet that you copied and stored in the previous task.

    ![[Graphical user interface, text, application, Teams Description automatically generated](media/2b2baee2c5bc49b17f41cb930fb8cba0.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P81.png)

1.  Click **Save & Close**.

    ![[Graphical user interface, text, application Description automatically generated](media/b80bd27b66c7be47651b1c0c7e403456.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P82.png)

1.  Now open the other **Chat Widget Code** associated with the **Healthcare Patient Portal** website.

    ![[A picture containing text Description automatically generated](media/ada590194178a7887fb2f26bdc5d0997.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P83.png)

1.  In the **Chat Widget Code** record associated with the Healthcare Patient Portal, paste in **Value (HTML)** the same Chat Widget Code snippet that you copied and stored previously and added to the customer self-service chat widget code. Replace any value that may have already populated the field.

    ![[Graphical user interface, text, application, email, Teams Description automatically generated](media/c4d7d635a96cba9ea7c687f825ffaef1.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P84.png)

1.  Select **Save and Close**.

Congratulations! In this exercise you have successfully updated the chat widget in the Power App Portal Content Snippets. With this configuration, the Health Bot will be visible on the Power Apps portal for both the customer self-service template and the healthcare patient portal template.

### Step 4: Extend Azure Health Bot with Custom Scenarios

**Dynamics 365 Omnichannel** integration allows the patient to interact with **Azure Health Bot** using the Dynamics 365 chat widget to access the medical knowledge and your custom scenarios. It also, allows the escalation of a bot conversation to a live agent to continue the interaction. When escalating a conversation, Dynamics passes along the conversation history and the context to the agent.

In this exercise, you will be doing the following:

-   Designing the below Health Bot Scenario called **MCH_PatientService**

    ![[Diagram Description automatically generated](media/aa3babb0c8c18ad33678a2160e4a1eda.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P92.png)

-   Design another Health Bot Scenario called **MCH_PatientServiceWelcome**. This scenario holds the starting statement which will allow the user to invoke the **MCH_PatientService** scenario.
-   Set the **Automatic Welcome Scenario** to be the MCH_PatientServiceWelcome custom scenario you create. This will begin the scenario when a user first interacts with the Health Bot.

**Task 1: Create MCH_PatientService Scenario**

In this task, you will create the **MCH_PatientService** bot scenario using the designer canvas.

1.  Navigate back to the Azure **Health Bot instance** homepage where you set the bot settings. This is the portal management link you copied from the Azure portal.

    ![[Text Description automatically generated](media/52f9eefb1d4ed9c2d11c32ce39d589e2.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P93.png)

1.  Click to expand the side navigation bar. Navigate to **Scenario > Manage**.

    ![[Graphical user interface, text, application Description automatically generated](media/54b43717341fa742eaaec826aeb1b6ee.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P94.png)

1.  Click **+ New** button on the top ribbon.

    ![[Graphical user interface, text Description automatically generated](media/a253ee03b82b4b8561a42dff2df19774.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P95.png)

1.  Provide the following details for the new health bot scenario:
    1.  **Name**: MCH_PatientService
    2.  **Scenario ID**: MCH_PatientService

        ![[Graphical user interface, text, application, email Description automatically generated](media/e0ed6333d9b8c65cc4dc48173addf264.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P96.png)

1.  Now let’s design the scenario conversation. It should navigate you directly to the designer. If not, select the MCH_PatientService scenario in **Scenarios > Manage** to edit.

    ![[A screenshot of a computer Description automatically generated](media/417c5fe2418f598d479045a83f5c4150.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P97.png)

**Step 1: Add Bot Introduction Statement**

1.  Add a beginning **Statement** to the scenario by selecting the icon and dragging Statement icon onto the editor.

    ![[A picture containing application Description automatically generated](media/b516d814db8461c6eb70cdf3ad149ce9.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P98.png)

1.  Enter the Display Text: **Hi there, I’m your Healthcare Assistant.**

1.  Select the **pencil** next to **Statement** in the top bar and change Title to **Intro**. Click **OK**.

    ![[Graphical user interface, text, application, email Description automatically generated](media/657c4b563cd91c6565437ab8e50067d0.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P99.png)

1.  Click **OK**. You will see the intro statement added to the designer canvas. Double click anytime to edit.

    ![[A picture containing graphical user interface Description automatically generated](media/1e92ce2c1feebfa7c619eccab58449e8.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P100.png)

**Step 2: Add Statement for Medication Request or Live Agent**

This section prompts two buttons Medication Refill and Live Agent. When user click any one of the buttons it will set the appropriate text to the variable MedicationOrAgent.

1.  Select **Prompt** icon and drag down onto canvas

    ![[A picture containing application Description automatically generated](media/b516d814db8461c6eb70cdf3ad149ce9.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P101.png)

1.  Enter the following details:
    1.  **Display Text**: Would you like to request a medication refill or chat with a live agent?
    2.  **Variable name**: MedicationOrAgent
    3.  **Data type**: string
    4.  Rename Title to **MedOrAgent**.

1.  Click **Cards** button.

    ![[Graphical user interface, text, application, email, Teams Description automatically generated](media/93b11208ed430ea0ad07198abdd1ca14.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P102.png)

1.  Select **Add Card**.

    ![[A picture containing chart Description automatically generated](media/281be669c17d3b241eca69feecd52f3f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P103.png)

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

        ![[Graphical user interface, application Description automatically generated](media/a44d164a6edc930f6c1658426ac63c95.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P104.png)

1.  Click **Ok** three times to get back to designer

    ![[Shape Description automatically generated with medium confidence](media/34f82d64754dd2e3d878ec8258ccc951.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P105.png)

    ![[Graphical user interface, text, application, email, Teams Description automatically generated](media/3b58f00a534b55890a493f97f6166b48.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P106.png)

1.  Connect **Intro** and **Appointment** boxes. Select the bottom circle on **Intro** and drag it to the top circle on the new prompt. An arrow will automatically appear when you try to connect Intro and MedOrAgent boxes using ellipse pointer.

    ![[Diagram Description automatically generated](media/b1cfb7c9f5fbb82fa6fae62b1f7175e5.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P107.png)

1.  Select **Save**.

    ![[A screenshot of a computer Description automatically generated with medium confidence](media/640c882facec6712afe2e94a9884987d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P108.png)

1.  Select **Run** to see the output in the WebChat on the right.

    ![[Diagram Description automatically generated](media/630a466e889e3ed9c2f83c4e97756eaf.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P109.png)

    ![[Graphical user interface, text, application, email Description automatically generated](media/efcba2d9805cba46e311eb53335e1854.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P110.png)

**Step 3: Add MedicationOrAgent Decision Branch**

This section checks whether the user has clicked Medication Refill or Live Agent with the help of the variable MedicationOrAgent. It will redirect the message accordingly.

1.  Add a **Branch** to the designer canvas.

    ![[Graphical user interface, application Description automatically generated](media/c7265982598d0257ce5f9d3f17ca96e7.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P111.png)

1.  Enter the following in the javascript Boolean expression: **scenario.MedicationOrAgent === "MedicationRefill"**

1.  Rename to **IsMedRefill.** Select **OK**.

    ![[Graphical user interface, text, application, email Description automatically generated](media/7a39b7c348f4cc0c8c1a5a53eafabceb.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P112.png)

1.  Select and drag the bottom circle of the **MedOrAgent** prompt to the top circle of the **IsMedRefill** branch decision to connect them.

    ![[Diagram Description automatically generated](media/b113af54b4c9c9c48da94edaa5068ec4.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P113.png)

**Step 4: Prompt User to Enter Data for Medication Refill Option**

1.  Add a **Prompt** element. This will be used to display the Form data (using Adaptive Card) to capture Patient name, email, and phone to create an appointment.

    ![[A picture containing application Description automatically generated](media/b516d814db8461c6eb70cdf3ad149ce9.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P114.png)

1.  Add the following details:
    1.  **Variable name**: formData
    2. **Variable Data Type**: Object
    3.  Change Title to **Submit**
    4.  Do not add any display text since the adaptive card will display instead

        ![[Graphical user interface, text, application, email, Teams Description automatically generated](media/1ad4bef6081c37eb67d2d0f93a97eebe.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P115.png)

1.  Click **Cards** button > **Add Card** > **Adaptive Card**.

1.  Refer to the lab resources file **AdaptiveCardForMedicationRefill.txt** and copy the json content and paste it in the json section of your card.

    ![[Graphical user interface, text, application Description automatically generated](media/404152ca20198d07c212414011a659eb.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P116.png)

1.  Select **OK** three times to get back to the designer.
  
1.  Connect the **Yes** condition of the **IsMedRefill** branch to the **Submit** prompt.

    ![[Diagram Description automatically generated](media/a5bb7a0418310b933aff30336c4063c1.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P117.png)

1.  Save and run your current scenario. If you don’t save the scenario first, it won’t run with updates since the last save. If you haven’t saved at all, it won’t recognize any conversation.

    ![[Graphical user interface Description automatically generated with medium confidence](media/1c8ffc95d5934d3955cfe53d3346265e.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P118.png)

1.  You should see the below output when running the conversation and selecting “Medication Refill” card when prompted to show the AdaptiveCard.

    ![[Graphical user interface, text, application, email Description automatically generated](media/fca92b19bfce499d598d7a55713c47ee.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P119.png)

**Step 5: Add Confirmation Statement**

1.  Add a **Statement** element.

    ![[A picture containing application Description automatically generated](media/b516d814db8461c6eb70cdf3ad149ce9.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P120.png)

1.  Add **Display text** as the following: **scenario.formData.myName + " - Thanks for providing the information, we have created a Medication Request for you regarding the following medication: " + scenario.formData.myMedReq**

1.  Rename the statement to **Confirmation**.

    ![[Graphical user interface, text, application, email Description automatically generated](media/c47dcb3d7a32364f35a2294bb7d671c9.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P121.png)

1.  Connect the **Submit** step to the **Confirmation** step in the designer canvas.

    ![[Diagram Description automatically generated](media/d1acfdfdd2e30d7c4c7f2f185fe6ef35.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P122.png)

1.  Select **Save** and **Run** to see your scenario in the webchat.

    ![[Graphical user interface, text, application, email Description automatically generated](media/5690a711f136db5f2ca17266ac7d9e45.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P123.png)

1.  Fill in information for the request and click **Submit** to see the confirmation text.

    ![[Graphical user interface, application, email Description automatically generated](media/786f6621fef13817f85e684137fab801.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P124.png)

**Step 6: Invoke Live Agent Action**

1.  Add a **Statement** element to the canvas.

    ![[A picture containing application Description automatically generated](media/b516d814db8461c6eb70cdf3ad149ce9.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P125.png)

1.  Enter **Display Text**: **Please wait, I am transferring your request to a live agent for further assistance.**
  
1.  Rename the statement to **Live Chat**.

    ![[Graphical user interface, text, application, email Description automatically generated](media/ee2a571508a2098b1c9bec202dc4eca2.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P126.png)

1.  Click **OK** to return to the designer page.
  
1.  Connect the **No** decision of the **IsMedRefill** branch to the **Live Chat** statement.

    ![[Diagram Description automatically generated](media/889f727bb25d21b0c1673b7186cf851b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P127.png)

**Step 7: Add Action to Invoke Escalation**

1.  Add an **Action** element to the canvas, used to trigger an escalation to Omnichannel Live Agent

    ![[](media/df4a09908aab05c4afd2452b91e3421e.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P128.png)

1.  Add the following code in the action, which will trigger the Live agent chat:

    session.sendChannelData('Escalating...', {

    "tags": JSON.stringify({type: "Escalate", context: {"EscalateToAgent": 1}})

    });

2.  Name the action **Escalate**. Click **OK** to return to the designer page.

    ![[Graphical user interface, text, application, email Description automatically generated](media/17adbd0c4d01461d3b903d3646b533f5.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P129.png)

1.  Connect the **Live Chat** to the new **EscalateToAgent** action. You completed the final connection!

    ![[Diagram Description automatically generated](media/902c24320f1946f91119a0bfc17405cb.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P130.png)

1.  Save and run your scenario to see the full scenario output.

1.  Test all logical paths. Selecting Live Agent in the authored card should show the escalation action.

    ![[Graphical user interface, application Description automatically generated](media/8488f1dd21de5b0c2c5f57e47d099b35.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P131.png)

1.  Exit the **MCH_PatientSerivce** scenario editor.

    ![[Graphical user interface, application, Word Description automatically generated](media/b8c32a8fa1d1e6352b3f1107dfe233e8.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P132.png)

**Task 2: Create MCH_PatientServiceWelcome Scenario**

In this task, you will create another bot scenario called **MCH_PatientServiceWelcome** to invoke the **MCH_PatientService** scenario.

1.  On the Azure Health Bot scenarios page, select **+New** to create another new scenario

    ![[Graphical user interface, text, application Description automatically generated](media/c6b04a9da53ad529f22ef4d556d45127.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P133.png)

1.  Provide the following details for the new scenario and click **Create**:
    1.  **Name**: MCH_PatientServiceWelcome
    1.  **Scenario ID**: MCH_PatientServiceWelcome

        ![[Graphical user interface, text, application, email Description automatically generated](media/1b11ff53df84e918ea553680a7af058d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P134.png)

1.  On the scenario editor designer, add a **Statement** element.

    ![[A picture containing application Description automatically generated](media/b516d814db8461c6eb70cdf3ad149ce9.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P135.png)

1.  Rename the statement **Welcome**. Do not add any Display text as we will show it in the card instead.

    ![[Graphical user interface, text, application, email, Teams Description automatically generated](media/74531c6974cde48e51ba6c35e56c591e.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P136.png)

1.  Select **Cards.**

    ![[Graphical user interface, application Description automatically generated](media/47643908c0f6bc1989a8daf5e2ca2c7b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P137.png)

1.  Select **Add Card**.

    ![[A picture containing graphical user interface Description automatically generated](media/ac86d871f38494a993d9a9bd5f9f1f83.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P138.png)

1.  Choose **HeroCard.** Add **Title**: **Welcome to Lamna Healthcare Patient Service Portal**

    ![[Graphical user interface, text, application, email Description automatically generated](media/e741b113d254e8d41ee2f7a2bf958cd1.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P139.png)

1.  Select **Add Action** and provide the following details:
    1.  **Action type**: imBack
    1.  **Action value**: "begin MCH_PatientService"
    1.  **Action title**: "Lamna Healthcare Support"

    ![[Graphical user interface, text, application, email Description automatically generated](media/a0d7274c808aad868044608d858c64c4.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P140.png)

1.  Click **OK** and view your completed scenario. This will be used to kick off the conversation and allow the other MCH_PatientService scenario to be invoked through the authored card.

    ![[Table Description automatically generated with low confidence](media/8e359f4b4786269de20defefc053c6f0.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P141.png)

1.  Save and run to test your bot scenario **MCH_PatientServiceWelcome** scenario in the Web Chat.

    ![[Text Description automatically generated with medium confidence](media/a6d6888f3b8e614b1e6898637ae4e48d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P142.png)

1.  Exit the scenario designer.

**Task 3: Configure Welcome Scenario as Automatic**

In this task, we will set the MCH\_ PatientServiceWelcome to be the “Automatic Welcome Scenario” in settings. This will always trigger the welcome scenario when a user starts a conversion with the **Azure** **Health Bot**.

1.  Navigate to **Configuration > Conversation**

    ![[Graphical user interface, application Description automatically generated](media/71293e93eb1c9b1f83bc4a25e82d6dbe.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P143.png)

1.  In the **Interactions** tab, scroll down to the **Automatic Welcome** section.

    ![[Graphical user interface, text, application, email Description automatically generated](media/fe96dc9aa5d19f2d14139f7459c37c73.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P144.png)

1.  In the **Automatic welcome** scenario dropdown, select the **MCH_PatientServiceWelcomeScenario**.

    ![[Graphical user interface, application Description automatically generated](media/749d66eeb5e6727e2003be406ac57fc1.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P145.png)

**Task 4: Test Health Bot Escalation from Power Apps Portal to Dynamics 365 Omnichannel**

1.  Navigate to **Power Apps** and click to open **Lamna Healthcare Patient Portal**.

    ![[Opem Lamna Healthcare Portal](media/4ab86dc05d1b52e1fbfbe9ed18ccd3af.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P146.png)

1.  You should see the Health Bot “Let’s Chat” button in the lower right-hand corner of the screen. This means the chat widget was successfully embedded into the Customer Self-service portal.

    ![[Graphical user interface, website Description automatically generated](media/6683bae327bf4773ae70d6ab3a6d035a.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P147.png)

1.  When you the click chat widget, bot will trigger a welcome scenario message we created and set as the default welcome message **(MCH_PatientServiceWelcome)**.

    ![[Graphical user interface, text, application Description automatically generated](media/b8eb18cb6b252e2a24987cbf10c0ce05.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P148.png)

1.  Navigate back to **Power Apps** and open **Customer Service Workspace.**

    ![[Graphical user interface, text, application, email Description automatically generated](media/b09bde1f0830a5c103062359f145ef38.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P149.png)

    **Note**: Omnichannel for Customer Chat Widget will work only when you see the presence status is enabled. There should be a splash loading screen that goes through multiple steps and then displays the status indicator as available once loaded. (Status is enabled when green with checkmark in circle**)**

    ![[Check presence status](media/11c92a2a155e998af758dd1eb2765cc6.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P150.png)

    Splash screen:

    ![[Graphical user interface, text, application, email Description automatically generated](media/e58927b04a1dd6043c593bd66f9b1102.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P151.png)

1.  In the **Health Bot in Lamna Healthcare Patient Portal**, click **Lamna Healthcare Support** button, then the **Live Agent** button to witness the escalation into Omnichannel to chat with a live agent (your user!)

    ![[Graphical user interface, application Description automatically generated](media/6a5907104682e1c1adfa1bad184b157f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P152.png) ![[Graphical user interface, text, application, chat or text message Description automatically generated](media/a2737e43893fda1bddebcba898810df3.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P153.png)

1.  Navigating back to **Omnichannel for Customer Service**, your user as the Live Agent should receive an incoming notification with Accept/Reject options for that chat.

3.  Click **Accept** to connect and chat with customer (In this case chat with the **patient**).

    ![[live agent notification on Customer Service](media/5a7e0e433a3cdc34a690e4a34d21698e.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P154.png)

1.  As soon as Live Chat Agent accepts the incoming chat notification, Omnichannel for Customer Service has opened a **Live Chat Widget** and Agent would be able to see the entire bot conversation with user and continue the chat conversation with user for further assistance.

    ![[live agent notification on Customer Service](media/6acb2789860498db29fd59afed37b410.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab02/L2P155.png)

**Congratulations!** You have successfully extended the Azure Health Bot with custom scenarios and tested the end-to-end escalation scenario from a patient using the Azure Health Bot in Power Apps Portals to chatting with a Live Agent in Omnichannel for Customer Service.
