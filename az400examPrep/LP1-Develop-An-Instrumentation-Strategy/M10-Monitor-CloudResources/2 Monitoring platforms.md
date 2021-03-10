# Monitoring platforms

Monitoring platforms generally fall into two categories: those that are agent-based, and those that are not.

* Agent-based is
  * A **remote component** that signals back to an application performance monitor's (APM) central controller or hub
  * or A **Daemon** that serves as that controller's proxy.
* With a **basic APM**, the agent would simply **ping a server or application** periodically to make sure it's still available.
* Most **modern APM agents** are more sophisticated, sending telemetry to central hubs distributed throughout the cloud.
* **Some agents** may be **attached to client-side** applications or Web apps, reporting performance and connectivity data from JavaScript agents running in users' browsers.

## 1. Agent-Based APM Platforms

Modern APM platform vendors utilize agents in a variety of ways.

For example:

* **Inject JavaScript code** into the HTML content of Web pages, **enabling functions on the client side** to **communicate performance** data **with APM** platform servers
* Gather records from the performance logs generated by
  * Applications
  * Services running on the client
  * The client itself
* Partake in the compilation of a central database of system events for analysis by or from the APM controller

### Alert

A warning that the central controller can raise when it ascertains that one or more of the resources being monitored have attained a specified, usually negative, condition, such as one of the following:

* The value of a metric being monitored that represents a **performance level has descended below a static baseline** amount set in advance
* The value of a metric representing an operating parameter (such as **CPU utilization**) or representing a midrange of tolerance levels (such as **network traffic**) **rises above or falls below a static threshold** set in advance
* The controller observes one or more operating parameters that collectively indicate a behavior has **fallen outside the tolerance range for "normal"**
* The controller detects that an **application has crashed** or is no longer responding to input

Alert is a **message intended to be delivered to a person**.

It typically **is not the job of an agent to send alerts**. Rather, it gathers the data for processing and analysis by another APM component, from which alerts may then be generated.

An **agent-based APM platform** is a **network messaging hub**. Machine data (the kind generated by machines, for machines) constitutes a majority of the data presently in use.

By establishing an effective network among server nodes dedicated to the task of maintaining service levels, the proper use of agent-based APMs may reduce the volume of machine data over time.

### 1.1 New Relic

The **New Relic monitoring platform**, now dubbed New Relic One, is one of many **agent-based monitoring tools** available on the market.

It makes every conceivable manageable component in a solution **visible**, **observable**, and **manageable**.

This platform utilizes the following classes of agents:

1. **APM agent** Gathers relevant data concerning the performance of a specific application. It may be installed alongside the application itself as a separate component and contacted via API. This is the preferred option for a program written in a compiled language such as C++. Optionally, it may be installed as a library or dependent code inside an application written in an interpreted language such as Java, Node.js, Python, or Ruby. This option has the virtue of more direct access to the functions and dependencies specified by the source code.
2. **Mobile agent** - A variant of the APM agent optimized for deployment on Android and iOS devices.
3. **Browser agent** - A segment or "snippet" of JavaScript code attached to a Web page by way of an HTML tag. This code contains instructions enabling a background **client-side app** to collect performance data generated by the browser, and periodically publish that data to the New Relic collector.
4. **Infrastructure agent**
    * Installed on a remote machine, or on the home server itself (either of which may be a VM) so that it's launched at startup.
    * This agent runs unattended and reports on the overall state of the **processor**, **memory**, **network** connectivity, and local **storage**.
    * The infrastructure agent gathers **metrics samples** over relatively non-intrusive intervals such as 5, 10, or 20 seconds.

A **New Relic agent** periodically (by default, each second) **sends packages** of **metrics** and **performance** data to a **central hub called the collector**, which is located inside New Relic's own private domain.

An **organization subscribing to New Relic One** may use either their own Web browser or New Relic's own browser to communicate with New Relic's servers, where data compiled by the collector has been stored for distribution to subscribers.

The platform's **reports**, **charts**, and **dashboards** are all **browser-based.**

**Insights** is New Relic's brand for the component

* Analyzes collected data
* Generates reports and alerts
* Projects dashboards

One of its more distinguishing features is its **service map** - an **updated graph** that **maps the active components** of a **Web application based** on a composite view assembled from the last half-hour's worth of snapshots taken by all the APM agents remotely monitoring the application.

## 2. Agentless Monitoring Platforms

The typical agentless monitoring tool or platform **relies on the current state of a server**, including the **system services that support its hardware** to provide the information the platform needs to ascertain its **operating status**, and to **determine** **whether** an event regarding that **status should be actionable**.

The most prominent of these services is **logging**.

For a **log** to be certified by standards organizations as auditable **each of its records must include** the following:

1. The **identity and/or type of each activity** performed that is relevant to the category of the log
2. The **identity of the owner of that activity**, or the authenticated source responsible for launching it
3. The **names of components or objects in the environment** affected by the activity
The time in which the activity took place
4. The **result of the activity** (what changed, if anything)

Each record needs to be presentable to a human operator in an intelligible manner.

* Some logs are stored in plain text, which is the most human-legible form, in which case a record may appear as one row in a multi-column table.
* Alternately, a record may be stored within a database in a compressed or abbreviated fashion
* With exclusive tags that represent objects such as identities.

