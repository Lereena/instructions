- get syntax tree of expression

`$ ocamlfind ppx_tools/dumpast -e "[%addone 1 + 2]"`

- build ppx

`$ ocamlbuild -package compiler-libs.common addone_ppx.native`

- apply ppx

`$ ocamlc -ppx ./path_to_the_compiled_ppx test.ml`

- see the result of application

`$ ocamlfind ppx_tools/rewriter ./addone_ppx.native addone.ml`
