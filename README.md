# Virtual package definition for custom OCaml system compilers

Assuming you have installed a custom compiler version, e.g. `4.08.0+foo`, to
your PATH and want to use it in opam without recompilation, you can use this
package to treat it as a system compiler:

```
opam pin ocaml-system.$(opam var sys-ocaml-version) git+https://github.com/AltGr/ocaml-system
```

The trick is that this allows you to specify the custom version of your
compiler, which is normally rejected by the
[ocaml-system](http://opam.ocaml.org/packages/ocaml-system/) package from the
repository.

The package definition here is similar, except that it refers to its version
dynamically in the `available:` field.
