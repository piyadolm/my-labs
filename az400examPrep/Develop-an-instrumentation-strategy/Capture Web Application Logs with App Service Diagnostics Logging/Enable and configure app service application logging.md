# What are app logs?

App logs are the output of runtime trace statements in app code.

For example:

- Check some logic in your code by adding a trace to show when a particular function is being processed
- See a logged message when a particular level of error has occurred

App logging is primarily for apps in **pre-production** and for **troublesome issues**, because excessive logs can carry a performance hit and quickly consume storage. For this reason **logging to the file system is automatically disabled after 12 hours**.

App logging has scale limitations, primarily because files are being used to save the logged output.

The types of logging available through the Azure App Service depends on the code framework of the app, and on whether the app is running on a Windows or Linux app host.

## ASP.NET

ASP.NET apps only run on Windows app services, use the **System.Diagnostics.Trace** class.

Logging Level | System.Diagnostics.Trace  
------------ | -------------
Error | Trace.TraceError("Message");
Warning | Trace.TraceWarning("Message");
Information | Trace.TraceInformation("Message");
Verbose | Trace.WriteLine("Message");

## ASP.NET Core apps

ASP.NET Core apps can run on either Windows or Linux, use the **logger factory** class, and then use one of six-log levels:

| Logging Level | ASP.NET Core apps Logger Factory  | ASP.NET |
| ------------ | ------------ | ------------ |
| 5 - Critical | logger.LogCritical("Message"); | Error |
| 4 - Error | logger.LogError("Message"); | Error |
| 3 - Warning | logger.LogWarning("Message"); | Warning |
| 2 - Information | logger.LogInformation("Message"); | Information |
| 1 - Debug | logger.LogDebug("Message"); | Verbose |
| 0 - Detailed Trace | logger.LogTrace("Message"); | Verbose |

## Node.js apps

on Windows or Linux, app logging is enabled using the **console()** method:

- console.error("Message") - writes a message to **STDERR**
- console.log("Message") - writes a message to **STDOUT**

Both types of message are written to the Azure app service **error-level** logs.

## Logging differences between Windows and Linux hosts

### Windows apps

Windows apps benefit from a rich logging infrastructure because:

- Windows-based Web apps are a well-established Azure service
- Messaging for ASP.NET apps is tightly integrated with the underlying IIS service (
Azure Web apps use the Web server (IIS process)).

### Other apps

Logging options may be limited by the development platform, even when running on a Windows app service.

### Linux-base script apps

The logging functionality available to Linux-based scripted apps is determined by the Docker image used for the app's container.

- **Basic logging**, using redirections to STDERR or STDOUT, uses the Docker logs.
- **Richer logging** functionality is dependent on the underlying image.

To download equivalent Web application logging as provided by IIS for Windows apps, may require connecting to your container using SSH.

The following table summarizes the logging support for common app environments and hosts.

| App environment | Host | Error | Warning | Information | Verbose | Save to File System | Save to Blob storage |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| ASP.NET | Windows | Yes | Yes | Yes | Yes | Yes | Yes |
| ASP.NET Core | Windows | Yes | Yes | Yes | Yes | Yes | Yes |
| ASP.NET Core | Linux | Yes | - | -  | - | Yes  | - |
| Node.js | Windows | STDERR | Yes | STDOUT | Yes | Yes | Yes |
| Node.js | Linux | Yes | - | -  | - | Yes | - |
| Java | Linux | Yes | - | -  | - | Yes | - |

## Alternatives to app diagnostics

### Application Insights

Pros:

- A site extension that provides additional performance monitoring features
- Designed for **production** app deployments as well as being a potentially useful **development tool**
- Providing the same set of rich telemetry and performance data whether the app is ASP.NET or Node

Cons:

- Have to include specific code within your app
- Billable service

### Matrics

- Can help you profile how your app is operating
- Useful in **production**, as well as, **development**
- Can view **CPU, memory, network, and file system usage**
- Set up **alerts** when a counter hits a particular threshold
- Billing for metrics is covered by the app service plan tier

## Enable logging using the Azure portal

### Send logging to File System

Logging to the file system will be **automatically reset to Off after 12 hours**.

1. Navigate to your App Service in Azure Portal
2. Navigate to Diagonistic blade
3. Set **Application logging (Filesystem)** to **On**
4. Set the **Level** to Error, Warning, Information, or Verbose.

### Send logging to Blob storage

1. Navigate to your App Service in Azure Portal
2. Navigate to Diagonistic blade
3. Set **Application logging (Blob)** to **On**
4. Select a storage account and container, **must be same region with Web app**
5. Set the **Level** to Error, Warning, Information, or Verbose.
6. Set **Retention Period**, because log to blob will never been delete.

## Enable logging using the Azure CLI

The current version of Azure CLI does not enable you to manage app logging to blob storage. To enable app logging to the file system, run this command.
> az webapp log config --application-logging true --level verbose --name <app-name> --resource-group <resource-group-name>

For example, to enable logging to the file system for an app called contosofashions123, capturing all messages, run this command.
> az webapp log config --application-logging true --level verbose --name contosofashions123 --resource-group contosofashionsRG

There is currently no way to disable application logging by using Azure CLI commands; however, the following command resets file system logging to error-level only.
> az webapp log config --application-logging false --name <app-name> --resource-group <resource-group-name>

To view the current logging status for an app, use this command.
> az webapp log show --name <app-name> --resource-group <resource-group-name>