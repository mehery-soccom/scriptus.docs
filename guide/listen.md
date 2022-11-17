---
layout: default
title: $.listen()
parent : Guide
#grand_parent : Guide
nav_order: 2
has_children: true
---
# Listen to Inbound Message
- Listen to inbound message and decide flow
{:toc}

- Details
  - Listen to inbound message and decide new step
  - Sets the handler for next message from User, with more options to handover to multiple handlers based on conditions.

## $.listen ( defaultHandler )
*  defaultHandler - <font size="2"> default handler for user response</font>
```javascript
  // Listen to current inbound message
    $.listen(postCredit);
  // First reply and then Listen to current inbound message
    $.reply({
      text :  {
        body : `So you are ${inbound.getText()}`
       }
    }).listen(postCredit);
```

## $.listen ( conditions... )
*  condition.text <font size="1"> (optional)</font> - <font size="2">Match Exact Text </font>
*  condition.code <font size="1"> (optional)</font> - <font size="2">Match Button Code </font>
*  condition.pattern <font size="1"> (optional)</font> - <font size="2">Match with regex </font>
*  condition.handler - <font size="2"> handler for user response<</font>

####  Match Exact Text
```javascript
  $.listen({
    text : "Good",
    handler : goodHandle  //If answer is "Good"
  },{
    text : "Bad",
    handler : badHandle //If answer is "Bad"
  },otherHandle); // If answer is none of the above, this is default handler

```
#### Match with regex
```javascript
  $.listen({
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

####  Match Intent
```javascript
  $.listen({
    intent : "good",
    handler : goodHandle  //If intent is "Good"
  },{
    intent : "bad",
    handler : badHandle //If intent is "Bad"
  },otherHandle); // If answer is none of the above, this is default handler

```

