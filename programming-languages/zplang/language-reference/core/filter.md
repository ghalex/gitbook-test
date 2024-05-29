---
description: Filters an array
---

# filter

```clojure
(filter fn arr)
```

### Returns

A portion of the given array, filtered down to just the elements from the given array that pass the test implemented by the provided function

### Parameters

<mark style="color:purple;">**fn (lambda)**</mark> - a function to be run for each array element. It should return a [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) value

<mark style="color:purple;">**arr (array)**</mark> - the array to be filtered

### Examples

{% code lineNumbers="true" %}
```clojure
;; filter all values smaller then 2
(filter (fn [x] (> x 2)) [1, 2, 3, 4, 5])
;;=> [3, 4, 5, 6]


```
{% endcode %}
