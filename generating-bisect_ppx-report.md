Creating a code coverage report using bisect_ppx and ocamlfind:

- lib.ml

```
let unity x = x;;
let funix ()= 0;;
let fgeneric () = failwith "Not implemented";; 
```

- test.ml

```
open OUnit2;;
open Lib;;

let test1 test_ctxt = assert_equal "x" (Lib.unity "x");;

let test2 test_ctxt = assert_equal 100 (Lib.unity 100);;

let suite =
"suite">:::
    ["test1">:: test1;
     "test2">:: test2]
;;

let () = 
    run_test_tt_main suite
;;
```

- command line

`$ ocamlfind c -package bisect_ppx -c lib.ml`

`$ ocamlfind c -package oUnit -c test.ml`

`$ ocamlfind c -linkpkg -package bisect_ppx -package oUnit lib.cmo tests.cmo`

`$ ./a.out`

`$ bisect-ppx-report -I build/ -html coverage/ bisect*.out`
