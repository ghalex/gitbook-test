---
description: Creates a new array from calling a function on every array element
---

# map

```clojure
(map fn arr)
```

### Returns

The function returns a new array that contains the transformed values after applying the specified function to each element of the input array.

### Parameters

<mark style="color:purple;">**fn (lambda)**</mark> - the function to be applied to each element of the array.

<mark style="color:purple;">**arr (array)**</mark> - the input array containing elements to be transformed.

{% hint style="info" %}
* The `map` function applies the specified function to each element of the array in a sequential manner.\

* The function passed to `map` can be a predefined function or an anonymous function defined using the <mark style="color:blue;">`(fn [args] body)`</mark> syntax.\

* The original input array remains unchanged, and a new array is returned with the transformed values.\

* The `map` function is useful for performing transformations on arrays, such as incrementing values, applying mathematical operations, or applying custom functions to each element.
{% endhint %}

### Examples

{% code lineNumbers="true" %}
```clojure
(map inc [1, 2, 3, 4, 5])              ;; increment all values
;;=> [2, 3, 4, 5, 6]

(map (fn [x] (* x 2)) [1, 2, 3, 4])    ;; multiply all values with 2
;;=> [2, 4, 6, 8]

(map (fn [symbol] {symbol}) ["AAPL", "MSFT"]) ;; creates an array of assets
;;=> [{symbol: "AAPL", close: ...}, {symbol: "MSFT", close: ...}]
```
{% endcode %}
