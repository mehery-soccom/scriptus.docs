---
layout: default
title: Introduction
nav_order: 1
has_children: true
---
# Introduction

Welcome to our Scriptus - a tool that enables you to write your own bot with minimum code.


### Bot Script
Piece of code which handles spcific part of conversation based on pre-decided or user inputs


### Handlers
When a *User* interacts with a *BOT*, it raises an **Event**. When an event occurs during BOT conversation, system invokes certain functions based on these events. So, how does the _System_ know when to execute the mentioned function or code? The event handlers handle this. The event handlers are the functions defined in _BOT Script_ which are specialized in a certain type of data or focused on certain special tasks and manage how the element should react to a specific event. 

> User &rarr; System &rarr; Event &rarr; Handler 

There are two type handlers
* [Bot Event Handler](guide/#bot-event-handlers)
* [Custom Event Handler](guide/#custom-event-handlers)