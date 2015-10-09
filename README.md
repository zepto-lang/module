# module

A minimal module system for zepto. It is in early alpha.

# Usage

You can create and import modules like so (no need to import the file,
as it is part of the standard library):
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
  (multiplicator (lambda (a b) (mather * a b))))

; there now is a library called mathematica. You can access it like that:
(define subtractor (import "mathematica:subtractor"))

; or, if you prefer to import it under another name:
(define the-most-useful-function (import "mathematica:subtractor"))

; if you want to import the whole thing:
(define mathematica (import "mathematica"))

; then you can access those functions like that:
(mathematica "adder")
=> No documentation available
  source: (lambda ("a" "b") ...)
```

Modules can also, be extended, like so:

```clojure
(module-extend "mathematica"
  (export (list :divisor divisor))

  (divisor (lambda (a b) (/ a b))))
```

Please note that current references to the library need to be updated
if that happens after already importing the library and private properties
are not available in the extension (sorry).

<br/>

*Have fun!*
