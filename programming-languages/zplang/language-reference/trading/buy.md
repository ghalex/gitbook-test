---
description: Generates a new buy order
---

# buy

```clojure
(buy {asset} shares options?)
```

### Description

The `buy` function generates a buy order for a specified symbol and number of units. It returns an order object containing information about the buy action. The function also supports additional options to control order generation based on existing open positions.

### Returns

The `buy` function returns an order object containing information about the buy action. If the order is not generated due to existing open positions, it may return `null`&#x20;

### Parameters

<mark style="color:purple;">**{asset} (asset)**</mark> - asset to be bought

<mark style="color:purple;">**shares (number)**</mark> - the number of units (shares, contracts, etc.) to be bought.

<mark style="color:purple;">**options (optional, object)**</mark> \
&#x20;   \- **target**: checks _openPositions_ and generates order to balance portfolio

### Examples

{% code lineNumbers="true" %}
```clojure
(buy {AAPL} 1)            ;; buys one share of AAPL
;;=> order {symbol: "AAPL", action: "buy", units: 1, ....}

;; openPositions = [{symbol: "AAPL", side: "long", units: 1}]
(buy {AAPL} 1 {target: true})
;; will not generate a order because openPositions allready has
;; 1 share of AAPL long
```
{% endcode %}
