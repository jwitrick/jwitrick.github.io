---
layout: post
title:  "How to start looking at configuration management"
date:   2014-11-26 12:01:14
categories: jekyll update
---

#How to start looking at configuration management

I wanted to take a few minutes to discuss how to get started with configuration management, and some thing’s to keep in mind when thinking about it. 

First I wanted to clear up a few misconceptions. The term and practice of configuration management does not mean less code; it does not mean less time spent maintaining it; and it does not mean its simple. The topic of configuration management should be approached like any other software development project. What does it solve? What does it need to do? Who are the consumers? These questions will help in selecting the tools used. For more specific information use the Wikipedia page (http://en.wikipedia.org/wiki/Configuration_management).

Once the scope is defined, the next important step is choosing a tool. The big tools available are Ansible, Chef, Puppet and, SaltStack (I wont go into detail about them as there are plenty of websites that have done some comparisons). Each tool has similar end results so knowing what you want out of configuration management will assist in choosing the correct tool for you.  Some questions to ask are:
```
*   How long will it take to get started on the tool?
*   How easy is the tool to use?
*   How easy is it to understand what the tool is doing?
*   How does it scale (100 servers, 1,000 servers, 10,000 servers, etc.)?
•   What is the community support?
```

Up until now I have been generic in how to approach configuration management, and the tools, now I am going to list out things that are important to me. I am going to look at the stability of the tool, the common usages, involvement of the community, and finally how does it scale.

##Stability and features:

First the tool should be well documented and stable. I should not have to constantly wait for the next release of the software for a feature that the other tools have had built in for years. I should trust the tools and their release cycle to know they are not releasing major issues. 

For example:
```
•   Ansible – 3 minor releases and many bug fixes
•   Chef – 8 minor version releases and a few bug fixes
•   Puppet – 3 minor releases and a few bug fixes
•   SaltStack – 7 minor release and many many bug fixes
```

##Documentation and usability:
 
Next I look at how the documentation (or community) says the tool should be used. If I find there are a lot of differences between them, then there is more time required to train people and maintain a consistent implementation. For me personally I want a simple command that can be run to execute the configuration process. This allows for simpler integration with orchestration tools. 

For example when looking at chef, the example usage is simple, “sudo chef-client” and that’s it, it does not matter if I am updating a single file, or deploying an entire new server it’s the same command, and when it finishes running I know the server is in the state I want it. 

On the flip side tools like Ansible, and SaltStack have the ability to run parts of their code at a time, while this is useful for only deploying a portion of the code, its has its drawbacks. It means different people can write code in different ways (no consistent usage), it means that if only part of the code is deployed then you cant say with 100% certainty what state your server is in.

##Community Involvement:

Community involvement is an important step being able to use someone else’s code to do the same thing allows for less custom code that needs to be maintained, quicker deployment and release time, and generally better stability overall. If there is a large community that releases and maintains common code, it means that more people have invested time in this product, like its usages, and want to make it better. 

For example:
```
•   Ansible has over 1,500 roles
•   Chef has 1, 800 cookbooks
•   Puppet has almost 2,900 modules
•   Salt has 150 community formulas
```
Which means that for ansible, chef or puppet for almost any piece of software I want to use there is a good possibility that someone has already created it. While salt is not yet up to that level.

##Scale:

How does the tool scale? For me to answer that question I do research on who is actively using the tool. What is the size of there company? How many servers do they run? What do they have to say about the tool? These are some basic questions, but they generally give me faith in my decision. 

For example:
```
•  Facebook has publicly said it uses chef to manage 150,000 servers across the globe, 
•  Shopzilla is running clusters in the thousands on puppet. 
```

When looking at the scale of the companies using the tools it shows both how well it scales, and how dedicated these companies are to the tool.

##Conclusion
In conclusion, after looking at the different criteria I have found that Chef and Puppet fit my needs the best. They are well documented, and maintained. They have been proven to scale exceptionally well, and there usages are somewhat fixed. I feel confident that new people to configuration management will find using Chef or Puppet to be easy to get started, easy to understand, and easy to use. 

