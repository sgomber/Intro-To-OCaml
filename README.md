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


## Links

1. [A First Hour with OCaml](https://ocaml.org/docs/first-hour)

# Examples

## Lists

* [Tail of a list](https://ocaml.org/problems#1)

    ```ocaml
    let rec last = function
    | [] -> None
    | [x] -> Some x
    | _ :: t -> last t;;
    ```

* [Eliminate consecutive duplicates](https://ocaml.org/problems#8)

    ```ocaml
    let rec compress = function
    | f :: (s :: _ as t) -> if f = s then compress t else f :: compress t
    | small_one -> small_one;;
    val compress : 'a list -> 'a list = <fun>
    ```

* [Pack consecutive duplicates](https://ocaml.org/problems#9)

    ```ocaml
    let rec pack = function
    | f :: (s :: _ as t) -> let (hp :: tp as rec_result) = pack t in (if f = s then ((f :: hp) :: tp) else [f] :: rec_result)
    | [x] -> [[x]]
    | [] -> [];;
    ```