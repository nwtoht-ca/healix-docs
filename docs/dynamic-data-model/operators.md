---
sidebar_position: 3
---

# Operators, Constants and Literals

## Operators

Operators are thing like plus ``` + ``` or minus ``` - ``` to perform operations on data.  They follow the standard order of operations. E.g. multiplication is performed before addition and calculations in parenthesis ``` ( ) ``` are performed first.

<table>
  <tr>
    <th>Operator</th>
    <th>Comments</th>
  </tr>
  <tr>
    <td>+ - * /</td>
    <td>standard math operators</td>
  </tr>
  <tr>
    <td>()</td>
    <td>for controlling order of operations</td>
  </tr>
  <tr>
    <td>||</td>
    <td>logical or. e.g. true || false === true</td>
  </tr>
  <tr>
    <td>&&</td>
    <td>logical and. e.g. true && false === false</td>
  </tr>
  <tr>
    <td>!</td>
    <td>logical not  e.g. !true === false</td>
  </tr>
  <tr>
    <td>? : </td>
    <td>Conditional (ternary) operator - The conditional (ternary) operator is the only operator that takes three operands: a condition followed by a question mark (?), then an expression to execute if the condition is truthy followed by a colon (:), and finally the expression to execute if the condition is falsy. This operator is like an if...else statement. For example:
    <pre>
    (true ? "A" : "B") === "A"<br/>
    (false ? "A" : "B") === "B"
    </pre>
    </td>
  </tr>
  <tr>
    <td>==</td>
    <td>Type insensitive equality. Forgives differences in types. e.g. ("1" ==1) === true</td>
  </tr>
  <tr>
    <td>===</td>
    <td>Type sensitive equality.  Types matter. e.g. ("1"===1) === false</td>
  </tr>
  <tr>
    <td>!=</td>
    <td>Type insensitive non-equality. Forgives differences in types. e.g. ("1" !=1) === false</td>
  </tr>
  <tr>
    <td>!==</td>
    <td>Type sensitive non-equality.  Types matter. e.g. ("1"!==1) === true</td>
  </tr>
  <tr>
    <td>&gt; &gt;= &lt; &lt;=</td>
    <td>Greater than, greater than or equal, less than, less than or equal</td>
  </tr>
    <tr>
    <td>, &#x7b; } </td>
    <td>Separators. Commas , separate parameters to functions.  Some functions use braces &#x7b; } to group data elements</td>
  </tr>
</table>


<table>
  <tr>
    <th>Constant or Literal</th>
    <th>Comments</th>
  </tr>
  <tr>
    <td>12345.67</td>
    <td>Any constant number can be entered. can include exponential (e)</td>
  </tr>
  <tr>
    <td>"text"</td>
    <td>Any text constant can be entered (use only double quotes "</td>
  </tr>
  <tr>
    <td>true</td>
    <td>boolean value of true</td>
  </tr>
  <tr>
    <td>false</td>
    <td>boolean value of false</td>
  </tr>
  <tr>
    <td>undefined</td>
    <td>not defined - identical to Javascript undefined</td>
  </tr>
  <tr>
    <td>null</td>
    <td>null value - identical to Javascript null</td>
  </tr>
  <tr>
    <td>0xffff</td>
    <td>hex literals '0' [xX] [0-9a-fA-F]</td>
  </tr>
  <tr>
    <td>0o7777</td>
    <td>octal literals '0' [oO] [0-7]</td>
  </tr>
  <tr>
    <td>0b1111</td>
    <td>binary literals '0' [bB] [0-1]</td>
  </tr>
</table>
