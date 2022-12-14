# Curve Stable Coin Simulator

[![npm (tag)](https://img.shields.io/npm/v/curve-stablecoin-simulator)](https://www.npmjs.com/package/curve-stablecoin-simulator)
![Tests (tag)](https://img.shields.io/github/actions/workflow/status/0x-stan/curve-stablecoin-simulator/tests.yml?branch=main)
![Snyk Security Check (tag)](https://img.shields.io/github/actions/workflow/status/0x-stan/curve-stablecoin-simulator/snyk.yml?branch=main&label=Snyk%20Security%20Check)

[curve-stablecoin](https://github.com/curvefi/curve-stablecoin) js implementation.

🖥️ [Graphic Live Demo](https://crvusd.0xreviews.xyz/)

## Install

```sh
npm i curve-stablecoin-simulator
```

## Getting Started

```ts
import { LLAMMA, Controller } from "curve-stablecoin-simulator";

const amm = new LLAMMA(100, 0.00, 0, 0.05, 0.02, 10 ** 6, 1000);
const controller = new Controller(0.02, 0.05, amm);

// deposit 10 ETH borrow 1000 crvUSD with 10 bands range
controller.create_loan("user1", 10, 1000, 10);

// swap in 100 crvUSD out ETH, min received 0.8ETH
// will return acctually out amount.
const out_amount = amm.exchange(0, 1, 1000, 0.8);
```

## Test

```sh
cd curve-stablecoin-simulator
npm install
npm test

# output
> curve-stablecoin-simulator@0.1.14 test
> mocha

 11  -_-_-_-_-_-__,------,
 0   -_-_-_-_-_-__|  /\_/\ 
 0   -_-_-_-_-_-_~|_( ^ .^) 
     -_-_-_-_-_-_ ""  "" 

  11 passing (275ms)
```

## TODO

- PegKeeper
- mpoliceis
  - AggMonetaryPolicy
  - ConstantMonetaryPolicy
