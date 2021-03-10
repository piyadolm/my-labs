# Unify monitoring solutions in Azure

## Criteria for assessing Azure Monitor

You use Azure Monitor if:

* You need a single solution to help you collect, analyze, and act on log data from both cloud and on-premises.
* You're using services such as Azure Application Insights and Azure Security Center. Those services store their collected data in workspaces for Azure Monitor. You can then use Azure Monitor Log Analytics to interactively query the data.

## Benefits of Azure Monitor

Azure Monitor centralizes and combines your metrics and log data from different sources.

Additionally, you can **run a single query over the logs collected from your services**. You can then analyze log data collected from several sources, and have a unified understanding of all of your data.

## Integration with Azure Security Center

Azure Security Center collects data from resources such as virtual machines by using the Log Analytics Agent.

The Log Analytics Agent can be installed automatically on all virtual machines. You'll need to set automatic provisioning to On in Azure Security Center under Settings - Data Collection.

From that point, your data will be stored in a Log Analytics workspace. A workspace is created for you, or you choose an existing one.

A workspace can be used with multiple subscriptions. You can gather data from machines across multiple subscriptions, and analyze it together from one central location.

You can analyze log data in workspaces by using Log Analytics. Log Analytics is an interactive tool in Azure that you use to write and test queries for your logs, and analyze results.

## Integration with Application Insights

Azure Application Insights and Azure Monitor come integrated. Y**our Application Insights data is collected and stored in logs that you can view and analyze by using Log Analytics**. You can open Log Analytics from Application Insights by selecting Analytics from the Overview pane of your application.
