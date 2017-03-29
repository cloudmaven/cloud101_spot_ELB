---
layout: break
title: "Introduction to the Google Cloud console & using the Compute Engine API"
teaching: 0
exercises: 30
questions:
- "How do I build a virtual machine in the Google Cloud?"
- "How do I transfer my data in and out of my virtual machine to external cloud storage"
objectives:
- "Learn to launch an GCP Compute Engine"
- "Learn to create a Google Cloud storage bucket"
- "Learn how to use the Google Cloud Shell SDK to transfer data from your Compute Engine to Google Cloud Storage"
- "Tips for navigating the Google Cloud console"
keypoints:
- We want to build launch a Google Cloud compute engine and transfer some data into storage.
- We will learn about the different available storage mechanisms on Google Cloud. 
- We will learn how to use the Google Cloud Shell
---

## Launch a Google Cloud compute engine
Like for AWS and Azure, we will be deploying a Google Cloud compute engine. We can deploy a GCP compute engine through the console or using Google Cloud Shell. The equivalent in GCP of the AWS or Azure CLI is called the gsutil. 

Once you sign in, this is what the console looks like - they call it the dashboard: 

![](/cloud101_cloudproviders/fig/03-gcp-intro-0001.png)

Select "Compute Engine" on the left hand menu 
![](/cloud101_cloudproviders/fig/03-gcp-intro-0002.png)

Next, create a small machine in the us-west1-a zone. For the boot disk, use a 25GB Ubuntu 16.04LTS disk. For identity management and API access, choose "Allow full access to all Cloud APIs". We are also going to allow full HTTP access. 

You can see the estimated pricing on the right hand side of the screen which is pretty nifty. 
![](/cloud101_cloudproviders/fig/03-gcp-intro-0003.png)

You can leave the other options as the default. At the bottom of the screen, instead of clicking on "Create" we are going to test out the gcloud command line. This will bring up the terminal in the browser. 
![](/cloud101_cloudproviders/fig/03-gcp-intro-0004.png)

![](/cloud101_cloudproviders/fig/03-gcp-intro-0005.png)

Check if the virtual machine has been provisioned by going to the Compute Engine dashboard. 
![](/cloud101_cloudproviders/fig/03-gcp-intro-0006.png)

![](/cloud101_cloudproviders/fig/03-gcp-intro-0007.png)

You can open an SSH terminal from your browser once you find your compute engine. 
![](/cloud101_cloudproviders/fig/03-gcp-intro-0008.png)

![](/cloud101_cloudproviders/fig/03-gcp-intro-0009.png)

You can also transfer files directly from your local machine to your compute engine - it's a little slow though!
![](/cloud101_cloudproviders/fig/03-gcp-intro-0010.png)

![](/cloud101_cloudproviders/fig/03-gcp-intro-0011.png)

For this tutorial, we are going to use the browser terminals -- you can still use your standalone terminal for this. 

If you are using a Google Compute Engine, which we are, gsutil is already installed. 

## Provision Google Cloud Storage



