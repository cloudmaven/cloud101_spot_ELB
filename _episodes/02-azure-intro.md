---
title: "Introduction to Microsoft Azure, Blob Storage and Virtual Machines"
teaching: 0
exercises: 30
questions:
- "How do I launch a virtual machine in Microsoft Azure?"
- "How do I use my virtual machine to transfer data to blob storage?"
objectives:
- "Learn to provision an Azure Virtual Machine"
- "Learn to create an Azure Blob Storage"
- "Learn to transfer data from the Azure VM to Blob Storage"
keypoints:
- "We will build an Azure Virtual Machine"
- "You get the picture"
---
## Prerequisites
- Sign up for a [Microsoft Azure account](https://azure.microsoft.com/en-us/free/?b=17.09b)

## Launch an Azure Virtual Machine

*This tutorial was adapted from https://docs.microsoft.com/en-us/azure/virtual-machines/windows/classic/tutorial*

Virtual machine > Add > Search for "Ubuntu" > Ubuntu 16.04 LTS (long term support) > Deployment type: Resource Manager

You can fill in the relevant information. We are going to go with using a password to log in this time, but it is probably more secure to use ssh-keygen to generate and ssh key. 

Create a new resource group 

We are going to go with the default options. 

If you click on the newly created Virtual Machine tab in the portal, you can view the configuration. One of the neat things with Azure is that you can specify your own DNS label name. Remember to save your configuration after you have edited it. 

## Create a blob storage
We will create an Azure storage account through the portal. 

In the portal, click the '+' sign for New > Storage > Storage Account
We are going to go with a standard disk because it's cheap. We will also use the Resource Group you created when you deployed your virtual machine. It is important to understand the [Data Replication options](https://docs.microsoft.com/en-us/azure/storage/storage-redundancy)


Now we will ssh into your Azure VM and set up the necessary tools for connecting to blob storage. Similar to what we did with the AWS tutorial -- we will ssh into the virtual machine and download and upload some files. This is necessary for the web frameworks tutorial. 

This time we will ssh using the administrator name, DNS label and password we specified in the Azure VM configuration. 

```bash
$ ssh -X -Y amanda@uwcloud101demo.westus.cloudapp.azure.com #substitute amanda and cloud101demo with your own username and DNS label
$ sudo apt update
$ wget 'https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh'
$ bash Miniconda3-latest-Linux-x86_64.sh
$ source ~/.bashrc
$ pip install --user azure-cli
```

Working with the Azure CLI. Note that there are also other ways to get your files in and out of blob storage including the Azure Storage Explorer app, Visual Studio and the web portal. Here we will use only the Azure CLI and authenticate it through the browser. 

```bash
$ az #to see all available options
$ az login #This will allow you to authenticate your Azure CLI through the browser window 
```

You should see something that looks like this:
![](/cloud101_cloudproviders/fig/02-azure-intro-0005.png)






## Transferring data from your virtual machine to your storage bucket
