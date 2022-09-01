# Module 4 Lesson 2 Lab 6: Virtual Visits

### Overview

Microsoft Cloud for Healthcare’s Virtual Clinic application allows clinicians to use video conferencing to provide high-quality, personalized, and affordable consultations. Using the entire meetings platform in Microsoft Teams, providers will be able to schedule, manage, and conduct virtual visits with patients. The Virtual Clinic application can then be embedded inside of Microsoft Teams to provide a practitioner with a full view of their patient’s information and history all in one unique experience.

Virtual Care focuses on the **Enhance patient engagement** priority scenario by providing a virtual health solution for scheduling and following up on virtual visits between patients, providers, and care managers.

![Graphical user interface Description automatically generated with low confidence](media/a80a4a603d633f5df7d527053e243986.png)

This lab will focus on the healthcare story of Reed Flores.

![Timeline Description automatically generated](media/e1b780cb60215a8edad2bdc8e3f231d0.png)

After coming home from hiking, Reed noticed he had a new rash on his right leg. He decides to schedule a virtual appointment to get a diagnosis.

In this lab, you will first play the role of a Lamna Healthcare system administrator by configuring the Microsoft Cloud for Healthcare Virtual Clinic application to be used for virtual appointments. Then, you will play the role of Reed Flores by scheduling a virtual appointment with his practitioner, Alex Johnson. Finally, you will join the virtual appointment from the view of a practitioner to observe the complete end-to-end experience.

### Learning objectives

In this lab, you will:

-   Configure the Virtual Clinic app
-   Configure Microsoft Teams for virtual visits
-   Schedule a virtual visit in the Patient Portal

### Step 1: Configure Virtual Clinic Application

In this exercise, you will configure the Microsoft Cloud for Healthcare Virtual Clinic application. The Virtual Clinic application allows practitioners to use video conferencing in Microsoft Teams to provide high-quality, personalized, and affordable consultations for their patients.

**Task 1: Create a new Practitioner Specialty for the Patient Portal**

In this task, we are going to create a new **Practitioner Specialty** for the Patient Portal. Practitioner Specialties are used to define the **reason** why a patient is booking the virtual appointment. They are defined as Codeable Concepts records, with the type of Practitioner Specialty.

Below is an example of the appointment booking screen in the Patient Portal. As the first step in the process, the user must select a reason for their appointment.

![Graphical user interface, text, application, email Description automatically generated](media/ccb1b44d12b0d6caabd252475a2145df.png)

1.  Go to <https://make.powerapps.com/>.
1.  In the upper right-hand corner, click the **funnel** **icon** which will open **Advanced Find**.

    ![Icon Description automatically generated with low confidence](media/1faacbcd948dcdf1d466318763fd2d55.png)

1.  In the **Search** box, browse for **Codeable Concepts** and click **Results**.

    ![Graphical user interface, text, application, email Description automatically generated](media/02c3d6b00c0d7b8e9ea846b1252224aa.png)

1.  Click New Codeable Concept.

    ![Graphical user interface, application Description automatically generated](media/318b20befd92fdf710272f5e41dcf626.png)

1.  In the new Codable Concept record, fill in the following details and click **Save**.
    1.  **Name**: General Medicine
    2.  **Text**: General Medicine
    3.  **Type**: Practitioner Specialty
    4.  **Code**: general

        ![Graphical user interface, application Description automatically generated](media/4a13e98825a4d57bfd20fea2f4a2b167.png)

**Congratulations!** You have created a new Practitioner Specialty that will now be available for selection as an appointment visit in the Patient Portal.

**Task 2: Configure Mapped System User on Practitioner Record**

In this task, you will configure the Mapped System User field on the Practitioner record. This field should be set to the system user that maps to the contact record. In our case here, we will set it to the record associated with our logged in user. This will allow our user to act as the practitioner in the virtual visit.

There are two different places the Teams meeting may be created:

