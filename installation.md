---
layout: default
---

# Installation hints

The simplest way to install Core, Async, and the rest of our libraries
is to use [OPAM](http://opam.ocamlpro.com).

## Core in the toplevel

_Note:_ You need core, ppx\_jane and ppx\_bin\_prot >= 113.24.01 for
these instructions to work properly.

If you want to use Core and its associated libraries and syntax
extensions in the toplevel, you can put the following in your
`.ocamlinit` file:

<pre class="sh_caml">
#use "topfind"
#thread
#require "ppx_jane,core.top"
#require "async"
#require "core_extended"
open Core.Std
</pre>

## Building with Core and OCamlBuild

If you want to build using `ocamlbuild`, then you can put the
following in your `_tags` file:

<pre class="sh_caml">
true: package(core,ppx_jane)
true: thread,debug
</pre>

Then you can build your app by calling:

<pre class="sh_sh">
$ ocamlbuild -use-ocamlfind myproject.native.
</pre>
