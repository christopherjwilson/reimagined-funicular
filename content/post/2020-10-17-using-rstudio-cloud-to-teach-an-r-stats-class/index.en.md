---
title: Using RStudio.cloud to teach an R Stats class
author: Christopher Wilson
date: '2020-10-17'
slug: []
categories:
  - R
  - Teaching
tags:
  - R
  - RStudio
  - rstudio.cloud
authors: []
featured: no
image:
  caption: ''
  focal_point: ''
subtitle: ''
summary: ''
---

I teach a research methods module that uses R for statistical analysis. As a keen user of R and RStudio, I had to decide the best way to deliver the course and how to ensure a straightforward and consistent experience for students, most of whom were new to R.

For the 2019-2020 academic year, we used rstudio.cloud, a cloud instance of R that is designed for collaboration and teaching. At the time, rstudio.cloud was in pre-release status and was free, so the trade-off was the potential for some bugs, but with no cost attached.

Why choose a cloud-based platform? Did it work? Would I use it again? Read on.

(This is not an advertorial. I don't work for RStudio and they don't know I'm writing this.)

## The problem with packages and IT security settings

A long time ago, (but not so long that I don't remember) universities used to be places of technological experimentation, where coding was a common skill and *nix operating systems were ubiquitous. 

Alas, this is no longer the case and computers are locked down for security purposes. This can be a barrier to students learning computer skills and plays havoc with tools like R, because package installation can be completely broken due to restrictions on a machine, even where R is installed. 

So frustrating is the experience of trying to use R on an institutional machine, that I just use my own laptop whenever I need to do anything research-related. This wouldn't do for teaching a class of 20 students, who - even if they have their own laptop - would have various operating systems etc., potentially requiring bespoke technical support, should any issues arise.

Enter RStudio.cloud, which seemed the perfect solution.

## It's R and RStudio in a browser!

One of the first things that struck me about using rstudio.cloud is that it's R and R Studio - in a web browser. If you are transitioning from the RStudio desktop version, you are immediately presented with the same layout and tools. It's full-fat, package-installing, graph-making goodness - no skimping.

## You can share collaborate and view students' work

Well, I say immediately, but that's not quite the case, because when you first login, you are presented with a dashboard that lists your __Workspaces__. For me a Workspace represented a course I was teaching: I added students to the workspace, within which I could create projects for each lesson. 

__Projects__ function very much like they do in the desktop app: you have a collection of scripts, files and potentially packages that are linked to a project. Projects exist independently of each other and have their own name, so I used a new project for each lesson. 

From the students' perspective, they can login, see the workspace I have added them to and create their own duplicate of any project I have created in the workspace. Their projects are visible to them and me (as the instructor) but once a project has been duplicated by the student, their copy is independent from the original - material the instructor adds later is not copied into project duplicates.

## It's an environment within an environment

The dashboard, with workspaces and projects etc., is what the user sees _before_ they enter the RStudio environment, which appears only when a project is opened. As well as workspaces and projects, the dashboard includes links to RStudio training materials and other resources. 

All of this is very useful, but is worth noting that this additional layer of interaction means that students who are completely new to R and RStudio will have to learn to manage and navigate the rstudio.cloud interface (duplicating projects etc.) at the same time as learning R and R Studio. It can be a lot to take in and definitely has an additional cognitive cost at the outset.

## _Almost_ everything works

Having said that, when you get down to working with RStudio, it's amazing how everything just works as you would expect. Install packages, write scripts, make graphs. The files are visible in the files tab and are saved in and accessed from rstudio.cloud's servers, so you need to upload and download to and from the cloud to get things in and out of the environment. It's as straightforward as it can be. I don't know, however, about encryption and security, so I have never uploaded sensitive data and only used the rstudio.cloud for teaching purposes.

There are a couple of things that I had trouble with though: the RQDA package has its own GUI interface for coding qualitative data - this package does not install due to dependancies that won't work in the browser (understandably). I also had issues with LearnR and some shiny stuff. I don't know if any of these things can or will be fixed due to the browser nature of rstudio.cloud, but I wouldn't call them deal-breakers.

## It's not built for speed

It's worth noting that rstudio.cloud won't run as fast as your desktop or laptop computer. I wouldn't run large simulations on this thing! It chugs a bit when installing packages and opening projects, but tends to work okay after it gets settled. Allow a few minutes for students to open projects, duplicate them and install packages if needed. For the basic work of writing scripts and running code, it works just fine.

## Now that it costs, the choice changes

As I mentioned, rstudio.cloud was free when I used it (for me and the students). Now that is not the case. It's understandable why a company needs to charge for a product. Moreover, I think this is a good product. However, I can't ask students to pay for an account and I can't guarantee that the free tier, with a limited number of hours and projects, will allow me to design and deliver the course in the same way I did previously.

One suggestion would be to buy an institutional license; but that is not as strightforward as it seems. Like many universities, mine has a license for SPSS. I teach many courses in SPSS but have been transitioning some of them to R because I think it will benefit the students to learn R. The main reason I can do this is because R and RStudio are free - I don't have to convince my university to pay for a license for another statistical analysis tool (rstudio.cloud) that, at the moment, only some people would use. 

If everyone were already using R, then transitioning to a cloud version for ease of deployment might be an easier sell. But then the university might want to install RStudio server edition, so everything stays in-house and the data are stored on their own servers (GDPR compliance). After all, if you are going to pay for a tool like RStudio, you want to be able to use it for more than just teaching.

## Conclusions

So, in the end, rstudio.cloud is a strange beast. It's a very good platform that does exactly what it says it will do. However, I don't know how I could recommend it to my fellow lecturer/professors to teach their class, when I know so many of them will likely be in the same position that I am in. If, on the other hand, it suits your needs, then definitely give it a try.
