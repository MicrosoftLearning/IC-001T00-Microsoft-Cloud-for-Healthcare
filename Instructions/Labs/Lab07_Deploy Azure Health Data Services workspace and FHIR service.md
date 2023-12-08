# Module 5 Lesson 4 Lab 7: Deploy Azure Health Data Services workspace and FHIR service

## Overview

In this lab, you will deploy an **Azure Health Data Services workspace** containing a **FHIR service** instance. In addition, you will set up Postman as your application for testing the FHIR service API.

**FHIR service** is the core component for reading, writing, and querying structured health data in Azure Health Data Services. You may have heard of the predecessor to FHIR service – called Azure API for FHIR (Microsoft's first generally available FHIR PaaS solution). For this training, we will be focusing on the new Azure Health Data Services FHIR service, which has some big advantages over its predecessor (like transaction bundles, workspace level configuration, and performance improvements for search, import, and export).

**Azure Health Data Services workspace relationship with FHIR, DICOM, and MedTech services**

In the Azure health ecosystem, the Azure Health Data Services workspace is a logical container for associated healthcare service instances such as FHIR, DICOM (Digital Imaging and Communications in Medicine), and MedTech services. You can provision multiple FHIR, DICOM, and MedTech services in a single workspace to meet your solution needs.

![Graphical user interface, application, Teams Description automatically generated](./IMAGES/Lab07/L7P1.png)


## Exercise 1: Deploy Azure Health Data Services workspace and FHIR service to your Azure environment

In the first part of this lab, you will use a template to deploy resources with the Azure Portal. This template will deploy
- Azure Health Data Services workspace 
- FHIR service 
- FHIR Loader 
- FHIR-Proxy 

1.	Login to [Azure Portal](https://portal.azure.com/) with your credentials.

2.	Click on three horizontal bars on the top-left of the Azure portal and click on **Create a resource.**
 
3.	In the search bar, Enter **Azure Health Data Services**. Then expand **create** and click on **Azure Health Data Services.**
 
4.	Update with the below details:

    i.	**Azure subscription** – Your Azure subscription

    ii. **Resource group** – Create new and name it as AHDSW – XX (XX is the unique ID for unique value)

    iii. **Workspace name** – ahdswdemo- XX ((XX is the unique ID for unique value)

    iv.	**Region** – East US

    v. Click on **Review + Create.**
 
5.	After a successful validation click on **Create**.
 
6.	Wait for the deployment is successful and click on Resource.
 
7.	You now can create a FHIR service, DICOM service, and MedTech service from the newly deployed Azure Health Data Services workspace. For this lab, click on **Deploy FHIR service.**
 
8.	Click on **Add FHIR Service**.
 
9.	Enter a **Service name** as **training** for your FHIR service. Select the **FHIR version** as **R4**, and then select **Review + create.**
 
10.	Once the validation is successful, click on **Create**.
 
11.	Wait for the deployment to complete.
 
12.	 Click on **Go to resource** once the deployment is complete.
 
### Exercise 2: Set up Postman and test FHIR service

In the next part of this lab, you will

• Visit another page and follow the instructions on setting up Postman.

• Make API calls to test FHIR service using Postman.

## Task 1 - Register a service client application in Microsoft Entra ID 

1. Open a duplicate tab of Azure Portal and search for **Microsoft Entra ID**. Select the option from the list displayed accordingly.

2. Click on **App registrations** from the left navigation pane.

3. Select **New registration.**

4. Update the below details:

   1. **Name of the application** – myhealthapiapp-XX (XX is the unique ID for unique value)

   2. For Supported account types, select **Accounts in this organization directory only**. Leave the other options as is.

   3. Select **Register**.
 
5. The app is created.

6. Select **Authentication** from the left navigation pane to review the settings. The default value for **Allow public client flows** is "**No**".
 
7. Select **Add a platform** to configure the platform. 
 
8. For Postman, select **Mobile and desktop applications**. 
 
9. Enter (https://www.getpostman.com/oauth2/callback) in the **Custom redirect URIs** section. Select the **Configure** button to save the setting.
 
10.	 Click on **Certificates & secrets** from the left navigation pane.
 
11.	Click on **New client secret.**
 
12.	Enter the **Description** as **Mysecret1** and Let the Expires value be as it is. Click on **Add**. Copy the **Value** and **Secret ID’s** value in a notepad
 
13.	 Select **API permissions** from the left navigation pane.

14.	Click on **Add a new permission.**
 
15.	Since we are using Azure Health Data Services, you'll add a permission to the service by searching for **Azure Healthcare APIs** under **APIs my organization uses**.
 
16.	Select **Delegated permissions** and search for **user_impersonation**. Select **user_impersonation**, and then select **Add permissions.**
 
17.	Click on **Grant Admin consent for Contoso**. Click on **Yes**.

 
## Task 2 - Assign FHIR Data Contributor role in Azure for Postman service client

1.	In the Azure Portal, Enter **FHIR** in the search area. 

2.	Select the FHIR service created – **training-XX** ((XX is the unique ID for unique value). Click on the service.

2.	Click on the Access control (IAM) from the left navigation pane. 
 
3.	Click on **Add > Add role assignment.**
 
4.	Search for **FHIR Data contributor** and select the option from the list. Click on **Next**.
 
5.	Click on **Select members** and add the use that you are logged in and the app you created. Click on **Review + Assign**.
 
6.	Click on **Review + Assign** again. 

7.	The role is added.
 
8.	Perform the same steps and add the role for the application - **myhealthapiapp** that we created.

## Task 3 – Launch Postman and import environment and collection files

1.	Install the [Postman application](https://www.postman.com/downloads/) and login with credentials by creating a new account.

2.	Launch the Postman application. Create a Workspace by name My **FHIRService**. Click on **Create**.
 
3.	On the left navigation pane, click on **Environments** and select **Create environment** and update the environments variables by following the next steps.
 
4.	Access the Postman environment template for **FHIR service** by opening the github URL https://github.com/microsoft/azure-health-data-services-workshop/blob/main/resources/docs/samples/fhir-service.postman_environment.json. 

5.	Click on anywhere inside the code and select all ( Ctrl +A) 

6.	Open a Note pad and paste the code. Right click and then click **Save as** to save the file with the name – **fhir-service.postname_environment.JSON** locally in JSON format.
 
7.	Access the Postman environment template for **FHIR proxy** using the URL https://github.com/microsoft/azure-health-data-services-workshop/blob/main/resources/docs/samples/fhir-proxy.postman_environment.json. 

8.	Click on anywhere inside the code and select all ( Ctrl +A) 

9.	Open a Note pad and paste the code. Right click and then click Save as to save the file with the name – **fhir-proxy.postname_environment.JSON** locally in JSON format.
 
10.	Switch back to Postman application in your workspace. Click on the **Environments** tab on the left and click the Import button next to the workspace name.

11.	Import the **fhir-service.postman_environment.json** file that you saved locally in the beginning of this exercise. On the **Import** pane, click on **Files**.
 
12.	Select the **fhir-service.postman_environment.json** file from your local drive and click **Open**. 

13.	Similarly, Import the **fhir-proxy.postman_environment.json** file that you saved locally in the beginning of this exercise.
 
14.	Now, access the **FHIR-CALLS.postman-collection.json** file available in this repo https://github.com/microsoft/azure-health-data-services-workshop/blob/main/resources/docs/samples/FHIR-CALLS.postman_collection.json. 

15.	Click on anywhere inside the code and select all ( Ctrl +A) 

16.	Open a Note pad and paste the code. Right click and then click Save as to save the file with the name – **fhir-CALLS.postname_environment.JSON** locally in JSON format.
 
17.	Navigate to the **Postman** and import the file like previously done

18.	Access the **FHIR_Search.postman_collection.json** file available in this repo https://github.com/microsoft/azure-health-data-services-workshop/blob/main/resources/docs/samples/FHIR_Search.postman_collection.json. 

19.	Click on anywhere inside the code and select all ( Ctrl +A) 

20.	Open a Note pad and paste the code. Right click and then click Save as to save the file with the name – f**hir-Search.postname_environment.JSON** locally in JSON format.
 
21.	Switch back to **Postman** application and import the files accordingly.
 
## Task 4 – Configure Postman environment

1.	Select **Environment** tab on the left navigation of Postman and then select **fhir-service** environment.
 
2.	For the fhir-service Postman environment, you will need to retrieve the following values from the Azure portal. Copy the following values from the Azure portal and paste them in the respective CURRENT VALUE columns of fhir-service environment.

	1. **tenantId** – Microsoft Entra  tenant ID (go to Microsoft Entra ID -> Overview -> Tenant ID)

	2. **clientId** - Application (client) ID for Postman service client app that you created.

   	3. **clientSecret** - Client secret value stored for Postman application.

	4. **fhirurl** - Go to Resource Group on Azure portal and then select your Resource group. Select FHIR service resource group. On the FHIR service resource group, on the Overview tab, go to FHIR metadata endpoint and copy without "/metadata" on the end.

	5. **resource** - Same as fhirurl

	6. **bearerToken** - Blank. 
 
3.	Select the three horizontal dots on the table and select **Persist All.**
 
4.	Click **Save** to retain the fhir-service environment values.

5.	Repeat Step 1 to Step 4 for fhir-proxy environment.

## Task 5 - Get an access token from Microsoft Entra 

In order to connect to FHIR service, you will need to get an access token first. To obtain an access token from AAD via Postman, you can send a POST AuthorizeGetToken request. The POST AuthorizeGetToken call comes pre-configured as part of the FHIR CALLS collection that you imported earlier.

1.	In Postman, click on **Collections** on the left, select the **FHIR CALLS** collection.

2.	Expand and select **POST AuthorizeGetToken**. 
 
3.	Make sure that **fhir-service** environment is selected from the dropdown menu above the **Send** button.
 
4.	On clicking **Send**, you should receive a response in the Body tab like shown below. The access_token value is automatically saved to the bearerToken variable in the Postman environment.
   
	{
  	  "token_type": "Bearer",
  	  "expires_in": "3599",
  	  "ext_expires_in": "3599",
 	   "expires_on": "XXXXXXXXXX",
 	   "not_before": "XXXXXXXXXX",
  	  "resource": "XXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX",
  	  "access_token": "XXXXXXXXXXXX..."
	}
 
You now have a valid access token in your Postman environment and can use the token in subsequent API calls to your FHIR service.

**Note** - Access tokens expire after 60 minutes. To obtain a token refresh, simply make another POST AuthorizeGetToken call and you will receive a new token valid for another 60 minutes.

## Task 6 - Test FHIR service with Postman

1.	Click on **Collections** from the left navigation pane. Expand the **FHIR CALLS** collection, and then select the **GET List Metadata call**. 
 
2.	Click **Send** to test that **FHIR** **service** is functioning on a basic level. The **GET List Metadata** call returns the FHIR service's Capability Statement. 
  
3.	If you receive an error, there should be information in the response indicating the cause of the error. If you receive a response like shown below, this means your setup has passed the first test.

4.	Click on **POST Save Patient** in the **FHIR CALLS** collection and press **Send**. 
  
5.	If you get a response like shown below, this means you succeeded in populating FHIR service with a Patient Resource. This indicates that your setup is functioning properly.
 
6.	Enter **GET List Patients** in the FHIR CALLS collection and press **Send**. 
 
 
7.	If the response is as shown below, this means you successfully obtained a list of every Patient Resource stored in the FHIR service database (currently only one patient). This means your setup is fully functional.
 
8.	Now you can experiment with other sample calls or your own FHIR API calls.
