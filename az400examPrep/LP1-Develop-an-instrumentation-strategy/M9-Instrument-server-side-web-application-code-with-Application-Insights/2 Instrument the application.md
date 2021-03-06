# Instrument the application

The **TelemetryClient** object is used to record information about application-specific events and metrics.

## Events and metrics

1. **Events**
    * Represent any kind of event that occurs in your application that you are interested in tracking.
    * Each kind of event that occurs in your application needs a **unique** name
    * Tracked events can have arbitrary data attached to them that can be used to **Filter** and **Group** the data
    * You can find every tracked event with all its data in the **Diagnostic** search view in Azure Portal.
    * You can create **aggregate visualizations** in **Metrics Explorer**

2. **Metrics**
    * **Numeric** measurements
    * Taken **independently** of any event
    * Each metrics much have a **unique** name
    * **Pre-aggregated** - App Insights stores and transmits a statistical summary of measurements taken over time, not the exact value of each measurement (Reduce costs, makes metric data available for viewing and querying more quickly)
    * **Multidimensional** - metrics can also be multidimensional, record multiple values into a single metric - for segment, filter, group the data in visualizations

## Add instrumentation to your code

### 1. Get a TelemetryClient object

The *TelemetryClient* class provides access to all the properties and methods that you use to send information to Application Insights.

When you initialize the SDK with UseApplicationInsights(), TelemetryClient is registered for dependency injection. This means you can efficiently access TelemetryClient by adding it to the constructor of any controller or other component where you want to use it.

### 2.1 Track events

To track an event that occurs within your application, call **TrackEvent** on a **TelemetryClient** with the **name of the event**. TrackEvent supports two optional **IDictionary** arguments for tracking named properties and numeric metrics related to the event.

> // Track an event
> this.aiClient.TrackEvent("CommentSubmitted");
> // Track an event with properties
> this.aiClient.TrackEvent("VideoUploaded", new Dictionary<string, string> {{"Category", "Sports"}, {"Format", "mp4"}});

### 2.2 Track metrics

Metrics are recorded a little differently: call **GetMetric** with the name of the metric to get a **Metric** object, and then call **TrackValue** on it to record the measurement data.

* For single-dimensional metrics
    > this.aiClient.GetMetric("SimultaneousPlays").TrackValue(5);

* For multidimensional metrics
    > Metric userResponse = this.aiClient.GetMetric("UserResponses", "Kind");
    > userResponse.TrackValue(24, "Likes");
    > userResponse.TrackValue(5, "Loves");
