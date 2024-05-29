---
description: Creates a new lambda function
---

# fn

```clojure
(fn [params*] exp*)
```

### Description

Creates a new lambda function. You can store this using \`def\` keyword and call it later. See examples

### Body

<mark style="color:purple;">**params**</mark> - lambda parameters, ex: \`\[param1, param2]\`

<mark style="color:purple;">**exp**</mark> - any number of expressions. Last expression will be the return value when lambda get's evaluated.

{% hint style="info" %}
There is a short version of `fn`

```clojure
[x] => (* x 2) => (fn [x] (* x 2))
```
{% endhint %}

### Examples

{% code lineNumbers="true" %}
```clojure
(def add (fn [a, b] (+ a b)))
(add 2 3)
;;=> 5

(map (fn [x] (* x 2)) [1, 2, 3, 4])
;;=> [2, 4, 6, 8]

```
{% endcode %}
