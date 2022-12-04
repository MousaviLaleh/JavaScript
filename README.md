## JavaScript Fundamentals

## Counting Cards 
In the casino game Blackjack, a player can determine whether they have an advantage on the next hand over the house by keeping track of the relative number of high and low cards remaining in the deck. This is called Card Counting. <br/>
Having more high cards remaining in the deck favors the player. Each card is assigned a value according to the table below. When the count is positive, the player should bet high. When the count is zero or negative, the player should bet low.<br/>
<table>
  <tr>
    <th>Count Change</th>
    <th>Cards</th>
  </tr>
  <tr>
    <td align='center'>+1</td>
    <td align='center'>2, 3, 4, 5, 6</td>
  </tr>
  <tr>
    <td align='center'>0</td>
    <td align='center'>7, 8, 9</td>
  </tr>
    <tr>
    <td align='center'>-1</td>
    <td align='center'>10, 'J', 'Q', 'K', 'A'</td>
  </tr>
</table> 	            

You will write a card counting function. It will receive a card parameter, which can be a number or a string, and increment or decrement the global count variable according to the card's value (see table). The function will then return a string with the current count and the string Bet if the count is positive, or Hold if the count is zero or negative. The current count and the player's decision (Bet or Hold) should be separated by a single space. <br/>

**Example Outputs:**&nbsp; -3 Hold&nbsp; or&nbsp; 5 Bet 
<br/>

**Hint:** <br/>
Do NOT reset count to 0 when value is 7, 8, or 9.<br/>
Do NOT return an array.<br/>
Do NOT include quotes (single or double) in the output.
<br/>

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
Now let's try the code bellow:  <br/>
console.log(cc(7)); 
<br/>
you will get the result of :  0 Hold

<br/>

