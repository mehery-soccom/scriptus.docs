---
layout: default
title: Hello World
parent : Examples
nav_order: 2
has_children: true
---
# Hello World

```javascript

function onMessageReceive(){
  return $.reply({
    text :  {
      body : "Hi, I am good how are you?"
     }
  });
}


```