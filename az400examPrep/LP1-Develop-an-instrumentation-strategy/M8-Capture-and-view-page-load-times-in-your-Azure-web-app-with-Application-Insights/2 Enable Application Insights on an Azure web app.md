# Enable Application Insights on an Azure web app

You can enable **runtime instrumentation**, the type of Application Insights instrumentation that **doesn't require you to change you app's code**, when the app is **first created** or at **any time afterwards**.

## What is Application Insights?

An Azure service that help you to **monitor** the **performance** and **behavior** of **web applications**.

Two kinds of data:

1. **Events** - individual data points that can represent any kind of event that occurs in an app.

    * Technical events - occur with the application runtime
    * Business events - are related to the business domain of the application or actions taken by users
2. **Metrics** - measurements of values, taken at regular intervals, not tied to specific events
    * Technical: Application's runtime or infrastructure, e.g. the length of a queue
    * Business: Related to the application's business domain or users, e.g. how many videos are viewed in an hour

## Application Insights resources

* Application Insights is represented in Azure **as a resource deployed to one of your subscriptions**.
* It's a repository for application telemetry data
* **Instrumentation key** is needed to configure in the app to send telemetry data to an Application Insights

## Visualizations

From Application Insights resource in Azure Portal, you can visualize the telemetry captured from your app in a variety of ways:

* **Live metrics streams:** Charts that **display performance values** as they vary in **near-real time**.
* **Metrics explorer:** Tool that **shows how metrics vary over time**.
* **Alerts:** **Messages automatically sent** to app admins when target **metrics** exceed specified **thresholds**.
* **Profiler:** Shows **how a set of requests were delivered**. You can use these profiles, for example, to see which page elements load slowly.
* **Application Map:** Displays the **components of an application and how they link to each other**.
* **Usage analysis:** Information about your app's users. For example, you can see numbers of unique users and sessions and information about user retention.

These tools are all available in:

* Azure portal
* Visual Studio
* Power BI
* Rest API
* Continuous Export

## Runtime instrumentation and build-time instrumentation

1. **Runtime instrumentation:**
    * No change on web app's source code.
    * Can be enabled when create web app or anytime afterwards.
    * Some advanced data displays aren't available
2. **Build-time instrumentation:**
    * Developers add a server-side SDK to the web app's code.
    * Full functionality and the richest set of visualizations
    * Custom events and telemetry to your code to monitor unusual or unique behavior.
3. **Client-side instrumentation:**
    * By including a standard Application Insights **JavaScript library** in pages delivered to your app's users
    * Captures information about the user experience of the app
        * Page load times
        * Details of browser exceptions
        * Performance data about AJAX calls
    * Can configure Azure App Service web apps to **automatically inject the client SDK** and capture many client-side metrics.
    * Can add JavaScript code to capture data about specific events.
    * Enables displays like usage analysis.

## Web app requirements

**Windows web apps** support all:

* Runtime instrumentation
* Build-time instrumentation
* Automatic client-side instrumentation

Web apps created with the ASP.NET or ASP.NET Core frameworks have the best integration with Application Insights.

You can enable runtime instrumentation for a Windows App Service web app when you create the app or at a later time.

**Linux web apps**:

* Application Insights in Linux apps is fully supported, but you need to modify application code to reference the **Application Insights SDK**

## Enabling runtime instrumentation

To enable it when you create the web app, on the web app **Create** pane, select the **Monitoring** tab and then select **Yes** next to **Enable Application Insights**. This screen will also give you the opportunity to create a new Application Insights resource.

If you choose to create a web app without enabling Application Insights, y**ou can enable it later on the Application Insights page of the web app's pane**.

## Enabling automatic client-side telemetry

To automatically inject the **JavaScript SDK** and necessary configuration into pages served by your web app, add a new application setting named **APPINSIGHTS_JAVASCRIPT_ENABLED** and set the value to **true**.

## Inject the Application Insights JavaScript SDK into the web app

You can inject the **Application Insights JavaScript SDK** into the web app without involving developers, and because this will generate more data for performance analysis, you want to **enable client-side monitoring**. To do this, follow these steps:

1. Navigate to your **App Service** in Azure Portal
2. Under **Settings** on the left, select **Configuration**. You will be on the **Application Settings** tab.
3. On the **Application Settings** page select **+ New application setting**.
4. In the **Enter a name** box, enter **APPINSIGHTS_JAVASCRIPT_ENABLED**.
5. In the **Enter a value** box, enter **true**.
6. At the bottom of the **Application Settings** page, select **OK** and at the top of the **App Services** page select **Save**.
7. In the top-left corner of the **App Service** page, select **Overview**
8. Select **Restart**, and then select **Yes**.
