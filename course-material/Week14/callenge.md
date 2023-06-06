# challenge



"" + 1 + 0
"" - 1 + 0
true + false
6 / "3"
"2" * "3"
4 + 5 + "px"
"$" + 4 + 5
"4" - 2
"4px" - 2
"  -9  " + 5
"  -9  " - 5
null + 1
undefined + 1
"apple" > "pineapple"
"2" > "12"
---


Use switch statement to determine the grade of the student depending on a given final mark.
Given :

finalMArk = 65

finalMark >= 90 console 'grade is A'
finalMark >= 80 console 'grade is B'
finalMark >= 70 console 'grade is C'
finalMark >= 60 console 'grade is D'
else console 'failed'
---

Use the `switch` case statement to write a script that outputs the number of days in a month based on the input month and year.

**Hint** 
There are four cases:

- If the month is 1, 3,5, 7, 8, 10, or 12, the number of days in a month is 31.
- If the month is 4, 6, 9, or 11, the number of days in that month is 30.
- If the month is 2, and the year is not the leap year, the number of days is 28. If the year is the leap year, the number of days is 29.
- If the input month is not in the range, the script jumps the default branch and sets the dayCount variable to -1 that indicates the invalid month.


and finally convert switch case to if statements
---

Using if..else, write the code which gets a number via prompt and then shows in alert:

1, if the value is greater than zero,
-1, if less than zero,
0, if equals zero.
In this task we assume that the input is always a number.
---

Rewrite this if using the conditional operator '?':
let result;

if (a + b < 4) {
  result = 'Below';
} else {
  result = 'Over';
}
---
Bonus : 
Rewrite if..else using multiple ternary operators '?'.

For readability, it’s recommended to split the code into multiple lines
let message;

if (login == 'Employee') {
  message = 'Hello';
} else if (login == 'Director') {
  message = 'Greetings';
} else if (login == '') {
  message = 'No login';
} else {
  message = '';
}
---