-   In the case of virtual appointments, the Teams meeting is created on the mapped user’s calendar.
-   In the case of instant virtual appointments, the Teams meeting is created on the Organizer (organizer email for virtual appointments) specified in the Admin settings.
1.  In Power Apps, select **Apps** and then open the **Virtual Clinic** application.

    ![Graphical user interface Description automatically generated](media/ebf86a3f8ca40a22a7615f0126e698ca.png)

1.  Click **People**, change the view to **Active Practitioners**, and open the **Alex Johnson** record.

    ![Graphical user interface, application Description automatically generated](media/02e773cf30f4ed94ff650aa83db31add.png)

1.  Select your logged in user as the Mapped System User.

    ![Graphical user interface, application Description automatically generated](media/59446647d343ea4a04f3948997dea8a9.png)

1.  Click Save & Close.

**Congratulations!** You have mapped the practitioner record to your logged in user.

**Task 3: Enable a Practitioner’s Schedule**

In this task, you will configure the practitioner’s schedule to allow patients to book appointments with them using the Patient Portal. This will allow Reed to schedule an appointment with his practitioner, Alex Johnson.

1.  In the Virtual Clinic app, change the sitemap area in the lower left corner from Operations to **Schedule Administration**.

    ![Graphical user interface, text, application Description automatically generated](media/e033de1a1d28384b5af217bd335302d3.png)

1.  On the sitemap, select **Schedules** and open the **Alex Johnson schedule** record.

    ![Table Description automatically generated](media/08500f5b62502dbd57406c734c23fd41.png)

1.  Change **Active** from No to **Yes** and click **Save**.

    ![Graphical user interface, text, application Description automatically generated](media/b80d9a614b642828fe6326e9cd33c41a.png)

**Congratulations!** You have enabled a practitioner’s schedule to be used for booking virtual appointments.

**Task 4: Configure Slots**

In this task, we will configure a new appointment slot to show practitioner’s availability. This will allow patients to select an available appointment time slot when booking with a practitioner. In this case, we will enable the practitioner, Alex Johnson, to be available today at a set time for virtual appointments.

1.  In the Virtual Clinic app, select **Slots** on the Site Map and click + **New**.

    ![Graphical user interface, table Description automatically generated](media/eda35f527c35329d961bea0989a8b78a.png)

1.  Fill in the following record details and click **Save & Close**.
    1.  **Name**: Alex Johnson Slot
    2.  **Start**: Today, at a later time
    3.  **End**: Today, an hour after the Start
    4.  **Schedule**: Alex Johnson schedule
    5.  **Status**: Free
    6.  isVirtual: Yes
    7.  **Specialty**: General Medicine (the practitioner specialty record you created)
    8.  **Service** **Category**: General Medicine (same as specialty)

        ![A screenshot of a computer Description automatically generated](media/4b9bbe16e1a0df3b6ed58acd59877153.png)

**Congratulations!** You have created a new virtual slot for Reed to book with his practitioner, Alex Johnson.

**Task 5: Configure Environment Variables**

In this task, you will configure the environment variables necessary to generate a Microsoft Teams URL for virtual appointments.

1.  Go to <https://make.powerapps.com/>
1.  Go to Apps and click on See environment variables.

    ![Graphical user interface Description automatically generated](media/0070f93d2bc7dc2fa97e7d925973b5c4.png)

1.  Scroll down to the bottom to find the **Virtual Visit Secret** and the **Virtual Visit Client ID**. These environment variables are used to authenticate against the Microsoft Graph API to schedule the meeting event. To set these up, we need to create a new Application Registration in Microsoft Azure.

    ![Graphical user interface, text, application, email Description automatically generated](media/012aec1d6bf3f211366c99ddc9f61dd4.png)

1.  **Copy and paste** the following variables:
    1.  **Virtual Visit Secret**: aJm7Q\~y_bSlwV0z\~pQ0NZ3-zIlmhNKJbPzPfa
    2.  **Virtual Visit Client ID**: dfda9044-cb98-4b0f-8086-cd651dbe4af4

        ![Graphical user interface, text, application, email Description automatically generated](media/56775c1a6d99c72da699b2996c50a05f.png)

