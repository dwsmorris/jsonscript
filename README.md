# PatternScript

PatternScript is an interpreted, embedded lisp for functional programming in JavaScript.

PatternScript ...

* ... is encoded in JSON string dictionaries
```
{   'myNumber'      : '4',
    'myString'      : '"hello"',
    'myBoolean'     : 'false'                         }
```
* ... uses prefix-notation S-expressions
```
{   'myCalculation' : '(- 10 (* 2 3))'     
    '(square x)'    : '(* x x)'                       }
```
* ... provides immutable value bindings
```
{   'myName'        : '"Darryl"',
    'greeting'      : '(+ "Hello " myName)'           }
```
* ... has access to all JavaScript operators and built-in functions
```
{   '(isTeen age)'  : '(&& (>= age 13) (<= age 19))',
    '(cubed x)'     : '(Math.pow x 3)'                }
```
* ... has access to any third-party libraries defined in your environment
```
{   '(sumTree tree)': '(_.sum (_.flattenDeep tree))'  }
```
