## String concatenation with binary +

Let’s meet the features of JavaScript operators that are beyond school arithmetics.

Usually, the plus operator  `+`  sums numbers.

But, if the binary  `+`  is applied to strings, it merges (concatenates) them:

    let s =  "my"  +  "string"; 
     alert(s);  // mystring
     
  Note that if any of the operands is a string, then the other one is converted to a string too.

    alert(  '1'  +  2  );  // "12" 
     alert(  2  +  '1'  );  // "21"

See, it doesn’t matter whether the first operand is a string or the second one.

Here’s a more complex example:

```javascript
alert(2 + 2 + '1' ); // "41" and not "221"
```

Here, operators work one after another. The first `+` sums two numbers, so it returns `4`, then the next `+` adds the string `1` to it, so it’s like `4 + '1' = '41'`.

```javascript
alert('1' + 2 + 2); // "122" and not "14"
```

Here, the first operand is a string, the compiler treats the other two operands as strings too. The  `2`  gets concatenated to  `'1'`, so it’s like  `'1' + 2 = "12"`  and  `"12" + 2 = "122"`.

The binary  `+`  is the only operator that supports strings in such a way. Other arithmetic operators work only with numbers and always convert their operands to numbers.

Here’s the demo for subtraction and division:

```javascript
alert(  6  -  '2'  );  // 4, converts '2' to a number
alert(  '6'  /  '2'  );  // 3, converts both operands to numbers
```

  Taks  in vs 


