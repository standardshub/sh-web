---
layout: post
title:  "Automatic GraphQL"
date:   2020-03-18 13:51:54 +0700
categories: resources
author: Sittichai Santiworakul
image: /assets/images/gallery/r5.jpg
---
This post, written by guest writer Fikayo Adepoju, was originally published on The New Stack here.<!--more-->

GraphQL is quickly becoming a preferred alternative to the traditional REST architecture API developers have been using for many years. It gives front-end developers the ability to query only what they need through a single endpoint. Because of its numerous benefits, back-end developers are adapting industry-standard strategies to ensure they build fluent and scalable APIs in GraphQL.

One of those standards is having a well-tested GraphQL API. In this post, we will take a look at how to test GraphQL APIs and automate the testing process with CircleCI.

Prerequisites
To follow along with this post, you will need the following already set up:

Basic knowledge of GraphQL
Node.js installed on your system (you can confirm this by running the node -v command on your terminal to print out the version of Node.js installed)
Git installed on your system (you can confirm this by running the git command on your terminal; this should print out available git commands)
A GitHub account
A CircleCI account
Creating the GraphQL server
Our first task is to set up a simple GraphQL server using Node.js. Create a folder for the project by running the following command: