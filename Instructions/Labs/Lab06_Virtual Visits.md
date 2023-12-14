# Module 4 Lesson 2 Lab 6: Virtual Visits

## Overview

Microsoft Cloud for Healthcare's virtual health allows clinicians to use video conferencing to provide high-quality, personalized, and affordable consultations. Using the entire meetings platform in Microsoft Teams, providers can schedule, manage, and conduct virtual consultation with patients. With the Microsoft Teams integration, practitioners get a full view of their patient's information and history.

Virtual Care focuses on the **Deliver Exceptional Patient experiences** and **Foster health team collaboration** priority scenario by providing a virtual health solution for scheduling and following up on virtual visits between patients, providers, and care managers.


This lab will focus on the healthcare story of Reed Flores.



After coming home from hiking, Reed noticed he had a new rash on his right leg. He decides to schedule a virtual appointment to get a diagnosis.

In this lab, you will first play the role of a Lamna Healthcare system administrator by configuring the Microsoft Cloud for Healthcare Virtual Clinic application to be used for virtual appointments. Then, you will play the role of Reed Flores by scheduling a virtual appointment with his practitioner, Alex Johnson. Finally, you will join the virtual appointment from the view of a practitioner to observe the complete end-to-end experience.

## Exercise 1: Configure Microsoft Cloud for Healthcare for virtual visits

In this exercise, you will configure the Microsoft Cloud for Healthcare Virtual Clinic application. The Virtual Clinic application allows practitioners to use video conferencing in Microsoft Teams to provide high-quality, personalized, and affordable consultations for their patients.

## Task: Create a new Codeable Concept for practitioner specialty type

In this task, you’ll create a new Codeable Concept of type **practitioner specialty** to use on the **Patient Portal**. Practitioner specialty is used to define a reason why a patient is booking the virtual appointment.

As the first step in the booking process, the user must select a reason, which includes the practitioners' specialties.

**Note** - The Codeable Concept is one of the most important data items in HL7’s Fast Healthcare Interoperability Resources (FHIR) and is defined in the FHIR specification as a value that is usually supplied by providing a reference to one or more terminologies or ontologies, but may also be defined by the provision of text. Practitioner covers all individuals who are engaged in the healthcare process and healthcare-related services as part of their formal responsibilities and this resource is used for attribution of activities and responsibilities to these individuals.Practitioners include (but are not limited to):

    •	physicians, dentists, pharmacists

    •	physician assistants, nurses, scribes

    •	midwives, dietitians, therapists, optometrists, paramedics

    •	medical technicians, laboratory scientists, prosthetic technicians, radiographers

    •	social workers, professional homecare providers, official volunteers

    •	receptionists handling patient registration

    •	IT personnel merging or unmerging patient records

    •	Service animal (for example, ward assigned dog capable of detecting cancer in patients)

Following is an example of the appointment booking screen in the Patient Portal, which displays the practitioner’s specialties defined as Codeable Concepts.
 
For an entity that isn’t shown directly on an application’s navigation, you can add a new record for those entities through Power Apps. To create a new practitioner specialty, you’ll create a new Codeable Concept record through Power Apps.

1.	While signed into your Microsoft 365 tenant, open a new tab, and go to Microsoft Power Apps. Select your environment.

2.	On the left navigation pane, select **Tables**.

3.	In the right pane, select **All** tables.

4.	Use the search box in the upper right corner to search for the string **codeable**.

5.	Select the **Codeable Concept** table from the search results and then select Edit.
 
6.	Select **+New** **row** dropdown and then select **New row using form.**

7.	In the **New Codable Concept** form, fill in the following details.

    o	**Name** - General Medicine

    o	**Text** - General Medicine

    o	**Type** - Practitioner Specialty

    o	**Code** – general

    o	Select **Save & Close**

8.	After saving and closing the new **Codeable Concepts** form, select **Done** on the **Currently adding a new row** pop-up to refresh the **Codeable Concepts** table.

 
9.	Once the **Codeable Concepts** table is refreshed, select the **Name** column, and then select **Filter by.**

 
10.	In the **Filter by** pane, use the below expression and select **Apply**.

    o	**Operator**: Contains

    o	**Value**: General

 
11.	You can now verify that a new codeable concept of type **Practitioner** **Specialty** is successfully created.

 
You've created a new practitioner specialty that will now be available for selection as an appointment visit reason in the Patient Portal.