1.  Finally, enter the email address of your logged in user into the Virtual Appointment Scheduler Email field (*ex: iaduser77@powerplatformopenhacks.onmicrosoft.com*).

    ![Graphical user interface, text, application, email Description automatically generated](media/4dfedeb1ee2a225e24947e8cb66909e8.png)

1.  Click Save and close.

    ![A picture containing shape Description automatically generated](media/44a48230a3b1acd0daa899234e90566c.png)

**Congratulations!** You have obtained the Virtual Visit Client ID and Virtual Visit Secret combination to be used to authenticate against the Microsoft Graph API to schedule virtual meeting events. You have also entered the email address of a primary event scheduler.

**Task 6: Activate Flows and Connection References**

In this task, we will activate the Flows and Connection References that deployed along with the Virtual Clinic application.

1.  Navigate to <https://make.powerapps.com/>.
1.  Click **Solutions** and then click **+ New Solution**.

    ![Graphical user interface, text, application, email Description automatically generated](media/4754d85b05618140ea7f1f9ad24ee2c1.png)

1.  Name the solution “LamnaHealthcare”, choose the **Default Publisher** and click **Create**.

    ![Graphical user interface, text, application, email Description automatically generated](media/5477e74e67a4d5fc0e61cecf25a4f038.png)

1.  Select the new **LamnaHealthcare** solution and click **Edit**.

    ![Graphical user interface, application Description automatically generated](media/0db14a90b193fbe7382d9613b10c5c08.png)

1.  Click **+ Add existing** and select **Cloud flow** under Automation**.**

    ![Graphical user interface, application Description automatically generated](media/b7bd1ab8c37c47e7770742e135d9cb03.png)

1.  Select CF -\> Schedule Teams Meeting for instant and virtual, update record with url and status to booked and click Add.

    ![Table Description automatically generated](media/98d3128e46503ca1af29a560478963e2.png)

1.  **Select** the Cloud flow. Navigate to **Details in a new tab** on the command bar to open Power Automate.

    ![Graphical user interface, text, application Description automatically generated](media/ed7b4c077792139d9ac5235932d03c7a.png)

1.  Under the **Connection References** section, click **Edit**

    ![Graphical user interface, text, application, email Description automatically generated](media/7c1f3a06a732fa0bb7e3065753fc9c12.png)

1.  Click **Edit**.

    ![Graphical user interface, text, application, chat or text message Description automatically generated](media/db96215330daafc96fbe45dd5174ded1.png)

1.  Click **Sign in** for **Microsoft Dataverse** to create the Connection Reference.

    ![Graphical user interface, application, Teams Description automatically generated](media/c63e62ebd65b7c6f46f9d694dec8278b.png)

1.  Click **Sign in** for **Office 365 Users** to create the Connection Reference.

    ![Graphical user interface, application, Teams Description automatically generated](media/8b9238a0adf152fc5ccc87e0fcf52ebb.png)

1.  Click Continue

    ![Graphical user interface, application, Teams Description automatically generated](media/8badfc5b56e5eb0cfa9545db92a076bb.png)

1.  Click **Save** to commit your updates.

    ![Graphical user interface Description automatically generated](media/a0dd75240c923ef21273380ecec512aa.png)

1.  Click the **Back** **arrow** to return to the flow’s main page. Ensure it has completed saving first.

    ![Graphical user interface Description automatically generated](media/ecda0b0dbacdd67534de676419edfdbf.png)

1.  Click **Turn on** to turn on the flow.

    ![Graphical user interface, text, application, email Description automatically generated](media/a5e24735c323fa23123fd2c911194225.png)

**Congratulations!** You have set the Connection References and turn on the Cloud flow for creating virtual appointments.

