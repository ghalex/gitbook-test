---
description: Loops through an array and evaluates the expr in a lexical context
---

# loop

```clojure
(loop var? in array expr*)
```

### Description

Loops through an array and evaluates the `expr` in a lexical context. If var is missing you can access the value using \`\_value\`

### Body

<mark style="color:purple;">**var**</mark> - the name of the variable

<mark style="color:purple;">**array**</mark> - the array to loop

<mark style="color:purple;">**expr\***</mark> - expressions to be evaluated

### Examples

{% code lineNumbers="true" %}
```clojure
(loop var1 in [1, 2, 3, 4]
    (print var1)
)
;;=> 1, 2, 3, 4

(loop [1, 2, 3, 4]
    (str _value ":" _index)
)

(def names ["John", "Bob", "Marry"])
(loop name in names
    (str "Hello" name)
)
;;=> Hello John
;;=> Hello Bob
;;=> Hello Marry

```
{% endcode %}
