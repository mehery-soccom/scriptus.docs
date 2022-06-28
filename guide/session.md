---
layout: default
title: $.session()
parent : Guide
nav_order: 3
has_children: true
---
# Session Api's
- Method exposed trigger session apis'
{:toc}


## $.session.close ()
Closes the session and session will start from defautl assigned queue next time
```javascript
function myHandler(){
    return $.session.close();
}
```
## $.session.route ( options )
Sesison can be switched between multiple apps using routing api by providing *QueueCodes*
*  options.queue - <font size="2"> Target Queue where convesation should swith to.</font>
*  options.team <font size="1"> (optional)</font> - <font size="2">works only if options.queue is agent type </font>
*  options.agent <font size="1"> (optional)</font> - <font size="2">works only if options.queue is agent type </font>

```javascript
$.session.route({
  queue : "my_other_bot",
  params : {
    //Additonal params to send to next app
  }
});
```
### $.session.route.to.queue ( queueCode, params )
```javascript
$.session.route.to.queue("my_agent_app");

// Is short-cut for
$.session.route({
    queue : "my_other_bot",
});
```

### $.session.route.to.team ( teamCode )
```javascript
$.session.route.to.team("my_team_code");

// Is short-cut for
$.session.route({
    queue : "agent_desk", //Default agent queue
    team : "my_team_code"
});
```
### $.session.route.to.agent ( agentCode )
```javascript
$.session.route.to.agent("my_agent_code");

// Is short-cut for
$.session.route({
    queue : "agent_desk", //Default agent queue
    agent : "my_agent_code"
});
```