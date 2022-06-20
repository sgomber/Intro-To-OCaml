# Installation

## Linux

Run the following commands as `sudo`:

```bash
apt-get update
apt-get install ocaml -y
```

This will get ocaml setup, which can be verified by the
`ocaml --version` command.

```bash
$ ocaml --version
The OCaml toplevel, version 4.08.1
```

I will be using [utop](https://github.com/ocaml-community/utop) for
this introduction. Utop is an improved toplevel (i.e., Read-Eval-Print Loop) for OCaml.
It can run in a terminal or in Emacs. It supports line editing, history, real-time and context
sensitive completion, colors, and more.

```bash
sudoo apt-get install utop
```

# Getting Started

Typing `utop` in the terminal will open up the REPL which can be used
to play around with OCaml.

![Starter](/screenshots/starter.PNG)


# Basic Syntax

## Expressions

```
2 > 3;;
"bye" ^ "bye";;
2.1 *. 3;
(2.1 : float)
```

`;;` marks the end of the statements.
`^` is the string concatenation operator.
`*.` is the multiplication for floats.
`:` is used for type annotations.

## If-Else

```
if "batman" > "superman" then "yay" else "boo";;
```

- "if 0" will not work as OCaml requires the expression after if to be a boolean.
- The then and else branches should have the same return type.

```
## INVALID USES

if 0 then 1 else 2;;
if true then "yay" else 1;;
```

## Let Definations

```
let x = 42;;
let x = e;; // e is any expression.
```

- x should be an identifier and should follow the identifier rules.
- (let x = 42) is not an expression.

## Let Expressions

```
let a = 0 in a;;
>> Evaluates to 0, basically substitutes variable values in the expression after in

let a = a1 in e1;;
```

These lets are only "scoped" to the expressions after `in`.

```
let e = 5 in (let e = 6 in e);;
```
This evaluates to 6 as the inner expression returns 6 which has no
"e" for the outer let to replace!

In light of this, `let x = 2;;` can be read as "let x = 2 in *rest of
whatever you type*".
