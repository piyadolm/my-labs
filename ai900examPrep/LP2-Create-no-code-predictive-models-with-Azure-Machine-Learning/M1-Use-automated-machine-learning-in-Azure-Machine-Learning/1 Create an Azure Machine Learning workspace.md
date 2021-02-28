# Create Azure Machine Learning workspace

Azure Machine Learning is a cloud-based platform for building and operating machine learning solutions in Azure.

* Includes a wide range of **features** and **capabilities** that help to **prepare data**, **train models**, **publish predictive services**, and **monitor** their usage.
* Helps to increase their efficiency by **automating** many of the time-consuming tasks associated with **training models**
* Enables to use cloud-based compute resources that **scale effectively** to handle large volumes of data while incurring costs only when actually used.

## Create an Azure Machine Learning workspace

You can use Azure Machine Learning workspace for manage:

* Data
* Compute resources
* Code
* Models
* Other artifacts

Steps to create a workspace:

1. In Azure Portal, select **+Create a resource** from your subscription
2. Search for **Machine Learning**, create a new Machine Learning resource the following settings:

    * Subscription
    * Resource Group
    * **Workspace name**: Enter a unique name for your workspace
    * Region
    * **Storage account**: Note the **default new storage account** that will be created for your workspace
    * **Key vault**: Note the **default new key vault** that will be created for your workspace
    * **Application insights**: Note the **default new application insights** resource that will create for your workspace
    * **Container registry**: None (one will be created automatically the first time you deploy a model to a container)

3. Wait
4. On the **Overview** page for your Machine Learning Workspace, launch **Azure Machine Learning studio**
5. Sign into Azure Machine Learning studio using your Microsoft account
6. Select your **Azure directory** and **subscription**, and your **Azure Machine Learning workspace**.
7. In Azure Machine Learning studio, toggle the manu icon at the top left to view the various pages in the interface.
