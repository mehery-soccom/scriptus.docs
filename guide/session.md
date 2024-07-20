---
layout: default
title: $.session
parent : Guide
nav_order: 12
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

### $.session.route.to.skills ( skill_1, skill_2, skill3, ...skills_n )
```javascript
$.session.route.to.skills("orthos","dental");

// Is short-cut for
$.session.route({
    queue : "agent_desk", //Default agent queue
    skills : ["orthos","dental"]
});
```

## $.session.feedback ( options )
Save sesison feedback.
*  options.score - <font size="2"></font>
*  options.tag - <font size="2"></font>
*  options.review - <font size="2"></font>

```javascript
$.session.feedback({
  score : 5.0
});
```

### $.session.feedback.set.score ( value )
```javascript
$.session.feedback.set.score(5.0);

// Is short-cut for
$.session.feedback({
    score : 5.0
});
```

### $.session.feedback.set.tag ( value )
```javascript
$.session.feedback.set.tag("good");

// Is short-cut for
$.session.feedback({
    tag : "good"
});
```

### $.session.feedback.set.review ( value )
```javascript
$.session.feedback.set.review("It was very helpful");

// Is short-cut for
$.session.feedback({
    review : "It was very helpful"
});
```

## $.session.app.config ( options )
Get your app config.

```javascript
$.session.app.config();
```
