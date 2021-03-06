# View Application Insights metrics in the Azure portal

## Tools for data visualization

1. **The Azure portal:**
    * Can find a variety of tools by going to the **Application Insights resource** in the portal.
    * Include **a set of common performance charts** on the **Overview** page, an **Application** map, and **Performance** and **Failures** pages.
    * An **Application Insights dashboard** that contains a **common set of charts**.
    * Can use the **Metrics** page to:
        * Design new charts
        * Add new charts to dashboards
2. **Power BI:**
    * Used by business analysts to **investigate business values** like sales and profit margins.
    * Can **connect Power BI to an Application Insights resource** and use it to display web app telemetry data.
3. **Visual Studio:**
    * Developers can **connect Visual Studio to Application Insights**
    * View the **same charts and visualizations** that are shown in the Azure **portal**
    * See **code** and **performance** data in one tool
4. **Custom tools:**
    * Application Insights includes a **comprehensive API for accessing telemetry and analytics**
    * Custom tools and applications can use the API to power their own visualizations
    * For example, if you have a custom mobile app that your business decision makers use to view sales data, you can add a visualization of web site performance statistics to the app.

## Custom charts

You can create your own chart on the Metrics page. For example, you can:

1. **Specify a time period for the chart**
    * This could be the **last 30 minutes or the last 30 days**, or somewhere in between
    * You can also **specify a start and end time** for the period that interests you
2. **Specify the type of chart**
    * Line
    * Area
    * Bar
    * Scatter
3. **Specify a metric to display**
    * This metric will be shown on the vertical axis
4. **Specify an aggregation method**
    * Average
    * Minimum
    * Maximum
    * Sum
    * Count for the chosen metric at each plotted point
5. **Specify a filter**
    * Data that doesn't satisfy the filter won't be displayed
    * Use filters when you need to focus on a specific data set

## Go to the Application Insights resource and dashboard

* The Application Insights resource is **separate** from the App Service resource that contains the instrumented web app.
* When you enable **runtime instrumentation** in a web app, a **link appears in the Azure portal** that takes you from the web app resource to the Application Insights resource that receives the data.
* From the web app, you can go to the Application Insights page and select View Application Insights data to go to the Application Insights resource and make configuration changes.
* Another way to view the Application Insights dashboard is to select Dashboard from the Azure portal menu.
* If more than one dashboard is stored for your user account, you might need to switch to the Application Insights dashboard you want by selecting it in the drop-down list in the upper-left corner.
