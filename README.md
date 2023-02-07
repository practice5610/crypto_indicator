[![Travis CI](https://img.shields.io/travis/asimasim84/technicalindicators.svg?style=flat-square)](https://travis-ci.org/asimasim84/technicalindicators)

# TechnicalIndicators

A javascript technical indicators written in typescript.


# Installation

## Node.js versions >= 10

``` bash
npm install --save technicalindicators
```

``` javascript
const SMA = require('technicalindicators').SMA;
```

## Node.js versions < 10

For nodejs version below 10 use 1.x versions of this library.

## Webpack

Make sure you have the following in your config file.

``` javascript
module.exports = {
  resolve: {
    mainFields: ["module", "main"]
  }
}

```

## Browser

For browsers install using npm,

For ES6 browsers use

``` bash
npm install --save technicalindicators
```

```html
<script src="node_modules/technicalindicators/dist/browser.es6.js"></script>
```

For ES5 support it is necessary to include the babel-polyfill and respective file browser.js otherwise you will get an error. For example see [index.html](https://github.com/asimasim84/technicalindicators/blob/master/index.html "index.html")

``` bash
npm install --save technicalindicators
npm install --save babel-polyfill
```

``` html
<script src="node_modules/babel-polyfill/browser.js"></script>
<script src="node_modules/technicalindicators/dist/browser.js"></script>
```

### Pattern detection

Pattern detection is removed from version 3.0, if you need pattern detection use v2.0

All indicators will be available in window object. So you can just use

``` javascript
sma({period : 5, values : [1,2,3,4,5,6,7,8,9], reversedInput : true});
```

or

``` javascript
SMA.calculate({period : 5, values : [1,2,3,4,5,6,7,8,9]});
```

# Playground



# Crypto Trading hub

If you like this project. You'll love my other project [crypto trading hub](https://cryptotrading-hub.com/?utm_source=github&utm_medium=readme&utm_campaign=technicalindicators "Crypto trading hub")

1. Its free
1. Realtime price charts
1. Unified trading experience across exchanges
1. Price alerts
1. Realtime crypto screening using javascript (Find coins making high and low in realtime or anything you can write using this library and javascript in realtime)
1. Trading from charts,
1. Modify orders and ability to trade and create studies using javascript.

![Home](/images/home.png)
![Screener](/images/screener.png)
![Trade](/images/trade.png)





# CandleStick Pattern


1. [Bearish Engulfing Pattern](https://runkit.com/aarthiaradhana/bearishengulfingpattern).
2. [Bullish Engulfiing Pattern](https://runkit.com/aarthiaradhana/bullishengulfingpattern).
3. [Dark Cloud Cover](https://runkit.com/aarthiaradhana/darkcloudcover).
4. [Downside Tasuki Gap](https://runkit.com/aarthiaradhana/downsidetasukigap).
5. [Doji](https://runkit.com/aarthiaradhana/doji).
6. [DragonFly Doji](https://runkit.com/aarthiaradhana/dragonflydoji).
7. [GraveStone Doji](https://runkit.com/aarthiaradhana/gravestonedoji).
8. [BullishHarami](https://runkit.com/aarthiaradhana/bullishharami).
9. [Bearish Harami Cross](https://runkit.com/aarthiaradhana/bearishharamicross).
10. [Bullish Harami Cross](https://runkit.com/aarthiaradhana/bullishharamicross).
11. [Bullish Marubozu](https://runkit.com/aarthiaradhana/bullishmarubozu).
12. [Bearish Marubozu](https://runkit.com/aarthiaradhana/bearishmarubozu).
13. [Evening Doji Star](https://runkit.com/aarthiaradhana/eveningdojistar).
14. [Evening Star](https://runkit.com/aarthiaradhana/eveningstar).
15. [Bearish Harami](https://runkit.com/aarthiaradhana/bearishharami).
16. [Piercing Line](https://runkit.com/aarthiaradhana/piercingline).
17. [Bullish Spinning Top](https://runkit.com/aarthiaradhana/bullishspinningtop).
18. [Bearish Spinning Top](https://runkit.com/aarthiaradhana/bearishspinningtop).
19. [Morning Doji Star](https://runkit.com/aarthiaradhana/morningdojistar).
20. [Morning Star](https://runkit.com/aarthiaradhana/morningstar).
21. [Three Black Crows](https://runkit.com/aarthiaradhana/threeblackcrows).
22. [Three White Soldiers](https://runkit.com/aarthiaradhana/threewhitesoldiers).
23. [Bullish Hammer](https://runkit.com/nerdacus/technicalindicator-bullishhammer).
24. [Bearish Hammer](https://runkit.com/nerdacus/technicalindicator-bearishhammer).
25. [Bullish Inverted Hammer](https://runkit.com/nerdacus/technicalindicator-bullishinvertedhammer).
26. [Bearish Inverted Hammer](https://runkit.com/nerdacus/technicalindicator-bearishinvertedhammer).
27. [Hammer Pattern](https://runkit.com/nerdacus/technicalindicator-hammerpattern).
28. [Hammer Pattern (Unconfirmed)](https://runkit.com/nerdacus/technicalindicator-hammerpatternunconfirmed).
29. [Hanging Man](https://runkit.com/nerdacus/technicalindicator-hangingman).
30. [Hanging Man (Unconfirmed)](https://runkit.com/nerdacus/technicalindicator-hangingmanunconfirmed).
31. [Shooting Star](https://runkit.com/nerdacus/technicalindicator-shootingstar).
32. [Shooting Star (Unconfirmed)](https://runkit.com/nerdacus/technicalindicator-shootingstarunconfirmed).
33. [Tweezer Top](https://runkit.com/nerdacus/technicalindicator-tweezertop).
34. [Tweezer Bottom](https://runkit.com/nerdacus/technicalindicator-tweezerbottom).

or

Search for all bullish or bearish using


``` javascript
var twoDayBullishInput = {
  open: [23.25,15.36],
  high: [25.10,30.87],
  close: [21.44,27.89],
  low: [20.82,14.93],
}

var bullish = require('technicalindicators').bullish;

bullish(twoDayBullishInput) //true
```


# API

There are three ways you can use to get the indicator results.

## calculate

Every indicator has a static method `calculate` which can be used to calculate the indicator without creating an object.

``` javascript
const sma = require('technicalindicators').sma;
var prices = [1,2,3,4,5,6,7,8,9,10,12,13,15];
var period = 10;
sma({period : period, values : prices})
```

or

``` javascript
const SMA = require('technicalindicators').SMA;
var prices = [1,2,3,4,5,6,7,8,9,10,12,13,15];
var period = 10;
SMA.calculate({period : period, values : prices})
```

## nextValue

`nextValue` method is used to get the next indicator value.

``` javascript
var sma = new SMA({period : period, values : []});
var results = [];
prices.forEach(price => {
  var result = sma.nextValue(price);
  if(result)
    results.push(result)
});
```

## getResult

This a merge of calculate and nextValue. The usual use case would be

1. Initialize indicator with available price value

1. Get results for initialized values

1. Use nextValue to get next indicator values for further tick.

    ``` javascript
    var sma = new SMA({period : period, values : prices});
    sma.getResult(); // [5.5, 6.6, 7.7, 8.9]
    sma.nextValue(16); // 10.1
    ```

    Note: Calling nextValue will not update getResult() value.

### Precision

This uses regular javascript numbers, so there can be rounding errors which are negligible for a technical indicators, you can set precision by using the below config. By default there is no precision set.

  ``` javascript
  const technicalIndicators = require('technicalindicators');
  technicalIndicators.setConfig('precision', 10);
  ```


# Contribute

Create issues about anything you want to report, change of API's, or request for adding new indicators. You can also create pull request with new indicators.

## Environment dependencies

Typescript: Use typescript 2.0.0 other you might get max call stack reached error.

``` npm install -g typescript@2.0.0 ```

TechnicalIndicators depends on the [`canvas` package](https://npmjs.com/canvas), which requires some dependencies to be installed. You can find the instructions to do that [here](https://github.com/Automattic/node-canvas#installation). If you do not install these dependencies, expect to get this error message during the installation of TechnicalIndicators:

```
> canvas@1.6.6 install /Users/balupton/Projects/trading/technicalindicators/node_modules/canvas
> node-gyp rebuild

./util/has_lib.sh: line 31: pkg-config: command not found
gyp: Call to './util/has_lib.sh freetype' returned exit status 0 while in binding.gyp. while trying to load binding.gyp
```

## Setup

``` bash
git clone git@github.com:asimasim84/technicalindicators.git  # or use your fork
cd technicalindicators
npm run start
```

## Running tests and getting coverage

``` bash
npm test
npm run cover
```

## Adding new indicators

1. Add tests for the indicator and make them pass.
   (It would be better if a sample of the stockcharts excel is used for the test case.)
1. Add the indicator to the `index.js` and `src/index.ts`
1. Run build scripts: `npm run build-lib && npm run generateDts && npm run start`
1. Add it to `README.md`, with the link to the runkit url containing the sample.
1. Add indicator it to keywords in `package.json` and `bower.json`
1. Send a Pull Request.


## Verify Documentation

``` bash
node testdocs.js
open "http://localhost:5444/testdocs.html"
```


# Donate
1. XRB: `xrb_1shh8i77upiq4bjzi3ajik9ofq14bbcucshoapi3m7f8d74dc5k31o56yj5r`
1. ETH: `0x0B56580Eb25f3F7e366dDA697161d314C17Bcb6a`
1. LTC: `LLTUhKBRKs9sbW9F8MFQm7VVdZ1dJnXzGc`
1. BTC: `1FGeJHoj7tjeLrm4JNtyPWTdBKPJjcqP6Y`
1. BCH: `1AUFc8CEfHVjnoixbqTbX62WV8DZkpC1DU`
