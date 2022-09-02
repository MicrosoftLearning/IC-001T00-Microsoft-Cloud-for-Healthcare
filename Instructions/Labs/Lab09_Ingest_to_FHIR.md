# Module 5 Lesson 4 Lab 9: Ingest to FHIR

### Overview

In this lab, you will learn how to use the FHIR Loader utility to ingest FHIR data into the FHIR service.

Data ingestion into FHIR is a vital capability for a healthcare organization's integration with multiple health data systems. While the FHIR service does features a custom $import operation for data ingestion, it is only recommended for the initial transfer of data into the FHIR service (data loading at high speeds). Alternate approaches can be used for the ongoing, transactional loading of FHIR data. In this challenge, we will be using Microsoft's FHIR Loader (OSS) utility, which is an Azure Function App built for importing data into the FHIR service.

### Learning objectives

In this lab, you will:
-	ingest FHIR data into FHIR service with FHIR Loader
-	identify issues in loading FHIR bundles
-	recognize data constraints with FHIR Loader
-	track and compare FHIR Loader operations


### Step 1 - Download Sample Data

Start by downloading these two .zip files to your desktop (when you click the links, you will see a download button on the right).

-   [good_bundles.zip](https://github.com/microsoft/azure-health-data-services-workshop/blob/main/Challenge-03%20-%20Ingest%20to%20FHIR/samples/good_bundles.zip)
-   [bad_bundles.zip](https://github.com/microsoft/azure-health-data-services-workshop/blob/main/Challenge-03%20-%20Ingest%20to%20FHIR/samples/bad_bundles.zip)

### Step 2 - Use FHIR Loader to upload data

Visit the FHIR Loader (OSS) repository [here](https://github.com/microsoft/fhir-loader) and read the documentation for more info on the operating principles of the application.

1.  In Azure Portal, navigate to the Blob Storage account that was created for FHIR Loader in Lab-01. Go to **Portal -\> Resource Group -\> Storage account** (the name of the Storage account will end in **"impsa"**).

![Graphical user interface Description automatically generated](media/c660d0e200fcb143a1b039dec50dc294.png)

1.  In the Storage account, click on the **Storage browser (preview)** blade and then click on **Blob containers**.

![Graphical user interface, application Description automatically generated](media/404fbf7039c8105160567637eaf20039.png)

-   
1.  Click on the **zip** container and upload the good_bundles.zip file downloaded in Step 1 of this lab.

![Graphical user interface, application Description automatically generated](media/d3ea92d504b59587ba02f17ed55b6ffd.png)

-   Once you click **Upload**, the FHIR Loader will automatically import the data from the .zip file into the FHIR service database.
1.  Now, when you do a refresh and click on **bundlesprocessed**, you should see six files as shown below.

*Note: If you upload a .zip file, the names of the bundles within the .zip archive are exposed (not the .zip filename itself).*

![Graphical user interface, text, application Description automatically generated](media/dc344ba965b18cd9b440cb766211ecbb.png)

### Step 3 - Debug issues with importing FHIR data

1.  Now try importing the bad_bundles.zip file that you downloaded in Step 1 of this lab. Upload the file to the same container where you uploaded the good_bundles.zip file.
2.  What happens as a result? Go ahead and unzip the bad_bundles.zip archive. Open and inspect the JSON bundle in a text editor (e.g., VS Code). You can compare this "bad" JSON bundle with the "good" JSON bundles contained in the good_bundles.zip archive.

Refer to the Troubleshooting section below or the FHIR Loader [testing](https://github.com/microsoft/fhir-loader/blob/main/docs/testing.md) documentation for information on tracking issues in FHIR data ingestion.

### Step 4 – BONUS: Troubleshooting

Here are some points for inspecting FHIR Loader operations:

-   In **Storage browser (preview)**, go to **Container** -\> **bundleserr** to view info about errors in importing FHIR bundles.

![Graphical user interface, text, application, email Description automatically generated](media/73cad23739978b4eb9e207510f0d8ac8.png)

-   Find the **.response** file and click on the three dots (···) located on the right end of the file. Then click **View/edit**.

![Graphical user interface, application Description automatically generated](media/f60c009b0430df0f79fca87330ea4b56.png)

-   What is the reason given for the error?
-   In comparison, you can go to **bundlesprocessed** and look in the .result files for ingest operations that succeeded. For example, in the image below there is a 201 status code, meaning success. The response shows an endpoint for a FHIR Resource ExplanationOfBenefit/\<resourceId\>, indicating that this Resource (ExplanationOfBenefit/\<resourceId\>) has been successfully persisted in FHIR service from the ingest operation.

![Graphical user interface, text, application, Word Description automatically generated](media/51c7d437f7843a45b94a53a3db240deb.png)

What does success look like for Lab-03?

-   Successfully upload and import data from the file good_bundles.zip.
-   Successfully identify the problem in the bad_bundles.zip file. Use the Troubleshooting tips above for help.

