# Analyze web applications by using Azure Application Insights

## Criteria for assessing Application Insights

You use Application Insights if:

* You want to **analyze and address issues** and problems that affect your **application**'s health.
* You want to **improve your application's development lifecycle**.
* You want to **analyze users' activities** to help understand them better.

## Integrate Application Insights with your applications

To integrate Application Insights with your applications:

1. Set up an Application Insights resource in the Azure portal
2. Install an instrumentation package in your application. The package will monitor your application and send log data to the Log Analytics workspace.

## 1. Monitor your applications continuously

Application Insights can send alerts for issues like failures or unavailability of your application. You can **create availability tests to monitor the health of your applications continuously**. Availability tests allow you to check the health of your application from different geographic locations.

You can create an **availability test** in the Azure portal. You need to specify details likes:

* The frequency
* The URL of your application
* Locations from which to test it

You specify the conditions that should trigger an alert. **For example, Application Insights can send an alert if a certain number of locations are unavailable**. And you specify who should be notified. Send notifications through email or text message. Or use **runbooks** and **webhooks** to respond to **alerts** in an automated way.

When you've created your availability test, **you'll see how your application is doing across different locations**.

## 2. Continuously monitor your release pipelines

Application Insights works with Azure Pipelines. Use them together to improve your development lifecycle. When an Azure Pipelines release pipeline receives an alert from Application Insights that something went wrong, it can stop the deployment. It then rolls back the deployment until the issue that caused the alert is resolved. This way, you respond much earlier and more effectively to issues as they arise in the development lifecycle.

### 2.1 Azure App Service deployment with continuous monitoring

When you create a new release pipeline in Azure Pipelines, you need to use the **Azure App Service deployment with continuous monitoring** template and apply it to your pipeline.

The template automatically creates a pipeline stage. View the tasks in your stage to configure the connection between your pipeline and Application Insights.

You need to provide details about your application and the Application Insights resource, and then save your configuration.

Template provides alert rules for:

* Server exceptions
* Failed requests
* Server response times
* Availability
* Custom - You can also modify alert rules and customize them for your specific needs.

### 2.2 Continuous monitoring gate

Add a continuous monitoring gate to your release pipeline. **Use the gate to stop deployment when an issue has been identified**, and continue deployment automatically when the issue is resolved.

First, you need to enable gates in the configuration of pre-deployment conditions. Then add the gate that you want. You can, for example, add a gate that will listen for active alerts:

### 2.3 Release summary

Analyze your release by viewing the logs in the release summary. You'll see all of your release steps, and whether each has succeeded or failed. You'll also see details of what caused a failure.
