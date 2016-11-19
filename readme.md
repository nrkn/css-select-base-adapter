# css-select-base-adapter

Provides some base functions needed by a 
[`css-select`](https://github.com/fb55/css-select) adapter so that you don't
have to implement the whole thing.

## usage

```javascript
var baseAdapter = require('css-select-base-adapter');

var myAdapter = {
  // implementation here
};

var adapter = baseAdapter(myAdapter);

// use adapter with css-select
```

## how it works

An adapter for `css-select` requires the following functions to be implemented:

```
isTag, existsOne, getAttributeValue, getChildren, getName, getParent,
getSiblings, getText, hasAttrib, removeSubsets, findAll, findOne
```

You can pass this module a more minimal implementation and it will return a full 
adapter that fills in any missing functions, provided that you implement at 
least:  

```
isTag, getAttributeValue, getChildren, getName, getParent, getText
```

See the 
[`css-select` readme](https://github.com/fb55/css-select/blob/master/README.md)
for more information on the required function signatures.