In any event, either the record needs to be legible in its native form, or a log management platform should be capable of rendering that record intelligibly for human analysis.

### 2.1 Sumo Logic

Sumo Logic is one example of an agentless monitoring platform.

It is based on a concept it calls **machine data analytics**, which is centered on log management. Because most services and applications in a Linux-based server know to use **Linux' syslog utility** for generating logs in a proper format.

Sumo Logic:

* Can simply be **pointed to the right directory**
* Can **populate dashboards and generate reports**.

### Traditional Sumo Logic

* Use component called the **collector** which gathers data from logs and incorporates it into a database.
* Technically, the collector is an agent.

### Modern Sumo Logic

* Sumo Logic has been moving away from the agent-driven system, now offering instead a cloud-based service called the **hosted collector**.
* This is a **SaaS service** that **interacts with the on-premises** collector through the network.
* The analysis performed by the Sumo Logic platform begins with database queries conducted through its **Web-based console**.
* Inspired by **Hadoop** and its **MapReduce** algorithm, Sumo Logic uses proprietary algorithms that it calls **LogReduce** to look for ways to logically join related data together from separate log tables.
* A **custom query language** enables an IT operator to **retrieve records** from the database curated by the collector, **based on criteria** that can be expressed symbolically. For example, a query can retrieve records from multiple logs that all contain the word "SECURITY," expressed as *SECURITY* (with leading and trailing asterisks), and then group those records together according to a common field category. The result is a custom table containing events that might be flagged for later review by security personnel.

### 3. Tracing in Microservice Environments

With **microservices**, the code modules of an application become applications unto themselves, which interact with and pass control between one another through the network. To find one another, they may use raw IP addresses, but more likely they use a DNS server for service discovery, or they might make use of a service mesh to discover each other's identities and locations.

An **orchestrator** such as Kubernetes improves service levels by replicating as many of the individual microservices as the cluster needs to account for fluctuating traffic volume, and can then delete these replicas when traffic subsides.

Supporting a microservices environment with a **conventional monitoring** platform that observes events from the outside is like equipping a metropolitan area with a population of more than a million people with a single party-line telephone circuit. Theoretically it would work, given an infinite time constraint, but communications over such a system would be **unworkably slow**.

Consequently, **specialized APM platforms are available for monitoring microservice-based solutions**.

### 3.1 Prometheus

One of the first monitoring tools to address the requirements of a microservices environment was Prometheus.

* Instead, **rather than deploy app agents onto applications and portable functions** like a clandestine surveillance mission, **Prometheus relies on developers' abilities and willingness to build instrumentation into the source code of their containerized applications**. To that end, the team provides a **portable code library that developers include with their code**. Each instance of the library has its own local database, which serves as a kind of outbox for outgoing messages.
* **Rather than wait for messages to be sent**, or "pushed," in its direction, the **Prometheus server pulls** (or as some Prometheus engineers say, "scrapes") this local database for **time-series updates**. The Prometheus **server periodically determines whether alerts are warranted**, relying upon alerting rules established by an administrator.
* **Rather than publishing these alerts itself**, **it submits them to an independent alert manager**. Since messaging queues on distributed systems can be constructed any number of different ways, Prometheus opts not to re-invent the wheel. **Its alert manager is designed to be integrated with whatever queue or messaging service the organization already uses**. It prepares alerts for delivery and dispenses them accordingly.

## Integrated APM Platforms

Increasingly, cloud service providers such as Amazon and Microsoft offer native monitoring services that are integrated into their cloud platforms.

**Azure**, for example:

* Supports **Azure Monitor**, which comprises a set of services that developers and administrators can use to collect, analyze, and act upon telemetry regarding the performance of applications and the infrastructure that hosts them. Events emanating from applications, virtual machines, and other resources are logged and used to compute performance metrics.
* Various services such as **Azure Log Analytics** and **Microsoft Power BI** can be connected to the data sources where logs and metrics are stored to generate actionable insights and create visual dashboards.
* In addition, developers can instrument their applications with Azure **Application Insights** to generate custom telemetry. This provides an extra layer of monitoring that is application-specific and that can be extremely beneficial in diagnosing errors and their root causes -- often without having to dive into the source code.

**AWS** offers similar capabilities in the form of

* Amazon **CloudWatch**, which is a comprehensive monitoring service for AWS cloud resources and applications that run on AWS. Among other things, CloudWatch can be used to monitor CPU utilization on EC2 instances, collect metrics regarding AWS databases and storage volumes, monitor existing system and application logs for signs of trouble, and raise alarms when metrics exceed a specified threshold. You can also build custom workflows that automatically take actions you define when changes occur to a solution's AWS resources.

AWS and Azure users are not required to use CloudWatch and Azure Monitor; third-party APM platforms such as Relic One and Sumo Logic may be used instead. But the fact that CloudWatch and Azure Monitor are integrated into their respective platforms offers certain advantages, one of which is the ability to automatically scale cloud resources in response to events emanating from the monitoring service. It is a relatively simple matter, for example, to scale the number of VM instances when average CPU utilization falls outside a specified range. Such scaling can also be accomplished by using custom connectors to make the cloud platform aware of notifications from external monitoring platforms, but integrated monitoring reduces complexity by eliminating the need for such customizations.