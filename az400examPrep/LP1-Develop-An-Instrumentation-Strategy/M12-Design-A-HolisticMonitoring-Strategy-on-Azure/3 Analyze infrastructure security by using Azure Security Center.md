# Analyze infrastructure security by using Azure Security Center

## Criteria for assessing Azure Security Center

You use Security Center if:

* You want to **identify and address risks and threats to your infrastructure**.
* You don't have the traditional in-house skills and capital needed to secure a complex infrastructure.
* You want to **secure an infrastructure** that consists of **on-premises** and **cloud** resources.

## Understand the security posture of your architecture

Security Center gives detailed analyses of different components of your environment. These components include:

* Data security
* Network security
* Identity and access
* Application security

This way, Security Center helps you understand the security of your architecture. You can then build and maintain better infrastructures.

### Recommends

Security Center recommends how to address the issues and risks that it has uncovered. You use recommendations like the following one to improve the security and compliance of your architecture.

## Protect against threats with Azure Security Center

Use **access and application controls** in Security Center to help protect your resources. These controls **block suspicious activity**.

For example, you protect your virtual machines through **just-in-time (JIT) virtual machine access**. JIT is a feature that blocks persistent access to virtual machines. Your virtual machines are only accessed based on audited access that you configure.

You can control which applications are allowed to run on your virtual machines through adaptive application controls.

You can configure adaptive controls by using the Adaptive application controls option under the ADVANCED CLOUD DEFENSE section of the Azure Security Center menu.

## Respond to threats with Azure Security Center

* You have the responsibility to **dismiss alerts** if no action is required, such as if there are false positives.
* You also need to **act to address known attacks** and block, for example, known malicious IP addresses. Also, you must decide which alerts require more investigation.

Security Center gives a **centralized view** of all of your security alerts. Security Center **ranks security alerts based on their severity**. Security Center also **combines related alerts** as much as possible into a single security incident.

### Playbooks

Playbooks are **automated procedures that you run against alerts**. You configure a playbook in the Playbooks pane of the Azure Security Center menu. You create a playbook by configuring a **logic app**.

### Threat Protection

View your security alerts through the Security alerts pane under the THREAT PROTECTION section on the main menu.
You drill down into specific security incidents by selecting an incident.
You can then choose to run your configured **playbooks** against your alert.
You can further investigate the alert by using the Continue investigation option. An **investigation map shows all of the entities that are related to this alert**.
