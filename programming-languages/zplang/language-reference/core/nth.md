---
description: Retrieves the element at a specified index from an array.
---

# nth

```clojure
(nth index arr)
```

### Returns

The function returns the element at the specified index in the given array.

### Parameters

<mark style="color:purple;">**index (number) -**</mark> the index of the element to retrieve from the array

<mark style="color:purple;">**arr (array) -**</mark> the array from which the element is to be retrieved.

{% hint style="info" %}
* The index can be positive or negative.\

* If the absolute value of the specified index exceeds the length of the array it will be divided by the array length
{% endhint %}

### Examples

{% code lineNumbers="true" %}
```clojure
(nth 1 [1, 2, 3, 4, 5])        
;;=> 2

(nth -1 ["John", "Pop", "Maria"])
;;=> Maria


```
{% endcode %}
