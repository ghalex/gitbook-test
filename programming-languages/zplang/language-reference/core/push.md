---
description: Appends an element to the end of an array and returns a new array
---

# push

```clojure
(push element arr)
```

### Returns

The `push` function returns a new array that includes the original elements of the input array followed by the appended element. The `push!` function modifies the original array and returns the value

### Parameters

<mark style="color:purple;">**element (any) -**</mark> the element to be added to the array.

<mark style="color:purple;">**arr (array) -**</mark> the input array to which the element will be appended.

{% hint style="info" %}
* The `push` function returns a new array with the appended element, leaving the original array unmodified.\

* The <mark style="color:blue;">`push!`</mark> function modifies the original array directly returning a value.\

* Both functions are used to add elements to the end of an array.\

* It is important to note the distinction between the `push` function, which creates a new array, and the `push!` function, which modifies the array in-place.
{% endhint %}

### Examples

{% code lineNumbers="true" %}
```clojure
(push 5 [1, 2])
;;=> [1, 2, 5]

(def arr1 [1, 2, 3])
(push 4 arr1)
;;=> [1, 2, 3, 4]

arr1    ;; arr1 remains the same
;;=> [1, 2, 3]

(push! 5 arr1)
;;=> 5
arr1
;;=> [1, 2, 3, 5]

```
{% endcode %}
