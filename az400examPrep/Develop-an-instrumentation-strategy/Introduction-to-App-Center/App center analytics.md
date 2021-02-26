# How App Center Analytics works

By collecting, analyzing, and executing on your app's usage data, you can improve your app experience.

## What is analytics?

Analytics is the analysis of data, often looking for patterns. For app analytics, you are collecting data on the usage of your app to discover your users' behavior when they are using your app and its features.

For App Center, you will collect these data by integrating the App Center SDK for your app platform. With the SDK in place in your app, you start to immediately gather user insights. You can also start to collect custom data to analyze the usage of every part of your app.

## Collect key metrics

* See what devices and operating systems your users have
* See what languages are used
* Track the adoption of new releases of your app.

data is in the analytics **Overview** page

* See active user numbers and trends
* Session durations
* Popular devices
* Geographic distribution
* distribution of users across versions of your app

## Collect custom event data

Events in App Center are actions taken by the user. Tracking event allows you to learn about how your users interact with your app.
You can use this information to see:

* **Where users are leaving that progression**, which could potentially indicate a place to improve the usability of your app.
* **What areas of your app are the most popular**, allowing you to grow those areas or improve the presentation of that information in other parts of the app.

While tracking events, you can also **attach properties to your events** with additional information. For example, you might be tracking an event for when your user uploads a file. Attaching properties about that file type (image, text, etc.) would allow you to see the most popular file types.

Event tracking also establishes a history that can help diagnose crashes that you discover in the diagnostics information on App Center. You could examine the specific steps a user took before they encountered an unexpected error or before the app crashed entirely.

## Export collected analytics data

Default - 90 days, 28 days

To retain data for longer periods, you can configure App Center to continually export data to Azure Blob Storage or Application Insights.

