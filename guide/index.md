---
layout: default
title: Guide
nav_order: 2
has_children: true
---
# Guide

## Bot Event Handlers
Bot events are handler methods which are by default gets triggered whenever specific system event occurs. 

### onMessageReceive
*  This handler gets called whenever messages is recieved from user
```javascript
function onMessageReceive(){
	$.reply({
	    text :  {
	      body : "Hi, I am good how are you?"
	     }
	});
}
```

### onSessionStart
*  This handler gets called whenever new session starts
```javascript
function onSessionStart(){
	$.reply({
	    text :  {
	      body : "Hi, I am good how are you?"
	     }
	});
}
```

### onSessionRouted
*  This handler gets called whenever session is routed to current queue from different queue
```javascript
function onSessionRouted(){
	$.reply({
	    text :  {
	      body : "Hi, I am good how are you?"
	     }
	});
}
```

## Custom Event Handlers
Custom event handlers are the functions defined by developer to handle specific user response, at a specifc point in conversation.

### Resposne Listner
```javascript
function onMessageReceive(){
	$.reply({
	    text :  {
	      body : "Hi, I am good how are you?"
	     }
	}).listen(onResponseHandler1); // listner event handler is set
}
function onResponseHandler1(){
	$.reply({
	    text :  {
	      body : "Hi, I am good how are you?"
	     }
	});
}
```