# Use scaling up and scaling out in your architecture

## Scaling up or down

### Azure VM

In Azure virtual machines, you scale based on a virtual machine size.

### Azure SQL Database

Azure SQL Database is a platform as a service (PaaS) implementation of Microsoft SQL Server.
You can scale up a database based on the number of database transaction units (DTUs) or vCPUs.

* DTUs are an abstraction of underlying resources and are a blend of CPU, IO, and memory. For example, you could scale your database in Azure SQL Database from a size of P2 with 250 DTUs up to a P4 with 500 DTUs to give the database more throughput and capacity.

### Azure App Service

Azure App Service is a PaaS website-hosting service on Azure. Websites run on a virtual server farm, which is also known as an App Service plan.

You can scale the App Service plan up or down between tiers. You also have capacity options within those tiers. For example, an S1 App Service plan has 1 vCPU and 1.75 GB of RAM per instance. You could scale up to an S2 App Service plan, which has 2 vCPUs and 3 GB of RAM per instance.

## Scaling out or in

### VMSS

* Virtual machine scale sets let you create and manage a group of identical, load-balanced VMs.
* The number of VM instances can automatically increase or decrease in response to demand or a defined schedule.

### Azure SQL Database

You could share the load across database instances by sharding. Sharding is a technique to distribute large amounts of identically structured data across a number of independent databases.

### Azure App Service

Scaling out in this way means that you're increasing the number of virtual machines in the farm. As with virtual machine scale sets, the number of instances can be automatically raised or lowered in response to certain metrics or a schedule.

## Autoscale

* You can set a minimum and maximum threshold of instances.
* You can scale based on specific metrics like queue length or CPU utilization.
* You also can scale based on schedules.

## Considerations when you scale in and out

### State handling

When the application scales in, any state that was stored on the instance that's removed from your environment will be lost.

A common pattern is to externalize your state to another service, like Azure Cache for Redis or SQL Database, which makes your web servers stateless.

## Throttling

Use a throttling mechanism to **limit the number of requests from a source**.

Throttling is most frequently used in **applications that expose API endpoints.**

For example, if you exposed an API for customers to get data, you could limit the number of requests to 100 per minute. If any single customer exceeded this limit, you could respond with an HTTP 429 status code and include the wait time before another request can successfully be submitted.

## Serverless

Serverless computing provides a cloud-hosted execution environment that runs your apps but completely abstracts the underlying environment.

Create instance of the service > Add your code > execute > remove instance of the service

Serverless app runs only when it's triggered by an event, scaling and performance are handling automatically

Example of Serverless computing in Azure

* Azure Functions
* Azure Container Instances
* Azure Logic Apps

No infrastructure cost,  billed for the resources you use.

## Containers

A method of running applications in a virtualized environment.

### Virtual Machine VS Containers

* A **virtual machine** is virtualized at the **hardware level**, where a hypervisor makes it possible to run multiple virtualized operating systems on a single physical server.
* **Container** is virtualized at the **OS level**, which makes it possible to run multiple identical application instances within the same OS.

### Benefit of Containers

* Designed to be created, scaled out, and stopped dynamically as your environment and demands change.
* Ability to run multiple isolated applications on each virtual machine

Example of Container services in Azure

* Azure Kubernetes Service (AKS)
* Azure Container Instances
