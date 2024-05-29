# 🕟 Learn in X minutes

```clojure
; Comments start with semicolons.

; ZapLang is written in "forms", which are just
; lists of things inside parentheses, separated by whitespace.

; Some basic examples:
; str will create a string out of all its arguments
(str "Hello" "World") ; => "Hello World"

; Math is straightforward
(+ 1 1) ; => 2
(- 2 1) ; => 1
(* 1 2) ; => 2
(/ 2 1) ; => 2

; Equality is =
(= 1 1) ; => true
(= 2 1) ; => false

; You need not for logic, too
(not true) ; => false

; Nesting forms works as you expect
(+ 1 (- 3 2)) ; = 1 + (3 - 2) => 2

; Assets
; ZapLang has the concept of asset.
{AAPL} ; => {symbol: "AAPL", price: 180, ...}

; You can get the price for today, yesterday or any day
{AAPL, 2 days ago} ; => {symbol: "AAPL", price: 176 -> 2 days ago}
{AAPL, yesterday}

; You can fetch multiple prices at once
{AAPL, 5 bars} ; => [{symbol: "AAPL", price:...}, {symbol: "AAPL", price:...}, ...]
{AAPL, 2 bars, 2 days ago}

; ZapLang has the concept of arrays and objects
; Arrays
[1, 2, 3, 4]

; Get an element from an array
(nth 2 [1, 2, 3, 4])

; Other functions for arrays
(push 2 [2, 3, 4]) ; => [2, 3, 4, 2]
(pop [2, 3, 4]) ; => [2, 3]

; Use filter, map to interact with arrays
(map inc [1, 2, 3]) ; => [2, 3, 4]
(filter even? [1, 2, 3]) ; => [2]

; Use reduce to reduce them
(reduce + [1 2 3 4])
; = (+ (+ (+ 1 2) 3) 4)
; => 10

; You can create a var using def
(def x 1)
(def asset {AAPL}) ; store an asset

; Use fn to create new functions. A function always returns
; its last statement.
(fn [] "Hello World") ; => fn

; Assign a function to a var
(def hello-world (fn [] "Hello World"))
(hello-world) ; => "Hello World"

; You can shorten this process by using defn
(defn hello-world [] "Hello World")

; The [] is the list of arguments for the function.
(defn hello [name]
  (str "Hello " name))
(hello "Steve") ; => "Hello Steve"

; Objects
(def myObj {name: "john", age: 21}) ; => {name: "john", age: 21}

; Acces a value from an object
(:name myObj) ; => john
(get "name" myObj) ;=> john

; Assets are treated like objects
(:symbol {AAPL}) ;=> "AAPL"
(:close {AAPL}) ;=> 180 - close price



```
