Creating a code usage report using ocamlcp:

- lib.ml

```
let unity x = x;;
let funix ()= 0;;
let fgeneric () = failwith "Not implemented";;

print_endline (unity "hello")
```

- command line:

`$ ocamlcp -p a lib.ml -o lib`

`$ ./lib`

`$ ocamlprof lib.ml`

- result:

```
let unity x = (* 1 *) x;;
let funix ()= (* 0 *) 0;;
let fgeneric () = (* 0 *) failwith "Not implemented";;

print_endline (unity "hello")
```
