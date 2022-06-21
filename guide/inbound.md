---
layout: default
title: inbound
parent : Guide
nav_order: 2
has_children: true
---
# Inbound Message
- Inbound is global variable available to you read inbound details
{:toc}


## inbound.message
*  Complete message object. for complete structure [view InBoundMsg](https://docs.mehery.com/server-xms/public2/index.html?shell#tocS_InBoundMsg)


## inbound.contact
*  Complete contact object. for complete structure [view InBoundContact](https://docs.mehery.com/server-xms/public2/index.html?shell#tocS_InBoundContact)


## inbound.getText()
*  a shortcut for *inbound.message.text.body*

## inbound.getCode()
*  will return the *button code* selected by user.