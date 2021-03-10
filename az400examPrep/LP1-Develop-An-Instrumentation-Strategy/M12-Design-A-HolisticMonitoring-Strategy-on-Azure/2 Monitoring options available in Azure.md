# Monitoring options available in Azure

## 1. What is Azure Security Center?

A service that manages the security of your infrastructure from a centralized location.

Security Center helps you deal with security challenges because it provides you with tools that:

* **Improve your protection against security threats**. Use Security Center to monitor the health of your resources and implement recommendations.
* **Ease the configuration of your security.** Security Center is natively integrated with other Azure services, such as **PaaS services** like Azure SQL Database. For IaaS services, enable automatic provisioning in Security Center.

## 2. What is Azure Application Insights?

You use Azure Application Insights to **monitor and manage the performance of your applications**. Application Insights automatically gathers information related to **performance, errors, and exceptions** in applications.

You also use Application Insights to **diagnose what has caused the problems** that affect an application.

## 3. What is Azure Monitor?

* Azure Monitor is the service for **collecting, combining, and analyzing data** from different sources.
* **All the application log data** that Application Insights collects is stored in a workspace that **Azure Monitor can access**.
* You'll then have a **central location to monitor** and analyze the health and performance of all your applications.
* Other services like **Security Center also rely on Azure Monitor**. Security Center, for example, collects security-related data from your virtual machines and other resources. Security Center stores this data in a workspace that you can access from Azure Monitor.

## 4. What is Azure Sentinel?

You use Azure Sentinel to collect data across your enterprise on:

* The devices
* Users
* Infrastructure
* Applications

### 4.1 Built-in threat intelligence

* Built-in threat intelligence for **detection and investigation** can help reduce false positives.
* **Proactively** hunt for threats and anomalies
* **Respond** by using orchestration and automation.

### 4.2 Data sources

You connect your data sources to Sentinel. These sources include:

* **Microsoft services** - such as Office 365 and Azure Advanced Threat Protection. 
* **External solutions** - such as AWS CloudTrail or on-premises sources. The dashboard shows detailed information collected from your sources.

### 4.3 Incidents

Incidents help you **group and combine alerts that are related**. You use incidents to reduce the noise generated because of the scale of the data. Incidents also help you to further investigate any anomalous activities or threats that have raised alerts.

### 4.4 Playbooks

Use playbooks to **automate your response to alerts** in Sentinel. You configure playbooks by using Azure Logic Apps. Your playbook details the steps to take when an alert is triggered in Sentinel.

### 4.5 Hunting queries

Use hunting queries to l**ook for threats across your enterprise before alerts are raised**. Microsoft security researchers maintain built-in hunting queries that act as a base for you to build your own queries.

### 4.6 Notebooks

Use notebooks to **automate your investigations**

Notebooks are **playbooks that can consist of investigation or hunting steps that you reuse** or share with others. Use Azure Notebooks for Azure Sentinel to develop and run your notebooks. For example, you might use the Guided hunting - Office365-Exploring notebook to hunt for anomalous activities in Office 365 across your enterprise.
