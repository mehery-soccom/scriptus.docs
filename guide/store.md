---
layout: default
title: $.store
parent : Guide
nav_order: 3
has_children: true
---
# Read and Save Data
- Multiple apis to read and write data persitant data
{:toc}


## $.store.global ( ...keys )
global variables can be read using this api
```javascript
function myChanedMethod(){
    return $.store.global('key1','key2').then(function({key1,key2}){
      console.log(key1,key2);
    });
}
/// Alternativly

async function myChanedMethod(){
    let { key1 ,key2} = await $.store.global('key1','key2');
    console.log(key1,key2);
}
```

## $.store.data ( ...keys )
glbal variables can be read using this api
```javascript
function myChanedMethod(){
    return $.store.global('key1','key2').then(function({key1,key2}){
      console.log(key1,key2);
    });
}
/// Alternativly

async function myChanedMethod(){
    let { key1 ,key2} = await $.store.global('key1','key2');
    console.log(key1,key2);
}
```