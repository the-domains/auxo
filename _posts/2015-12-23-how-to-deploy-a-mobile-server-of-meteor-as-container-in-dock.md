---
inFeed: true
hasPage: true
inNav: false
inLanguage: null
starred: false
keywords: []
description: ''
datePublished: '2015-12-23T23:32:15.429Z'
dateModified: '2015-12-23T22:42:42.154Z'
title: How to deploy a mobile server of meteor as container in docker
author: []
authors: []
publisher:
  name: null
  domain: null
  url: null
  favicon: null
sourcePath: _posts/2015-12-23-how-to-deploy-a-mobile-server-of-meteor-as-container-in-dock.md
published: true
url: how-to-deploy-a-mobile-server-of-meteor-as-container-in-dock/index.html
_type: Article

---
There are different solutions to run a meteor app as container in docker, one solution that works pretty well is provided by meteorhacks, the only problem is that you can add the platform android because when the image is running will ask for the ANDROID\_HOME env variable in the docker system, and installing and configuring all of that in a docker image is a tedious process you don't want to do. So in this tutorial we will learn how to deploy a meteor app with some some inline commands as:

For download meteor you can do it in this link or use the command for Mac and Linux:

Let's create a new project called meteor-mobile-server

When the project is created run the next command in the terminal

The app will run in http://localhost:3000 by default if you want to change that you have to add a env variable called ROOT\_URL=(value) Example:

Now we're going to install docker, you can see the install option in this link.

We're going to create two files one called Dockerfile in the root folder of the prject, and the other called meteor.sh in a new folder called deployenv/bin

In the Dockerfile we're going to add the next lines of code:

In the deployenv/bin/meteor.sh you can add the following lines of code:

We are setting the run variables as global env variables. Now we are going to build the app.

Once the build is completed we're going to run the container adding the global env variables.