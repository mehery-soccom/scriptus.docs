---
layout: default
title: $.google()
parent : Integrations
nav_order: 4
has_children: true
---
# $.google()
- Prepares make API calls to wit service
{:toc}

- Setup
1. Login to AdminPanel and go to Token & Keys &#8594; Add Variable
1. Add Google Clouse Perms Json and save.

### $.google.dialogflow.detectIntent(input)
- Is equivalent to [projects.agent.sessions.detectIntent](https://googleapis.dev/nodejs/dialogflow/latest/google.cloud.dialogflow.v2.Sessions.html#detectIntent1)
- returns standard google dialogflow detectIntent response

```javascript
///Chained Pattern
async function  onMessageReceive(){
  return $.google.dialogflow.detectIntent({
      queryInput: {
        text : {
          text: "hello there",
          languageCode: 'en-US'
        }
      }
  }).then(function(resp){
      console.log("resp from with is",resp);
  })
// OR Async
async function  onMessageReceive(){
  let resp = await $.google.dialogflow.detectIntent({
      queryInput: {
        text : {
          text: "hello there",
          languageCode: 'en-US' //opitonal
        }
      }
  });
  console.log("resp from with is",resp);
}
```


### $.google.dialogflow.intent()
- returns intent of current inbound message

#### Sample Code 
```javascript
///Chained Pattern
async function  onMessageReceive(){
  return $.google.dialogflow.intent()
    .then(function(resp){
      console.log("resp from with is",resp);
    });

// OR Async
async function  onMessageReceive(){
  let resp = await $.google.dialogflow.intent()
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
