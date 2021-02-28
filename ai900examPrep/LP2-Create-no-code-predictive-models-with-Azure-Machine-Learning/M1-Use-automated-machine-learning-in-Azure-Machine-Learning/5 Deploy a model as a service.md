# Deploy a model as a service

After you've used automated machine learning to train some models, you can **deploy the best performing model as a service for client applications** to use.

## Deploy a predictive service

you can deploy a service as an **Azure Container Instances** (ACI) or to an **Azure Kubernetes Service** (AKS) cluster.

1. In **Azure Machine Learning studio**, on the **Automated ML** page, select the run for your automated machine learning experiment and view the **Details** tab.
2. Select the **algorithm name** for the best model. Then, on the **Model** tab, use the **Deploy** button to deploy the model.
3. In the **Model summary** section, **observe the Deploy status**. Wait for this status to change to **Successful**.
4. View the **Endpoints** page. Then select the **Consume** tab and note the following information there.

    * The **REST endpoint** for your service
    * The **Primary Key** for your service

## Test the deployed service

Now that you've deployed a service, you can test it using some simple code.