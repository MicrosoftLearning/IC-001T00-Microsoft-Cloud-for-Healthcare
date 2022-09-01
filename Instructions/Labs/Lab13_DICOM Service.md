# Module 6 Lesson 4 Lab 13: DICOM Service

### Step 1 - Find your Azure Health Data Services workspace using Azure Portal

In Lab-01 of this workshop, you deployed an Azure Health Data Services workspace in your resource group. You can view your Azure Health Data Services workspace settings by navigating to **Portal** -\> **Resource Group** and finding the resource with a name ending in **"ws"** (see image below).

![Graphical user interface, application Description automatically generated](media/4814c3a4a448d967906ad9ea30bb8d5e.png)

Click on the item in the list. Then, scroll down and click on the **DICOM service** blade. Once there, click on the **+Add DICOM service** button and proceed to the next step.

### Step 2 - Deploy DICOM service using Azure Portal

Now you will visit another page and follow the instructions to [Deploy DICOM service using the Azure portal](https://docs.microsoft.com/en-us/azure/healthcare-apis/dicom/deploy-dicom-services-in-azure). Go directly to \#3 in the instructions and begin from there. Then return here when finished.

*Note: DICOM service deployment typically takes several minutes.*

### Step 3 - Configure Azure roles for access to DICOM data

You will need to add the **DICOM Data Owner** role for yourself (i.e., your username in Azure) as well as for the Postman service client that you created in Lab-01 ([documentation available here](https://docs.microsoft.com/azure/healthcare-apis/configure-azure-rbac#assign-roles-for-the-dicom-service)).

### Step 4 - Import Postman environment and collection files to connect with DICOM service

1.  Access the Postman environment template for DICOM service [here](https://github.com/microsoft/azure-health-data-services-workshop/blob/main/Challenge-08%20-%20DICOM%20service/postman/dicom-service.postman_environment.json). Save the file locally (click on **Raw** and then do a **Save as** from your browser).
2.  In Postman, find the **Environments** tab on the left and click the **Import** button.
3.  Import the dicom-service.postman_environment.json file that you just saved locally.
-   Add the file to Postman using the **Upload Files** button. Then click **Import**.
1.  Now, access the Conformance-as-Postman.postman_collection.json file available [here](https://github.com/microsoft/dicom-server/blob/main/docs/resources/Conformance-as-Postman.postman_collection.json) and save the file locally. Then import the file into Postman.
-   Add the file to Postman using the **Upload Files** button. Then click **Import**.

### Step 5 - Configure Postman environment

You will now configure a new Postman environment for DICOM service (dicom-service).

1.  For the dicom-service Postman environment, you will need to retrieve the following values:

*From your existing* fhir-service *Postman environment:*

-   tenantId - AAD tenant ID (you also can find it in **AAD** -\> **Overview** -\> **Tenant ID**).
-   clientId - Application (client) ID for Postman service client app.
-   clientSecret - Client secret for your Postman app.

*New values you need to input:*

-   resource - https://dicom.healthcareapis.azure.com
-   baseUrl - Service URL appended with /v1. Go to **Portal** -\> **Resource Group** -\> **DICOM service** -\> **Service URL**. Copy and add /v1 on the end: https://\<workspace-name\>-\<dicom-service-name\>.dicom.azurehealthcareapis.com/v1.

Populate the above parameter values in your dicom-service Postman environment. Input the values in the **CURRENT VALUE** column. Leave bearerToken blank. Make sure to click **Save** to retain the dicom-service environment values.

### Step 6 - Choose a path for the rest of the lab

From here, you will be using the DICOM service for the features outlined in [the beginning of this lab](https://github.com/microsoft/azure-health-data-services-workshop/tree/main/Challenge-08%20-%20DICOM%20service#learning-objectives-for-challenge-08). You have the option to follow either of these paths:

**Basic Path**

You can use an already configured Postman collection to execute the series of tasks.

\-or-

**Advanced Path**

You can follow the provided articles that go over how to programmatically communicate with the DICOM service using C\#, Python, or cURL.

Basic Path

Step 1 - Obtain an access token to connect with DICOM service

1.  In Postman, make sure you have selected your dicom-service environment as the active environment.
2.  Click on the Conformance-as-Postman collection.
3.  Click on the POST AuthorizeGetToken request and click **Send**. You should receive a 200 OK message in response. Your access token is now saved to the bearerToken environment variable in your dicom-service Postman environment. Access tokens expire after 60 minutes. A refresh can be obtained by sending the POST AuthorizeGetToken request again.

Step 2 - Populate DICOM service with single instance images

1.  Once your dicom-service Postman environment is set up and you have obtained an access token, please go to [this repo](https://github.com/microsoft/dicom-server/tree/main/docs/dcms) and download the three DICOM instance files (.dcm).
2.  Then, for each of the three POST Store-single-instance calls in the Conformance-as-Postman collection, go to **Body**, click on the "x" next to the filename, click **Select File** and choose the appropriate .dcm file (downloaded in the previous step).

    ![A screenshot of a computer Description automatically generated with medium confidence](media/d8cb3668a1ea6067dff339ffaa1c502a.png)

3.  Press **Send** for each POST Store-single-instance call and you will populate your DICOM service with the three .dcm single instance files.

### Step 3 - Execute Outlined Features via Postman Collection

-   The Conformance-as-Postman collection has a complete set of API calls that you can execute one by one. See the list below for details.
-   Store DICOM files to the service
-   Search among the files that are stored within the DICOM service
-   Retrieve DICOM instance
-   Check logs of changes in DICOM service via Change Feed
-   Manage extended query tags in your DICOM service instance
-   Add extended query tags
-   List extended query tags
-   Get extended query tags
-   Update extended query tags
-   Delete extended query tags

Advanced Path

Step 1 - Choose your preferred method for uploading, searching, and retrieving DICOM images (C\#, cURL, or Python)

Each method comes with a set of prerequisites and instructions for getting started:

C\# - <https://docs.microsoft.com/azure/healthcare-apis/dicom/dicomweb-standard-apis-c-sharp>

cURL - <https://docs.microsoft.com/en-us/azure/healthcare-apis/dicom/dicomweb-standard-apis-curl>

Python - <https://docs.microsoft.com/en-us/azure/healthcare-apis/dicom/dicomweb-standard-apis-python>

Step 2 - Check the logs of the changes in the DICOM service via Change Feed

The Change Feed provides logs of all the changes that occur in your DICOM service. You can view instructions in this [Change Feed Overview article](https://docs.microsoft.com/en-us/azure/healthcare-apis/dicom/dicom-change-feed-overview).

Step 3 - Manage Extended Query tags in your DICOM service instance

By default, the DICOM service supports querying on the DICOM tags specified in [the conformance statement](https://docs.microsoft.com/en-us/azure/healthcare-apis/dicom/dicom-services-conformance-statement#searchable-attributes). By enabling extended query tags, the list of tags can easily be expanded based on the application's needs.

You can follow the instructions given in this [Extended Query Tag Overview article](https://docs.microsoft.com/en-us/azure/healthcare-apis/dicom/dicom-extended-query-tags-overview) to manage query tags.

### Step 4 – BONUS : Set up a DICOM viewer for DICOM service

As an added challenge, go to [this repo](https://github.com/microsoft/dicom-ohif) and follow the instructions to set up an [Open Health Imaging Foundation DICOM viewer](https://ohif.org) for your DICOM service.

Once you have configured the DICOM viewer, you can experiment with viewing the three DICOM instance files (.dcm) that you downloaded earlier in this lab.

What does success look like for Lab-08?

-   Provison and configure DICOM service for ingestion and storage of DICOM studies.
-   Use DICOM service to upload, search, and retrieve DICOM studies.
-   Check changes log (Change Feed).
-   Add/remove additional query tags

