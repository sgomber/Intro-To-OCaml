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



