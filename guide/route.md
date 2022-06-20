---
layout: default
title: $.route()
parent : Guide
nav_order: 2
has_children: true
---
# Route Session
- Sesison can be routed between multiple apps using *QueueCodes*
{:toc}


## $.route ( options )
Sesison can be switched between multiple apps using routing api by providing *QueueCodes*
*  options.queue - <font size="2"> Target Queue where convesation should swith to.</font>
*  options.team <font size="1"> (optional)</font> - <font size="2">works only if options.queue is agent type </font>
*  options.agent <font size="1"> (optional)</font> - <font size="2">works only if options.queue is agent type </font>

```javascript
$.route({
  queue : "my_other_bot",
  params : {
    //Additonal params to send to next app
  }
});
```
### $.route.to.queue ( queueCode, params )
```javascript
$.route.to.queue("my_agent_app");

// Is short-cut for
$.route({
    queue : "my_other_bot",
});
```

### $.route.to.team ( teamCode )
```javascript
$.route.to.team("my_team_code");

// Is short-cut for
$.route({
    queue : "agent_desk", //Default agent queue
    team : "my_team_code"
});
```
### $.route.to.agent ( agentCode )
```javascript
$.route.to.agent("my_agent_code");

// Is short-cut for
$.route({
    queue : "agent_desk", //Default agent queue
    agent : "my_agent_code"
});
```