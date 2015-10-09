# module

A minimal module system for zepto. It is in early alpha.

# Usage

After importing `module.zp`, you can create and import modules like so:
```clojure
(load "module.zp")
(module "mathematica"
  (export
    (list :adder adder)
    (list :subtractor subtractor)
    (list "multiplicator" multiplicator))

  (mather (lambda (scheme a b) (scheme a b)))
  (adder (lambda (a b) (mather + a b)))
  (subtractor (lambda (a b) (mather - a b)))
; there now is a library called mathematica. You can access it like that:
(define subtractor (import "mathematica:subtractor"))
; or, if you prefer to import it under another name:
(define the-most-useful-function (import "mathematica:subtractor"))
```

<br/>

*Have fun!*
