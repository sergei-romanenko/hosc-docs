# Higher Order Lazy Language (HLL) #

## The lexical structure of HLL ##

Type names, type variables, constructor names, function names and variables are 
represented by identifiers.

An identifier is a sequence of latin letters and digits, the first character
being a letter.

A function name, type variable and a variable must start with a small letter.

A constructor name and type name must start with a capital letter.

## The syntax of programs ##

In the following {*A*} means the construct *A* repeated zero or more times,
and [*A*] means the construct *A* is optional. Literals and keywords are 
shown as `code`.

---

*program* ::= {*typeDefinition*} *goal* [ `where` {*functionDefinition*} ]

*goal* ::= *expression*

*typeDefinition* ::= `data` *typeConstructor* `=` *dataConstructor* {`|` *dataConstructor*} `;`

*typeConstructor* ::= *typeName* {*typeVariable*} `;`

*dataConstructor* ::= *constructorName* {*type*} `;`

*type* ::= *typeVariable* \| *typeConstructor* \| *type* `->` *type* \| `(` *type* `)`

*functionDefinition* ::= *functionName* `=` *abstraction* `;`

*expression* :: = *variable* \| *constructor* \| *functionName* \| *abstraction* \| *application* \| *caseExpression* \| *letrec* | `(` *expression* `)`

*constructor* ::= *constructorName* {*expression*}

*abstraction* ::= `\` *variable* { *variable* } `->` *expression*

*application* ::= *expression* *expression*

*caseExpression* ::= `case` *expression* `of` `{` {*branch*} `}`

*letrec* ::= `letrec` *functionName* `=` *abstraction* `in` *expression*

*branch* ::= *pattern* `->` *expression* `;`

*pattern* ::= *constructorName* {*variable*}

---

HLL is typed using the Hindley-Milner polymorphic typing system.

A program in HLL consists of a number of data type definitions, an expression to 
be evaluated and a set of function definitions. An expression to be evaluated 
may contain free variables.

A left-hand side of a data type definition is a type name (more precisely, a
type constructor name) followed by a list of type variables. The right-hand side
consists of one or more constructor declarations.

An expression is either a variable, a constructor, a lambda abstraction, an 
application, a case expression or an expression in parenthesis. A function 
definition binds a variable to a lambda abstraction. The intended operational 
semantics of HLL is the normal-order graph reduction to a weak head normal 
form. The data analysis is performed by pattern matching with constructors in 
case expressions.

Each constructor has a fixed arity. The variables in the patterns of case 
expressions and the arguments of lambda-abstractions are bound; all other 
variables are free. Each function has exactly one definition and all variables 
within a definition are bound. No variables may appear more than once within a 
pattern. Patterns in a case expression are non-overlapping and exhaustive.

Currently, in a source program, letrec expressions are allowed to appear only 
inside the program goal.

## Examples ##

### Functions over lists ###

```
data List a = Nil | Cons a (List a);

append (map f xs) (map f ys)

where

compose = \f g x ->  f (g x);

unit = \x -> Cons x Nil;

id = \xs ->
    case xs of {
        Nil -> Nil;
        Cons x1 xs1 -> Cons x1 (id xs1);
    };

map = \f xs ->
    case xs of {
        Nil -> Nil;
        Cons x1 xs1 -> Cons (f x1) (map f xs1);
    };

join = \xs ->
    case xs of { 
        Nil -> Nil;
        Cons x1 xs1 -> append x1 (join xs1);
    };

append = \xs ys ->
    case xs of {
        Nil -> ys;
        Cons x1 xs1 -> Cons x1 (append xs1 ys);
    };
```
