---
layout: default
title: $.wit()
parent : Integrations
nav_order: 3
has_children: true
---
# Rest API
- Prepares make API calls to wit service
{:toc}

### $.wit()
```javascript
///Chained Pattern
async function  onMessageReceive(){
  return $.wit()
              .message(inbound.getText())
              .then(function(resp){
              console.log("resp from with is",resp);
  })

// OR Async
async function  onMessageReceive(){
  let resp = await $.wit().message(inbound.getText())
    console.log("resp from with is",resp);
}
```


