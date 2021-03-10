# Why monitor

* For an information system to be manageable, it must be monitored.
* The greater the complexity of the system, the more important it is to assess its operational status in real time (or near real time) and in a quantitative manner - with numbers, values, and percentages.
* Operators need to know how a system is performing, and they especially need to know if the system goes down or encounters repeated errors that pose a threat to reliability and availability.

Monitoring is as important in mission-critical solutions deployed to the cloud as the solutions themselves. In a fully monitored data-center environment, instrumentation is provided by software. Instrumentation generally takes on the three forms depicted in Figure 1:

1. **Logs** - **Permanent, immutable records** of events stored in a consistent, **tabular format**, if not in a full database. An event may be indicative of one of many conditions, including:
    * A **change in the status** of a monitored component (for example, from "busy" to "available")
    * The **completion of a task** or sequence of instructions
    * A **milestone in the progression** of data through a network, or the availability of units in a network
    * An **error**, which in this context is a behavior that the system or application has not been programmed to handle or mitigate
2. **Metrics** - **Values that represent the relative health, stability, and availability** of a service or application or the infrastructure that hosts it
3. **Traces** - **Records of the paths of execution for programs and services**, especially in a highly distributed system, indicating the sequence of instructions that may have triggered, either directly or indirectly, an event

## 1. Logs

* **Table of machine data** relevant to the **operative history of a component** or an element of software **over a period of time**.
* A **log-monitoring or log-management (LM) platform** provides **access to the messages being recorded by services, applications, and infrastructure components** in an information system.
* In **Linux-based** servers, both **system services** and **applications** rely on the operating system's syslog service to store and maintain logs, usually in the **/var/log** directory.

### Log-management (LM) platform

* Detect when the **contents of logs in this directory have been changed** and can scan those contents for changes.
* **Scan** the logs **periodically**, or it might **subscribe** to notifications indicating that a log has been updated.
* **Examines** a **database** or other local **storage** component **where these changes are filed**, and determines whether any of these changes:
  * Either collectively or individually, warrants an alert - a message intended to be seen by a human operator.
* The more sophisticated LM platforms **leverage streaming message queues** such as Apache Kafka, which can **distribute messages through a network** extremely efficiently.

#### An LM platform should be capable of performing the following tasks:

1. **Correlation:**
    * **Joining relevant recorded events together** into a single view so that managers are not forced to scan raw data for potentially pertinent information
2. **Normalization:**
    * **Reducing the volume of recorded data in the database**, as well as in administrators' views of the database, into more manageable volumes
3. **Reporting**
    * P**resenting a graphical**, **informational view** of events that is intelligible to someone working outside the realm of day-to-day IT operations

Maintained regularly and properly, logs collectively **represent all the actionable events that are relevant to the health of an information system**, as well as to any diagnosis of failures or low service levels. When services or system components write pertinent data to logs, a log monitor can analyze this data in real time in order to diagnose or even predict failure conditions.

## 2. Metrics

* **Quantitative values and performance levels pertinent** to the services being provided to customers, or to the infrastructure hosting those services.
* The metrics an organization chooses to measure are **driven by the elements of service delivery that it believes are important** to its **customers** and **users**.

### Service delivery

* The **final step** in a long process that involves the **concurrent operation of a myriad of mechanisms**

### Mechanisms

* **both accurate and fitting**, because every component of a service is a complex rendering of a simple machine. It takes inputs, processes them, and produces an output. It's this realization - that systems are comprised of individual mechanisms, each of which we can understand - that makes monitoring both feasible and practical.

### Logs vs Metrics

* **Logs** records events **over time**
* **Metrics** represent states of being or service levels, often at the **present time**.
* **Logs** can conceivably record the states of **various metrics** over given intervals
* **Logs** can report on certain **metrics based on composite values attained from other logs**.
* Many **metrics are based on correlations** - comparisons or ratios of one factor to others - which may best be rendered by **application performance monitors (APMs)** rather than through log analysis.
* **Other metrics** are observations **compiled from outside the system itself**, including estimates of users' ability to comprehend the system.

### Common categories of low-level, IT-related metrics tracked by an APM platform include:

1. **Request queue volume:**
    * A measure of the backlog of incoming user requests, compared to the system's ability to respond to them
2. **User sentiment:**
    * Estimates based on the relative level of productive workflow compared to the activity level of a user
3. **Resource availability**
    * The responsiveness of system resources to requests or queries
4. **Error rates**
    * The relative volume of behavioral events that cannot be mitigated by the application, or by the server's infrastructure
5. **Session length**
    * The intervals of time between users logging on and logging off

APM platforms frequently offer higher-level, more observational metrics that are more transactional and customer-oriented - for example, service-level scores (1-star to 5-star scores rendered by users), service abandonments (intervals of time before a user gives up before achieving the application's objective), and frequency of customer logons over extended periods.

## 3. Traces

**Trace-maintenance platforms** represent a category of **performance-management tool** that collect data about the **low-level service calls between highly distributed services and functions**, especially in containerized environments orchestrated by Kubernetes.

A modern trace-maintenance or trace-monitoring tool is capable of:

* Identifying SQL queries
* HTTP-based calls to APIs
* Remote procedure calls
* Ideally, any transaction from one component that passes control to, or relies upon a response from, another component.

### Timeline

* A common feature of trace-monitoring tool.
  * Plots the **sequence of events** in a compound transaction
  * Charting which events are **dependent** upon one another, which can take place in **parallel**.
  * Plot **dependency graphs** that depict the relationship between components of a distributed system. Graph can provide developers with their first visual snapshots of the shape and texture of their applications, depicting which components are heavily relied upon, as well as which ones can cause transactional bottlenecks and slower workflows.

## Making Complex Systems Observable

An information system need not have a flat, rudimentary architecture to be relatable or observable.

**Monitoring is the only way for an administrator to achieve full situational awareness.** The only way to achieve an accurate picture of an entire system and the interdependencies and relationships of its parts to one another is to send probes into those parts, have each probe build a chart of what it perceives, and stitch the charts together into one map.
