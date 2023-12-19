# Module 5 Lesson 4 Lab 9: Ingest to FHIR

## Overview

In this lab, you will learn how to use the FHIR Loader utility (https://github.com/microsoft/fhir-loader) to ingest FHIR data into the FHIR service.

Data ingestion into FHIR is a vital capability for a healthcare organization's integration with multiple health data systems. While the FHIR service does features a custom $import operation for data ingestion, it is only recommended for the initial transfer of data into the FHIR service (data loading at high speeds). Alternate approaches can be used for the ongoing, transactional loading of FHIR data. In this lab, we will be using Microsoft's FHIR Loader (OSS) utility, which is an Azure Function App built for importing data into the FHIR service.

The open-source FHIR Loader is designed to ease the process of FHIR data import into the FHIR service. The operation simply involves uploading FHIR data files to Azure blob storage, and from there the FHIR Loader automatically transfers the data for persistence in the FHIR service database. The user may upload FHIR Bundles in regular JSON format (.zip compressed or non-compressed) or NDJSON format (non-compressed). Operationally, FHIR Loader works by making parallel asynchronous API calls to the FHIR service.

Below is a component view of FHIR Loader connected to the FHIR service endpoint.

![image](./IMAGES/Lab09/image1.png)

In Lab 7, the ARM template automatically deployed and configured FHIR Loader to connect with FHIR service in your resource group.

For this lab, you will upload FHIR data bundles for import into the FHIR service. You will need to examine error logs and determine what is preventing the data in one of the bundles from being ingested.

**Prerequisites**

- Successful completion of Lab 7

- A text editor (e.g., Visual Studio Code (see https://code.visualstudio.com/)

## Learning objectives

In this lab, you will:

-	Ingest FHIR data into FHIR service with FHIR Loader

-	Identify issues in loading FHIR bundles

-	Recognize data constraints with FHIR Loader

-	Track and compare FHIR Loader operations

## Exercise 1: Download Sample Data

1.  Start by downloading these two .zip files to the VM desktop (Open the following URLs in new tabs. You will see a download button on the right).

- **good_bundles.zip** at (https://github.com/microsoft/azure-health-data-services-workshop/blob/main/Challenge-03%20-%20Ingest%20to%20FHIR/samples/good_bundles.zip)

![image](./IMAGES/Lab09/image2.png)


## Exercise 2: Use FHIR Loader to upload data

1.	Open a tab in the browser. Go to [Azure Portal](https://www.portal.azure.com/)

2.	Login with your credentials.

3.	Enter Storage Account in the Search area on the home page. Select the option accordingly.
 
![image](./IMAGES/Lab09/image3.png)

4.	Click on **Create**.
 
![image](./IMAGES/Lab09/image4.png)

5.	Update the below details:

    a.	Select your **Azure subscription**

    b.	Select your Azure Health Data services resource group

    c.	Storage account name – **fhir123**

    d.	Select **Review**
 
![image](./IMAGES/Lab09/image5.png)

6.	Once the Validation is a success. Click on **Create**.

7.	The deployment takes a while to complete. You can see the service in your resource group.
 
![image](./IMAGES/Lab09/image6.png)

## Exercise 3: Upload data to FHIR

1.	Go to [Azure Portal](https://www.portal.azure.com/) and select **Resource Groups.**
 
![image](./IMAGES/Lab09/image7.png)

2.	Select your resource group created.
 
![image](./IMAGES/Lab09/image8.png)

3.	Navigate to your Resource group – **AHDSW**. Select the **Storage account.**

4.	In the **Storage account**, select the **Storage browser** blade and then select **Blob containers**.
 
![image](./IMAGES/Lab09/image9.png)

5.	Select the **zip** container and select **Upload**. If you don’t find it, you can create a new container with the name **zip**. Once created, upload the files.
 
![image](./IMAGES/Lab09/image10.png)

6.	Browse and upload the **good_bundles.zip** file downloaded in Exercise 1 of this lab.

7.	Select **Zip** in **Select an** **existing container** field. 

8.	Select **Upload**, and the FHIR Loader will automatically import the data from the .zip file into the FHIR service database.
 
![image](./IMAGES/Lab09/image11.png)

We have successfully uploaded and import data from the file good_bundles.zip.



