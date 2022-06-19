---
layout: default
title: $.reply()
parent : Guide
nav_order: 2
has_children: true
---
# Reply Message
- Reply message to connected User
{:toc}


## $.reply(message)
*  message.text - <font size="2"> text reply to user</font>

### message.text
```javascript
$.reply({
    text :  {
      body : "Hi, I am good how are you?"
     }
});
```

### message.options.buttons
*  message.options <font size="1"> (optional)</font> - <font size="2">Provide reply options to User </font>

#### message.options.buttons.text
```javascript
$.reply({
    text :  {
      body : "Hi, I am good how are you?"
     },
     options : {
       buttons : [ "Good", "Bad" ] //Pass text as options
     }
});
```
#### message.options.buttons.code
```javascript
$.reply({
    text :  {
      body : "Hi, I am good how are you?"
     },
     options : {
       buttons : [
        { code : "good", label : "Good" },
        { code : "bad", label : "Bad" }
      ] //Pass text as options
     }
});
```
### next(handler)
*  handler - <font size="2"> handler responsible for handling next message from user</font>

### listen(condtions)
*  handler - <font size="2"> same as next() but with more options, can handover to multiple handlers based on conditions</font>
*   [See options](reply.listen.html)

