---
layout: page
title: What Is Devops?
author: joe_morgan
tags: [devops, bizdevops, devops-lite]
comments: false
image:
  feature: night-lights-1.jpg
  credit: static.pexels.com
  creditlink: https://static.pexels.com/photos/370/lights-night-dark-abstract.jpeg
---

People have been defining and redefining devops for years. The intent here isn't to propose yet another definition, but to try to describe the thinking behind the modern devops movement and to provide a gentle introduction for those of you who are new to the topic. For you seasoned devops professionals, please jump in and correct me if I go astray.

It may be obvious from the word devops&mdash;technically called a <a href="https://en.wikipedia.org/wiki/Portmanteau" target="_blank" title="Wikipedia">portmanteau</a>, but I prefer "frankenword"&mdash;that this all started as a way to combine development and operations. To bridge the gap between coders and infra people. But why? What gap are we talking about?

##Build and Release##

At the risk of oversimplifying (and without getting into the historical details, best left to the pros at <a href="http://itrevolution.com/the-history-of-devops/" target="_blank" title="IT Revolution Press">IT Revolution Press</a>), it's about the old school build and release process, which kind of resembles this:
<figure>
	<img src="/images/build-and-release.jpg" alt="Soldiers (developers) throwing a hand grenade (code) over a wall at a target (IT operations)" />
	<figcaption>
		source of original image: <a href="https://upload.wikimedia.org/wikipedia/commons/e/e8/US_Navy_080123-F-1644L-044_A_Marine_assigned_to_the_3rd_Low_Altitude_Air_Defense_Battalion,_throws_a_M-67_Fragment_Grenade_at_the_firing_range.jpg" title="Wikimedia Commons">Wikimedia Commons</a>
	</figcaption>
</figure>

Developers throw code over the wall and, due to differences in environments (hardware, operating systems, configuration), it  often blows up in the infra teams' faces. Usually at the last minute in a release cycle, on a Friday, after the dev teams have all gone home. The developers are called back in to help fix things, fire drills ensue, fingers are pointed, code gets rolled back, and people generally have a horrible time.

Historically, the result of this is that deployments are done infrequently to minimize disruption; often quarterly, or even once or twice per year. But long build and release cycles mean that businesses struggle to be nimble, to respond to feedback from users, and to bring ideas from concept to fruition.

Given this, it shouldn't be surprising that, for many years, people have been looking for a better way to do things.

##Automation##

The rise of automation isn't exactly new. Developers have been using tools like Ant and Maven to improve build processes since the turn of the century (and before), and there are certainly analogs on the ops side. But it wasn't until tools were created to facilitate the *collaboration* of developers and IT operations staff that we started to see some real gains. The seminal example of this was the 2009 Velocity conference talk by John Allspaw and Paul Hammond, <a href="https://www.youtube.com/watch?v=LdOe18KhtT4" target="_blank" title="10+ Deploys Per Day: Dev and Ops Cooperation at Flickr">10+ Deploys Per Day: Dev and Ops Cooperation at Flickr</a>.

Since those early days, there has been an explosion of tools coming out of the devops movement. So many in fact that people keep coming up with new ways to keep track of and organize them all. The <a href="https://xebialabs.com/periodic-table-of-devops-tools/" target="_blank" title="Periodic Table of DevOps Tools">Periodic Table of DevOps Tools</a> by XebiaLabs is my current favorite.

And along with the popularity of these tools comes an increasing number of success stories from the companies that have embraced them (and, more importantly, the thinking behind them). Esty <a href="http://www.slideshare.net/beamrider9/continuous-deployment-at-etsy-a-tale-of-two-approaches" target="_blank" title="Continuous Deployment at Esty: A Tale of Two Approaches (on slideshare)">spoke at SWSX in 2013</a> about doing 25+ deploys per day (a number that has since doubled to more than 50 per day at QCon, London), while Amazon reports performing a production deployment every *<a href="https://www.youtube.com/watch?v=dxk8b9rSKOo&amp;feature=youtu.be&amp;t=10m8s" target="_blank" title="Velocity 2011: Jon Jenkins, &quot;Velocity Culture&quot;">11.6 seconds</a>*.

So the tools are obviously a means to an end. If the end in question is a deployment metric, then that should tell us something. What is a production release but the delivery of value from the business to the consumer?




<!-- bizdevops came up as early as 2012

1. To provide a brief introduction of devops, setting up the commonly accepted view of devops as automation of operations tasks and the cooperation of development and operations
2. To challenge and that definition by getting at the heart of what such automation seeks to accomplish
3. To ultimately broaden that definition to align better with the underlying principles of the devops movement
4. To hypothesize some of the types of applications that devops thought can have in other areas of business and life
5. To invite the audience to participate in the conversation, in the post comments and even by contributing to the github repo for the blog (link to the submit a post page)
6. References for further learning -->
