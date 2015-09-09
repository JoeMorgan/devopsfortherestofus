---
layout: post
title: Guapo&#58; Devops Tooling for the Front-End
author: joe_carpenito
excerpt: "At Sapient Nitro, we're looking at utilizing elements of the devops toolkit to accelerate our work and improve quality and consistency between projects."
tags: [devops, front-end, docker, jenkins, tooling, testing, dashboards]
comments: true
---

## What the what?

As developers in a fast paced environment, we're asked to move around quite a bit. Task to task, project to project, toolset to toolset, environment to environment. This is a lot to ask! Typically each of us grows accustom to our own (clearly superior) tools and environments and we entrench ourselves in our ways. We wouldn't have to dive too far into this ideology to see how this is not so conducive to switching gears very quickly, but nonetheless we force ourselves to live with it. We learn new, but painfully similar tools. We stand-up and configure Apache, or Nginx with different configurations. We install, update, and roll back versions of Node.js, npm, Grunt, Gulp, Ruby, Sass, etc., etc., etc. until at last the code base we've checked out runs without error or warning. Often times this process must be repeated in some fashion to then setup a CI environment on a server. 

<figure>
	<a href="https://media.giphy.com/media/xkJ967hJt01gI/giphy.gif"><img src="https://media.giphy.com/media/xkJ967hJt01gI/giphy.gif"></a>
	<figcaption>"Could you hop over to this project for a couple days?"</figcaption>
</figure>

This is a whole lot of pain and besides, we're "developers," not "environment setter uppers." Surely there is something we can do to alleviate all of this?

## Enter El Guapo
Imagine a world in which you could download a lightweight (sub-100 line) configuration file, run a couple of commands, and in the time it takes your office [insert popular pod or packet based coffee dispensary brand name here] machine to make a cup of coffee, you have a completely installed, configured, and running dev environment ready to go. What's more, you've got unit, end to end, performance, and CSS regression testing built in! Right about now you're likely thinking; "This is the stuff of story book fantasies! Akin to dragons and unicorns!" Certainly, this would be fantastic, and fortunately for all of us, there is a way.

El Guapo is an ongoing project our development group has taken on to create a solution based more in reality than a dragon or unicorn. At it's core, it is a distributable Ubuntu environment running a pre-configured Apache installation, and already set up with many of the development tools we use in our day to day work (Node, npm, Gulp, Grunt, etc.). On top of this, the distribution ships with a toolset that is ready to be integrated with a given project. This toolset includes pre-configurations of Selenium and Nightwatch.js for unit and end to end testing, sitespeed.io for performance testing, and a modified installation of BackstopJS for CSS regression testing. All of these testing methods has accompanying dashboards for quick visibility into the status of a project.

So yes, this is definitely more real than a unicorn.

<figure>
	<a href="http://www.thisiswhyimbroke.com/images/unicorn-mask1.jpg"><img src="http://www.thisiswhyimbroke.com/images/unicorn-mask1.jpg"></a>
	<figcaption>"Hang on Bill, let me check my test coverage before we hit the bars."</figcaption>
</figure>

###Docker 

In order for all of this to be real, we need that crucial core functionality of the ability to quickly and easily distribute our environment. We found this solution in [Docker](https://www.docker.com/). You can get the complete description and ins and outs of Docker on their site, but for our purposes, it is a medium for running extremely lightweight VM's that can be heavily customized and built on command. There are three main concepts to internalize for the purpose of this explanation;

 1. Docker image - this is the instance of your environment, a pre-built installation with everyting you need to get going
 2. Docker container - when you run an image, you get a container, a running instance of your environment
 3. Docker file (Dockerfile) - this is the slimmest way to distribute an environment, it is the instruction set to build a Docker image

As a developer, one needs only pull down the El Guapo container from [Docker Hub](https://hub.docker.com/) and run it, or get the very lightweight Dockerfile, build the image, and then run it just the same. Once the container is running, Docker exposes and IP which makes the project and testing dashboards (hosted in the container) accessible via a local browser. 

It's worth noting at this point that Docker is used for a multitude of applications (pun intended) and further exploration of it is highly encouraged, but now that you've gotten the elevator speech on it, we take a look at El Guapo's toolbox.

###Standardized Tools and Testing

Our development group is a pretty diverse bunch, and with that diversity comes a wide variation in experience and exposure. In terms of testing, everyone is *familiar*, but it is not always put into practice on projects, and when it is, sometimes the coverage can become lax. Other times, it may not really make sense to have certain types of testing. A large scale web application might require **everything** to be tested, but a microsite with a four week development timeline, might just require some light end to end testing and performance testing. 

With El Guapo, a developer can choose what to use and when to use it. By simply making these tools available and easily accessible, a developer can make use of a little or as much testing as a project requires. This makes the toolbox a pretty powerful learning tool. Due to the "get your feet wet first" nature of the toolbox, someone can focus on learning a single aspect of testing, and grow into it as a practice over the course of a single, or many projects. 


<figure>
	<a href="https://media.giphy.com/media/RdAA6TFprPmsE/giphy.gif"><img src="https://media.giphy.com/media/RdAA6TFprPmsE/giphy.gif"></a>
	<figcaption>"This batch should be done testing after lunch."</figcaption>
</figure>

###Continuous Integration and server deployment

Finally, we want all of of our building and testing to happen automatically, both locally and on our servers. Well, since we have total control over our own environment, we can simply setup an instance of Jenkins in our Docker image and we're ready to go! The power this affords us is having a CI environment already setup for our front end that can be deployed on a server in the form of our Docker container. Too often we find ourselves wrestling with trying to get a new server environment setup to build our project (often remotely) and it's goes a lot like this:

<figure>
	<a href="https://media.giphy.com/media/PKgRu9KQuZpSg/giphy.gif"><img src="https://media.giphy.com/media/PKgRu9KQuZpSg/giphy.gif"></a>
	<figcaption>"Careful... Careful... Screw it."</figcaption>
</figure>

This allows us to both emulate very closely the actual server environment locally via Docker, and deploy much more quickly and frequently with Docker. This also makes getting our server set up initially much easier and faster.

##Putting it all together



