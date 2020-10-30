[![npm version](https://badge.fury.io/js/hardhat-gas-reporter.svg)](https://badge.fury.io/js/hardhat-gas-reporter)
[![Build Status](https://travis-ci.org/cgewecke/hardhat-gas-reporter.svg?branch=master)](https://travis-ci.org/cgewecke/hardhat-gas-reporter)

# hardhat-gas-reporter

[eth-gas-reporter](https://github.com/cgewecke/eth-gas-reporter) plugin for [hardhat](http://gethardhat.com). :fuelpump:

## What

**A Mocha reporter for Ethereum test suites:**

- Gas usage per unit test.
- Metrics for method calls and deployments.
- National currency costs of deploying and using your contract system.
- CI integration with [codechecks<sup>beta</sup>](http://codechecks.io)

### Example report

![Screen Shot 2019-06-23 at 2 10 19 PM](https://user-images.githubusercontent.com/7332026/59982003-c30a4380-95c0-11e9-9d93-e3af979df227.png)

## Installation

```bash
npm install hardhat-gas-reporter --save-dev
```

And add the following to your `hardhat.config.js`:
```js
require("hardhat-gas-reporter");
```

Or, if you are using TypeScript, add this to your hardhat.config.ts:
```ts
import "hardhat-gas-reporter"
```

**Looking for buidler-gas-reporter docs?** [They moved here...][1]

## Configuration
Configuration is optional.
```js
module.exports = {
  gasReporter: {
    currency: 'CHF',
    gasPrice: 21
  }
}
```
:bulb: **Pro Tip**

The options include an `enabled` key that lets you toggle gas reporting on and off using shell
environment variables. When `enabled` is false, mocha's (faster) default spec reporter is used.
Example:

```js
module.exports = {
  gasReporter: {
    enabled: (process.env.REPORT_GAS) ? true : false
  }
}
```
## Usage

This plugin overrides the built-in `test` task. Gas reports are generated by default with:
```
npx hardhat test
```

## Options / Documentation

A list of options and other useful documentation can be found at [eth-gas-reporter](https://github.com/cgewecke/eth-gas-reporter)

[1]: https://github.com/cgewecke/buidler-gas-reporter/tree/buidler-final#installation
