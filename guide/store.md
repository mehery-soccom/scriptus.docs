---
layout: default
title: $.store
parent : Guide
nav_order: 13
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

## $.store.local ( ...keys )
local variables can be read using this api
```javascript
async function myChanedMethod(){
    let { key1 ,key2} = await $.store.local('key1','key2');
    console.log(key1,key2);
}
```

## $.store.local.set ( key, value )
local variable can be stored using this api
```javascript
async function myChanedMethod(){
    let key1 = await $.store.local.set('key1',"My Variable Value");
    console.log(key1);
}
```

## $.store.local.get ( key )
local variable can be read using this api
```javascript
async function myChanedMethod(){
    let key1 = await $.store.local.get('key1');
    console.log(key1);
}
```