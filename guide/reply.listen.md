---
layout: default
title: $.reply.listen()
parent : $.reply()
grand_parent : Guide
nav_order: 2
has_children: true
---
## listen
- Sets the handler for next message from User, with more options to handover to multiple handlers based on conditions.

### Wild-Card listner
```javascript
    $.reply({
      text :  {
        body : `So you are ${inbound.getText()}`
       }
    }).listen(postCredit);
```
### Match Based listner
#### Match Exact Text
```javascript
  $.reply({
    text :  {
      body : "Hi, I am good how are you?"
     }
  }).listen({
    text : "Good",
    handler : goodHandle  //If answer is "Good"
  },{
    text : "Bad",
    handler : badHandle //If answer is "Bad"
  },otherHandle); // If answer is none of the above, this is default handler

```
#### Match Text Pattern
```javascript
  $.reply({
    text :  {
      body : "Hi, I am good how are you?"
     }
  }).listen({
    pattern : /good/i,
    handler : goodHandle  //If answer is "Good"
  },{
    pattern : /bad/i,
    handler : badHandle //If answer is "Bad"
  }, otherHandle); // If answer is none of the above, this is default handler

```
#### Match Button Code
```javascript
  $.reply({
    text :  {
      body : "Hi, I am good how are you?"
     },
     options : {
       buttons : [
        { code : "good", label : "Good"},
        { code : "bad", label : "Bad"}
      ] //Pass text as options
     }
  }).listen({
    code : "good",
    handler : goodHandle  //If answer is "Good"
  },{
    code : "bad",
    handler : badHandle //If answer is "Bad"
  },otherHandle); // If answer is none of the above, this is default handler

```

