## Introduction

Welcome to Azure Bicep workshop. 

Bicep is a domain-specific language (DSL) that uses declarative syntax to deploy Azure resources. In a Bicep file, you define the infrastructure you want to deploy to Azure, and then use that file throughout the development lifecycle to repeatedly deploy your infrastructure. Your resources are deployed in a consistent manner.

![Bicep processing](images/bicep-processing.png)

We are going to deploy a full stack application to Azure in multiple environments reusing Bicep templates.

**Learning objectives:**

* Infrastructure-as-Code 101
* ARM and Bicep
* Full stack app templates
* Authoring, best practices
* DevOps

**Prerequisites:**

* Fundamental cloud computing knowledge about Microsoft Azure
* Azure subscription (if you don't have, check how to [get started](https://azure.microsoft.com/en-us/free/))
* [Visual Studio Code (VSC)](https://code.visualstudio.com/) with [Bicep extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-bicep)
* Azure CLI version 2.35 (or above), [check how install ](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli)
* You can also install Bicep CLI manually as described [here](https://docs.microsoft.com/en-us/azure/azure-resource-manager/bicep/install#azure-cli), but Azure CLI should be able to do this once you execute command that needs Bicep transpiler

**Prerequisites checks:** 

We recommend to follow this workshop using Linux or MacOS terminal, for Windows users it's best to install [WSL](https://docs.microsoft.com/en-us/windows/wsl/install). Open up your VSC and using terminal window check the following:

```bash

# 1. Check version of the Azure CLI
az --version

# 2. Login to Azure Portal
az login

# 3. Create a resource group
az create group -g azure-bicep-worshop-rg -l westeurope

# 4. List resource groups (table output)
az group list -o table

# 5. Delete a resource group
az delete group -g azure-bicep-worshop-rg

```

Make sure all 5 steps from the above give no errors. If you have access to multiple Azure tenants and subscriptions, double check your workspace and set proper subscription so you won't get any surprises: 

```bash

# 1. List subscriptions (table output)
az account list -o table

# 2. Set an account (should be marked "True" in "IsDefault")
az account set -is <SubscriptionId>

```

## Author

Hi there 👋

I’m Evgeny Rudinsky, an Cloud Architect based in The Netherlands and author of this workshop. These days most of my work I do with Microsoft Azure and I’m certified Azure Solution Architect Expert, DevOps Engineer Expert, Azure Security Engineer, Azure Administrator Associate, Azure Developer Associate and Identity and Access Administrator Associate.

Follow me on [@evgenyrudinsky](https://twitter.com/evgenyrudinsky) and check [my blog](https://erudinsky.com/) if interested in Cloud Native, Automation and DevSecOps.