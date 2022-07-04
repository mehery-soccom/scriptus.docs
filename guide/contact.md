---
layout: default
title: $.contact
parent : Guide
nav_order: 11
has_children: true
---
# Contact Api's
- Method exposed to contact apis'
{:toc}


## $.contact.prefs.lang ()
Sets the language pregs for contact
```javascript
function myHandler(){
    return $.contact.prefs.lang('en_US');
}
```