# Udacity-DevOps-Azure-Project-3 - Ensuring Quality Releases
CI / CD Test Automation Pipeline - Azure DevOps - Terraform - JMeter -Selenium - Postman

## Intro

* To use  a variety of industry leading tools, especially Microsoft Azure, to create disposable test environments and run a variety of automated tests with the click of a button.

![intro.png](./images/intro.png)

## Dependencies
| Dependency | Link |
| ------ | ------ |
| Terraform | https://www.terraform.io/downloads.html |
| JMeter |  https://jmeter.apache.org/download_jmeter.cgi|
| Postman | https://www.postman.com/downloads/ |
| Python | https://www.python.org/downloads/ |
| Selenium | https://sites.google.com/a/chromium.org/chromedriver/getting-started |
 

## Azure Resources
 - Azure Free account  
 - Azure Storage account (resource)
 - Azure Log Workspace (resource)
 - Terraform Service principle (resource)
 - Azure DevOps Organization ( https://azure.microsoft.com/en-us/services/devops/)
 - Azure CLI (resource)

## Steps

1. Clone this repo:

```sh
git clone https://github.com/jfcb853/Udacity-DevOps-Azure-Project-3
```

2. open a Terminal in VS Code and connect to your Azure Account and get the Subscription ID

```bash
az login 
az account list --output table
```

3. Configure storage account to Store Terraform state

* Execute the script **azure-storage-account.sh** :

```bash
./azure-storage-account.sh
```

* Take notes of **storage_account_name**, **container_name**, **access_key**

> storage_account_name: tstate3994
> container_name: tstate
> access_key: j/bg+StBWOPqf5fQCPF+tCLFeGURmKEnE675v4aVN1RzyUW3+wlFLrq/dTon4XPrCRKMl5/Z79qNRGR7ZHBPQw==

5. Create a Log Analytics workspace

```bash

```

4. To create a  Service Principal with **Contributor** role, perform the following steps:

```bash
az ad sp create-for-rbac --name="UdacityProject3" --role="Contributor" 
```

> Take notes of **appId**, **password**, and **tenant** as will be used later on terraform

6.  On your terminal create a SSH key

```bash
ssh-keygen -t rsa
cat ~/.ssh/id_rsa.pub
```

