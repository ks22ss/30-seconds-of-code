---
title: Object Key Value To Array
tags: array,object
firstSeen: 2023-01-31T21:36:00+08:00
---


Converts an object to arrays of objects that is assigned with new keys and the original key, value as new value.


- Use Object.keys() to return an array of keys of the given object.
- Use Array.prototype.map() to construct a new array of objects.
- Each object will have two new keys, where the first key will be the first argument and second key will be the second argument.
- Each object will have two new values, with the original key being the first value and the original value being the second value.


```js
const objectKeyValueToArray = (key1, key2, obj) => {
  return Object.keys(obj).map((key) => {
    const item = {};
    item[key1] = key;
    item[key2] = obj[key];
    return item;
  });
};
```


```js
const clients = {
  Tom: 'tom@email.com',
  John: 'john@email.com',
  Alex: 'alex@email.com'
};


objectKeyValueToArray('name', 'email', clients);
/*
[
  { name: 'Tom', email: 'tom@email.com' },
  { name: 'John', email: 'john@email.com' },
  { name: 'Alex', email: 'alex@email.com' }
]
*/


const products = {
  iPhone13: 699,
  iPhone14: 649,
  iPhone15: 799
};


objectKeyValueToArray('product', 'price', products);
/*
[
  { product: 'iPhone13', price: 699 },
  { product: 'iPhone14', price: 649 },
  { product: 'iPhone15', price: 799 }
]
*/
```
