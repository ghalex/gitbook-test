---
description: Generates a new sell order
---

# sellAmount

```clojure
(sellAmount {asset} amount options?)
```

### Returns

The `sellAmount` function returns an order object containing information about the sell action. If the order is not generated due to existing open positions, it may return `null`&#x20;

### Parameters

<mark style="color:purple;">**{asset} (asset)**</mark> - asset to be sold

<mark style="color:purple;">**amount (number)**</mark> - amount to be sold

<mark style="color:purple;">**options (object)**</mark>\
&#x20;   \- **round**: only hole shares\
&#x20;   \- **target**: checks _openPositions_ and generates order to balance portfolio



### Examples

{% code lineNumbers="true" %}
```clojure
(sellAmount {AAPL} 200)            ;; sells 1.29 shares of AAPL if price is 155
;;=> order {symbol: "AAPL", action: "sell", units: 1.29, ....}

(sellAmount {AAPL} 200 {round: true})    ;; sells 1 shares of AAPL if price is 155
;;=> order {symbol: "AAPL", action: "sell", units: 1, ....}
```
{% endcode %}
