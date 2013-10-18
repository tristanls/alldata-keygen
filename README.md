# alldata-keygen

_Stability: 1 - [Experimental](https://github.com/tristanls/stability-index#stability-1---experimental)_

[![NPM version](https://badge.fury.io/js/alldata-keygen.png)](http://npmjs.org/package/alldata-keygen)

Key generation module for [AllData](https://github.com/tristanls/alldata), a distributed master-less append-only immutable event store database implementing "All Data" part of [Lambda Architecture](http://www.slideshare.net/nathanmarz/runaway-complexity-in-big-data-and-a-plan-to-stop-it).

## Usage

```javascript
var AllDataKeygen = require('alldata-keygen');
var key = AllDataKeygen.createKey();
// 20130927T005240652508858176
```

## Test

    npm test

## Overview

AllDataKeygen generates a unique key for every event to be stored in AllData.

## Documentation

### AllDataKeygen

**Public API**

  * [AllDataKeygen.createKey()](#alldatakeygencreatekey)

#### AllDataKeygen.createKey()

Creates a new key. Example: `20130927T005240652508858176`.

Format is `YYYYMMDDThhmmsslllnnnnnnnnn`:

  * `YYYY` current UTC year
  * `MM` current UTC month
  * `DD` current UTC day
  * `T` time separator
  * `hh` current UTC hours
  * `mm` current UTC minutes
  * `ss` current UTC seconds
  * `lll` current UTC milliseconds
  * `nnnnnnnnn` nanoseconds "unique" marker from `process.hrtime()[1]`; could be less than 9 digits