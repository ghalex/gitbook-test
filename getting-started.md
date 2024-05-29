# Getting Started

## 1. Install CLI

Start by installing the CLI globally using your preferred package manager.

{% tabs %}
{% tab title="npm" %}
```sh
npm install @zaptrade/cli -g
```
{% endtab %}

{% tab title="yarn" %}
{% code overflow="wrap" fullWidth="false" %}
```bash
yarn global add @zaptrade/cli
```
{% endcode %}
{% endtab %}

{% tab title="pnpm" %}
```bash
pnpm install @zaptrade/cli -g
```
{% endtab %}
{% endtabs %}

## 2. Create a project

Generate a **new project** using zapcli. This action will set up a sample project and install all necessary dependencies.

```shell
zapcli create MyProject
```

Open your project in VSCode or any other editor.

## 3. Run automation

ZapCLI can execute an automation once on a specific day and showcase the orders in the terminal or store them in a file (e.g., `orders.json`).

To run an automation just open it in VSCode (`src/hello.zp`) and press `Ctrl+Shift+B`. Or you can use the terminal:

```bash
zapcli execute ./src/hello.zp

## or

npm execute
```

## 3. Run your first backtest

```bash
zapcli backtest ./src/hello.zp

## or use the shortcut

npm backtest
```

This command will execute `hello.zp` for a duration of **20 days**. It will display the result in the terminal and save the backtest data in `report/data.json`. You can view a **visual report** by opening the `report/report.html` file.

## 4. Write your own automation

To write your own strategy you need to create an automation file that will be run on every bar. Currently we have been using the `hello.(zp|js)` file

{% tabs %}
{% tab title="hello.zp" %}
```clojure
;; Loops a list a symbols and buys 1 share of each

(def symbols [
  "AAPL",
  "MSFT"
])

(loop symbol in symbols
  (buy {symbol} 1)
)
```
{% endtab %}

{% tab title="hello.js" %}
```javascript
const assets = ["AAPL", "MSFT"]
const window = 1
const settings = {}

function run() {
  for (const symbol of assets) {
    this.buy(this.asset(symbol), 1)
  }
}
```
{% endtab %}
{% endtabs %}

To see more automation examples check out the [Examples ](programming-languages/zplang/examples.md)page.

## 5. Configuration

ZapCLI is using a configuration file to run a backtest or execute an automation file. Your project started with the default config file:

```javascript
import { analyzers } from '@zaptrade/backtest'

const config = {
  // Data provider Zapant.com by default
  dataDir: "./data",
  apiUrl: "http://zapant.com/api",
  // Configuration example to execute an automation once
  execute: {
    date: "2024-05-20",
    inputs: {
      assets: ["AAPL", "MSFT"],
      initialCapital: 10000,
      openPositions: [{
        symbol: 'AAPL',
        openDate: 1682366400000,
        openPrice: 200.00,
        closeDate: null,
        closePrice: null,
        units: 5,
        side: 'long',
        accountType: 'paper'
      }]
    },
  },
  // Configuration to run a backtest
  backtest: {
    startDate: "2024-05-01",
    endDate: "2024-05-20",
    saveResult: "./report/data.json",
    inputs: {
      assets: []
    },
    analyzers: [
      new analyzers.RetursAnalyzer(),
      new analyzers.PositionsAnalyzer()
    ]
  }
}

export default config;
```

As you can see here you can configure your backtest with a start, end date or add analyzers to run with your backtest. To learn more about Analyzers and Data Providers please read the documentaion.

