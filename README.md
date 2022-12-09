# JavaScript Fundamentals

## Stand in Line
#### __ a code with Array and Function
In Computer Science a queue is an abstract Data Structure where items are kept in order. New items can be added at the back of the queue and old items are taken off from the front of the queue. <br/>
```
- Write a function nextInLine which takes an array (arr) and a number (item) as arguments.
- Add the number to the end of the array, then remove the first element of the array.
- The nextInLine function should then return the element that was removed.
```
**Solution :**

```
function nextInLine(arr, item) {
    // push the new item into the array
    arr.push(item);
    // show the removed item in the output
    return arr.shift();
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```
Your result would be:

```
Before: [1,2,3,4,5]
1
After: [2,3,4,5,6]
```

## Golf Code
#### __ a code with Array and IF statement
In the game of Golf, each hole has a par, meaning, the average number of strokes a golfer is expected to make in order to sink the ball in the hole to complete the play. Depending on how far above or below par your strokes are, there is a different nickname.<br/>
Your function will be passed par and strokes arguments. Return the correct string according to this table which lists the strokes in order of priority; top (highest) to bottom (lowest):
<table>
  <tr align='center'>
    <th>Strokes</th>
    <th>Return</th>
  </tr>
  <tr align='center'>
    <td>1</td>
    <td>"Hole-in-one!"</td>
  </tr>
  <tr align='center'>
    <td> <= par-2</td>
    <td>"Eagle"</td>
  </tr>
  <tr align='center'>
    <td>par-1</td>
    <td>"Birdie"</td>
  </tr>
  <tr align='center'>
    <td>par</td>
    <td>"Par"</td>
  </tr>
  <tr align='center'>
      <td>par+1</td>
      <td>"Bogey"</td>
  </tr>
  <tr align='center'>
      <td>par+2</td>
      <td>"Double Bogey"</td>
  </tr>
  <tr align='center'>
      <td> >= par+3 </td>
      <td>"Go Home!" </td>
  </tr>
</table> 	

**Note:** par and strokes will always be numeric and positive. We have added an array of all the names for your convenience.

**Solution :**
```
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  if (strokes == 1) {
    return "Hole-in-one!";
  } else if ( strokes <= par-2){
    return "Eagle";
  } else if (strokes == par-1) {
    return "Birdie";
  } else if (strokes == par +1) {
    return "Bogey";
  } else if (strokes == par +2) {
    return "Double Bogey";
  } else if ( strokes >= par+3){
    return "Go Home!";
  } else {
    return "Par";
  }
}
```
If you try this code bellow :

```console.log(golfScore(4, 6));```

you will get the result : &nbsp;**Double Bogey**



## Counting Cards
#### __ a code with Switch and IF statements
In the casino game Blackjack, a player can determine whether they have an advantage on the next hand over the house by keeping track of the relative number of high and low cards remaining in the deck. This is called Card Counting. <br/>
Having more high cards remaining in the deck favors the player. Each card is assigned a value according to the table below. When the count is positive, the player should bet high. When the count is zero or negative, the player should bet low.<br/>
<table>
  <tr>
    <th>Count Change</th>
    <th >Cards</th>
  </tr>
  <tr align='center'>
    <td>+1</td>
    <td>2, 3, 4, 5, 6</td>
  </tr>
  <tr align='center'>
    <td>0</td>
    <td>7, 8, 9</td>
  </tr>
  <tr align='center'>
    <td>-1</td>
    <td>10, 'J', 'Q', 'K', 'A'</td>
  </tr>
</table> 	            

You will write a card counting function. It will receive a card parameter, which can be a number or a string, and increment or 
decrement the global count variable according to the card's value (see table). The function will then return a string with the 
current count and the string Bet if the count is positive, or Hold if the count is zero or negative. The current count and the 
player's decision (Bet or Hold) should be separated by a single space. <br/>

**Example Outputs:**&nbsp; -3 Hold&nbsp; or&nbsp; 5 Bet 

**Hint:**

Do NOT reset count to 0 when value is 7, 8, or 9.<br/>
Do NOT return an array.<br/>
Do NOT include quotes (single or double) in the output.

**Solution :**

```
let count = 0; 
function cc(card) { 
  switch (card) { 
    case 2: <br/>
    case 3: <br/>
    case 4: <br/>
    case 5: <br/>
    case 6: <br/>
      count += 1; 
      break; 
    case 10: 
    case 'J': 
    case 'Q': 
    case 'K': 
    case 'A': 
      count -= 1; 
      break; 
  } 
  let result = 'Hold'; 
  if (count > 0) { 
    result = 'Bet'; 
  } 
  return count + " " + result;
}
```
<br/>
Now let's try the code bellow:

```console.log(cc(7));```

you will get the result : **0 Hold**

<br/>


## JavaScript Objects

### Using Objects for Lookups
convert  the switch statement into an object called "lookup". use it to look up "val" and assignt the strings to the "result" variables:

