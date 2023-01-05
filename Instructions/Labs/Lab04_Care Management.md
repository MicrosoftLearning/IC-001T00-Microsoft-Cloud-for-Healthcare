# Module 4 Lesson 2 Lab 4: Care Management

## Overview

The **Care Management** application allows healthcare systems to provide coordinated care to each patient by quickly communicating the right information, at the right time, to the right people. Users can easily create, personalize, and enable new care plans for patients, manage care teams, and view patients’ clinical timelines and care insights right within the application.

Key capabilities for Care Management include the following:

-   **Care team**: View and collaborate with care teams to provide the best care for the patient.
    -   **Care plan**: Create and assign care plans and automate adherence to improve care coordination for your patients.
    -   **Clinical timeline**: Concise, sequential, and interactive view of patient's clinical occurrences.
    -   **Virtual clinic**: Provide your care team members the ability to perform virtual appointments with patients.

Care Management focuses on both **Enhance patient engagement** and **Empower health team collaboration** priority scenarios. It creates a system that allows for enhanced care team collaboration and coordination, virtual care options, and a 360 view of patient healthcare data including patient insights.

![](./IMAGES/Lab04/L4P1.png)

This lab will focus on the story of Lamna Healthcare Company, who is opening a new location in Redmond, WA.

![Timeline Description automatically generated](./IMAGES/Lab04/L4P2.png)

Now that Lamna Healthcare Company’s new location is ready to open, we need to ensure the new location record is in the system and that the employees understand the healthcare data model basics and how the tables and relationships are surfaced in the Care Management application.

## Learning objectives

In this lab, you will:

-   Explore the Healthcare Data Model
-   Navigate the Care Management application
-   Create a new Location record

## Exercise 1: Explore the Healthcare Data Model

In this exercise, you will learn about the core care management data tables. If you’d like to explore the tables in deeper detail on Microsoft Docs, please visit [Overview of Microsoft Cloud for Healthcare entities](https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/healthcare-overview).

The healthcare data model uses some of the out-of-the-box tables from Dynamics 365 applications. The following Healthcare solutions use the built-in Dynamics 365 tables:

| Healthcare solution    | Dynamics 365 tables                                      |
|------------------------|----------------------------------------------------------|
| Care Management        | Account, Activities, Contact, Tasks                      |
| Home Health            | Bookings, Incident, Products, Work Order                 |
| Patient Outreach       | Lead/Lead Score, Marketing Emails, Contact, Tasks        |
| Patient Service Center | Agent Script, Knowledge Article, Queues, Survey Response |