### Step 2: Configure Microsoft Teams for Virtual Visits

In this exercise, you will configure integration with Microsoft Teams for Lamna Healthcare Company. Microsoft Teams offers several features useful for hospitals and other healthcare organizations. By integrating Microsoft Cloud for Healthcare with Microsoft Teams, you can improve the collaboration between your care team staff and enhance patient care. You can quickly schedule and conduct virtual visits remotely with patients.

Additionally, your care team can use Microsoft Teams internally to do the following:

-   Chat, call, post messages, and communicate as a team.
-   Store and share files and documents to collaborate.
-   Use Shifts to create, manage, and share schedules among your staff.

**Task 1: Install and Set up Microsoft Teams Integration**

By default, the Basic and Enhanced Microsoft Teams integration is disabled for customer engagement apps in Dynamics 365. In this Task, we will enable Microsoft Teams in Dynamics 365.

1.  Go to <https://admin.powerplatform.microsoft.com/>.
1.  Select your Microsoft Cloud for Healthcare environment from the list

    ![Graphical user interface, text, application Description automatically generated](media/1836537d73376573e5fb9d2b7558e082.png)

1.  You will land on your environments detail page.

    ![Graphical user interface, text, application, email Description automatically generated](media/ef6fd936eacf8812499e25fbbaac2b61.png)

1.  Click the **Settings** button on the top command bar.

    ![Text, whiteboard Description automatically generated](media/85896a835a3355e762af5fe9840d9bad.png)

1.  Expand Integration and click Teams integration settings.

    ![Graphical user interface, text, application, email Description automatically generated](media/2329de372d9876c76a8d754209242107.png)

1.  On the Microsoft Teams collaboration and chat page, switch Turn on the linking of Dynamics 365 records to Microsoft Teams channels to Yes.

    ![Graphical user interface, text, application, email Description automatically generated](media/899a692a21780118c2faaf57bd7a1a78.png)

1.  Click the **Save** button at the bottom left.

    ![Graphical user interface, text, application, email Description automatically generated](media/137b241141333e8d18ae569620d62026.png)

1.  After the page finishes saving, switch Turn on Enhanced Microsoft Teams Integration to Yes.

    ![Graphical user interface, text, application, email, Teams Description automatically generated](media/70dac6602a56df9ff64212d15428c21f.png)

1.  Another pop-up window will open to grant permissions. Select the user you are signed in as currently.

    ![Graphical user interface, text, application Description automatically generated](media/2f13a02d898b9e3d9c6537ab58559e6c.png)

1.  Click **Accept** for requested permissions. It may take several minutes to configure. Ensure you do not have pop ups blocked that may interfere with the communication. If so, turn off blockers for this website, cancel and try connecting again.

    ![Graphical user interface, text, application, email Description automatically generated](media/a7da2492f689d1f452376b93eace9bc2.png)

1.  Once the dialog disappears, Click the **Save** button at the bottom left.

    ![Graphical user interface, text, application, email Description automatically generated](media/f71311d436c06414f5e4d721ee94e808.png)

1.  You will now see that both Microsoft Teams Integration settings are set to Yes. Click **OK**.

    ![Graphical user interface, text, application, email Description automatically generated](media/14be7b5a7a18f48531305653a3979668.png)

**Congratulations!** You have enabled Microsoft Teams integration for Dynamics 365.

**Task 2: Embed Virtual Clinic App in Microsoft Teams**

In this task, you will customize the Microsoft Teams experience for a practitioner by embedding the Virtual Clinic app to the Teams channel in your environment. We will be utilizing the Microsoft Teams web experience for this task.