```
function phoneticLookup(val) {
  let result = "";
  switch(val) {
    case "alpha":
      result = "Adams";
      break;
    case "bravo":
      result = "Boston";
      break;
    case "charlie":
      result = "Chicago";
      break;
    case "delta":
      result = "Denver";
      break;
    case "echo":
      result = "Easy";
      break;
    case "foxtrot":
      result = "Frank";
  }
  return result;
}
```

**And the solution is:**

```
function phoneticLookup(val) {
  var result = "";
  var lookup = {
    "alpha" : "Adams",
    "bravo" : "Boston",
    "charlie" : "Chicago",
    "delta" : "Denver",
    "echo" : "Easy",
    "foxtrot" : "Frank"
  };
  result = lookup[val];
  return result;
}
```
If you check the code with the data below:
```
console.log(phoneticLookup("charlie"));
```
your result would be :&nbsp;  ```Chacago```

## Record Collection
### a code for JavaScript Objects
You are given an object literal representing a part of your musical album collection. Each album has a unique id number as its key and several other properties. Not all albums have complete information.<br/>

You start with an updateRecords function that takes an object literal, records, containing the musical album collection, an id, a prop (like artist or tracks), and a value. Complete the function using the rules below to modify the object passed to the function.<br/>
- Your function must always return the entire record collection object.
- If prop isn't tracks and value isn't an empty string, update or set that album's prop to value.
- If prop is tracks but the album doesn't have a tracks property, create an empty array and add value to it.
- If prop is tracks and value isn't an empty string, add value to the end of the album's existing tracks array.
- If value is an empty string, delete the given prop property from the album.

Note: A copy of the recordCollection object is used for the tests.

```
const recordCollection = {
  2548: {
    albumTitle: 'Slippery When Wet',
    artist: 'Bon Jovi',
    tracks: ['Let It Rock', 'You Give Love a Bad Name']
  },
  2468: {
    albumTitle: '1999',
    artist: 'Prince',
    tracks: ['1999', 'Little Red Corvette']
  },
  1245: {
    artist: 'Robert Palmer',
    tracks: []
  },
  5439: {
    albumTitle: 'ABBA Gold'
  }
};
 
function updateRecords(records, id, prop, value) {

.... your code here ...

  return records;
}
updateRecords(recordCollection, 5439, 'artist', 'ABBA');
```

**Solution 1 :**

```
function updateRecords(records, id, prop, value) {
  if (prop !== 'tracks' && value !== "") {
    records[id][prop] = value;
  } else if (prop === "tracks" && records[id].hasOwnProperty("tracks") === false) {
    records[id][prop] = [value];
  } else if (prop === "tracks" && value !== "") {
    records[id][prop].push(value);
  } else if (value === "") {
    delete records[id][prop];
  }
  return records;
}
```

__Solution 2 :__
This solution uses the fact that objects are stored as references to slightly simplify the solution syntax.

```
function updateRecords(records, id, prop, value) {
  // Access target album in record collection
  const album = records[id];

  // If value is an empty string,
  //  delete the given prop property from the album
  if (value === "") {
    delete album[prop];
  }
  // If prop isn't tracks,
  //  update or set that album's prop to value
  else if (prop !== "tracks") {
    album[prop] = value;
  }
  // If prop is tracks,
  //  add value to the end of the album's existing tracks array
  else {
    album["tracks"] = album["tracks"] || [];
    album["tracks"].push(value);
  }

  // Your function must always return the entire record collection object
  return records;
}
```

__Solution 3 :__

```
function updateRecords(records, id, prop, value) {
  if (value === '') {
    delete records[id][prop];
  } else if (prop === 'tracks') {
    records[id][prop] = records[id][prop] || [];  // this is called shortcircuit evaluation
    records[id][prop].push(value);
  } else {
    records[id][prop] = value;
  }
  return records;
}
```

__Code Explanation__
First checks if value is a blank string. If so, then the key (prop) is removed from the object.
If that first check doesn’t pass, it next checks if prop is equal to tracks. The tracks array is initialized if it does not exist, and then value is pushed into the tracks array. (This step uses shortcircuit evaluation)
If both these checks fail (meaning value is not an empty string and prop is not tracks), then either a new key (prop) and value (value) are added to the object, or an existing key is updated if the prop already exists.

__Example Run:__

updateRecords(5439, "artist", "ABBA");
<br/>
- value is not a blank string, so the first condition of the else if statement fails.
- prop is equal to “artist”, not “tracks”, so the second condition of the else if statement fails.
- in the ‘else’ clause, artist: "ABBA" is added to the 5439 id.


## While Loop
ou can run the same code multiple times by using a loop.
The first type of loop we will learn is called a while loop because it runs *while a specified condition is true* and stops once that condition is no longer true.
<br/>
```
const myArray = [];
let i = 5;
while (i >= 0) {
  myArray.push(i);
  i--;
}
```
The result of this code ```console.log(myArray); ```
is ``` [ 5, 4, 3, 2, 1, 0 ] ```
