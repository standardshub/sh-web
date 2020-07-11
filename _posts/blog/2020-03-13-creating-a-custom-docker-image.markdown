---
layout: post
title:  "Creating a custom Docker image to run your CI builds"
date:   2020-03-13 13:51:54 +0700
categories: blog
author: Sittichai Santiworakul
image: /assets/images/gallery/g6.png
---
guide provides tips on how to create an effective Docker image to be used as the primary image in the Docker executor. <!--more-->All steps within the job, including orb commands, will execute in this image. This guide does not, however, cover how to build and publish a Docker image that will then be used in your production environment or to distribute your open source application.

I’d like you to ask yourself, are you sure you want to do this? There are many people who don’t want to install a few packages at run-time because it will increase their build time by 20-45 seconds. They then invest several hours figuring out how to create their own Docker image, and then more time over months and years to maintain that image. Sometimes it’s not worth the effort.

In situations where lots of packages need to be installed, source code needs to be compiled, or downloads occur over slow connections, this is the sweet spot where your own custom Docker image will shine.

Still interested? Great, let’s get started.

Writing the Dockerfile
Everything begins and ends with the Dockerfile. It is the blueprint from which a Docker image is created. Visit Docker’s Getting Started - Part 2 guide for more information about the Dockerfile.

The base image

A Dockerfile typically starts with the FROM statement which declares the base image your new image will use. While in no way required, we strongly recommend using the CircleCI base convenience image as your base image.

FROM cimg/base:stable
The CircleCI base image serves as the base for all of the next-gen convenience images. You can learn more about all of the new images here. It’s designed from the ground up to work well on CircleCI. It has all the required tools, as well as the most common tools, that the majority of our customers need. For example, the checkout special step requires git to be installed in the Docker image. The save_cache and persist_workspace special steps, as well as their loading equivalents, require tar and gzip installed. Our base image includes all of these tools and we ensure that the list of software is maintained as additional requirements arise or are removed.

This image is also fairly popular on our platform which means there are cache benefits to be obtained by basing your image on our base image. You can learn more about the CircleCI base convenience image and how to use it on its GitHub page. If you choose to use a different base image, I’d suggest at least visiting the GitHub page to see what packages we install so you can copy that list for yourself.