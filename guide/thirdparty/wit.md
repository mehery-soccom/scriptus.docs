---
layout: default
title: $.wit()
parent : Integrations
nav_order: 3
has_children: true
---
# $.wit()
- Prepares make API calls to wit service
{:toc}

- Setup
1. Login to AdminPanel and go to Token & Keys &#8594; Add Variable
1. Add WIT.ai token and save.

### $.wit.message(text)
- returns standard wit.ai response

```javascript
///Chained Pattern
async function  onMessageReceive(){
  return $.wit.message(inbound.getText())
              .then(function(resp){
              console.log("resp from with is",resp);
  })

// OR Async
async function  onMessageReceive(){
  let resp = await $.wit.message(inbound.getText())
    console.log("resp from with is",resp);
}
```

### $.wit.intet()
- returns intent of current inbound message

#### Sample Code 
```javascript
///Chained Pattern
async function  onMessageReceive(){
  return $.wit()
              .intet()
              .then(function(resp){
              console.log("resp from with is",resp);
  })

// OR Async
async function  onMessageReceive(){
  let resp = await $.wit().intet();
    console.log("resp from with is",resp);
}
```
#### Sample response
```json
{ 
  intents : [{ name : "greetings"}],
  entities : [{name : "country",value : "india"}],
  reply : {
      text : "Hi there how can I help you?"
  }
}
```

