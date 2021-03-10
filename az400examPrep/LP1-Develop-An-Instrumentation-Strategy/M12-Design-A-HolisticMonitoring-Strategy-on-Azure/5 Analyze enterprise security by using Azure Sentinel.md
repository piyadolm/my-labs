# Analyze enterprise security by using Azure Sentinel

## Criteria for assessing Azure Sentinel

You use Azure Sentinel if:

* You want a detailed overview of your organization, potentially across multiple clouds and on-premises locations.
* You want to avoid reliance on complex and disparate tools.
* You want to use enterprise-grade AI, built by experts, to identify and handle threats across your organization.

## 1. Connect your data sources

You create an Azure Sentinel resource in the Azure portal. The process for creating this resource involves creating a Log Analytics workspace, and then adding it to Sentinel.

### Data Connectors

You need to connect data sources for your enterprise. Sentinel integrates with:

* **Microsoft solutions** - including Azure Active Directory and Office 365
* **Non-Microsoft solutions** - Sentinel also has a **REST API** that allows you to connect to other data sources.

Use the Sentinel dashboard to view all of your data connectors.

When you connect the data source, **your logs will be synced to Sentinel**. You'll see a summary of the data that has been collected in the DATA RECEIVED graph for your connector. You'll also see the different data types that have been collected for the source. For example, the Azure Active Directory connector collects sign-in logs and audit logs for you.

## 2. Use alerts to monitor your enterprise

You can **configure alert rules** to investigate anomalies and threats more intelligently.

You can **respond** **manually** **or** by using **playbooks** for automated responses.

### Analytics

In the **analytics pane** of your Sentinel dashboard, you can **view all the rules that you have** in place. You can also **create new rules** there.

When you create a rule:

* Specify whether it should be enabled or disabled at the outset
* Specify the severity of the alert
* Rule query

## 3. Investigate incidents

Use the **Incidents pane** to see details about your incidents, such as how many you've closed and how many remain open. You also use the pane to find out when an incident happened and to determine its severity.

You select an incident to start to investigate it. You see information about the incident on the right side. Select View full details to get more information.

You see that multiple entities have been mapped to this incident. When you want to investigate an incident, you set its status from New to In progress and assign it to an owner.

### Investigate

You're then ready to investigate. When you select **Investigate**, you get an investigation map. You use the map to better understand what caused an incident and the affected scope. You also use the map to correlate data surrounding an incident.

The investigation map lets you drill down into an incident. You can, for example, get details about a user who is identified as part of the incident.

The investigation map also gives you a **timeline that helps you understand which event occurred at a particular time**. Use the timeline feature to understand the path that a threat might have taken over time.

## 4. Respond to threats with playbooks

Playbooks can help you automatically respond to threats in Sentinel. You create a new playbook through the Playbooks pane in your Sentinel dashboard.