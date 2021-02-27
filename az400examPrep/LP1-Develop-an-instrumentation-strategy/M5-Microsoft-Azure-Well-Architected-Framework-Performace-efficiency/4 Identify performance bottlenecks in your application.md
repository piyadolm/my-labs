# Identify performance bottlenecks in your application

In this unit, you'll look at processes and tools that can help you make sure that your application performs well.

## Performance requirements

Nonfunctional requirements help you find balance point of performance requirement and improvement.

These particular requirements don't tell you what your app must do. Instead, they tell you what quality levels it must meet. For example, you can define nonfunctional requirements to discover:

* How fast a transaction must return under a given load.
* How many simultaneous connections your application needs to support before it begins to return errors.
* If there's server failure, what's the maximum amount of time your application is allowed to be down before a backup is online.

Benefit of nonfunctional requirements:

1. Ensure that your application meets expectations
2. Ensure your application doesn't require more effort or cost more money than necessary
3. You can also plan your monitoring and operations rules

## Performance monitoring options in Azure

### 1. Azure Monitor

provides a single management point for infrastructure-level logs and monitoring for most of your Azure services. Collecting, analyzing, and acting on telemetry from your cloud and on-premises environments.

Azure Monitor collects data from each of the following tiers:

* **Application monitoring data:** Data about the performance and functionality of the code you've written, regardless of its platform.
* **Guest OS monitoring data:** Data about the OS on which your application is running. This OS might be in Azure, another cloud, or on-premises.
* **Azure resource monitoring data:** Data about the operation of an Azure resource.
* **Azure subscription monitoring data:** Data about the operation and management of an Azure subscription, and data about the health and operation of Azure itself.
* **Azure tenant monitoring data:** Data about the operation of tenant-level Azure services, such as Azure Active Directory (Azure AD).

### 2. Log Analytics

Centralized logging can help you uncover hidden issues that might be difficult to track down. With Log Analytics, you can query and aggregate data across logs. This cross-source correlation can help you identify issues or performance problems that might not be evident when you look at logs or metrics individually.

### 3. Application performance management (APM)

Deep application issues are often tricky to track down. This type of scenario is when it can be beneficial to integrate telemetry into your application by using an application performance management (APM) solution.

* Helps you to track down low-level application performance and behavior.
* Telemetry can include individual page request times
* Exceptions within your application
* Even custom metrics to track business logic

#### Application Insights

* An Azure service that provides this deep application performance management.
* Stores its data in a common repository, and metrics are shared with Azure Monitor.
* Take advantage of shared functionality such as alerts, dashboards, and deep analysis with the Log Analytics query language