Visit [Healthcare data model overview](https://docs.microsoft.com/en-us/dynamics365/industry/healthcare/overview-data-model) on Microsoft Docs to learn more about the Healthcare data model.

### Task 1: Navigate Patient Details Tables and Relationships

In this task, you will explore the main tables related to Patient Data. Select each table name to navigate to the Microsoft Docs page that goes into detail about each table.

**Patient Detail Table Definitions**

| Table Name | Definition |
|----|----|
| **Patient (Contact)**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/administration/administrationcore/contact+++ | Person with whom a business unit has a relationship, such as customer, supplier, and colleague. |
| **AllergyIntolerance**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/clinical/clinicalcore/allergyintolerance+++ | Risk of harmful or undesirable, physiological response which is unique to an individual and associated with exposure to a substance. |
| **Condition**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/condition+++ | A clinical condition, problem, diagnosis, or other event, situation, issue, or clinical concept that has risen to a level of concern. |
| **MedicationRequest**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/medicationrequest+++ | An order or request for both supply of the medication and the instructions for administration of the medication to a patient. |
| **RelatedPerson**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/relatedperson+++ | Information about a person that is involved in the care for a patient, but who is not the target of healthcare, nor has a formal responsibility in the care process. |

See below for the **Patient Detail Entity Relationship Diagram**.

![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P3.png)

### Task 2: Navigate Clinical Data Tables and Relationships

In this task, you will explore the main tables related to Clinic Data. Select each table name to navigate to the Microsoft Docs page that goes into detail about each table.

**Clinical Data Table Definitions**

| Table Name | Definition |
|----|----|
| **Patient or Practitioner (Contact)**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/administration/administrationcore/contact+++ | Person with whom a business unit has a relationship, such as customer, supplier, and colleague. |
| **Organization**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/applicationcommon/organization+++ | Top level of the Microsoft Dynamics 365 business hierarchy. The organization can be a specific business, holding company, or corporation. |
| **Location**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/location+++ | Details and position information for a physical place where services are provided and resources and participants may be stored, found, contained or accommodated. |
| **AppointmentEMR**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/appointmentemr+++ | A booking of a healthcare event among patient(s), practitioner(s), related person(s) and/or device(s) for a specific date/time. This may result in one or more Encounter(s). |
| **Procedure**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/procedure+++ | An action that is or was performed on a patient. This can be a physical intervention like an operation, or less invasive like counseling or hypnotherapy. |
| **Encounter**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/encounter+++ | An interaction between a patient and healthcare provider(s) for the purpose of providing healthcare service(s) or assessing the health status of a patient. |
| **EpisodeOfCare**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/episodeofcare+++ | An association between a patient and an organization / healthcare provider(s) during which time encounters may occur. |
| **Observation**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/observation+++ | Measurements and simple assertions made about a patient, device or other subject. |
| **CodeableConcept**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/codeableconcept+++ | A Codeable Concept represents a value that is usually supplied by providing a reference to one or more terminologies, but may also be defined by the provision of text. |

See below for the **Clinical Data Entity Relationship Diagram**.

![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P4.png)

### Task 3: Navigate Care Plan Management Tables and Relationships

In this task, you will explore the main tables related to Care Plan Management. Select each table name to navigate to the Microsoft Docs page that goes into detail about each table.

**Care Plan Management Table Definitions**

| Table Name | Definition |
|----|----|
| **Patient (Contact)**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/administration/administrationcore/contact+++ | Person with whom a business unit has a relationship, such as customer, supplier, and colleague. |
| **CarePlan**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/careplan+++ | Describes the intention of how one or more practitioners intend to deliver care for a particular patient, group or community for a period of time, possibly limited to care for a specific condition |
| **CarePlanActivity**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/clinical/clinicalcareteam/careplanactivity+++ | Identifies a planned action to occur as part of the plan. For example, a medication to be used, lab tests to perform, self-monitoring, education, etc. |
| **CarePlanActivityGoal**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/clinical/clinicalcareteam/careplanactivitygoal+++ | Internal reference that identifies the goals that this activity is intended to contribute towards meeting. |
| **Goal**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/clinical/clinicalcareteam/goal+++ | Target objective for a user or a team for a specified time period. |
| **CarePlanGoal**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/clinical/clinicalcareteam/careplangoal+++ | Describes the intended objective(s) of carrying out the care plan. |
| **Encounter**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/encounter+++ | An interaction between a patient and healthcare provider(s) for the purpose of providing healthcare service(s) or assessing the health status of a patient. |
| **Episode of Care**, +++https://docs.microsoft.com/en-us/common-data-model/schema/core/industrycommon/healthcare/foundational/commoncore/episodeofcare+++ | An association between a patient and an organization / healthcare provider(s) during which time encounters may occur. |

See below for the **Care Plan Management Entity Relationship Diagram**.

![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P5.png)

===

## Exercise 2: Navigate Care Management Application

In this exercise, you will navigate the patient record and explore all the detailed information that is captured about the patient by Microsoft Cloud for Healthcare. In this case, we will examine the healthcare information of Amber Rodriguez to see how a care team member would obtain a full view of the patient.

1. [] Navigate to +++http://make.powerapps.com+++ in an In-Private or Incognito window. If you are in an official training class, sign in with your assigned user.

1. [] Select the **MC4H Labs Environment** in the upper right.

    ![](./IMAGES/Lab04/L4P6.png)

1. [] In Power Apps, select **Apps** in the left sitemap. Select and open **Care Management**.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P7.png)

1. [] You will be landed in the **Health Analytics** section showing either the **Care Coordinator Dashboard** or the **Care Plan Activities Dashboard**. These are helpful tools for care coordinators to get a complete view of their healthcare organization data, including care plans, care plan activities, care plan goals, appointments (EMR), and activity timeline.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P8.png)

1. [] Select **People** in the left Site Map.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab04/L4P9.png)

1. [] Find and select **Amber Rodriguez** from the **Active Patients** view. Open the record by double clicking or selecting **Edit** in the command bar.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab04/L4P10.png)

1. [] Take a moment to examine the **Summary** tab on Amber’s patient record. The purpose of the patient record is to give a comprehensive view of Amber’s latest information. In the summary tab, the care team member will have a full view of Amber’s **Conditions**, **Test Results**, **Patient Relationships**, **Allergies** **and** **Sensitivities**, **Clinical Data**, and **Patient Interactions**.

    ![A screenshot of a computer Description automatically generated with medium confidence](./IMAGES/Lab04/L4P11.png)

