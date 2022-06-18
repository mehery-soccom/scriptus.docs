---
layout: default
title: options
parent : Examples
nav_order: 2
has_children: true
---
## options

### buttons
#### text
```javascript
$.reply({
    text :  {
      body : "Hi, I am good how are you?"
     },
     options : {
       buttons : ["Good","Bad"] //Pass text as options
     }
});

```
#### code
```javascript
$.reply({
    text :  {
      body : "Hi, I am good how are you?"
     },
     options : {
       buttons : [
        { code : "good", label : "Good"},
        {code : "bad", label : "Bad"}
      ] //Pass text as options
     }
});

```

