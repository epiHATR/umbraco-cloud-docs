# Introduction
This repository contains documentations on How to use Umbraco Cloud Command Line Interface aka ```umbraco cli``` to interact with your Umbraco .NET Core project. <br/>
Umbraco Version v1.0.1 now support Umbraco 11 with .NET framework v7.0

## Table of Contents
- [Prerequisites](#prerequisites)
  - [Tools and CLI](#tools-and-cli)
  - [Azure account and Subscription](#azure-account-and-subscription)
- [Installation](#installation)
- [Usages](#usages)
  - [umbraco](#umbraco)
    - [umbraco version](#umbraco-version)
  - [umbraco account](#umbraco-account)
    - [umbraco account login](#umbraco-account-login)
    - [umbraco account set](#umbraco-account-set)
  - [umbraco project](#umbraco-project)
    - [umbraco project new](#umbraco-project-new)
    - [umbraco project list](#umbraco-project-list)
    - [umbraco project show](#umbraco-project-show)
    - [umbraco project delete](#umbraco-project-delete)
  - [umbraco deployment](#umbraco-deployment)
    - [umbraco deployment new](#umbraco-deployment-new)

## Prerequisites
### Tools and CLI
In order to run ```umbraco cli commands``` on your local machine or your build-agent like Github runner, Gitlab Runner, Azure DevOps build agent, you need to install following tools
- [az cli version 2.3+](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)
- [zip 3.0](https://stackoverflow.com/questions/18180060/how-to-zip-a-file-using-cmd-line)

### Azure account and Subscription
You are going to use ```umbraco cli``` to interact with your Umbraco .NET core project on Azure so you need to have:
- An active Azure subscription
- An account with Owner or Contributor on above subscription. You can also use service principal credentials to use with ```umbraco cli```

## Installation
Run following command to get ```umbraco cli``` up and running on your machine
```bash
#install umbraco cli command here
```
Run ```umbraco --help``` to get basic documentation of cli:
```bash
umbraco --help
```

## Usages
This section describe some basic command now supported by ```umbraco cli```. There're some flags supported in every commands as bellow:
```bash
--help   | -h           Show command and sub commands help text.
--debug  | -d           Show command logs and execution time.
--output | -o           Return output in specific format, support json, table, yaml, tsv.
--query  | -q           Query in result using JMESpath query.
```

### umbraco
### umbraco version
Show version of current ```umbraco cli```, it return supported umbraco version and .NET version as well.
```bash
umbraco version
#output
{
  "extensions": {
    "dotnet": ".NET V7.0",
    "umbraco-cms": "11"
  },
  "umbraco-cli": "v1.0.1"
}
```
### umbraco account
#### umbraco account login
You need to authenticate against the Azure Cloud environment to use the ```umbraco cli``` for project management or deployment purposes.
By default, the umbraco cli will utilize the current session of your az account on your machine. If you have logged in with ```az login --tenant```, you can now execute other umbraco cli commands without requiring an additional umbraco account login.

You can also use ```umbraco account login``` to change current session of your ```az cli``` by:
```
umbraco login --app-id clientId --app-secret clientSecret --tenant-id tenantID
```

#### umbraco account set
As described above, the ```Umbraco CLI``` uses the ```Azure CLI``` as a proxied command-line interface to interact with Azure. Therefore, you can also switch the current active Azure subscription using one of the following commands:
```bash
az account set --subscription myAzureSubscriptionID
#or
umbraco accoaunt set --subscription myAzureSubscriptionID
```

### umbraco project
#### umbraco project new
#### umbraco project list
#### umbraco project show
#### umbraco project delete

### umbraco deployment
#### umbraco deployment new