1. [] In the **Active Conditions** section, the care provider can get a view of all of Amber’s pre-existing conditions.

    ![Graphical user interface Description automatically generated with medium confidence](./IMAGES/Lab04/L4P12.png)

1. [] In the **Patient Relationships** area, you can see Amber’s related people in the system.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P13.png)

1. [] In the **Allergies and Sensitivities** section, you can get a singular point of view of all the reported allergies that the care givers need to be aware of for the patient.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab04/L4P14.png)

1. [] In the **Clinical Details** section, you can cycle through the various icons to see different medical details including **medications and prescriptions**, **encounters**, **results and diagnostics**, and **procedures**. This is a simple and efficient way to observe patient healthcare details.

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab04/L4P15.png) ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab04/L4P16.png)

    ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab04/L4P17.png) ![Graphical user interface, text, application Description automatically generated](./IMAGES/Lab04/L4P18.png)

1. [] The **Patient Interactions** section shows any activity, note, or post and can be filtered or sorted.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab04/L4P19.png)

1. [] Select the **Profile** tab to get **Patient, Address, and Insurance Information.** In the **Patient Information**, notice that key patient data such as **Date of Birth** and **Primary Practitioner** are shown. The healthcare data model uses the contact entity from the Common Data Model and defines the type of contact as patient, practitioner, or related person. This determines the type of form shown.

    ![Graphical user interface Description automatically generated](./IMAGES/Lab04/L4P20.png)

1. [] Select the **Clinical Timeline** tab. On this tab, a care team member will be able to view a weekly calendar of the patient’s clinical information as well as a list of any upcoming or previous events.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P21.png)

1. [] Select the **Upcoming** **events** dropdown in the right pane and switch to **previous events**.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P22.png)

1. [] See the list of events Amber had previously including **Appointments**, **Care Plans**, **Encounters**, and **Medication Requests**.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab04/L4P23.png)

1. [] Select the **Care Plan** tab. On this tab, the care team member will be able to see a full view of all the Care Plans associated to the patient. This includes a list of their care plan activities and statistics for completed activities and goals. You can create a new care plan or filter by care plan type in this view.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P25.png)

1. [] Select the **Care Team** tab. On this tab, the care team member can find other members who may be providing care to the patient for any current conditions and care plans.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P24.png)
    
1. [] Finally, select the **Related** tab to see any additional details related to the patient record.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P26.png)

**Congratulations!** You have explored the Care Management app and its featured data within a patient record.

===

## Exercise 3: Create a New Location

In this exercise, you will be creating a new Location record for the **Lamna Healthcare Company** Organization. They have opened a new branch in **Redmond, WA** and we need to ensure this location is in the system.

1. [] Select and open **Care Management** from the **Apps** list if you do not already have it open.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P27.png)

1. [] In the **Care Management** sitemap on the left, select **Locations**.

    ![A picture containing graphical user interface Description automatically generated](./IMAGES/Lab04/L4P28.png)

1. [] In the **All Locations** view, select **+New**.

    ![A picture containing diagram Description automatically generated](./IMAGES/Lab04/L4P29.png)

1. [] Fill in the following information for the new location:
    1.  **Name**: +++Lamna Healthcare – Redmond, WA+++
    1.  **Address City**: +++Redmond+++
    1.  **Address State**: +++WA+++
    1.  **Managing Organization**: +++Lamna Healthcare Company+++

        ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P30.png)

        ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P31.png)

1. [] Select **Save & Close**. Now let’s see the new location in the Managing Organization record.

1. [] In the sitemap on the left, select **Organizations**.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P32.png)

1. [] Change the grid view in the drop-down from **My Active Accounts** to **Active Accounts**.

    ![Graphical user interface, text, application, email Description automatically generated](./IMAGES/Lab04/L4P33.png)

1. [] Once in the **Active Accounts** view, select the **Lamna Healthcare Company** Organization.

    ![Graphical user interface, application Description automatically generated](./IMAGES/Lab04/L4P34.png)

1. [] On the **Lamna Healthcare Company** record, select the **Related** tab and scroll down to select **Locations**.

    ![Graphical user interface, application, email Description automatically generated](./IMAGES/Lab04/L4P35.png)

1. [] You will see the newly created **Lamna Healthcare – Redmond, WA** location associated to the record.

    ![Text Description automatically generated](./IMAGES/Lab04/L4P36.png)

**Congratulations!** You created a new location in Redmond, WA for Lamna Healthcare Company using the Care Management application.

