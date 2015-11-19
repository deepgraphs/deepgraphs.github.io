# **DeepGraphs Core Specification**

## **Hypermedia Extensive Rules and Affordances Service Description Language**

* **Editor:** [Michael Petychakis](https://twitter.com/mpetyx), [National Technical University of Athens](http://www.ntua.gr/)
* **Created:** Monday, September 22 2014
* **Updated:** Thursday, October 30 2014

***

# Abstract
DeepGraphs is a simple format that gives a consistent and easy way to hyperlink between resources in your API and describe the possible workflows that the developer has predicted and allows for this. By specifying a number of concepts commonly used in Web APIs, as well as  it enables the creation of generic API clients.

Adopting DeepGraphs will make your API explorable, and its documentation easily discoverable from within the API itself. It will also enable all the DeepGraph clients to interact with it, while developers would have to configure them in a high level.

DeepGraphs is focusing on JSON-LD as it fits more natural to serialise the advanced rules that are going to be exchanged. Thus, all information could be encoded to RDF and treated accordingly.


# Status of This Document
This document is merely a public working draft of a potential specification. It has no official standing of any kind and does not represent the support or consensus of any standards organisation.

***

# Table of contents
1. [Introduction](#introduction) 
2. [Conformance](#conformance)
3. [DeepGraphs at a glance](#deepgraphs-at-a-glance)
4. [Using DeepGraphs](#using-deepgraphs)
5. [DeepGraphs Model](#deepgraphs-model)
6. [Example](#example)
7. [Libraries](#libraries)
8. [Acknowledgements](#acknowledgements)

## Introduction


## Conformance
This specification describes the conformance criteria for DeepGraphs API documentations and DeepGraphs clients. This criteria is relevant to authors, authoring tool implementers, and client implementers. All authoring guidelines, diagrams, examples, and notes in this specification are non-normative, as are all sections explicitly marked as non-normative. Everything else in this specification is normative.

The key words must, must not, required, shall, shall not, should, should not, recommended, not recommended, may, and optional in this specification have the meaning defined in [RFC2119](http://www.ietf.org/rfc/rfc2119.txt).


## DeepGraphs at a glance

DeepGraphs aims to be a specification for the Internet of Things. Its main goal is to stand as an interoperability layer between server and client implementations. This will happen through a specification that takes into account most of the behaviour in today's web and automate this. 

### Designing a new API
While designing a new DeepGraphs a API the developer has to bear in mind that first he needs to define a finite state machine of all the possible situations of the client server interaction.
To describe the API, any Hypermedia standard will work to show the map of all the possible paths that the client has to follow. This finite state machine is going to be encoded in [SWRL](http://www.w3.org/Submission/SWRL/) (maybe also [RuleML](http://ruleml.org/) is going to be supported in the future, or depending on the implementation).

### Designing a new client
Clients are a little bit different to what has already been widely adopted in the web nowadays. Clients are generic reasoners that depending on their goals, they follow the paths according to the event driven reasoning that has been sent to them by the server. They actually in practice consume all the map by the Hypermedia API and also they have the rules provided as a compass on what to do next at every moment.
Following this logic, DeepGraphs client could interact with several servers simultaneously or even implement combined transactions on those servers.

 


## Using DeepGraphs

## Background
In this section we are going to describe into more detail about the core principles behind DeepGraphs Specification.
If you would like to involve yourself deeper into the theory behind all this, you can read more at the [Theoretical Background](theoretical-background)

## DeepGraphs Model
The DeepGraphs conventions revolve around representing three simple concepts: Resources, Links and FSM.

### Resources

**Resources** have:

Links (to URIs)
Embedded Resources (i.e. other resources contained within them)
State (your bog standard JSON or XML data)

### Links

**Links** have:

A target (a URI)
A relation aka. 'rel' (the name of the link)
A few other optional properties to help with deprecation, content negotiation, etc.

### Finite State Machines

**Finite State Machines** have:

A series of steps
All possible scenarios from each situation
Error Handling in unforeseen situations

## The Structure of a DeepGraph Document

### Minimum valid document

A DeepGraph document must at least contain an empty resource.

An empty JSON object:

> {}

### Resources

> {}

### Links

> {}

### Finite State Machine

At the end of it, there is the Finite State Machine, in a SWRL format. This is recognised by 'fsm' tag. An empty such document will be like below.

```
{
"fsm": {
      #Rules
   }
}
```
### Example

For information into a more concrete example onto a whole DeepGraph document you can find [here](example)

## Libraries
Here there are going to be two lists. Since the DeepGraphs is a specification both for designing servers and clients, we are going to keep a list for server implementations and one for clients.

### Server Libraries

### Client Libraries


## Acknowledgements