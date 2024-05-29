---
description: Generates a new buy order
---

# buyAmount

```clojure
(buy {asset} amount options?)
```

### Returns

The `buy` function returns an order object containing information about the buy action. If the order is not generated due to existing open positions, it may return `null`&#x20;

### Parameters

<mark style="color:purple;">**{asset} (asset)**</mark> - asset to be bought

<mark style="color:purple;">**amount (number)**</mark> - amount to be bought

<mark style="color:purple;">**options (optional, object)**</mark>\
&#x20;   \- **round**: only hole shares\
&#x20;   \- **target**: checks _openPositions_ and generates order to balance portfolio



### Examples

{% code lineNumbers="true" %}
```clojure
(buyAmount {AAPL} 200)            ;; buys 1.29 shares of AAPL if price is 155
;;=> order {symbol: "AAPL", action: "buy", units: 1.29, ....}

(buyAmount {AAPL} 200 {round: true})    ;; buys 1 shares of AAPL if price is 155
;;=> order {symbol: "AAPL", action: "buy", units: 1, ....}
```
{% endcode %}