1.  While logged in to your Microsoft 365 tenant, open a new tab and go to [teams.microsoft.com](https://teams.microsoft.com).
1.  Click **Next** through the prompts, and then click **Let’s Go.**

    ![Graphical user interface, application, website Description automatically generated](media/38cb4520ab52a69964b85936b95fc228.png)

1.  Select Teams on the left navigation bar and then click **Create Team.**

    ![Graphical user interface, text, application, chat or text message Description automatically generated](media/c3f3046db55b654eb748f94825aac452.png)

1.  Select From scratch.

    ![Graphical user interface, application Description automatically generated](media/a333cef7d1afcaa22e72522f4de518a4.png)

1.  Select **Public**.

    ![Graphical user interface, application Description automatically generated](media/b1ae8aee4900194a459ebed9398346e4.png)

1.  Name the Team “**Lamna Healthcare – Redmond**” and click **Create**. You may skip add members step.

    ![Graphical user interface, application, Teams Description automatically generated](media/682c2a0ef24005fd91427113453ace44.png)

1.  Once the Team is created and the **General channel** selected, click the **+** button to add a tab

    ![Graphical user interface, application, Teams Description automatically generated](media/ec40e5cc4aaefc2f45941dcffe1f2cf2.png)

1.  Search for “Power Apps” and select **Power Apps**

    ![Graphical user interface, application, Teams Description automatically generated](media/889a72631d0c182a0dc46df5cccfdf3a.png)

1.  Click **Add**

    ![Graphical user interface, application, Teams Description automatically generated](media/721b19459b496796ffb9ded2f886e5f7.png)

1.  Select **Model-driven apps** form the dropdown menu, then scroll down and select **Virtual Clinic** and click **Save**. Ensure to select the app that is associated with your environment.

    ![Graphical user interface, application, Teams Description automatically generated](media/be3a8fc25645a7e38b6d0763e4b18e87.png)

1.  You will now see the Virtual Clinic app embedded in Microsoft Teams

    ![Graphical user interface, text, application Description automatically generated](media/bdbff2ffd925ef80930571dc24df5163.png)

**Congratulations!** You have embedded the Virtual Clinic app in Microsoft Teams.

### Step 3: Schedule a Virtual Visit

In this final exercise, you will use the items that you configured in the previous exercises to schedule a virtual visit between Reed Flores and his practitioner, Alex Johnson.

**Task 1: Schedule an Instant Virtual Appointment**

In this task, you will log in to the Patient Portal as Reed Flores and schedule an instant virtual appointment.

1.  Go to <https://make.powerapps.com/>
1.  First, we must create an account in the patient portal for Reed Flores like we did for Casey Jensen in Lab 05: Patient Access & Service Center. Go to Apps and open Healthcare Administration.

    ![Screenshot of Apps screen with Healthcare Administration App](media/546ab9d2b2e4d2a6f5b8192a7d00eb18.png)

1.  Open Reed Flores’ record and select **Create Invitation** on the command bar.

    ![](media/1b0a2c7a9ec521b9a369efc2a4030aa0.png)

1.  Click **Save** and navigate to the **Advanced** tab for the invitation code. Store the invitation code.

    ![Graphical user interface, text, application, email Description automatically generated](media/9a8fef20860634aee1f905c847523418.png)

1.  Navigate back to Power Apps and open the **Lamna Healthcare Patient Portal.**

    ![Table Description automatically generated with low confidence](media/775a411d65cfd4b848686ea23a176231.png)

1.  Select **Sign in**.

    ![Graphical user interface, text Description automatically generated](media/2734a3e7f954d428097939d5facec573.png)

1.  Select the Redeem Invitation tab, enter the Invitation code, and click Register.

    ![Graphical user interface, text, application Description automatically generated](media/80b8c405116d03c6e6a807e94850b42b.png)

1.  Create an account for **Reed Flores**. Click Register.

    ![Graphical user interface, text, application, email Description automatically generated](media/b70b1b69703205a3825c086fc8459b5e.png)

1.  If you are landed on the profile page, select the Lamna Healthcare name or logo in the top left to go to the homepage.

    ![Graphical user interface, application Description automatically generated](media/6ce32b3e794b766e00b044a832bfb3a1.png)

1.  Expand Appointments and select Schedule new.

    ![Graphical user interface, website Description automatically generated](media/04e1d36b478a3f302a3fc90945051ac8.png)

1.  Select Instant virtual appointment.

    ![Graphical user interface, text, application, email Description automatically generated](media/07d854417b3ea7ccb8b7ddb58700d486.png)

1.  Select the **General Medicine** option that you created earlier in the lab as the reason for the visit.

    ![Graphical user interface Description automatically generated](media/59bc7018bb8ec462a8652f5d00f4bbc5.png)

1.  On the Personal tab, Reed Flores’ personal information should auto-populate. Scroll down and click **Next** to go to the next section. It may take a moment for the button to enable.

    ![](media/4f03c8b11c4510e49a769078c9d77b90.png)

1.  On the insurance section, click **+ Add Insurance.**

    ![Graphical user interface Description automatically generated with medium confidence](media/65db925389d314c89cb609ef86eb0a8f.png)

1.  Fill out the required fields with any information and click **Next.**

    ![Graphical user interface, text, application, email Description automatically generated](media/8f3c2e7487c8db26fb36d9c08aab8adb.png)

1.  Click **Next.**

    ![Graphical user interface, text, application, email Description automatically generated](media/6c6b6cba9f36defd6cca7fd1cdf1b36e.png)

1.  **Check the box** for Consent Terms and then click **Join queue**.

    ![Graphical user interface Description automatically generated](media/d98f08003dca032ccd7a1a4273330f68.png)

1.  A new internet browser tab will open and may be blank. Let’s join as the practitioner first and then rejoin as the patient.
2.  
3.  Open a new tab in your browser and go to [teams.microsoft.com](https://teams.microsoft.com). Select “**Use the web app instead**”.

    ![Graphical user interface, text, application, chat or text message Description automatically generated](media/41adac5e90d22499042b6d405a037561.png)

1.  Navigate to the Virtual Clinic app that you embedded in the “Lamna Healthcare – Redmond” Teams channel.

    ![Graphical user interface, application Description automatically generated](media/230b0405cfc97bddcb7cdc5fdb604f89.png)

1.  On the Instant Virtual Appointment Dashboard, you will see that **Reed Flores** has arrived for a virtual appointment. **Double-click to open the record**.

    ![Graphical user interface, text, application, email Description automatically generated](media/61597aa3bc69ab8a0e6afee27ef8ea86.png)

1.  When Reed Flores’ patient record opens, click **Join Meeting**.

    ![Graphical user interface Description automatically generated](media/aecc4110c4fa4280aa5efb01883ea462.png)

1.  Click **Cancel** as we will not open the Microsoft Teams desktop app in this example.

    ![Graphical user interface, text, application Description automatically generated](media/06c98860f36980c6b316ee955e6aa981.png)

1.  Click **Continue on this browser** to proceed with opening the virtual meeting.

    ![Graphical user interface, application Description automatically generated](media/6ded8121de17f3d604a5faf169afe487.png)

1.  Click **Join now** to join the virtual meeting.

    ![Graphical user interface, application, Teams Description automatically generated](media/4c6606e1e16ab28769ae6316af714aa8.png)

1.  Click **Teams** on the right to reduce the size of the meeting and see the full holistic experience for a practitioner.

    ![Graphical user interface, application, Teams Description automatically generated](media/89a698961ee5fedba87ce4592207a13d.png)

    ![A screenshot of a computer Description automatically generated](media/bc0a291ad2f6bf24bd264686124f3d40.png)

1.  Go back to the Lamna Healthcare Patient Portal tab and **click the link** provided to join the appointment as the patient in the portal.

    ![Graphical user interface, website Description automatically generated](media/345f50ff673cd7ab4a4d38d5c0d9acb4.png)

**Congratulations!** You have scheduled an instant virtual appointment using the patient portal and joined the appointment as a practitioner using the Virtual Clinic app embedded in Microsoft Teams.

