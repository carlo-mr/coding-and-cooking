---
layout: single
classes: wide
title:  "Accelerate - The Science of Lean Software and DevOps"
date:   2019-07-12 14:30:00 +0200
header:
  image: /assets/images/keyboard.jpg
  teaser: /assets/images/accelerate/teaser.jpg
sidebar:
  - image: /assets/images/accelerate/teaser.jpg
categories: coding
tags: architecture devops book 
excerpt: "My abstract of the Book: \"Accelerate - The Science of Lean Software and DevOps\""
---

![Accelerate Book Cover](/assets/images/accelerate/cover.jpg "Accelerate Book Cover"){: .align-center}


# Introduction

My first contact with the book "Accelerate -  The Science of Lean Software and DevOps" was at the W-Jax conference in 2018. I think it was [Eberhard Wolff](https://ewolff.com) who mentioned something in the lines of: 

_There are "good" organizations/teams, they deliver (to production) at least once per day and then there are the "bad" organizations that fail to do that._

He used Accelerate as reference for that statement.

That statement triggered something in me. On the one side I found it pretty hard to call organizations that are not able to deliver to production everyday "bad". On the other hand I thought it might be necessary to be this hard in the communication just to ensure people are actually listening. 
It's like if [Robert C. Martin](https://blog.cleancoder.com/uncle-bob/2014/12/17/TheCyclesOfTDD.html) would state _"It would be nice, if you as professional programmer, could be so kind and write some unit tests for your code"_ instead of _"You should not write a single line of prodction code without prior writing a failing unit test for it"._

# Software Delivery Performance

Now I finally had the time to read Accelerate.

Accelerate is a write-up of the ["Accelerate - State of DevOps"](https://puppet.com/blog-tags/state-devops) researches from 2013 - 2017 along with a deep-enough dive into the scientific methods used, to collect and interpret the data, to give confidence in the findings.

The first question answered in the book is how to actually measure software delivery performance.
The 4 measures selected by the researchers are: 

* Lead Time ("The time it takes to go from a customer making a request to the request being satisfied")
* Deployment Frequency ("A software deployment to production or to an app store")
* Mean Time to Restore
* Change Fail Percentage

Lead Time and the Deployment Frequency are considered measures of the _tempo_ of software delivery performance.

Additionally the researches wanted to investigate if tempo gains happen at the expense of the stability.
Acknowledging that failures in rapidly changing complex systems are inevitable the question _"How long it generally takes to restore service in case of an incident"_ was preferred to the standard measure of reliability (time between failures).

The final metric is what percentage of changes to production (software releases or infrastructure configuration changes) fail.

The analysis of the collected data regarding the software delivery performance revelead significantly different categories of performances:

| 2016                      | High Performers                      | Medium Performers                        | Low Performers                                   |
|---------------------------|--------------------------------------|------------------------------------------|--------------------------------------------------|
| Lead Time for Changes     | Less than one hour                   | Between one week and one moth            | Between one month and six months                 |
| Deployment Frequency      | On demand (multiple deploys per day) | Between once per week and once per month | Between once per month and once every six months |
| Mean Time to Restore      | Less than one hour                   | Less than one day                        | Less than one day                                |
| Change Failure Percentage | 0-15%                                | 31-45%                                   | 16-30%                                           |

One of the most interesting points I found in this book was that not only there is no trade-off between improving performance and achieving higher levels of stability and quality, but high performers do better _at all_ of these measures.
{: .notice--info}

# Key Drivers for Software Delivery Performance

Based on these findings the researchers were looking for key capabilties that drive software delivery performances.

What they found are 5 categories with a total of 24 key capabilities detailed below.

## Overview

* [Continous delivery](#continous-delivery)
  * Use version control
  * Automate your deployment process
  * Implement continous integration (CI)
  * Use trunk-based development methods
  * Implement test automation
  * Support test data management
  * Shift left on security
  * Implement continous delivery

* [Architecture](#architecture)
  * Use a loosely coupled architecture
  * Architect for empowered teams

* [Product and process](#product-and-process)
  * Gather and implement customer feedback
  * Make the flow of work visible through the value stream
  * Work in small batches
  * Foster and enable team experimentation


* [Lean management and monitoring](#lean-management-and-monitoring)
  * Have lightweight change approval processes 
  * Monitor across application and infrastructure to inform business decisions
  * Check system health proactively
  * Improve processes and manager work with work-in-progress (WIP) limits
  * Visualize work to monitor quality and communicate throughout the team

* [Cultural](#cultural)
  * Support a generative culture
  * Encourage and support learning
  * Support and facilitate collaboration among teams
  * Provide resources and tools that make work meaningful
  * Support or embody transformational leadership

## Continous delivery

### Use version control for all production artifacts

Although it might seem obvious to use version control for source code nowadays the researchers specifically mention to also have any configuration (system / application) and build or environment automation scripts under version control.

### Automate your deployment process

Computers should perform repetitive tasks so people can focus on solving problems. Therefore the less manual effort for deployments is needed the better it is. Also together with everything stored in version control it should be possible to easily replicate the production environment (without production data) in testing to be able to investigate errors.


### Implement continous integration (CI)

Integrating each persons work at least daily wiht a following build including tests reduces the risk of integration problems compared to long lived feature branches and allows teams to develop cohesive software more rapidly. See also [Martin Fowler on Continuous Integration](https://martinfowler.com/articles/continuousIntegration.html).


### Use trunk-based development methods

There should not be more than 3 active branches at a time and the branches should only live for a very short time (e.g. 1 day). This reduces the risk and time needed for merging. It also seem to encourage refactorings.   

### Implement test automation

Again repetitive tasks should be done by computers. A _reliable_ testsuite gives teams confidence that their software is releasable.It's worth investing ongoing effort in a reliable test suite (see also [Eradicating Non-Determinism in Tests](https://martinfowler.com/articles/nonDeterminism.html). Another important note here is that acceptance tests should primarily be created and maintained by developers. Tests created by QA or an outsourced party is not correlated with IT performance.
Testers are still essential though by performing exploratory, usability and acceptance testing and helping developers evolve the test suites.
Once automated tests should regularly be run to give developers feedback.

### Support test data management

To be able to run the automated tests it is important to have the correct test data. The management and the collection of necessary test data is therefore vital for smoothly running automated test suites.

### Shift left on security

Integrating feedback from information security teams early in the process e.g. during design or demos reduces the time needed to spend later on to fix security issues.

### Implement continous delivery (CD)

Continous delivery has positive impact on various aspects: delivery performance, quality, culture, reduced burnouts and deployment pain.
Although of course this comes not for free. A lot of things have to be automated, team interaction and ways of working have to be rethought.

## Architecture

The study found two architectural characteristics to be important for achieving high performance: 

* Can most of the testing be done without an integrated environment?
* Can an application be deployed independently of other applications/services it depends on?

### Use a loosely coupled architecture

Design systems that can be changed and validated independently. High performance teams require little communication between delivery teams to get their work done.

### Architect for empowered teams

Having teams to choose tools and frameworks from an approved list prevents teams from choosing technologies that will be most suitable for their practical needs and from experimenting (learning) with new approaches and paradigms.

What tools or technologies you use is irrelevant if the people who must use them hate using them, or if they don't achieve the outcomes they care about.

On the other side when tools provided make the engineers life actually easier, they will adopt them of their own free will.

## Product and process

### Gather and implement customer feedback

It is important to software delivery performance to actively gather customer feedback and to incorporate this in the design of the product.

### Make the flow of work visible through the value stream

Having a good understanding and visibility of the flow of work from business all the way to the customer has a positive impact on performance.

### Work in small batches

Work should be decomposed in samll features that can be completed in a week or less. This enables short lead times and faster feedback loops.

### Foster and enable team experimentation

Development teams shouild be empowered to try out new ideas and create or update specifications during the process without requiring approval from outside. When combined wuth working in small batches, custoemr feedback and making the flow of work visible this can have a huge impact on performance.

## Lean management and monitoring

### Have lightweight change approval processes

A change approval process based on peer review (code reviews / pair programming) results in a beeter performances than using change approval boards.

### Monitor across application and infrastructure to inform business decisions

Use monitoring data from instrastructure and applications to drive business decisions.

### Check system health proactively

Rate-of-change and threshold warnings in monitoring systems allow teams to preemptively detect problems.

### Improve processes and manager work with work-in-progress (WIP) limits

Visual WIP limits help drive process improvements, increase throughtput and makes constraints visible.

### Visualize work to monitor quality and communicate throughout the team

Software delivery performance is affected by visually displaying quality and WIP metrics.

## Cultural

### Support a generative culture (as outlined by Westrum)

A culture with good infortmation flow, high cooperation and trust, bridging between teams and conscious inquiry is predictive of IT performance.
Check here for more on the cultural model defined by [sociologist Ron Westrum](https://continuousdelivery.com/implementing/culture/).

### Encourage and support learning

A job is satisfying if it makes good use of skills and abilities. In an ever changing environment, with a lot of tasks being automated more and more, it is important to build new skills, learn new approaches and paradigms.

### Support and facilitate collaboration among teams

Improve the interaction of previously siloed teams like development, operations and information security.

### Provide resources and tools that make work meaningful

Another important point in job satisfaction is that the tools and resources needed to do the work are provided.

### Support or embody transformational leadership

Amplify the techincal and process work which is essential in DevOps. Five factors are key to this: Vision, intellectual stimulation, inspirational communication, supportive leadership and personal recognition.


The illustration of all the impacting factors can be seen below. (taken from [Overall Research Program](https://devops-research.com/assets/transformation_practices.pdf))

![Overall Research Programm](/assets/images/accelerate/overall-devops-research.png "Overall Research Programm")


_Teaser Photo from [Chuttersnap](https://unsplash.com/@chuttersnap)@[Unsplash](https://unsplash.com/search/photos/speed)_
