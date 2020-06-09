---
layout: post
title:  "Continuous deployment for progressive web applications"
date:   2020-03-17 13:51:54 +0700
categories: blog
author: Sittichai Santiworakul
image: /assets/images/gallery/g4.png
---
Progressive web applications (PWAs) continue to gain widespread attention, <!--more-->acceptance, and compatibility with web browsers due to their native-like attributes. One of the mandatory security considerations to deploying these applications is that they must be hosted securely. Due to this, PWA features will not work on a non-secure URL, i.e. a URL that does not use the secure https:// protocol. In this post, we will be create an automated deployment pipeline that deploys our PWA to a secure URL on Firebase.

Prerequisites
To follow this post, a few things are required:

Basic knowledge of Javascript
Node.js installed on your system
An HTTP Server Module installed globally on your system (npm install -g http-server)
A Firebase account
A CircleCI account
A GitHub account
With all these installed and set up, let’s begin the tutorial.

Setting up the demo application
The first task is to create our demo application that we will be deploying to Firebase. Run the following commands to create a directory for the project and go into the root of the directory:

mkdir my-pwa-firebase
cd my-pwa-firebase
Next, let’s create our application home page. Create a file named index.html at the root of the project and paste the following code into it:

In the home page file above, we link to three files: manifest.json which we will use to set up the Add to Home Screen PWA feature, styles.css to apply some basic styling to our page, and app.js which will load in the service worker that we haven’t created yet, but will shortly. In the body of our page, we have a title that reads Welcome to the home of Dogs and below it, we display a list of dog pictures. As you can see, this is a dog site (apologies to the cat lovers).

The dog images are contained in an images folder at the root of the project. I have referenced the dog pictures in index.html according to the filenames used in images. Go ahead and create this folder, you can download dog pictures for free here and rename them appropriately.

Let’s add styles by creating the file styles.css at the root of our project and pasting the following code in it:

This file gives our page background color and makes the title text white. Let’s take our app for a spin by running the following command at the root of the project to invoke the global http-server module to spin up a local server to serve our app:

http-server
You will see a screen similar to the one below when you load the URL in your browser (your dogs will likely be different from mine):

