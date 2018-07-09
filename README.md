[![Build Status](https://travis-ci.org/pelevesque/find-duplicates.svg?branch=master)](https://travis-ci.org/pelevesque/find-duplicates)
[![Coverage Status](https://coveralls.io/repos/github/pelevesque/find-duplicates/badge.svg?branch=master)](https://coveralls.io/github/pelevesque/find-duplicates?branch=master)
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

# find-duplicates

Finds indices of duplicates in an array of elements.

## Node Repository

[https://www.npmjs.com/package/@pelevesque/find-duplicates](https://www.npmjs.com/package/@pelevesque/find-duplicates)

## Installation

`npm install @pelevesque/find-duplicates`

## Tests

### Standard Style & Unit Tests

`npm test`

### Standard Style & Unit Tests & Coverage

`npm run cover`

### Usage

#### Requiring the Module

```js
const findDuplicates = require('@pelevesque/find-duplicates')
```

#### One Set of Duplicates

```js
const elements = [
  'd131dd02c5e6eec4', // a
  '55ad340609f4b302',
  'd131dd02c5e6eec4', // a
  'd131dd02c5e6eec4', // a
  'd8823e3156348f5b'
]
const result = findDuplicates(elements)
// result === [[0, 2, 3]]
```

#### Many Sets of Duplicates

```js
const elements = [
  'd131dd02c5e6eec4', // a
  '55ad340609f4b302',
  'd8823e3156348f5b', // b
  'd131dd02c5e6eec4', // a
  'd8823e3156348f5b', // b
  '551111111114b302', // c
  '551111111114b302'  // c
]
const result = findDuplicates(elements)
// result === [[0, 3], [2, 4], [5, 6]]
```

#### Using the stopAtFirstSet Flag

```js
// When using the stopAtFirstSet flag, only the first set is returned.
// Note: In this case, an array is returned instead of an array of arrays.
const elements = [
  'd131dd02c5e6eec4', // a
  '55ad340609f4b302',
  'd8823e3156348f5b', // b
  'd131dd02c5e6eec4', // a
  'd8823e3156348f5b', // b
  '551111111114b302', // c
  '551111111114b302'  // c
]
const stopAtFirstSet = true
const result = findDuplicates(elements, stopAtFirstSet)
// result === [0, 3]
```
