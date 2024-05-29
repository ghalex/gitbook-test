---
description: Retrieves the value associated with a specified key
---

# get

```clojure
(get key obj)
```

### Returns

The `get` function returns the value associated with the specified key in the map object. If the key is not found or if any intermediate nested key is missing, it returns `null`&#x20;

### Parameters

<mark style="color:purple;">**key (string)**</mark> - the key to retrieve the corresponding value from the object

<mark style="color:purple;">**obj (object)**</mark> - he map object from which to retrieve the value

### Examples

{% code lineNumbers="true" %}
```clojure
(get "name" {name: "John", age: 22})              ;; get value for key name
;;=> John

(get "agenda.phone" {agenda: {phone: 22, other: 22}})
;;=> 22

```
{% endcode %}
