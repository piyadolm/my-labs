# Configure a Spring Cloud Config Server

**Spring Cloud Config Server** will be managed and supported by ASC, to be used by **Spring Boot microservices**.

Spring Cloud Config Server will get its configuration data from a Git repository, where Spring Boot configuration files will be stored.

* It allows storing sensitive parameters (like your database password) outside of your application.
* Your configuration is stored in a Git repository, so its data can be tagged or rolled back.
* It uses a specific Git repository, which can be secured separately.
* It provides a centralized place to store all your configuration data, for all your microservices.

## GitHub personal token

ASC can access Git repositories that are:

* Public
* Secured by SSH
* Secured by using HTTP basic authentication

For the last option, we need to create GitHub personal token, and select scope of token as entire "repo".

## Cofigure ASC to access Git repository

1. Go to Azure Portal
2. Go to overview page of your ASC server and select **"Config server"**
3. Configure the repository that we created

    * Add the repository URL
    * Add your branch in Label (default is main)
    * Click **Authentication**, select **HTTP Basic**
    * **Username** is your GitHub login name
    * **Password** is the **personal token**

4. Click on **Apply** and wait
5. Click on **Validate** and wait
