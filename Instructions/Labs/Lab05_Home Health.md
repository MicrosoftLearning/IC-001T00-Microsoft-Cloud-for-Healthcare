# Module 4 Lesson 2 Lab 5: Home Health

### Overview

Microsoft Cloud for Healthcare’s **Home Health** application allows provider personnel to schedule appointments for the patient based on a variety of factors. It allows for the communication of the right information, at the right time, to the right people, to provide safe and effective care to your patients. Manage home visit schedules, notify patients, and give access to medical information to the provider on the go.

Key capabilities of Home Health include:

-   **Schedule home visit**: Enable care coordinators to schedule home visit appointments, while viewing patient information directly in context.
-   **Provider scheduling**: View schedules of care team members and optimize visiting routes.
-   **Patient engagement**: Notify patients about upcoming appointments, follow up with patients after a visit, and automatically check with patients between visits.
-   **Home visit coordination**: Coordinate care and support distinct processes and tasks for the home visit.

Home Health focuses on both the **Empower health team collaboration** and **Enhance patient engagement** priority scenarios by creating a system that allows for improved care team coordination with optimized resources and enhanced patient engagement with personalized experiences and home visits.

![Chart Description automatically generated with medium confidence](media/45d491cf8432b9a27508118cffbf4b8c.png)

This lab will focus on the healthcare story of Monica Thomson.

![Timeline Description automatically generated](media/54f29d6f3dc7b9698687890145216753.png)

Monica sprained her knee while ice skating last winter and was prescribed at-home physical therapy by her practitioner to rehabilitate the injury. To facilitate this home care scenario, Lamna Healthcare Company has deployed Microsoft Cloud for Healthcare’s Home Health capabilities.

In this lab, you will play the role of a Lamna Healthcare Company Home Health dispatcher to configure the Home Health application.

### Learning objectives

In this lab, you will:

-   Create a Bookable Resource
-   Configure the Schedule Board
-   Leverage Care Management Components with the Field Service Mobile App

### Step 1: Create a Bookable Resource

In this exercise, you will learn how to create a **Bookable Resource** to be used for scheduling a Home Health Work Order. A bookable resource in the Microsoft Cloud for Healthcare is anything that needs to be scheduled. This most commonly includes people, equipment, and physical spaces (facilities). Bookable Resources must be created before scheduling a Home Health Work Order.

Each resource can have different attributes that distinguish it from others, including but not limited to the following:

-   Characteristics (for example: Accounting)
-   Categories (for example: Manager)
-   Territories (for example: Washington State)
-   Organizational Unit (for example: Seattle Service Delivery)
-   Location (for example: Location Agnostic)
-   Resource Type (for example: User)

Now let’s create a Bookable Resource in the Home Health application.

1.  Navigate to <https://make.powerapps.com/>.
1.  Open the Field Service app.

    ![Open the Field Service app](media/b1a5c43c06384c7a293c57933e5b391a.png)

1.  In the bottom left of the navigation pane, change the area from **Service** to **Resources.**

    ![Change the area from Service to Resources](media/95c251ccd13f8c6659db279af81dec04.png)

1.  This will take you to the Bookable Resources entity. Click **New** on the command bar to create a new **Bookable Resource**.

    ![Click New on the command bar to create a new Bookable Resource](media/57c73f1284ffd4bbc9b4e4e3d6f14b09.png)

1.  Select **Resource Type**. A Resource type is a classification that describes who or what the resource is and how the resource relates to your organization. In this case, select **User**, who is a person and a member of your organization and needs access to the Field Service Mobile app.

    ![Select Resource Type](media/06b3cbe9c8ae58066483399b36f73b10.png)

1.  Pick your training **User** and select your **Time Zone.**

    ![Pick a User and select their Time Zone](media/912185bb5ef9ce22d4b6ace29c5dd887.png)

2.  Click **Scheduling** to decide where the resource starts and ends his or her working day for scheduling and routing purposes. There are three options available when selecting the **Start/End location** for the Bookable Resource:
3.  
-   **Location agnostic** - select this option if the location of this resource is not required for the business need and does not need to be considered during the scheduling process. Note that if the work location of a requirement is set to on site, location agnostic resources will not return in results.
-   **Resource Address** - select this option if the resource starts and ends his or her day at a unique location. The exact location is derived from the latitude and longitude values on the related user, account, or contact records depending on the resource type.
-   **Organizational Unit** - select this option if the resource starts and ends the day at an organizational unit, typically representing a company location.

    In this case, choose **Location Agnostic**.

    ![Choose Location Agnostic](media/2b5b3e9699b5070a0d21a1a29bd69ffb.png)

