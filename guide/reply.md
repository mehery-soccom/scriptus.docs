---
layout: default
title: $.reply()
parent : Guide
nav_order: 2
has_children: true
---
# Reply Message
- Reply message to connected User
{:toc}


- Details
  - Reply message to connected User

## $.reply ( message )
*  message.text - <font size="2"> text reply to user</font>

### message.text
```javascript
$.reply({
    text :  {
      body : "Hi, I am good how are you?"
     }
});
```

### message.options.buttons
*  message.options <font size="1"> (optional)</font> - <font size="2">Provide reply options to User </font>

#### message.options.buttons.text
```javascript
$.reply({
    text :  {
      body : "Hi, I am good how are you?"
     },
     options : {
       buttons : [ "Good", "Bad" ] //Pass text as options
     }
});
```
#### message.options.buttons.code
```javascript
$.reply({
    text :  {
      body : "Hi, I am good how are you?"
     },
     options : {
       buttons : [
        { code : "good", label : "Good" },
        { code : "bad", label : "Bad" }
      ] //Pass text as options
     }
});
```

### message.template
*  message.template.code - <font size="2">Template code defined in Admin panel</font>
*  message.template.data <font size="1"> (optional)</font> - <font size="2">Data to be used in template</font>
*  message.template.lang <font size="1"> (optional)</font> - <font size="2">Language preference for code selection</font>

```javascript
$.reply({
  template: {
    code: "transaction_details",
    data: {
      amount: 10,
      currency: "INR"
    },
    lang: "en_US"
  }
});
```

### message.video
*  message.video.link - <font size="2">Url of video to be sent</font>
*  message.video.filename <font size="1"> (optional)</font> - <font size="2">Caption to be attached with video</font>
*  message.video.caption <font size="1"> (optional)</font> - <font size="2">Video File name </font>

```javascript
$.reply({
  "video": {
    "caption": "your-video-caption",
    "filename": "your-video-caption",
    "link": "http(s)://the-url"
  }
});
```

### message.image
*  message.image.link - <font size="2">Url of image to be sent</font>
*  message.image.filename <font size="1"> (optional)</font> - <font size="2">Caption to be attached with image</font>
*  message.image.caption <font size="1"> (optional)</font> - <font size="2">image File name </font>

```javascript
$.reply({
  "image": {
    "caption": "your-image-caption",
    "filename": "your-image-caption",
    "link": "http(s)://the-url"
  }
});
```

### message.document
*  message.document.link - <font size="2">Url of document to be sent</font>
*  message.document.filename <font size="1"> (optional)</font> - <font size="2">Caption to be attached with document</font>
*  message.document.caption <font size="1"> (optional)</font> - <font size="2">document file name </font>

```javascript
$.reply({
  "document": {
    "caption": "your-document-caption",
    "filename": "your-document-caption",
    "link": "http(s)://the-url"
  }
});
```

### message.audio
*  message.audio.link - <font size="2">Url of audio to be sent</font>
*  message.audio.filename <font size="1"> (optional)</font> - <font size="2">Caption to be attached with audio</font>
*  message.audio.caption <font size="1"> (optional)</font> - <font size="2">audio file name </font>

```javascript
$.reply({
  "audio": {
    "caption": "your-audio-caption",
    "filename": "your-audio-caption",
    "link": "http(s)://the-url"
  }
});
```

### .next ( handler )
*  handler - <font size="2"> handler responsible for handling next message from user</font>

### .listen ( condtions, ...)
*  handler - <font size="2"> same as next() but with more options, can handover to multiple handlers based on conditions</font>
*   [$.reply({...}).listen({},...)](listen.html)

