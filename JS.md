``` js
// Fake data generator
const getItems = count =>
  Array.from({
    length: count
  }, (val, key) => key)
    .map(key => ({
      id: `item-${key}`,
      content: `item ${key}`
    })
  );
```
