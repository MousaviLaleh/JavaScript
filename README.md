## JavaScript Fundamentals

## Stand in Line
#### __ a code with Array and Function
In Computer Science a queue is an abstract Data Structure where items are kept in order. New items can be added at the back of the queue and old items are taken off from the front of the queue. <br/>
```
- Write a function nextInLine which takes an array (arr) and a number (item) as arguments.
- Add the number to the end of the array, then remove the first element of the array.
- The nextInLine function should then return the element that was removed.
```
**Aanswer :**

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

**Answer :**
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
#### __ a code with Switch and If statements
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

**Answer :**

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


