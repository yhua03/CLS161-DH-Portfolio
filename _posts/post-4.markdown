---
layout: post
title:  "Distant Reading"
date:   "2022-10-30"
categories: jekyll update
---

## Reading Reflection 3 - *Application Programming Interfaces (APIs)* ##

I first learned about the concept of API back when I took Comp 20 in my sophomore year.I've never heard of the term Named Entity Recognition before CLS161. I want to dedicate this reading reflection to these two topics and reflect upon what have I learned about API and NER and what are some interesting projects or applications that I can work with thw two mechanisms. 

First, let's start with API. To really conceptually understand API, I realized that it is crucial to review the architecture of API as client and server, or multiple of them. WHen an application sends a request, it is classified as the client, asking for some type of information or data. And to answer that request, the server sends something in response to the client. After a little bit of extra research into the topic, I learned that there are mainly 4 different ways that APIs can work:

1)SOAP APIs
Simple Object Access Protocol - Client and server exchange messages through the code format in XML, but SOAP APIs have not been as popular as it used to be as more advacned tech and models have been developed.

2)RPC APIs
Remote Procedure Calls - The communication between clients and servers are based on functions. So client needs to complete a request through some form of functions and the server will respond the output as the response to the clients

3)Websocket APIs
As one of the most modern API development, Websocket APIs use JSON objects to pass data. In addition, even when there's no request sent from the client, the server can send callback messages to connected clients, which is unique among other APIs.

4)REST APIs
Representational State Transfer - which is also the main tyype of APIs that I learned from COMP 20. There are pre-defined functions such as GET, PUT, DELETE, which makes client-server interactions to be very automatic and systemized. Most URLs use this sort of API interaction, and communication between server and the client is conducted using HTTP.
