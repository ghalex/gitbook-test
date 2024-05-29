---
description: Generates a new sell order
---

# sell

```clojure
(sell {asset} shares options?)
```

### Returns

The `sell` function returns an order object containing information about the sell action. If the order is not generated due to existing open positions, it may return `null`&#x20;

### Parameters

<mark style="color:purple;">**{asset} (asset)**</mark> - asset to be sold

<mark style="color:purple;">**shares (number)**</mark> - the number of units (shares, contracts, etc.) to be sold.

<mark style="color:purple;">**options (optional, object)**</mark>\
&#x20;   \- **target**: checks openPositions and generates order to balance portfolio

### Examples

{% code lineNumbers="true" %}
```clojure
(sell {AAPL} 1)            ;; sells one share of AAPL
;;=> order {symbol: "AAPL", action: "sell", units: 1, ....}

;; openPositions = [{symbol: "AAPL", side: "short", units: 1}]
(sell {AAPL} 1 {target: true})
;; will not generate a order because openPositions allready has
;; 1 share of AAPL short
```
{% endcode %}
