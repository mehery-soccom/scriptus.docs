---
layout: default
title: $.rest()
parent : Guide
nav_order: 2
has_children: true
---
# Rest API
- Prepares make http calls to 3rd party url
{:toc}

## $.rest(options)
*  options.url - <font size="2"> end point URL to be hit</font>
*  options.headers <font size="1"> (optional)</font> - <font size="2">http headers to to passed </font>

```javascript
    $.rest({
      url : 'https://api.first.org/data/v1/countries',
      header : {
        'X-Amz-Target' : 'XAmzTargetValue'
      }
    });
```
### get(query)
<font size="2">It will execute prepared request with <i>GET</i> method</font>
  *  query - <font size="2"> query params</font>

```javascript
    $.rest({
      url : 'https://api.first.org/data/v1/countries',
    }).get({
      region : 'Africa'
    });
```

### post(json)
<font size="2">It will execute prepared request with <i>POST</i> method with <i>application/json</i> request body</font>
  *  json - <font size="2"> json body</font>

```javascript
    $.rest({
      url : 'https://api.first.org/data/v1/countries',
    }).post({
      region : 'Africa'
    });
```
### submit(fields)
<font size="2">It will execute prepared request with <i>POST</i> method with <i>application/x-www-form-urlencoded</i></font>
  *  fields - <font size="2"> map with fields values</font>

```javascript
    $.rest({
      url : 'https://api.first.org/data/v1/countries',
    }).submit({
      region : 'Africa'
    });
```

### json(handler)
<font size="2">Parse response as json and hand it over to handler</font>
  *  handler - <font size="2"> handler method</font>

```javascript
function onMessageReceive(){   
    $.rest({
      url : 'https://api.first.org/data/v1/countries',
    }).submit({
      region : 'Africa'
    }).json(myHandler);
}

function myHandler(json) {
  return $.reply({
    text : {
      body : json.toString()
    }
  })
}

```