### Task : Create a new Practitioner's schedule

In this task, you'll configure the practitioner's schedule to allow patients to book appointments with them in the Patient Portal.

1.	While on [Power Apps](https://make.powerapps.com/), on the left navigation pane, select **Tables**.

2.	In the right pane, select **All** tables.

3.	Use the search box in the upper right corner to search for the string **schedule**.

4.	Select the **Schedule** table. and click on **Edit**.

**Note**: Select the Schedule table with the Name - **msemr_schedule** 

5.	In the **Schedule columns and data** section, select the dropdown to add an existing column to the editable view. Search for **Active** and then select Active to add the column. You may also remove the columns that have no data. Select **Save**.
 
6.	Select **Alex Johnson schedule** under the **Name** column and then change the value of **Active** column from **No** to **Yes**. You may need to scroll right in the grid.
 
You've enabled a practitioner's schedule to be used for booking virtual appointments.

## Task: Configure slots for appointments

In this task, you'll configure a new appointment slot to show practitioner's availability. This configuration will allow patients to select an available appointment time slot when booking with a practitioner. Enable Reed's practitioner, Alex Johnson, to be available today at a set time for virtual appointments.

1.	Go to [Power Apps.](https://make.powerapps.com/)

2.	Select **Apps** on the left navigation.

3.	Select **Virtual Clinic** app in the right pane. Click on **Play** button to launch the app.

4.	select **Schedule** on the left navigation pane under administration

5.	Select the Alex Johnson schedule from the **Active Schedules** list.
 
6.	Scroll down to the bottom of the page. Select **+ New Slot** under **Associated slots**

7.	Fill in the following details in the **New Slot** form and select **Save & Close**.

    1.	**Name** - Alex Johnson Slot

    2.	**Start** - Today, at a later time

    3.	**End** - Today, an hour after the Start

    4.	**Schedule** - Alex Johnson schedule

    5.	**Status** - Free

    6.	**isVirtual** - Yes

    7.	**Specialty** - General Medicine (the practitioner specialty record you created)

    8.	**Service** **Category** - General Medicine (same as specialty)

    9.	Select **Save and Close**

You've created a new virtual slot for Reed to book with the practitioner, Alex Johnson.

### Task : Configure Mapped System User on Practitioner Record

In this task, you'll configure the Mapped System User field on the Practitioner record. This field should be set to the system user that maps to the contact record. Set this field to our logged-in user record.

-   In the case of virtual appointments, the Teams meeting is created on the mapped user’s calendar.
-   In the case of instant virtual appointments, the Teams meeting is created on the Organizer (organizer email for virtual appointments) specified in the Admin settings.

1.  Launch the Healthcare Administration app from power apps. Select **Practitioners** on the left navigation pane.

2.	Select the **Alex Johnson** record and select **Edit**.
  
3.	In the **Summary** tab, select your logged-in user as the **Mapped System User.** Select **Save & Close.**

**Note** – If you get any window for duplicates. Please ignore and save.

You've mapped the practitioner record to your logged in user so that you can accept the video call when the patient has a virtual visit.

## Task: Enable cloud flow

In this task, you’ll create connection references and enable the cloud flow for virtual care.

1.	While signed into your Microsoft 365 tenant, open a new tab, go to [Power Apps.](https://make.powerapps.com/)

2.	Select **Solutions** and then select **+ New Solution.**

3.	Use the below information to create a new solution and select **Create**.

    o	**Display name** - Lamna Healthcare

    o	**Name** - LamnaHealthcare

    o	**Publisher** - CDS Default Publisher
 
4.	On the Lamna Healthcare solution page, select **+ Add existing** and then select **Cloud flow** under **Automation**.
 
5.	On the **Add existing cloud flows** page, select **CF -> Schedule Teams Meeting for instant and virtual, update record with url and status to booked** and select **Add**.
 
6.	Select the cloud flow. Select **Details** dropdown and then select **Details** in a new tab.
 
7.	Select **Edit** on the cloud flow page.
 
8.	Select **Sign in** for **Microsoft Dataverse** and **Office 365 Users** connectors to sign in with the currently logged-in user and create a connection reference.
 
9.	Select **Continue**.
 
10.	Select **Save** to commit your updates.
 
11.	After the flow is saved successfully, select the **Back arrow** to return to the flow’s main page.

12.	The status of the flow is **Off**. Select **Turn on** to enable the flow on top-right corner of the page
 
13.	Close the **Power Automate** tab to go back to Lamna Healthcare solution page and select **Publish all customizations.**

You’ve created connection references to Microsoft Dataverse and Office 365 Users connectors and turned on the cloud flow for creating virtual appointments.


## Exercise 2: Configure Microsoft Teams for Virtual Visits

In this exercise, you will configure integration with Microsoft Teams for Lamna Healthcare Company. Microsoft Teams offers several features useful for hospitals and other healthcare organizations. By integrating Microsoft Cloud for Healthcare with Microsoft Teams, you can improve the collaboration between your care team staff and enhance patient care. You can quickly schedule and conduct virtual visits remotely with patients.

Additionally, your care team can use Microsoft Teams internally to do the following:

-   Chat, call, post messages, and communicate as a team.

-   Store and share files and documents to collaborate.

-   Use Shifts to create, manage, and share schedules among your staff.

### Task : Enable Microsoft Teams Integration

By default, the Basic and Enhanced Microsoft Teams integration is disabled for customer engagement apps in Dynamics 365. In this Task, we will enable Microsoft Teams in Dynamics 365.

1.  Go to [Power Platform admin center](https://admin.powerplatform.microsoft.com)

1.  Select **Environments**. Select your environment. Next, select **Settings**

1.  Select **Integration** and then select **Teams integration settings.**

1.  On the **Microsoft Teams collaboration and chat** page, switch **Turn on the linking of Dynamics 365 records to Microsoft Teams channels** to **Yes**.

5.	Switch **Turn on Enhanced Teams Integration** to **Yes**.

6.	On the pop-up, select the currently signed-in user to grant the necessary permissions.

7.	Select **Accept**.

8.	Switch **Turn on Microsoft Teams chats inside Dynamics 365** to **Yes**, and then select **Save**.

**Congratulations!** You have enabled Microsoft Teams integration for Dynamics 365.

## Exercise : Schedule a Virtual Visit

In this final exercise, you will use the items that you configured in the previous exercises to schedule a virtual visit between Reed Flores and his practitioner, Alex Johnson.

### Task 1: Schedule an Instant Virtual Appointment

In this task, you will log in to the Patient Portal as Reed Flores and schedule an instant virtual appointment.

1.  Go to [Power Apps.](https://make.powerapps.com)

2.  Select **Apps** on the left navigation pane.

3.	Select and open **Healthcare Administration** app by selecting play button.

4.	Select **Patients** app in the left navigation pane.
 
5.	In the right pane, on the **Active Patients** view, select the record **Reed Flores** and then select **Edit**.
 
6.	Select ellipsis (⋮), and then select **Create Invitation** from the pop-up.

7.	Select **Save** on the **New Invitation** form.

8.	Go to the **Advanced** tab and copy the Invitation Code to use on the patient portal.

9.	Go to Power Pages,  Launch your **Lamna healthcare Patient Portal** in Desktop view

10.	Select **Sign in** on the landing page.
 
11.	Go to the **Redeem invitation** tab. Paste the **Invitation Code** you retrieved in the previous task. Leave the box unchecked for returning customer. Select **Register**.
 
12.	Enter a username and password for **Reed Flores**. Something you'll remember. Select **Register**.
 
13.	You may land on the profile page. Select the logo in the upper right to go to the **homepage**.
 
14.	Go to **Appointments** and select **Schedule** **new**.
 
15.	Select **Instant virtual appointment.**
 
16.	Select the **General Medicine** option that you created earlier in the exercise as the reason for the visit.
 
17.	In the **Personal** section, scroll down and select **Next**.

18.	In the **Insurance** section, select **+ Add Insurance.**

**Note** - If you encounter an error when adding the insurance, ensure the environment variables and API permissions are set up as mentioned in the [Configure environment.](https://learn.microsoft.com/en-us/training/modules/training-environment-preparation-healthcare/4a-azure-trial) For more information on these settings, see [Set up and configure a Patient access portal.](https://learn.microsoft.com/en-us/dynamics365/industry/healthcare/configure-portals#known-issue)
 
19.	Fill out the required fields with any information and select **Next**.
 
20.	Select **Next**.
 
21.	**Check the box** for Consent Terms and then select **Join queue.**
 
22.	A new internet browser tab opens and may be blank. **Select the link** provided to join the appointment.
 
You've scheduled an instant virtual appointment using the patient portal.

