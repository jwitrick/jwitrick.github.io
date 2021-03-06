---
layout: post
title:  "Treating infrastructure as part of your application"
date:   2014-02-26 12:54:14
categories: jekyll update
---



How to treat infrastructure as code

What is infrastructure? Is it a piece of hardware that your application run on? Or is it a combination of hardware and software configured for a specific purpose?

That is a really simple question, right? Wrong. Since the beginning of software development until now there have been many different ideas, styles, and technologies. Before the idea was to connect to a mainframe and do your work, which changed into all the work being done on your local machine, which morphed again to using virtual machines, and most recently a move to a cloud server for better collaboration. Each time a change in development area changes its adopted to solve problems that have arisen from the previous areas. And after awhile the same type of issues arise, how to make the development area closer to production. 

Inevitably we will be working on server or environment that is not in the same state as the location where it will be deployed. The differences between different server states can cause issues down the road (deployment, maintenance, etc..).

How do we solve this? Should we always tear down our development environment after each? That is one solution. It would ensue that your development environment is clean and as close to production as possible (assuming its recreated in the same fashion production is deployed). Some downsides to it are that recreating the development environment is time consuming, takes time to tear down and recreate. Along that line of thought when a server is torn down there is a risk of other applications or servers that are actively communicating with servers within this environment, what happens to those servers? And finally what about the data within the development environment, can you afford to lose it?

Another solution is to treat the code that creates the servers are code itself. Start thinking about how the server is created/configured and not just about how the application run on the server. Stop assuming the hardware infrastructure is always in the latest state. Start ensuring it is in the latest good state.

I work on a team which utilizes the configuration management tool ‘Chef’ to handle the creating/maintaining servers and software deployed on those servers. The problem I have seen is when people start to fix a software defect, the mindset is to use existing development servers and start there. Why is this bad? Its bad because the last time that development server was updated using chef was 4 months ago, and there were a lot of updates to cookbook used to configure the server. By just jumping in and assuming the server is in the latest state, you will have started off on the wrong foot.

How can this be avoided? You can either do what was suggested above (tear down the development server and only re-create it when needed). Or you can extend the set of practices of your team to make them realize that the code which configures the servers is just as important as the software code itself. 

Make creating/updating the server the first step of any software development practice. In the long run, more people will understand how servers are configured, how software is running on the servers, and reduce the number of complications that can arise during deployment.

When approaching any bug fix, or feature request one of the first questions people need to answer is: “What state is the server in?” The easiest way to answer that question is to always spend a fee minutes and ensure your development server is in the same state as your production server. In my case, ensure the latest cookbooks are deployed on the server. If a problem is found with the state of the server and the latest cookbook release, don’t just hack the cookbooks until they work. Spend time understanding why, and understand that if a server is deployed by following one set of steps in production it MUST be done in the same way in development.

When transitioning to the ‘devops’ movement take a few minutes to learn from mistakes made by my team and me. Always treat your server as part of your application, and take time to ensure your server is always in the latest state.


[jekyll-gh]: https://github.com/jwitrick
[jekyll]:    http://jwitrick.github.io
