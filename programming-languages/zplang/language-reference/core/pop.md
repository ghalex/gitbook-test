---
description: Retrieves a new array without the last element from an input array
---

# pop

```clojure
(pop arr)
```

### Returns

The function returns a new array that contains all elements of the input array except the last one.

### Parameters

<mark style="color:purple;">**arr (array)**</mark>** - t**he input array from which the last element is to be excluded.

{% hint style="info" %}
* The `pop` function returns a new array without the last element, while leaving the original array unmodified.\

* If the input array is empty, the function will return an empty array, as there are no elements to exclude.\

* The `pop` function does not have an in-place mutation effect on the input array. If you want to modify the array directly, you can use the <mark style="color:blue;">`pop!`</mark> function instead.
{% endhint %}

### Examples

{% code lineNumbers="true" %}
```clojure
(pop [1, 2, 3])
;;=> [1, 2]

(def arr1 [1, 2, 3])
(pop arr1)
;;=> [1, 2]

arr1    ;; arr1 remains the same
;;=> [1, 2, 3]

(pop! arr1)
;;=> 3
arr1
;;=> [1, 2]

```
{% endcode %}
