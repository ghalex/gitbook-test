---
description: Generates buy/sell orders to close provided positions
---

# closePositions

```clojure
(closePositions positions)
```

### Returns

An array with orders

### Parameters

<mark style="color:purple;">**positions (array)**</mark> - an array with positions to be closed

### Examples

{% code lineNumbers="true" %}
```clojure
(closePositions )              ;; will close all positions
;;=> [{symbol: 'AAPL', ...}]

(defn filterMSFT [p] (= "MSFT" (:symbol p)))
(def msft (filter filterMSFT openPositions)

;; will close MSFT positions
(closePositions msft)            
;;=> [{symbol: 'MSFT', ...}]

```
{% endcode %}
