# Train a machine learning model

Azure Machine Learning includes an **automated machine learning** capability that leverages the scalability of cloud compute to **automatically try multiple pre-processing techniques** and model-training algorithms in parallel **to find the best performing supervised machine learning model** for your data.

You can use automated machine learning to train models for:

* Classification (predicting categories or classes)
* Regression (predicting numeric values)
* Time series forecasting (regression with a time-series element, enabling you to predict numeric values at a future point in time)

## Run an automated machine learning experiment

1. In **Azure Machine Learning studio**, view the **Automated ML** page.
2. Create a new Automated ML run
3. After submitted, it will start automatically, wait run status to change from Preparing to running.
4. When the run status changes to Running, view the Models tab and observe as each possible combination of training algorithm and pre-processing steps is tried and the performance of the resulting model is evaluated. The page will automatically refresh periodically, but you can also select ↻ Refresh. It may take ten minutes or so before models start to appear, as the cluster nodes need to be initialized before training can begin.
5. Wait for the experiment to finish.

## Review the best model

After the experiment has finished; you can review the best performing model that was generated (within **exit criteria**)

The best model is identified based on the **evaluation metric** you specified.

1. On the **Details** tab of the **automated machine learning run**, note the best model summary.
2. Select the **Algorithm** name for the best model to view its details.
3. **Normalized root mean square error** value, select **View all other metrics** to see values of other possible evaluation metrics for a regression model.
4. Select the Metrics tab and select the **residuals** and **predicted_true** charts if they are not already selected. Then review the charts, which **show the performance of the model by comparing the predicted values against the true values**, and by showing the residuals (differences between predicted and actual values) as a histogram.

    * **Predicted vs. True** chart show a diagonal trend in which the predicted value correlates closely to the true value.
    * **Residual Histogram** shows the frequency of residual value ranges. what you should hope to see is that the most frequently occurring residual values are clustered around 0

5. Select the **Explanations** tab. Click on the **arrows** >> next to **Explanation ID** to expand the explanations list. Select an **explanation ID**, select **View previous dashboard experience** on the right-hand side. Then select **Global Importance**. This chart shows **how much each feature in the dataset influences the label prediction**.

