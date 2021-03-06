# Optimize network performance

In this unit, you'll learn about **the importance of network latency** and **how to reduce it within your architecture**.

## The importance of network latency

Network latency is the time that it takes for data to travel between a source to a destination across a network.

* Distance: Calls between services in different physical locations will still have network latency directly correlated to the distance between them.
* Number of round trips: depending on the communication needs of an application, more round trips might be required. Each round trip comes with a latency tax, and each round trip adds to the overall latency.

## 1. Latency between Azure resources

The goal here is to minimize the network latency between each layer of the application. How you'll improve your network latency depends on your application and data architecture. Azure provides mechanisms to resolve latency issues through several services.

## 2. Latency between users and Azure resources

You want to optimize delivery of the front-end user interface to your users.

### 2.1 Use a DNS load balancer for endpoint path optimization

You can create additional web front-end nodes for users around the world and let Azure Traffic Manager distribute load from users to front-end.

**Traffic Manager is a DNS-based load balancer** that you can use to distribute traffic within and across Azure regions.

* **Priority:** You specify an ordered list of front-end instances. If the one with the highest priority is unavailable, Traffic Manager routes the user to the next available instance.
* **Weighted:** You set a weight against each front-end instance. Traffic Manager then distributes traffic according to those defined ratios.
* **Performance:** Traffic Manager routes users to the closest front-end instance based on network latency.
* **Geographic:** You set up geographical regions for front-end deployments and route your users based on data sovereignty mandates or localization of content.

### 2.2 Use a CDN to cache content close to users

The static content can be delivered to users faster by using a content delivery network (CDN), such as Azure Content Delivery Network.

Content delivery networks can also be used to host cached dynamic content. Extra consideration is required though, because cached content might be out of date compared with the source. Context expiration can be controlled by setting a time to live (TTL). If the TTL is too high, out-of-date content might be displayed and the cache would need to be purged.

### 2.3 Use ExpressRoute for connectivity from on-premises to Azure

ExpressRoute is a private, dedicated connection between your network and Azure. It gives you guaranteed performance and ensures that your users have the best path to all of your Azure resources.
