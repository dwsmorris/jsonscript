# JsonScript

... is encoded in JSON string dictionaries
```
{   'myNumber'                      : '4',
    'myString'                      : '"hello"',
    'myBoolean'                     : 'false'                                               }
```
... uses prefix-notation S-expressions
```
{   'myCalculation'                 : '(- 10 (* 2 3))'     
    '(square x)'                    : '(* x x)'                                             }
```
... provides immutable value bindings
```
{   'myName'                        : '"Darryl"',
    'greeting'                      : '(+ "Hello " myName)'                                 }
```
... has access to all JavaScript operators and built-in functions
```
{   '(isTeen age)'                  : '(&& (>= age 13) (<= age 19))',
    '(cubed x)'                     : '(Math.pow x 3)'                                      }
```
... has access to any third-party libraries defined in your environment
```
{   'sumTree'                       : '(_.compose _.sum _.flattenDeep)'                     }
```
... supports array and object literals
```
{   'integerArray'                  : '([] 1 2 (+ 1 2) 4)',
    'object'                        : '({} "four" 4 "tree" ([] "leaf" ([] "leaf" "leaf")))' }
```
... automatically curries JavaScript operators and all PatternScript functions
```
{   'add2'                          : '(+ 2)',
    'five'                          : '(add2 3)',
    '(isLiquid freeze boil temp)'   : '(&& (> temp freeze) (< temp boil))',
    '(isWater temp)'                : '(isLiquid 0 100)'                                    } 
```
... allows pattern matching against literals
```
{   '(reciprocal 0)'                : '(throw "division by zero")',
    '(reciprocal x)'                : '(/ 1 x)'                                             }
```
... supports wildcards in pattern matches
```
{   '(quotient _ 0)'                : '(throw "division by zero")',
    '(quotient x y)'                : '(/ x y)'                                             }
```
... allows predicate guard functions in pattern match signatures
```
{   '(factorial (! (_.isNumber _)))': '(throw "factorial requires a number")',
    '(factorial (!== (% _ 1) 0))'   : '(throw "factorial requires an integer")',
    '(factorial (< _ 1))'           : '(throw "factorial requires a positive integer")',
    '(factorial 1)'                 : '1',
    '(factorial n)'                 : '(* n (factorial (- n 1)))'                           }
```