1.  Click the **Field Service** tab to optionally configure any other aspects of the Bookable Resource.

    ![Chart, scatter chart Description automatically generated](media/6dfa2885a17d20b8036d2ffc496f0eb5.png)

1.  **Save** the record.

    ![Graphical user interface, text, application, chat or text message Description automatically generated](media/771a887f4633174c726ae60b9363f7f7.png)

1.  After **saving** the bookable resource, it's time to set the **working hours** of the resource. Working hours are considered by the following:
-   The schedule board by displaying working and nonworking hours as different colors.
-   The schedule assistant by only displaying resources that are working in the result.
-   Resource Scheduling Optimization, which automatically books requirements to resources that are working.

    Click **Show** **Work Hours** on the command bar:

    ![Click Show Working Hours on the command bar](media/151ca48127d9a991bf68c921af5e568e.png)

1.  Click +New -\> Working hours.

    ![Click +New -\> Working Hours](media/181a12785dcac45bb27f8e71faddf1b0.png)

1.  Choose **date** you want the working schedule to begin on, the beginning and end **time** of working hours (such as 8am to 5pm), along with a **repeat** option such as "every day” and then click off Sunday and Saturday. Click **Save**.

    ![Choose date you want the working schedule to begin on, the beginning and end time of working hours (such as 8am to 5pm), along with a repeat option such as "every day” and then click off Sunday and Saturday.  Click Save](media/6a0c710657f66aa08b28beb4c782e253.png)

1.  Go back to the General tab. If the bookable resource has specific skills, you should add them now. To create a **Resource Characteristic**, go to the subgrid on the form and select **+New Bookable Resource Characteristic** from the command menu.

    ![Go back to General and create a Resource Characteristic by selecting +New Bookable Resource Characteristic](media/4addb5bc71276945cbf404f5282b0573.png)

1.  In the **Skill Name** field, click the magnifying glass and select **+New Characteristic.**

    ![Graphical user interface, text, application Description automatically generated](media/9e47dbcc38923b1358bce279553da777.png)

1.  A quick create form for Characteristic will appear. We want to assign a characteristic to the bookable resource. In this case, the user can speak Spanish fluently. Therefore, type “**Spanish fluency**” for the characteristic **Name** and click **Save & Close.**

    ![Graphical user interface, text, application Description automatically generated](media/74797c398cdc9bdf884e028a8988a3eb.png)

1.  Back on the Bookable Resource Characteristic quick create form, the Skill Name should be populated with the new Spanish fluency characteristic. Click **Save & Close**.

    ![Graphical user interface, text, application, email Description automatically generated](media/819dac43a33e1309360befe3e8c19655.png)

Note: Characteristics represent a resource's skills and certifications. This could be concrete, like a CPR certification; more general, like accounting or web development experience; or as simple as security clearance for a specific building or fluency in the Spanish language.

1.  If you’d like more data in the system, you may create **two** more **Bookable Resources** following the same process. For each of them, select **Contact** as the **Resource Type** and choose any Contact in the system. Choose **Location Agnostic** just as before and click **Save**. Configure the **Work Hours** the same as the previous Bookable Resource and click **Save & Close**.

**Congratulations**! You have created a Bookable Resource. In the next task, we will use this bookable resource to help configure the Schedule Board. For more information on bookable resources, see [Set up bookable resources (Dynamics 365 Field Service) \| Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/field-service/set-up-bookable-resources).

### Step 2: Configure the Schedule Board

In this exercise, you will configure the schedule board for the **Bookable Resource** created in the previous task. The schedule board provides an overview of resource availability and bookings you can make. Before you use the schedule board, it is important to set up the views and filters to your preference. To use the schedule board booking functionality, geocoding, and location services, you need to turn on maps.

Here is an example of a configured **Schedule Board**:

![Screenshot of a configured Schedule Board in Home Health application](media/aeacbb4f554003cb9c42aa839388a71f.png)

1.  Navigate to <https://make.powerapps.com/>.
1.  Open the Resource Scheduling app.

    ![Open the Resource Scheduling app](media/9ad0ae5cb7830f6f7074c10313a4ac56.png)

1.  Change the area in the bottom left navigation drop down from Resource Scheduling to **Settings.**

    ![Change the area to Settings](media/87279fa1881a42a05db9c8e1da84d81e.png)

1.  Click **Administration** on the site map**.**

    ![Click Administration](media/f04c55dd887897948a1f82c89f8bc9d0.png)

1.  Select Scheduling Parameters.

    ![Click Scheduling Parameters](media/f63619719cf902b97ebc6e55ca63a4fc.png)

1.  Set “**Connect to Maps**” to **Yes**. Then click **OK** to accept the terms. If it is already set to yes, you can skip this step.

    ![Change “Connect to Maps” to Yes ](media/4cbdb340e4a282e077dda43e73eef342.png)

    ![Click OK to accept the terms](media/ecd54790de6f4377d6d0cf53f887c55f.png)

1.  Click Save & Close.
2.  
3.  Open the Home Health app.

    ![open the Home Health app](media/bb83b5144e3bb88e1a933e92793973d5.png)

Now we will associate the Thomson Household home care work order with the Spanish fluency characteristic, so they match Monica with someone who is fluent in Spanish. We have already applied this characteristic to her practitioner. We also want to set the estimated duration for the home visit.

1.  Click **Home Care** on the left sitemap and open the Home Care Work Order record number **00034** associated with the **Thomson Household**.

    ![Graphical user interface, text, application, email Description automatically generated](media/870340179b05ade4bc62518074ac8f59.png)

1.  On the Summary tab, scroll down to the Primary Incident section and set the **Primary Incident Estimated Duration** to 1 hour (this will ensure that the work order takes up time on the Resource’s calendar).

    ![Graphical user interface, text, application, email Description automatically generated](media/6a0f0f32186542789d541366d0315f92.png)

1.  Click **Related** and then click **Characteristics**.

    ![Graphical user interface, application Description automatically generated](media/9d27c5a0e12148357743819ecf94a783.png)

1.  Click **+ New Requirement Characteristic**.

    ![Graphical user interface, text, application Description automatically generated](media/3333a3c57c1fd92bd21e73b14969d43f.png)

1.  Choose “**Spanish fluency**” for the **Characteristic** and Work Order **00034** as the **Resource Requirement**.

    ![Graphical user interface, text, application, email Description automatically generated](media/b2340c112dfc1d7dd3e1325f484e8202.png)

**Important**: Make sure the **Work Order** number populated in the **Resource Requirement** field on the general tab matches the Work Order number on the **Field Service** tab on the Resource Requirement record.

![Graphical user interface, application Description automatically generated](media/e99ce9b925e5d9f9925113d40f719d0d.png)

1.  Click **Save & Close**. You will now see the new characteristic requirement in the subgrid.

    ![Graphical user interface, text, application Description automatically generated](media/f0e96545df55391a166842653a59fb05.png)

1.  Now let’s configure the schedule board. Select **Schedule Board** on the left site map.

    ![Click Schedule Board](media/fc1c9bf18ae93e0bf5f47935aaf0684a.png)

1.  Click the **plus button (+)** in the upper right corner to create a new **Schedule Board tab.**

    ![Click the + button to create a new Schedule Board tab](media/96f93675be2ede04b25fbcfa0e0f20b1.png)

1.  Name the new Schedule Board tab “**My Schedule Board Tab**”. Leave all defaults and click **Add**.

    ![Graphical user interface, application Description automatically generated](media/319c3cd7e3c8273689bad5e9687d81d4.png)

1.  Click on the Scheduler Settings **gear icon.**

    ![Click on the Scheduler Settings gear ](media/2a9c3de563a10ebdf690081a9b070f13.png)

1.  Change the Hours view to be closer to typical working hours, such as 6am to 6pm.

    ![Change the Hours view to be closer to typical working hours, such as 6am to 6pm](media/5c7cfa078bf08c50d5ce5340c7fed871.png)

1.  Open the Unscheduled Work Orders by selecting the small arrow at the bottom of the screen.

    ![Graphical user interface, application, table, Excel Description automatically generated](media/d05a532231b5800ab460033648e7c25b.png)

1.  Select the **Unscheduled Work Orders** tab. Find work order **00034** where you added the **Spanish fluency** characteristic and click the grid to highlight it. Select **Find Availability** to open the Schedule Assistant filter.

    ![Graphical user interface, application Description automatically generated](media/78dea84161b4a04573e5e0b6740fd19b.png)

1.  Notice that any Bookable Resources which do not have the “Spanish fluency” characteristic are dropped from the search. Click the **Book** button on the Bookable Resource’s schedule to schedule the work order.

    ![Graphical user interface, text, application Description automatically generated](media/195879ec181adb6613e5b3fe19468cb1.png)

1.  The work order is now scheduled and will no longer show in the Unscheduled Work Orders grid. The Resource Optimizing tool will schedule it for the next available time. Click **Exit Search** to close the pane.

    ![The work order is now scheduled and has disappeared from the bottom grid.  Click Exit Search to close the pane](media/9112a5b430ee7da1881def66e34086a6.png)

**Congratulations**! You have configured a Schedule Board tab and scheduled a Home Health visit using the bookable resource you created in the previous task. For more information on schedule boards, see [Use and configure the schedule board (Dynamics 365 Field Service) \| Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/field-service/configure-schedule-board).

### Step 3 – BONUS : Leverage Care Management Components with Field Service Mobile App

In this exercise, we will walk you through the **Field Service Mobile App** and demonstrate how to leverage **Care Management** components from the perspective of a Nurse or a Physical Therapist out in the field working with a patient. We will explain the installation process, how to set up **Home Health** users and security profiles, and how to use the mobile app to complete work orders.

[The Field Service (Dynamics 365) mobile app](https://docs.microsoft.com/en-us/dynamics365/field-service/mobile-power-app-overview) is designed and optimized for mobile health workers to view Dynamics 365 Home Health work orders and patient information. This mobile app is **built on Microsoft Power Platform** and is customizable to your business needs with the same admin console as all Dynamics 365 business apps.

It is available natively for Apple iOS and Google Android phones and tablets, the Field Service (Dynamics 365) mobile app offers technicians many capabilities they need to perform onsite customer service, such as the following:

-   A calendar view of assigned jobs
-   Support for picture, video, and asset barcode scanning
-   Customer signature capture
-   Offline capabilities so mobile health workers can continue viewing and recording work in areas without internet

Here is a calendar view of scheduled work orders:

![Graphical user interface, application Description automatically generated](media/2e5e9db963ab6d530418845ade450cf6.jpeg)

**Task 1: Assign Security Roles to Field Service Mobile Users**

In this task we will assign the Field Service – Resource role to Home Health workers.

1.  Navigate to <https://make.powerapps.com> in your incognito window.
1.  Click the **gear icon** in the upper righthand corner and go to **Advanced Settings**.

    ![Graphical user interface, application Description automatically generated](media/26d7f778f6db24083fd5f0fc77101de9.png)

1.  You will be navigated to the classic view. If it takes a while to load, refresh the page.

    ![Graphical user interface, text, application Description automatically generated](media/285d4a3caa05eeb169876c5d44c11624.png)

1.  Click **Settings** on the top command bar and then in the flyout menu choose **Security**.

    ![Graphical user interface, application, website Description automatically generated](media/9e2e1cfb3cfdc3e00849d1e1938e66da.png)

1.  Click **Users**.

    ![Graphical user interface, text, application, email Description automatically generated](media/9aa374708ca8db47660463e546249b76.png)

1.  Select the view drop-down and change the view to show “**Enabled Users**”.

    ![Graphical user interface, text, application Description automatically generated](media/9ff0176dc324515b5652585ebebd844b.png)

1.  Find and select the user whom you would like to assign the “Field Service – Resource” role. Select **Manage Roles** on the command bar.

    ![Graphical user interface, text, application Description automatically generated](media/f5571d213e2744cb9a522827de51773e.png)

1.  Scroll down to select the “**Field Service – Resource**” security role and click OK.

    ![Graphical user interface, application, table Description automatically generated](media/0328b9e0b0c4d0fa928a84b7efe8e321.png)

**Congratulations**! You have assigned the Field Service – Resource role to a Field Service Mobile Home Health user in the Microsoft Cloud for Healthcare.

**Task 2: Download the Field Service Mobile app and sign in**

In this task, we will walk through how to download the Field Service Mobile app to an iOS or Android device and sign in.

1.  Go to the app store on your iOS or Android device and search for Dynamics 365 Field Service.
1.  Download the app called **Field Service (Dynamics 365),** as seen in the following screenshot. It is the mobile application built on the Power Platform.
1.  Launch the app and sign in with the Microsoft Cloud for Healthcare username and password for the user that you assigned the “Field Service – Resource” security role to in the previous task.

    ![Graphical user interface, application Description automatically generated](media/fd954522fc93ff4e89e6fa3adf204cfa.jpg)![Graphical user interface, text, application, chat or text message Description automatically generated](media/e8b070c9401384ce23dde2a47e69dd4f.png)

**Congratulations**! You have downloaded and signed into the Field Service Mobile as a Home Health user in the Microsoft Cloud for Healthcare

**Task 3: Use the Field Service Mobile app to manage Home Health Work Orders**

In the last exercise, we assigned **Home Health Work Order** 00034 to our Home Health Bookable Resource. We will now view and make updates to the work order in the Field Service mobile app, and then view those changes in the Microsoft Cloud for Healthcare Home Health app.

1.  On your mobile device, log into the Field Service Mobile App as your Bookable Resource user. If you encounter a message that says “Contact your administrator for access to your organization’s mobile apps”, select the menu icon in the top left and **toggle Show non-production apps to Yes**.

    ![Graphical user interface, application Description automatically generated](media/9a5550e99f9452a0bd2fc1167ec305cb.png)![Graphical user interface, application, Teams Description automatically generated](media/b72140bc6e194e5f30a4dfcba11d72ac.png)![Graphical user interface, application, Teams Description automatically generated](media/e4d773ccab2f6e32d22cb313d85f6faa.png)

1.  In the list of environments, **find the Microsoft Cloud for Healthcare environment** that you have been working in. You will find the Home Health Work Order in the calendar view in an “**In Progress**” state.

    ![Graphical user interface, application Description automatically generated](media/9877ab5409479e5a37e06c419e4dc40e.png)

1.  **Click to open** the Work Order. Notice the Booking Status says **In Progress**. Expand the status field using the blue arrow in the upper right. Click the **magnifying glass** next to the status field to modify the value.

    ![Graphical user interface, application Description automatically generated](media/236f05ee83a34f4b146c0d7c71613b01.png)![Graphical user interface, application Description automatically generated](media/f45d26ce6b69d27a0b2f8f0ac9099be2.png)

1.  **Remove** In progress from the selected values by clicking the x next to it.

    ![Graphical user interface, application Description automatically generated](media/fe5149ab79fe7715ab06602c378cf0c0.png)![Graphical user interface, text, application, chat or text message Description automatically generated](media/1b5d968705fbc93319a405827d0361b6.png)

1.  Set the **Booking Status** to **Completed** to close the Work Order. Click **Save** in the upper right.

    ![Graphical user interface, text, application, chat or text message Description automatically generated](media/88234ac2354b631f88825427c02c62f6.png)![Graphical user interface, application Description automatically generated](media/ac17e377cdf7e66cc9447e14a95f4bf6.png)

1.  The Work order has been completed and the time values have reflected based on the start time and when we completed the order. We are now finished with the mobile app.

    ![Graphical user interface, application Description automatically generated](media/7b07e14bda3da47cab31084a8f7bf61b.png)![Graphical user interface, application Description automatically generated](media/7038371b29c0b298e93fd72388d413df.png)

1.  Navigate back to the **Home Health app**. You’ll see on the **schedule board** the work order has been updated to show the reflected time and status.

    ![Graphical user interface, application Description automatically generated](media/3cb76fabb19cc0c3148ffc5db983cdb5.png)

1.  Click **Home Care** on the site map and find **Work Order 00034**. You will see that the **System Status** has been updated to “Completed”.

    ![Graphical user interface, text, application, chat or text message Description automatically generated](media/1815d724599e1253ad7dabb657008321.png)

    ![Graphical user interface, text, application, email Description automatically generated](media/da0c30550746d4d1719b3ec421857302.png)

**Congratulations!** You have assigned a Home Health Work Order to a Home Health Bookable Resource, made updates to the work order in the Field Service mobile app, and then viewed those changes in the Microsoft Cloud for Healthcare Home Health app. For more information on the Field Service mobile app, see [Install and set up the Field Service (Dynamics 365) mobile app \| Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/field-service/mobile-power-app-get-started).

