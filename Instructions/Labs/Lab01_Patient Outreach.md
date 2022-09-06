Module 4 Lesson 1- Lab 1: Patient Outreach
==========================================

### Overview

The **Patient Outreach** application in Microsoft Cloud for Healthcare allows
healthcare providers to communicate with their communities and patients in a
targeted, efficient way. Patient Outreach is a patient campaign management
application that helps you organize and automate marketing and outreach to
patients.

Key capabilities of **Patient Outreach** include:

-   Patient segmentation - Prebuilt patient segments are based on the industry
    standard Healthcare Effectiveness Data and Information Set (HEDIS) to
    provide baseline patient cohorts.

-   Patient engagement campaigns - Create healthcare-specific email campaigns
    that use patient segments based on the HEDIS industry standard.

-   Event management - Use provider and payer event management templates for
    event administration and registration.

Patient Outreach focuses on the **Enhance patient engagement** priority scenario
by creating personalized communication based on patient insights.

![Graphical user interface Description automatically generated](./IMAGES/L1P1.png)

This lab focuses on the healthcare story of Elizabeth Moore.

![[Timeline Description automatically generated](media/6ec25178faea7cdb8abc9ae2bf891354.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P2.png)

At an annual checkup earlier this year, Elizabeth learned that she has
hypermetropia, a common eye condition in adults in which nearby objects are
blurry. Lamna Healthcare Company has seen a recent influx of patients who want
to be more educated on hypermetropia and has decided to increase their patient
outreach efforts by hosting a virtual marketing event.

In this lab, you will play the role of a Lamna Healthcare Company marketing
administrator and will use the Patient Outreach capabilities in Microsoft Cloud
for Healthcare to create a virtual marketing event.

### Learning objectives

In this lab, you will:

-   Create a patient segment.
-   Create a marketing email.
-   Create a patient journey.
-   Create a healthcare marketing event.

### Step 1: Create a Patient Segment

In this exercise, you will create a Patient Segment using the Patient Outreach
app in Microsoft Cloud for Healthcare. A **Patient Segment** is used to group
patients into cohorts based on similar characteristics so that they can be
better targeted with marketing communications. In this example, you will create
a Patient Segment for patients with hypermetropia (a vision condition in which
nearby objects are blurry).

1.  While logged into your Microsoft 365 tenant, navigate to
    <https://make.powerapps.com/>.

2.  Go to **Apps** and open **Marketing**.

![[Graphical user interface, text, application, email Description automatically generated](media/0c80e4c5c760423b6d4e4e2abda03e06.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P3.png)

1.  Navigate to the bottom left drop-down and change the selection from
    **Marketing** to **Settings**.

![[Graphical user interface, text, application Description automatically generated](media/e72fa56c5f3c9527b0b0e58dbf7e4fc6.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P4.png)

1.  On the **Settings overview** screen, select **Dataset configuration** under **Data
    management**.

![[Graphical user interface, application Description automatically generated](media/8018d431e68878191fbd44f227ab6dbc.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P5.png)

1.  Scroll down and select the **Condition (msemr_condition)** entity.

![[Graphical user interface, text, application Description automatically generated](media/330743414440f627a1f4255c263b1b45.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P6.png)

1.  **Publish Changes** on the top right.

![[Publish Changes.](media/077c825edf16384e8cfe22ed35173493.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P7.png)

Note: While it may take up to 30 minutes for changes to take effect, they are generally ready in a few minutes.

1.  Go back to **Apps** and open **Patient Outreach**.

![[Graphical user interface, text, application, email Description automatically generated](media/756d685076162bd7b183689ddf2c3d67.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P8.png)

1.  Click **Segments** on the left navigation bar to create a new specific group of patients.

![[Click Segments to create a new specific group of patients.](media/e48936f82e9265eb2f56ab8a968aa15f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P9.png)

1.  Click **New** to create a new Patient Segment. Select **+ New Dynamic Segment**.

![[Click New to create a new Patient Segment. Select + Dynamic Segment. ](media/2e14944f52f2405cd8d880626adc2886.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P10.png)

Did you know? Static segments enable you to choose and add segment members manually based on existing lists or search results. Dynamic Segments, which you define by using a set of rules and conditions, are constantly and automatically changing based on information in your database. Since we want our group to change depending on database information, we are choosing the dynamic segment option.

1.  When prompted to choose a **Segment Template** option, click **Skip** since we will create our own Segment.

![[Graphical user interface, application Description automatically generated](media/8836f85b428d1f8643dfa2ec92798483.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P11.png)

1.  Name the new Segment **Patients with Hypermetropia**. Select **Add query block.**

![[Name the new segment "Patients with Hypermetropia"](media/bed72c718ece1a4d43ce46e0a30ea54a.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P12.png)

![[Graphical user interface, text, application, email, Teams Description automatically generated](media/3d9cfc2c4084728e90d9da89ee2b1327.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P13.png)

1.  We will now create a new Segment for Active Patients who have a Hypermetropia condition where the Contact has a Status of Active, and the related Condition Description contains “Hypermetropia”. Configure this new segment by doing the following:

    1.  Leave **Contact** as the main entity.

    2.  In the attribute drop-down, select **Status** from the list of fields.

    3.  When the additional fields appear, set condition to Status **Is Active**.

    4.  Click **Add > Add related entity**.

![[Graphical user interface, text, application Description automatically generated](media/ff2da8f66ed1224f9becf605992b852d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P14.png)

1.  It should default to **AND** in the drop-down. Now let’s add the second part of the condition.

2.  In **Select related entity** drop down, choose **Condition (Condition -\> Contact (Patient))**.

3.  Click the nested **Add > Add condition to Condition**.

![[Graphical user interface, text, application, email Description automatically generated](media/de65a23fcb8bd5d9911eec87e9d81336.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P15.png)

1.  Select attribute Condition (msemr_name).

2.  Change the operator to **Contains** and type **Hypermetropia**.

![[Graphical user interface, text, application Description automatically generated](media/016344261ae2303d7040022ed2d55fa1.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P16.png)

1.  Select **Save** and then select **Go live** to publish the segment (you won't be able to use it in a customer journey until it goes live, even though you've saved it).

![[Select Save and then select Go live to publish the segment (you won't be able to use it in a customer journey until it goes live, even though you've saved it).](media/18bef382e7318fb6a8c07c6dade833e3.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P17.png)

1.  Select **Refresh** on the command bar to refresh the page. Select the **Members** tab to see which patients have been added to the Dynamic Segment. Notice Elizabeth Moore in the list who will eventually be a recipient of our marketing event outreach email.

![[Graphical user interface, text, application, email Description automatically generated](media/bc651fc36c2e87f121023f3a4e4ba2f2.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P18.png)

**Congratulations**! You have completed the steps to create a patient segment that groups together contacts with hypermetropia. This patient segment will be used in the next set of tasks. For more information about dynamics segments, see [Create a dynamic segment (Dynamics 365 Marketing) \| Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/marketing/create-segment). For more information about segments in general, see [Working with segments (Dynamics 365 Marketing) \| Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/marketing/segmentation-lists-subscriptions).

### Step 2: Create a Marketing Email 

In this exercise, you will create a marketing email that will be used to reach out to the patient segment you created in the previous exercise. Marketing emails are used to directly communicate with the patients that reside in a particular patient segment.

1.  In the **Patient Outreach** app, scroll down to **Marketing Execution** in the left navigation pane and click **Marketing emails.**

![[Click Marketing emails](media/0cb9d30217f56133063365da32c1d11d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P19.png)

1.  In the **Active marketing emails** view, open **Email invitation – Free Diabetes Prevention Event**.

![[Graphical user interface, text, email Description automatically generated](media/50a48c0fa76e0b54fd77ce08f12bd97f.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P20.png)

1.  Click **Save** on the command bar and then **Save as**.

![[](media/32641d7a42361b57123fde2fb3a13bae.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P21.png)

1.  Change the **Name** of the event to **Email Invitation – Healthy Eye Seminar Virtual Event** and the **Description** to **Healthy Eye Seminar Event**.

![[Text Description automatically generated](media/0a1fb441ae38e93ef754394a53dcf9ea.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P22.png)

1.  Click **Save and Close**.

![[Text Description automatically generated](media/0a1fb441ae38e93ef754394a53dcf9ea.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P23.png)

1.  Navigate back to **Marketing** emails list and select your newly created segment **Email Invitation – Healthy Eye Virtual Seminar**.

![[Graphical user interface, text, application, email Description automatically generated](media/3661e393cd87565ceb425e7b20322c29.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P24.png)

1.  Click the image in the Designer.

![[Graphical user interface, website Description automatically generated](media/236f1e0966ef31f8e1c8228425929be2.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P25.png)

1.  Hover over the image in the **Edit image** pane and click **Replace**. Click **Upload to library**.

![[Graphical user interface, application, PowerPoint Description automatically generated](media/f1a9210228a8475edeb61517599dde5c.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P26.png)

1.  Right-click the image below and save as **Glasses.jpg**.

![[A pair of glasses on a book Description automatically generated with medium confidence](media/5f173bc3cf175c1adfd135a43c783ffc.jpg)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P27.png)

1.  Select **Add files**.

![[Graphical user interface, application Description automatically generated](media/6d7dd3f3a9151bbe236def29bdc51191.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P28.png)

1.  Find and select the file **Glasses.jpg** which you just saved. Click **Upload**.

![[Select the “Glasses.jpg” image from the [file location], click Upload, then click Done](media/4cab8f99af9ef5b8c3971effab2eebcd.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P29.png)

1.  Select **Done**.

![[Graphical user interface, text, application Description automatically generated](media/23d75f573d107d99712b8a40063f4e0d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P30.png)

1.  Edit the text of the email as follows:

    1.  **Date**: Pick a date in the future
    2.  **Headline**: Healthy Eye Seminar
    3.  **Description 1**: Hi, {{contact.firstname}}! You are invited to Lamna Healthcare’s Healthy Eye Virtual Event.
    4.  **Description 2**: Come join us at this virtual event!

![[Graphical user interface, text, application Description automatically generated](media/23d75f573d107d99712b8a40063f4e0d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P31.png)

1.  Edit the **footer** text of the email so that it reads **©2022 Lamna Healthcare Event.** Do not edit the dynamic text below it.

![[Graphical user interface, application Description automatically generated](media/92575fd2e9a87d19b06909bacb648e68.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P32.png)

1.  Click **Save** on the command bar and then click **Go live** so that the marketing email is available for use.

![[](media/dbd246cd45618455707020cd2d79fe9d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P33.png)

**Congratulations**! You have completed the necessary steps to create a marketing email for patient outreach. This marketing email will be used in the
next set of tasks. For more information on creating marketing emails, see [Create a marketing email (Dynamics 365 Marketing) \| Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/marketing/create-marketing-email).

### Step 3: Create a Patient Journey

In this exercise, you will create a Patient Journey for the patient segment that you created in the first exercise. A **Patient Journey** can expand your
organization’s patient outreach marketing capabilities by helping healthcare organizations guide the members of a selected segment through the communication process. It does this by using automated messaging, activity generation, interactive decision points, and more.

Here is an example of a configured **Patient Journey**, which focuses on the Patient Activation Measure segment group and sends them a marketing email after a 3-month waiting period.

![[Patient Journey selected on site map](media/1f6cd3035cdd8840461ff082633bb855.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P34.png)

Now let’s make our own customer journey for patients with hypermetropia.

1.  In the **Patient Outreach** app in <http://make.powerapps.com/>, click **Patient journeys** under **Marketing execution** on the Site map.

![[Graphical user interface, text, application, chat or text message Description automatically generated](media/35f929d4098bff810c57882ddf0ea8de.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P35.png)

1.  Click **New** to create a new Patient Journey.

![[Click New to create a new Patient Journey](media/00748ef156fabf2a3a4d58d11af6d2aa.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P36.png)

1.  When prompted to choose a **Customer journey template** option, click **Skip** as we will create our own customer journey.

![[Click Skip as we will create our own customer journey](media/cff77ed4b74b5b0f63f5cac408ed8bb3.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P37.png)

1.  In the **Designer** view under **Who do you want to be on this journey?**, select the plus sign to **Set audience.**

![[New customer journey screenshot](media/950b2c345861ab6ba5ea082a6cf623b0.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P38.png)

1.  In the **Audience** panel that shows on the right, **search** for the **Patients with Hypermetropia** segment that you created in the previous task.

![[Find the “Patients with Hypermetropia” segment that you created in the previous task](media/28b85d67fb830639b7af441c4cb08f85.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P39.png)

1.  Select “**Patients with Hypermetropia**” for the source segment.

![[select “Patients with Hypermetropia” ](media/23624d08867f764e1e2e9fdfb0399e68.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P40.png)

1.  Click the **General** tab and rename the record to **Healthy Eye Seminar**. Click **Save**.

![[Name the record Healthy Eye Seminar](media/cb53a8ba2bbddb26d72450dbffa4cc7a.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P41.png)

1.  Go back to the **Designer** tab. On the canvas between the gray arrows after the starting box, select the blue plus sign (**+**) that appears when you scroll over the line.

![[Add button appears in designer tab](media/360ac702f2eb1f0d43e4a9429a2ec4b3.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P42.png)

1.  Select **Send an email** from the contextual menu.

![[select Send an email from the contextual menu](media/71589db06379eae22149949f2f364fc0.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P43.png)

1.  In the panel on the right for the **Email** field, select the marketing email **Email Invitation – Healthy Eye Seminar**” that you created in the
    previous exercise.

![[Customer Journey Designer View to select an email](media/694f520cda16b8cd338d67c856186663.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P44.png)

![[Select the “Email Invitation – Healthy Eye Seminar” email that you created in the previous task](media/32fc70058101117b29ad6cd15875260d.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P45.png)

1.  Click **Save.**

![[click save for customer journey](media/abb79ae8383fef52a15c914de75da4cc.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P46.png)

1.  Switch to the **General** tab to configure the run schedule for your customer journey. Enter a **Start and End** date and time that makes sense
    for your event. If you want to see insights for the journey, choose an upcoming **Start time** on today’s date. Remember the dates you enter for the
    next exercise.

![[Graphical user interface, application Description automatically generated](media/a25f05b4fff7e1ef0fcdd658cf2011dd.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P47.png)

1.  Click **Save**.

2.  Your journey is now ready to go. To start the journey, navigate back to the **Designer** tab and publish it by selecting **Go live** on the command bar.

![[select go live on the command bar](media/de5ed776db0ab62e5f41632dd51feeb2.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P48.png)

1.  Dynamics 365 Marketing copies the journey to its email marketing service, which executes the journey by processing contacts, performing actions, and collecting results during the time it is set to run. Watch the journey's **Status Reason** as it sequences through **Going Live** to **Live**.

![[Your journey is now ready to go. To start the journey, publish it by selecting Go live on the command bar](media/40d5926277e159ebcfcfc164a741f4b3.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P49.png)

1.  Once your patient journey runs, you will be able to gather **key metrics and insights** from the record. When this information is available depends on the date and time you chose for the start of the customer journey. You may come back to see the results later if they aren’t yet available.

**Congratulations**! You have created a patient journey by utilizing the patient segment and marketing email you created in the previous exercise. For more information on patient journeys, see [Create a simple customer journey (Dynamics 365 Marketing) \| Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/marketing/create-simple-customer-journey).

### Step 4: Create a Virtual Healthcare Educational Event

In this exercise, you will create a healthcare-focused, virtual educational **Event** corresponding to the patient journey you created in the previous exercise that sends the Healthy Eye Seminar event invite to everyone in the patient segment. The **Marketing Event Management** feature helps you every step of the way, from initial planning and budgeting through promotion and publication, attendee registration, webinar broadcasting, final analytics, lead generation, and evaluation of ROI.

1.  In the **Patient Outreach** application, click **Events** on the **Site Map** under **Event Management**.

![[Click on Events on the Sitemap](media/d9eaffe3517cf97f5953775396a879f3.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P50.png)

1.  Select **New** on the command bar to create a new event.

2.  Enter details for the New Event. Enter **Event Name** as **Healthy Eye Seminar** and enter the same **Schedule details** as you entered for the Marketing email in the previous exercise. Familiarize yourself with the other fields on the forms as part of the Preliminaries event stage.

![[new Event record](media/af57c80f2a746549154af5e6a4afb078.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P51.png)

1.  Click **Save**.

2.  Since this will be a virtual event, in the **Stream This Event Online** section, toggle “**Do you want to stream this event**” to **Yes**.

![[Select Yes to stream the event online](media/2c517683a531aefa31bb6974004659dd.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P52.png)

![[Graphical user interface, application Description automatically generated](media/54a8cc2efcf02bae679920ca1508b487.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P53.png)

1.  In the **Business Process Flow**, select the first stage **Preliminaries**. In the flyout, click **Next Stage.**

![[Click Preliminaries and then click Next Stage](media/08a5f8a76105e84dc2724181e655b0f5.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P54.png)

1.  Advance each stage in the business process flow until you reach the **Launch** stage. Observe the fields associated with stage as you advance through them.

![[Business Process flow with all stages checked up to Launch](media/f7b0995f6d11a11941b7cc79448467bd.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P55.png)

1.  Click **Go live** on the command bar. If you don’t see Go live available, select **Save** first.

![[Click Go live on the command bar](media/4fc68f56dc09929e68b64439c4deb451.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P56.png)

1.  You will see the **Teams URL** populated.

![[Graphical user interface, text, application Description automatically generated](media/0e0e295f3185f7b7fdd1ad6572f39a74.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P57.png)

1.  You may also choose to **change the meeting options**. After toggling to enable this setting, additional fields appear. These allow you to modify settings such as making the recording available to attendees, enabling meeting chat, allowing reactions, etc.

![[Graphical user interface, text Description automatically generated](media/3e0791109e24f0ddd603da44a6829655.png)](https://github.com/MicrosoftLearning/IC-001T00-Microsoft-Cloud-for-Healthcare/blob/master/Instructions/Labs/IMAGES/L1P58.png)
