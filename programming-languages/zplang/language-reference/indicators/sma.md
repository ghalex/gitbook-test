---
description: Simple Moving Averange
---

# sma

```clojure
(sma len symbol options?)
```

### Description

The `sma` function calculates the Simple Moving Average (SMA) for a specified number of days for a given asset symbol. It returns the SMA value for the specified period or an array of SMA values if the `roll` option is provided.

### Returns

The `sma` function returns the calculated SMA value for the specified period. If the `roll` option is provided, it returns an array of SMA values for each rolling period. The `offset` option allows retrieving the SMA value from a specific offset day.

### Parameters

<mark style="color:purple;">**len (asset)**</mark> - the number of days to calculate the SMA

<mark style="color:purple;">**symbol (string)**</mark> - symbol of the asset for which the SMA is to be calculated

<mark style="color:purple;">**options (optional, object) -**</mark> additional options to control the calculation (e.g., rolling, offset).

{% hint style="info" %}
* The `sma` function calculates the Simple Moving Average (SMA) for a specified number of days for a given asset symbol.\

* Additional options can be provided to control the calculation, such as the rolling option to calculate SMA values for multiple rolling periods.\

* The exact calculation method and behavior of the function may vary depending on the specific trading system or context in which it is used.
{% endhint %}

### Examples

{% code lineNumbers="true" %}
```clojure
(sma 21 "AAPL")            ;; Simple Moving Averange for last 21 days
;;=> 188.3

(sma 21 "AAPL" {roll: 2})   ;; Simple Moving Averange for last 21 days
;;=> [188.3, 188.22, 178.97]

(sma 21 "AAPL" {offset: 2})   ;; SMA 21 starting 2 days ago
;;=> 188.2
```
{% endcode %}
