---
layout: single
classes: wide
title:  "The Duties of a Software Architect"
date:   2017-10-03 12:00:00 +0100
header:
  image: /assets/images/keyboard.jpg
  teaser: /assets/images/architect-duties/teaser.jpg
sidebar:
  - image: /assets/images/architect-duties/teaser.jpg
categories: coding
tags: architecture
excerpt: "A write up of the 6 duties of a software architect. Requirement clarification, Communication, Structure Design, Transversal Concepts Design, Implementation Accompaniment and Architecture Evaluation"
---
Last week I had the opportunity to attended the workshop “Mastering Software Architectures” by [Gernot Starke][gernot-starke] and [Peter Hruschka][peter-hruschka].
If you ever have the chance to have a training with the two you should take the opportunity!

In this post I want to recap the 6 duties that form the software architect role:

* Clarify requirements
* Communicate
* Design Structures
* Design transversal concepts
* Accompany the implementation
* Evaluate Architectures


These tasks do not follow any specific order are related to each other. During the project or rather product lifecycle they repeatedly occur.


# Clarify requirements
If you work in the software industry you will not be surprised that requirements are not always clear. You might ask why it is the architects task to clarify these. Don’t we have functional experts or similar which can nail the requirements? Generally yes. But thats no always the case. And also in good requirement documents there will be room for for assumptions.
Its the task of the architect to actively clarify and make things explicit.

Also software architecture should be adequate. To fulfill this the architect needs to clearly understand the requirements and then derive quality goals from these. The quality goals can later help to evaluate the architecture.

# Communicate
The architect is the role in a development team with the most interfaces/connections to other stakeholders. Therefore he needs to be able to communicate in a variety of “languages” and ways.
Being able to analyze a bug together with the developers in the code and then communicating the results to management is one example. The way the architect needs to talk to these different stakeholders are very different.

With the developers everything revolves around code. In which component/class is the bug? How can we fix it?

Management is (usually) not interested in the component that causes the bug. They need to know how much it costs. How many customers are concerned and how long it will take to fix it.

Also the architect should keep an eye on a up-to-date list of the stakeholders. So that he is aware of who to talk to for different topics. This list can and will evolve over time. I already mentioned two stakeholders but the list can be very long. Additionally to the management and the developers there usually are testers, operation people, security officers, customers, external partners and so on. Each of those should to be addressed slightly differently.
This aspect should also be reflected in the architecture documentation. A good architect clarifies with the relevant stakeholders what information they expect from the documentation and tailors the different parts to their needs.


# Design structures & transversal concepts
Designing the structure and finding/defining transversal or cross cutting concepts in the system is probably the main duty of the architect and has many dependencies to there other activities.

There are many ways to find out how to structure the system. None of them is the “correct” one, instead you should use multiple approaches and actively switch between those to see things from a different perspective. It can help to first start with a rough first idea about technical aspects and refine this over time iteratively. Also it can help to keep the quality goals in mind that have been deducted from the requirements, often these can give an orientation.

Some keywords that might help for the structure design process are:

* Top-Down, Bottom-Up
* Quality Driven Design
* Domain Driven Design
* Patterns

Concepts are aspects that affect multiple building blocks of an application and guide the implementation. They give a more general solution approach. Sometimes selected tools or frameworks come already with a set of concepts. The areas where concepts are applied are diverse.
It could be the way persistence is handled in the system, or logging, transactions, security and many more.
The documentation for concepts should answer the following questions:

* Why is a problem solved using a distinct concept?
** Show the purpose
* What is the concept?
** Be very detailed
* How is the concept applied?
**Show examples, a prototype, code snippets


# Accompany the implementation
A critical duty is to accompany the implementation in order to ensure that the decisions taken are also reflected in the code (at different levels). 
A close follow-up also allows to adjust when it shows that decision should be reconsidered. Generally the architectural tasks are to be handled iteratively. Trying things out, gathering feedback and then (if necessary) adjusting is important.
There are a lot of ways for the architect (or the team) to follow-up during the implementation:

* Code reviews
* Code analysis
* Pair/Mob Programming
* A Definition of Done
* Coding guidelines
* …

# Evaluate Architectures
The evaluation of software architecture can either be done quantitatively or qualitatively.

Quantitatively means that the software is mapped to numbers. There are different measures that can be chosen. Lines of code, complexity, coupling of different components, resource consumption and many more.
It is advisable to combine multiple measures to find hotspots in the code.

Qualitative evaluation tries to identify risks regarding the quality goals of an architecture and the interplay of different quality goals.
Therefore the chosen quality goals are refined with concrete scenarios. For each of the quality goals a possible implementation approach is selected.
Then the documentation and the code of the software is taken and evaluated against the scenarios and implementation approaches.
The outcome of this is a subjective evaluation which should help to identify which of the quality goals might be at risk.

The overall outcome of the assessment can be taken as input for other architectural tasks.

# Two more things
To conclude I want to highlight not all of the different duties need to be done by the same person in the team. The role of the architect can (and should) be spread across the team. Generally there will still be one person that takes the responsibility for the taken decisions – you could call that person the “Chief Architect”.

As the architect should take responsibility for the system (that it is build correctly and with the correct quality measures), he should also be involved (or involve himself) in different processes. For example the employee or tool selection processes. Furthermore he should have the competency to take design decisions – how can he take responsibility for decisions otherwise.


_Teaser Photo from [Pexels][pexels-teaser]_

[gernot-starke]: http://gernotstarke.de/
[peter-hruschka]: http://www.peterhruschka.eu/
[pexels-teaser]: https://www.pexels.com/de-de/foto/arbeit-arbeitsplatz-buro-business-273222/
