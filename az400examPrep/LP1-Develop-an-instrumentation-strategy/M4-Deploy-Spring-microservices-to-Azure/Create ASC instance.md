# Create an Azure Spring Cloud instance

Using:

* Azure Portal
* Azure CLI

For Azure CLI need to install *spring-cloud* extension
> az extension add -n spring-cloud -y

## Creation

Naming convention (similar to storage account)

* Name must be **unique** among all ASC instances across all of Azure
* Allow only **lowercase letters, numbers, hyphens**.
* 1st character must be a letter
* last character must be a letter/number
* **4 to 32 characters** long

### Azure ACL command

> az spring-cloud create \
> -g resource-group-name \
> -n asc-instance-name \
> --sku standard \
> --enable-java-agent
