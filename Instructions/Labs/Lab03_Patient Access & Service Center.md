# Module 4 Lesson 1- Lab 3: Patient Access & Service Center

### Overview

Microsoft Cloud for Healthcare includes Patient Access and Patient Service Center.

You can provide patients with access to their health data, in-person and virtual appointment scheduling, and information through knowledge articles. Patient Access provides a portal that will help you give patients the ability to chat with a health bot, communicate with a caregiver, and view their clinical data.

Patient Access includes the following capabilities that you can provide to your patients:

-   **Access** - Patients have a user-friendly portal to access their health information.
-   **Direct engagement** - Patients can engage through automated chat conversations that will hand off to your patient service center.
-   **Scheduling and messaging** - Patients can schedule appointments and send messages to their providers.

In the Patient Service Center, you can engage with your patients in the way that they want while monitoring automatic conversations through the Microsoft Azure Health Bot service. Additionally, service agents can help your patients with information and setting up appointments.

The Patient Service Center includes the following capabilities:

-   **Monitor patient conversations** - An ongoing conversations dashboard provides information on the conversations that are handled by the agents and integrated bots.
-   **Agent scripts** - Use provider-specific agent scripts to address patient issues.
-   **Monitor effectiveness** - Conversation intelligence provides insights for service center managers on agent performance.
-   **Follow-up** - Send follow-up surveys on patient satisfaction, reminders on appointments, and more.
-   **Appointment scheduling** - Schedule or reschedule appointments during conversations with patients.

The Patient Access Portal and Patient Service Center modules focus on the **Enhance Patient Engagement** priority scenario by communicating effectively with patients with the prebuilt guidance and automated systems.

