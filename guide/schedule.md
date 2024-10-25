---
layout: default
title: $.schedule()
parent : Guide
nav_order: 13
has_children: true
---
# Organisation-Schedule APIs
- To access your organisation's schedule details
{:toc}


## $.schedule.isOn ( scheduleName )
Check whether the schedule is On.
*  scheduleName - <font size="2">Name of the schedule</font>

```javascript
function myHandler(){
    return $.schedule.isOn("Schedule 1").then(function (result) {
        if(result){
            // take action when schedule is On
        } else {
            // take action when schedule is Off
        }
    }
}
```