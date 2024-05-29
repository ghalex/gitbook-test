---
description: Assigns new key-value pairs to a map object
---

# set

```clojure
(set keyValuePairs obj)
```

### Returns

The `set` function returns a new map object with the updated key-value pairs. The original map object **remains unchanged**

### Parameters

<mark style="color:purple;">**keyValuePairs (object)**</mark> - an object containing the key-value pairs to be added or modified in the map

<mark style="color:purple;">**obj (object)**</mark> - the target map object to which the key-value pairs will be assigned.

{% hint style="info" %}
* The `set` function assigns new key-value pairs to a map object\

* It creates a new map with the updated values and does not modify the original map.\

* The function takes a target map object and an object containing key-value pairs to be added or modified.\

* The resulting map contains the original key-value pairs along with any new or modified pairs
{% endhint %}

### Examples

{% code lineNumbers="true" %}
```clojure
(def obj1 {age: 22})
(set {height: 100} obj1)
;;=> {age: 22, height: 100}

obj1    ;; obj remains unchange
;;=> {age: 22}

```
{% endcode %}
