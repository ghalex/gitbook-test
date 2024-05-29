---
description: Evaluates a statement
---

# if

```clojure
(if cond yesBlock noBlock?)
```

### Description

Evaluates `cond` and if true calls `yesBock` otherwise calls `noBlock`

### Body

<mark style="color:purple;">**cond**</mark> - condition to be tested

<mark style="color:purple;">**yesBlock**</mark> - block evaluated if `cond` true

<mark style="color:purple;">**noBlock? (optional)**</mark> - block evaluated if `cond` false

### Examples

{% code lineNumbers="true" %}
```clojure
(if (> 3 2) "yes" "no")
;;=> yes

(def var1 "aaa")
(if (= var1 "name")                ;; condition
    (print "Var & name equal")     ;; yes 
    (print "not equal")            ;; no
)
;;=> "not equal"

(if (and (> 2 3) (= 2 2))
    (print "Yess")
)

```
{% endcode %}