![[Graphical user interface Description automatically generated](media/df4dee19dba74e977d1d001c9dbd3a3d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P1.png)

The lab for this module will focus on the healthcare story of Casey Jensen.

![[Timeline Description automatically generated](media/d5a64c7764ba9f24286ff331aaad8bd4.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P2.png)

Casey is an avid runner but has exercise-induced asthma and requires an albuterol inhaler to help her breathe while running. Casey has realized that her current albuterol inhaler is low on medication and decides that it's a good time to get a refill.

In this lab, you'll first play the role of a Lamna Healthcare system administrator, where you'll set up the Patient Access portal and various tools in the Patient Service Center application. Next, you'll play the role of Casey, who will sign in to the portal, navigate the various options, interact with the Azure Health Bot, and escalate to a live agent in Patient Service Center to refill the medication.

### Learning objectives

In this lab, you will:

-   Configure and navigate the Patient Access Portal
-   Create and configure Agent Scripts to show in the Productivity Pane
-   Create and configure Knowledge Articles
-   Experience escalation scenario from Patient Portal through Azure Health Bot into Patient Service Center

### Step 1: Configure & Navigate the Patient Access Portal

In this exercise, you will learn how to do the following:

1.  Configure an external website to the Healthcare Patient Portal template
2.  Create a registration code and invite a patient to create an account for the website
3.  Log in as a patient to navigate the features of the healthcare website

The **Healthcare Patient Portal** is a template installed in your environment by the Patient Access module in Microsoft Cloud Solution Center when Microsoft Cloud for Healthcare was deployed.

A **Portal** is an external website that allows for communication between a company and its users. In this case, the Lamna Healthcare Company wants an external website for their patients to access their medical history and communicate effectively with the institution. The Healthcare Patient Portal template tailors the website’s user interface for a healthcare company focusing on secure communication, information access, and an overall improved patient experience.

Here’s what you should see after configuring and logging into the Healthcare Patient Portal:

![[Screenshot of Healthcare Patient Portal landing page](media/a4aac2020f8208d5c4ce226518242a48.jpeg)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P3.png)

If you’d like to learn more about portals, check out Microsoft Docs: [What is Power Apps portals?](https://docs.microsoft.com/en-us/powerapps/maker/portals/overview)

**Task 1: Configure the Healthcare Patient Portal**

Prior to deploying Microsoft Cloud for Healthcare, we created a portal in your environment using the **Customer Self-Service** template. This was a prerequisite to install the Healthcare Patient Portal as part of the Patient Access module.

Lamna Healthcare wants to associate the previously installed Customer Self-Service portal with the **Healthcare Patient Portal** template, so the correct website is displayed to the user. The following steps will guide you through how to bind your website to the proper template and restart the portal for changes to apply.

We will first open the Portal to show the Customer Self-Service template currently bound. After the configuration steps in this task, you will see the new Healthcare Patient Portal user interface.

1.  Navigate to <https://make.powerapps.com> in an In-Private or Incognito window.
1.  Select the correct environment from the upper right **Environment** drop down.

    ![[](media/118bf5867e47b80161dc93e75a5cef91.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P4.png)

1.  Select **Apps** on the left navigation bar.

    ![[Graphical user interface, application Description automatically generated](media/7ab15895d0ee4a9b65aa90fe7b2bb640.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P5.png)

1.  Find the **Lamna Healthcare** **Patient Portal** app. It should be the only app where the app type is Portal. You may also search for it in the Search bar in the upper right.

    ![[Screenshot of Lamna Healthcare Patient Portal in App list](media/d9c9fdf86983ff0ad75b9781e2d0399c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P6.png)

1.  Click the app name to open the **Lamna Healthcare Patient Portal**. You may also select **More Commands (…) > Browse** or click **Browse** on the top command bar to open it.

    ![[Screenshot of selecting Lamna Healthcare Patient Portal](media/a00d6bf269495a44ecccd0bb4011c764.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P7.png)

1.  You should see the Customer Self-Service template shown in the Lamna Healthcare Patient Portal.

    ![[Screenshot of customer self-service portal landing page](media/5c21b675adf113661526ce9d7322fb7d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P8.png)

1.  Close the Lamna Healthcare Patient Portal website. Now you will configure it to the Healthcare Patient Portal template.

1.  Return to Apps section in Power Apps. Select the **Lamna Healthcare Patient Portal** app if it isn’t already selected.

    ![[Screenshot of Lamna Healthcare Patient Portal in App list](media/d9c9fdf86983ff0ad75b9781e2d0399c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P9.png)

1.  Select **More Commands (…) > Settings**.

    ![[Screenshot of selecting Lamna Healthcare Patient Portal](media/bab62afdddd0a7f8d4294463f4e58f85.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P10.png)

1.  This will bring out the **Portal settings** panel on the right.

    ![[Graphical user interface, application Description automatically generated](media/6fe6f74488d5c91b22712f44941e658d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P11.png)

1.  In **Portal settings**, under **Advanced options**, select **Administration**.

    ![[Screenshot of portal settings dialog](media/491eec7fa5d805cb64a60fd61dc4b32f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P12.png)

1.  Selecting Administration will open a new window, the **Power Apps Portals admin center**, where you can do portal administrative tasks. You should be first navigated to the **Portal Details** tab of the Power Apps Portals admin center.

    ![[Graphical user interface, application Description automatically generated](media/1dfcb065aeca17a47e7e1b4c0b5f08f8.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P13.png)

1.  Scroll down to **Update Portal Binding > Select Website Record**.

    ![[Screenshot of current portal binding as customer self-service](media/ca0ab3497406e60443d5f6e422aeffbd.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P14.png)

1.  Open the **Select Website Record** drop down and change the value from Customer Self-Service to **Healthcare Patient Portal.** This will bind the Healthcare Patient Portal template with this portal URL and show the proper user interface to the user for our healthcare scenario.

    ![[Screenshot of selecting Healthcare Patient Portal in drop down](media/98ec46b914bc968d646627bf7cb5a5fd.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P15.png)

1.  Select **Update**.

    ![[Screenshot of updating portal binding](media/ceebde8bfffa247f33bb8d6cb4a83083.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P16.png)

1.  Select **Portal Actions** section on the left navigation. Then click the first option, **Restart.**

    ![[Screenshot of selecting Portals Admin Center, select Portal Actions, and Restart](media/6632dccb2295a51ee6da61feb1b553d6.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P17.png)

1.  When prompted, confirm the **Restart** for the portal. This will allow the change to take effect.

    ![[Screenshot of restart confirmation dialog](media/ebfccbea2a3e3a0b524dbb248adc124d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P18.png)

1.  Wait 1-5 minutes for the portal to restart. (Feel free to refill water or stretch your legs!)

1.  After a few minutes, open the **Lamna Healthcare Patient Portal** in Power Apps.

    ![[Screenshot of Lamna Healthcare Patient Portal in App list](media/d9c9fdf86983ff0ad75b9781e2d0399c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P19.png)

1.  If you see **HTTP Error 503: The service is unavailable,** the portal is still restarting.

    ![[Screenshot of Server Unavailable, error 503 ](media/21097c788c60e469bf2af43f909bf8e0.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P20.png)

1.  Once the Portal is opened and running properly, it should look like the following:

    ![[Screenshot of Patient Access Portal sign in page with the Healthcare Patient Portal template configured.](media/b20128a1bc4c2800499865d3159af9ce.jpeg)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P21.png)

**Congratulations!** You completed the post deployment steps to configure the Healthcare Patient Portal template deployed from Patient Access. After updating the bindings and restarting the portal, the website now shows as Healthcare Patient Portal template rather than Customer Self-Service.

**Task 2: Modify Company Name in Patient Portal**

In this task, we will edit the Patient Portal website to align the name with Lamna Healthcare Company since the template uses a generic company name.

1.  Navigate to **Apps** in <https://make.powerapps.com>.
1.  Select the **Healthcare Patient Portal** app and click **More Commands (…) > Edit**.

    ![[Graphical user interface, application Description automatically generated](media/b80aced98cd2d73b58c646537cc26dac.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P22.png)

1.  The Patient Portal designer will load after getting thing ready.

    ![[Graphical user interface, application Description automatically generated](media/acf541e7ed85ad1ae051d4adc1501fe4.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P23.png)

1.  Once loaded, you should see **Contoso Healthcare** in the upper left of the design screen. The name may be overlapping the logo but will display properly on the website.

    ![[Graphical user interface, table Description automatically generated](media/1aa54af4205ceccbc609d0c27ea24854.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P24.png)

1.  Click the text box that reads **Contoso Healthcare** and change it to **Lamna Healthcare**.

    ![[A picture containing table Description automatically generated](media/7056dc139049101a98f96a8faa2346ee.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P25.png)

1.  The page should automatically save the changes. You can verify in the command bar that it says **Saved**, has the green check mark, and on hover shows the correct saved time.

    ![[A picture containing background pattern Description automatically generated](media/d758717616fdf61843f047075274fba4.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P26.png)

1.  Select **Sync Configurations** in the command bar to sync data to CDS.

    ![[Graphical user interface, application Description automatically generated](media/d358036b7b72daa60269c26dfb117f55.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P27.png)

1.  It may take a moment to load the preview.

    ![[Graphical user interface Description automatically generated](media/856c9b494ef46aefade5841ca92399b1.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P28.png)

1.  Once configurations are completed syncing, select **Browse website** on the command bar.

    ![[](media/a470a73c9f4cc83c7889783d7aa9852a.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P29.png)

1.  The Healthcare Patient Portal should open, and you should see the **Lamna Healthcare** company name in the upper left corner.

    ![[A person holding a baby Description automatically generated with low confidence](media/3572173d1baad1996d694beb62f6c8d4.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P30.png)

**Congratulations!** You completed modifying the Healthcare Patient Portal to display the correct company name.

**Task 3: Invite a Patient to the Portal**

Now that the Patient Portal is ready to go, we need to allow Lamna Healthcare patients to create accounts.

In this task, you will learn how to **create an invitation code** for patients to sign up and use the Lamna Healthcare Patient Portal. Since **Casey Jensen** will be accessing the patient portal to fill her medication in this lab, we will create an account for her.

1.  Open the **Healthcare Administration** app in [Power Apps](http://make.powerapps.com).

    ![[Screenshot of Apps screen with Healthcare Administration App](media/546ab9d2b2e4d2a6f5b8192a7d00eb18.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P31.png)

1.  In the **Administration** section of the sitemap, select **People,** if not already selected. You will see the **Active Patients** grid view. Open the **Casey Jensen** patient record so we can obtain an invitation code for her to use.

    ![[Graphical user interface, application Description automatically generated](media/eb2ddad1307dfd171cdfe13436fbe1ad.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P32.png)

1.  On Casey Jensen patient record, select **Create Invitation** from the top command bar. It should be near the right side.

    ![[Graphical user interface, text, application Description automatically generated](media/bdec1fee98911c5ddb646aeeeeed1ad8.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P33.png)

1.  You may have to expand additional options to see this command in the drop down.

    ![[Screenshot of Create Invitation command after expanding more options](media/a51267c180b172cd4b60ae3ebf393afc.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P34.png)

1.  A New Invitation form will appear. You don’t need to make any changes. Click **Save.** Once saved, an invitation code will be created for the patient. Let’s go retrieve it.

    ![[Graphical user interface, application Description automatically generated](media/3c9bf2c5682525105562acec474e93cb.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P35.png)

1.  Go to the **Advanced** tab on the Invitation record. Copy and store the **Invitation Code** for accessing the Patient Portal in the next task.

    ![[Graphical user interface, text, application, email Description automatically generated](media/34524f1a4b0e995152d4920b42f19bad.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P36.png)

**Congratulations!**  You have successfully created an invitation code for **Casey** to register an account in the Patient Portal.

**Task 4: Redeem Invitation Code and Sign into Patient Portal**

In this task, you will **transition personas** and act as **Casey Jensen**, who just received an invitation code to Lamna Healthcare’s Patient Portal and is excited to register and navigate its features.

1.  Open the Lamna Healthcare Patient Portal in [Power Apps](https://make.powerapps.com/).

    ![[Screenshot of Lamna Healthcare Patient Portal in App list](media/d9c9fdf86983ff0ad75b9781e2d0399c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P37.png)

1.  In the first task, we configured the portal to the Healthcare Patient Portal template. Now that it’s been restarted, your Patient Portal should open and look like the following:

    ![[Screenshot of Healthcare Patient Portal Sign in Landing Page](media/8b600d15eb5bafdcb7a735457814c725.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P38.png)

1.  If you still see the Customer Self-Service template, make sure you’ve completed Exercise 1, Task 1 to change the template to the Healthcare Patient Portal.

1.  In the Patient Portal, select **Sign in**.

    ![[Screenshot of Sign in prompt](media/a3e05c50406a1d8acc6a3b0c8dde49a6.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P39.png)

1.  After the sign in page loads, select the **Redeem invitation** tab.

    ![[Graphical user interface, text, application Description automatically generated](media/4f705ca9a55d46441a14a5d21f2d9b4c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P40.png)

1.  Paste the **Invitation code** you stored for Casey Jensen. Click **Register.**

    ![[Graphical user interface, text, application, email Description automatically generated](media/98ea55cae8145080378d854c4b47fda7.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P41.png)

1.  Register a new local account for Casey Jensen with the following recommended details:
    1.  **Email**: Casey.Jensen@contoso.com (should auto-fill)
    2.  **Username**: CaseyJensen
    3.  **Password**: Make up your own. Please note the password to use for sign in later.

        ![[Graphical user interface, text, application, email Description automatically generated](media/46b12ab28790cc7676100e227610ec40.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P42.png)

1.  Click **Register**. After selecting Register, you should be signed into the Patient Portal.

**Congratulations!** You have successfully redeemed an invitation to register an account for Casey and signed in.

**Task 5: Navigate the Patient Access Portal**

In this task, you will continue as **Casey** and navigate the features of the Patient Portal.

1.  After registering for an account in the **Patient Access Portal**, you should be welcomed by the portal Homepage or profile page if your account requires action, such as email confirmation required. You can ignore the email confirmation warning if displayed.

    ![[Graphical user interface, application Description automatically generated](media/e2519952290c4b7808b08d7d65e6d880.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P43.png)

1.  Select **Lamna Healthcare** in the upper left to go back to the Homepage.

    ![[Graphical user interface, application Description automatically generated](media/3fa87ce9f874614b804657d0bc26cd18.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P44.png)

1.  You will be navigated to the Patient Portal **Homepage**.

    ![[Graphical user interface, application Description automatically generated](media/edd13cbeb614c2da3be6399108a4ae41.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P45.png)

1.  In the center of the homepage, you will see **shortcuts** to schedule an appointment, view messages, or find a doctor.

    ![[Screenshot of homepage shortcuts](media/638bef51cae429fb425812ff81fedd14.jpeg)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P46.png)

1.  Below the shortcuts, you will see **current patient information** including unread messages, upcoming appointments, and current medications.

    ![[Graphical user interface, text, application, email Description automatically generated](media/2651c1fa4b133250b3cdb592a5e1bb79.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P47.png)

1.  In the left navigation bar, you will see all available options for navigation in the Patient Portal. Click through the options to see what’s available and each associated screen.

    ![[Graphical user interface, application Description automatically generated](media/44e0855db215207e1d806f362657bc84.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P48.png)

1.  **Home** command will direct you to the homepage.

1.  **Find a doctor** shows a list of practitioners with associated information.

    ![[Table Description automatically generated](media/b46da4073d8ae30b098c88d9e68e2802.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P49.png)

1.  **Messages** allows a secure method to send and receive messages to healthcare professionals. Expand Messages on the navigation bar to see both the **Inbox** and **Sent** messages.

    ![[Graphical user interface, text, application Description automatically generated](media/0b3dfec5cfd26a0fb2ffae1b133b8e24.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P50.png)

1.  Expand **Appointments** to check upcoming and schedule new appointments. Scheduling new appointments allows for clinic or virtual appointments, which also includes instant virtual appointments. The Virtual Visit Lab will go through the process of booking an instant virtual appointment.

    ![[Graphical user interface, text, application Description automatically generated](media/45a0c94134f93577215b5b10a874ae9b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P51.png)

1.  Check **Medical records** including medications, allergies, conditions, visit summaries, care plans, and care team. You can see a full overview and filter by date and type.

    ![[Graphical user interface, text, email Description automatically generated](media/9cc4b68f58784f0ac3581541e567be66.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P52.png)

1.  Lastly, there is Personal information, including emergency contacts and insurance coverages.

    ![[Text Description automatically generated](media/070d2df534c62b19930c545db8e76d7f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P53.png)

    ![[Graphical user interface, text, application Description automatically generated](media/6b0d8912dfc0e6ea0023b31de824035e.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P54.png)

1.  The Azure Health Bot icon shows at the lower right-hand corner of the screen. You may start a conversation by clicking **Let’s Chat** button to open the virtual assistant.

    ![[Screenshot of Let's Chat virtual assistant Health Bot](media/d57b9e593f492102cdd20dbbd438d7e6.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P55.png)

1.  In the final exercise, we will have a full conversation with the bot, but for now we will close and continue.

    ![[Screenshot of closing the Health Bot conversation](media/12f977916359020d423e6738565c1c1c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P56.png)

1.  You may access the patient Profile page at any time by selecting the patient’s name in the upper right drop-down and selecting **Profile**.

    ![[Graphical user interface, text, application Description automatically generated](media/5123b861b30e199a8b0165933892c1d2.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P57.png)

1.  Here you can customize the patient profile as needed. For now, we will keep it the same.

    ![[Graphical user interface, application Description automatically generated](media/2e9e895883dbdda3057021b22952966b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P58.png)

1.  You may log out of the Patient Portal by selecting the patient’s name in the upper right drop-down and selecting **Sign Out**.

    ![[Graphical user interface, text, application Description automatically generated](media/ee216091aca8d2d1a1fb53cbb74ad1da.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P59.png)

1.  You should be redirected back to the sign in page.

    ![[A person holding a baby Description automatically generated with low confidence](media/d591821c155ce37b42cad19bf4937d6d.jpeg)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P60.png)

**Congratulations!** You have navigated the Patient Portal to see what information and communication is available to the Patient. In this exercise, you learned how to configure the Patient Access Portal to display as the Healthcare Patient Portal, modify the portal to display the company name, invite patients to register to the website, and navigate the website features.

### Step 2: Configure Agent Scripts

Lamna Healthcare Company wants to ensure they have proper tools in place to provide the best service and guidance during patient interactions.

Patient Service Center has a **productivity pane** which is an auxiliary work area which contains tools that support or expedite an agent's tasks when engaging with patients. During a patient engagement, it will be embedded directly on the screen next to patient information and can be collapsed or expanded as needed.

See the following documentation to learn more about the productivity pane: [Productivity pane overview](https://docs.microsoft.com/en-us/dynamics365/omnichannel/administrator/productivity-pane)

**Agent Scripts** are one of the tools in the productivity pane that agents can use to help with patient care. Agent Scripts provide guidance for a specific situation and help organizations be unified, accurate, and effective while also being faster and more efficient with patients. The scripts ensure that only accurate, company-endorsed information is being shared and help reduce error and improve customer satisfaction.

In this exercise, you will create an agent script to appear in the productivity pane in Patient Service Center. The following screen shows the productivity pane on the right-hand side with the Agent Scripts tab showing. The agent script selected is Validate Patient Information and there are two steps shown. You will not see this below output until the final exercise in this lab while testing escalation, however, you will be creating the components needed to display in the productivity pane later.

![[Graphical user interface, application Description automatically generated](media/e9e70b76c91efe963f17e1245dbcc88f.JPG)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P61.png)

**Task 1: Assign Productivity Tools Administrator Role**

In this task, you will assign the necessary roles to your user to create and use agent scripts. Specifically, you will be adding the **Productivity tools administrator** and **Productivity tools user** roles. The Productivity tools administrator can do any action (create/read/write/append/delete) on the agent script, while the Productivity tools user only has read capabilities. Since we are creating them, we need the administrator role.

See the following documentation to learn more about these roles: [Assign roles and enable users for Omnichannel for Customer Service](https://docs.microsoft.com/en-us/dynamics365/omnichannel/administrator/add-users-assign-roles#understand-roles-and-their-privileges)

1.  Using an In-Private or Incognito window, navigate to [Power Apps](http://make.powerapps.com).
1.  Select the correct environment from the upper right **Environment** drop down.

    ![[](media/396337261137b8319d9cae85d9cefbba.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P62.png)

1.  Select **Apps** on the left navigation bar.

    ![[Graphical user interface, application Description automatically generated](media/7ab15895d0ee4a9b65aa90fe7b2bb640.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P63.png)

1.  Open the **Omnichannel admin center** app.

    ![[Screenshot of Omnichannel Administrator App in Power Apps](media/1f903d0ba4d66a015c432c0ba5e4f797.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P64.png)

1.  Select the **gauge** icon in the upper right corner and navigate to **Advanced Settings**.

    ![[Screenshot of Advanced settings in Settings drop down](media/8f673538d6f6c594ae83a217d121200c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P65.png)

1.  A new window should open and navigate to Dynamics 365. It may take a while to load. If it’s been longer than a minute, stop and reload the page. It should then load faster.

1.  In Dynamics 365, select **Settings > Security**.

    ![[Screenshot of Dynamics 365 navigation to settings and security on command bar](media/8df791e0613a679d2667dfda6ad39d00.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P66.png)

1.  Under **Security**, select **Users**.

    ![[Screenshot of Users option first in the list of security settings](media/d56e54332566174314f7f98e4b2868da.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P67.png)

1.  Switch the view drop down from Omnichannel Users to **Enabled Users** for the grid view so that your user will show in the list.

    ![[Screenshot of Switching view in drop down to from Omnichannel Users to Enabled Users](media/4bb54de365815f3f95a48ceb32e4184b.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P68.png)

1.  While in the **Enabled User** list, scroll down to **find your user** or use the **Search** bar.

    ![[Screenshot of searching for user in enabled user list](media/07f63477e1de63e1e662c2e29930b06f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P69.png)

1.  Select your user for the training and select **Manage Roles** on the top command bar.

    ![[Screenshot of Selecting current IAD User in list and clicking Manage Roles button on command bar](media/2fea347790e3a9500986ebef69801b9f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P70.png)

1.  Scroll down and select the following two roles to your user and select **OK**.
    1.  Productivity tools administrator
    2.  Productivity tools user

        ![[Screenshot of Manage User Roles dialog where 2 roles have been selected: Productivity tools administrator and Productivity tools user](media/4bdee9a7ed4c8c640a681b207b202e82.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/Lab03/L3P71.png)

        Note: You will assign more roles in this lab. It is recommended to leave the User screen open.

**Congratulations!** You have successfully assigned the necessary **Productivity tools** user roles to set up and use agent scripts.

**Task 2: Create an Agent Script**

In this task, you will create an agent script in the Omnichannel admin center app. This script will guide the agent to **validate patient information** when a conversation is initiated between a patient and an agent in Patient Service Center. The script will have two steps, one to **confirm phone information** and another to **verify insurance information**. This task will guide you through creation of this agent script and its steps.

1.  Navigate to **Omnichannel admin center** application which you opened in the first task.
1.  In the left navigation bar, under **Agent Experience**, select **Agent Scripts.**
2.  
3.  On the Active Agent scripts page, select +New.

    ![Omnichannel Administration app to create new agent scripts](media/089b479205b27b682872f9f693bcf427.png)

1.  For the **New Agent script** record, specify the following:
    1.  **Name:** Validate Patient Information
    2.  **Unique Name**: msdyn_ValidatePatientInformation

        ![Create new agent script called Validate Patient Information](media/424e9ffba8a8729ed5f6ef7fef5f697e.png)

1.  Click **Save**. The **Agent script** steps should appear on the right

    ![Graphical user interface, text, application Description automatically generated](media/baf7c183a9b679cfbd9324f68b4b0364.png)

1.  In the Agent script steps section, select +New Agent script step.

    ![Add Agent script step to the new agent script](media/69e50ed3d916abd30dd1e169169ce18a.png)

1.  **Quick Create** form for the **Agent script step** appears. Specify the following fields:
    1.  **Name:** Confirm Phone Number
    2.  **Unique Name**: msdyn_ConfirmPhone
    3.  Order: 1
    4.  Action type: Text
    5.  **Text instructions**: Ask patient to confirm phone number.

        ![Screenshot of Quick create form for a step to Confirm Phone Number for the patient](media/bd79321f1edbc3acefc77ee02c45e273.png)

1.  Click **Save and Close**. Now let’s add another step.
2.  
3.  In the Agent script steps section, select +New Agent script step again.

    ![Screenshot of New Agent script step button in agent script steps subgrid ](media/9b9b4c3927e3928c2165b592427ca1b4.png)

1.  Another **Quick Create** form for the **Agent script step** appears. Specify the following fields:
2.  **Name:** Verify Insurance Information
3.  **Unique Name**: msdyn_VerifyInsuranceInformation
4.  Order: 2
5.  Action type: Text
6.  **Text instructions**: Ask Patient for Insurance Provider and ID \#. Verify their response matches insurance information on file.

![Screenshot of Quick create form for a step to Verify Insurance Information for the patient](media/7b82621394d3b31e2a4050e6bcef29d3.png)

1.  Select **Save and Close**. Both steps should now be in the **Agent script steps** table.

    ![Graphical user interface, text, application, email Description automatically generated](media/9ae9c32c1ceeb9d84c620c7b7f39e1ee.png)

1.  The agent script is now complete. Select **Save & Close**.

    ![Screenshot of the completed "Validate Patient Information" Agent script](media/a40d9b391cd9cd61c4fc141bfa45145d.png)

**Congratulations!** You have completed creating an agent script with two steps to validate patient information, including phone number and insurance information.

**Task 3: Associate the Agent Script with a Session Template**

In this task, you will associate the agent script with a session template so it will load for agents based on the type of session they’ve opened. We will be associating the agent script we just created with the **Default chat session.** This is the default chat session that opens during an escalation to an agent in Patient Service Center.

1.  Open the **Omnichannel admin center** app in Power Apps if you aren’t already in it.

    ![Screenshot of Omnichannel Administrator App in Power Apps](media/1f903d0ba4d66a015c432c0ba5e4f797.png)

1.  In the left navigation bar, under **Agent Experience**, select **Sessions**.

    ![Graphical user interface, application Description automatically generated](media/e038d4d0259fd80402c86883e6b77606.png)

1.  Select the **Chat session – default** session template. We will associate this session with the agent script.

    ![Graphical user interface, text, application, chat or text message Description automatically generated](media/b594ef069577ba1493cf80899ee4a25d.png)

1.  Double click or select Edit on the command bar to open the **Chat session – default** record.

    ![Graphical user interface, table Description automatically generated](media/93a09a033715c2df44ea0617c8e20ce6.JPG)

1.  Select the Agent scripts tab. In the Agent scripts section, select Add Existing Agent script.

    ![Screenshot of Add existing agent script button in the agent scripts subgrid of the "Chat session - Default" template](media/099a5bc9ce948faf09e58c42de11c5f2.png)

1.  The **Lookup Records** pane should appear on the right.

    ![Screenshot of Searching for Validate Patient Information record in Lookup field](media/00b24e808e88c2eabc959a20fc6fd5a0.png)

1.  In the Look for Records box, select the **search icon** (magnifying glass).![Screenshot of selecting "Validate Patient Information" which shows as agent script record](media/94971a046f6950267b5636b9413b45f4.png)
2.  
3.  Select the **Validate Patient Information** agent script from the list and click **Add.**

    ![Screenshot of Add button on bottom of Lookup Records pane](media/96a82f74b0eb1ffaaa0e8ee100eb7e42.png)

1.  Chat session – default Session Template should have the Validate Patient Information Agent script.

    ![chat session - default agent script tab](media/1364191676ecbba4aafca6224e4f2686.png)

**Congratulations!** You have successfully created an agent script with two steps and associated the agent script with the default chat session. Now your agents can use this script during a default chat session with a patient.

### Step 3: Configure Knowledge Articles

In this exercise, you will learn how to create and manage **Knowledge Articles** that can address any number of issues your customers would like to discuss during the patient service center conversation. These knowledge articles will appear in the productivity pane in Patient Service Center through AI-enabled suggestions.

![Graphical user interface, application Description automatically generated](media/8a9c44ffbba7b810ea6f9389d72c1088.jpeg)

**Task 1: Assign Knowledge Manager User Role**

In this task, we will assign the necessary user role to create and view knowledge articles.

1.  If you kept the User Settings page up from the previous exercise, navigate to that page. If you didn’t keep it open, follow all the steps in Exercise 2, Task 1 and then return here to assign the proper role.
1.  Once you’ve selected your user and clicked **Manage Roles**, you must assign the necessary role(s).

    ![Screenshot of Selecting current IAD User in list and clicking Manage Roles button on command bar](media/2fea347790e3a9500986ebef69801b9f.png)

1.  There are three roles you can choose with [create/read permissions for Knowledge Articles](https://docs.microsoft.com/en-us/dynamics365/customer-service/customer-service-hub-user-guide-knowledge-article#create-a-knowledge-article).
    1.  Knowledge Manager
    2.  Customer Service Manager
    3.  Customer Service Representative
1.  For this lab, select the **Knowledge Manager** role.

    ![Screenshot of Manage User Roles dialog with Knowledge Manager role selected](media/0c6f6bcfb699312d64d3cf30bbecf7e1.png)

1.  Also ensure you have the System Administrator role. Official training users have it assigned.

    ![Graphical user interface Description automatically generated](media/a6456591f6c79edcde47af8d81355902.png)

1.  Select **OK** to close the Manage User Roles window and accept changes.

**Congratulations!** You have assigned the proper roles to create and read knowledge articles.

**Task 2: Set up Knowledge Management Settings**

1.  In [Power Apps](http://make.powerapps.com), open the **Customer Service Hub** app.

    ![Screenshot of Customer Service Hub application in Power Apps list](media/e4e8ca9f21365f405fd6d7de651decaf.png)

1.  In Customer Service Hub**,** on the left navigation bar, go to the bottom left corner where there’s a drop down that says **Service**. Select it and change the area to **Customer Service Admin Center**.

    ![Screenshot of bottom left drop down selection changing from Service to Service Management](media/32e65e67c221eedb9537ff1830158665.png)

1.  Once in in the Customer Service Admin Center area, scroll down to Knowledge Base Management section and select Settings in the left navigation.

    ![Screenshot of Settings option in the site map in Knowledge Base Management section](media/0f47a4ea6cb910d750c1ed3faf283858.png)

1.  **Record Types** allows you to configure the record types you want to turn on for knowledge management.
    1.  The list will include all entities that are available for an N:N relationship.
    2.  Knowledge management is enabled for **Case** table by default. Because our scenario will also use the Case table, **we don’t need to add any additional tables at this time**.

        ![Screenshot of Record Types for knowledge management, with all available on the left and selected on the right.  Currently selected are Case and Contact.](media/823d8feb0addd6d1ca4624cc313cd0e3.png)

1.  For Support Portal Connection, this allows you to integrate an external portal for publishing knowledge articles.
    1.  Selecting Yes would share the knowledge article as a link in the email sent to the customer.
    2.  Selecting No would share the article content inserted in the email body.
    3.  Keep as **No** as we will not be integrating an external portal connection

        ![Text Description automatically generated](media/ea379ac5d214d37effa00e3118c4c844.png)

1.  In the Knowledge Articles Feedback section, set Enable users to provide feedback on knowledge articles from search control to Yes. This will allow users to provide feedback on knowledge articles opened from knowledge search control.

    ![Graphical user interface, text, application Description automatically generated](media/39b8281dcce100a7026284c8684e0cac.png)

**Task 3: Create Knowledge Article**

In this task, you will create a new knowledge article about Asthma for agents to access during patient conversations.

1.  In **Customer Service Hub,** on the left navigation bar, go to the bottom left corner where you previously modified the drop down. Change it back from Customer Service Admin Center to **Service**.

    ![Screenshot of bottom left drop down selection changing back from Service Management to Service ](media/e871a19df46d79073edfe588b14e1067.png)

1.  In the sitemap, navigate to Service \> Knowledge Articles.

    ![Screenshot of Knowledge Article option in site map](media/00ffb41c57784a8f3cb9793f7e566c46.png)

1.  Select New on the command bar.

    ![Screenshot of New button on command bar in Knowledge Article section](media/57c21bff3f4cedf8bf8db26f8e3e618b.png)

1.  You should be on the **Content** tab of a new knowledge article.

    ![Screenshot of content tab of a new knowledge article](media/05ebe37355ff7b3b0fc38c7b4bb1be91.png)

1.  On the **Article** Content section tab of the new knowledge article, specify the following details:
    1.  Title: Shortness of Breath
    2.  Keywords: Asthma, shortness of breath, trouble breathing, inhaler, albuterol
    3.  Description: Uncomfortable sensation or awareness of breathing or needing to breathe.

        ![Screenshot of the new knowledge article with title, keyword, and description completed](media/6153262144eab58ac00217ae64c4537c.png)

    4.  In the Content section, copy and paste the content for your knowledge article.

**Common causes**

Shortness of breath is not always related to an underlying condition. It may be caused by:

• Aerobic exercise

• Intense physical activity

• High altitude with lower oxygen levels

• Poor cardiovascular fitness

• Anxiety

• Being obese

• General weakness

**Treatment**

Self-treatment: Self- care steps that may be helpful in some less- serious cases:

• Stop smoking

• Avoid exposure to pollutants, allergens and environmental toxins

• Lose weight if overweight

• Avoid exertion at elevations

• Take slow even breaths

• When you breathe out, put your lips together, like slowly blowing out a candle (Pursed Lip Breathing)

**See a doctor if you notice:**

• Chest pain or pressure

• Inability to function

**See a doctor immediately if you notice:**

• Fever or a change in the amount, color, or thickness of sputum

• Breathlessness does not go away after resting for 30 minutes

• Swelling in the feet and ankles

• Trouble breathing when you lie flat

• High fever, chills, and cough

• Wheezing

• Worsening of pre- existing shortness of breath

1.  Select **Save**.

    ![Screenshot of save button on command bar for the new knowledge article](media/e5d4e192477dd75f6562c2b79044024c.png)

The Business Process flow bar at the top of the form helps you to drive the article towards completeness. You have the option to customize the stages in the Business Process flow to suit your requirements. We will now complete the author stage so it can move into review.

1.  On the Business process bar, select **Author**. The business step options should pop out below.

    ![Graphical user interface, text, application, email Description automatically generated](media/57bfddad3d76fe1f19df74c9367f44c8.png)

1.  Add the **Article Subject:** Default Subject. This is the subject of the article to help with searches.
2.  
3.  Check the box for **Mark for Review** as Mark Complete.
4.  
5.  In the Assign Primary Author drop-down list, you may choose a person who is responsible for maintaining the article content. By default, the user who creates the article is the primary author. For this training, we will keep it as our IAD user.
6.  
7.  Select **Next** Stage to mark the article complete and ready for review.

    ![Screenshot of close up of the author stage with information filled out](media/68e191a98761c7f8cf1af06369315737.png)

1.  The knowledge article is now in the review stage of the business process flow and is ready for review.

    ![Screenshot of Review Stage selected in the business process flow](media/8ffe9c715b0d79ed71b64d9f2afb6fd1.png)

**Congratulations!** You have successfully created a knowledge article for Shortness of Breath and marked it for review.

**Task 4: Review and Publish Knowledge Article**

To ensure accuracy of the knowledge article, typically someone else would review and approve it. For this training exercise, you will mark the article reviewed and approved yourself. Quick note that this task also requires the Knowledge Manager role or another that can approve knowledge articles.

1.  In Customer Service Hub, navigate to Service \> Dashboards and use the drop-down to choose the My Knowledge Dashboard.

    ![Screenshot of Dashboards selected in site map, changing the view from Tier 1 dashboard to My Knowledge Dashboard in Customer Service Hub](media/99ab776f79b9c1dee74989e3566de123.png)

1.  Note the **Shortness of Breath** knowledge article in My Active Articles stream.

    ![Screenshot of "Shortness of Breath"  article showing in My Active Articles stream in My Knowledge Dashboard](media/cad75dd81011f049765e4289b10ea811.png)

1.  Select the **Shortness of Breath** knowledge article.
2.  
3.  On the Business process bar, in the Review stage and in the Review drop-down, select Approve.

    ![Screenshot of the business process flow of a knowledge article which is in review stage and has the Review field drop down selected on the approved option](media/43e8f5464d7afc435088a38e554e1476.png)

1.  Click OK when prompted to Confirm approve article.

    ![Screenshot of the OK button to confirm approval of article](media/225c0dc11357426a72918a03147f61a3.png)

1.  Select **Next Stage** to move to Publish stage.

    ![Screenshot of the next stage button below the review field in the business process flow](media/9170066168ce52a44b2a506e28a27544.png)

1.  You should now be in the **Publish** stage and **Status Reason** should have changed to **Approved.**

    ![Screenshot of publish stage currently highlighted and status reason field in upper right changed to approved](media/aad77bd8e2b677707d0228875832b2b1.png)

**Congratulations!** You have successfully reviewed and approved the knowledge article. We will show you how to publish the Knowledge Articles to be available during patient service center calls.

**Task 5: Publish your Knowledge Article**

In this task, you will learn how to publish the knowledge article so it’s live and ready to be used.

1.  In your **Shortness of Breath** Knowledge Article, Select the **Publish** stage.
    1.  For Set Product Associated check the box Completed.
    2.  Add an **Expiration Date** for one year from now.
    3.  Select **Finish**

        ![Screenshot of fields filled in for publish stage of knowledge article.  Check Completed textbox for Set Product Associated and Add an expiration date for one year from now](media/a58a4eee25001ea231db54551034f46b.png)

1.  Once you select Finish, the business process flow should show as completed.

    ![Screenshot of business process flow showing completed flag after selecting finish](media/7ef44795ee7e7b508110f1d643665faa.png)

1.  Now you can specify the additional Publish details. On the command bar to go **More** \> **Publish**.

    ![Screenshot of Command bar selecting more and Publish command](media/36c8b3abe8da59c416dead6c56edaa7f.png)

1.  Specify the following details (see screenshot below):
    1.  Publish: Now
    2.  Published Status: Published
    3.  Expiration State: Published
    4.  Expiration Status: Published
    5.  Publish approved related translations with Article, choose Yes.
1.  Select **Publish**

    ![Screenshot of Publish dialog with details filled out and publish button at bottom](media/83239e1b381acd73c49268fc373fb101.png)

**Congratulations!** You have successfully reviewed and published the knowledge article. We will see these knowledge articles highlighted in Patient Service Center when testing the final escalation.

### Step 4: Experience Escalation & Smart Assist Features

In this exercise, you will utilize the Smart Assist features and test the full experience you configured for the patient and patient service center agent. Starting from when the patient logs into the portal website, continuing with a health bot conversation, and ending with an escalation to a human agent who can provide proper care in Dynamics 365 with Agent Scripts and Knowledge Articles.

The following screen shows Patient Service Center after a patient has been escalated to a call agent. This lab will conclude by bringing together all the components we’ve set up in previous exercises and show how the call agent can give personalized experiences with proposed insights directly in the application.

![Graphical user interface, application Description automatically generated](media/8e6706ef2eef1c1bdb9efbf831041956.jpeg)

**Task 1: Patient Logs into Access Portal & Agent logs into Patient Service Center**

1.  Navigate to Power Apps and open the **Lamna Healthcare Patient Portal** app.
1.  Sign into the Patient Portal as Caseyn Jensen, using the credentials you created in Exercise 1, Task 2 when you registered Casey for the patient portal.

    ![Graphical user interface, text, application, email Description automatically generated](media/db07329384b199f5a9f6d94f03b3d336.png)

1.  You should be directed to the profile if your email requires confirmation. Click **Contoso Healthcare** in the upper left to go to the portal Homepage.

    ![Graphical user interface, application Description automatically generated](media/430a84080ec4eb8c3541d5945b916b57.png)

1.  Your patient is all set in the Patient Portal. Now we need to make sure an agent is available for them when the Health Bot needs to escalate.

    ![A screenshot of a computer Description automatically generated with low confidence](media/f6b87d973d06712d264439c35ac3e3ba.png)

    Note: Before opening Patient Service Center, make sure you have completed adding the Omnichannel agent role to your user in Lab 04.

2.  If you didn’t assign the Omnichannel agent role in Lab 04, assign the proper role by following the steps in Exercise 2, Task 1 – Assign Productivity User Roles. Once you’ve selected your user and clicked **Manage Roles**, assign the **Omnichannel agent** role and click **OK**.

    ![Graphical user interface, application Description automatically generated](media/3b75a901c3e5d933582bfe973909e26c.png)

1.  Navigate to Apps and open the **Patient Service Center** app.

    ![Graphical user interface, application, Teams Description automatically generated](media/cf542213d626521ace985ea2f08e48e8.png)

1.  In the **Patient Service Center**, you should see a “Loading…” splash screen that goes through percentages. This ensures the live agent status is captured properly.

    ![Screenshot of splash screen which is faded white background and shows loading percentages for page load.  This will allow omnichannel to work properly.](media/6854dfaaeceff89490446f0545377eab.png)

    1.  If you don’t see the splash screen and the presence indicator is grayed out, escalation into the app from the health bot won’t work properly.
    2.  Refresh again or close and reopen Patient Service Center until the splash screen appears. You may need to close all other apps or close incognito altogether and sign back in.
    3.  If you just assigned the Omnichannel agent role, it may take up to 15 minutes to apply and for the presence to show for your user.
1.  Once your presence indicator is green, you are ready to accept patient escalations.

**Congratulations!** You have successfully logged in as both the patient and the live agent. Now it’s time to start the Health Bot conversation.

**Task 2: Patient Escalates through Healthcare Bot**

1.  Select the **Let’s Chat** Health Bot chat widget in the bottom right corner of the portal.
1.  The Health Bot should go through the same conversation you created in Lab 04.
2.  Make sure you set the Welcome message in the Health Bot lab
3.  If the welcome message doesn’t show, check the settings you did in Lab 04 (Teams and Human handoff enabled). Also make sure you added the widget snippet to the Patient Healthcare chat widget.
1.  Select **Lamna Healthcare** **Support** to start a support conversation.

    ![Graphical user interface, text, application Description automatically generated](media/f7998f51dffae5f8261257a48c16004c.png)

1.  Select **Live Agent** in the next prompt to escalate to an agent.

    ![Graphical user interface, text, application Description automatically generated](media/9a82e8062df05c6b478fc2faab834062.png)

1.  You will see the chat notifies you -- **An agent will be with you in a moment.**

    ![Graphical user interface, text, application, chat or text message Description automatically generated](media/fbd6bfbbec418bf994d9698671442a55.png)

1.  Now let’s switch over to the **Patient Service Center** app so you can accept the escalation as an agent.

**Congratulations!** You have successfully configured and started a conversation with the Health Bot in the Healthcare Patient Portal and asked to escalate to an agent in Patient Service Center.

**Task 3: Agent Provides Personalized Care in Patient Service Center with the Productivity Pane**

In this task, you will act as the Patient Service Center Agent, accept the escalation from the healthbot and assist the patient with their issue by using the productivity pane.

1.  Navigate back to the **Patient Service Center** app. You should be signed in as your IAD User.
1.  Notice in the upper right corner there is a **Chat request** from your user.

    ![Graphical user interface, application Description automatically generated](media/a86b475cd7f4a303e6c23504344da447.png)

1.  Select **Accept** to start a conversation with the patient.

    ![Graphical user interface, application Description automatically generated](media/e05e4951c00fe8148cb16c780ad0591e.png)

1.  The page should reload and show the patient record, active chat, and productivity pane as seen below.

    ![Graphical user interface, text, application, email Description automatically generated](media/8a35ab925db7741cabcc59089d727d13.png)![Graphical user interface, text, application Description automatically generated](media/ee07e8ee1d71c1a249f16a2b9f49f4b0.png)

2.  See the chat directly embedded on the left-hand side. Try out the command bar below it to see various options such as **auto-replies** and **surveys**.
3.  
4.  Navigate the **productivity pane**. Go through the **agent script** and check off ones you complete asking the patient.
5.  
6.  Go to **Knowledge Article** tab and **search** for “Breath” or “Inhaler”. Notice your Knowledge Article appear.

**Congratulations!** You completed the full experience from logging in as a patient to the portal, conversing with the health bot, and escalating into Patient Service Center to navigate the features for the agent.
