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
 
 // Usage
getItems(3);

// Returns
// [
//   {id: "item-0", content: "item 0"},
//   {id: "item-1", content: "item 1"},
//   {id: "item-2", content: "item 2"}
// ]
```

``` js
// A little function to help us with reordering the result
// (drag and drop 'item-0' to last position)
const reorder = (list, startIndex, endIndex) => {
  const result = Array.from(list);
  const [removed] = result.splice(startIndex, 1);
  result.splice(endIndex, 0, removed);

  return result;
}

// Usage
reorder(getItems(3), 0, 2);

// Returns
// [
//   {id: "item-1", content: "item 1"},
//   {id: "item-2", content: "item 2"},
//   {id: "item-0", content: "item 0"}
// ]
```

``` js
// Returns a random integer between min (inclusive) and max (inclusive)
// Using Math.round() will give you a non-uniform distribution
function getRandomInt(min, max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
}

// Usage
getRandomInt(1, 4);

// Returns 1, 2 or 3
```
